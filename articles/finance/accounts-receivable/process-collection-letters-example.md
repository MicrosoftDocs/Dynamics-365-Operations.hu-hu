---
title: Fizetési felszólítások feldolgozása (példa)
description: Ez a témakör egy példán keresztül bemutatja a fizetési felszólítások létrehozásának, nyomtatásának és feladásának folyamatát.
author: JodiChristiansen
ms.date: 02/03/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CustPosting, CustCollectionLetterNote
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2021-02-03
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: fdde6ebaebf37a883aef0dcc3ea12909c3d43532d604ff78d708d737b26bc57e
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6721851"
---
# <a name="process-collection-letters-example"></a>Fizetési felszólítások feldolgozása (példa)

[!include [banner](../../includes/banner.md)]

Ez a témakör egy példán keresztül bemutatja a fizetési felszólítások létrehozásának, nyomtatásának és feladásának folyamatát. A példa a Követelések és beszedések rész **Fizetések és jóváírások figyelmen kívül hagyása a fizetési felszólítás kódjának kiszámítása során** lehetőségén alapul. Az USMF bemutatóvállalat és egy új vevő, az US-045 adatait használja.

A kezdéshez lépjen a **Kinnlevőségek \> Vevők \> Összes vevő** lehetőségre, válassza az **Új** lehetőséget, majd adja meg az US-045 vevő létrehozásához szükséges adatokat.

Amikor befejezte, kövesse az alábbi lépéseket.

1. Lépjen a **Követelések és beszedések \> Fizetési felszólítás \> Fizetésifelszólítás-sorozat beállítása** lehetőségre, és állítsa be a fizetésifelszólítás-sorozatot a vevői feladási profilhoz rendelt alábbi táblának megfelelően.

|     Fizetési felszólítás kódja      |     Leírás                           |     Pénznem      |     Fő számla        |     Illeték pénznemben     |     Minimális késedelmes        |     Nap zárolás      |
|---------------------------------  |---------------------------------------    |-----------------  |-----------------------    |-------------------------- |-----------------------    |---------------------  |
|     1. fizetési felszólítás         |     Második értesítés díjjal        |     USD           |                           |     0,00                  |     0,00                  |     2                 |
|     2. fizetési felszólítás         |     Második értesítés díjjal        |     USC           |     403150                |     20.00                 |     10,00                 |     3                 |
|     Beszedés                    |     Utolsó értesítés díjjal         |     USD           |     403150                |     50.00                 |     100.00                |     15                |

A következő ábra a tábla azon adatait mutatja be, amelyek a **Fizetési felszólítás** oldalon jelennek meg. 

[![Fizetésifelszólítás-sorozat beállítása.](./media/Ignore-payments-creditmemos-1.PNG)](./media/Ignore-payments-creditmemos-1.PNG)

 Most be kell állítania a példához szükséges két paramétert.

2. Lépjen a **Követelések és beszedések \> Beállítás \> Kinnlevőségek paraméterei** lehetőségre, és kövesse az alábbi lépéseket:

    1. A **Követelések és beszedések** lapon állítsa a **Fizetések és jóváírások figyelmen kívül hagyása a fizetési felszólítás kódjának kiszámítása során** lehetőséget **Igen** értékre.
    2. Győződjön meg arról, hogy a **Fizetési felszólítás létrehozása a következő szerint:** mező értéke a **Vevő** legyen.

    [![Kinnlevőségek paramétereinek beállítása a beszedésekhez.](./media/Ignore-payments-creditmemos-2.PNG)](./media/Ignore-payments-creditmemos-2.PNG)

3. Lépjen a **Kinnlevőségek \> Számlák \> Kizárólag szabadszöveges számlák** lehetőségre, válassza az **Új** lehetőséget, majd kövesse a következő lépéseket:

    1. A **Vevői számla** mezőben válassza a következőt: **US-045**.
    2. A **Számla dátuma** mezőbe írja be a következő értéket: **1/15/2021**.
    3. A **Határidő** mezőbe írja be a következő értéket: **1/16/2021**.
    4. A **Számlasorok** gyorslapon a **Fő számla** mezőbe írja be a következőt: **401100**.
    5. Írjon be **500.00** értéket az **Egységár** mezőbe.
    6. Válassza a **Feladás** parancsot.

    Most két jóváírást kell megadnia a vevő számára.

4. Válassza az **Új** lehetőséget, majd kövesse az alábbi lépéseket:

    1. A **Vevői számla** mezőben válassza a következőt: **US-045**.
    2. A **Számla dátuma** mezőbe írja be a következő értéket: **1/15/2021**.
    3. A **Határidő** mezőbe írja be a következő értéket: **1/16/2021**.
    4. A **Számlasorok** gyorslapon a **Fő számla** mezőbe írja be a következőt: **401100**.
    5. Az **Egységár** mezőbe írja be a következő értéket: **-100,00**.
    6. Válassza a **Feladás** parancsot.

5. Ismételje meg a 4. lépést, de írja a **-200,00** értéket az **Egységár** mezőbe.
6. Menjen a **Kinnlevőségek \> Vevők \> Összes vevő** lehetőségre, és válassza ki az **US-045** vevőt. Ezután a műveleti ablaktáblán válassza a **Tranzakciók \> Tranzakciók** lehetőséget a korábban feladott vevői tranzakciók ellenőrzéséhez.

    [![Feladott vevői tranzakciók ellenőrzése.](./media/Ignore-payments-creditmemos-3.PNG)](./media/Ignore-payments-creditmemos-3.PNG)

    Most fizetési felszólításokat kell létrehoznia az US-045 vevőhöz.

7. Lépjen a **Követelések és beszedések \> Fizetési felszólítás \> Fizetési felszólítások létrehozása** részre, és kövesse az alábbi lépéseket:

    1. A **Számla** és a **Jóváírás** beállítása legyen **Igen**.

        Alapértelmezés szerint a **Fizetési felszólítás** mező beállítása **Felszólítás vevőnként**.

    2. A **Fizetési felszólítás dátuma** mezőbe írja be a következő értéket: **1/19/2021**.
    3. A **Szerepeltetni kívánt rekordok** gyorslapon válassza a **Szűrés** lehetőséget, majd a **Vevői számla** mezőben adja hozzá az **US-045** vevőt.
    4. Válassza ki az **OK** lehetőséget.
    5. Kattintson az **OK** gombra a fizetési felszólítások létrehozásához.

8. Lépjen a **Követelések és beszedések \> Fizetési felszólítás \> Fizetési felszólítások áttekintése és feldolgozása** részre, és kövesse az alábbi lépéseket:

    1. Figyelje meg, hogy a fizetési felszólítás kódja a fejlécben és a tranzakciósorban is **1. fizetési felszólítás**, mivel ez a fizetési felszólítás a sorozat első fizetési felszólítása. (A tranzakciósorok megtekintéséhez lehet, hogy ki kell választania a **Tranzakciók** gyorslapot.)

   [![Annak ellenőrzése, hogy ugyanaz a fizetésifelszólítás-kód jelenik-e meg a fejlécben és a sorokban.](./media/Ignore-payments-creditmemos-4.PNG)](./media/Ignore-payments-creditmemos-4.PNG)

    2. A műveleti ablaktáblán válassza ki a **Feladás** elemet.
    3. A **Feladás dátuma** mezőbe írja be a következő értéket: **1/19/2021**.

    Most ismét létre kell hoznia a fizetési felszólításokat az US-045 vevőhöz.

9. Lépjen a **Követelések és beszedések \> Fizetési felszólítás \> Fizetési felszólítások létrehozása** részre, és kövesse az alábbi lépéseket:

    1. A **Számla** és a **Jóváírás** beállítása legyen **Igen**.

        Alapértelmezés szerint a **Fizetési felszólítás** mező beállítása **Felszólítás vevőnként**.

    2. A **Fizetési felszólítás dátuma** mezőbe írja be a következő értéket: **1/23/2021**.
    3. A **Szerepeltetni kívánt rekordok** gyorslapon válassza a **Szűrés** lehetőséget, majd a **Vevői számla** mezőben adja hozzá az **US-045** vevőt.
    4. Válassza ki az **OK** lehetőséget.
    5. Kattintson az **OK** gombra a fizetési felszólítások létrehozásához.

10. Lépjen a **Követelések és beszedések \> Fizetési felszólítás \> Fizetési felszólítások áttekintése és feldolgozása** részre, és kövesse az alábbi lépéseket:

    1. Figyelje meg, hogy a fizetési felszólítás kódja a fejlécen: **1. fizetési felszólítás**. A tranzakciósorok kódja azonban **2. fizetési felszólítás**.

   [![Annak ellenőrzése, hogy különböző fizetésifelszólítás-kódok jelennek-e meg a fejlécben és a sorokban.](./media/Ignore-payments-creditmemos-5.PNG)](./media/Ignore-payments-creditmemos-5.PNG)

  A kódok eltérőek, mivel a **Fizetések és jóváírások figyelmen kívül hagyása a fizetési felszólítás kódjának kiszámítása során** lehetőség **Igen** értékre van állítva.

  2. Ne adja fel ezt a fizetési felszólítást.

11. Lépjen a **Követelések és beszedések \> Beállítás \> Kinnlevőségek paraméterei** pontra, majd a **Beszedések** lapon állítsa a **Fizetések és jóváírások figyelmen kívül hagyása a fizetési felszólítás kódjának kiszámítása során** lehetőséget **Nem** értékre.

    [![Fizetések és jóváírások figyelmen kívül hagyása a fizetési felszólítás kódjának kiszámítása során beállítása Nem értékre.](./media/Ignore-payments-creditmemos-6.PNG)](./media/Ignore-payments-creditmemos-6.PNG)

    Most ismét létre kell hoznia a fizetési felszólításokat az US-045 vevőhöz.

12. Lépjen a **Követelések és beszedések \> Fizetési felszólítás \> Fizetési felszólítások létrehozása** részre, és kövesse az alábbi lépéseket:

    1. A **Számla** és a **Jóváírás** beállítása legyen **Igen**.

        Alapértelmezés szerint a **Fizetési felszólítás** mező beállítása **Felszólítás vevőnként**.

    2. A **Fizetési felszólítás dátuma** mezőbe írja be a következő értéket: **1/23/2021**.
    3. A **Szerepeltetni kívánt rekordok** gyorslapon válassza a **Szűrés** lehetőséget, majd a **Vevői számla** mezőben adja hozzá az **US-045** vevőt.
    4. Válassza ki az **OK** lehetőséget.
    5. Kattintson az **OK** gombra a fizetési felszólítások létrehozásához.

13. Lépjen a **Követelések és beszedések \> Fizetési felszólítás \> Fizetési felszólítások áttekintése és feldolgozása** pontra, és figyelje meg, hogy a fizetési felszólítás kódja a fejlécben és a tranzakciósorban is **2. fizetési felszólítás**.

    [![Annak ismételt megjelenítése, hogy ugyanaz a fizetésifelszólítás-kód jelenik meg a fejlécben és a sorokban.](./media/Ignore-payments-creditmemos-7.PNG)](./media/Ignore-payments-creditmemos-7.PNG)

    Ugyanaz a kód jelenik meg mindkét helyen, mivel a **Fizetések és jóváírások figyelmen kívül hagyása a fizetési felszólítás kódjának kiszámítása során** lehetőség **Nem** értékre van állítva.
