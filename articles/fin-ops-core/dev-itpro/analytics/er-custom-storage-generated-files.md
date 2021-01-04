---
title: Egyéni tárhelyek meghatározása a létrehozott dokumentumoknak
description: Ez a témakör ismerteti, hogyan bővítheti a dokumentumok tárolóhelyeinek listáját, amelyeket az elektronikus jelentési (ER) formátumok hoztak létre.
author: NickSelin
manager: AnnBe
ms.date: 10/29/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-3-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 362ac7f10cc61e26be89dfbae0e84745d42588a3
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/05/2020
ms.locfileid: "4680758"
---
# <a name="specify-custom-storage-locations-for-generated-documents"></a><span data-ttu-id="cd189-103">Egyéni tárhelyek meghatározása a létrehozott dokumentumoknak</span><span class="sxs-lookup"><span data-stu-id="cd189-103">Specify custom storage locations for generated documents</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="cd189-104">A alkalmazásprogramozási felület (API) az Elektronikus jelentéskészítéshez (ER) lehetővé teszi a tárolóhelyek listájának kibővítését ER formátumok által létrehozott dokumentumokhoz..</span><span class="sxs-lookup"><span data-stu-id="cd189-104">The application programming interface (API) of the Electronic reporting (ER) framework lets you extend the list of storage locations for documents that ER formats generate.</span></span> <span data-ttu-id="cd189-105">Ez a témakör bemutatja, hogyan adhat hozzá egyéni tárolási helyet a létrehozott dokumentumokhoz úgy, hogy az ER célhelyek létrehozásának feladatát átadja az alapértelmezett célgyárnak, majd egy egyéni osztály megvalósításával, amely saját céllogikával rendelkezik.</span><span class="sxs-lookup"><span data-stu-id="cd189-105">This topic explains how to add a custom storage location for generated documents by delegating the task of creating ER destinations to the default destination factory and then implementing a custom class that has its own destination logic.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="cd189-106">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="cd189-106">Prerequisites</span></span>

<span data-ttu-id="cd189-107">Telepít egy topológiát, amely támogatja a folyamatos buildet.</span><span class="sxs-lookup"><span data-stu-id="cd189-107">Deploy a topology that supports continuous build.</span></span> <span data-ttu-id="cd189-108">A további tudnivalókért lásd: [A folyamatos build- és tesztautomatizálást támogató topológiák telepítése](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/perf-test/continuous-build-test-automation).</span><span class="sxs-lookup"><span data-stu-id="cd189-108">For more information, see [Deploy topologies that support continuous build and test automation](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/perf-test/continuous-build-test-automation).</span></span> <span data-ttu-id="cd189-109">A topológiához a következő szerepkörök egyikével kell rendelkezzen hozzáféréssel:</span><span class="sxs-lookup"><span data-stu-id="cd189-109">You must have access to this topology for one of the following roles:</span></span>

- <span data-ttu-id="cd189-110">Elektronikus jelentések fejlesztője</span><span class="sxs-lookup"><span data-stu-id="cd189-110">Electronic reporting developer</span></span>
- <span data-ttu-id="cd189-111">Elektronikus jelentések funkcióival foglalkozó konzulens</span><span class="sxs-lookup"><span data-stu-id="cd189-111">Electronic reporting functional consultant</span></span>
- <span data-ttu-id="cd189-112">Rendszergazda</span><span class="sxs-lookup"><span data-stu-id="cd189-112">System administrator</span></span>

<span data-ttu-id="cd189-113">Ezen topológia fejlesztői környezetéhez való hozzáféréssel is kell rendelkezzen.</span><span class="sxs-lookup"><span data-stu-id="cd189-113">You must also have access to the development environment for this topology.</span></span>

<span data-ttu-id="cd189-114">A témakörben szereplő összes feladat elvégezhető az **USMF** vállalatnál.</span><span class="sxs-lookup"><span data-stu-id="cd189-114">All the tasks in this topic can be completed in the **USMF** company.</span></span>

## <a name="import-the-fixed-asset-roll-forward-er-format"></a><span data-ttu-id="cd189-115">A tárgyieszköz-meghosszabbítás ER formátum importálása</span><span class="sxs-lookup"><span data-stu-id="cd189-115">Import the Fixed asset roll forward ER format</span></span>

<span data-ttu-id="cd189-116">Az egyéni tárolási helyhez hozzáadására szánt dokumentumok létrehozásához [importálja](er-download-configurations-global-repo.md) a **Tárgyieszköz-meghosszabbítás** ER formátumkonfigurációt az aktuális topológiába.</span><span class="sxs-lookup"><span data-stu-id="cd189-116">To generate the documents that you plan to add a custom storage location for, [import](er-download-configurations-global-repo.md) the **Fixed asset roll forward** ER format configuration into the current topology.</span></span>

![Konfigurációk tárháza oldal](./media/er-custom-storage-generated-files-import-format.png)

## <a name="run-the-fixed-asset-roll-forward-report"></a><span data-ttu-id="cd189-118">Jelentés tárgyi eszközök előregörgetéséről futtatása</span><span class="sxs-lookup"><span data-stu-id="cd189-118">Run the Fixed asset roll forward report</span></span>

1. <span data-ttu-id="cd189-119">Nyissa meg a **Tárgyi eszközök** \> **Lekérdezések és jelentések** \> **Tranzakciójelentések** \> **Tárgyieszköz-előregörgetés** menüpontot.</span><span class="sxs-lookup"><span data-stu-id="cd189-119">Go to **Fixed assets** \> **Inquiries and reports** \> **Transaction reports** \> **Fixed asset roll forward**.</span></span>
2. <span data-ttu-id="cd189-120">Adjon meg **1/1/2017** (2017. január 1.) dátumot a **Kezdő dátum** mezőben.</span><span class="sxs-lookup"><span data-stu-id="cd189-120">In the **From date** field, enter **1/1/2017** (January 1, 2017).</span></span>
3. <span data-ttu-id="cd189-121">Adjon meg **1/31/2017** (2017. január 31.) dátumot a **Befejező dátum** mezőben.</span><span class="sxs-lookup"><span data-stu-id="cd189-121">In the **To date** field, enter **1/31/2017** (January 31, 2017).</span></span>
4. <span data-ttu-id="cd189-122">A **Pénznem mezőben** válassza ki a **Könyvelési pénznemet**.</span><span class="sxs-lookup"><span data-stu-id="cd189-122">In the **Currency field**, select **Accounting currency**.</span></span>
5. <span data-ttu-id="cd189-123">A **Formátumleképezés** mezőben válassza a **Tárgyi eszköz előregörgetés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="cd189-123">In the **Format mapping** field, select **Fixed asset roll forward**.</span></span>
6. <span data-ttu-id="cd189-124">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="cd189-124">Select **OK**.</span></span>

![Futásidejű párbeszédpanel a Tárgyi eszköz előregörgetése jelentéshez](./media/er-custom-storage-generated-files-runtime-dialog.png)

<span data-ttu-id="cd189-126">A Microsoft Excel alkalmazásban tekintse át a létrehozott és letölthető kimenő dokumentumot.</span><span class="sxs-lookup"><span data-stu-id="cd189-126">In Microsoft Excel, review the outbound document that is generated and available for download.</span></span> <span data-ttu-id="cd189-127">Ez a viselkedés az [alapértelmezett viselkedés](electronic-reporting-destinations.md#default-behavior) egy olyan ER-formátumnál, amelyhez nincsenek [célhelyek](electronic-reporting-destinations.md) konfigurálva, és amely interaktív módban fut.</span><span class="sxs-lookup"><span data-stu-id="cd189-127">This behavior is the [default behavior](electronic-reporting-destinations.md#default-behavior) for an ER format that no [destinations](electronic-reporting-destinations.md) are configured for, and that is running in interactive mode.</span></span>

## <a name="review-the-source-code"></a><span data-ttu-id="cd189-128">A forráskód áttekintése</span><span class="sxs-lookup"><span data-stu-id="cd189-128">Review the source code</span></span>

<span data-ttu-id="cd189-129">Tekintse át a kódot a `generateReportByGER()` metódusban az `AssetRollForwardService` osztályban.</span><span class="sxs-lookup"><span data-stu-id="cd189-129">Review the code of the `generateReportByGER()` method of the `AssetRollForwardService` class.</span></span> <span data-ttu-id="cd189-130">Figyelje meg, hogy a `Run()` metódus az ER keretrendszer hívására és a **Tárgyi eszközök előregörgetése** jelentés generálására szolgál.</span><span class="sxs-lookup"><span data-stu-id="cd189-130">Notice that the `Run()` method is used to call the ER framework and generate the **Fixed asset roll forward** report.</span></span>

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

## <a name="modify-the-source-code"></a><span data-ttu-id="cd189-131">A forráskód módosítása</span><span class="sxs-lookup"><span data-stu-id="cd189-131">Modify the source code</span></span>

1. <span data-ttu-id="cd189-132">A Visual Studio-projektben adjon hozzá egy új osztályt (`AssetRollForwardDestination` ebben a példában), és írja meg a kódot, hogy implementálja az egyéni célhelyet a **Tárgyi eszköz előregörgetés** jelentések generálásához.</span><span class="sxs-lookup"><span data-stu-id="cd189-132">In your Visual Studio project, add a new class (`AssetRollForwardDestination` in this example), and write code to implement your custom destination for **Fixed asset roll forward** reports that are generated.</span></span>

    - <span data-ttu-id="cd189-133">A `new()` metódus úgy van kialakítva, hogy beolvassa az eredeti ER célhely tárgyát és az alkalmazás logikája által diktált paramétert, amely meghatározza, hogy a rendszer mely egyéni helyen tárolja a jelentéseket.</span><span class="sxs-lookup"><span data-stu-id="cd189-133">The `new()` method is designed to get the original ER destination object and the application logic–driven parameter that specifies the custom location where generated reports should be stored.</span></span> <span data-ttu-id="cd189-134">Ebben a példában az egyéni hely a kiszolgáló helyi fájlrendszerének azon mappájának neve, amely az Alkalmazásobjektum-kiszolgáló (AOS) szolgáltatást futtatja.</span><span class="sxs-lookup"><span data-stu-id="cd189-134">In this example, the custom location is the name of a folder of the local file system of the server that runs the Application Object Server (AOS) service.</span></span>
    - <span data-ttu-id="cd189-135">A `saveFile()` metódus úgy van kialakítva, hogy a létrejövő dokumentumot az AOS szolgáltatást futtató kiszolgáló helyi fájlrendszerének mappájába mentse.</span><span class="sxs-lookup"><span data-stu-id="cd189-135">The `saveFile()` method is designed to save a generated document to a folder of the local file system of the server that runs the AOS service.</span></span>

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

2. <span data-ttu-id="cd189-136">A Visual Studio projektben adjon hozzá egy új osztályt (ebben a példában `AssetRollForwardDestinationFactory`), és írja meg a kódot egy egyéni célgyár beállításához, amely delegálja a célhely létrehozását az alapértelmezett célgyár számára, és tördelje a fájl célhelyét a saját célhelyével.</span><span class="sxs-lookup"><span data-stu-id="cd189-136">In your Visual Studio project, add a new class (`AssetRollForwardDestinationFactory` in this example), and write code to set up a custom destination factory that delegates the creation of a destination to the default destination factory, and to wrap a file destination with your own destination.</span></span>

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

3. <span data-ttu-id="cd189-137">Módosítsa a meglévő `AssetRollForwardService` osztályt, és írja meg kódot az egyéni cél-gyár beállításához a jelentésfuttatóhoz.</span><span class="sxs-lookup"><span data-stu-id="cd189-137">Modify the existing `AssetRollForwardService` class, and write code to set up a custom destination factory for the report runner.</span></span> <span data-ttu-id="cd189-138">Figyelje meg, hogy egy egyéni cél-gyár létrehozásakor az alkalmazás által vezérelt paraméter, amely meghatároz egy célmappát át lesz adva.</span><span class="sxs-lookup"><span data-stu-id="cd189-138">Notice that when a custom destination factory is constructed, the application-driven parameter that specifies a target folder is passed.</span></span> <span data-ttu-id="cd189-139">Ily módon a célmappa a létrejövő fájlok tárolásához használatos.</span><span class="sxs-lookup"><span data-stu-id="cd189-139">In this way, that target folder is used to store generated files.</span></span>

    > [!NOTE] 
    > <span data-ttu-id="cd189-140">Győződjön meg róla, hogy a megadott mappa (**c:\\0**, ebben a példában) szerepel az AOS szolgáltatást futtató kiszolgáló helyi fájlrendszerében.</span><span class="sxs-lookup"><span data-stu-id="cd189-140">Make sure that the specified folder (**c:\\0** in this example) is present in the local file system of the server that runs the AOS service.</span></span> <span data-ttu-id="cd189-141">Ellenkező esetben egy [DirectoryNotFoundException](https://docs.microsoft.com/dotnet/api/system.io.directorynotfoundexception?view=netcore-3.1) kivétel fog megjelenni futásidőben.</span><span class="sxs-lookup"><span data-stu-id="cd189-141">Otherwise, a [DirectoryNotFoundException](https://docs.microsoft.com/dotnet/api/system.io.directorynotfoundexception?view=netcore-3.1) exception will be thrown at runtime.</span></span>

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

4. <span data-ttu-id="cd189-142">Építse újra projektjét.</span><span class="sxs-lookup"><span data-stu-id="cd189-142">Rebuild your project.</span></span>

## <a name="re-run-the-fixed-asset-roll-forward-report"></a><span data-ttu-id="cd189-143">Jelentés tárgyi eszközök előregörgetéséről újrafuttatása</span><span class="sxs-lookup"><span data-stu-id="cd189-143">Re-run the Fixed asset roll forward report</span></span>

1. <span data-ttu-id="cd189-144">Nyissa meg a **Tárgyi eszközök** \> **Lekérdezések és jelentések** \> **Tranzakciójelentések** \> **Tárgyieszköz-előregörgetés** menüpontot.</span><span class="sxs-lookup"><span data-stu-id="cd189-144">Go to **Fixed assets** \> **Inquiries and reports** \> **Transaction reports** \> **Fixed asset roll forward**.</span></span>
2. <span data-ttu-id="cd189-145">A **Kezdő dátum** mezőben adja meg az **1/1/2017**-es számot.</span><span class="sxs-lookup"><span data-stu-id="cd189-145">In the **From date** field, enter **1/1/2017**.</span></span>
3. <span data-ttu-id="cd189-146">A **Befejező dátum** mezőben adja meg az **1/31/2017**-es számot.</span><span class="sxs-lookup"><span data-stu-id="cd189-146">In the **To date** field, enter **1/31/2017**.</span></span>
4. <span data-ttu-id="cd189-147">A **Pénznem mezőben** válassza ki a **Könyvelési pénznemet**.</span><span class="sxs-lookup"><span data-stu-id="cd189-147">In the **Currency field**, select **Accounting currency**.</span></span>
5. <span data-ttu-id="cd189-148">A **Formátumleképezés** mezőben válassza a **Tárgyi eszköz előregörgetés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="cd189-148">In the **Format mapping** field, select **Fixed asset roll forward**.</span></span>
6. <span data-ttu-id="cd189-149">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="cd189-149">Select **OK**.</span></span>
7. <span data-ttu-id="cd189-150">Tekintse át a helyi **C:\\0** mappát a generált fájl megkereséséhez.</span><span class="sxs-lookup"><span data-stu-id="cd189-150">Browse the local **C:\\0** folder to find the generated file.</span></span>

> [!NOTE]
> <span data-ttu-id="cd189-151">Mivel a `originDestination` objektum nem szerepel ebben a példában az `AssetRollForwardDestination` objektumban, az ER formátum [célhelyek](electronic-reporting-destinations.md) figyelmen kívül lesz hagyva futásidőben.</span><span class="sxs-lookup"><span data-stu-id="cd189-151">Because the `originDestination` object isn't used in the `AssetRollForwardDestination` object in this example, the configurations for the ER format [destinations](electronic-reporting-destinations.md) will be ignored at runtime.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="cd189-152">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="cd189-152">Additional resources</span></span>

- [<span data-ttu-id="cd189-153">Elektronikus jelentéskészítés (ER) céljai</span><span class="sxs-lookup"><span data-stu-id="cd189-153">Electronic reporting (ER) destinations</span></span>](electronic-reporting-destinations.md)
- [<span data-ttu-id="cd189-154">Bővíthetőség kezdőlap</span><span class="sxs-lookup"><span data-stu-id="cd189-154">Extensibility home page</span></span>](../extensibility/extensibility-home-page.md)
