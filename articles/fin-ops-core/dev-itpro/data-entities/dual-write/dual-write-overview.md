---
title: Kettős írás – áttekintés
description: Ez a témakör áttekintést nyújt a kettős írásról, amely szinte valós idejű kommunikációt biztosít az ügyfél-kapcsolati alkalmazások, illetve a Pénzügy és Az Üzemeltetés alkalmazások között.
author: RamaKrishnamoorthy
ms.date: 02/06/2020
ms.topic: overview
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: e71d1496da24b21949259e8f43a32cd4ff60249c
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2022
ms.locfileid: "7984141"
---
# <a name="dual-write-overview"></a>Kettős írás – áttekintés

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]



## <a name="what-is-dual-write"></a>Mi az a kettős írás?

A kettős írás egy olyan kiváló infrastruktúra, amely szinte valós idejű kommunikációt biztosít az ügyfél-kapcsolati alkalmazások, illetve a Pénzügy és a Műveletek alkalmazások között. Amikor a vevőkkel, termékekkel, személyekkel és műveletekkel kapcsolatos adatok az alkalmazás határain túl is eljutnak, az a szervezet minden részlegét felbátorítja.

A kettős írással szorosan és kétirányúan működik együtt a Pénzügy és a Műveletek alkalmazások és a Dataverse. A Pénzügy és a Művelet alkalmazások bármely adatváltozása írást, a pénzműveleti alkalmazásokba írást és bármilyen Dataverse Dataverse adatváltozást okoz. Ez az automatizált adatáramlás integrált felhasználói élményt nyújt az alkalmazások között.

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

A kettős írás a Pénzügy és művelet alkalmazásokban használt fogalmak és az ügyfél-megállapodási alkalmazások koncepciói közötti megfeleltetést hozza létre. Ez az integráció a következő eseteket támogatja:

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

A kettős írás automatizálja a Pénzügy és a Műveletek alkalmazások, valamint az ügyfél-megállapodási alkalmazások közötti adatáramlást. A kettős írás két olyan AppSource-megoldást tartalmaz, amelyek telepítve van Dataverse-szolgáltatásban. A megoldások bővítik a tábla sémáját, beépülő moduljait és munkafolyamatait a Dataverse-ben, hogy ERP méretűre skálázhatók legyenek. A sikeres implementációhoz az ügyfél-programfejlesztőknek és -fejlesztőknek meg kell érteniük ezeket a módosításokat, és együtt kell működniük a Pénzügyi és üzemeltetési alkalmazásokkal.

Ha paritást hoz létre a Pénzügy és Művelet alkalmazásokkal, akkor a kettős írás alapvető változásokat hoz létre a Dataverse sémában. Ha megérti a konstrukciót, akkor a későbbiekben elkerülhetők lesznek a tervezéssel és fejlesztéssel kapcsolatos javítások.

+ Ha a kettős írású AppSource-csomagot telepítik, a Dataverse új fogalmakat kap, például a vállalatot és a felet. Ezek az alapfogalmak segítik a Dataverse dynamics 365 értékesítésre, a Dynamics 365 marketingre, a Dynamics 365 ügyfélszolgálatra és a Pénzügy és műveletek alkalmazásokkal való problémamentes együttműködésre használt Dynamics 365 Field Service alkalmazásokat.

+ A tevékenységek és megjegyzések egyesülnek, és bővítésükkel támogatják a C1 (a rendszer felhasználóit) és a C2 (a rendszer ügyfeleit).

+ Ha meg szeretné akadályozni, hogy a pénzügyi és a műveletalkalmazások és az alkalmazások közötti pénznemátadás során adatvesztés jelennek meg, a vevői kapcsolati alkalmazások pénznem adattípusában meg lehet hosszabbíthatja Dataverse a tizedesjegyek számát. A funkció a meglévő sorokat a metaadat-réteg új kiterjesztett állapotára fordítja le. A folyamat során a program a pénzadatok helyett decimális adatokra fordítja le a pénznemet, és a pénznem értéke 10 tizedesjegyet támogat. Ez a funkció választható, és a szervezetek, amelyeknél nem szükséges a több, mint 4 tizedesjegy pontosság nem kell, hogy elfogadják. A további tudnivalókat lásd: [Pénznem-adattípus áttelepítése a kettős íráshoz](currrency-decimal-places.md).

+ [Dátum hatályossága](../../dev-tools/date-effectivity.md) hozzá lesz adva a Dataverse-hez. A múltbéli, jelenlegi és jövőbeli dátumokat is támogatni fogja ugyanazon táblában.

+ A termékek, árajánlatok, rendelések és számlák esetében támogatott a termék [egységének átváltása](../../../../supply-chain/pim/tasks/manage-unit-measure.md).

További tájékoztatás a közelgő módosításokról: [Újdonságok és módosítások a kettős írásban](whats-new-dual-write.md).



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
