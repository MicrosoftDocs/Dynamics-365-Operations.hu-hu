---
title: Termékek adatainak áttekintése
description: Ez a témakör a termékinformációk kezelésével kapcsolatban tartalmaz tájékoztatást. A termékinformációk kezelése megosztott termékmeghatározás, kategorizálás és azonosítók révén működik a jogi személyeken belül, valamint egy termék egyes konfigurációi révén is, hogy beférjen a üzleti folyamatokba.
author: t-benebo
ms.date: 06/01/2017
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResProductMaintainWorkspace, EcoResProductListPage, EcoResProductVariantMaintainWorkspace, EcoResProductVariantPerCompanyImagePart, EcoResProductRelationType,EcoResProductAvailabilityPart,  EcoResProductReleasedSelect, EcoResProductLookup, EcoResProductVariantsPendingReleaseFormPart, EcoResProductSearchLookup, EcoResProductNumberRename, EcoResDimensionBasedConfigWorkspace, EcoResProductVariantImagePart, EcoResProductImagePart, EcoResProductVariantsPerCompanyPart, InventItemIdLookupByDefaultOrderSetting, EcoResProductReleaseSessions, EcoResProductVariantMaintainWorkspaceConfiguration, EcoResProductProcessManufacturingWorkspaceConfiguration, EcoResProductMasterVariantsPart, EcoResProductDiscreteManufacturingWorkspaceConfiguration, EcoResProductVariantAvailabilityPart, EcoResProductInformationFactBox, EcoResProductLookupTest, EcoResProductImageTest, EcoResProductReleasedRecentlyCreatedFormPart, EcoResPhysicalProductDimensions, PdsMRCRegulatedListItem, EcoResProductAvailabilityPart, PdsMRCRestrictionList, InventItemIdLookupAllocationId, EcoResProductAvailability, EcoResProductEntityAttributeTableFieldAssociation, EcoResProductImagePart, EcoResProductRelation, EcoResProductReleaseAddProduct, EcoResProductPerCompanyListPage, EcoResProductParameters, PdsMRCRestrictedItemByCountryState, EngChgCasePreview, InventTablePreview, PdsMRCItemDetails, EngChgCaseAssociate, PdsMRCCustomerHistory, PdsMRCVendorHistory, PdsMRCRestrictedCountryStateByItem, InventItemIdGroupLookup, InventLocationLookup, PdsMRCValidityIntervalbyCountry, PdsMRCValidityIntervalbyCountry, PdsMRCEventTracker, PdsMRCReportingCountry, PdsMRCDocument, PdsMRCReportingList, PdsMRCItemCAS, GraphicsTestForm, EngChgPicklist
audience: Application User
ms.reviewer: kamaybac
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: benebotg
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2c8aabeed66f864d1d1060a6452a3b554611c295
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/31/2022
ms.locfileid: "8063316"
---
# <a name="product-information-overview"></a>Termékek adatainak áttekintése

[!include [banner](../includes/banner.md)]



Ez a témakör a termékinformációk kezelésével kapcsolatban tartalmaz tájékoztatást. A termékinformációk kezelése megosztott termékmeghatározás, kategorizálás és azonosítók révén működik a jogi személyeken belül, valamint egy termék egyes konfigurációi révén is, hogy beférjen a üzleti folyamatokba. 

A termékinformáció az ellátási lánc és a kereskedelmi alkalmazások gerince minden ágazatban. Olyan folyamatokra és technológiákra utal, amelyek középpontjában a termékekkel kapcsolatos információk központi kezelése áll (például az ellátási láncok között). Nagyon fontos, megosztott termékdefiníciókat, dokumentációkat, attribútumokat és azonosítókat használjanak. Az üzleti megoldások különböző moduljaiban termékkel kapcsolatos információkra és a konfigurálásra van szükség az egyes termékekhez, termékcsaládokhoz vagy termékkategóriákhoz kapcsolódó üzleti folyamatok kezeléséhez.

## <a name="product-definition"></a>Termékdefiníció

A terméket elsősorban a termékszáma, a neve és a leírása határozza meg. Azonban más adatokra is szükség van egy termék vagy egy szolgáltatás leírásához:

- Termék típusa: cikk vagy szolgáltatás
- Termék altípusa: egyedi termékek vagy alaptermékek
- Termékváltozat-modell definíciója:

     - Termékdimenziók és dimenziócsoportok
     - Termékek elnevezési rendszere
     - Termékkonfigurációs modellek

- A termék társítása egy vagy több kategóriához
- A termék és a kategória-attribútumok meghatározása
- Termékképek
- Mellékletek
- Mértékegységek és kapcsolódó átalakítások
- A nevek és leírások fordításai

## <a name="distribution-export-and-import-of-product-data"></a>Termékadatok elosztása, exportálása és importálása

A termékdefiníció a Supply Chain Management rendszerben hozható létre. Importálható a termék életciklus-kezelési (PLM), a termékadatok kezelési (PDM) vagy a termékinformációk kezelési (PIM) rendszereiből. Ha a Supply Chain Management több példánya fut párhuzamosan, általában egy példány szolgál a többi példány termékadatainak alapjául. Ezt a megközelítést támogatja nagy számú adatkészlet, amely lehetővé teszi a termékdefiníciós adatok exportálását és importálását egyik példányból a másikba.

A termékadatok sok példányban történő elosztásának támogatásához a Supply Chain Management rendszer lehetővé teszi a Microsoft Dataverse használatát. A termékdefiníciók exportálhatók a Supply Chain Management egy példányából a Microsoft Dataverse szolgáltatásba. A termékdefiníciók felhasználhatók más üzleti alkalmazások, például a Dynamics 365 Sales termékadatokkal történő ellátására.

Vegye figyelembe, hogy a dinamikus és aktív szervezeteknél a termékinformációs adatok naponta változnak. Ezért a pontos és aktuális termékadatok karbantartása önmagában kritikus üzleti folyamat.

## <a name="product-masters-and-product-variants"></a>Alaptermékek és termékváltozatok

Egy olyan mozgékony világban, amelyben a termékeket gyorsan hozzá kell igazítani az ügyfelek igényeihez, a termékmeghatározások termékkészletre vonatkoznak az egyedi termékek helyett. A Supply Chain Management rendszerben ezeket az általános termékeket *alaptermékeknek* nevezik. Az alaptermékek tárolják azokat a meghatározásat és szabályokat, amelyek meghatározzák az egyedi termékek leírását és az üzleti folyamatokban történő viselkedésüket. E meghatározások alapján egyedi termékek hozhatók létre. Ezen egyedi termékek a *Termékváltozatok*.

Az alaptermék egy termékdimenzió-csoporthoz és egy konfigurációs technológiához van társítva az üzleti szabályok meghatározása érdekében. A termékdimenziók (szín, méret, stílus és konfiguráció) olyan meghatározott attribútumkészletet jelentenek, amelyek az alkalmazás egészében használhatók a kapcsolódó termékek konkrét viselkedésének meghatározására és nyomon követésére. Ezek a dimenziók segítik a felhasználókat a termékek keresésében és azonosításában is.

## <a name="configuration-technologies"></a>Konfigurációs technológiák

Három konfigurációs technológia közül választhat:

- Az előre definiált változatokat előre meghatározott cikkdimenziók határozzák meg. A termékváltozat definíciója tartalmazza a dimenziók egy konkrét érvényes kombinációjának meghatározását, például a színt, a stílust és a méretet. Minden egyes kombináció egyedi termékváltozatot eredményez.
- A dimenzión alapuló konfigurációt általában a gyártási forgatókönyvek használják, és lehetővé teszi a Konfiguráció dimenzió használatát az anyagjegyzékek (AJ) meghatározásában. Egy adott konfigurációt kiválasztása után a rendszer azokaz az anyagjegyzéksorokat használja, amelyek az adott tervezési és termelési konfigurációra érvényesek. Ezt nevezik *Globális anyagjegyzéknek*, mert egy közös anyagjegyzéket használ egy termék minden konfigurációjához.
- A megszorításon alapuló konfiguráció egy termékkonfigurációs modellt használ annak érdekében, hogy leírja az összes lehetséges attribútumot és azokat az összetevőket, amelyek egy adott modell minden lehetséges változatának leírásához szükségesek. Az attribútumok kombinációinak korlátozásai szabályos kifejezésekkel vagy táblázatos alapú korlátozásokkal írhatók le. A termékkonfigurációs modellek és a konfigurátorok egyre fontosabbá válnak a termékinformációk kezelésében, és minden iparágban használatosak.

Ha a Supply Chain Management rendszer végrehajtását tervezi, rendkívül fontos a megfelelő konfigurációs technológia kiválasztása az üzleti folyamat számára. Egy termék nem konvertálható egyik modellből a másikba a végrehajtást követően.

## <a name="product-variant-model-definition-workspace"></a>Termékváltozat modelldefiníciója munkaterület

A **Termékváltozat modelldefiníciója** munkaterület áttekintést ad az alaptermékekről. Megjeleníti az alaptermékek és a kapcsolódó termékváltozatok kiadási állapotát is az egyes jogi személyekhez kapcsolódóan.

## <a name="released-products"></a>Kiadott termékek

A meghatározott jogi személyhez kiadott termékeket *Kiadott termékeknek* nevezik. A termékek egyszerre egy jogi személynek ömlesztve vagy több jogi személynek is kiadhatók. Mivel megtörténhet, hogy a termékek különféle tulajdonságait és attribútumait jogi személyenként kell hozzáadni, a **Kiadott termék karbantartása** munkaterület segítségével figyelemmel kísérheti és végrehajhatja az egyes jogi személyek, illetve a jogi személy a alszervezeteiben nemrégiben kiadott termékeket.

### <a name="released-product-maintenance-workspace"></a>Kiadott termék karbantartása

A **Kiadott termék karbantartása** munkaterületet a **Munkaterület konfigurálása** menüpontban konfigurálhatja. Válasszon ki egy kategóriahierarchiát, és a munkaterület szűréséhez szükséges kategóriát. A munkaterület releváns termékadatainak módosításához napi időkorlátokat is meghatározhat a **Nemrégiben kiadott termékek** és a **Leállított kiadott termékek** esetében.

A munkaterület összegző lapokból és két listából áll. A **Nyitott esetek** listája olyan termékmódosítási eseteket tartalmaz, amelyekben a kiválasztott termékkategória-hierarchiában levő termékek befejezetlenek vagy lezáratlanok. A **Nemrégiben kiadott** lista olyan termékeket jeleníti meg, amelyeket a munkaterület-konfigurációban beállított időkorláton belül adtak ki. A listában szereplő minden egyes cikk esetében a rendszer futtat egy ellenőrzést, és megjelenik az ellenőrzési állapot. Ez az állapot azt jelezheti, hogy a jogi személyhez szükséges konfigurációk még nem fejeződtek be. A listából közvetlenül hozzáférhet a **Kiadott termék részletei**, a **Termékattribútum karbantartása**, a **Termékkategóriák karbantartása**, az **Alapértelmezett rendelésbeállítások** és a **Szöveg fordításai** lapokhoz a termék szükséges konfigurációjának elvégzéséhez.

### <a name="manually-creating-a-new-released-product"></a>Újonnan kiadott termék manuális létrehozása

Manuálisan hozhat létre egy kiadott terméket egyetlen futtatásban a szervezet üzleti folyamataitól attól függően, valamint attól függően, hogy milyen szabályokat alkalmaz a funkció használatával kapcsolatban. Ez a funkció létrehoz egy új terméket, és automatikusan kiadja azt az aktuális jogi személynek. Új termék létrehozásához kattintson a **Kiadott termékek** lehetőségre a **Kiadott termék karbantartása** munkaterületen vagy a **Kiadott termék** listaoldalon.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]