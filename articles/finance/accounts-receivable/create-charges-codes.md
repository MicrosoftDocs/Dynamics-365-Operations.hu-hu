---
title: Költségkódok létrehozása
description: Ez a témakör leírja, hogyan kell konfigurálni a költségkódokat mind a Kötelezettségek, mind a Kinnlevőségek esetében.
author: rachel-profitt
ms.date: 12/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: MarkupTable
audience: Application User
ms.reviewer: roschlom
ms.custom: ''
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2022-01-03
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 034be190890a67fd0921d40fffdc704b9d6d5df7
ms.sourcegitcommit: 5bfd6511d710deb539b4030eb0e9c48d25513595
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/19/2022
ms.locfileid: "8014105"
---
# <a name="create-charges-codes"></a>Költségkódok létrehozása

Ez a témakör leírja, hogyan kell konfigurálni a költségkódokat mind a Kötelezettségek, mind a Kinnlevőségek esetében. Ha a szervezet előírja, hogy az értékesítési és beszerzési rendelések sorai mellett az értékesítési és beszerzési rendelések sorai mellett az értékesítési összegeket is nyomon kell követni, erre a célra költségkódokat használhat. Például fuvardíjat és biztosítást fizet egy beszerzési rendelés alapján, és ezeket az összegeket külön kell tételként megadni a beszerzési rendelésen. Ebben az esetben megadhatja, hogy az összegeket kiadási számlákra adja-e fel, vagy hozzáadja a cikkek költséghez.

## <a name="set-up-charges-codes-for-accounts-receivable"></a>A Kinnlevőségek – Költségkódok beállítása

A Kinnlevőségek között a következő lépések szerint hozhatja létre a költségkódokat.

1. Ugrás **a Kinnlevőségek –** &gt; **Költségek beállítása** &gt; **költségkódhoz**
2. Válassza az **Új** lehetőséget.
3. A **Költségkód** mezőben adja meg a költség kódját.
3. A Leírás **mezőbe írja be a költség** leírását.
4. Nem kötelező: A **Cikk áfacsoport** mezőjében válasszon ki egy áfacsoportot.
5. A Feladás gyors oldalon adja meg, hogyan legyen a költség automatikusan tartozik és **követel** tételekként könyvelve.
6. Ha a főkönyvi számlát tartozástípusként vagy követel típusúként választotta, adja meg a Feladás mezők feladási típusát, és adja meg a fő számlát **a** Számla **·** **mezőkben**.

### <a name="example"></a>Példa

A vevő fizeti a díjat. Így hozzáadódik az értékesítési rendelés végösszegeihez. A következő feladási adatokat állíthatja be:

- A Tartozás szakasz Típus mezőjében válassza ki a Vevő/szállító lehetőséget a számla költségének a vevő számlájához **való** **·** **hozzáadásához**.
- A Jóváírás **szakasz Típus** **mezőjében válassza ki a** **Főkönyvi** számlát. Ezután a Számla mezőben válassza ki a **számladíjakból** származó bevétel fő számláját.

> [!NOTE]
> Ha a kiválasztott kód tartozástípusa vagy követel típusa Főkönyvi számla vagy Cikk, a költségtranzakcióhoz más pénznemet **is** be lehet **írni**.

A költségek szövegét a vevőhöz rendelt nyelven nyomtathatja ki. Ha más nyelven is meg kell adni a költségkód szövegét, válassza a **Fordítások** lehetőséget.

## <a name="set-up-charges-codes-for-accounts-payable"></a>A Kötelezettségek – Költségkódok beállítása

A Kötelezettségekhez a következő lépések szerint hozhatja létre a költségkódokat.

1. Tegye a következők egyikét:

    - Ugrás **a Kötelezettségek –** &gt; **Költségek beállítása** **– Költségek** &gt; **kódra**.
    - Ugrás a **Beszerzés és forrás** &gt; **beállítási** &gt; **költségek** &gt; **költségei kódra**

2. Válassza az **Új** lehetőséget.
3. A **Költségkód** mezőben adja meg a költség kódját.
3. A Leírás **mezőbe írja be a költség** leírását.
4. Nem kötelező: A **Cikk áfacsoport** mezőjében válasszon ki egy áfacsoportot.
5. Nem kötelező: A Maximális összeg mezőben adja meg a **költségkódhoz** engedélyezett maximális összeget.

    Ez a mező a szállítói számlák költségének ellenőrzésére használható. A költségek ellenőrzésének engedélyezéséhez jelölje be a Számlaegyeztetés érvényesítése jelölőnégyzetet a Kötelezettségek paraméterei **lap** **·** **Számlaellenőrzés** lapján.

    > [!IMPORTANT]
    > A számlák költségeinek ellenőrzéshez létre kell hoznia egy olyan irányelvszabály-típus példányát is, amely az adott szállítói számla irányelvében szereplő költségeken alapul.

6. A Feladás gyors oldalon adja meg, hogyan legyen a költség automatikusan tartozik és **követel** tételekként könyvelve.
7. Ha a főkönyvi számlát tartozástípusként vagy követel típusúként választotta, adja meg a tartozásfeladás és a Követel feladás mező feladási típusát, és adja meg a fő számlát a Tartozik számla és a Követel **számla** **·** **·** **·** **mezőben**.
8. Ha engedélyezni szeretné egy olyan számla költségértékének összehasonlítását, amely a megfelelő beszerzési rendelés fejlécében vagy sorában szereplő költségeket tartalmazza, jelölje be a Beszerzési rendelés és számla értékeinek **összehasonlítása** jelölőnégyzetet.

### <a name="example"></a>Példa

A költséget a beszerzési rendelés vagy szállítói számla végösszegének részeként rögzítheti költségként. A következő lépések szerint állíthatja be a feladási adatokat. 

- A Jóváírás szakasz Típus mezőjében válassza ki a Vevő/szállító lehetőséget a számla költségének szállítói számlához **való** **·** **hozzáadásához**.
- A Terhelés **szakasz Típus** **mezőjében válassza ki a** **Főkönyvi** számlát. Ezután a Számla mezőben válassza ki a számlaköltségek fő **számláját**.

A következő lépések szerint állíthatja be a feladási adatokat úgy, hogy az egységköltséget hozzáadja a rendszer a cikk-költséghez.

- A Jóváírás szakasz Típus mezőjében válassza ki a Vevő/szállító lehetőséget a számla költségének szállítói számlához **való** **·** **hozzáadásához**.
- A Terhelés szakasz Típus mezőjében válassza ki a Cikket, és adja hozzá a költséget **a** **·** **cikk**-költséghez.

> [!NOTE]
> Előfordulhat, hogy a beszerzési rendelésen vagy számlán megadott pénznemtől eltérő pénznemet szeretne használni. Ha a kiválasztott kód tartozástípusa vagy követel típusa Főkönyvi számla vagy Cikk, más **pénznemet** is **be lehet** írni.

A költségek szövegét a vevőhöz rendelt nyelven nyomtathatja ki. Ha más nyelven is meg kell adni a költségkód szövegét, válassza a **Fordítások** lehetőséget.
