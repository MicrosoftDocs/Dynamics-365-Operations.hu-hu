---
title: A hullámfeldolgozás konfigurálása
description: Ez az útmutató leírja, hogy hogyan állíthatja be azokat a feltételeket, amelyek meghatározzák, hogy milyen munkát hozzon létre a rendszer a raktárra vonatkozóan, a hullám feldolgozásakor, és hogy a hullámokat manuálisan vagy automatikusan dolgozzák-e fel.
author: ShylaThompson
manager: tfehr
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSWaveTemplateTable, InventLocationIdLookup, WHSParameters, ProdParameters, whswavetablecreatenew, WHSWaveTable, WHSWaveAttributes, WHSKanbanWaveTable, WHSWaveTableListPage, WHSKanbanWaveTableListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e22816b33739141fbcd188d631a07313db415959
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4977288"
---
# <a name="configure-wave-processing"></a>A hullámfeldolgozás konfigurálása

[!include [banner](../../includes/banner.md)]

Ez az útmutató leírja, hogy hogyan állíthatja be azokat a feltételeket, amelyek meghatározzák, hogy milyen munkát hozzon létre a rendszer a raktárra vonatkozóan, a hullám feldolgozásakor, és hogy a hullámokat manuálisan vagy automatikusan dolgozzák-e fel. A hullámsablonok és a lekérdezések beállításával határozza meg a feltételeket, amelyek megegyeznek az értékesítési rendelés, a termelési rendelés vagy a kanban rendelések kiadott soraival rendelkező hullámmal. A rendszer a hullám feldolgozását azokban raktárházakban végzi, amelyek a Raktárház kezelési modul funkcióját használják, és nem pedig Készlet kezelési modul funkcióját. Ezt a folyamatot lefuttathatja az USMF bemutatócégen.

1. Válassza a **Navigációs ablaktábla >Modulok > Raktárkezelés > Beállítás > Hullámok > Hullámsablonok** lehetőséget
2. Kattintson az **Új** elemre.
3. Adjon meg egy értéket a **Hullámsablon neve** mezőben. A hullámsablon beállításakor meghatározza azt a sorrendet, amelyben a sablonok megegyeznek az értékesítési rendeléseken, a termelési rendeléseken vagy kanbanokon kiadott sorral. Ha egy sor ki van adva a raktárba vagy a termeléshez, azt az első hullámsablont használja, amely megfelel a feltételnek. Javasoljuk, hogy a legspecifikusabb feltételekkel kialakított sablont helyezze a lista elejére. Minél szélesebbek a feltételek, annál valószínűbb, hogy egy sor teljesíti a feltételeket, és ez ahhoz vezethet, hogy a rendszer nem a megfelelő hullámhoz rendeli a sort.  
4. Adjon meg egy értéket a **Hullámsablon leírása** mezőben.
5. A **Hely** mezőben adjon meg vagy válasszon ki egy értéket. Az USMF használata esetén választhatja a 2-es helyet.  
6. A **Raktár** mezőben adjon meg vagy válasszon ki egy értéket. Az USMF használata esetén kiválaszthatja az 24-es raktárt.  
7. Állítsa az **Hullámlétrehozás automatizálása** mezőt **Igen** értékre. Válassza ezt a lehetőséget, hogy a rendszer automatikusan hozzon létre hullámot, amikor egy értékesítési rendelés, termelési rendelés vagy kanban kiadásra kerül a raktárba.  
8. Állítsa a **Hullám feldolgozása a raktárba történő kiadáskor** lehetőséget **Igen** értékre. Ha bejelöli ezt a lehetőséget, a rendszer automatikusan feldolgozza a hullámot és létrehozza a munkát, valahányszor egy sor kiadásra kerül a raktárba.  
9. Állítsa a **Hullámkiadás automatizálása mezőt** **Igen** értékre. Ezzel a beállítással automatikusan adhatja ki a hullámot. A rendszer létrehozza a kitárolási munkát, ami hozzáférhetővé vélik a mobileszközökön.  
10. Állítsa a **Hozzárendelés nyitott hullámokhoz** mezőt **Igen** értékre. A rendszer a hullámsablon lekérdezésszűrője alapján rendeli hozzá a sorokat a hullámokhoz.  
11. Állítsa a **Hullám feldolgozása automatikusan a küszöbértéknél** lehetőséget **Igen** értékre. Válassza ezt a lehetőséget, hogy a rendszer automatikusan feldolgozza a hullámot, amikor annak értékei elérik a súlyra, szállítmányra vagy sorokra vonatkozóan a Hullám küszöbértékek mezőcsoportban beállított küszöbértékeket. Ez a lehetőség csak akkor érhető el, ha a Szállítás beállítás van kiválasztva a Hullámsablon típusa mezőben.  
12. Állítsa a **Feltöltési munka kiadásának automatizálása** mezőt **Igen** értékre. Válassza ki ezt a lehetőséget, hogy a rendszer automatiksuan létrehozza és kiadja az igényalapú feltöltési munkát. Hozzá kell adnia az újratöltési hullámmódszert a hullámsablonhoz, majd létrehozni egy Hullámigény típusú újratöltési sablont.  
13. Bontsa ki a **Módszerek** szakaszt.

    - Az alapvető hullámfeldolgozási módok lehetővé teszik a tevékenységek sorozatát, amelyen minden hullám áthalad, amikor feldolgozta a rendszer. Például rendelkezhet hullám feltöltési móddal. Egy módszer hozzáadásakor az automatikusan a megfelelő helyen jelenik meg a lépések sorrendjében. Ha a Feltöltési munka kiadásának automatizálása beállítást Igen értékre állította be, akkor itt kell hozzáadnia az újratöltési módszert.  
    - A hullámattribútumok szűrőként működnek azon típusú cikkek korlátozásához, amelyek a hullámokat használhatják. Például megadhatja a egy cikkcsoportot.  
14. Kattintson a **Mentés** gombra.
15. Zárja be a lapot.
16. Ugorjon a **Raktárkezelés > Beállítás > Raktárkezelési paraméterek** elemre.
17. Bontsa ki a **Hullámfeldolgozás** szakaszt.
18. A **Hullámfeldolgozási kötegcsoport** mezőben adjon meg, vagy válasszon ki egy értéket.
19. Állítsa be a **Hullámok kötegelt feldolgozása** lehetőséget **Igen** értékre.
20. A **Várakozás zárolásra (ms)** mezőben adjon meg egy számot. Adja meg azt az időt (ezredmásodpercben), amennyit egy felosztási lépésnek várakoznia kell egy olyan rendszererőforrásra, amelyet amely egy másik felosztási lépés zárolt. Ha ez az idő letelik, a hullám feldolgozása nem történik meg, és a rendszer egy hibaüzenetet jelenít meg.  
21. Kattintson a **Mentés** gombra.
22. Zárja be a lapot.
23. Ugorjon a **Navigációs panel > Modulok >Gyártásvezérlés > Beállítás > Gyártásvezérlési paraméterek** pontra.
24. A **Kiadás raktárba** mezőben válasszon ki egy lehetőséget.

Az értékesítési és a kanban rendelésekhez, a készletet a rendelés raktárból történő kiadása előtt le kell foglalni. Ellenkező esetben a cikkek vagy a felosztási sorok nem dolgozhatók fel a hullámban. A termelési rendelésekre vonatkozóan kiválaszthatja a Részleges foglalás engedélyezése lehetőséget. Ez például hasznos, ha a termelés megkezdéséhez szükséges anyagok rendelkezésére állnak, és addig pedig várni tud, amíg a további anyagok beérkeznek az eljárás végrehajtáshoz. Ha ezt a lehetőséget választja, akkor manuálisan meg kell ismételnie a raktárba kiadás folyamatát, amikor további anyagok rendelkezésre állnak.  
25. Zárja be a lapot.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]