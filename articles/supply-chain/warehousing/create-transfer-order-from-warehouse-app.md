---
title: Átmozgatási rendelések létrehozása a raktári alkalmazásból
description: Ez a témakör azt részletezi, hogyan lehet átmozgatási rendeléseket létrehozni és feldolgozni a Raktárkezelés mobilalkalmazásból
author: perlynne
ms.date: 09/02/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSMobileDeviceQueueEvent
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-09
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 986abfaef81474571de7db179253c4d76f65d4bec180fa9f355f3218ddbb96ba
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6746819"
---
# <a name="create-transfer-orders-from-the-warehouse-app"></a>Átmozgatási rendelések létrehozása a raktári alkalmazásból

[!include [banner](../includes/banner.md)]

Ez a funkció lehetővé teszi a raktári dolgozók számára, hogy közvetlenül a Raktárkezelés mobilalkalmazásból hozzanak létre és dolgozzanak fel átmozgatási rendeléseket. A dolgozók azzal kezdik, hogy kiválasztják a célraktárat, majd az alkalmazás segítségével egy vagy több azonosítótáblát beolvasnak, hogy azonosítótáblát adhassanak hozzá az átmozgatási rendeléshez. Ha a raktári dolgozó kiválasztja a **Rendelés teljesítése** elemet, akkor egy kötegelt feladat létrehozza a szükséges átmozgatási rendelést és a rendelési sorokat az adott azonosítótáblákhoz regisztrált aktuális készlet alapján.

## <a name="enable-the-create-transfer-orders-from-the-warehouse-app-feature"></a><a name="enable-create-transfer-order-from-warehouse-app"></a>Átmozgatási rendelések létrehozásának engedélyezése raktári alkalmazásból

A funkció használatba vétele előtt engedélyeznie kell a funkciót és annak előfeltételeit a rendszerben. A rendszergazdák használhatják a [funkciókezelési](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) oldalt a funkció állapotának ellenőrzéséhez, és szükség esetén engedélyezéséhez.

1. Először a [Raktáralkalmazás-események feldolgozása](warehouse-app-events.md) funkciót kell engedélyezni, amely a következőként szerepel a [funkciókezelés](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) listában:
    - **Modul:** Raktárkezelés
    - **Funkció neve** – Raktári alkalmazás eseményeinek feldolgozása
1. Ezután engedélyezze az *Átmozgatási rendelések létrehozása a raktári alkalmazásból* funkciót, amely a következőként szerepel a listában:
    - **Modul:** Raktárkezelés
    - **Funkció neve** – Átmozgatási rendelések létrehozása és feldolgozása raktári alkalmazásból
1. Ha szeretné automatizálni a kimenő szállítmányok feldolgozását, engedélyeznie kell a [Kimenő szállítmányok jóváhagyása kötegelt feladatokból](confirm-outbound-shipments-from-batch-jobs.md) funkciót. A funkció a következőként szerepel:
    - **Modul:** Raktárkezelés
    - **Funkció neve** – Kimenő szállítmányok jóváhagyása a kötegelt feladatokból

## <a name="set-up-a-mobile-device-menu-item-to-create-transfer-orders"></a><a name="setup-warehouse-app-menu"></a>Mobileszköz-menüelem beállítása átmozgatási rendelések létrehozásához

Az alábbiakban általános útmutatás található az átmozgatási rendelés létrehozásához szükséges mobileszköz-menüelemek beállításáról. Attól függően, hogy a vállalat igényei szerint milyen automatizálási szintet kell beállítani, amikor a felhasználók az üzemben átmozgatási rendeléseket hoznak létre, különféle konfigurációk lesznek engedélyezve. Az ebben a dokumentumban szereplő eset egy ilyen konfigurációt mutat be.

1. Lépjen a **Raktárkezelés \> Beállítás \> Mobileszköz \> Mobileszköz-menüelemek** részre.
1. Új menüelem hozzáadásához válassza az **Új** elemet. Ezt követően végezze el a következő beállításokat a kezdéshez:

    - **Menüelem neve** – Adja meg a menüelem nevét a Supply Chain Management számára.
    - **Cím** – Rendeljen hozzá egy menünevet, ahogy a Raktárkezelés mobilalkalmazásban dolgozók számára kell megjelennie.
    - **Mód** – Állítsa *Közvetett* értékre (ez a menüelem nem hoz létre munkát).
    - **Tevékenységkód** – Állítsa *Átmozgatási rendelés létrehozása az azonosítótáblákból* értékre, lehetővé téve a raktári dolgozók számára, hogy egy vagy több beolvasott azonosítótábla alapján hozzanak létre átmozgatási rendelést.

1. Az **Átmozgatási rendelés sorlétrehozási irányelv** beállításával irányíthatja, hogy az átmozgatási rendeléssorok milyen módon jöjjenek létre ezzel a menüelemmel. A sorok létrehozása és frissítése a beolvasott azonosítótáblához regisztrált aktuális készlet alapján történik. Válasszon a következő értékek közül:

    - **Nincs foglalás** – Az átmozgatási rendelés sorait nem foglalja le a rendszer.
    - **Sor foglalásával vezérelt azonosítótábla** – Az átmozgatási rendelés sorai le lesznek foglalva, és az „Azonosítótábla-vezérelt” stratégiabeállítást használja, amely tárolja a rendelési sorokhoz tartozó azonosítótábla-azonosítókat. Az átmozgatási rendelés sorainak munkalétrehozási folyamata részeként ezért használhatók a Megtalált azonosítótábla-azonosító értékek.

1. A **Kimenő szállítások irányelveinek** beállításával a kimenő átmozgatási rendelés szállítási folyamataihoz igény szerint több automatizmus is hozzáadható. Amikor egy dolgozó megnyomja a **Rendelés teljesítése** gombot, az alkalmazás létrehozza a *Rendelés teljesítése* raktári alkalmazási eseményt, amely az aktuális átmozgatási rendelés minden egyes sorához elmenti az itt kiválasztott értéket a **Kimenő szállítások irányelvei** mezőbe. Később, amikor egy kötegelt feladat feldolgozza az események várólistáját az átmozgatási rendelés létrehozásához, a kötegelt munka ki tudja olvasni az e mezőben tárolt értéket, és ezért el tudja rendelni, hogy az adott munka hogyan dolgozza fel az egyes sorokat. A következők közül választhat:

    - **Nincs** – Nincs automatikus feldolgozás.
    - **Raktárba kiadás** – Automatizálja a kiadást a raktári folyamat számára.
    - **Szállítás visszaigazolás** – Automatizálja a szállítás-visszaigazolás folyamatát.
    - **Kiadás és szállítás megerősítése** – Automatizálja a raktárba történő kiadás és a szállításmegerősítés folyamatát.

## <a name="add-the-mobile-device-menu-item-to-a-menu"></a>A mobileszköz menüelem hozzáadása menühöz

1. Lépjen a **Raktárkezelés \> Beállítás \> Mobileszköz \> Mobileszköz menü** elemre.
1. Válassza ki a **Szerkesztés** opciót.
1. Válasszon ki egy meglévő menüt az új menüpont kiválasztása után a **Választható menük és menüelemek** alatt. A menüelem hozzáadásához kattintson a jobbra mutató nyílra.

## <a name="create-a-transfer-order-based-on-license-plates"></a>Átmozgatási rendelés létrehozása azonosítótábla alapján

A Raktárkezelés mobilalkalmazás egyszerű eljárással hoz létre átmozgatási rendeléseket az azonosítótábla alapján. Ehhez a dolgozónak a következőket kell tennie a Raktárkezelés mobilalkalmazás segítségével:

1. Hozzon létre egy átmozgatási rendelést, és határozza meg a célraktárt.
1. Határozza meg az összes szállítandó azonosítótáblát.
1. Válassza a **Rendelés teljesítése** elemet.

>[!NOTE]
> Több dolgozó is hozzárendelheti az ugyanazon átmozgatási rendeléshez szánt azonosítótáblákat a **Átmozgatási rendelés kiválasztása** gombbal, hogy kiválasszon egy meglévő, feldolgozatlan átmozgatási rendelésszámot a raktári alkalmazás eseménysorából. Az átmozgatási rendelésszámok keresési módszeréről további tudnivalók találhatók a [A raktári alkalmazás eseményeinek lekérdezése](#inquire-the-warehouse-app-events) részben.

## <a name="example-scenario"></a>Példaforgatókönyv

Ez a példa áttekintést nyújt az átmozgatási rendelések létrehozásának és automatikusan feldolgozásának a folyamatáról a kiválasztott azonosítótáblákon nyilvántartott aktuális készlet alapján.

Ha ezt a folyamatot a javasolt értékek alkalmazásával kívánja megkezdeni, akkor bemutatóadatokat is tartalmazó rendszerben kell dolgoznia, és mielőtt elkezdi, ki kell választania a *USMF* jogi személyt.

Ez a folyamat feltételezi, hogy már engedélyezte az [Átmozgatási rendelések létrehozása és feldolgozása raktári alkalmazásból](#enable-create-transfer-order-from-warehouse-app) és a [Raktári alkalmazás eseményeinek feldolgozása](warehouse-app-events.md) funkciót.

Az átmozgatási rendelés létrehozásának mobileszköz-menüelemekben történő beállításán kívül be kell állítani és engedélyezni kell a további sablonokat, a helyutasításokat és a kötegelt feladatokat is.

### <a name="example-scenario-blueprint"></a>Példa

Ön kiskereskedő, és több azonosítótáblája van, amelyek több elemet tartalmaznak, és ezek mindegyike az egyik raktárának adott helyén található (*51-es raktár*). Szeretné engedélyezni azt a folyamatot, amely lehetővé teszi, hogy a dolgozók átmozgatási rendelést hozzanak létre egy másik raktárba (*61-es raktár*), a beolvasott azonosítótáblák egy csoportjára. Automatikusan kiszállítja illetve frissíti az átmozgatási rendelést, amint a megrendelés utolsó azonosítótábláját is felismerte a rendszer.

![Példa automatizált átmozgatási rendelés feldolgozására.](media/create-transfer-order-from-app-example.png "Példa automatizált átmozgatási rendelés feldolgozására")

### <a name="create-a-mobile-device-menu-item-for-creating-transfer-orders"></a>Mobileszköz-menüelem létrehozása átmozgatási rendelések létrehozásához

Ez a szakasz bemutatja, hogyan lehet új mobileszköz-menüelemet létrehozni az átmozgatási rendelések létrehozásához. Állítsa a **Mód** elemet *Közvetett* értékre, a **Tevékenységkód** pedig legyen *Átviteli rendelés létrehozása az azonosítótáblákból*.

1. Lépjen a **Raktárkezelés \> Beállítás \> Mobileszköz \> Mobileszköz-menüelemek** részre.
1. Válassza az **Új** lehetőséget.
1. A **Menüelem neve** mezőbe írja be a *Létrehozás IDE* nevet.
1. A **Cím** mezőbe írja be a *Létrehozás IDE* nevet.
1. A **Mód** mezőben válassza a *Közvetett* lehetőséget.
1. A **Tevékenységkód** alatt jelölje be az *Átmozgatási rendelés létrehozása azonosítótábla alapján* elemet.
1. A **Rendeléssor-létrehozási irányelv** alatt válassza a *Sor foglalásával vezérelt azonosítótábla* elemet.
1. A **Kimenő szállítások irányelvei** alatt válassza a *Kiadás és szállítás megerősítése* elemet.
1. Lépjen a **Raktárkezelés \> Beállítás \> Mobileszköz \> Mobileszköz menü** elemre.
1. Válassza ki a **Szerkesztés** opciót.
1. Válassza ki a meglévő **Készlet** menüt, majd válassza az új menüpontot a **Rendelkezésre álló menük és menüelemek** alatt. A menüelem a jobbra mutató nyíl kiválasztásával adható hozzá a **Készlethez**.

### <a name="set-up-work-templates-to-auto-process-and-break-work-by-located-license-plate"></a>Munkasablonok beállítása, a munka azonosítótábla alapján való automatikus feldolgozására és megszakítására

Ez a szakasz azt mutatja be, hogyan lehet engedélyezni egy munkasablont a hullám kiadásakor a sablon által létrehozott munka automatikus feldolgozásához.

1. Lépjen a **Raktárkezelés \> Beállítás \> Munka \> Munkasablonok** elemre.
1. A **Munkarendelés típusa** mezőben válassza ki az *Átmozgatás* elemet.
1. Válassza az **Új** lehetőséget egy új munkasablon létrehozásához.
1. A **Munkasablon** mezőbe írja be: *51 AT automatikus feldolgozása*.
1. A **Munkasablon leírása** mezőbe írja be: *51 AT automatikus feldolgozása*.
1. Jelölje be az **Automatikus feldolgozás** jelölőnégyzetet. Ezt az összes automatizálási lépés feldolgozása miatt kell bejelölni.
1. A bemutatóadatok között már létezik egy *51 Átmozgatás* munkasablon; a **Sorszám** mező felülírásával adjon az új munkasablonnak alacsonyabb sorszámot, mint a meglévő *51 Átmozgatás* sorszáma.
1. Az eszköztár **Mentés** gombjára kattintva engedélyezheti a **Munkasablon részletei** gyorslapot.
1. A **Munkasablon részletei** gyorslapon válassza az eszköztár **Új** elemét. Két sort kell hozzáadnia.
1. A **Munkatípus** mezőben válassza a *Kitárolás* lehetőséget.
1. A **Munkaosztály azonosítója** mezőben válassza a *TransfOut* elemet.
1. Válassza az **Új** elemet az eszköztárban a **Munkasablon részletei** alatt.
1. A **Munkatípus** mezőben válassza a *Betárolás* lehetőséget.
1. A **Munkaosztály azonosítója** mezőben válassza a *TransfOut* elemet.
1. A **Mentés** gombbal engedélyezheti az **Utasításkód** mezőt.
1. A **Munkatípus** *Eltárolás* sorában válassza az **Utasításkód** *Baydoor* elemét. Gondoskodjon róla, hogy az új munkasablon a legalacsonyabb **Sorszámot** kapja.
1. Válassza az eszköztár **Lekérdezés szerkesztése** elemét a lekérdezéstervező megnyitásához.
1. A **Tartomány** lapon válassza a **Hozzáadás** lehetőséget.
1. A hozzáadott sor **Mező** elemében válassza a *Raktárt*.
1. A **Feltételek** mezőben válassza az *51-et*.
1. Lépjen a **Rendezés** lapra.
1. Válassza a **Hozzáadást**, majd a **Mező** értékét állítsa *Megtalált azonosítótábla-azonosítóra*. Ennek a mezőnek a bejelölésével aktiválhatja az eszköztár **Munkafejléczónák** gombját.
1. Kattintson az **OK** majd az **Igen** gombra a csoportosítás visszaállításához és a visszalépéshez a **Munkasablonok** lapra.
1. Válassza a **Munkafejléczónák** elemet, és aktiválja a **Csoportosítás ezen mező szerint** funkciót a **Megtalált azonosítótábla-azonosítóhoz**, majd zárja be.

> [!NOTE]
> Nem minden beállítást lehet automatikusan feldolgozni; ilyen például a tényleges súly szerinti cikkek és a vegyes nyomon követési dimenziók használata.

### <a name="set-up-location-directives-for-the-license-plate-guided-strategy"></a>Helyutasítások beállítása az azonosítótábla-vezérelt stratégiához

Ez a szakasz bemutatja, hogyan kell beállítani egy helyutasításos kitárolási folyamatot az **Azonosítótábla-vezérelt** stratégia használatához.

1. Ugrás a **Raktárkezelés \> Beállítás \> Helyutasítások** elemre.
1. Válassza ki a **Szerkesztés** opciót.
1. A navigációs lista fejlécében válassza ki a **Munkarendelés típusa** alatt az *Átmozgatás* elemet.
1. A navigációs listán válassza ki az **51-esből Kitároláshoz** meglévő helyutasítást.
1. A **Sorok** gyorslapon jelölje be a **Felosztás engedélyezése** jelölőnégyzetet.
1. A **Helyutasítási műveletek** gyorslapon válassza az **Új** parancsot, ha egy új műveleti sort szeretne hozzáadni.
1. A **Név** mezőbe írja be: *AT-vezérelt*.
1. A **Stratégia** mezőben válassza az *Azonosítótábla-vezérelt* elemet. Ennek a műveletnek a legalacsonyabb sorszámúnak kell lennie.
1. Kattintson az eszköztár **Mentés** gombjára.
1. Válassza az eszköztár **Frissítés** ikonját.
1. A **Helyutasítási műveletek** gyorslapon válassza a *Kitároláshoz* sort.
1. A **Helyutasítási műveletek** eszköztárán válassza a **Mozgatás lefelé** elemet, hogy a sorszám nagyobb legyen, mint az éppen létrehozott *AT-vezérelt* művelet sorszáma.

> [!NOTE]
> Az azonosítótábla-vezérelt stratégia megpróbálja lefoglalni az átmozgatási rendelés soraihoz társított azonosítótáblát tartalmazó helyeket, és megpróbál kitárolási munkát létrehozni. Ha azonban ez nem lehetséges, és a kitárolási munkákat is létre szeretné hozni, akkor egy másik helyutasítási művelettel kapcsolatos stratégiához kell visszalépnie, és lehet, hogy a raktár egy másik területén is keresi kell a készletet, az üzleti folyamattól függően.

### <a name="set-up-a-batch-job-to-process-warehouse-app-events"></a>Kötegelt feladat létrehozása a raktári alkalmazás eseményeinek feldolgozásához

Ez a szakasz bemutatja, hogyan lehet beállítani az ütemezett kötegelt feladatokat a raktári alkalmazások eseményeinek feldolgozására.

1. Lépjen a **Raktárkezelés \> Ismétlődő feladatok \> Raktári alkalmazás eseményeinek feldolgozása** menüpontra.
2. A párbeszédpanelen engedélyezze a **Kötegelt feldolgozást** a **Futtatás a háttérben** szakaszban.
3. Válassza az **Ismétlődés** lehetőséget, majd állítsa be a kötegelt feladatot a feldolgozásra, a vállalat által igényelt intervallum szerint.
4. Az **OK** gombbal térjen vissza a fő párbeszédpanelhez.
5. A fő párbeszédpanel **OK** gombjára kattintva adja hozzá a feladatot a kötegelt feladatok várólistájához.

### <a name="set-up-a-batch-job-to-release-transfer-orders-automatically"></a>Átmozgatási rendeléseket automatikusan kiadó kötegelt feladat beállítása

Ez a szakasz bemutatja, hogyan lehet beállítani ütemezett kötegelt feladatokat a „kiadásra kész” jelű átmozgatási rendelések kiadására.

1. Lépjen a **Raktárkezelés \> Kiadás a raktárba \> Értékesítési rendelések automatikus kiadása** elemre.
1. A párbeszédpanelen nyissa meg a **Szerepeltetni kívánt rekordok** szakaszt.
1. Válassza a **Szűrőt** a **Szerepeltetni kívánt rekordok** szakaszban.
1. A **WHSTransferAutoRTWQuery** lekérdezési oldal **Tartomány** lapján a **Hozzáadás** elem kiválasztásával adjon hozzá egy új sort a lekérdezéshez.
1. Az új sor **Tábla** mezőjében válassza ki a legördülő menüt, és válassza ki az **Átmozgatási sor kiadása a raktárba** táblát.
1. A **Mező** legördülő menüben válassza a **Kimenő szállítások irányelvei** elemet.
1. A **Feltételek** mezőben válassza a **Kiadás és szállítás megerősítése** elemet.
1. Abban a sorban, ahol a **Mező** tartalma *Raktárból* a **Feltételek** mezőben, válassza ki az *51-et*.
1. Az **OK** gombbal térjen vissza a fő párbeszédpanelhez.
1. Nyissa meg a **Futtatás a háttérben** szakaszt a kötegelt feldolgozás beállításához.
1. Engedélyezze a **Kötegelt feldolgozást** a **Futtatás a háttérben** szakaszban.
1. Válassza az **Ismétlődés** lehetőséget, majd állítsa be a kötegelt feladatot a feldolgozásra, a vállalat által igényelt intervallum szerint.
1. Az **OK** gombbal térjen vissza a fő párbeszédpanelhez.
1. A fő párbeszédpanel **OK** gombjára kattintva adja hozzá a feladatot a kötegelt feladatok várólistájához.

### <a name="set-up-the-process-outbound-shipment-batch-job"></a>A „Kimenő szállítmányok feldolgozása” kötegelt feladat beállítása

Ez a szakasz azt mutatja be, hogyan lehet beállítani az ütemezett kötegelt feladatokat a „szállításra kész” státuszú átmozgatási rendelési sorokra vonatkozó, szállításra kész kimenő szállítmányok visszaigazolásának futtatásához.

1. Lépjen a **Raktárkezelés \> Ismétlődő feladatok \> Kimenő szállítmányok feldolgozása** menüpontra.
1. Bontsa ki a **Szerepeltetni kívánt rekordok** szakaszt.
1. Válassza ki a **Szűrő** elemet.
1. A **WHSLoadShipConfirm** lekérdezéstervezőben válassza az **Illesztések** lapot.
1. A tábla hierarchiájának kibontásával nyissa meg a **Rakományok** és a **Rakomány adatai** elemet.
1. Válassza ki a **Rakomány adatai** táblát.
1. Nyomja meg a **Tábla-összekapcsolás hozzáadása** gombot.
1. A táblák kapcsolatainak listájában a **Kapcsolat** oszlopban szűréssel vagy kereséssel találja meg az *Átmozgatási rendelés sorai (Hivatkozás)* elemet.
1. Emelje ki a listában a táblák kapcsolatát, majd nyomja meg a **Kiválasztás** gombot.
1. Válassza ki az **Átmozgatási rendelési sorok** táblát.
1. Nyomja meg a **Tábla-összekapcsolás hozzáadása** gombot.
1. A táblák kapcsolatainak listájában a **Kapcsolat** oszlopban szűréssel vagy kereséssel találja meg a *Raktári áttárolás további sorai (Rekordazonosító)* elemet.
1. Emelje ki a listában a táblák kapcsolatát, majd nyomja meg a **Kiválasztás** gombot.
1. Válassza ki a **Tartomány** lapot.
1. A **Tartomány** lekérdezési tábláiban három lekérdezésifeltétel-tartományt kell beállítania. Sor hozzáadásához válassza a **Hozzáadás** gombot.
1. Adjon hozzá tartományt a **Rakományok** táblához. Állítsa a **Mezőt** *Állapot betöltése* értékre, a **Feltételeket** pedig *Berakodva* értékre.
1. Adjon hozzá még egy tartományt a **Raktári áttárolás további sorai** táblához. Állítsa a **Mezőt** a *Kimenő szállítások irányelveire*, majd állítsa a **Feltételeket** *Kiadás és szállítás megerősítésére*.
1. Adjon hozzá egy másik tartományt a **Rakomány adatai** táblához. Állítsa a **Mezőt** *Hivatkozás* értékre, majd állítsa a **Feltételeket** *Átmozgatási rendelés szállítása* értékre.
1. Az **OK** gombbal térjen vissza a fő párbeszédpanelhez.
1. Bontsa ki a **Futtatás a háttérben** szakaszt.
1. Engedélyezze a **Kötegelt feldolgozást**.
1. Válassza az **Ismétlődés** lehetőséget, majd állítsa be a kötegelt feladatot a feldolgozásra, a vállalat által igényelt intervallum szerint.
1. Az **OK** gombbal térjen vissza a fő párbeszédpanelhez.
1. A fő párbeszédpanel **OK** gombjára kattintva adja hozzá a feladatot a kötegelt feladatok várólistájához.

> [!NOTE]
> További információért lásd: [Kimenő szállítmányok jóváhagyása kötegelt feladatokból](confirm-outbound-shipments-from-batch-jobs.md).

## <a name="processing-the-example-for-create-transfer-order-from-the-warehouse-app"></a>Az „Átmozgatási rendelések létrehozása a raktári alkalmazásból” példájának feldolgozása

### <a name="add-on-hand-on-a-license-plate"></a>Azonosítótáblán levő aktuális készlet hozzáadása

Ennek a helyzetnek a kiindulási pontjaként a tényleges rendelkezésre álló készletet tartalmazó azonosítótáblával kell rendelkeznie.

| Tétel | Raktár | Készlet állapota | Helyszín | Azonosítótábla | Mennyiség |
| --- | --- | --- | --- | --- | --- |
| A0001 | 51 | Rendelkezésre áll | LP-010 | LP10 | 1 |
| A0002 | 51 | Rendelkezésre áll | LP-010 | LP10 | 2 |

Adjon hozzá ténylegesen rendelkezésre álló mennyiségeket a következő értékek felhasználásával:

> [!NOTE]
> Létre kell hoznia az azonosítótáblát, és a vegyes cikkek szállítását lehetővé tevő helyeket, például az LP-010-et kell használnia.

### <a name="create-and-process-transfer-orders-from-the-warehouse-app"></a>Átmozgatási rendelések létrehozása és feldolgozása a raktári alkalmazásból

1. Nyissa meg az alkalmazást, és jelentkezzen be *51-es* felhasználóként. A jelenlegi felhasználói raktár az 51-es lesz.
1. Válassza ki a **Létrehozás IDE** menüelemet a beállítás során hozzáadott menühelyről.
1. Kezdje el az átmozgatási rendelés létrehozását, ehhez adja meg a célraktárat (célraktár) a **Raktár** mezőben, majd adja meg: *61*. Az új átmozgatási rendelés az 51-es aktuális raktárból (Kiinduló raktár) a *61-es* célraktárba kerül áttárolásra.
1. Válassza ki az **OK** lehetőséget.
1. Olvasson be egy azonosítótábla-azonosítót az **Azonosítótábla** mezőbe. Adja meg a korábban hozzáadott készlet-azonosítótáblát, *LP10*.
1. Válassza ki az **OK** lehetőséget.
1. Válassza a menü gombot, majd válassza ki a **Rendelés teljesítése** elemet a raktári alkalmazás átmozgatási rendelésének létrehozásához.

Az említett példában két **Raktári alkalmazási esemény** (*Átmozgatási rendelés létrehozása* és az *Átmozgatási rendelés teljesítése*) került alkalmazásra.

### <a name="inquire-the-warehouse-app-events"></a><a name="#inquire-the-warehouse-app-events"></a>Raktári alkalmazás eseményeinek lekérdezése

A Raktárkezelés mobilalkalmazás által létrehozott esemény-várólistát és eseményüzeneteket a **Raktárkezelés \> Lekérdezések és jelentések \> Mobileszköznaplók \> Raktári alkalmazás eseményei** menüpontba lépve tekintheti meg.

Az *Átmozgatási rendelés létrehozása* esemény üzenetei *Várakozás* állapotba kerülnek, ami azt jelenti, hogy a **Raktáralkalmazás-események feldolgozása** kötegelt feladata nem veszi és nem dolgozza fel az esemény üzeneteit. Amint az eseményüzenetek állapota *Várólistára* változik, a kötegelt feladat feldolgozza az eseményeket. Ez az *Átmozgatási rendelés teljesítése* létrehozásakor történik meg (amikor a dolgozó megnyomja a **Rendelés teljesítése** gombot a Raktárkezelés mobilalkalmazásban). Az *Átmozgatási rendelés létrehozása* során az üzenetek feldolgozása megtörtént, az állapot *Befejeződött* vagy *Sikertelen* értékre frissül. Amikor az *Átmozgatási rendelés teljesítése* állapot *Befejeződött* értékre frissül, a program törli a várólistából az összes kapcsolódó eseményt.

Mivel az átmozgatási rendelés adatainak létrehozásához szükséges **Raktári alkalmazási eseményeket** a kötegelt feladat nem dolgozza fel az előtt, hogy az üzenetek státusza *Várólistára* módosul, a kért átmozgatási rendelési számokat az **Azonosító** mezőben kell megkeresni. Az **Azonosító** mező a **Raktári alkalmazási esemény** lap fejlécében található.

A raktári esemény feldolgozásakor előfordulhat, hogy az átmozgatási rendelési sor létrehozása sikertelen. Ebben az esetben az eseményüzenet állapota *Sikertelen*; a **Köteg naplófájl** adataiból lehet megtudni ennek az okát, és hogy milyen lépéseket lehet tenni a problémák megoldása érdekében.

Általában a folyamat hiányzó beállításával kapcsolatos problémák fordulnak elő, például hiányzó tranzitraktár az *Átmozgatási rendelés létrehozása* eseményhez. Ilyen esetben adjon hozzá egy tranzitraktárt a szállítási raktárhoz, és változtassa meg az **Alaphelyzet** opcióval a raktáralkalmazás-esemény összes üzenetének állapotát *Sikertelenről* *Várólistára*, hogy a kötegelt feladat a beállítási adatok kijavítása után újra feldolgozza az eseményüzeneteket.

A termelési környezeteken belül a kivételek inkább a feldolgozással kapcsolatosak, például egy igényelt azonosítótábla esetében, amely a kötegelt feladat feldolgozási ideje alatt üres, és így nem jönnek létre átmozgatásirendelés-sorok. Vagy ezt a sikertelen eseményüzenetet távolítja el a **Törlés** opcióval, vagy hozzáadja a szükséges tényleges aktuális készletet az azonosítótáblán, és alkalmazza az **Alaphelyzet** opciót az összes kapcsolódó eseményüzenetre.

A további tudnivalókat lásd: [Raktári alkalmazás eseményeinek feldolgozása](warehouse-app-events.md).

### <a name="follow-up-on-the-example-scenario-processing"></a>A példa szerinti eset feldolgozásának követése

Ebben az esetben a következő történt:

1. Ön a Raktárkezelés mobilalkalmazás használatával kiválasztott egy menüelemet, amely az **Átmozgatási rendelés létrehozása azonosítótábla alapján** tevékenységkódot használja.
1. Az alkalmazás kérte, hogy az átmozgatási rendeléshez válassza ki a célraktárt. A forrás raktár mindig az, amelynél Ön aktuálisan dolgozóként van bejelentkezve.
1. A célraktár kiválasztásakor a rendszer lefoglalt egy azonosító számot a közelgő átmozgatási rendelés számára (a rendszerben definiált átmozgatási rendelésszámsorrend alapján), de még nem hozta létre az átmozgatási rendelést.
1. Amikor Ön beolvasta az *LP10* azonosítótáblát, amely az új raktárba áttárolandó aktuális készletet tartalmazza, egy **Raktári alkalmazásesemény** lett hozzáadva a későbbiekben feldolgozandó események várólistájához. A raktári esemény tartalmazott beolvasással kapcsolatos adatokat, például a tervezett átmozgatási rendelésszámot.
1. A Raktárkezelés mobilalkalmazásban, ha a **Rendelés teljesítése** gomb be van jelölve, létrejön egy új raktári alkalmazási esemény, az **Átmozgatási rendelés teljesítése**, valamint a kapcsolódó meglévő esemény, az **Átmozgatási rendelés létrehozása** állapota módosul **Várólistára**.
1. A háttérben a **Raktáralkalmazás-események feldolgozásának kötegelt feladata** felvette a **Várólista** eseményt, és összegyűjtötte a beolvasott azonosítótáblával kapcsolatos aktuális készletet. Az aktuális készlet alapján létrejön a tényleges átmozgatási rendelés rekordja és a kapcsolódó sorok. A feladat az átmozgatási rendelés **Kimenő szállítások irányelvei** mezőjét is kitöltötte a *Kiadás és szállítás megerősítéséhez* beállított értékkel, és összekapcsolta az azonosítótáblát az **Azonosítótábla-vezérelt** stratégia soraival.
1. Az átmozgatási rendeléssor **Kimenő szállítások irányelvei** mezőjének értéke alapján az **Átmozgatási rendelések automatikus kiadása kötegelt feladat** lekérdezésének eredménye az, hogy az átmozgatási rendelés kiadásra kerül a szállítási raktárba. Az alkalmazott **Hullámsablon**, **Munkasablon** és a **Helyutasítások** beállítása miatt a munka automatikus folyamatainak eredményeképpen a **Rakomány állapota** *Berakodva* értékre frissült.
1. A rendszer végrehajtja a rakomány **Kimenő szállítmányok feldolgozása kötegelt feladatát**, és ekkor megtörténik az átmozgatási rendelés kiszállítása és az előzetes kiszállítási értesítés (ASN) létrehozása.
1. Ezeknek az eseményeknek az ütemezése a létrehozott kötegelt feladatok **Ismétlődési** beállításától függ.

## <a name="frequently-asked-questions"></a>Gyakori kérdések

### <a name="mobile-device-menu-item-setup"></a>Mobileszköz-menüelem beállítása

#### <a name="why-cant-i-see-create-transfer-order-from-license-plate-in-the-menu-item-work-activity-drop-down-list"></a>Miért nem látom az „Átmozgatási rendelés létrehozása azonosítótábla alapján” elemet a menüelem-munkatevékenység legördülő listájában?

Engedélyezni kell az *Átmozgatási rendelések létrehozása és feldolgozása raktári alkalmazásból* elemet. További információért lásd: [Átmozgatási rendelések létrehozásának engedélyezése raktári alkalmazásból](#enable-create-transfer-order-from-warehouse-app).

### <a name="warehouse-management-mobile-app-processes"></a>A Raktárkezelés mobilalkalmazás folyamatai

#### <a name="why-cant-i-see-the-menu-button-complete-order"></a>Miért nem látom a „Rendelés teljesítése” menügombot?

Az átmozgatási rendeléshez legalább egy azonosítótáblát hozzá kell rendelni.

#### <a name="can-several-warehouse-management-mobile-app-users-add-license-plates-to-the-same-transfer-order-at-the-same-time"></a>Ugyanazon átmozgatási rendeléshez egyszerre a Raktárkezelés mobilalkalmazás több felhasználója is hozzáadhat azonosítótáblát?

Igen, több raktári dolgozó is beolvashat azonosítótáblát ugyanazon átmozgatási rendelésbe.

#### <a name="can-the-same-license-plate-be-added-to-different-transfer-orders"></a>Hozzáadható ugyanazon azonosítótábla különböző átmozgatási rendelésekhez?

Nem, egy azonosítótábla csak egy átmozgatási rendeléshez adható hozzá.

#### <a name="after-having-selected-the-complete-order-button-can-i-then-add-more-license-plates-for-that-transfer-order"></a>A „Rendelés teljesítése” gomb kiválasztása után hozzáadhatok-e még azonosítótáblát az átmozgatási rendeléshez?

Nem, több azonosítótábla már nem adható hozzá olyan átmozgatási rendeléshez, amely **Átmozgatási rendelés teljesítése** raktári alkalmazási eseménnyel rendelkezik.

#### <a name="how-can-i-find-existing-transfer-orders-to-be-used-via-the-select-transfer-order-button-in-the-warehouse-management-mobile-app-if-the-order-has-not-yet-been-created-in-the-backend-system"></a>Hogyan lehet megtalálni a Raktárkezelés mobilalkalmazásban az „Átmozgatási rendelés kiválasztása” gombbal használható meglévő átmozgatási rendeléseket, ha a rendelés még nincs létrehozva a háttérrendszerben?

Jelenleg nem lehet átmozgatási rendeléseket keresni az alkalmazásban, de az átmozgatási rendelésszámok a **Raktári alkalmazás eseményei** lapon megtalálhatók. A további tudnivalókat lásd: [Raktári alkalmazás eseményeinek lekérdezése](#inquire-the-warehouse-app-events).

#### <a name="can-i-manually-select-the-transfer-order-number-to-be-used-from-the-warehouse-management-mobile-app"></a>Kiválaszthatom-e manuálisan a használandó átmozgatási rendelésszámot a Raktárkezelés mobilalkalmazásból?

Csak a számsorozatokon keresztül automatikusan létrehozott átmozgatási rendelésszámokat támogatja a rendszer.

### <a name="background-processing"></a>Feldolgozás a háttérben

#### <a name="how-should-i-clean-up-records-in-my-warehouse-app-events-queue-message-tables"></a>Hogyan lehet törölni rekordokat a raktári alkalmazási események várólistájának üzenettábláiban?

Ezt a **Raktári alkalmazási események** oldalon tekintheti meg és tarthatja karban. A további tudnivalókat lásd: [Raktári alkalmazás eseményeinek lekérdezése](#inquire-the-warehouse-app-events).

#### <a name="why-is-the-transfer-order-receipt-date-not-updated-according-to-my-delivery-date-control-setup"></a>Miért nem módosult az átmozgatási rendelés „Kézhezvételi dátuma” a „Szállítási dátum ellenőrzése” beállításomnak megfelelően?

Az átmozgatási rendelések létrehozása a **Szállítási dátum ellenőrzése** funkció nélkül történik.

#### <a name="can-i-use-a-license-plate-having-physical-negative-inventory-on-hand"></a>Használhatok negatív tényleges aktuális készlettel rendelkező azonosítótáblát?

A funkció csak pozitív fizikai aktuális készletmennyiségeket támogat az azonosítótábla szintjén, de negatív fizikai aktuális készletmennyiségek is lehetnek a magasabb raktárban és készletállapot-szinteken, amikor az áthelyezési rendelésekhez társítják az azonosítótáblákat.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]