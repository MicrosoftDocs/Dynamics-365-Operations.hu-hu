---
title: Javításkezelés
description: A problémákat csoportokba rendszerezheti, így hozzájárul ahhoz, hogy a korábban már bevált megoldások javaslatként elérhetők legyenek.
author: kamaybac
ms.date: 04/30/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAConditionTable, SMASymptomArea, SMADiagnosisArea, SMAResolutionTable, SMARepairStage
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1456c65f28d2a1d06497ddde81c9e68cc078c061
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/29/2021
ms.locfileid: "7567919"
---
# <a name="repair-management"></a>Javításkezelés       

[!include [banner](../includes/banner.md)]


A javításkezeléshez a roblémákat csoportokba rendszerezheti. Ez hozzájárul ahhoz, hogy a korábban már bevált megoldások javaslatként elérhetők legyenek.

Ön beállítja a tüneteket, a diagnózist és a megoldás beállításait. Ezeket mindet alkalmazhatja később, amikor hasonló elem érkezik javításra. Javítási állapotokat is beállíthat, amelyekkel egy-egy javítási kérdés előrehaladását nyomon lehet követni.

## <a name="setting-up-repair-management"></a>A javításkezelés beállítása

A következő beállítási űrlapok segítségével adja meg a tünetek, a diagnózis és a megoldás meghatározásához használt adatokat a javításhoz.

- **Szolgáltatáskezelés** \> **Beállítás** \> **Javítás** \> **Feltételek**.
- **Szolgáltatáskezelés** \> **Beállítás** \> **Javítás** \> **Tünetterületek**.
-  **Szolgáltatáskezelés** \> **Beállítás** \> **Javítás** \> **Diagnózisterületek**.
- **Szolgáltatáskezelés** \> **Beállítás** \> **Javítás** \> **Megoldások**.
- **Szolgáltatáskezelés** \> **Beállítás** \> **Javítás** \> **Javítási állapotok**.

## <a name="symptoms-and-conditions"></a>Tünetek és feltételek

A tünetek a probléma vevő általi leírását jelentik. A tünetek a vevő azon megfigyeléseit foglalják magukban, amelyek a javítás szükségességét jelzik.

Beállíthat tünetterületeket, tünetkódokat és feltételeket. A tünetterület a meghibásodás területét fedi le, a tünetkód a meghibásodása tünetét fedi le.. A feltétel azt a helyzetet vagy környezetet mutatja be, amelynél a probléma előfordul.

**Példa**

A számítógépet azért hozták be javításra, mert a merevlemez hosszabb ideig tartó használat után nem működik. A merevlemez meghibásodása "kék képernyő" hibaüzenetet okoz. A technikust, aki átveszi a számítógépet, a következő tüneteket és feltételeket rögzíti:

1.  A tünetterület a merevlemez

2.  A tünetkód a "kék képernyő" hiba

3.  A körülmény az, hogy a merevlemez hosszabb idejű használat után hibásodik meg

## <a name="diagnosis-and-resolutions"></a>Diagnózis és megoldások

A diagnózis és a megoldások mezői a javítási szempontból tett állítások. Ezek azok a lépések, amelyeken egy technikus végigment a probléma kivizsgálása céljából.

A diagnosztikai terület foglalkozik a feladat megoldásához végrehajtandó művelettel. A diagnóziskód mutatja, hogyan történt a probléma kezelése, míg a megoldás lehet az, hogy a cikket javították, kicserélték, vagy a vevő visszavonta a rendelést. Ha például a számítógépet megjavítják, a diagnózis területe tartalmazhatja a „hibás alkatrész” leírást, a diagnóziskód lehet „új videokártya beszerelve”, míg a megoldás lehet „cserélve”.

## <a name="repair-stages"></a>Javítási állapotok

A javítási állapotok a javítási folyamat haladását mutatják. A javítási állapothoz egy **Elkészült** láttamozási paraméter is tartozik, amely mutatja, hogy a javítási sor befejezése megtörtént, és rögzítve van a befejezés dátuma és időpontja.

## <a name="applying-repair-management"></a>A javításkezelés alkalmazása

Ahhoz, hogy egy cikken alkalmazható legyen a javításkezelés, a cikken be kell lennie állítva egy szervizrendeléshez tartozó szolgáltatásiobjektum-kapcsolatnak. Ezután a szervizrendelésből létrehozhat egy javítási sort az aktuális feladatra vonatkozó információval. A javítási soron határozza meg a javítás alatt álló szolgáltatási objektumot, valamint a tünetekkel, diagnózissal és a végrehajtással kapcsolatos információkat. A javítási sorhoz jegyzetet is létrehozhat.

A javítási folyamat minden lépéséhez létrehozhat külön javítási sort.

## <a name="create-a-repair-line-on-a-service-order"></a>Javítási sor létrehozása szervizrendeléshez

1.  Lépjen ide: **Szolgáltatáskezelés** \> **Közös** \> **Szervizrendelések** \> **Szervizrendelések**.

2.  Válassza ki azt a szervizrendelést, amelyik a javítást igénylő szolgáltatási objektumot tartalmazza.

3.  Válassza a **Javítás** \> **Javítási sorok** elemet a **Javítási sorok** képernyő megnyitásához.

4.  Válassza ki az **Új** lehetőséget egy új sor létrehozásához.

5.  Válasszon ki egy szolgáltatási objektumot. Bármely szolgáltatási objektum választható, amelyiknél be van állítva objektumkapcsolat a szervizrendeléshez.

6.  Válassza ki a javítási sorban az odavágó, előre beállított tüneteket, diagnózis- és végrehajtási értékeket, és ha szükséges, a **Megjegyzés** fülre kattintva hozzon létre jegyzetet a javítási sorhoz.

7.  Az új javítási sor mentéséhez válassza a **Mentés** parancsot. A **Javítási sorok** képernyő **Általános** lapjának **Létrehozás dátuma és időpontja** mezője frissül a mentés dátumával.

## <a name="tracking-progress-and-resolving-a-repair-issue"></a>Nyomon követési állapot és egy javítási feladat megoldása

A javítási sor javítási állapotainak megadásával nyomon követheti a javítás előrehaladását.

Amikor egy javítási feladat elkészül, lezárhatja a javítási sort. A javítási állapotot állítsa be olyan állapotra, amelynél az **Elkészült** tulajdonság engedélyezve van. Befejezési időként a program az aktuális dátumot és időt regisztrálja a soron.

## <a name="close-a-repair-line-for-a-resolved-issue"></a>Megoldott feladat javítási sorának lezárása

1.  Nyissa meg a **Javítási sorok** képernyőt. Végezze el a témakörben korábban, a javítási sor létrehozásánál ismertetett lépéseket.

2.  Válassza ki a lezárni kívánt javítási feladathoz tartozó javítási sort.

3.  A **Javítási állapot** mezőben válasszon olyan állapotot, amelynél engedélyezve van az **Elkészült** tulajdonság.

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]