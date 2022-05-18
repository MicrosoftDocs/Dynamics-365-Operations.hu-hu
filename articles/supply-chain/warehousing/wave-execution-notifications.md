---
title: Hullámvégrehajtási értesítések
description: Ez a témakör bemutatja a hullámvégrehajtási értesítéseket, és elmagyarázza, hogy kell beállítani.
author: Mirzaab
ms.date: 04/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WhsWaveNotificationPolicy, WHSParameters, WHSWaveTemplateTable, BusinessEventsWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.0
ms.openlocfilehash: b6218610b673963f5d43e1b29c6fc356ea977935
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/03/2022
ms.locfileid: "8672514"
---
# <a name="wave-execution-notifications"></a>Hullámvégrehajtási értesítések

[!include [banner](../includes/banner.md)]

A *Hullámvégrehajtási értesítések* funkció üzleti eseményeket és a Műveletközpontot használja a hullámvégrehajtással kapcsolatos értesítések kézbesítéséhez. Lehetővé teszi az értesítéseket létrehozó események típusainak, az azokat létrehozó raktáraknak és az ezeket fogadó felhasználóknak a megadását.

A navigációs sáv jobb oldalán található **Üzenetek megjelenítése** gomb (harang szimbólum) jelzi, ha Műveleti központ üzenete elérhető az aktuális felhasználó számára. A felhasználó az **Üzenetek megjelenítése** gomb kiválasztásával megnyithatja a Műveleti központot, és áttekintheti az üzeneteket.

Üzleti események akkor történnek, amikor üzleti folyamatok futnak. Az üzleti folyamatok feladatokból állnak. Az üzleti folyamat során az abban részt vevő felhasználók üzleti műveleteket hajtanak végre a feladatok elvégzéséhez. Az üzleti események olyan mechanizmust biztosítanak, amely lehetővé teszi, hogy a külső rendszerek értesítést fogadjanak a Pénzügy és Üzemeltetési alkalmazásoktól. Ily módon a rendszerek üzleti műveleteket hajtanak végre az üzleti eseményekre reagálva. További tájékoztatás: [Üzleti események áttekintése](../../fin-ops-core/dev-itpro/business-events/home-page.md).

## <a name="turn-the-wave-execution-notifications-feature-on-or-off"></a>A Hullám-végrehajtási értesítések szolgáltatás be- és kikapcsolása

Az Ellátásilánc-kezelés 10.0.25-ös verziója szerint ez a funkció alapértelmezés szerint be van kapcsolva. A rendszergazdák úgy kapcsolhatják *be* és kapcsolják ki ezt a funkciót, hogy a szolgáltatáskezelési munkaterület Hullám-végrehajtási értesítési szolgáltatását [keresi](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

## <a name="scenario-send-wave-batch-execution-notifications-to-the-action-center"></a>Forgatókönyv: Hullám kötegelt végrehajtási értesítések küldése a Műveleti központba

Ez a forgatókönyv bemutatja a végponttól végpontig tartó folyamatot a hullám kötegelt végrehajtásával kapcsolatos hibákról szóló értesítések küldéséről egy megadott szerepkörnek a Műveleti központ használatával.

### <a name="make-demo-data-available"></a>A bemutató adatok elérhetővé tétele

A jelen forgatókönyv követéséhez a demó adatokat kell telepíteni, és az **USMF** demó jogi személyt kell használnia.

### <a name="make-sure-that-waves-are-run-in-batch-mode"></a>Győződjön meg arról, hogy a hullámok kötegelt módban futnak

1. Lépjen a **Raktárkezelés \> Beállítás \> Raktárkezelési paraméterek** részre.
1. A **Hullámfeldolgozás** gyorslapon állítsa a **Hullámok feldolgozása kötegben** beállítást *Igen* értékre.

> [!NOTE]
> Ha le szeretné tiltani a hullám kötegelt végrehajtásával kapcsolatos értesítéseket, állítsa a **Hullámfeldolgozás kötegelt értesítéseinek letiltása** beállítást *Igen* értékre.

### <a name="configure-a-wave-notification-policy"></a>Hullámértesítési házirend konfigurálása

A hullámértesítési házirendek határozzák meg az elküldött értesítések típusait és az értesítést kapó felhasználókat.

1. Ugorjon a **Raktárkezelés \> Beállítás \> Hullámok \> Hullámértesítési házirendek** lehetőségre.
1. Hozzon létre egy második rekordot, amelynek beállításai a következők:

    - **Hullámértesítési házirend:** *24BatchError*
    - **Leírás:** *Raktár 24 hullám kötegelt hibája*
    - **Értesítés küldése:** *Csak hiba*
    - **Címzett szerepkör:** *Rendszergazda*

        > [!NOTE]
        > Mivel ez a forgatókönyv bemutatóadatokat használ, a *Rendszergazda* szerepkör az egyszerűség kedvéért van kiválasztva. Ezért mivel rendszergazda felhasználóként van bejelentkezve, értesítéseket fog kapni. A gyakorlatban azonban általában ki kell választania egy konkrétabb szerepkört, amelynek értesítést küld a hullám kötegelt végrehajtási hibáiról, például a *Raktárkezelő* szerepkört.

1. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.

### <a name="configure-a-wave-template"></a>Hullámsablon konfigurálása

A hullámsablonokkal összekötheti a hullámmetódusok megadott példányait a hozzá tartozó hullámcímkesablonokkal.

1. Ugorjon a **Raktárkezelés \> Beállítás \> Hullámok \> Hullámsablonok** pontra.
1. A listapanelen állítsa be a **Hullámsablontípus** mezőt *Szállítás* értékre, majd válassza a *24 szállítás alapértelmezett* hullámsablont a 24. raktárhoz.
1. Az **általános** gyorslapon adja meg a **Hullámértesítési házirend** mezőt *24BatchError* értékre.

### <a name="configure-a-work-template"></a>Munkasablon konfigurálása

A munkasablonok a hullámvégrehajtás során a munka létrehozására használhatók. Ebben az esetben a hullámvégrehajtásnak hibát kell kiváltania. Ha a munkasablon-lekérdezést nem létező raktár használatára állítjuk be, biztosítjuk, hogy a hullámvégrehajtás sikertelen, és ezért értesítést küld.

1. Lépjen a **Raktárkezelés \> Beállítás \> Munka \> Munkasablonok** elemre.
1. A listapanelen állítsa be a **Munkasablontípus** mezőt *Értékesítési rendelések* értékre, majd válassza a *24 SO állapot* munkasablont a 24. raktárhoz.
1. A műveleti ablaktáblán válassza a **Lekérdezés szerkesztése** lehetőséget.
1. A lekérdezésszerkesztő párbeszédpanelben a **Tartomány** lapján szerkessze a következő sort (vagy adja hozzá, ha nem létezik):

    - **Tábla:** *Ideiglenes munkatranzakciók*
    - **Származtatott tábla:** *Ideiglenes munkatranzakciók*
    - **Mező:** *Raktár*
    - **Feltételek:** Módosítsa az értéket *24*-ről *Hiba* értékre.

1. Válassza az **OK** gombot, és erősítse meg a módosítást.

### <a name="create-a-sales-order-and-release-it-to-the-warehouse"></a>Értékesítési rendelés létrehozása és kiadása a raktárba

1. Ugorjon az **Értékesítés és marketing \> Értékesítési rendelés \> Összes értékesítési rendelés** pontra.
1. Hozzon létre egy olyan értékesítési rendelést, amelynek beállításai a következők:

    - **Vevőkód** *US-001*
    - **Raktár:** *24*

1. Az **Értékesítésirendelés-sorok** gyorslapon adjon hozzá egy értékesítésirendelés-sort, amely a következő beállításokat tartalmazza:

    - **Cikkszám:** *A0001*
    - **Mennyiség:** *10*

    > [!NOTE]
    > Ezek a cikkek és mennyiségek csak példák. A megadott raktárban elegendő készlettel kell rendelkezniük.

1. Miközben az **Értékesítésirendelés-sorok** gyorslapján az új sor továbbra is be van jelölve, akkor válassza az eszköztáron a **Készlet \> Foglalás** elemet.
1. A **Foglalás** lap műveleti ablaktáblán válassza ki az **Adag foglalása** elemet. Ezután zárja be az oldalt.
1. Válassza ki a művelet ablaktáblán a **Raktár** lapon a **Kiadás raktárba** lehetőséget.

### <a name="notifications-from-wave-batch-job-execution"></a>Értesítések hullám kötegelt feladatának végrehajtásáról

Az üzleti események beállításától függően végül értesítést kap a hullámvégrehajtási hibákról. A Műveletközpont üzenete a következő példához fog hasonlítani, és egy hivatkozást tartalmaz a sikertelen hullámra.

> **Hiba a hullám végrehajtása során**  
> Hiba történt a USMF-000000001 hullám végrehajtása során.  
> Utolsó üzenetek: Nem jött létre munka a USMF-000000001 hullámhoz.
>
> **ÁLLAPOT**  
> Aktív
>
> Nyitott hullámrészletek

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
