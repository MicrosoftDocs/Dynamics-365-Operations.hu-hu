---
title: Kézi készletmozgás halasztott feldolgozása
description: Ez a témakör azt mutatja be, hogyan használható a Microsoft kézi készletmozgásának halasztott feldolgozása Dynamics 365 Supply Chain Management.
author: Mirzaab
ms.date: 04/27/2021
ms.topic: article
ms.search.form: WHSWorkProcessingPolicy, WHSWorkDeferredPutProcessingTask
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-04-27
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 5e5d0a93a4c628d4867161d082b0f0e177ddb95c
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8863737"
---
# <a name="deferred-processing-of-manual-inventory-movement"></a>Kézi készletmozgás halasztott feldolgozása

[!include [banner](../includes/banner.md)]

Ez a témakör azt mutatja be, hogyan használható a Microsoft kézi készletmozgásának halasztott feldolgozása Dynamics 365 Supply Chain Management.

A halasztott feldolgozás esetében a raktári dolgozók továbbra is más munkát folytatnak, mialatt a betárolási művelet a háttérben lesz feldolgozva. A haslasztott feldolgozás akkor hasznos, ha a kiszolgálón előfordulhat a feldolgozási idő megnövekedése alkalomszerűen vagy nem tervezetten, és a megnövekedett feldolgozási idő hatással lehet a dolgozó termelékenységére. Ezzel a *Készletmozgás* munkatípus hozzá lett adva a funkció által támogatott munkatípusok halmazhoz.

A háttérbeli feldolgozást a [Raktári alkalmazás eseményeinek feldolgozása funkció](warehouse-app-events.md) használatával érheti el.

## <a name="turn-on-this-feature-for-your-system"></a>A funkció bekapcsolása a rendszerhez

A funkció elérhetővé tétele érdekében kapcsolja be a [funkciókezelés](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) modulban a következő funkciókat. A következő sorrendben kell bekapcsolni őket:

1. *Szervezeti szintű munkazárolás*<br>(Az Ellátásilánc-kezelés 10.0.21-es verziója esetén ez a funkció kötelező, ezért alapértelmezés szerint be van kapcsolva, és nem lehet újra kikapcsolni.)
1. *Raktári alkalmazás eseményeinek feldolgozása*<br>(Az Ellátásilánc-kezelés 10.0.25-ös verziója alapértelmezés szerint be van kapcsolva.)
1. *Halasztott Put műveletek*
1. *Manuális készletmozgási művelet halasztott feldolgozása*<br>(Az Ellátásilánc-kezelés 10.0.25-ös verziója esetén ez a funkció kötelező, ezért alapértelmezés szerint be van kapcsolva, és nem lehet újra kikapcsolni.)

## <a name="configure-the-work-processing-policies"></a>Konfigurálja a munkafeldolgozási irányelveket

A halasztott feldolgozás használatához a munkafeldolgozási irányelvet kell beállítania és használnia. A raktári munka halasztott feldolgozásához a [Raktári munka halasztott feldolgozása funkció](deferred-put.md) a következő munkatípusokat támogatja: *Értékesítési rendelés*, *Rendelési probléma átvitele* és *Feltöltés*. A *Kézi készletmozgás halasztott feldolgozása művelet* új munkatípust ad hozzá: *Készletmozgás*.

A munkafeldolgozási irányelv beállításához kövesse az alábbi lépéseket.

1. Ugorjon a **Raktárkezelés \> Beállítás \> Munka \> Munkafeldolgozási irányelvek** pontra.
1. Jelöljön ki vagy egy meglévő irányelvet a listapanelen, vagy hozzon létre egy új irányelvet az **Új** lehetőség Művelet panelen történő kiválasztásával. Minden irányelv fejléce a következő mezőket tartalmazza:

    - **Munkafolyamat irányelv neve** – A munkafolyamat irányelv neve.
    - **Leírás** – A munkafolyamat irányelv leírása.

1. A **Feldolgozási szabályok** gyorslapon állítsa be az irányelv által alkalmazandó szabályok gyűjteményét. Az eszköztár gombjaival lehet a szükséges szabályokat hozzáadni és eltávolítani. Állítsa be a következő mezőket minden egyes szabálynál:

    - **Munkarendelés típusa** – Válassza ki azt a munkatípust, amelyre az irányelv vonatkozik.
    - **Művelet** – Az irányelv feldolgozásához használt művelet kiválasztása. Ha a *Készletmozgás* beállítást választotta a **Munkarendelés típusa** mezőben, akkor ezt a mezőt nem kell beállítani, mivel a ki- és a betárazási műveletek feldolgozása is egyetlen eseményként történik.
    - **Munkafeldolgozási módszer** – A munkasor feldolgozására használt módszer kiválasztása. Ha az *Azonnali* lehetőséget választja, a működés hasonlít arra viselkedésre, amikor a sor feldolgozásához nem használnak munkafeldolgozási irányelvet. Ha a *Halasztott* lehetőséget választja, a rendszer a kötegkeretrendszert használó halasztott feldolgozást alkalmazza.
    - **Halasztott feldolgozási küszöb** – Ha a mezőt *0* (nulla) értékre állítja, akkor nincs küszöb. Ebben az esetben a *Halasztott* feldolgozási mód lesz használva, ha lehetséges. Ha a meghatározott küszöbérték kiszámítása a küszöbérték alatt van, az *Azonnali* módszer lesz használva. Máskülönben a rendszer a *Halasztott* módot használja, ha lehetséges. Az értékesítéssel és átadással kapcsolatos munkák esetében a küszöbérték számítása a munka során a hozzárendelt forrás terhelésisorok száma szerint történik. Feltöltési munka esetén a küszöb kiszámítása a munka során feltöltött munkasorok számának használatával történik. Ha például az eladásokhoz *5* értéket ad meg a küszöbértékhez, akkor biztosítja, hogy a kisebb munkák, amelyeknek kevesebb, mint öt kezdeti forrássora van, nem fogják használni a halasztott feldolgozást, de a nagyobb munkák igen. A küszöbérték csak akkor érvényes, ha a **Munka feldolgozási módszere** mező *Halasztott* értékre van állítva.
    - **Halasztott feldolgozási kötegcsoport** – Adja meg a feldolgozáshoz használt kötegcsoportot. Ha a *Készletmozgás* beállítást választotta a **Munkarendelés típusa** mezőben, akkor ezt a mezőt nem kell beállítania, mert a kötegcsoport ki van választva a **Raktári események feldolgozása** párbeszédpanelen.

## <a name="assign-the-work-creation-policy"></a>Rendeje hozzá a munkalétrehozási irányelvet

A munkalétrehozási irányelv hozzárendelésének részleteit lásd: [Raktári munka halasztott feldolgozása](deferred-put.md).

## <a name="set-up-a-batch-job-to-process-warehouse-app-events"></a>Kötegelt feladat létrehozása a raktári alkalmazás eseményeinek feldolgozásához

A *Kézi készletmozgás halasztott feldolgozása művelet* alkalmazásához állítson be egy ütemezett kötegelt feladatot.

1. Lépjen a **Raktárkezelés \> Ismétlődő feladatok \> Raktári alkalmazás eseményeinek feldolgozása** menüpontra.
1. A **Raktári alkalmazás eseményeinek feldolgozása** párbeszédablakban, a **Futtatás a háttérben** gyorslapon állítsa a **Kötegelt feldolgozás** beállítást *Igen* értékre.
1. Válassza az **Ismétlődés** lehetőséget, és állítson be egy olyan futtatás-ütemezést, amely megfelel a vállalata követelményeinek.
1. Kattintson az **OK** gombra a párbeszédpanelen.

## <a name="inquire-about-the-warehouse-app-events"></a>Raktári alkalmazással kapcsolatos események lekérdezése

A raktári alkalmazás által létrehozott esemény-várólistát és eseményüzeneteket a **Raktárkezelés \> Lekérdezések és jelentések \> Mobileszköznaplók \> Raktári alkalmazás eseményei** menüpontba lépve tekintheti meg.

A *Készletmozgás* esemény üzenetei *Várólista* állapotba kerülnek az első létrehozásukkor. Ez az állapot azt jelzi, hogy a **Raktári alkalmazás eseményeinek feldolgozása** kötegelt feladat felveszi és feldolgozza az eseményüzeneteket. Amikor az állapot *Befejeződött* értékre frissül, a program törli a várólistából az összes kapcsolódó eseményt.

Minden *Készletmozgás* esemény eseménytípusonként és raktáranként egy gyűjteményben van összegezve.

A kötegelt feladat a raktári alkalmazáseseményeket a **Raktári alkalmazásesemények feldolgozása** párbeszédpanelen beállított ismétlődésnek megfelelően fogja feldolgozni. Ezért amíg egy üzenet feldolgozása meg nem történik, az **Azonosító** mezőben meg lehet keresni a raktárazonosítót.

Az üzenet részletei a mozgatás részleteit tartalmazzák (például a „forráshely” és a „célhely” értéket).

A további tudnivalókat lásd: [Raktári alkalmazás eseményeinek feldolgozása](warehouse-app-events.md).

## <a name="configure-the-mobile-device-menu-to-skip-the-deferred-processing-policy"></a>Konfigurálja a mobileszköz menüjét a halasztott feldolgozási irányelv kihagyásához

A halasztott feldolgozási irányelv kihagyása érdekében a mobileszköz menü konfigurálásával kapcsolatos részleteket lásd: [Raktári munka halasztott feldolgozása](deferred-put.md).

## <a name="impact-on-closed-work-dates"></a>A lezárt munkaidőpontokra gyakorolt hatás

A lezárt munkadátumokra gyakorolt hatás további részleteit lásd: [Raktári munka halasztott feldolgozása](deferred-put.md).

## <a name="additional-resources"></a>További erőforrások

- [Raktári munka halasztott feldolgozása](deferred-put.md)
- [Raktározási alkalmazás eseményeinek feldolgozása](warehouse-app-events.md)
- [Mobileszközök beállítása raktári munkához](configure-mobile-devices-warehouse.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
