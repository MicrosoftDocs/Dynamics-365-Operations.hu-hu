---
title: Kettős írás – áttekintés
description: Ez a témakör áttekintést nyújt a kettős írásról, amely közel valós idejű interakciót biztosít az ügyfél-elköteleződési alkalmazások és a Finance and Operations alkalmazások között.
author: RamaKrishnamoorthy
ms.date: 02/06/2020
ms.topic: overview
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: f39322a0c2ef50ef2bbeb256c80096e0687c4642
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/31/2022
ms.locfileid: "8061334"
---
# <a name="dual-write-overview"></a>Kettős írás – áttekintés

[!include [banner](../../includes/banner.md)]





## <a name="what-is-dual-write"></a>Mi az a kettős írás?

A Dual-write egy beépített infrastruktúra, amely közel valós idejű interakciót biztosít az ügyfél-elköteleződési alkalmazások és a Finance and Operations alkalmazások között. Amikor a vevőkkel, termékekkel, személyekkel és műveletekkel kapcsolatos adatok az alkalmazás határain túl is eljutnak, az a szervezet minden részlegét felbátorítja.

A kettős írás szorosan összekapcsolt, kétirányú integrációt biztosít a Finance and Operations alkalmazások és a Dataverse. Bármilyen adatváltozás a Finance and Operations alkalmazásokban, a következőre írásokat okoz Dataverse, és az esetleges adatváltozások Dataverse okoz írásokat a Finance and Operations alkalmazásokba. Ez az automatizált adatáramlás integrált felhasználói élményt nyújt az alkalmazások között.

![Adatkapcsolat az alkalmazások között.](media/dual-write-overview.jpg)

A kettős írásnak két aspektusa van: egy *infrastruktúra* szempont és egy *alkalmazási* szempont.

### <a name="infrastructure"></a>Infrastruktúra

A kettős írás infrastruktúrája bővíthető és megbízható, és a következő kulcsfontosságú funkciókat tartalmazza:

+ Az alkalmazások közötti szinkron és kétirányú adatáramlás
+ Szinkronizálás, lejátszási, szüneteltetési és felzárkóztatás módokkal együtt a rendszer támogatása érdekében az online és offline/aszinkron mód esetében.
+ A kezdeti adatok szinkronizálásának lehetősége az alkalmazások között
+ A tevékenység és a hibanaplók kombinált nézete adatrendszergazdák számára
+ Egyéni figyelmeztetések és küszöbértékek konfigurálásának és értesítésekre való feliratkozás képessége
+ Intuitív felhasználói felület (UI) szűréshez és átalakításokhoz
+ Táblafüggőségek és kapcsolatok beállításának lehetősége
+ Bővíthetőség a szabványos és egyéni táblák és leképezések esetében
+ Megbízható alkalmazáséletciklus-kezelés
+ Beépített beállítási élmény új ügyfelek számára

### <a name="application"></a>Pályázat

A kettős írás leképezést hoz létre a Finance and Operations alkalmazásokban és az ügyfelek bevonásával kapcsolatos alkalmazásokban található fogalmak között. Ez az integráció a következő eseteket támogatja:

+ Integrált vevői alapadat
+ A vevői hűségkártyákhoz és jutalompontokhoz való hozzáférés
+ Egységes alaptermékkel kapcsolatos élmény
+ Szervezeti hierarchiák ismertsége
+ Integrált szállítói alapadat
+ A pénzügyi és adóügyi hivatkozási adatokhoz való hozzáférés
+ Igény szerinti árképzési motorral kapcsolatos élmény
+ Integrált Potenciális vevők készpénzre váltása élmény
+ Képesség a házon belüli eszközök és a vevői eszközök felhasználhatóságára helyszíni ügyfelek által
+ Integrált beszerzésirányítási élmény
+ Integrált tevékenységek és megjegyzések a vevői adatokhoz és dokumentumokhoz
+ Lehetőség a tényleges készlet elérhetőségének és részleteinek keresésére
+ Projekt készpénzre váltási élménye
+ Több cím és szerepkör kezelésének képessége a fél koncepción keresztül


## <a name="top-reasons-to-use-dual-write"></a>A kettős írás használatának legfőbb okai

A kettős írás adatintegrációt tesz lehetővé az egész Microsoft Dynamics 365 alkalmazásban. Ez a robosztus keretrendszer összeköti a környezeteket és lehetővé teszi az üzleti alkalmazások együttműködését. Íme a legfontosabb okok a kettős írás használatára:

+ A kettős írás szorosan összekapcsolt, szinte valós idejű, kétirányú integrációt tesz lehetővé a Finance and Operations alkalmazások és az ügyfélkapcsolati alkalmazások között. Az integrációnak köszönhetően a Microsoft Dynamics 365 egyben nyújt szolgáltatást az összes üzleti megoldáshoz. A Dynamics 365 Finance és Dynamics 365 Supply Chain Management szolgáltatásokat használó ügyfelek, akik nem Microsoftos megoldásokat használnak ügyfélkapcsolat-kezeléshez (CRM) a kettős írás támogatása miatt áttérnek a Dynamics 365 szolgáltatásra.
+ Az ügyfelekről, termékekről, műveletektől, projektektől és az eszközök internetes hálózatától (IoT) származó adatok automatikusan átáramlanak a Dataverse szolgáltatásba a kettős íráson keresztül. Ez a kapcsolat nagyon hasznos a Power Platform bővítésben érdekelt vállalatok számára.
+ A kettős írás infrastruktúrája a nincs kódolás/kevés kódolás elvet követi. Minimális mérnöki erőfeszítést kell tenni a szabványos táblák közti leképezések kiterjesztéséhez, és az egyéni leképezések szerepeltetéséhez.
+ A kettős írás online és offline módot is támogat. A Microsoft az egyetlen olyan vállalat, amely online és offline mód támogatását is kínálja.

## <a name="what-does-dual-write-mean-for-developers-and-architects-of-customer-engagement-apps"></a><a id="developer-architect"></a>Mit jelent a kettős írás az ügyfélkapcsolati alkalmazások fejlesztői és tervezői számára?

A kettős írás automatizálja az adatáramlást a Finance and Operations és az ügyfélelköteleződési alkalmazások között. A kettős írás két olyan AppSource-megoldást tartalmaz, amelyek telepítve van Dataverse-szolgáltatásban. A megoldások bővítik a tábla sémáját, beépülő moduljait és munkafolyamatait a Dataverse-ben, hogy ERP méretűre skálázhatók legyenek. A sikeres megvalósítás érdekében az ügyfél-elköteleződési alkalmazások fejlesztőinek és tervezőinek meg kell érteniük ezeket a változásokat, és együtt kell működniük partnereikkel a Finance and Operations alkalmazásokban.

A Finance and Operations alkalmazásokkal való paritás megteremtése érdekében a kettős írás alapvető változtatásokat hajt végre a Dataverse séma. Ha megérti a konstrukciót, akkor a későbbiekben elkerülhetők lesznek a tervezéssel és fejlesztéssel kapcsolatos javítások.

+ Ha a kettős írású AppSource-csomagot telepítik, a Dataverse új fogalmakat kap, például a vállalatot és a felet. Ezek a koncepciók segítik a ráépülő alkalmazásokat Dataverse, beleértve a Dynamics 365 Sales, a Dynamics 365 Marketing, a Dynamics 365 Customer Service és a Dynamics 365 Field Service, hogy zökkenőmentesen kommunikáljon a Finance and Operations alkalmazásokkal.

+ A tevékenységek és megjegyzések egyesülnek, és bővítésükkel támogatják a C1 (a rendszer felhasználóit) és a C2 (a rendszer ügyfeleit).

+ Az adatvesztés elkerülése érdekében a Finance and Operations alkalmazások és a pénznemek közötti átvitel során Dataverse, akkor bővítheti a tizedesjegyek számát az ügyfelek elköteleződését szolgáló alkalmazások pénznemadat-típusában. A funkció a meglévő sorokat a metaadat-réteg új kiterjesztett állapotára fordítja le. A folyamat során a program a pénzadatok helyett decimális adatokra fordítja le a pénznemet, és a pénznem értéke 10 tizedesjegyet támogat. Ez a funkció választható, és a szervezetek, amelyeknél nem szükséges a több, mint 4 tizedesjegy pontosság nem kell, hogy elfogadják. A további tudnivalókat lásd: [Pénznem-adattípus áttelepítése a kettős íráshoz](currrency-decimal-places.md).

+ [Dátum hatályossága](../../dev-tools/date-effectivity.md) hozzá lesz adva a Dataverse-hez. A múltbéli, jelenlegi és jövőbeli dátumokat is támogatni fogja ugyanazon táblában.

+ A termékek, árajánlatok, rendelések és számlák esetében támogatott a termék [egységének átváltása](../../../../supply-chain/pim/tasks/manage-unit-measure.md).

További tájékoztatás a közelgő módosításokról: [Újdonságok és módosítások a kettős írásban](whats-new-dual-write.md).



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
