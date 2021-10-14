---
title: A hullámfeldolgozási példa konfigurálása
description: Ez a témakör bemutat egy példát arról, hogyan állíthatja be azokat a feltételeket, amelyek meghatározzák, hogy milyen munka jön létre a raktár részére a hullám feldolgozásakor, és hogy egy hullám manuálisan vagy automatikusan lesz-e feldolgozva.
author: Mirzaab
ms.date: 03/17/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: WHSWaveTemplateTable, InventLocationIdLookup, WHSParameters, ProdParameters, whswavetablecreatenew, WHSWaveTable, WHSWaveAttributes, WHSKanbanWaveTable, WHSWaveTableListPage, WHSKanbanWaveTableListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 39c3fecf9250ee89c22003d5dff4ea662c3042e3
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/29/2021
ms.locfileid: "7572985"
---
# <a name="configure-wave-processing-example"></a>A hullámfeldolgozási példa konfigurálása

[!include [banner](../../includes/banner.md)]

Ez a témakör bemutat egy példát arról, hogyan állíthatja be azokat a feltételeket, amelyek meghatározzák, hogy milyen munka jön létre a raktár részére a hullám feldolgozásakor, és hogy egy hullám manuálisan vagy automatikusan lesz-e feldolgozva. A hullámsablonok és a lekérdezések beállításával határozza meg a feltételeket, amelyek megegyeznek az értékesítési rendelés, a termelési rendelés vagy a kanban rendelések kiadott soraival rendelkező hullámmal.

## <a name="enable-sample-data"></a>Mintaadatok engedélyezése

Ha ezt a forgatókönyvet az itt megadott mintaadatok és értékek alapján kívánja elvégezni, akkor egy olyan rendszert kell használnia amelynél a szokásos demóadatok telepítve vannak. Az **USMF** jogi személyt is ki kell választani a kezdés előtt.

## <a name="example-scenario-configure-wave-processing"></a>Példahelyzet: hullámfeldolgozás konfigurálása

Ez a példa végighalad a különböző beállításokon, amelyek a hullámok létrehozásának, feltöltésének, feldolgozásának és kiadásának módját befolyásolják.

1. Válassza a **Navigációs ablaktábla >Modulok > Raktárkezelés > Beállítás > Hullámok > Hullámsablonok** lehetőséget
1. Válassza az **Új** lehetőséget.
1. Adjon meg egy értéket a **Hullámsablon neve** mezőben. A hullámsablon beállításakor meghatározza azt a sorrendet, amelyben a sablonok megegyeznek az értékesítési rendeléseken, a termelési rendeléseken vagy kanbanokon kiadott sorral. Ha egy sor ki van adva a raktárba vagy a termeléshez, azt az első hullámsablont használja, amely megfelel a feltételnek. Javasoljuk, hogy a legspecifikusabb feltételekkel kialakított sablont helyezze a lista elejére. Minél szélesebbek a feltételek, annál valószínűbb, hogy egy sor teljesíti a feltételeket, és ez ahhoz vezethet, hogy a rendszer nem a megfelelő hullámhoz rendeli a sort.  
1. Adjon meg egy értéket a **Hullámsablon leírása** mezőben.
1. A **Hely** mezőben adjon meg vagy válasszon ki egy értéket. Az USMF használata esetén választhatja a 2-es helyet.  
1. A **Raktár** mezőben adjon meg vagy válasszon ki egy értéket. Az USMF használata esetén kiválaszthatja az 24-es raktárt.  
1. Állítsa az **Hullámlétrehozás automatizálása** mezőt **Igen** értékre. Válassza ezt a lehetőséget, hogy a rendszer automatikusan hozzon létre hullámot, amikor egy értékesítési rendelés, termelési rendelés vagy kanban kiadásra kerül a raktárba.  
1. Állítsa a **Hullám feldolgozása a raktárba történő kiadáskor** lehetőséget **Igen** értékre. Ha bejelöli ezt a lehetőséget, a rendszer automatikusan feldolgozza a hullámot és létrehozza a munkát, valahányszor egy sor kiadásra kerül a raktárba.  
1. Állítsa a **Hullámkiadás automatizálása mezőt** **Igen** értékre. Ezzel a beállítással automatikusan adhatja ki a hullámot. A rendszer létrehozza a kitárolási munkát, ami hozzáférhetővé vélik a mobileszközökön.  
1. Állítsa a **Hozzárendelés nyitott hullámokhoz** mezőt **Igen** értékre. A rendszer a hullámsablon lekérdezésszűrője alapján rendeli hozzá a sorokat a hullámokhoz.  
1. Állítsa a **Hullám feldolgozása automatikusan a küszöbértéknél** lehetőséget **Igen** értékre. Válassza ezt a lehetőséget, hogy a rendszer automatikusan feldolgozza a hullámot, amikor annak értékei elérik a súlyra, szállítmányra vagy sorokra vonatkozóan a **Hullám küszöbértékek** mezőcsoportban beállított küszöbértékeket. Ez a lehetőség csak akkor érhető el, ha a **Szállítás** beállítás van kiválasztva a **Hullámsablon típusa** mezőben.  
1. Állítsa a **Feltöltési munka kiadásának automatizálása** mezőt **Igen** értékre. Válassza ki ezt a lehetőséget, hogy a rendszer automatiksuan létrehozza és kiadja az igényalapú feltöltési munkát. Hozzá kell adnia az újratöltési hullámmódszert a hullámsablonhoz, majd létrehozni az újratöltési sablont a **Hullámigény** típussal.  
1. A hullámattribútumok hozzárendeléséhez használja az **Alapértelmezett értékek** mezőcsoportban található beállításokat. A hullámattribútumok szűrőként működnek azon típusú cikkek korlátozásához, amelyek a hullámokat használhatják. Például megadhatja a egy cikkcsoportot.  
1. Bontsa ki a **Módszerek** szakaszt, és állítsa be a hullámsablon által elvégzett műveleteket. Az alapvető hullámfeldolgozási módok lehetővé teszik a tevékenységek sorozatát, amelyen minden hullám áthalad, amikor feldolgozta a rendszer. Például rendelkezhet hullám feltöltési móddal. Egy módszer hozzáadásakor az automatikusan a megfelelő helyen jelenik meg a lépések sorrendjében. Ha a **Feltöltési munka kiadásának automatizálása** beállítást **Igen** értékre állította be, akkor itt kell hozzáadnia az újratöltési módszert.  
1. Válassza a **Mentés** lehetőséget.
1. Zárja be a lapot.
1. Ugorjon a **Raktárkezelés > Beállítás > Raktárkezelési paraméterek** elemre.
1. Bontsa ki a **Hullámfeldolgozás** szakaszt.
1. A **Hullámfeldolgozási kötegcsoport** mezőben adjon meg, vagy válasszon ki egy értéket.
1. Állítsa be a **Hullámok kötegelt feldolgozása** lehetőséget **Igen** értékre.
1. A **Várakozás zárolásra (ms)** mezőben adjon meg egy számot. Adja meg azt az időt (ezredmásodpercben), amennyit egy felosztási lépésnek várakoznia kell egy olyan rendszererőforrásra, amelyet amely egy másik felosztási lépés zárolt. Ha ez az idő letelik, a hullám feldolgozása nem történik meg, és a rendszer egy hibaüzenetet jelenít meg.  
1. Válassza a **Mentés** lehetőséget.
1. Zárja be a lapot.
1. Ugorjon a **Navigációs panel > Modulok >Gyártásvezérlés > Beállítás > Gyártásvezérlési paraméterek** pontra.
1. A **Kiadás raktárba** mezőben válasszon ki egy lehetőséget.

    Az értékesítési és a kanban rendelésekhez, a készletet a rendelés raktárból történő kiadása előtt le kell foglalni. Ellenkező esetben a cikkek vagy a felosztási sorok nem dolgozhatók fel a hullámban. A termelési rendelésekre vonatkozóan kiválaszthatja a **Részleges foglalás engedélyezése** lehetőséget. Ez például hasznos, ha a termelés megkezdéséhez szükséges anyagok rendelkezésére állnak, és addig pedig várni tud, amíg a további anyagok beérkeznek az eljárás végrehajtáshoz. Ha ezt a lehetőséget választja, akkor manuálisan meg kell ismételnie a raktárba kiadás folyamatát, amikor további anyagok rendelkezésre állnak.
1. Zárja be a lapot.

## <a name="additional-resources"></a>További erőforrások

- [Hullám létrehozása és feldolgozása](../wave-processing.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
