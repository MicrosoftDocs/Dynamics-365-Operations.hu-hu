---
title: Egyéni tárhelyek meghatározása a létrehozott dokumentumoknak
description: Ez a témakör ismerteti, hogyan bővítheti a dokumentumok tárolóhelyeinek listáját, amelyeket az elektronikus jelentési (ER) formátumok hoztak létre.
author: NickSelin
ms.date: 10/29/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-3-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 25719de3d86785442e00f7375de525b95bdb094d
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5753696"
---
# <a name="specify-custom-storage-locations-for-generated-documents"></a>Egyéni tárhelyek meghatározása a létrehozott dokumentumoknak

[!include[banner](../includes/banner.md)]

A alkalmazásprogramozási felület (API) az Elektronikus jelentéskészítéshez (ER) lehetővé teszi a tárolóhelyek listájának kibővítését ER formátumok által létrehozott dokumentumokhoz.. Ez a témakör bemutatja, hogyan adhat hozzá egyéni tárolási helyet a létrehozott dokumentumokhoz úgy, hogy az ER célhelyek létrehozásának feladatát átadja az alapértelmezett célgyárnak, majd egy egyéni osztály megvalósításával, amely saját céllogikával rendelkezik.

## <a name="prerequisites"></a>Előfeltételek

Telepít egy topológiát, amely támogatja a folyamatos buildet. A további tudnivalókért lásd: [A folyamatos build- és tesztautomatizálást támogató topológiák telepítése](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/perf-test/continuous-build-test-automation). A topológiához a következő szerepkörök egyikével kell rendelkezzen hozzáféréssel:

- Elektronikus jelentések fejlesztője
- Elektronikus jelentések funkcióival foglalkozó konzulens
- Rendszergazda

Ezen topológia fejlesztői környezetéhez való hozzáféréssel is kell rendelkezzen.

A témakörben szereplő összes feladat elvégezhető az **USMF** vállalatnál.

## <a name="import-the-fixed-asset-roll-forward-er-format"></a>A tárgyieszköz-meghosszabbítás ER formátum importálása

Az egyéni tárolási helyhez hozzáadására szánt dokumentumok létrehozásához [importálja](er-download-configurations-global-repo.md) a **Tárgyieszköz-meghosszabbítás** ER formátumkonfigurációt az aktuális topológiába.

![Konfigurációk tárháza oldal](./media/er-custom-storage-generated-files-import-format.png)

## <a name="run-the-fixed-asset-roll-forward-report"></a>Jelentés tárgyi eszközök előregörgetéséről futtatása

1. Nyissa meg a **Tárgyi eszközök** \> **Lekérdezések és jelentések** \> **Tranzakciójelentések** \> **Tárgyieszköz-előregörgetés** menüpontot.
2. Adjon meg **1/1/2017** (2017. január 1.) dátumot a **Kezdő dátum** mezőben.
3. Adjon meg **1/31/2017** (2017. január 31.) dátumot a **Befejező dátum** mezőben.
4. A **Pénznem mezőben** válassza ki a **Könyvelési pénznemet**.
5. A **Formátumleképezés** mezőben válassza a **Tárgyi eszköz előregörgetés** lehetőséget.
6. Válassza ki az **OK** lehetőséget.

![Futásidejű párbeszédpanel a Tárgyi eszköz előregörgetése jelentéshez](./media/er-custom-storage-generated-files-runtime-dialog.png)

A Microsoft Excel alkalmazásban tekintse át a létrehozott és letölthető kimenő dokumentumot. Ez a viselkedés az [alapértelmezett viselkedés](electronic-reporting-destinations.md#default-behavior) egy olyan ER-formátumnál, amelyhez nincsenek [célhelyek](electronic-reporting-destinations.md) konfigurálva, és amely interaktív módban fut.

## <a name="review-the-source-code"></a>A forráskód áttekintése

Tekintse át a kódot a `generateReportByGER()` metódusban az `AssetRollForwardService` osztályban. Figyelje meg, hogy a `Run()` metódus az ER keretrendszer hívására és a **Tárgyi eszközök előregörgetése** jelentés generálására szolgál.

```xpp
class AssetRollForwardService extends SysOperationServiceBase
{
    public const str ERFormatModelName = 'Fixed assets';
    public const str ERModelDataSourceName = 'model';
    public const str DefaultExportedFileName = 'AssetRollForward';

    /// <summary>
    /// Generates report by general electronic reporting
    /// </summary>
    /// <param name = "_contract">The Asset Period Statement contract</param>
    public void generateReportByGER(AssetRollForwardContract _contract)
    {
        ERFormatMappingId   formatMappingId;
        AssetRollForwardDP  dataProvider;
        AssetRollForwardTmp assetRollForwardTmp;
        Query               query;

        query = new Query(SysOperationHelper::base64Decode(_contract.parmQuery()));
        dataProvider = AssetRollForwardDP::construct();
        formatMappingId = _contract.parmFormatMapping();
        assetRollForwardTmp = dataProvider.getAssetRollForwardTmp(_contract, query);

        if (assetRollForwardTmp)
        {
            try
            {
                ERIModelDefinitionParamsAction parameters = new ERModelDefinitionParamsUIActionComposite()
                    .add(new ERModelDefinitionDatabaseContext().addTemporaryTable(assetRollForwardTmp))
                    .add(new ERModelDefinitionObjectParameterAction(ERModelDataSourceName, 'MyParameters', _contract, true));

                // Call ER to generate the report.
                ERObjectsFactory::createFormatMappingRunByFormatMappingId(formatMappingId, DefaultExportedFileName)
                    .withParameter(parameters)
                    .withFileDestination(_contract.getFileDestination())
                    .run();
            }
            catch
            {
                // An error occurred while exporting data.
                error("@SYP4861341");
            }
        }
        else
        {
            // There is no data available.
            info("@SYS300117");
        }
    }
}
```

## <a name="modify-the-source-code"></a>A forráskód módosítása

1. A Visual Studio-projektben adjon hozzá egy új osztályt (`AssetRollForwardDestination` ebben a példában), és írja meg a kódot, hogy implementálja az egyéni célhelyet a **Tárgyi eszköz előregörgetés** jelentések generálásához.

    - A `new()` metódus úgy van kialakítva, hogy beolvassa az eredeti ER célhely tárgyát és az alkalmazás logikája által diktált paramétert, amely meghatározza, hogy a rendszer mely egyéni helyen tárolja a jelentéseket. Ebben a példában az egyéni hely a kiszolgáló helyi fájlrendszerének azon mappájának neve, amely az Alkalmazásobjektum-kiszolgáló (AOS) szolgáltatást futtatja.
    - A `saveFile()` metódus úgy van kialakítva, hogy a létrejövő dokumentumot az AOS szolgáltatást futtató kiszolgáló helyi fájlrendszerének mappájába mentse.

    ```xpp
    using Microsoft.Dynamics365.LocalizationFramework;

    /// <summary>
    /// Destination class for <c>AssetRollForwardDestinationFactory</c> that stores a generated report.
    /// </summary>
    public class AssetRollForwardDestination implements ERIFileDestination
    {
        private ERIFileDestination originDestination;
        private str TargetFolder;

        /// <summary>
        /// Creates a stream for new file.
        /// </summary>
        /// <param name = "_fileName">Name of a new file.</param>
        /// <returns>Stream for new file.</returns>
        public System.IO.Stream newFileStream(System.String _fileName)
        {
            return originDestination.newFileStream(_fileName);
        }

        /// <summary>
        /// Saves file in destination.
        /// </summary>
        /// <param name = "_stream">A stream to save.</param>
        /// <param name = "_fileName">A file name.</param>
        /// <returns>Saved stream.</returns>
        public System.IO.Stream saveFile(System.IO.Stream _stream, System.String _fileName)
        {
            _stream.Seek(0, System.IO.SeekOrigin::Begin);
            using (var localStream = System.IO.File::OpenWrite(TargetFolder + _fileName))
            {
                _stream.CopyTo(localStream);
            }
            return _stream;
        }

        /// <summary>
        /// Constructs destination for fixed asset roll forward report.
        /// </summary>
        /// <param name = "_originDestination">The original destination.</param>
        /// <param name = "_TargetFoder">The folder to store a report that's being created.</param>
        /// <returns>The fixed asset roll forward destination.</returns>
        public static AssetRollForwardDestination construct(ERIFileDestination _originDestination, str _TargetFoder)
        {
            return new AssetRollForwardDestination(_originDestination, _TargetFoder);
        }

        protected void new(ERIFileDestination _originDestination, str _TargetFoder)
        {
            originDestination = _originDestination;
            TargetFolder = _TargetFoder;
        }
    }
    ```

2. A Visual Studio projektben adjon hozzá egy új osztályt (ebben a példában `AssetRollForwardDestinationFactory`), és írja meg a kódot egy egyéni célgyár beállításához, amely delegálja a célhely létrehozását az alapértelmezett célgyár számára, és tördelje a fájl célhelyét a saját célhelyével.

    ```xpp
    using Microsoft.Dynamics365.LocalizationFramework;
    using Microsoft.Dynamics365.LocalizationFramework.Format.FileGeneration;

    /// <summary>
    /// Destination factory for using <c>AssetRollForwardDestinationFactory</c>.
    /// </summary>
    public class AssetRollForwardDestinationFactory implements ERIFileDestinationFactory, ERIFileDestinationFactoryPostProcessor
    {
        private ERIFileDestinationFactory originDestinationFactory;
        private str TargetFolder;

        /// <summary>
        /// Creates file destination for print management.
        /// </summary>
        /// <param name = "_fileDestination">A default file destination.</param>
        /// <param name = "_identification">An identification strategy.</param>
        /// <param name = "_rootContext">A root context.</param>
        /// <param name = "_root">A root element.</param>
        /// <returns>A file destination.</returns>
        public ERIDataDrivenFileDestination createPrintMgmtDestination(
            ERIFileDestination _fileDestination,
            ERIObjectIdentificationStrategy _identification,
            ERTextFormatDataContext _rootContext,
            ERTextFormatIFileComponent _root)
        {
            ERIDataDrivenFileDestination dataDrivenDestination = originDestinationFactory.createPrintMgmtDestination(
                _fileDestination,
                _identification,
                _rootContext,
                _root);

            IFileDestinationHost fileDestinationHost = dataDrivenDestination as IFileDestinationHost;
            if (fileDestinationHost)
            {
                fileDestinationHost.FileDestination = AssetRollForwardDestination::construct(
                    fileDestinationHost.get_FileDestination(),
                    TargetFolder);
            }

            return dataDrivenDestination;
        }

        /// <summary>
        /// Constructs the fixed asset roll forward destination factory.
        /// </summary>
        /// <param name = "_originDestinationFactory">The original destination.</param>
        /// <param name = "_TargetFolder">The string containing a folder name that corresponds to the report, that's being created.</param>
        /// <returns>The destination factory for the fixed asset roll forward report.</returns>
        public static AssetRollForwardDestinationFactory construct(ERIFileDestinationFactory _originDestinationFactory, str _TargetFolder)
        {
            AssetRollForwardDestinationFactory destinationFactory = new AssetRollForwardDestinationFactory(_originDestinationFactory, _TargetFolder);

            ERIFileDestinationFactoryPostProcessorsHost factoryPostProcessing = ERCast::asObject(destinationFactory.originDestinationFactory) as ERIFileDestinationFactoryPostProcessorsHost;

            if (factoryPostProcessing)
            {
                factoryPostProcessing.addDestinationPostProcessor(destinationFactory);
            }
            return destinationFactory;
        }

        public ERIFileDestination processDestinationAfterCreation(ERIFileDestination _sourceDestination)
        {
            return AssetRollForwardDestination::construct(_sourceDestination, TargetFolder);
        }

        protected void new(ERIFileDestinationFactory _originDestinationFactory, str _TargetFolder)
        {
            originDestinationFactory = _originDestinationFactory;
            TargetFolder = _TargetFolder;
        }
    }
    ```

3. Módosítsa a meglévő `AssetRollForwardService` osztályt, és írja meg kódot az egyéni cél-gyár beállításához a jelentésfuttatóhoz. Figyelje meg, hogy egy egyéni cél-gyár létrehozásakor az alkalmazás által vezérelt paraméter, amely meghatároz egy célmappát át lesz adva. Ily módon a célmappa a létrejövő fájlok tárolásához használatos.

    > [!NOTE] 
    > Győződjön meg róla, hogy a megadott mappa (**c:\\0**, ebben a példában) szerepel az AOS szolgáltatást futtató kiszolgáló helyi fájlrendszerében. Ellenkező esetben egy [DirectoryNotFoundException](https://docs.microsoft.com/dotnet/api/system.io.directorynotfoundexception?view=netcore-3.1) kivétel fog megjelenni futásidőben.

    ```xpp
    using Microsoft.Dynamics365.LocalizationFramework;
    /// <summary>
    /// The electronic reporting service class for fixed asset roll forward report
    /// </summary>
    class AssetRollForwardService extends SysOperationServiceBase
    {
        public const str ERFormatModelName = 'Fixed assets';
        public const str ERModelDataSourceName = 'model';
        public const str DefaultExportedFileName = 'AssetRollForward';

        /// <summary>
        /// Generates report by general electronic reporting
        /// </summary>
        /// <param name = "_contract">The Asset Period Statement contract</param>
        public void generateReportByGER(AssetRollForwardContract _contract)
        {
            ERFormatMappingId   formatMappingId;
            AssetRollForwardDP  dataProvider;
            AssetRollForwardTmp assetRollForwardTmp;
            Query               query;

            query = new Query(SysOperationHelper::base64Decode(_contract.parmQuery()));
            dataProvider = AssetRollForwardDP::construct();
            formatMappingId = _contract.parmFormatMapping();
            assetRollForwardTmp = dataProvider.getAssetRollForwardTmp(_contract, query);

            if (assetRollForwardTmp)
            {
                try
                {
                    ERIModelDefinitionParamsAction parameters = new ERModelDefinitionParamsUIActionComposite()
                        .add(new ERModelDefinitionDatabaseContext().addTemporaryTable(assetRollForwardTmp))
                        .add(new ERModelDefinitionObjectParameterAction(ERModelDataSourceName, 'MyParameters', _contract, true));

                    // Call ER to generate the report.
                    ERIFormatMappingRun formatMappingRun = ERObjectsFactory::createFormatMappingRunByFormatMappingId(formatMappingId, DefaultExportedFileName);
                    formatMappingRun.withParameter(parameters);
                    formatMappingRun.withFileDestination(_contract.getFileDestination());

                    ERIFileDestinationFactoryHost factoryHost = ERCast::asObject(formatMappingRun) as ERIFileDestinationFactoryHost;
                    if (factoryHost)
                    {
                        ERIFileDestinationFactory fileDestinationFactory = factoryHost.getFileDestinationFactory();
                        factoryHost.setFileDestinationFactory(AssetRollForwardDestinationFactory::construct(fileDestinationFactory, @'c:\0\'));
                        formatMappingRun.run();
                    }
                }
                catch
                {
                    // An error occurred while exporting data.
                    error("@SYP4861341");
                }
            }
            else
            {
                // There is no data available.
                info("@SYS300117");
            }
        }
    }
    ```

4. Építse újra projektjét.

## <a name="re-run-the-fixed-asset-roll-forward-report"></a>Jelentés tárgyi eszközök előregörgetéséről újrafuttatása

1. Nyissa meg a **Tárgyi eszközök** \> **Lekérdezések és jelentések** \> **Tranzakciójelentések** \> **Tárgyieszköz-előregörgetés** menüpontot.
2. A **Kezdő dátum** mezőben adja meg az **1/1/2017**-es számot.
3. A **Befejező dátum** mezőben adja meg az **1/31/2017**-es számot.
4. A **Pénznem mezőben** válassza ki a **Könyvelési pénznemet**.
5. A **Formátumleképezés** mezőben válassza a **Tárgyi eszköz előregörgetés** lehetőséget.
6. Válassza ki az **OK** lehetőséget.
7. Tekintse át a helyi **C:\\0** mappát a generált fájl megkereséséhez.

> [!NOTE]
> Mivel a `originDestination` objektum nem szerepel ebben a példában az `AssetRollForwardDestination` objektumban, az ER formátum [célhelyek](electronic-reporting-destinations.md) figyelmen kívül lesz hagyva futásidőben.

## <a name="additional-resources"></a>További erőforrások

- [Elektronikus jelentéskészítés (ER) céljai](electronic-reporting-destinations.md)
- [Bővíthetőség kezdőlap](../extensibility/extensibility-home-page.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]