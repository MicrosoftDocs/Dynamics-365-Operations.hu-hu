---
title: Munka létrehozásának ütemezése hullám közben
description: Ez a témakör a munka-létrehozási hullámfeldolgozás ütemezésének beállítását és használatát ismerteti.
author: perlynne
manager: mirzaab
ms.date: 01/14/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSPostMethod, WHSWavePostMethodTaskConfig, WHSWaveTemplateTable, WHSParameters, WHSWaveTableListPage, WHSWorkTableListPage, WHSWorkTable, BatchJobEnhanced, WHSPlannedWorkOrder
audience: Application User
ms.reviewer: ''
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2021-01-14
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: ed8f43c7db139b7b16ac6901d5db56ba2f021690
ms.sourcegitcommit: b7a7a14f8650913f6797ae1c4a82ad8adfe415fd
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/28/2021
ms.locfileid: "5078268"
---
# <a name="schedule-work-creation-during-wave"></a>Munka létrehozásának ütemezése hullám közben

[!include [banner](../includes/banner.md)]

A hullámfeldolgozási folyamat részeként használja a *Munka létrehozásának ütemezése* funkciót a hullámfeldolgozás teljesítményének növeléséhez azáltal, hogy a rendszer párhuzamos feldolgozással hozza létre a munkát.

Ha ez a funkció engedélyezve van, akkor automatikusan létrejön a tervezett munka, amelyet a rendszer végül feldolgoz a tényleges munka létrehozásához. Ha a hullámra vonatkozó rakománysorok száma eléri az előre meghatározott küszöbértéket, a rendszer gyorsabb munkát hoz létre párhuzamos, aszinkron feldolgozás alkalmazásával.

## <a name="enable-the-schedule-work-creation-feature"></a>A Munka létrehozásának ütemezése funkció engedélyezése

### <a name="enable-the-feature-in-feature-management"></a>Szolgáltatások engedélyezése a szolgáltatások kezelésében

A *Munka létrehozásának* ütemezése funkciót a használata előtt be kell kapcsolnia saját rendszerében. A rendszergazdák használhatják a [Funkciókezelés](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) munkaterületet a funkció állapotának ellenőrzéséhez, és szükség esetén bekapcsolásához. A funkció a következő módon jelenik meg:

- **Modul:** *Raktárkezelés*
- **Funkció neve:** *Munka létrehozásának ütemezése*

> [!NOTE]
> A *Munka létrehozásának ütemezése* engedélyezése előtt engedélyezni kell a *Szervezeti szintű munkazárolás* funkciót.

### <a name="manually-enable-batch-processing-of-waves"></a>Hullámok kötegelt feldolgozásának manuális engedélyezése

Ahhoz, hogy egy párhuzamos aszinkron módszert kihasználva raktári munkát hozzon létre, a hullámfolyamatnak kötegben kell futnia. Ennek a beállításához:

1. Ugorjon a  **Raktárkezelés \> Beállítás \> Raktárkezelési paraméterek** elemre.

1. Állítsa be az **Általános** lapon a **Hullámok kötegelt feldolgozása** lehetőséget *Igen* értékre. Ki is választhat egy külön **Hullámfeldolgozási kötegcsoportot**, hogy megakadályozza a kötegelt feladatok várólistájának feldolgozását a többi folyamattal egyidejűleg történő futását.

1. A **Zárolásra való várakozás (ms) idő** beállítása, amely akkor érvényes, ha a rendszer egyszerre több hullámot dolgoz fel. A legtöbb nagyobb hullámfolyamatnál a *60000* értéket javasoljuk.

### <a name="manually-enable-the-new-wave-step-method-for-existing-wave-templates"></a>Az új hullámlépés metódusának manuális engedélyezése a meglévő hullámsablonok számára

Indítsa el az új hullámlépés-metódus létrehozásával, majd az aszinkron feladatok párhuzamos feldolgozásának engedélyezésével.

1. Ugorjon a  **Raktárkezelés \> Beállítás \> Hullámok \> Hullámfeldolgozás módszerei** lehetőségre.

1. Válassza ki az  **Újragenerálás** metódust, és jegyezze fel, hogy a *WHSScheduleWorkCreationWaveStepMethod* felkerült a szállítási hullámsablonok során használható hullámfolyamati metódusok listájára.

1. Válassza ki a *WHSScheduleWorkCreationAluStepMethod* **Metódusnevű** rekordot, és válassza a **Feladatkonfigurációt**.

1. A Művelet panelen válassza az **Új** lehetőséget egy új dimenzió rácshoz való hozzáadásához, és használja a következő beállításokat:

    - **Raktár** – a munka-létrehozás feldolgozásának ütemezése során használt raktár kiválasztása.

    - **Kötegelt feladatok maximális száma** – adja meg a kötegelt feladatok maximális számát. A legtöbb esetben ennek az értéknek a 8–16 tartományban kell lennie, de javasoljuk, hogy az esetektől függően az optimális beállítással kísérletezzen.

    - **Hullámfeldolgozási kötegcsoport** – a kötegelt várólisták feldolgozásának optimalizálása érdekében válasszon ki egy külön hullámfeldolgozási kötegcsoportot.

Ezzel készen áll arra, hogy egy meglévő hullámsablont frissítsen (vagy újat hozzon létre), hogy a *Munka létrehozásának ütemezése* hullámfeldolgozási módszert használja.

1. Ugorjon a  **Raktárkezelés \> Beállítás \> Hullámok \> Hullámsablonok** pontra.

1. A műveleti ablaktáblán válassza a **Szerkesztés** lehetőséget.

1. A lista ablaktáblában válassza ki a frissíteni kívánt hullámsablont (ha bemutatóadatokkal tesztel, akkor a *24 Alapértelmezett szállítás* használható).

1. Bontsa ki a **Metódusok** gyorslapot, és válassza ki azt a sort, amelynek a **Fennmaradó metódusok** rácsban a **Név** értéke *Munka létrehozásának ütemezése*.

1. Válassza a **Kijelölt metódusok** oszlopra mutató nyalat a kijelölt sornak az oszlopba való mozgatásához. (Egyszerre csak egy kiválasztott metódus lehet, amely vagy a *WHSScheduleWorkCreationAluStepMethod* vagy a *createWork* lehetőséget használja, így a *createWork* **metódusnévvel** létrehozott meglévő sor automatikusan átkerül a **Fennmaradó metódusok** rácsba.)

## <a name="set-wave-task-processing-threshold-data"></a>Hullámfeladat-feldolgozási küszöbérték adatainak beállítása

A rendszer akkor hozza létre az alapértelmezett hullámfeladat-feldolgozási küszöbérték-adatokat, amikor egy hullámfolyamat bármilyen feladatalapú feldolgozással fut. Az adatok segítségével lehet szabályozni, hogy mikor fusson aszinkron módon és feladatalapúan a hullámfeldolgozás, így lehetővé válik a feldolgozás és a munka létrehozása párhuzamosan.

Az alapértelmezett adatok kezdetben 15-ös küszöbértéket használnak a rakománysorok minimális számára (MINIMUMLOADLINES). Ez azt jelenti, hogy amikor a rendszer egy hullámot több mint 15 rakománysorral dolgoz fel, aszinkron feladatfeldolgozást fog használni. Ezt az adatot manuálisan is beszúrhatja a **WHSTopTaskProcessingThresholdParameters** táblába a tesztkörnyezetben, de ha éles környezetben módosítania kell ezt a beállítást, frissítés kéréséhez forduljon a Microsoft támogatási szolgálatához.

## <a name="work-with-the-feature"></a>A funkció használata

Ha a *Munka létrehozásának ütemezése* funkció engedélyezve van, akkor a hullámfeldolgozás tervezett munkát hoz létre, amelyet végül az új munka-létrehozási folyamat fog alkalmazni. A munka létrehozása során a rendszer letiltja a munkát az *egész szervezetre kiterjedő munkazárolási* funkcióval.

Az alábbi folyamatábra bemutatja, hogyan jön létre tervezett munka a hullámfeldolgozás során.

![Munka létrehozásának ütemezése](media/schedule-work-creation-process.png)

### <a name="planned-work"></a>Tervezett munka

A **Tervezett munka részletei** lap (**Raktárkezelés \> Munka \> Tervezett munka részletei**) a hullámfeldolgozás során kezdetben létrehozott tervezett munka adatait jeleníti meg. A következő **Folyamatállapot** értékek érhetők el:

- **Várakozás** – a tervezett munka várakozik a munka létrehozására.
- **Kész** – a tervezett munkát használták munka létrehozására.
- **Sikertelen** – a hullámfeldolgozás nem sikerült. A tervezett munka **Sikertelen** állapotban lehet tényleges munkával vagy anélkül. Ha a tényleges munkalétrehozási folyamat sikertelen, a tényleges munka *Visszavonva* állapotú marad.

### <a name="batch-job-for-the-work-creation-process"></a>Kötegelt feladat a munkalétrehozási folyamathoz

A hullámok feldolgozásához szükséges kötegelt feladatok megtekintéséhez jelölje ki a **Kötegelt feladatok** lehetőséget a **Minden hullám** oldal műveletablakában.

Innen megtekintheti a kötegelt feladatok minden egyes adatát a kötegeltfeladat-azonosítókhoz.
