---
title: Egységes termékélmény
description: Ez a témakör a termékadatok integrációját ismerteti a Finance and Operations alkalmazás és a Common Data Service között.
author: t-benebo
manager: AnnBe
ms.date: 12/12/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: a52e8f65e7e2a8d90ddf5efa47c07d6995ef645d
ms.sourcegitcommit: 54baab2a04e5c534fc2d1fd67b67e23a152d4e57
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/04/2020
ms.locfileid: "3019817"
---
# <a name="unified-product-experience"></a>Egységes terméktapasztalat

[!include [banner](../../includes/banner.md)]

[!include [preview-banner](../../includes/preview-banner.md)]

Ha egy üzleti ökoszisztéma olyan Dynamics 365-alkalmazásokból áll, mint a Finance, a Supply Chain Management vagy a Sales, akkor a vállalkozások ezeket az alkalmazásokat használják a termék adatainak forrásaként. Ennek az az oka, hogy ezek az alkalmazások megbízható termék-infrastruktúrát biztosítanak, kiegészítve a kifinomult árképzési koncepciókkal és az aktuális készlet pontos adataival. Azok a vállalkozások, amelyek külső termékéletciklus-kezelő (PLM) rendszert használnak a termék adatainak lekéréséhez, a termékeket becsatornázhatják a Finance and Operations-alkalmazásokból más Dynamics 365-alkalmazásokba. Az egységes termékélmény az integrált termékadat-modellt elérhetővé teszi a Common Data Service szolgáltatásban, így az alkalmazás minden felhasználója (beleértve a Power Platform-felhasználókat is) igénybe veheti Finance and Operations-alkalmazáskból származó részletes termékadatokat.

Itt a termék adatmodellje a Sales megoldásból.

![Adatmodell CE-termékekhez](media/dual-write-product-4.jpg)

Itt a termék adatmodellje a Finance and Operations-alkalmazásokból.

![Adatmodell a Finance and Operations termékeihez](media/dual-write-products-5.jpg)

Ez a két termékadat-modell integrálva lett a Common Data Service szolgáltatásba az alábbiakban látható módon.

![Adatmodell a Dynamics 365 alkalmazások termékeihez](media/dual-write-products-6.jpg)

A termékekhez kapcsolódó kettős írású entitásleképezések csak egyirányú, csaknem valós idejű adatátvitelre vannak tervezve a Finance and Operations-alkalmazások és a Common Data Service között. A termék-infrastruktúra azonban nyitott, hogy szükség esetén kétirányú lehessen. Noha személyre szabható, ez azonban az Ön felelőssége; a Microsoft nem javasolja ezt a megközelítést.

## <a name="templates"></a>Sablonok

A termékinformációk tartalmazzák a termékhez és a termék meghatározásához kapcsolódó összes információt, például a termékdimenziókat, illetve a nyomon követési és tárolási dimenziókat. A következő táblázat bemutatja a termékek és a kapcsolódó információk szinkronizálására létrehozott entitás-leképezések gyűjteményét.

Finance and Operations | Egyéb Dynamics 365 alkalmazások | Leírás
-----------------------|--------------------------------|---
Kiadott termékek V2 | msdyn\_sharedproductdetails | A **msdyn\_sharedproductdetails** entitás tartalmazza a termék meghatározására szolgáló mezőket a Finance and Operations-megoldásokból, illetve ez tartalmazza a termék pénzügyi és vezetési információit. 
Common Data Service kiadott egyedi termékek | Termék | A **Termék** entitás a termék meghatározására szolgáló mezőket tartalmazza. Tartalmazza az egyedi termékeket (termék altípusú termékeket) és a termékváltozatokat. A következő táblázat a leképezéseket mutatja be.
Termékszám alapján azonosított vonalkód | msdyn\_productbarcodes | A termék vonalkódja a termékek egyedileg történő azonosítására szolgál.
Alapértelmezett rendelésbeállítások | msdyn\_productdefaultordersettings
Termékspecifikus alapértelmezett rendelésbeállítások | msdyn_productdefaultordersettings
Termékdimenzió-csoportok | msdyn\_productdimensiongroups | A termékdimenzió csoportja határozza meg, hogy mely cikkdimenziók határozzák meg a terméket. 
Tárolásidimenzió-csoportok | msdyn\_productstoragedimensiongroups | A termék tárolási dimenziócsoportja képviseli azt a módszert amelyet használnak a termék elhelyezésének definiálásához a raktárban.
Nyomonkövetésidimenzió-csoportok | msdyn\_producttrackingdimensiongroups | A termék nyomon követési dimenziócsoportja a termék készletben történő nyomon követésére használt módszert jelöli.
Színek | msdyn\_productcolors
Méretek | msdyn\_productsizes
Stílusok | msdyn\_productsytles
Konfigurációk | msdyn\_productconfigurations
Alaptermékszínek | msdyn_sharedproductcolors | A **Megosztott termékszín** entitás azt jelzi, hogy egy adott alapterméknek milyen színei lehetnek. Ezt a koncepciót a program a Common Data Service szolgáltatásba is áthelyezi az adatok konzisztenciájának fenntartására.
Alaptermékméretek | msdyn_sharedproductsizes | A **Megosztott termékméret** entitás azokat a méreteket jelzi, amelyekkel egy adott alaptermék rendelkezhet. Ezt a koncepciót a program a Common Data Service szolgáltatásba is áthelyezi az adatok konzisztenciájának fenntartására.
Alaptermékstílusok | msdyn_sharedproductstyles | A **Megosztott termékstílus** entitás azt jelzi, hogy egy adott alapterméknek milyen stílusai lehetnek. Ezt a koncepciót a program a Common Data Service szolgáltatásba is áthelyezi az adatok konzisztenciájának fenntartására.
Alaptermék-konfigurációk | msdyn_sharedproductconfigurations | A **Megosztott termékkonfiguráció** entitás azt jelzi, hogy egy adott alapterméknek milyen konfigurációi lehetnek. Ezt a koncepciót a program a Common Data Service szolgáltatásba is áthelyezi az adatok konzisztenciájának fenntartására.
Minden termék | msdyn_globalproducts | A minden termék entitás tartalmazza a Finance and Operations-alkalmazások összes rendelkezésre álló termékét, a kiadott termékeket és a nem kiadott termékeket is.
Egység | uoms
Egységek átváltása | msdyn_ unitofmeasureconversions
Termékspecifikus mértékegység-átváltás | msdyn_productspecificunitofmeasureconversion
Termékkategóriák | msdyn_productcategories | A termékkategóriák mindegyike, valamint a szerkezetükkel és a jellemzőikkel kapcsolatos információk a termékkategória entitásban találhatók. 
Termékkategóriák hierarchiái | msdyn_productcategoryhierarhies | A termékhierarchiákat a termékek kategorizálására vagy csoportosítására használhatja. A kategóriahierarchiák a Common Data Service szolgáltatásban, a kategóriahierarchia entitás használatával érhetők el. 
Termékkategória-hierarchiához tartozó szerepkörök | msdyn_productcategoryhierarchies | A termékhierarchiák a D365 Finance and Operations különböző szerepköreiben használhatók. Annak megadása, hogy melyik kategóriát használja az egyes szerepkörökben, amelyekben a termékkategória szerepkörentitáshoz használatos. 
Termékkategóriák hozzárendelései | msdyn_productcategoryassignments | Ha terméket szeretne hozzárendelni egy kategóriához, akkor a termékkategória hozzárendelési entitását használhatja.

## <a name="integration-of-products"></a>Termékek integrálása

Ebben a modellben a termék a következő két entitás kombinációjával van ábrázolva a Common Data Service: **Termék** és **msdyn\_sharedproductdetails** helyeken. Ahol az első egység a termék definícióját tartalmazza (a termék egyedi azonosítója, a termék neve és a leírás), a második entitás a termék szintjén tárolt mezőket tartalmazza. Ennek a két entitásnak a kombinációja a terméknek a készletezési egység (SKU) fogalma alapján történő meghatározására szolgál. Minden kiadott termék adatai megjelennek az említett entitásokban (Termék és Megosztott termék részletei). Az összes (kiadott és nem kiadott) termék nyomon követésére a **Globális termék** entitás szolgál. 

Mivel a termék SKU-ként képviselteti magát, az egyedi termékek, alaptermékek és termékváltozatok koncepciója a következő módon rögzíthető Common Data Service szolgáltatásban:

- **A termékek altípus termékkel rendelkező termékek** saját maguk által meghatározott termékek. Nem kell dimenziókat definiálni. Egy példa erre egy meghatározott könyv. Ezeknél a termékeknél egy rekord jön létre a **Termék** entitásban, és egy rekord jön létre a **msdyn\_sharedproductdetails** entitásban. Nem jön létre termékcsaládrekord.
- Az **Alaptermékek** általános termékként használatosak, amelyek meghatározzák az üzleti folyamatokban történő működéséthez kapcsolódó definíciókat és szabályokat. Ezeknek a definícióknak alapján egyedei termékeket lehet létrehozni, amelyek a termék változatát jelentik. Például a póló az alaptermék, és a szín és a méret dimenzióként is megadható. A változatok adhatók ki, amelyek ezen dimenziók különböző kombinációi, például a kis kék póló vagy egy közepes zöld póló. Az integrációban egy rekord jön létre változatonként a terméktáblában. Ez a rekord tartalmazza a változatspecifikus adatokat, például a különböző dimenziókat. A termék általános információinak tárolása a **msdyn\_sharedproductdetails** entitásban történik. (Ez az általános információ az alaptermékben található.) Ezenkívül egy termékcsalád-rekord készül alaptermékenként. Az alaptermék adatait a rendszer szinkronizálja Common Data Service szolgáltatásba a kiadott alaptermék létrehozásával (de a változatok megjelenése előtt).
- Az **Egyedi termékek** a termékek a termék összes altípusára és az összes termékváltozatra utalnak. 

![Adatmodell termékekhez](media/dual-write-product.png)

Ha a kettős írás funkció engedélyezve van, a Finance and Operations modul alkalmazásai szinkronizálva lesznek a többi Dynamics 365 alkalmazásban a **Vázlat** állapotban. Az első azonos pénznemű árlistához lesznek hozzáadva. Más szóval a Dynamics 365 alkalmazás első árlistájához lesznek hozzáadva amely megfelel annak a jogi személynek a pénznemének, ahol a termék ki van adva a Finance and Operations-alkalmazásban. 

Alapértelmezés szerint a Finance and Operations-alkalmazások termékeit szinkronizálja a rendszer a többi Dynamics 365-alkalmazással **Vázlat** állapotban. Ha azt szeretné, hogy az **Aktív** állapotú termék szinkronizálva legyen, hogy például közvetlenül tudja használni az értékesítési rendelések árajánlataiban, akkor az alábbi beállítást kell választani: a **Rendszer > Adminisztráció > Rendszeradminisztráció > Rendszerbeállítások > Sales** lapon válassza a **Termékek létrehozása az aktív állapotban = igen** értéket. 

Ügyeljen rá, hogy a termékek szinkronizálása a Finance and Operations-alkalmazásokból a Common Data Service felé történik. Ez azt jelenti, hogy a termékentitás mezőiben szereplő értékek módosíthatók a Common Data Service szolgáltatásban, de ha a szinkronizálást aktiválják (ha egy termékmező módosul a Finance and Operations-alkalmazásban), akkor ez felülírja a Common Data Service értékeit. 

[!include [symbols](../../includes/dual-write-symbols.md)]

[!include [products](includes/EcoResReleasedDistinctProductCDSEntity-products.md)]

[!include [product details](includes/EcoResReleasedProductV2-msdyn-sharedproductdetails.md)]

[!include [global products](includes/EcoResEveryProductEntity-msdyn-globalproducts.md)]

## <a name="product-dimensions"></a>Termékdimenziók 

Termékdimenziók olyan jellemzők, amelyek termékváltozat azonosítására szolgálnak. A négy termékdimenzió (szín, méret, stílus és konfiguráció) a termék változatának meghatározásához hozzá van hozzárendelve a Common Data Service szolgáltatáshoz is. A következő ábra a Szín cikkdimenzió adatmodelljét mutatja be. Ugyanez a modell a méretekre, stílusokra és a konfigurációkra is érvényes. 

![Adatmodell termékekhez](media/dual-write-product-2.PNG)

[!include [product colors](includes/EcoResProductColorEntity-msdyn-productcolor.md)]

[!include [product sizes](includes/EcoResProductSizeEntity-msdyn-productsizes.md)]

[!include [product sizes](includes/EcoResProductStyleEntity-msdyn-productstyles.md)]

[!include [product sizes](includes/EcoResProductConfigurationsEntity-msdyn-productconfigurations.md)]

Ha egy terméknek különböző a termékdimenziói vannak (például a az alaptermék mérete és szín termékdimenziók tartoznak), akkor mindegyik különböző termék (azaz a termék variánsa) ezen termékdimenziók kombinációja. A B0001 termékszámű termék például egy extra kis méretűfekete póló, és a B0002 termékszám egy kis fekete póló. Ebben az esetben a termékdimenziók meglévő kombinációinak meghatározása történik. Például az előző példából származó póló lehet extra kicsi és fekete, kicsi és fekete, közepes és fekete, illetve nagy és fekete, de nem lehet extra nagy és fekete. Más szóval az a termékdimenziók, amelyek az alaptermékhez tartozhatnak meghatározottak, és a változatokat ezen értékek alapján lehet kiadni.

Annak érdekében, hogy nyomon követhesse a termékdimenziókat, amit egy alaptermék felvehet a következő entitások jönnek létre és lesznek leképezve a Common Data Service szolgáltatásban az egyes termékdimenziókhoz. A további tudnivalókat lásd: [Termékinformációk áttekintése](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/pim/product-information).

[!include [product colors](includes/EcoResProductMasterColorEntity-msdyn-sharedproductcolors.md)]

[!include [product sizes](includes/EcoResProductMasterSize-msdyn-sharedproductsizes.md)]

[!include [product styles](includes/EcoResProductMasterStyleEntity-msdyn-sharedproductstyles.md)]

[!include [product configurations](includes/EcoResProductMasterConfigurationEntity-msdyn-sharedproductconfigurations.md)]

[!include [product bar codes](includes/EcoResProductNumberIdentifiedBarcode-msdyn-productbarcodes.md)]

## <a name="default-order-settings-and-product-specific-default-order-settings"></a>Alapértelmezett rendelési beállítások és termékspecifikus alapértelmezett rendelési beállítások

Az alapértelmezett rendelési beállítások határozzák meg azt a helyet és raktárt, ahol a cikkek beszerzése és tárolása történik, illetve azt a minimális, maximális, többszörös és szokásos mennyiséget, amely felhasználásra kerül a kereskedéshez vagy a készletgazdálkodáshoz, valamint az átfutási időket, a leállító jelzőket és a rendelési ígéret módszerét. Ezek az információk a Common Data Service rendszerben az alapértelmezett rendelési beállításokkal és a termékre vonatkozó alapértelmezett rendelésbeállítási entitással érhetők el. További információ az [Alapértelmezett rendelési beállítások cikkben](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/production-control/default-order-settings)olvasható.

[!include [product sizes](includes/InventProductDefaultOrderSettingsEntity-msdyn-productdefaultordersetting.md)]

[!include [product sizes](includes/InventProductSpecificOrderSettingsV2Entity-msdyn-productspecificdefaultordersetting.md)]

## <a name="unit-of-measure-and-unit-of-measure-conversions"></a>Mértékegység és mértékegység-átváltások

A mértékegységek és a kapcsolódó átváltások a diagramon látható adatmodellben érhetők el a Common Data Service szolgáltatásban.

![Adatmodell termékekhez](media/dual-write-product-3.PNG)

A mértékegység fogalma integrálva van a Finance and Operations-alkalmazások és más Dynamics 365 alkalmazások között. A Finance and Operations-alkalmazás minden egységosztálya esetében létrejön egy olyan egységcsoport a Dynamics 365-alkalmazásban, amely az egységosztályhoz tartozó egységeket tartalmazza. Minden egységcsoporthoz egy alapértelmezett alapegység is létrejön. 

[!include [unit of measure](includes/UnitOfMeasureEntity-uom.md)]

[!include [unit of measure conversions](includes/UnitOfMeasureConversionEntity-msdyn-unitofmeasureconversions.md)]

[!include [product specific unit of measure conversions](includes/EcoResProductSpecificUnitConversionEntity-msdyn-productspecificunitofmeasureconversions.md)]

## <a name="initial-synchronization-of-units-data-matching-between-finance-and-operations-and-common-data-service"></a>Az egységadatok egyezésének eredeti kezdeti szinkronizálása a Finance and Operations és a Common Data Service között

### <a name="initial-synchronization-of-units"></a>Egységek kezdeti szinkronizálása

Ha a kettős írás engedélyezett, a Finance and Operations rendszerből származó egységeket a rendszer szinkronizálja a többi Dynamics 365-alkalmazással. A Finance and Operations-alkalmazásokból a Common Data Service szolgáltatásban szinkronizált egységcsoportok olyan jelölővel rendelkeznek, amely mutatja, hogy „Külsőleg karbantartottak”.

### <a name="matching-units-and-unit-classesgroups-data-from-finance-and-operations-and-other-dynamics-365-apps"></a>Egyező egységek és egységosztályok/csoportok Finance and Operations- és más Dynamics 365-alkalmazásokból származó adatai

Fontos megjegyezni, hogy az egység integrációs kulcsa az msdyn_symbol. Ennek megfelelően az értéknek egyedinek kell lennie a Common Data Service- vagy más Dynamics 365-alkalmazásokban. Mivel a többi Dynamics 365-alkalmazásban az „Egységcsoport azonosítója” és a „Név” határozza meg egy egység egyediségét, különböző eseteket kell figyelembe vennie az egységadatok Finance and Operations-alkalmazások és Common Data Service közötti egyeztetése során.

A Finance and Operations-alkalmazások és más Dynamics 365-alkalmazások egyező/átfedő egységei:

+ **Az egység olyan, másik Dynamics 365-alkalmazásokban lévő egységcsoportba tartozik, amelyik megfelel a Finance and Operations-alkalmazások társított egységosztályának**. Ebben az esetben a többi Dynamics 365-alkalmazás msdyn_symbol mezőjében a Finance and Operations-alkalmazásokból származó egységszimbólumot kell megadni. Emiatt az adatok egyeztetése során az egységcsoport beállítása „Külsőleg karbantartott” lesz a többi Dynamics 365-alkalmazásban.
+ **Az egység más Dynamics 365-alkalmazások olyan egységcsoportjába tartozik, amely nem felel meg a Finance and Operations-alkalmazások társított egységosztályának (nincs egységosztály a Finance and Operations-alkalmazásokban a többi Dynamics 365-alkalmazás egységosztályához).** Ebben az esetben a msdyn_symbol mezőt véletlenszerű karakterlánccal kell kitölteni. Ügyeljen rá, hogy az értéknek egyedinek kell lennie a többi Dynamics 365-alkalmazásban.

A Finance and Operations-egységek és -egységosztályok nem léteznek más Dynamics 365-alkalmazásokban:

A kettős írás részeként a Finance and Operations-alkalmazások egységcsoportjai és a megfelelő egységek más Dynamics 365-alkalmazásokban és a Common Data Service szolgáltatásban jönnek létre és szinkronizálódnak, az egységcsoportot pedig „Külsőleg karbantartottnak” állítja be a rendszer. Nincs szükség további rendszerindításra.

Más Dynamics 365-alkalmazások egységei, amelyek nem találhatók meg Finance and Operations-alkalmazásokban:

Az msdyn_symbol mezőt minden egységnél ki kell tölteni. Az egységek bármikor létrehozhatók a megfelelő egységosztályban (ha van ilyen) lévő Finance and Operations-alkalmazásokban. Ha az egységosztály nem létezik, akkor először létre kell hozni többi Dynamics 365-alkalmazás egységcsoportjával egyező egységosztályt (ügyeljen rá, hogy a Finance and Operations szolgáltatásban nem lehet egységosztályt létrehozni, csak bővítményen keresztül, ha kibővíti a felsorolást). Ezt követően létrehozhatja az egységet. Ügyeljen rá, hogy a Finance and Operations-alkalmazások egységszimbólumának az egységhez a többi Dynamics 365-alkalmazásban korábban meghatározott msdyn_symbol szimbólumnak kell lennie.

## <a name="product-policies-dimension-tracking-and-storage-groups"></a>Termékirányelvek: dimenzió, nyomon követés és tárolás csoportjai

A termékirányelvek a termékek és a készletbeli jellemzőik meghatározására használt irányelvek halmazai. A termékdimenzió-csoport, a termékkövetési-dimenziócsoport és a tárolási dimenziócsoport a termékirányelvekként találhatók meg. 

[!include [product dimension group](includes/EcoResProductDimensionGroup-msdyn-productdimensiongroups.md)]

[!include [product tracking dimension group](includes/EcoResTrackingDimensionGroup-msdyn-producttrackingdimensiongroups.md)]

[!include [product storage dimension group](includes/EcoResStorageDimensionGroup-msdyn-productstoragedimensiongroups.md)]

## <a name="product-hierarchies"></a>Termékhierarchiák

[!include [product category hierarchy](includes/EcoResProductCategoryHierarchyEntity-msdyn-productcategoryhierarchy.md)]

[!include [product category](includes/EcoResProductCategoryEntity-msdyn-productcategory.md)]

[!include [product category assignments](includes/EcoResProductCategoryAssignmentEntity-msdyn-productcategoryassignment.md)]

[!include [product category role](includes/EcoResProductCategoryHierarchyRoleEntity-msdyn-productcategoryhierarchyrole.md)]


## <a name="integration-key-for-products"></a>Termékek integrációs kulcsa 

Ha egyedileg szeretné azonosítani a termékeket a Dynamics 365 for Finance and Operations és a Common Data Service-termékek között, akkor integrációs kulcsot kell használni. A termékek esetében a **(termékszám)** az az egyedi kulcs, amely azonosít egy terméket a Common Data Service szolgáltatásban. Ez a következők összefűzésével jön létre: **(company, msdyn_productnumber)**. A **company** jelöli a jogi személyt a Finance and Operations szolgáltatásban; a **msdyn_productnumber** jelöli az adott termék termékszámát a Finance and Operations szolgáltatásban. 

Egy másik Dynamics 365-alkalmazás felhasználója esetén a termék a felhasználói felületen lévő **msdyn_productnumber** értékkel azonosítható (a mező címkéje a **Termékszám**). A termék képernyőjén mind a vállalat, mind a msydn_productnumber látható. A (productnumber) mező, a termék egyedi kulcsa viszont nem jelenik meg. 

Ügyeljen rá, hogy ha a Common Data Service szolgáltatásra épít alkalmazást, külön ügyelnie kell arra, hogy a (productnumber), vagyis az egyedi termékazonosító legyen az integrációs kulcs, ne pedig a msdyn_productnumber, mivel az utóbbi érték nem egyedi. 

## <a name="initial-synchronization-of-products-and-migration-of-data-from-common-data-service-to-finance-and-operations"></a>A termékek kezdeti szinkronizálása, és az adatok áttelepítése a Common Data Service szolgáltatásból a Finance and Operations szolgáltatásba

### <a name="initial-synchronization-of-products"></a>Termékek kezdeti szinkronizálása 

Ha a kettős írás engedélyezett, a Dynamics 365 Finance and Operations rendszerből származó termékeket a rendszer szinkronizálja a Common Data Service szolgáltatással és a többi Dynamics 365-alkalmazással. Ügyeljen rá, hogy a Common Data Service szolgáltatásban és a többi Dynamics 365-alkalmazásban a kettős írás előtt létrehozott termékek nem frissülnek, és a rendszer nem egyezteti őket a Finance and Operations termékadataival.

### <a name="matching-product-data-from-finance-and-operations-and-other-dynamics-365-apps"></a>A Finance and Operations és más Dynamics 365-alkalmazások termékadatainak egyeztetése

Ha ugyanaz a termék szerepel (átfedő/egyező) a Finance and Operations és a Common Data Service szolgáltatásban és más Dynamics 365-alkalmazásokban, akkor a kettős írás engedélyezésekor sor kerül a Finance and Operations szolgáltatásból származó termékek szinkronizálására, és az egyes termékekhez ismétlődő rekordok jelennek meg a Common Data Service szolgáltatásban.
Az előző helyzet elkerülése érdekében, ha más Dynamics 365-alkalmazásokban a Finance and Operations szolgáltatásban lévőkkel átfedő vagy egyező termékek vannak, akkor a kettős írást engedélyező rendszergazdának rendszerindítást kell végeznie a **Vállalat** (pl. „USMF”) és az **msdyn_productnumber** mezőn (például: „1234:Black:S”), mielőtt megtörténik a termékek szinkronizálása. Más szóval, a Common Data Service szolgáltatásban lévő termékben található két mezőben meg kell adni a termékszámot, valamint a Finance and Operations szolgáltatásban lévő azon megfelelő vállalatot, amelyhez egyeztetni kell a terméket. 

Amikor ezután megkezdődik a szinkronizálás, a Finance and Operations szolgáltatásból származó termékeket a rendszer szinkronizálja a Common Data Service szolgáltatásban és a többi Dynamics 365-alkalmazásban lévő egyeztetett termékekkel. Ez egyedi termékekre és termékváltozatokra is vonatkozik. 


### <a name="migration-of-product-data-from-other-dynamics-365-apps-to-finance-and-operations"></a>A termékadatok áttelepítése más Dynamics 365-alkalmazásokból a Finance and Operations szolgáltatásba

Ha más Dynamics 365-alkalmazások olyan termékekkel rendelkeznek, amelyek nem szerepelnek a Finance and Operations modulban, akkor a rendszergazda először használhatja az **EcoResReleasedProductCreationV2Entity** entitást az ilyen termékek Finance and Operations modulba történő importálásához. Ezután a fent ismertetett módon egyeztetheti a Finance and Operations modulból és a többi Dynamics 365-alkalmazásból származó termékadatokat. 
