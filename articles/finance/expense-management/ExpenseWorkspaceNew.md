---
title: Költségjelentések újragondolva
description: Ez a témakör a Microsoft Dynamics 365 Finance újratervezett és újragondolt költségjelentési bejegyzésekre vonatkozó élményével kapcsolatban tartalmaz információkat. Az új élmény egyszerűbbé teszi a költségjelentés végrehajtási folyamatát, és csökkenti a szükséges időt.
author: ryansandness
manager: AnnBe
ms.date: 06/14/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Operations, Core
ms.search.region: Global
ms.author: ryansand
ms.search.validFrom: 2019-6-30
ms.dyn365.ops.version: 10.0.3
ms.openlocfilehash: 8a8ad1ad84b8acaa54d8b03327157a930e562f59
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/27/2019
ms.locfileid: "2187659"
---
# <a name="expense-reports-reimagined"></a>Költségjelentések újragondolva

[!include[banner](../includes/banner.md)]

A költségjelentés bejegyzését újratervezték, hogy leegyszerűsítse a költségjelentés kitöltési folyamatát, és csökkentse a szükséges időt. Az új, költséggel kapcsolatos gyakorlat főbb összetevői a következők:

- Új költségkezelési munkaterület, amelyen a delegáltjai költségeihez is hozzáférhet.
- Az új bizonylategyeztetési gyakorlat, amellyel jobban megjelenítheti a fejléc szintű bizonylatokat, és leegyszerűsítheti a bizonylatok költségsorokhoz való csatolási folyamatát.
- Új írásvédett rács, amely sokkal több költségsor és további adatoszlopok megjelenítését teszi lehetővé. Ezután az összes részletezett és felosztott sor látható, a fölérendelt költségekkel együtt.
- Egyszerűsített ablaktábla a kiadások szerkesztéséhez.
- Újratervezett hiba-, figyelmeztetési és irányelvvel kapcsolatos üzenetek annak biztosítására, hogy a probléma megértéséhez és megoldásához megfelelő környezet álljon rendelkezésére. A Microsoft számos olyan üzenetet eltávolított, amely azelőtt jelent meg, mielőtt a felhasználóknak lehetőségük lett volna befejezni a feladataikat és foglalkozni a problémával, például a befejezetlen részletezésre vonatkozó üzenet.
- Új lap annak meghatározására, hogy mely mezők szükségesek a szervezetnél, mely mezők nem kötelezőek, és mely mezőket nem lehet rögzíteni. Ez a lap segít csökkenteni azoknak a mezőknek a számát, amelyeket a felhasználóknak be kell állítania.
- A költségjelentés új megjelenése, így a jelentések már nem tűnnek úgy, mintha a csak könyvelési szakemberek számára tervezték volna őket.

Az új élmény bekapcsolásához használja a **Funkciókezelés** munkaterületet, ahol bekapcsolhatja a **Költségjelentések újratervezve** funkciót. A funkció bekapcsolásakor a következő műveletek történnek:

- A meglévő költség munkaterületet az új munkaterülettel helyettesíti a program.
- A program hozzáad egy új menüelemet a költségmező láthatóságához.
- A program nem távolít el meglévő, költségelemekre vonatkozó menüelemeket (a meglévő oldal) vagy költségjelentési mezőket.
- A munkafolyamatok és az esetleges jóváhagyások továbbra is elviszik a meglévő költségjelentések lapra.

## <a name="getting-started-video-for-new-users"></a>Kezdő lépésekről szóló videó új felhasználóknak

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2Y7gO]

A (fenti videón látható) [Költséggel kapcsolatos gyakorlat a Dynamics 365 for Finance and Operations rendszerben](https://youtu.be/Ocy-MsTvEE0) szerepel a YouTube felületén megtalálható [Finance and Operations lejátszási listán](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW).

## <a name="new-features"></a>Új funkciók

| Új funkció | Leírás |
|---|----|
| Költségmező láthatósága | Egy új beállítási lap segítségével megadhatja, hogy mely mezők legyenek letiltva egy szervezetnél, hogy mely mezőkre van szükség, és mely mezők ajánlottak. |
| Kötelezően kitöltendő mezők | Az új egyszerű konfigurációval bizonyos mezőket kötelezővé tehet anélkül, hogy az irányelv-keretrendszert kellene használnia. |
| Választható mezők | A program hozzáad egy második lapot a választható mezőkhöz. Ily módon az alkalmazottak nem érzik úgy, mintha be kell állítaniuk ezeket a mezőket, de a mezők továbbra is könnyen hozzáférhetők. |
| Nem csatolt nyugták hozzáadása | A nem csatolt lehetőségek költségjelentéshez való hozzáadásának lehetősége jobban látható a munkaterületről és a költségjelentésen. |
| Továbbfejlesztett üzenetküldés | Jobban láthatók a költségsorok részletei, amelyeknél figyelmeztetések vagy hibák vannak. |
| Üzenetek csökkentése az üzenetsávon| Csökkentettük az információs napló üzeneteinek a számát, és a rendszer számos esetben aktívan igyekszik elkerülni az ismétlődő üzenetek megjelenését. |
| Csoportosított közös műveletek | A kezelőfelület letisztultabbá vált, valamint hozzáadtunk új műveletgombokat a legtöbb gyakori sorszintű művelethez és egy ellipszis gombot (…) a fejléc és a kevésbé gyakori művelet eléréséhez. |
| A láthatóságot növelő új munkaterület | Az új munkaterület olyan funkciókat és hivatkozásokat egyesít, amelyek lehetővé teszik a felhasználók számára a különböző területekre való ugrást. |
| Meglévő költségek és bizonylatok hozzáadása költségek létrehozása során | A költségjelentések létrehozásakor hozzáadhatja az összes, vagy csak a kiválasztott költségeket és bizonylatokat. |
| Árfolyam-számológép | Hozzáadtunk egy árfolyam-számológépet, amellyel kiszámíthatók az árfolyamok a saját pénzből fedezett több árfolyamos tranzakciókhoz. |
| Új költségsorok mentése és hozzáadása | A **Mentés** és **Új** gombok rendelkezésre állnak új költségek bevitelekor, hogy gyorsabban vihessen be költségsorokat. |
| Jobb láthatóság a felosztott és a részletezett sorok között | A részletezett és a szétosztott sorok közvetlenül megjelennek a kiadások listájában a láthatóság növelése érdekében, valamint könnyebben eldöntheti, hogy találhatók-e bennük irányelvvel kapcsolatos vagy más hibák. |
| Bizonylatok megjelenítése a részletezés során | A bizonylatok megjeleníthetők a részletezés során. |

A kezdeti kiadás a költségbejegyzési esetekre összpontosít. A költségjelentések felülvizsgálatára vagy jóváhagyására használt esetek mindegyike továbbra is a meglévő költségbejegyzés lapot fogja használni.

A következő funkciók vannak jelen a meglévő oldalon, de még nincsenek jelen az új oldalon. Ezek a funkciók a következő fontosabb kiadásoknál újra bevezetésre kerülnek:

- Jóváhagyások
- Kötelezettségek jóváhagyása és a könyvelés szerkesztésének lehetősége
- Több bejegyzési pont
- Utazásigénylés integrációja
- Adatentitás a költségmező láthatóságához
- Napidíjas költségekre vonatkozó bejegyzés
- Sorszintű munkafolyamat
- Ideiglenes jóváhagyói támogatás
- Speciális részletezés
