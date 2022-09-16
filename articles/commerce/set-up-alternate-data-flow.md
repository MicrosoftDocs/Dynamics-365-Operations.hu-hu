---
title: Ajánlásokhoz állítson be alternatív adatfolyamatot.
description: Ez a témakör azt ismerteti, hogyan kell konfigurálni egy környezetet egy alternatív adatforrás használatával, amely az adatokat szolgáltatja az ajánlásoknak.
author: bebeale
ms.date: 09/08/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.openlocfilehash: b507b9bb57c68aca9424b53f8ccc009efea733bc
ms.sourcegitcommit: f88273627ba105ede27f28fe67ccec2d7f78261c
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/09/2022
ms.locfileid: "9460103"
---
# <a name="set-up-an-alternate-dataflow-for-recommendations"></a>Ajánlásokhoz állítson be alternatív adatfolyamatot.

[!include [banner](includes/banner.md)]

Ez a témakör azt ismerteti, hogyan kell konfigurálni egy környezetet egy alternatív adatforrás használatával, amely az adatokat szolgáltatja az ajánlásoknak.

## <a name="comparison-of-out-of-the-box-dataflow-with-alternate-dataflow"></a>A dobozon túli adatfolyam összehasonlítása az alternatív adatforrással

A következő ábra a dobozonon túli adatáramlást ábrázolja egy környezetben.

![Környezetben való kis- és környezetkiáramlás](media/reco-out-of-the-box-dataflow-2.png)

A következő ábra egy másik adatfolyamot ábrázol, amelyben az entitástár szinkronizálási kötegelt feladata helyett alternatív adatfolyamati lépések vannak.

![Alternatív adatfolyam környezetben](media/reco-alternate-dataflow-2.png)

## <a name="assumptions"></a>Feltételezések

- Ez a cikk abból indul ki, hogy már engedélyezte az ajánlások szolgáltatását az ön környezetében. A további tudnivalókat lásd a Termék ajánlások [engedélyezése](enable-product-recommendations.md).
- Amikor fájlokkal és mappákkal dolgozik az adattároló Microsoft Azure fiókban:

    - Az Azure webes portál kezelőfelületét vagy az Azure Storage Explorer alkalmazást használhatja.
    - A fájlok és mappák **használata kiindulási pontjai a környezet URL-címének megfelelő nevű mappa alatti Dynamics365-financeandoperations** tárolóban találhatók.
    - Ha a üzenetdoboz-környezet neve **MyUAT**, a környezet alap URL-címe lesz `myuat.sandbox.operations.dynamics.com`.
    - Ha ugyanannak a tárolási fióknak több környezete van, mindegyik környezetnek saját gyökérmappja lesz.

## <a name="prerequisites"></a>Előfeltételek

Az alternatív adatforrás-megközelítés megvalósítása előtt teljesülnie kell a következő előfeltételeknek.

### <a name="set-up-microsoft-power-platform"></a>Microsoft Power Platform beállítása

A beállításhoz kövesse Microsoft Power Platform az Integráció engedélyezése [képernyőn található utasításokat Microsoft Power Platform](../fin-ops-core/dev-itpro/power-platform/enable-power-platform-integration.md).

### <a name="install-the-export-to-data-lake-add-in"></a>Az Adatakkre irányuló exportálás bővítmény telepítése

Ha telepíteni szeretne az Exportálás az Adatokba Bővítmény bővítményt, hajtsa [végre az Azure-fájlba történő exportálási bővítmény útmutatóját](../fin-ops-core/dev-itpro/data-entities/configure-export-data-lake.md).

> [!NOTE]
> Jegyezze fel a konfigurációs értékeket, mivel a következő lépésekhez szükség van rájuk.

### <a name="configure-tables-to-export-in-dynamics-365"></a>Táblák konfigurálása a Dynamics 365-ben történő exportáláshoz

A Dynamics 365 rendszerből való táblaszinkronizálást Azure Data Lake Storage az **Adatba exportálási fájlba lapon lehet** kezelni. Mivel az adott lapnak jelenleg nincs menüeleme, **csak** a Rendszergazda biztonsági szerepkör felhasználói nyitják meg.

A következő lépések szerint konfigurálhatja a táblákat a Dynamics 365-ben történő exportálásra.

1. Az Exportálás az Adathavi **lap** megnyitásához adja hozzá `?mi=DataFeedsDefinitionWorkspace` a karakterláncot a környezet alap URL-címéhez, amint azt a következő példa mutatja:

    `https://<environment-URL>/?mi=DataFeedsDefinitionWorkspace`

1. Az Adatexportál **lapon**, [és a cikk RetailSales](#list-of-retailsales-cube-tables) kockatáblák listájában felsorolt táblák másolása.
1. Bontsa **ki** a szűrőbeállítások listáját a Rendszernév oszlopban.
1. A szűrőtípus egyikének **kiválasztása**. Ezután helyezze a mutatót a szövegmezőbe, **és illessze be az Exportálás az Adatok tábláiba lapról átmásolt táblák** listáját.
1. A szűrőbeállítások listájának alján válassza az Alkalmaz **gombra**.
1. Jelölje ki a rács összes sorát, majd válassza az Aktiválás **lehetőséget**.

> [!NOTE]
> A következő lépésre való továbblépés előtt minden sort Futó állapotra kell **frissíteni**. A szükséges hibák elhárítása és megoldása.

### <a name="create-a-synapse-workspace"></a>Szintaktikás munkaterület létrehozása

A Szintaktikás munkaterület létrehozásához, ha még nem rendelkezik ilyen munkaterülettel, [kövesse a Gyorsindítás: Szintaktikás munkaterület létrehozása útmutatóban található utasításokat](/azure/synapse-analytics/quickstart-create-workspace).

Az Azure-erőforrások rendszerezése érdekében javasoljuk, hogy az Azure erőforráscsoportba helyezze az Adattároló és a Szintaktik típusú munkaterületet. Újra felhasználhatja azt a tárfiókot, amit az Adatexportba exportálási bővítmény telepítésekor hozott létre.

## <a name="create-a-database-in-synapse-for-recommendation-data-processing"></a>Adatbázis létrehozása a Szintaktikában ajánlási adatok feldolgozásához

A Közös adatmodell segédprogram konzolalkalmazás (CDMUtil_ConsoleApp) segítségével adatbázist hozhat létre a Szintakt táblában, és feltölti azt az adattároló közös adatmodell-tábláiból. Azt ajánljuk, hogy fejlesztési környezetben használja az adatbázishoz a Közös adatmodell segédprogramot, amennyiben van kiterjesztés.

> [!NOTE]
> A következő lépések feltételezik, hogy a RetailSales kockához nem ad hozzá bővítményadatokat.

A Következő lépések szerint hozhat létre adatbázist a Szintaktában.

1. Menjen a [Dynamics-365-FastTrack-Implementation-AssetsHub](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/tree/master/Analytics/CDMUtilSolution#2-cdmutil-console-app) parancsra, **és hajtsa végre a CDMUtilConsoleApp.zip** fájl letöltéséhez szükséges lépéseket.
1. Az irányítószám kibontése helyi mappába.
1. Nyissa meg **CDMUtil_ConsoleApp.dll.config fájlt** egy szövegszerkesztőben, és frissítse a következő értékeket:

    1. Adja meg **a bérlőazonosító** értékét (Azure-bérlőazonosító).
    1. Állítsa be **a Hozzáférési kulcs** értékét (az adattároló tárolófiók hozzáférési kulcsát).

        1. Nyissa meg saját tárolási fiókját az Azure-portálon.
        1. A lap bal oldalán található menüben válassza a Hozzáférési **kulcsokat**.
        1. A lap tetején válassza a Kulcsok **megjelenítése lehetőséget**.
        1. Válassza ki a másolás gombot a két kulcsmező egyikéhez, majd másolja be az értéket a konfigurációs fájlba a kettős idézőjelek közé.

    1. Állítsa a **ManifestURL értéket** a **Tables.manifest.cdm.json** fájl URL-címére a következőben Azure Data Lake Storage: Az URL-cím megtekintéséhez tallózással keresse meg a fájlt az Azure-portálon, válassza ki a nézet jobb oldalán látható három pontokat (**·**...**), majd válassza a Tulajdonságok lehetőséget**. Az URL-cím az Áttekintés lapon megjelenő első **tulajdonság**.
    1. Állítsa be **a TargetDbConnectionString** értéket a Szintiás munkaterület beépített kiszolgáló nélküli SQL-készletének kapcsolati karakterláncában.

        1. A Szintaktikás munkaterületen válassza a **Kezelés lapot**.
        1. Az almenüben válassza ki az SQL-készleteket **·**.
        1. Válassza a Beépített **név lehetőséget** a készlet tulajdonságainak megtekintéséhez.
        1. A tulajdonságok párbeszédpanelen válassza ki ADO.NET használni kívánt kapcsolattípust. Ezután másolja a kapcsolati karakterlánc értékét, és másolja át a konfigurációs fájlban található kettős idézőjelek közé.

        > [!NOTE]
        > Az adatbázisok létrehozásához engedéllyel kell rendelkeznie. A használat könnyebb használata érdekében érdemes **a beépített sqladminuser rendszergazdai** fiókot használni.

    1. **A ProcessEntities csomópont uncomment** beállítása igaz **értékre** (például`<add key="ProcessEntities" value ="true"/>`).

1. Mentse és zárja be a **CDMUtil_ConsoleApp.dll.config fájlt**.
1. **Az EntityList.json fájl másolása** a **/Manifest könyvtárba**.
1. A parancssori ablakban futtassa a **cdmutil_consoleapp.exe fájlt**.

> [!NOTE]
> A kimenet áttekintésekor 35 entitásnak/nézetnek, legalább 75 táblának kell lennie, és nincs hiba.

## <a name="prepare-the-data-lake-retailsales-aggregate-measurements-directory"></a>Az Adatok Kiskereskedelmisales összesítési mértékek könyvtárának előkészítése

### <a name="back-up-your-current-retailsales-cube-data-from-data-lake-storage"></a>Az aktuális RetailSales kockaadatok biztonsági létrehozása az adattárolóból

A jelenlegi RetailSales **kockaadatokról legegyszerűbben úgy lehet biztonsági másolatot készíteni, ha átnevezi a RetailSales** könyvtárat az Adattároló **RetailSales-biztonsági** másolatban, vagy valami hasonlót. Ez a módszer megtartja a meglévő adatokat, ha később szükséges a hibaelhárítás.

A **/RetailSales** kockamappa a következő helyen található:

`<storage-account>/dynamics365-financeandoperations/<environment-url (for example, myuat.sandbox.operations.dynamics.com)>/AggregateMeasurements/RetailSales`

### <a name="create-a-new-retailsales-folder-and-upload-the-model-file"></a>Új RetailSales mappa létrehozása és a modellfájl feltöltése

A következő lépések szerint **hozzon létre új RetailSales** **könyvtárat, és töltse fel a model.json** fájlt az Adattárolóba.

1. Hozzon létre egy új üres könyvtárat az előző könyvtárral azonos szinten, **és nevezze El RetailSales néven**.
1. Töltse fel **a model.json fájlt** az új könyvtárba.

## <a name="create-a-pipeline-to-copy-the-retailsales-cube-data"></a>Csővezeték létrehozása a RetailSales kocka adatainak másolása érdekében

A csővezeték beolvassa a RetailSales kockanézeteket, és az adatokat .csv fájlokba exportálja az adattárolóban.

A RetailSales kockaadatok másolására használt csővezeték létrehozásához kövesse az alábbi lépéseket.

1. A Szintaktikás munkaterületen válassza az Integráció **lapot**.
1. Válassza a pluszjelet (**+**), majd válassza az Importálás **a csővezeték-sablonból lehetőséget**.
1. Töltse le, majd válassza [az ExportRetailSalesCubeViews.zip fájlt](https://aka.ms/reco-alternate-dataflow-files).
1. Válassza ki az SQL adatbázishoz kapcsolt szolgáltatást.
1. Válassza ki a kapcsolt tárolási fiókot.
1. Nyissa meg az **Adatmásoló** eszközt, és módosítsa a **Mappa elérési út** tulajdonságát a következőre **\<environment_name\>: /...**.

### <a name="test-execution-of-the-pipeline"></a>A csővezeték végrehajtásának tesztelése

Javasoljuk, hogy a csővezetéket csak egyetlen nézet használatával tesztelje. A **RetailSales_RetailMediaTemplateView** nézet jól működik, mivel általában kevesebb, mint 10 sort tartalmaz.

## <a name="schedule-the-pipeline-to-run-on-a-recurring-schedule"></a>A csővezeték ütemezése ismétlődő ütemezés szerint való futásra

A csővezeték minden futtatásakor megtörténik az Azure-felhasználás. Azt ajánljuk, hogy 48 vagy hosszabb időközönként ütemezi a végrehajtásokat. A csővezeték mindig manuálisan futtatható, ha azonnal szinkronizálnia kell az adatokat. 
 
## <a name="table-list-for-synchronization-from-dynamics-365-to-data-lake-storage"></a>Táblalista a Dynamics 365-ről az adattárolóba való szinkronizáláshoz

A következő táblalista a RetailSales kockához szükséges táblák részkészlete. Az ajánlások szolgáltatás csak 15 nézetet használ a RetailSales kockában, és a szükséges táblák listája ennek megfelelően szűrve lett.

### <a name="list-of-retailsales-cube-tables"></a>A RetailSales kocka tábláinak listája

- BICalendarOffsets
- BIDateDimension
- BIDateDimensionValue
- Katalógus
- Katalógustermelés
- CatalogProductCategory
- CustInvoiceJour
- CustInvoiceTrans
- CustTable
- DataArea
- DimensionAttributeValueCombination
- DimensionAttributeValueSet
- DirPartyTable
- EcoResCategory
- EcoResCategoryHierarchy
- EcoResCategoryHierarchyRole
- EcoResColor
- EcoResConfiguration
- EcoResProduct
- EcoResProductCategory
- EcoResProductTranslation
- EcoResSize
- EcoResStyle
- HcmWorker
- InventDim
- InventDimCombination
- InventItemGroup
- InventItemGroupItem
- InventItemSetupSupplyType
- InventTable
- InventTrans
- LogisticsAddressCountryRegion
- LogisticsAddressCountryRegionTranslation
- Logisztikai hely
- LogisticsPostalAddress
- OMHIERARCHYPURPOSE
- RetailAssortmentLookup
- RetailAssortmentLookupChannelGroup
- RetailChannelProfile
- RetailChannelProfileProperty
- RetailChannelTable
- RetailChannelTableExt
- RetailConnDatabaseProfile
- RetailCustInvoiceJourTable
- RetailCustTable
- RetailMediaTemplate
- RetailOfflineProfile
- RetailPeriodicDiscount
- RetailRecoListConfigurationParameters
- RetailSalesTaxOverrideGroup
- RetailSharedParameters
- RetailSpecialCategoryMember
- RetailTenderTypeCardTable
- RetailTenderTypeTable
- RetailTerminalTable
- RetailTmpProductMedia
- RetailTransactionDiscountTrans
- RetailTransactionPaymentTrans
- RetailTransactionPaymentTransExt
- RetailTransactionSalesTrans
- RetailTransactionSalesTransExt
- RetailTransactionTable
- SalesLine
- SalesTable
- SystemParameters
- RETAILCATALOGINTERNALORG
- RETAILGROUPMEMBERLINE
- RETAILINTERNALORGANIZATION
- RETAILSPECIALCATEGORYPRODUCT
- RETAILPRODUCTCATEGORY
- ECORESCONFIGURATION
- DIMENSIONATTRIBUTE
- DIMENSIONATTRIBUTEVALUESET
- DIMENSIONHIERARCHY
- DIMENSIONHIERARCHYINTEGRATION
- DIMENSIONHIERARCHYLEVEL
- DIMENSIONPARAMETER
- OMExplodedOrganizationSecurityGraph

### <a name="view-list-for-the-parameter-to-pass-to-the-synapse-pipeline"></a>A Szintaktás folyamatnak átadva szükséges paraméter listájának megtekintése

A következő vesszővel elválasztott lista azokat a RetailSales kockanézeteket tartalmazza, amelyeken a csővezeték "select" műveletet hajt végre. Az eredményeket ezután az adattárolóba másolja.

RetailSales_RetailAssortmentRulesView,RetailSales_RetailChannelNavigationHierarchiesView,RetailSales_RetailChannelNavigationHierarchyCatalogProductsView,RetailSales_RetailChannelNavigationHierarchyCategoryNodesView,RetailSales_RetailChannelNavigationHierarchyCategoryProductsView,RetailSales_RetailMediaBaseUrlChannelView,RetailSales_RetailMediaRelativeUrlProductView,RetailSales_RetailMediaTemplateView,RetailSales_RetailOptOutCustomersView, RetailSales_RetailProductCategory,RetailSales_RetailProductTransaction,RetailSales_RetailProductVariantDimensionsView,RetailSales_RetailRecoListConfigurationParametersView,RetailSales_RetailRecoListsSharedParametersView,RetailSales_RetailEcoResProductTranslation

> [!IMPORTANT]
> A t csővezeték-paraméternek egy vesszővel elválasztott nézetnevek listájának kell lennie. Nem lehet szóköz és sorbe való beadagolás.

## <a name="environment-specific-fixes"></a>Környezetspecifikus javítások

### <a name="retailchannelview-fix"></a>RETAILCHANNELVIEW - javítás

A **RETAILCHANNELVIEW** nézet egy olyan kódolt egészszámot tartalmaz, amely a "kiskereskedelmi csatorna" típusú szervezetnek megfelelő. A típus tényleges értéke a környezetről a környezetre vagy bérlőről bérlőre változhat.

```SQL
CREATE OR ALTER   VIEW [dbo].[RETAILCHANNELVIEW]
AS
SELECT T1.RECID AS RECID1,
       T1.STOREAREA AS STOREAREA,
       T1.OMOPERATINGUNITID AS OMOPERATINGUNITID,
       T1.DEFAULTCUSTACCOUNT AS DEFAULTCUSTOMER,
       T1.RETAILCHANNELID AS RETAILCHANNELID,
       T1.CHANNELTYPE AS CHANNELTYPE,
       T1.PARTITION AS PARTITION,
       T1.RECID AS RECID,
       T2.OMOPERATINGUNITNUMBER AS OMOPERATINGUNITNUMBER,
       T3.NAME AS NAME
FROM   dbo.RETAILCHANNELTABLE AS T1 CROSS JOIN dbo.DIRPARTYTABLE AS T2 CROSS JOIN dbo.DIRPARTYTABLE AS T3
WHERE  ((((T1.OMOPERATINGUNITID = T2.RECID)
          )
         AND ((T2.RECID = T3.RECID)
              ))
        AND T2.INSTANCERELATIONTYPE IN (8363));
```

A hard-coded egész szám frissítéséhez kövesse az alábbi lépéseket.

1. A Dynamics 365-ben keresse meg **az online csatorna Csatornaazonosító** értékét.
1. A Szintaktikás adatbázishoz csatolt SQL Server Management Studio (SSMS) egyik példányán futtassa a következő lekérdezést.

    ```SQL
    select INSTANCERELATIONTYPE, NAME, NAMEALIAS, * from dbo.DIRPARTYTABLE where RECID IN (select OMOPERATINGUNITID from dbo.RETAILCHANNELTABLE where RETAILCHANNELID =     <channelID>)
    ```

1. Az érték másolása az első oszlopból (**INSTANCERELATIONTYPE**) és beillesztése a nézetdefinícióba.

## <a name="troubleshooting"></a>Hibaelhárítás

### <a name="pipeline-task-fails"></a>Értékesítési prognózis - feladat sikertelen

A CopyData feladathoz 15 csővezeték-feladat-végrehajtásnak **kell** lennie. Ha valamelyik végrehajtás sikertelen, ellenőriznie kell, hogy az összes függő SQL-objektum létezik-e, és hogy a lekérdezések lefutnak-e. Az összes függőség legegyszerűbb módja az, ha az SSMS segítségével csatlakozik az adatbázishoz. Ezután kijelölhet és visszatarthat egy nézetet (vagy a **jobb gombbal rákattinthat), és kiválaszthatja a LÉTREHOZÁS létrehozása új ablakban lehetőséget**.

A hibaüzenet a következő szöveget tartalmazhatja:

- Hiba: Hiba történt a forrás oldalán.
- Hiba történt a külső fájl kezelésekor: "Maximális hibák száma".
- /RetailSales/RetailSales_xxxxxx

#### <a name="example-scenario"></a>Példaforgatókönyv

Ebben a példában a RetailSales_RetailProductCategory **sikertelen**, és a rendszer "Maximális hibák száma" hibaüzenetet ad.

A hibakereséshez kövesse az alábbi lépéseket.

1. Nyissa meg az **EntityList.json fájlt** egy szövegszerkesztőben (például Kód Visual Studio).
1. A nézetdefiníció megkeres **RetailSales_RetailProductCategory**.

    ```SQL
    CREATE  VIEW [dbo].[RetailSales_RetailProductCategory] AS SELECT 0 AS ROW_UNIQUEKEY ,CATEGORY AS CATEGORYID ,PRODUCT AS PRODUCTID ,PRODUCTNAME ,CATEGORYNAME     ,PARENTCATEGORY AS PARENTCATEGORYID ,PARTITION ,RECID FROM RetailProductCategoryView
    ```

1. Ez a nézet csak egy másik nézettől függ: **RetailProductCategoryView** _. A _*RetailProductCategoryView**" nézetdefiníciójának megkeresve.

    ```SQL
    CREATE VIEW [DBO].[RETAILPRODUCTCATEGORYVIEW] AS SELECT T1.CATEGORY AS CATEGORY, T1.PRODUCT AS PRODUCT, T1.PARTITION AS PARTITION, T1.RECID AS RECID, T2.PRODUCTNAME AS PRODUCTNAME, T2.PARTITION AS PARTITION#2, T3.NAME AS CATEGORYNAME, T3.PARENTCATEGORY AS PARENTCATEGORY, T3.PARTITION AS PARTITION#3 FROM RETAILPRODUCTCATEGORY T1 CROSS JOIN ECORESPRODUCTTRANSLATIONS T2 CROSS JOIN RETAILCATEGORYEXPANDED T3 WHERE((( T1.PRODUCT = T2.PRODUCT) AND ( T1.PARTITION = T2.PARTITION)) AND (( T1.CATEGORY = T3.RECID) AND ( T1.PARTITION = T3.PARTITION)))
    ```

1. Ez a nézet három másik nézettől függ: RETAILPRODUCTCATEGORY **,** ECORESPRODUCTTRANSLATIONS **és** RETAILCATEGORYEXPANDED **·**. Keresse meg a nézetek definícióját, és sorolja fel függőségeit. Folytassa, amíg nem keres minden függő nézetet.

    A függőségi fa sorrendjében ez a teljes lista. A tizenharmadik nézetet ellenőrizni kell.

    - RetailSales_RetailProductCategory

        - RetailProductCategoryView

            - RETAILPRODUCTCATEGORY

                - ECORESPRODUCTCATEGORY
                - ECORESCATEGORYHIERARCHYROLE
                - RETAILSPECIALCATEGORYPRODUCT

                    - ECORESPRODUCT
                    - RETAILGROUPMEMBERLINE
                    - RETAILSPECIALCATEGORYMEMBER

            - ECORESPRODUCTTRANSLATIONS

                - ECORESPRODUCT
                - ECORESPRODUCTTRANSLATION
                - SYSTEMPARAMETERS

            - RETAILCATEGORYEXPANDED

                - ECORESCATEGORY
                - ECORESCATEGORYHIERARCHYROLE

1. Az Excel alkalmazásban hozzon létre a következő 13-as **számlálási(\*) adatokat a kimutatásokban\<view_name\>**. Futtassa ezeket az utasításokat az SSMS-ben, és küldje el az eredményeket a szövegnek. Ezután görgetve nézze meg, hogy valamelyik nézet sikertelen volt-e. A kezdeti hiba azt jelzi, hogy legalább az egyik nézet sikertelen lesz.

    ```SQL
    select count(*) from RetailProductCategoryView
    select count(*) from RETAILPRODUCTCATEGORY
    select count(*) from ECORESPRODUCTCATEGORY
    select count(*) from ECORESCATEGORYHIERARCHYROLE
    select count(*) from RETAILSPECIALCATEGORYPRODUCT
    select count(*) from ECORESPRODUCT
    select count(*) from RETAILGROUPMEMBERLINE
    select count(*) from RETAILSPECIALCATEGORYMEMBER
    select count(*) from ECORESPRODUCTTRANSLATIONS
    select count(*) from ECORESPRODUCTTRANSLATION
    select count(*) from SYSTEMPARAMETERS
    select count(*) from RETAILCATEGORYEXPANDED
    select count(*) from ECORESCATEGORY
    ```

1. A keresett adatok ellenőrzésének egyik módja a gyökérfüggő nézet létrehozása, amely létrehoz egy nézetdefiníciót az SSMS szolgáltatásban. Ezután ellenőrizze, hogy van-e R.filepath nevű Azure-adatfájl-oszlop **·**. Az oszlop jelenléte azt jelzi, hogy a vizsgált nézet adatokat olvas az Adattárolóból.

## <a name="additional-resources"></a>További erőforrások

[Termékajánlatok áttekintése](product-recommendations.md)

[Az Azure Data Lake Storage engedélyezése a Dynamics 365 Commerce környezetben](enable-adls-environment.md)

[Személyre szabott ajánlatok engedélyezése](personalized-recommendations.md)

[A hasonlóak megvásárlására vonatkozó javaslatok engedélyezése](shop-similar-looks.md)

[Személyre szabott termékajánlatok kikapcsolása](personalization-gdpr.md)

[Termékajánlások hozzáadása a pénztárnál](product.md)

[Ajánlatok hozzáadása a tranzakciós képernyőhöz](add-recommendations-control-pos-screen.md)

[AI-ML ajánlások eredményeinek helyesbítése](modify-product-recommendation-results.md)

[Válogatott ajánlások manuális létrehozása](create-editorial-recommendation-lists.md)

[Ajánlások létrehozása bemutató adatokkal](product-recommendations-demo-data.md)

[Termékajánlatok GYIK-je](faq-recommendations.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
