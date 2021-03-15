---
title: Anyagfelhasználás kiszámítása
description: Ez a cikk tájékoztatást nyújt az anyagfelhasználás kiszámításához kapcsolódó különféle lehetőségekkel kapcsolatban.
author: johanhoffmann
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BOMDesignerEditBOM, BOMTable, ProdBOM
audience: Application User
ms.reviewer: kamaybac
ms.custom: 53401
ms.assetid: 9cff88e4-0425-4707-9178-3c2cb10df7c2
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: acccc677c855fc675d52814d7f6f0a5141bbc8af
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "5001669"
---
# <a name="calculate-material-consumption"></a>Anyagfelhasználás kiszámítása

[!include [banner](../includes/banner.md)]

Ez a cikk tájékoztatást nyújt az anyagfelhasználás kiszámításához kapcsolódó különféle lehetőségekkel kapcsolatban. 

A következő, anyagfelhasználás kiszámításához való lehetőségek a **Beállítás** és **Fokozatos felhasználás** a lapokon, a **Sor adatai** gyorslapjon, az **Anyagjegyzék** oldalon érhetők el.

## <a name="variable-and-constant-consumption"></a>Változó és állandó felhasználás
A **Felhasználás** mezőben kiválaszthatja, hogy a felhasználás állandó vagy változó mennyiségként legyen kiszámolva. Válassza az **Állandó** lehetőséget, ha egy fix mennyiség vagy terjedelem szükséges a termeléshez, a termelt mennyiségtől függetlenül. Válassza a **Változó** lehetőséget, amely az alapértelmezett beállítás, ha a szükséges anyag a késztermékek mérete arányos a befejezett termékek számával.

## <a name="calculating-consumption-from-a-formula"></a>Felhasználás számítása képletből
A **Képlet** mezőben be lehet állítani különböző képleteket az anyagfelhasználás kiszámítására. Ha az alapértelmezett **Normál** értéket használja, a felhasználás a nem képletből lesz kiszámolva. A következő képletek együttműködnek a **Magasság**, **Szélesség**, **Mélység**, **Dűrűség**, és **Állandó** mezőkkel:

-   Magasság \* Konstans
-   Magasság \* Szélesség \* Konstans
-   Magasság \* Szélesség \* Mélység \* Konstans
-   (Magasság \* Szélesség \* Mélység / Sűrűség) \* Konstans

## <a name="rounding-up-and-multiples"></a>Kerekítés és többszörösök
A **Kerekítés** és a **Többszörösök** mezők együttesen lehetővé teszik az anyagfelhasználás értékének kerekítését. Például az anyagkezelési egység szerint kerekítheti az értéket, amelyben a nyersanyagot kitárolják a termeléshez. A következő lehetőségek érhetők el a **Kerekítés** mezőben: **Mennyiség**, **Mérték**, és **Felhasználás**.

### <a name="quantity"></a>Mennyiség

Ha bejelöli **Mennyiség** lehetőséget a kerekítés módszereként, a mennyiségnek a megadott mennyiség többszörösének kell lennie. Ha például csak egész számokat lehet megadni, válassza ki az **1** értéket a **Többszörösök** mezőben. Így a számok 1-el osztható mennyiségre lesznek kerekítve.

### <a name="measurement"></a>Mérték

Általában a **Mérték** lehetőséget kell a kerekítés módszerként választani, ha a nyersanyag meghatározott méretekben érkezik. Például egy 2 méteres fémcső szükséges egy késztermékhez, és fémcsövet 4,5 méteres hosszúságban tárolják. Ebben az esetben a **Mérték** kerekítési mechanizmusa használható annak kiszámítására, hogy hány fémcsőre van szükség egy adott számú késztermék előállításához. Ebben a példában a **Képlet** mező értéke a **Magasság \* Konstans**  értékre van állítva. A **Magasság** mező értéke **2**, amely a késztermékhez szükséges csőhosszt jelzi. A **Többszörös** mező értéke **4,5**, amely jelzi, hogy a cső 4,5 méteres hosszban lesz kitárolva. A számítás a következő:

1.  A 10 darab késztermékhez szükséges többszörösök száma: 10 ÷ 2 = 5 darab
2.  Összes felhasználás: 4,5 x 5 = 22,5 méter fémcső.

A feltételezés szerint 0,5 méter selejtcső keletkezik minden 5 darab felhasznált cső után.

### <a name="consumption"></a>Felhasználás

Általában a **Felhasználás** lehetőséget kell kerekítési módszerként választani, ha a nyersanyagot a termék egy adott anyagkezelési egység teljes mennyiségében kell megadni. Például 2 liter festékre van szükség egy darab késztermékhez, és a festéket 25 literes tartályokban tárolják ki. Ebben az esetben a **Felhasználás** kerekítési mechanizmusa használható a 25 literes tartályok esetében az egész számokra való kerekítéshez. Ha 180 darab késztermékre van szükség, így lehet kiszámítani a szükséges festék mennyiségét.

1.  Szükséges festék, a selejtet leszámítva: 180 x 2 = 360 liter
2.  Festékes dobozok száma: 360 ÷ 25 = 14,4, amely kerekítve 15.
3.  Szükséges festék, a selejtet beleszámítva: 15 x 25 = 375 liter

## <a name="step-consumption"></a>Fokozatos felhasználás
A fokozatos felhasználást kell használni a mennyiségi intervallumokban történő állandó felhasználás kiszámítására. Ha bejelöli a **Fokozatos felhasználás** elemet a **Képlet** mezőbe a **Beállítás** lapon, hozzáadhat információkat a lépésekről a **Fokozatos felhasználás** lapon. A rögzített felhasznált mennyiség a megtermelt mennyiség intervallumait állítható be. Például a fokozatos felhasználás a következő táblázatban látható módon van beállítva.

| Kezdő sorozat | Mennyiség |
|-------------|----------|
| 0,00        | 10.0000  |
| 100,00      | 20.0000  |
| 200,00      | 40.0000  |

Az anyagjegyzék (AJ) mennyisége 1, a termelési mennyiség pedig 110. A felhasználás receptúrája: Kezdő sorozat (Mennyiség) = Felhasználás. Mivel a termelési mennyiség 110, az beleesik a „100 fölött” sorozatba. Ezért a mennyiség 20.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]