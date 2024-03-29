---
title: TDS-csoport, PAN és TAN-információk beállítása a vevők és szállítók számára
description: Ez a cikk bemutatja a forrásnál levont adó (TDS) csoport, a állandó számlaszám (PAN) és a szállítók adószámlaszámának (TAN) beállítását.
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: 1a29f59e380360b6f828dcddbe84cad229b42d17
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8859766"
---
# <a name="tds-group-pan-and-tan-information-setup-for-vendors-and-customers"></a>TDS-csoport, PAN és TAN-információk beállítása a vevők és szállítók számára

[!include [banner](../includes/banner.md)]

Ez a cikk bemutatja a forrásnál levont adó (TDS) csoport, a állandó számlaszám (PAN) és a szállítók adószámlaszámának (TAN) beállítását.

1. Ugrás a **Kötelezettségek \> Szállítók: \> Minden szállító** vagy **Kinnlevőségek \> Vevők \> Minden vevő** lehetőségre.

    [![Minden szállító lap.](./media/apac-ind-TDS-55.png)](./media/apac-ind-TDS-55.png)

2. A Műveletablakban válassza az **Új** lehetőséget a szállító vagy vevő létrehozásához, és adja meg a szükséges adatokat. Másik lehetőségként válasszon ki egy meglévő szállítót vagy vevőt.
3. A **Számla és szállítás** gyorslapon az **Adóelőleg** szakaszban állítsa be az **Adóelőleg számítása** lehetőséget **Igen** értékre adóelőleg, TDS, forrásnál beszedett adó (TCS) számításához a szállítóhoz vagy ügyfélhez.
4. A beszerzési számla TDS-ének számítása a szállítóhoz vagy vevőhöz megadott alapértelmezett TDS-csoport alapján történik. A **TDS-csoport** mezőben válassza ki az alapértelmezett TDS-csoportot.

    > [!NOTE]
    > Az **Adóelőleg-csoport** mező és a **TCS-csoport** mező nem lesz elérhető, ha a **TDS-csoport** mezőben egy TDS-csoportot választ.

5. Válassza ki a szállító vagy vevő állandó számlaszámának állapotát az **Adóinformáció** gyorslapon a **PAN-információk** szakaszban, az **Állapot** mezőben:

    - **Nem érhető el** – A szállítónak vagy a vevőnek nincs PAN-ja.
    - **Beérkezett** – A szállítónak vagy a vevőnek van PAN-ja.
    - **Jelentkezett** – a szállító vagy a vevő PAN-ért jelentkezett.
    - **Érvénytelen** – A szállítónak vagy a vevőnek van PAN-ja, de nem érvényes.

6. Ha a **Beérkezett** beállítást választotta az **Állapot** mezőben annak jelzésére, hogy a szállítónak vagy a vevőnek van PAN-ja, írja be a PAN számot a **Szám** mezőbe. A PAN-nak öt betűből, majd négy numerikus karakterből, majd egy betűből kell állnia. Egy példa: **ABCDE1260A**.
7. Ha a **Jelentkezett** beállítást választotta az **Állapot** mezőben annak jelzésére, hogy a szállító vagy a vevő igényelt PAN-t, írja be a hivatkozási számot a **Referenciaszám** mezőbe.
8. Az **Értékelő** jellege mezőben válassza ki az értékelő kategória jellegét a szállítóhoz vagy ügyfélhez.

    - Cég
    - HUF
    - Megerősítve
    - Magánszemély
    - AOP
    - BOI
    - Önkormányzat
    - Egyebek

    [![Adóinformációk gyorslap.](./media/apac-ind-TDS-56.png)](./media/apac-ind-TDS-56.png)

9. Ezután a Műveleti panelen a **Szállító** lap **Regisztráció** csoportjában válassza a **Regisztrációs azonosítók** lehetőséget a **Címek kezelése** lap megnyitásához.
10. A **Címek kezelése** lapon, az **Adóinformációk** gyorslapon válassza a **Hozzáadás** vagy a **Szerkesztés** lehetőséget, hogy megnyíljon az **Adóinformációk kezelése** lap, ahol karbantarthatja az adóregisztrációs bejegyzést.
11. Az **Adóinformációk kezelése** lapon, az **Adóelőleg** gyorslap **Adószámla száma (TAN)** mezőjében adja meg a TAN-t. A TAN-nak négy betűből, majd öt numerikus karakterből, majd egy betűből kell állnia. Egy példa: **AFGH54821T**.
12. Zárja be a lapot.
