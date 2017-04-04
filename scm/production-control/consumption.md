---
title: "Az anyagfelhasználás számítása"
description: "Ez a cikk tájékoztatást nyújt az anyagfelhasználás kiszámításához kapcsolódó különféle lehetőségekkel kapcsolatban."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: BOMDesignerEditBOM, BOMTable, ProdBOM
audience: Application User
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 53401
ms.assetid: 9cff88e4-0425-4707-9178-3c2cb10df7c2
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: 2225707329c67a30d9234bef5282d49834ea042a
ms.lasthandoff: 03/31/2017


---

# <a name="calculate-material-consumption"></a>Az anyagfelhasználás számítása

Ez a cikk tájékoztatást nyújt az anyagfelhasználás kiszámításához kapcsolódó különféle lehetőségekkel kapcsolatban. 

A következő, anyagfelhasználás kiszámításához való lehetőségek a **Beállítás** és **Fokozatos felhasználás** a lapokon, a **Sor adatai** gyorslapjon, az **Anyagjegyzék** oldalon érhetők el.

## <a name="variable-and-constant-consumption"></a>Változó és állandó felhasználás
A a **felhasználás** mezőben ki lehet választani e mennyiség állandó vagy változó mennyiséget kell kiszámítani. Válassza ki **állandó** Ha egy rögzített mennyiség vagy kötet előállításához szükséges, a mennyiségtől függetlenül, amely elő. Válassza a **Változó**lehetőséget, amely az alapértelmezett beállítás, ha a szükséges anyag a késztermékek mérete arányos a befejezett termékek számával.

## <a name="calculating-consumption-from-a-formula"></a>Felhasználás számítása képletből
A **Képlet** mezőben be lehet állítani különböző képleteket az anyagfelhasználás kiszámítására. Ha az alapértelmezett **Normál** értéket használja, a felhasználás a nem képletből lesz kiszámolva. A következő képletek együttműködnek a **Magasság**, **Szélesség**, **Mélység**, **Dűrűség**, és **Állandó** mezőkkel:

-   Magasság \*állandó
-   Magasság \*szélessége \*állandó
-   Magasság \*szélessége \*z \*állandó
-   (Magasság \*szélessége \*mélység / sűrűség) \*Állandó

## <a name="rounding-up-and-multiples"></a>Kerekítés és többszörösök
A **Kerekítés** és a **Többszörösök** mezők együttesen lehetővé teszik az anyagfelhasználás értékének kerekítését. Például az anyagkezelési egység szerint kerekítheti az értéket, amelyben a nyersanyagot kitárolják a termeléshez. A következő lehetőségek érhetők el a **Kerekítés** mezőben: **Mennyiség**, **Mérték**, és **Felhasználás**.

### <a name="quantity"></a>Mennyiség

Ha bejelöli **Mennyiség** lehetőséget a kerekítés módszereként, a mennyiségnek a megadott mennyiség többszörösének kell lennie. Ha például csak egész számokat lehet megadni, válassza ki az **1** értéket a **Többszörösök** mezőben. Így a számok 1-el osztható mennyiségre lesznek kerekítve.

### <a name="measurement"></a>Mérték

Általában a **Mérték** lehetőséget kell a kerekítés módszerként választani, ha a nyersanyag meghatározott méretekben érkezik. Például egy 2 méteres fémcső szükséges egy késztermékhez, és fémcsövet 4,5 méteres hosszúságban tárolják. Ebben az esetben a **Mérték** kerekítési mechanizmusa használható annak kiszámítására, hogy hány fémcsőre van szükség egy adott számú késztermék előállításához. Például a **képlet** mező értéke **magasság \*állandó**. A **magasság** mező értéke **2** a csövet, a késztermék szükséges hosszát jelzi. A **Többszörös** mező értéke **4,5**, amely jelzi, hogy a cső 4,5 méteres hosszban lesz kitárolva. A számítás a következő:

1.  A 10 darab késztermékhez szükséges többszörösök száma: 10 ÷ 2 = 5 darab
2.  Összes felhasználás: 4,5 x 5 = 22,5 méter fémcső.

A feltételezés szerint 0,5 méter selejtcső keletkezik minden 5 darab felhasznált cső után.

### <a name="consumption"></a>Felhasználás

Általában a** Felhasználás** lehetőséget kell kerekítési módszerként választani, ha a nyersanyagot a termék egy adott anyagkezelési egység teljes mennyiségében kell megadni. Például 2 liter festékre van szükség egy darab késztermékhez, és a festéket 25 literes tartályokban tárolják ki. Ebben az esetben a **Felhasználás** kerekítési mechanizmusa használható a 25 literes tartályok esetében az egész számokra való kerekítéshez. Ha 180 darab késztermékre van szükség, így lehet kiszámítani a szükséges festék mennyiségét.

1.  Szükséges festék, a selejtet leszámítva: 180 x 2 = 360 liter
2.  Festékes dobozok száma: 360 ÷ 25 = 14,4, amely kerekítve 15.
3.  Szükséges festék, a selejtet beleszámítva: 15 x 25 = 375 liter

## <a name="step-consumption"></a>Fokozatos felhasználás
A fokozatos felhasználást kell használni a mennyiségi intervallumokban történő állandó felhasználás kiszámítására. Ha bejelöli **Fokozatos felhasználás** lehetőséget a **Képlet** mezőben a **Beállítás** lapon, is hozzáadhat információkat a lépésekről a **Fokozatos felhasználás** lapon. A rögzített felhasznált mennyiség a megtermelt mennyiség intervallumaiban is beállítható. Például a fokozatos felhasználás a következő táblázatban látható módon van beállítva.

| Kezdő sorozat | Mennyiség |
|-------------|----------|
| 0,00        | 10.0000  |
| 100,00      | 20.0000  |
| 200,00      | 40.0000  |

Az anyagjegyzék (AJ) mennyisége 1, a termelési mennyiség pedig 110. A felhasználás receptúrája: Kezdő sorozat (Mennyiség) = Felhasználás. Mivel a termelési mennyiség 110, az beleesik a „100 fölött” sorozatba. Ezért a mennyiség 20.


