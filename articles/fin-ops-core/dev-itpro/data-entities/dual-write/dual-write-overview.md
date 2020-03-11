---
title: Kettős írás – áttekintés
description: Ez a témakör áttekintést nyújt a kettős írásról. A kettős írás egy olyan infrastruktúra, amely közel valós idejű interakciót tesz lehetővé a Microsoft Dynamics 365 modellvezérelt alkalmazások és a Finance and Operations alkalmazások között.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 02/06/2020
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
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: 12c6a39700a260c138fab67ed370f94b3aa04213
ms.sourcegitcommit: a688c864fc609e35072ad8fd2c01d71f6a5ee7b9
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/20/2020
ms.locfileid: "3075986"
---
# <a name="dual-write-overview"></a>Kettős írás – áttekintés

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

## <a name="what-is-dual-write"></a>Mi az a kettős írás?

A kettős írás egy olyan beépített infrastruktúra, amely közel valós idejű interakciót tesz lehetővé a Microsoft Dynamics 365 modellvezérelt alkalmazásai és a Finance and Operations alkalmazások között. Amikor a vevőkkel, termékekkel, személyekkel és műveletekkel kapcsolatos adatok az alkalmazás határain túl is eljutnak, az a szervezet minden részlegét felbátorítja.

A kettős írás szorosan összekapcsolt, kétirányú integrációt tesz lehetővé a Finance and Operations alkalmazások és a Common Data Service között. A Finance and Operations alkalmazások bármely adatmódosulása írást eredményez a Common Data Service szolgáltatásban, és a Common Data Service bármely adatváltozása írást eredményez a Finance and Operations alkalmazásokban. Ez az automatizált adatáramlás integrált felhasználói élményt nyújt az alkalmazások között.

![Adatkapcsolat az alkalmazások között](media/dual-write-overview.jpg)

A kettős írásnak két aspektusa van: egy *infrastruktúra* szempont és egy *alkalmazási* szempont.

### <a name="infrastructure"></a>Infrastruktúra

A kettős írás infrastruktúrája bővíthető és megbízható, és a következő kulcsfontosságú funkciókat tartalmazza:

+ Az alkalmazások közötti szinkron és kétirányú adatáramlás
+ Szinkronizálás, lejátszási, szüneteltetési és felzárkóztatás módokkal együtt a rendszer támogatása érdekében az online és offline/aszinkron mód esetében.
+ A kezdeti adatok szinkronizálásának lehetősége az alkalmazások között
+ A tevékenység és a hibanaplók konszolidált nézete adatrendszergazdák számára
+ Egyéni figyelmeztetések és küszöbértékek konfigurálásának és értesítésekre való feliratkozás képessége
+ Intuitív felhasználói felület (UI) szűréshez és átalakításokhoz
+ Entitásfüggőségek és kapcsolatok beállításának lehetősége
+ Bővíthetőség a szabványos és egyéni entitások és leképezések esetében
+ Megbízható alkalmazáséletciklus-kezelés
+ Beépített beállítási élmény új ügyfelek számára

### <a name="application"></a>Alkalmazás

A kettős írás megfeleltetést hoz létre a Finance and Operations alkalmazások koncepciói és a Dynamics 365 modellvezérelt alkalmazásainak koncepciói között. Ez az integráció a következő eseteket támogatja:

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
+ Az ügyfelekről, termékekről, műveletektől, projektektől és az eszközök internetes hálózatától (IoT) származó adatok automatikusan átáramlanak a Common Data Service szolgáltatásba a kettős íráson keresztül. Ez a kapcsolat nagyon hasznos a Microsoft Power Platform bővítésben érdekelt vállalatok számára.
+ A kettős írás infrastruktúrája a nincs kódolás/kevés kódolás elvet követi. Minimális mérnöki erőfeszítést kell tenni a szabványos táblák közti leképezések kiterjesztéséhez, és az egyéni leképezések szerepeltetéséhez.
+ A kettős írás online és offline módot is támogat. A Microsoft az egyetlen olyan vállalat, amely online és offline mód támogatását is kínálja.

## <a name="what-does-dual-write-mean-for-users-and-architects-of-crm-products"></a>Mit jelent a kettős írás a CRM-termékek felhasználói és tervezői számára?

A kettős írás automatizálja a Finance and Operations alkalmazások és a Common Data Service szolgáltatás közti adatáramlást. A jövőbeli kiadásokban a Dynamics 365 modellvezérelt alkalmazásainak koncepcióit (pl. ügyfél, kapcsolattartó, árajánlat és megrendelés) a közepes és a felső-közép régióban található ügyfelekre is kiterjesztik.

Az első verzióban az automatizálás legtöbb elemét kettős írásos megoldások kezelik. A későbbi verziókban ezek a megoldások a Common Data Service program részévé válnak. Ha megértjük a Common Data Service közelgő változtatásait, akkor hosszú távon erőfeszítéseket spórolhat meg. Többek között az alábbi kritikus fontosságú módosítások történtek:

+ A Common Data Service új koncepciókat fog tartalmazni, például vállalat és felek. Ezek a fogalmak hatással lesznek az összes Common Data Service szolgáltatásra épített alkalmazásra, például a Dynamics 365 Sales, Dynamics 365 Marketing, Dynamics 365 Customer Service és Dynamics 365 Field Service alkalmazásra.
+ A tevékenységek és megjegyzések egyesülnek, és bővítésükkel támogatják a C1 (a rendszer felhasználóit) és a C2 (a rendszer ügyfeleit).
+ Íme a közelgő változások egy része a Common Data Service szolgáltatásban:

    - A decimális adattípus veszi át a pénz adattípus helyét.
    - A dátumérvényesség múltbéli, jelenlegi és jövőbeli dátumokat is támogatni fog ugyanazon a helyen.
    - Több támogatás áll majd rendelkezésre pénznemekkel és árfolyamokkal kapcsolatban, és felülvizsgálják az **Árfolyam** alkalmazásfejlesztési felületet (API).
    - A program támogatja az egységek átváltását.

A közelgő változásokkal kapcsolatos további információkért lásd: [Adatok a Common Data Service szolgáltatásban – 1. és 2. fázis](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/extensibility/extensibility-roadmap).
