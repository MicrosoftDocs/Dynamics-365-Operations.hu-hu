---
title: Kettős írás – áttekintés
description: Ez a témakör áttekintést nyújt a két írásról, amely szinte valós idejű kommunikációt biztosít az ügyfél-szerződés szerződésekkel kapcsolatos alkalmazások, illetve a pénzügyi és az üzemeltetési alkalmazások között.
author: RamaKrishnamoorthy
ms.date: 02/06/2020
ms.topic: overview
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: 943607a3ef28db11b7bc7805257914117e6ae38c
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9289638"
---
# <a name="dual-write-overview"></a>Kettős írás – áttekintés

[!include [banner](../../includes/banner.md)]





## <a name="what-is-dual-write"></a>Mi az a kettős írás?

A kettős írás egy olyan kiváló infrastruktúra, amely szinte valós idejű kommunikációt biztosít az ügyfél-kapcsolati alkalmazások, illetve a pénzügy és a műveleti alkalmazások között. Amikor a vevőkkel, termékekkel, személyekkel és műveletekkel kapcsolatos adatok az alkalmazás határain túl is eljutnak, az a szervezet minden részlegét felbátorítja.

A kettős írással szorosan és kétirányúan működik együtt a pénzügyi és a műveleti alkalmazások és a Dataverse. A pénzügy- és műveletalkalmazások bármely Dataverse Dataverse adatváltozása írást, a pénz- és műveletalkalmazások írását okozza. Ez az automatizált adatáramlás integrált felhasználói élményt nyújt az alkalmazások között.

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

### <a name="application"></a>Alkalmazás

A kettős írás segítségével megfeleltetést lehet létrehozni a pénzügyekkel és az üzemeltetéssel kapcsolatos alkalmazások koncepciói és az ügyfél-megállapodási alkalmazásokban használt fogalmak között. Ez az integráció a következő eseteket támogatja:

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

+ A kettős írás szorosan összekapcsolt, szinte valós idejű, kétirányú integrációt tesz lehetővé a Finance and Operations alkalmazások és az ügyfélkapcsolati alkalmazások között. Az integrációnak köszönhetően a Microsoft Dynamics 365 egyben nyújt szolgáltatást az összes üzleti megoldáshoz. Azok a vevők, akik a Dynamics 365 Pénzügyet Dynamics 365 Supply Chain Management és más nem Microsoft-megoldásokat használják az ügyfélkapcsolat-kezeléshez, a Dynamics 365 felé haladnak, és kettős írási támogatást nyújtanak.
+ Az ügyfelekről, termékekről, műveletektől, projektektől és az eszközök internetes hálózatától (IoT) származó adatok automatikusan átáramlanak a Dataverse szolgáltatásba a kettős íráson keresztül. Ez a kapcsolat nagyon hasznos a Power Platform bővítésben érdekelt vállalatok számára.
+ A kettős írás infrastruktúrája a nincs kódolás/kevés kódolás elvet követi. Minimális mérnöki erőfeszítést kell tenni a szabványos táblák közti leképezések kiterjesztéséhez, és az egyéni leképezések szerepeltetéséhez.
+ A kettős írás online és offline módot is támogat. A Microsoft az egyetlen olyan vállalat, amely online és offline mód támogatását is kínálja.

## <a name="what-does-dual-write-mean-for-developers-and-architects-of-customer-engagement-apps"></a><a id="developer-architect"></a>Mit jelent a kettős írás az ügyfélkapcsolati alkalmazások fejlesztői és tervezői számára?

A kettős írás automatizálja a pénzügyek és műveleti alkalmazások, valamint az ügyfél-megállapodási alkalmazások közötti adatáramlást. A kettős írás két olyan AppSource-megoldást tartalmaz, amelyek telepítve van Dataverse-szolgáltatásban. A megoldások bővítik a tábla sémáját, beépülő moduljait és munkafolyamatait a Dataverse-ben, hogy ERP méretűre skálázhatók legyenek. A sikeres megvalósítás érdekében az ügyfél-programfejlesztőknek és -mérnököknek meg kell érteniük ezeket a módosításokat, és együtt kell működniük a pénzügyi és műveleti alkalmazásokkal kapcsolatos megfelelőikkel.

Ha paritást hoz létre a pénzügyi és műveleti alkalmazásokkal, akkor a kettős írás alapvető változásokat hoz létre a sémában Dataverse. Ha megérti a konstrukciót, akkor a későbbiekben elkerülhetők lesznek a tervezéssel és fejlesztéssel kapcsolatos javítások.

+ Ha a kettős írású AppSource-csomagot telepítik, a Dataverse új fogalmakat kap, például a vállalatot és a felet. Dataverse Ezek az alapfogalmak segítenek az alkalmazásokban, például a Dynamics 365 Értékesítés, a Dynamics 365 Marketing, a Dynamics 365 Ügyfélszolgálat Dynamics 365 Field Service és a pénzügyi és üzemeltetési alkalmazásokkal való problémamentes kommunikációban.

+ A tevékenységek és megjegyzések egyesülnek, és bővítésükkel támogatják a C1 (a rendszer felhasználóit) és a C2 (a rendszer ügyfeleit).

+ Ha meg szeretné Dataverse akadályozni, hogy a pénzügyi és műveleti alkalmazások és az alkalmazások közötti pénznemátadás során adatvesztés jelennek meg, a vevői kapcsolati alkalmazások pénznem adattípusában meg lehet hosszabbíthatja a tizedesjegyek számát. A funkció a meglévő sorokat a metaadat-réteg új kiterjesztett állapotára fordítja le. A folyamat során a program a pénzadatok helyett decimális adatokra fordítja le a pénznemet, és a pénznem értéke 10 tizedesjegyet támogat. Ez a funkció választható, és a szervezetek, amelyeknél nem szükséges a több, mint 4 tizedesjegy pontosság nem kell, hogy elfogadják. A további tudnivalókat lásd: [Pénznem-adattípus áttelepítése a kettős íráshoz](currrency-decimal-places.md).

+ [Dátum hatályossága](../../dev-tools/date-effectivity.md) hozzá lesz adva a Dataverse-hez. A múltbéli, jelenlegi és jövőbeli dátumokat is támogatni fogja ugyanazon táblában.

+ A termékek, árajánlatok, rendelések és számlák esetében támogatott a termék [egységének átváltása](../../../../supply-chain/pim/tasks/manage-unit-measure.md).

További tájékoztatás a közelgő módosításokról: [Újdonságok és módosítások a kettős írásban](whats-new-dual-write.md).



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]

