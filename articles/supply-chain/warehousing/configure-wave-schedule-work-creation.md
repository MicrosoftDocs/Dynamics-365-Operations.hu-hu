---
title: Munka létrehozásának ütemezése hullám közben
description: Ez a témakör a munka-létrehozási hullámfeldolgozás ütemezésének beállítását és használatát ismerteti.
author: Mirzaab
ms.date: 01/14/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSPostMethod, WHSWavePostMethodTaskConfig, WHSWaveTemplateTable, WHSParameters, WHSWaveTableListPage, WHSWorkTableListPage, WHSWorkTable, BatchJobEnhanced, WHSPlannedWorkOrder
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-01-14
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: c955e7275c0bdc12dc206dde1d7e390f16270148
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/04/2022
ms.locfileid: "8691131"
---
# <a name="schedule-work-creation-during-wave"></a>Munka létrehozásának ütemezése hullám közben

[!include [banner](../../includes/banner.md)]

A hullámfeldolgozási folyamat részeként használja a *Munka létrehozásának ütemezése* funkciót a hullámfeldolgozás teljesítményének növeléséhez azáltal, hogy a rendszer párhuzamos feldolgozással hozza létre a munkát.

Ha ez a funkció engedélyezve van, akkor automatikusan létrejön a tervezett munka, amelyet a rendszer végül feldolgoz a tényleges munka létrehozásához. Ha a hullámra vonatkozó rakománysorok száma eléri az előre meghatározott küszöbértéket, a rendszer gyorsabb munkát hoz létre párhuzamos, aszinkron feldolgozás alkalmazásával.

## <a name="turn-on-the-scheduled-work-creation-features-in-feature-management"></a>A funkciókezelés ütemezett munkalétrehozási funkcióinak bekapcsolása

Az ebben a témakörben leírt funkciók csak akkor használhatók, ha a rendszerben be van kapcsolva. Használja a [Funkciókezelés](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) munkaterületet a következő funkcióknak az alábbi sorrendben történő bekapcsolásához:

1. **Szervezeti szintű munkazárolás** – Az ütemezett munkalétrehozás kézi és automatikus konfigurálásához egyaránt szükséges. (Az Ellátásilánc-kezelés 10.0.21-es verziója esetén ez a funkció kötelező, ezért alapértelmezés szerint be van kapcsolva, és nem lehet újra kikapcsolni.)
1. **Munka létrehozásának ütemezése** – Az ütemezett munkalétrehozás kézi és automatikus konfigurálásához egyaránt szükséges.
1. **Szervezeti szintű „Munka létrehozásának ütemezése” módszer** – Az ütemezett munkalétrehozás automatikus konfigurálásához szükséges. Erre a funkcióra nincs szükség, ha csak manuális konfigurációt használ.

<a name="Auto-enable-schedule-work-creation"></a>

## <a name="automatically-configure-scheduled-work-creation"></a>Ütemezett munkalétrehozás automatikus konfigurálása

Ha engedélyezi az *Szervezeti szintű „Munka létrehozásának ütemezése” módszer* funkciót, a következők automatikusan történnek a rendszerben:

- A *Munka létrehozásának ütemezése* hullámmódszer (`WHSScheduleWorkCreationWaveStepMethod`) hozzáadásra kerül, és úgy van beállítva, hogy párhuzamosan fusson az összes jogi személy között.
- Az összes olyan jogi személy hullámsablonjai esetében, amelyek **Hullámsablon típusa** beállítása *Szállítás* és **Sablon állapota** beállítása *Érvényes* értékre van állítva, a *Munka létrehozása* módszert a *Munka létrehozásának ütemezése* módszer váltja fel. Nem módosítja azonban a hullámsablonokat olyan jogi személyektől, amelyeknél megengedett a *Munka létrehozása* módszer ismétlődése.
- A *Munka létrehozásának ütemezése* módszer feladatkonfigurációi minden olyan jogi személy raktáraihoz létrejönnek, amelynél engedélyezve van a **Raktárkezelési folyamatok alkalmazása**. Ez azt jelenti, hogy a *Munka létrehozásának ütemezése* módszer alapértelmezés szerint párhuzamosan fog futni. A meglévő raktárak, amelyekben a **Raktárkezelési folyamatok használata** beállítást *Nem* értékről *Igen* értékre módosítja, alapértelmezés szerint szintén párhuzamosan futtatják ezt a módszert.
- Minden jogi személy kötegben fogja feldolgozni a hullámokat, és a **Várakozás zárolásra (ms)** az alapértelmezett *60 000* ms értékre lesz beállítva, ha korábban *0* ms volt.
- Minden új hullámsablon, amit létrehozott, a *Munka létrehozásának ütemezése* módszerrel fog rendelkezni a *Munka létrehozása* módszer helyett.

A meglévő feladat- és hullámfeldolgozási konfigurációk az összes olyan jogi személy esetében is megtartásra kerülnek, amelyek már be vannak állítva a hullámok kötegelt feldolgozására, valamint az összes olyan raktárhoz, amelyek már be vannak állítva az *Munka létrehozásának ütemezése* módszer párhuzamos használatára.

Ha szükséges, manuálisan visszaállíthatja azokat a beállításokat, amelyek automatikusan megtörténtek, amikor engedélyezte a *Szervezeti szintű Munka létrehozásának ütemezése módszer* funkciót, a következő lépések alkalmazásával:

- A hullámsablonok esetében lépjen a **Raktárkezelés \> Beállítás \> Hullámok \> Hullámsablonok** pontra. Cserélje le az *Munka létrehozásának ütemezése* módszert a *Munka létrehozása* lehetőségre.
- A raktári paramétereknél kattintson a Raktárkezelés **beállítása \>\> – Raktárkezelési paraméterek gombra**. A **Hullámfeldolgozás** lapon alkalmazza az előnyben részesített értékeket a **Hullámok feldolgozása kötegben** és a **Várakozás zárolásra (ms)** mezőkben.
- A hullámmódszerek esetében lépjen a **Raktárkezelés \> Beállítás \> Hullámok \> Hullámfeldolgozás módszerei** lehetőségre. Válassza a `WHSScheduleWorkCreationWaveStepMethod` lehetőséget, és a Művelet panelen, kattintson a **Feladatkonfiguráció** elemre. Szükség szerint módosíthatja vagy törölheti a kötegelt tevékenységek számát és a hozzárendelt hullámcsoportot az egyes felsorolt raktárakhoz.

## <a name="manually-configure-scheduled-work-creation"></a>Ütemezett munkalétrehozás manuális konfigurálása

Ha nem engedélyezte a [*Szervezeti szintű „Munka létrehozásának ütemezése” módszer* funkciót](#Auto-enable-schedule-work-creation), akkor az ebben a szakaszban megadott eljárásokkal manuálisan konfigurálhatja az ütemezett munkalétrehozást.

### <a name="manually-enable-batch-processing-of-waves"></a>Hullámok kötegelt feldolgozásának manuális engedélyezése

Ahhoz, hogy egy párhuzamos aszinkron módszert kihasználva raktári munkát hozzon létre, a hullámfolyamatnak kötegben kell futnia. Ennek a beállításához:

1. Lépjen a **Raktárkezelés \> Beállítás \> Raktárkezelési paraméterek** részre.
1. Állítsa be az **Általános** lapon a **Hullámok kötegelt feldolgozása** lehetőséget *Igen* értékre. Ki is választhat egy külön **Hullámfeldolgozási kötegcsoportot**, hogy megakadályozza a kötegelt feladatok várólistájának feldolgozását a többi folyamattal egyidejűleg történő futását.
1. A **Zárolásra való várakozás (ms) idő** beállítása, amely akkor érvényes, ha a rendszer egyszerre több hullámot dolgoz fel. A legtöbb nagyobb hullámfolyamatnál a *60000* értéket javasoljuk.

### <a name="manually-enable-the-new-wave-step-method-for-existing-wave-templates"></a>Az új hullámlépés metódusának manuális engedélyezése a meglévő hullámsablonok számára

Indítsa el az új hullámlépés-metódus létrehozásával, majd az aszinkron feladatok párhuzamos feldolgozásának engedélyezésével.

1. Ugorjon a **Raktárkezelés \> Beállítás \> Hullámok \> Hullámfeldolgozás módszerei** lehetőségre.
1. Válassza **ki az Újragenerálás** *metódust, és jegyezze fel, hogy a WHSScheduleWorkCreationCreationCreationMethod* metódusok felkerültek a szállítási hullámsablonok során használható hullámfolyamati metódusok listájára.
1. Válassza ki a *WHSScheduleWorkCreationAluStepMethod* **Metódusnevű** rekordot, és válassza a **Feladatkonfigurációt**.
1. A Művelet panelen válassza az **Új** lehetőséget egy új dimenzió rácshoz való hozzáadásához, és használja a következő beállításokat:

    - **Raktár** – a munka-létrehozás feldolgozásának ütemezése során használt raktár kiválasztása.
    - **Kötegelt feladatok maximális száma** – adja meg a kötegelt feladatok maximális számát. A legtöbb esetben ennek az értéknek a 8–16 tartományban kell lennie, de javasoljuk, hogy az esetektől függően az optimális beállítással kísérletezzen.
    - **Hullámfeldolgozási kötegcsoport** – a kötegelt várólisták feldolgozásának optimalizálása érdekében válasszon ki egy külön hullámfeldolgozási kötegcsoportot.

Ezzel készen áll arra, hogy egy meglévő hullámsablont frissítsen (vagy újat hozzon létre), hogy a *Munka létrehozásának ütemezése* hullámfeldolgozási módszert használja.

1. Ugorjon a **Raktárkezelés \> Beállítás \> Hullámok \> Hullámsablonok** pontra.
1. A műveleti ablaktáblán válassza a **Szerkesztés** lehetőséget.
1. A lista ablaktáblában válassza ki a frissíteni kívánt hullámsablont (ha bemutatóadatokkal tesztel, akkor a *24 Alapértelmezett szállítás* használható).
1. Bontsa ki a **Metódusok** gyorslapot, és válassza ki azt a sort, amelynek a **Fennmaradó metódusok** rácsban a **Név** értéke *Munka létrehozásának ütemezése*.
1. Válassza a **Kijelölt metódusok** oszlopra mutató nyalat a kijelölt sornak az oszlopba való mozgatásához. (Egyszerre csak egy kiválasztott metódus lehet, amely vagy a `WHSScheduleWorkCreationWaveStepMethod` vagy a `createWork` lehetőséget használja, így a `createWork` **Metódus neve** elemmel létrehozott meglévő sor automatikusan átkerül a **Fennmaradó metódusok** rácsba.)

## <a name="set-wave-task-processing-threshold-data"></a>Hullámfeladat-feldolgozási küszöbérték adatainak beállítása

A rendszer akkor hozza létre az alapértelmezett hullámfeladat-feldolgozási küszöbérték-adatokat, amikor egy hullámfolyamat bármilyen feladatalapú feldolgozással fut. Az adatok segítségével lehet szabályozni, hogy mikor fusson aszinkron módon és feladatalapúan a hullámfeldolgozás, így lehetővé válik a feldolgozás és a munka létrehozása párhuzamosan.

Az alapértelmezett adatok kezdetben 15-ös küszöbértéket használnak a rakománysorok minimális számára (`MINIMUMWAVELOADLINES`). Ez azt jelenti, hogy amikor a rendszer egy hullámot több mint 15 rakománysorral dolgoz fel, aszinkron feladatfeldolgozást fog használni. A tesztkörnyezetben manuálisan is beszúrhatja, illetve frissítheti a `WHSWaveTaskProcessingThresholdParameters` táblázat adatait. Ha éles környezetben módosítania kell ezt a beállítást, forduljon a Microsoft ügyfélszolgálatához, és kérje a frissítés kérését.

## <a name="work-with-the-scheduled-work-creation"></a>Az ütemezett munkalétrehozás használata

Az ütemezett munkalétrehozással kapcsolatos további részleteket lásd a [Hullám létrehozása és feldolgozása](wave-processing.md) részt. 


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
