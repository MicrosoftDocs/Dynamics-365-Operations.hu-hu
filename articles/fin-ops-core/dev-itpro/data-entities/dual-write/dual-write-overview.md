---
title: Kettős írás – áttekintés
description: Ez a témakör a kettős írás áttekintését nyújtja, amely közel valós idejű interakciót tesz lehetővé az ügyfélkapcsolati alkalmazások és a Finance and Operations alkalmazások között.
author: RamaKrishnamoorthy
ms.date: 02/06/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: 76c2f07ac5c25eea576cbb69256e76fbef4d86ca
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5754112"
---
# <a name="dual-write-overview"></a>Kettős írás – áttekintés

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]



## <a name="what-is-dual-write"></a>Mi az a kettős írás?

A kettős írás egy olyan beépített infrastruktúra, amely közel valós idejű interakciót tesz lehetővé az ügyfélkapcsolati alkalmazások és a Finance and Operations alkalmazások között. Amikor a vevőkkel, termékekkel, személyekkel és műveletekkel kapcsolatos adatok az alkalmazás határain túl is eljutnak, az a szervezet minden részlegét felbátorítja.

A kettős írás szorosan összekapcsolt, kétirányú integrációt tesz lehetővé a Finance and Operations alkalmazások és a Dataverse között. A Finance and Operations alkalmazások bármely adatmódosulása írást eredményez a Dataverse szolgáltatásban, és a Dataverse bármely adatváltozása írást eredményez a Finance and Operations alkalmazásokban. Ez az automatizált adatáramlás integrált felhasználói élményt nyújt az alkalmazások között.

![Adatkapcsolat az alkalmazások között](media/dual-write-overview.jpg)

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

A kettős írás megfeleltetést hoz létre a Finance and Operations alkalmazások és az ügyfélkapcsolati alkalmazások koncepciói között. Ez az integráció a következő eseteket támogatja:

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
+ Önálló erőforrás-kezelés felhasználók számára
+ Integrált csatornák a kiskereskedelem és marketing modulhoz
+ Betekintési lehetőség promóciókba és engedményekbe
+ Szolgáltatáskérési funkciók
+ Egyszerűsített szolgáltatási műveletek

## <a name="top-reasons-to-use-dual-write"></a>A kettős írás használatának legfőbb okai

A kettős írás adatintegrációt tesz lehetővé az egész Microsoft Dynamics 365 alkalmazásban. Ez a robosztus keretrendszer összeköti a környezeteket és lehetővé teszi az üzleti alkalmazások együttműködését. Íme a legfontosabb okok a kettős írás használatára:

+ A kettős írás szorosan összekapcsolt, szinte valós idejű, kétirányú integrációt tesz lehetővé a Finance and Operations alkalmazások és a Dynamics 365 modellvezérelt alkalmazásai között. Az integrációnak köszönhetően a Microsoft Dynamics 365 egyben nyújt szolgáltatást az összes üzleti megoldáshoz. A Dynamics 365 Finance és Dynamics 365 Supply Chain Management szolgáltatásokat használó ügyfelek, akik nem Microsoftos megoldásokat használnak ügyfélkapcsolat-kezeléshez (CRM) a kettős írás támogatása miatt áttérnek a Dynamics 365 szolgáltatásra.
+ Az ügyfelekről, termékekről, műveletektől, projektektől és az eszközök internetes hálózatától (IoT) származó adatok automatikusan átáramlanak a Dataverse szolgáltatásba a kettős íráson keresztül. Ez a kapcsolat nagyon hasznos a Power Platform bővítésben érdekelt vállalatok számára.
+ A kettős írás infrastruktúrája a nincs kódolás/kevés kódolás elvet követi. Minimális mérnöki erőfeszítést kell tenni a szabványos táblák közti leképezések kiterjesztéséhez, és az egyéni leképezések szerepeltetéséhez.
+ A kettős írás online és offline módot is támogat. A Microsoft az egyetlen olyan vállalat, amely online és offline mód támogatását is kínálja.

## <a name="what-does-dual-write-mean-for-developers-and-architects-of-customer-engagement-apps"></a><a id="developer-architect"></a>Mit jelent a kettős írás az ügyfélkapcsolati alkalmazások fejlesztői és tervezői számára?

A kettős írás automatizálja a Finance and Operations alkalmazások és az ügyfélkapcsolati alkalmazások közti adatáramlást. A kettős írás két olyan AppSource-megoldást tartalmaz, amelyek telepítve van Dataverse-szolgáltatásban. A megoldások bővítik a tábla sémáját, beépülő moduljait és munkafolyamatait a Dataverse-ben, hogy ERP méretűre skálázhatók legyenek. A sikeres végrehajtás érdekében az ügyfélkapcsolati alkalmazások fejlesztőinek és tervezőinek ismerniük kell ezeket a változtatásokat, és együtt kell működniük az ellenpéldányaikkal a Finance and Operations alkalmazásokban.

Ha a Finance and Operations alkalmazásokkal paritást szeretne létrehozni, a kettős írás a séma néhány fontos változtatást eszközök a Dataverse sémájában. Ha megérti a konstrukciót, akkor a későbbiekben elkerülhetők lesznek a tervezéssel és fejlesztéssel kapcsolatos javítások.

+ Ha a kettős írású AppSource-csomagot telepítik, a Dataverse új fogalmakat kap, például a vállalatot és a felet. Ezek a koncepciók elősegítik, hogy a Dataverse-re épülő alkalmazások, köztük a Dynamics 365 Sales, Dynamics 365 Marketing, Dynamics 365 Customer Service és Dynamics 365 Field Service, zökkenőmentesen működhessenek együtt a Finance and Operations alkalmazásokkal.

+ A tevékenységek és megjegyzések egyesülnek, és bővítésükkel támogatják a C1 (a rendszer felhasználóit) és a C2 (a rendszer ügyfeleit).

+ Ha meg szeretné akadályozni, hogy a Finance and Operations alkalmazások és a Dataverse közötti pénznemátvitelek során az adatveszteséget, bővítse ki a tizedes helyek számát az ügyfélkapcsolati alkalmazások pénznem adattípusában. A funkció a meglévő sorokat a metaadat-réteg új kiterjesztett állapotára fordítja le. A folyamat során a program a pénzadatok helyett decimális adatokra fordítja le a pénznemet, és a pénznem értéke 10 tizedesjegyet támogat. Ez a funkció választható, és a szervezetek, amelyeknél nem szükséges a több, mint 4 tizedesjegy pontosság nem kell, hogy elfogadják. A további tudnivalókat lásd: [Pénznem-adattípus áttelepítése a kettős íráshoz](currrency-decimal-places.md).

+ [Dátum hatályossága](../../dev-tools/date-effectivity.md) hozzá lesz adva a Dataverse-hez. A múltbéli, jelenlegi és jövőbeli dátumokat is támogatni fogja ugyanazon táblában.

+ A termékek, árajánlatok, rendelések és számlák esetében támogatott a termék [egységének átváltása](../../../../supply-chain/pim/tasks/manage-unit-measure.md).

További tájékoztatás a közelgő módosításokról: [Újdonságok és módosítások a kettős írásban](whats-new-dual-write.md).



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]