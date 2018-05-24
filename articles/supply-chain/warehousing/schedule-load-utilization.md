---
title: "Terhelési kihasználtság ütemezése"
description: "Ez a témakör ismerteti egy adott raktár esetén a rakomány beállítását és ütemezését."
author: MarkusFogelberg
manager: AnnBe
ms.date: 05/26/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WMSSpaceUtilSetup
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations
ms.custom: 269384
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: d52ad452c615a61739582431fcd100a7efa3d93a
ms.openlocfilehash: 350666cee8f2643c53e9eed8ee73299bbea1e757
ms.contentlocale: hu-hu
ms.lasthandoff: 04/26/2018

---

# <a name="schedule-load-utilization"></a>Terhelési kihasználtság ütemezése

[!include[banner](../includes/banner.md)]

Ütemezheti a terhelési kihasználtságot a kijelölt helytípusokhoz, valamint megtervezheti a jelenlegi és a jövőbeli terhelési kihasználtságot. Megtervezheti egy vagy több hely terhelését terhelési egységenként (raktár vagy zóna), vagy zóna és raktár kombinációjára.

## <a name="schedule-and-view-the-load-for-a-warehouse-or-site"></a>Raktár vagy hely terhelésének ütemezése és megtekintése

Helyek, raktárak vagy zónák terhelésének ütemezéséhez létre kell hoznia egy helykihasználási beállítást, és társítania kell egy alaptervvel.

A helykihasználási beállításban helytípusokat használ, mint például **Ömlesztett tárolóhely** és **Kitárolási hely** annak a megadásához, hogy hogyan legyen a helykihasználás tervezve. A tárolás terhelési módját is megadhatja, például **Zóna**.

A helykihasználás jövőbeli megtervezése a társított alapterv adatain végzett számításokon alapul. Az alaptervek előrejelzik a gyártáshoz és a műveletekhez szükséges bejövő és kimenő rendelések erőforrás-tervezését. A szabad terület előrejelzése a helykihasználás beállítása és a kiválasztott alapterv közötti kapcsolat alapján történik.

A helykihasználás beállításánál kiválasztott tárolásterhelési mód segítségével adhatja meg, hogy a terhelést minden egyes raktárra vagy zónára meg kell-e tervezni, vagy a tervezésnek tartalmaznia kell mind a raktár, mind a zóna adatait. Azt is megadhatja, hogy ki kell-e zárni a blokkolt helyeket a terhelési kihasználtság számításánál.

A helykihasználás tervezéséhez létrehozhatja a **Raktár terhelési kihasználtsága** jelentést. A jelentés létrehozásakor megadhatja, hogy a terhelési kihasználtságot minden egyes helyre külön, több helyre együtt vagy a kiválasztott terhelési egységre, például zónára vagy raktárra kell-e tervezni.

### <a name="create-a-space-utilization-setup-for-a-warehouse"></a>Raktár helykihasználási beállításának létrehozása

1. Válassza ki **Készletkezelés** \> **Beállítás** \> **Raktárfigyelés** \> **Helykihasználás**.
2. Válassza az **Új** elemet egy új helykihasználási beállítás létrehozásához. Adja meg az új beállítás azonosítóját és nevét.
3. A **Tárolás terhelési módja** mezőben válassza ki, hogy a helykihasználás áttekintése raktár, zóna, vagy raktár és zóna szerint legyen-e.
4. Állítsa a **Blokkolt helyek kihagyása** lehetőséget **Igen** beállításra a zárolt készletezési helyek kihagyásához a rendelkezésre álló hely számításából. Egy készlethely bejövő vagy kimenő forgalmának blokkolásához meg kell adnia a helyhez egy blokkolási okot az **Bemenet zárolva** vagy **Kimenet zárolva** mezőben az **Egyéb** gyorslapon a **Készlethelyek** képernyőn.
5. A **Helytípus** gyorslapon jelölje ki a helykihasználtság kiszámításánál figyelembe veendő helytípusokat. Legalább egy helytípust ki kell választania a tervezéshez.

### <a name="associate-a-space-utilization-setup-with-a-master-plan"></a>Helykihasználtsági beállítás társítása egy alaptervhez

1. Válassza ki ezt: **Készletkezelés** \> **Időszakos feladatok** \> **Terhelési kihasználtság ütemezése**.
2. Válasszon ki egy alaptervet az **Alapterv** mezőben.
3. A **Napok száma** mezőben adja meg a jelenlegi és jövőbeli terhelések tervezéséhez tartozó napok számát.
4. A **Helykihasználás** mezőben válassza ki azt a helykihasználási beállítást, melyet a jelenlegi és jövőbeli terhelések tervezéséhez kíván használni.

### <a name="specify-the-load-utilization-projection-and-view-information"></a>A terheléskihasználás tervezési és megtekintési adatainak megadása

1. Válassza ezt: **Készletkezelés** \> **Lekérdezések és jelentések** \> **Fizikai leltárjelentés** \> **Raktár terhelési kihasználtsága**.
2. A **Megjelenítés alapja** mezőben válassza ki a helykihasználás tervezési szintjét:

    - **Hely** – Ha minden helyre meg szeretné tervezni a helykihasználást. Ez az előrejelzés akkor hasznos, ha például meg szeretné tekinteni a hely összes raktárát, így egyensúlyban tarthatja a raktárak közötti helykihasználást.
    - **Terhelési egység** – Ha zónákra vagy raktárakra szeretné megtervezni a helykihasználást. A rendelkezésre álló hely ezután a kiválasztott értéknek megfelelő előre jelzett a **Tárolás terhelési módja** mezőben a **Helykihasználtsági** oldalon a helykihasználási beállítás létrehozása után.

3. Hajtsa végre az előző lépésben kiválasztott értéktől függően az alábbi lépések közül:

    - Ha a **Hely** lehetőséget választotta a **Megjelenítés alapja** mezőben, a **Hely** mező rendelkezésre áll. Válasszon ki a egy vagy több helyet az előrejelzéshez.
    - Ha a **Terhelési egység** lehetőséget választotta a **Megjelenítés alapja** mezőben, a **Hely** mező rendelkezésre áll. A terhelési egység megadása.

4. A **Terhelési típus** mezőben válassza ki a **Térfogat** vagy **Tömeg** elemet a raktár üzemi egységét, amelyhez a helyet meg kívánja tervezni.
5. A **Helykihasználás beállítása** mezőben jelölje be azt a helykihasználási beállítást, amelyet alapul fog venni az előrejelzés.

