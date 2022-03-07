---
title: Pénztár (POS) javítások szerializált termékekhez
description: Ez a témakör a szerializált termékeken végzett fejlesztéseket sorolja fel, amelyek segítségével időt takaríthat meg, és hatékonyabban végezheti munkáját.
author: ShalabhjainMSFT
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: shajain
ms.search.validFrom: 2017-08-01
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 9b988e8046fadad4579a12966a5031929202e7411f00ca8e0de149380ddb34fc
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6741756"
---
# <a name="point-of-sale-pos-improvements-for-serialized-products"></a>Pénztár (POS) javítások szerializált termékekhez

[!include [banner](includes/banner.md)]

## <a name="overview"></a>Áttekintés

A Commerce központokban megadott beállítások alapján a termékek lehetnek szerializáltak vagy nem szerializáltak. A szerializált termékeknél minden egyes cikkhez is hozzárendelhető egy egyedi szám, amely segít nyomon követni a garanciákat, cikkeket, és segít megerősíteni a tulajdonjogot. Bár a szerializált termékekhez már a Modern/felhőalapú pénztár (POS) rendszerben hozzá lehetett adni sorozatszámokat, számos fejlesztés révén a pénztárosok most időt takaríthatnak meg és hatékonyabban dolgozhatnak.

## <a name="pos-improvements"></a>Pénztári fejlesztések

- **Sorozatszámokra nincs szükség a fizetésig** – korábban a pénztárosnak, aki szerializált terméket adott hozzá a tranzakcióhoz, meg kellett adnia egy sorozatszámot. Ennek a követelménynek hátránya volt vevőkezelési helyzetekben, amikor a pénztárosoknak és értékesítési munkatársaknak lehetőségük nyílt értéknövelő termékek értékesítésére. A kifizetési lépésig a terméket gyakran frissíteni kellett a kosárban. Ezért minden alkalommal, amikor a pénztáros új terméket adott hozzá, a rendszer kérte tőle a sorozatszámot. A sorozatszám párbeszédpanelen mostantól látható egy **Hozzáadás később** gomb. Így az értékesítési munkatárs felveheti a cikket a tranzakcióba, de később is megadhatja a sorozatszámot. Az értékesítési munkatársak gyorsan hozzáadhatnak és szerializálhatnak cikkeket a kosárhoz, és elég a sorozatszámot csak a fizetés előtt megadni. Ha a sorozatszám egy szerializált termékhez nincs megadva, a tranzakciót végrehajtó pénztáros hibaüzenetet kap. Ez az üzenet jelzi, hogy a folytatás előtt a pénztárosnak meg kell adnia a hiányzó sorozatszámokat.

    Minden egyes szerializált cikkhez, ahol a sorozatszám ki lett hagyva, megjegyzés jelenik meg a tranzakciósor alatt. Ez a megjegyzés azt jelzi, hogy a sorozatszám a cikkhez még nem lett megadva. A pénztáros így gyorsan megtalálhatja a cikkeket, amelyekhez még nem tartozik sorozatszám.

    Az új **Sorozatszám hozzáadása** művelet olyan cikkekhez is biztosít sorozatszámot, amelyekhez nem tartozik sorozatszám. A sorozatszám megadása után azt nem lehet szerkeszteni. A pénztárosnek érvénytelenie kell a sort, és ismét hozzáadni a terméket.
    
- **Sorozatszámok nem szükségesek vevői rendelések feladásához** – a vevői rendelések feladhatók egy üzletben, és teljesíthetők egy másikból. A vevői rendelést felvevő pénztárosnak nem kell megadnia a sorozatszámot. A sorozatszám megadására a kitárolási vagy felvételi lépés során kerül sor. Azonban a sorozatszámot meg kell adni az összes olyan sortételnél, amelynél a **Végrehajtás** szállítási típus van kiválasztva. Ellenkező esetben a tranzakció nem hajtható végre.
- **A szerializált termékeket a rendszer nem összesíti a tranzakció képernyőn** – a **Termékek összesítése** beállítás a **Terminál** mezőcsoportban a **Funkcióprofil** oldalon ugyanazon nem szerializált termékek összesítését teszi lehetővé a tranzakció képernyőn. Ha az ugyanazon termékek vannak összesítve, azok könnyebben láthatók a tranzakciós rácsban. Azonban mivel a sorozatszámok általában egyediek, és az értékesítési munkatársaknak nem kell sorozatszámokat megadniuk a fizetésig, a **Termékek összesítése** beállítás nem vonatkozik a szerializált termékekre. Ezért a szerializált termékek összesítése nem történik meg a tranzakció képernyőn, ha a **Termékek összesítése** beállítás ki van választva.
- **A naplók sorozatszám szerinti keresésének képessége** – A naplókat mostantól sorozatszám szerint is lehet keresni. Ehhez nyissa meg a „Naplók” műveletet, és nyomja meg a „Speciális keresés” gombot az alkalmazássávon. A „Szűrő hozzáadása” gomb segítségével szűrő alkalmazható annak érdekében, hogy a sorozatszámokra is kereshessen.


[!INCLUDE[footer-include](../includes/footer-banner.md)]