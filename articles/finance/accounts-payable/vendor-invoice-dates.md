---
title: Szállítóiszámla-dátumok
description: Ez a témakör a szállítói számlákon megjelenő dátumokat írja le. Bemutatja azt is, hogyan lehet úgy beállítani a rendszert, hogy az automatikusan korrigálja a feladási dátumot.
author: sunfzam
ms.date: 2/09/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.custom: intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2021-08-30
ms.dyn365.ops.version: 10.0.23
ms.openlocfilehash: 943a84407d022c2c05bc534a35a2b5d44a94653e
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8876412"
---
# <a name="vendor-invoice-dates"></a>Szállítóiszámla-dátumok

[!include [banner](../includes/banner.md)]

Ez a témakör a szállítói számlákon megjelenő dátumokat írja le. Bemutatja azt is, hogyan lehet úgy beállítani a rendszert, hogy az automatikusan korrigálja a feladási dátumot.

A **Függőben lévő szállítói számla részletek** oldalon a számla fejlécében négy dátum látható: a számla befogadásának dátuma, a számla dátuma, a feladási dátum és a határidő. Szállítói számla létrehozásakor alapértelmezés szerint a következő dátumok vannak megadva:

- **Számla beérkezési dátuma** – Ez a mező az aktuális rendszerdátumra van beállítva.
- **Feladási dátum** – Ez a mező az aktuális rendszerdátumra van beállítva. 
- **Határidő** – A mező dátuma kiszámítása a feladási dátum és a fizetési feltételek alapján történik.
- **Számla dátuma** – Alapértelmezés szerint ez a mező üres. Azonban igény szerint megadható érték. Ebben az esetben a **Határidő** mezőben található dátum számladátum és a fizetési feltételek alapján újra lesz számítva.

Előfordulhat, hogy a szállítói számla függő állapotban van hosszú ideig az időszak lezárása után. Ha készen áll a feladásra, akkor a korábbi feladási időszak régi feladási dátumát használja a a napló. Az az időszak azonban már le van zárva. Emiatt a Kötelezettségek (AP) adminisztrátorának manuálisan kell módosítania minden korábban létrehozott függőben lévő számla feladási dátumát az új feladási időszakra.

Az ebben a cikkben ismertetett funkció segítségével beállítható a rendszer, így automatikusan az üzleti követelményeknek megfelelően módosítja a feladási dátumot.

## <a name="parameter-for-automatically-adjusting-the-vendor-invoice-posting-date"></a>Paraméter a szállítói számla feladási dátumának automatikus módosításához

A következő lépések segítségével engedélyezheti a rendszer számára a szállítói számlák feladási dátumának automatikus kiigazítását.

1.  Ugorjon a **Kötelezettségek \> Beállítás \> Kötelezettségek paraméterei** pontra.
2.  A **Főkönyv és áfa** lap **Feladási dátum automatikus beállítása** mezőjében a következő értékek egyikét válassza ki:

    - **Nincs módosítás** – A rendszer a feladás során nem módosítja automatikusan a feladási dátumot. Alapértelmezés szerint ez az érték van kiállítva.
    - **Mindig módosítsa a feladási dátumot a rendszerdátumra** – a rendszer automatikusan a rendszerdátumra módosítja a feladási dátumot a feladás során.
    - **A feladási dátum módosítása a rendszerdátumra, ha a feladási dátum értéke lezárt vagy várakoztatott** – A rendszer a feladás során a rendszerdátumra módosítja a feladási dátumot, de csak akkor, ha a feladási dátumnak megfelelő időszak állapota **Lezárva** vagy **Fel van függesztve**.
    - **A feladási dátum módosítása az új időszak első napjára, ha a feladási dátum értéke lezárt vagy várakoztatott.** – A rendszer a feladás során az új időszak első napjára módosítja a feladási dátumot, de csak akkor, ha a feladási dátumnak megfelelő időszak állapota **Lezárva** vagy **Fel van függesztve**.

> [!NOTE]
> Ha az automatikusan módosított új feladási dátum új pénzügyi évben van, akkor a számla feladási dátuma nem frissül. A felhasználó hibaüzenetet kap: "A pénzügyi év megváltozott. Ellenőrizze, majd adja meg újra a feladási dátumot." A feladáshoz frissíteni kell a számla új pénzügyi évének dátumát.

## <a name="impact-of-posting-date-changes"></a>A feladási dátumváltozások hatása

Ha egy függő szállítói számlán módosítja a feladási dátumot, a módosításnak a következő hatása lesz:

- **Határidő**

    - Ha **Számla dátuma** mező üres a határidő az új feladási dátum és fizetési feltételek alapján újra lesz számítva.
    - Ha a **Számla dátuma** mező előzőleg be lett állítva, a feladási dátum módosítása nem befolyásolja a határidő dátumát.

- **Készpénzfizetési engedmény dátuma**

    - Ha a **Számla dátuma** mező üres, a program az új feladási dátumot használja a készpénzfizetési engedmény kiszámításához.
    - Ha a **Számla dátuma** mező előzőleg be lett állítva, a készpénzfizetési engedmény nem módosul.

- **Árfolyam** – Az árfolyam dátumát a **Szállítói könyvelés frissítése a számladátum használatával** beállítás határozza meg a **Számla** lapon a **Kinnlévőségek paraméterei** oldalon (**Kintlévőségek \> Beállítás \> Kintlévőségek paraméterei**).

    - Ha ez a beállítás **Igen**, a számla dátumát használja a rendszer, és a feladási dátum módosítása nem befolyásolja az árfolyamot.
    - Ha ez a beállítás **Nem**, az árfolyam számítása a feladási dátum alapján történik. A feladási dátum frissítése esetén a könyvelési és jelentési összegek újra lesznek számítva. Ezért újra el kell végezni az egyeztetés ellenőrzését.

## <a name="validation"></a>Ellenőrzés

A **Kötelezettségek paraméterei** lap **Számla** lapján (**Kötelezettségek \> Beállítás \> Kötelezettségek paraméterei**) két további mező befolyásolja a számlafeldolgozást:

- Ha a **Használt számlaszám ellenőrzése** mező be van állítva **Ismétlődések tiltása a pénzügyi éven belül** beállításra, a rendszer a feladási dátum alapján ellenőrzi, hogy vannak-e ismétlődő számlák a számlafeladás során.
- Ha a **A dokumentumdátumnak szerepelnie kell a szállítói számlán** mezőben a **Hiba beállítás** van megadva, a **Számladátuma a függőben lévő számlafejlécben** mező kötelező. Ha a számla dátuma későbbi a feladási dátumnál, a rendszer egy hibaüzenetet küld.
