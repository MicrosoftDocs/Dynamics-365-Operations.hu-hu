---
title: "Kamatlábak beállítása kamatkódhoz"
description: "A kamatkódok olyan beállításokat tartalmaznak, amelyek meghatározzák, hogy mikor kerül sor kamat felszámítására, és hogyan történik annak kiszámítása a hátralékos számlákon."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 01/12/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 59402
ms.assetid: 3b945333-1eaf-4658-ab5a-1a7791a7eb40
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 7ae0bfdc157a7e2e5b9f871dae487a6f85e889b9
ms.contentlocale: hu-hu
ms.lasthandoff: 11/03/2017

---

# <a name="set-up-interest-rates-for-an-interest-code"></a>Kamatlábak beállítása kamatkódhoz

[!include[banner](../includes/banner.md)]


A kamatkódok olyan beállításokat tartalmaznak, amelyek meghatározzák, hogy mikor kerül sor kamat felszámítására, és hogyan történik annak kiszámítása a hátralékos számlákon.

Megteheti, hogy egyetlen kamatkódot állít be, és azt alkalmazza több vevő feladási profilra, számlázási kódra, illetve adott számlasorokra. Ha a kamatkód adatai megváltoznak, a kódot használó összes funkció automatikusan végrehajtja a változtatásokat az új tranzakciókon. Minden egyes kamatkódnál kétféle típusú kamatlábat állíthat be:
-   Kamatbevételek kamatlábai − Ezek olyan bevételt jelentenek, amely a számlákra vagy kamatlevelekre kamat felszámításával keletkezik.
-   Kamatfizetések kamatlábai − Ezek olyan költséget jelentenek, amely jóváírásokra fizetett kamat címén keletkezik.

Ezen két kamatlábtípus mindegyike létezhet ugyanabban az időben és ugyanazon kamatkódon. A kamatlábak háromféle számítástípuson alapulhatnak:
-   Százalékérték szerinti kamat.
-   Összeg szerinti kamat.
-   Tartomány szerinti kamat, amely egyetlen százalékértéket vagy összeget eredményez.

Ha a kamatszámításra egy kamatkód segítségével kerül sor, külön kamatlevél jön létre mindegyik kamatlábhoz, amely hatályban van abban az időszakban, amikor a kifizetés túllépte a tranzakció esedékességi dátumát. Használja a **Nyereségek** lapját a **Kamat kód** lapon a kamat kamatlábainak beállításához, amit a kamat felszámítása által kapott. Használja a **Kifizetések** oldalt a kamat kamatlábainak beállításához, amit kifizet.

## <a name="interest-rates-based-on-a-percentage"></a>Százalékértékek alapuló kamatlábak
Beállíthat kamatlábakat, amelyek egy megadott százalékot számítanak.

-   A kamat összege az összes pénznemre vonatkozik.
-   A nem kötelező kamat összeg határaival lehet megadni.
-   **Százalék** van kiválasztva** **a **Kamat számítása alapján** mezőben a **Kamatkódok beállítása** oldalon.

Például, ha olyan kamatkódot szeretne beállítani, amely kéthavonta 5 % kamatot számít fel, miután a számla kifizetése túllépte a tranzakció esedékességi dátumát, akkor írjon be 2 értéket az **Összes kamat kiszámítása** mezőbe, és jelölje be **Hónap** lehetőséget.

## <a name="interest-rates-based-on-amounts"></a>Összegeken alapuló kamatlábak
Beállíthat olyan kamatlábakat, amelyek egy megadott összeget számítanak ki pénznemenként.
-   Minden egyes pénznemhez egy kamatösszeg van megadva a kamat kódban.
-   A nem kötelező kamat összeg határaival lehet megadni.
-   **Összeg** van kiválasztva **Számítása kamat alapján** mezőben **Kamat kódok beállítása** oldalon.

Például, ha olyan kamatkódot szeretne beállítani, amely 20 naponta 25,00 egység kamatot számít fel, miután a számla kifizetése túllépte a tranzakció esedékességi dátumát, akkor írjon be 20 értéket az **Összes kamat kiszámítása** mezőbe és válassza ki a **Nap** lehetőséget.

## <a name="interest-rates-based-on-ranges"></a>Tartományokon alapuló kamatlábak
Beállíthat olyan kamatlábakat, amelyek változnak a lejárt összegtől, az összeg késedelmes napjainak számától vagy az összeg késedelmes hónapjainak számától függően.
-   Használhatja a **Pénznemenkénti Bevételek** lapot a minden egyes pénznemhez tartozó konkrét kamat beállításának meghatozásához. Így van ott is, ahol meghatározza a tartományt.
-   Használja a **Tartományok** gombot a beállítani kívánt tartomány megjelenítő sorok hozzáadására. A **Származó** érték jelzi a tartomány kezdetét és a **Kamat érték** száma vagy egy százalékot vagy egy összeget jelez a **Számítás kamat alapján** mezőben a **Kamat kódok beállítása** oldalon történő kiválasztástól függően.

## <a name="example-1-interest-by-range--amount"></a>1. példa: Kamat tartomány szerint = Összeg
Ön olyan kamatkódot állít be, amely kamatot számít fel minden három hónapban egyszer azt követően, hogy a számla kifizetése túllépi a tranzakció esedékességi dátumát. A számítást százalékos kamatmértékre szeretné alapozni, sávos módon az összegintervallumok szerint. A kamat értéke 1 százalék lesz legfeljebb 1.000,00 számlaértékig, 2 százalék 1.001,00 és 5.000,00 érték között, és 3 százalék az 5.000,00 feletti összegekre. A kamatkód mezőinek értékét a következőképpen kell beállítani.

| **Mezőnév**                  | **Mező értéke** |
|---------------------------------|-----------------|
| **Kamatkód**               | 3M%ByAmt        |
| **Kamatszámítás gyakorisága:**    | 3/Hónap         |
| **Kamat tartománya**           | Összeg          |
| **Kamat kiszámítása a következő alapján:** | Százalék      |

A tartomány adatait a következőképpen kell beállítani.

| **Kezdő érték** | **Kamat értéke** |
|----------------|--------------------|
| 0              | 1                  |
| 1,001          | 2                  |
| 5,001          | 3                  |

 
## <a name="example-2-interest-by-range--days"></a>2. példa: Kamat tartomány szerint = Napok
--------------------------------------------------

Ön olyan kamatkódot állít be, amely kamatot számít fel 15 naponként egyszer azt követően, hogy a számla kifizetése túllépi a tranzakció esedékességi dátumát. A számítást összegként megadott kamatmértékre szeretné alapozni, sávos módon napi intervallumok szerint. A kamat mértéke 10,00 egység lesz 15 naponta az első 60 napban, 15,00 egység 15 naponta 61.–90. nap között, és 20,00 egység 15 naponta a 91. naptól kezdődően. A kamatkód mezőinek értékét a következőképpen kell beállítani.

| **Mezőnév**                  | **Mező értéke** |
|---------------------------------|-----------------|
| **Kamatkód**               | 15DAmtXDay      |
| **Kamatszámítás gyakorisága:**    | 15/Nap          |
| **Kamat tartománya**           | Napok            |
| **Kamat kiszámítása a következő alapján:** | Összeg          |

A tartomány adatait a következőképpen kell beállítani.

| **Kezdő érték** | **Kamat értéke** |
|----------------|--------------------|
| 0              | 10                 |
| 61             | 15.                 |
| 91             | 20                 |

 
## <a name="example-3-interest-by-range--months"></a>3. példa: Kamat tartomány szerint = Hónapok
----------------------------------------------------

Ön olyan kamatkódot állít be, amely kamatot számít fel minden hónapban egyszer azt követően, hogy a számla kifizetése túllépi a tranzakció esedékességi dátumát. A számítást százalékos kamatmértékre szeretné alapozni, sávos módon hónapok szerint. A kamat mértéke 1,5 százalék lesz havonta az első három késedelmes hónapban, 2,0 százalék havonta a második három hónapban, és 2,5 százalék havonta az első hat hónapot követő minden hónapban. A kamatkód mezőinek értékét a következőképpen kell beállítani.

| **Mezőnév**                  | **Mező értéke** |
|---------------------------------|-----------------|
| **Kamatkód**               | 1M%ByMth        |
| **Kamatszámítás gyakorisága:**    | 1/hónap         |
| **Kamat tartománya**           | Hónapok          |
| **Kamat kiszámítása a következő alapján:** | Százalék      |

A tartomány adatait a következőképpen kell beállítani.

| **Kezdő érték** | **Kamat értéke** |
|----------------|--------------------|
| 0              | 1.5                |
| 4              | 2                  |
| 7              | 2,5                |

## <a name="new-versions"></a>Új verziók
A kamatkódok dátum érvényességek. Ha szeretné módosítani a kamatlábat, létrehozhat egy **új verziót**, ami a jövőbeli dátum szerint hatályos.

Különböző verziói megtekintéséhez használja a **Dátum, mint** menüt lehetőséget a fordulónap kiválasztásához. Bejelölheti a **Összes rekord megjelenítése** lehetőséget a lapon megjelenő összes kamatkód megtekintéséhez.




