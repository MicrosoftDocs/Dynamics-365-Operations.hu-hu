---
title: Figyelmeztetések áttekintése (videofelvételt tartalmaz)
description: Ez a cikk a figyelmeztetésekkel kapcsolatban tartalmaz általános tájékoztatást. A figyelmeztetések használatával lehet információkat nyerni a munkanap során nyomon követni kívánt eseményekről.
author: RichdiMSFT
ms.date: 09/04/2019
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: EventCreateRule
audience: Application user
ms.reviewer: sericks
ms.search.region: Global
ms.author: richdi
ms.search.validFrom: 2018-3-30
ms.dyn365.ops.version: Platform update 15
ms.openlocfilehash: b81eb8e0be4c7d7357a6b8b7b5f0ac025b9ab8ca
ms.sourcegitcommit: 873d66c03a51ecb7082e269f30f5f980ccd9307f
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/06/2022
ms.locfileid: "9124258"
---
# <a name="alerts-overview"></a>Figyelmeztetések áttekintése

[!include [banner](../includes/banner.md)]

## <a name="about-alerts"></a>Figyelmeztetések
A figyelmeztetések értesítési rendszert alkotnak a kritikus eseményekere vonatkozóan a rendszerben. A figyelmeztetések használatával lehet információkat nyerni a munkanap során nyomon követni kívánt eseményekről. Egyszerűen létrehozhatja saját figyelmeztetésiszabály-rendszerét, hogy figyelmeztetést kapjon a következő eseményekkel kapcsolatban: lejárt szállítási határidők, törölt rendelések, változó árak és egyéb olyan események, amelyekre valamilyen válaszreakció szükséges.

A vállalatirányításban (ERP) számos tipikus forgatókönyv létezik, ahol a riasztási funkció használható. Íme néhány példa.

### <a name="scenario-1-create-an-alert-rule-for-new-sales-orders"></a>1.eset: Figyelmezetési szabály létrehozása az új értékesítési rendelésekhez

1. Megjelenik a **Minden értékesítési rendelés** lap.
2. A műveleti ablakban a **Beállítások** lapon a **Megosztás** csoportban válassza az **Egyéni figyelmeztetés létrehozása** lehetőséget.
3. A **Figyelmeztetési szabály létrehozása** párbeszédpanelen, a **Figyelmeztetés feltétele** gyorslapon az **Esemény** mezőben válassza **A rekord létrehozva** lehetőséget.

### <a name="scenario-2-create-an-alert-rule-for-postponement-of-a-delivery-date"></a>2. eset: Figyelmeztetési szabály létrehozása a szállítási dátumok halasztásához

1. Megjelenik a **Minden beszerzési rendelés** lap.
2. Válassza ki egy beszerzési rendelés azonosítóját a beszerzési rendelés részleteinek eléréséhez.
3. Bontsa ki a **Beszerzési rendelés fejléce** gyorslapot.
4. A műveleti ablakban a **Beállítások** lapon a **Megosztás** csoportban válassza az **Egyéni figyelmeztetés létrehozása** lehetőséget.
5. A **Figyelmeztetési szabály létrehozása** párbeszédpanelen, a **Figyelmeztetés feltétele** gyorslapon a **Mező** mezőben válassza a **Szállítási időpont** lehetőséget.
6. Az **Esemény** mezőben válassza az **el lett halasztva** lehetőséget.
    
A **figyelmeztetési szabály létrehozása** párbeszédpanel bezárását követően a szabály megjelenik a **Figyelmeztetési szabályok kezelése** oldalon. Használja a **Figyelmeztetési szabályok kezelése** lapot a meglévő figyelmeztetési szabályok frissítésére. Például módosíthat eseményindítókat, eseményfrissítési értesítéseket és frissítheti a lejárati dátumokat. A **Figyelmeztetési szabályok kezelése** oldal megnyitásához nyomja meg a **Figyelmeztetést kérek** gombot a műveleti ablak **Beállítások** lapján.

## <a name="what-occurs-when-an-alert-rule-is-created"></a>Mi történik figyelmeztetési szabály létrehozása esetén?

Figyelmeztetési szabályok létrehozása esetén egy előre megadott esemény társítható egy konkrét mezőhöz. Például a mezőben megadott dátum megérkezik, vagy a mező tartama módosul. Alternatívaként egy eseményt társíthat egy adott oldal feljegyzéseihez. Például új rekord jön létre, vagy egy rekord törlődik.

Amikor a kiválasztott esemény bekövetkezik a mezőnél vagy az oldal egyik rekordjánál, a rendszer figyelmeztetést küld Önnek. Például létrehozhat egy olyan szabályt, amellyel társíthatja egy adott beszerzési rendeléssor **Szállítási dátum** mezőjét **határidő ennyi ideje lejárt** eseménnyel. Öt napos időkeretet állít be. Ebben az esetben a figyelmeztetés elküldésére öt nappal a beszerzési rendelés határideje után kerül sor.

Ezenkívül feltételek beállításával finomíthatja a figyelmeztetési szabályokat. Például figyelmeztetést kaphat az adott szállítói számlák számára létrehozott új beszerzési rendelésekről.

## <a name="preparing-for-an-alert"></a>Előkészületek figyelmeztetésre

Mielőtt figyelmeztetési szabályokat állítana be, döntse el, mikor vagy milyen helyzetben szeretne figyelmeztetést kapni. Ha tudja, mely eseményről szeretne értesítést kapni, keresse meg azt az oldalt, amelyen az eseményt előidéző adat megtalálható. Az esemény lehet egy elérkező dátum vagy egy bizonyos módosítás. Ezért meg kell találni a lapot, ahol a dátum meg van adva, vagy ahol megjelenik a módosuló mező vagy a létrehozott új rekord. Amint birtokában van ennek az adatnak, létrehozhatja az értesítési szabályt.

## <a name="components-of-an-alert-rule"></a>A figyelmeztetési szabályok összetevői

A figyelmeztetési szabályok öt összetevőből állnak:

- **Esemény** – A figyelmeztetési szabályt kiváltó esemény lehet egy beérkező dátum vagy egy bizonyos módosítás. Események adhat meg a **Figyelmeztető e-mailek küldése a feladatállapot módosulásakor** gyorslapján a **Figyelmeztetési szabály létrehozása** párbeszédpanelnek.
- **Feltétel** – Az **Figyelmeztetés időszaka** gyorslapján a **Riasztási szabály létrehozása** párbeszédpanelnek kiválaszthatja a feltétel hatókörét, amely megszabja, mikor kap riasztást az eseményekről. A szabályt vagy csak az aktuális rekordra, vagy a lapon látható összes rekordra alkalmazhatja. Ha a szabály több jogi személyre érvényes, a **Szervezeti szintű** beállítást be lehet állítani **Igen** értékre.
- **Szabály érvényességi ideje** – A **Figyelmeztetés vége** gyorslapján a **Riasztási szabály létrehozása** párbeszédpanelnek megadhatja, hogy meddig legyen aktív a figyelmeztetési szabály.
- **Tartalom** – a **Figyelmeztetés módja** gyorslapján a **Figyelmeztetési szabály létrehozása** párbeszédpanelnek megadhatja a figyelmeztető üzenetek által használandó tárgy szövegét és üzenet szövegét.
- **Felhasználó** – a **Figyelmeztetés címzettje** gyorslapján a **Figyelmeztetési szabály létrehozása** párbeszédpanelnek megadhatja, hogy melyik felhasználó kapja meg a figyelmeztető üzeneteket. A felhasználói azonosító alapértelmezés szerint be van jelölve.

    > [!NOTE]
    > Ez a beállítás a szervezeti rendszergazdákra korlátozódik.

## <a name="videos"></a>Videók

### <a name="how-to-use-alerts-to-monitor-filtered-data"></a>A figyelmeztetések használata a szűrt adatok figyeléséhez

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3DWZ3]

A [(fent](https://youtu.be/ZYKMcv6kl9s) látható) [szűrt adatsúdó figyeléséhez használt figyelmeztetések használatának beállítása a pénzügyi és műveleti elérhetővé](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) válik YouTube.

### <a name="alert-rule-options"></a>Riasztási szabály beállításai

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3E4PV]

A [figyelmeztetési szabály beállítási lehetőségeiről](https://youtu.be/cpzimwOjicM) készült videofelvétel (fent látható) [a pénzügyi és műveleti lehetőségek](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) között.YouTube




[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
