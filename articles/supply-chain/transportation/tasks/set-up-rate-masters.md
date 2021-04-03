---
title: Díjtörzsek beállítása
description: Ez az eljárás bemutatja, hogyan állíthat be egy díjnyilvántartást.
author: ShylaThompson
manager: tfehr
ms.date: 10/16/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TMSBreakMaster,TMSRateMaster,TMSRateMasterBase,TMSRateBaseType, TMSRouteWorkbench
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 77629cbaec4c4d4608b8941e55ab23a106d38727
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5233607"
---
# <a name="set-up-rate-masters"></a>Díjtörzsek beállítása

[!include [banner](../../includes/banner.md)]

Ez az eljárás bemutatja, hogyan állíthat be egy díjnyilvántartást. Általában a logisztikai vezető állítja be a díjnyilvántartást, a szállítmányozókkal aláírt szerződésektől függően. Ebben a példában egy légi fuvarozó számára állítunk be díjnyilvántartást. Ez az eljárás az USMF bemutatócéget használja.

## <a name="set-up-break-master"></a>Felosztástörzs beállítása

1. Lépjen a **Szállításkezelés > Beállítás > Minősítés > Felosztástörzs** pontra. A felosztást az árképzési szerkezet és annak töréspontjainak meghatározására használják. Az árképzési szerkezet többszintű árképzést használ a fizikai méretek alapján.  
1. Válassza az **Új** lehetőséget.
1. A **Felosztástörzs** mezőben adjon meg egy értéket.
1. A **Név** mezőben adjon meg egy értéket.
1. Az **Adattípus** mezőben válassza ki az adattípust.
1. Az **Összehasonlítás** mezőbe írja be a kért összehasonlítási értéket (operátorok használatával).
1. Írja be a felosztási értéket az **Felosztási egység** mezőbe.
1. A **Részletek** szakaszban hozzon létre annyi felosztást, amennyi az árképzési szerkezetéhez szükséges.
1. Válassza a **Mentés** lehetőséget.

## <a name="set-up-rate-master"></a>Díjtörzs beállítása

1. Lépjen a **Szállításkezelés > Beállítás > Minősítés > Díjjegyzék** pontra.
1. Válassza az **Új** lehetőséget.
1. Érték beírása a **Díjjegyzék** mezőbe.
1. Írjon be egy értéket a **Név** mezőbe.
1. Az **Értékelés metaadatok azonosítója** mód mezőben válassza a legördítő nyílat a keresőlista megnyitásához. A díjazási metaadatok azonosítója határozza meg a díjnyilvántartáshoz szükséges adatokat, mivel ez határozza meg a szállításkezelési motor számára szükséges metaadatokat, amely a ezt a díjnyilvántartást használja.  
1. Ebben a példában kattintson a P2P opció lehetőségre. Ez már definiálva van a bemutató adatokban.
1. A listában válassza ki a kiválasztott sorból a hivatkozást.
1. Válassza a **Mentés** lehetőséget.

## <a name="set-up-rate-base"></a>Díjalap beállítása

1. Válassza ki az **Alapdíjat**.
    * Az alapdíj határozza meg a szállítmányozó díját, és felhasználható egy tarifaszerkezet létrehozásához, mivel a felosztásban meghatározott töréspontok alapján rendszerezi a díjakat.  
2. Válassza az **Új** lehetőséget.
3. Érték beírása az **Alapdíj** mezőbe.
4. Írjon be egy értéket a **Név** mezőbe.
5. A **Felosztás** mezőben válassza ki a legördítő nyilat a a keresőlista megnyitásához.
    * A felosztást az árképzési szerkezet és annak töréspontjainak meghatározására használják. Az árképzési szerkezet többszintű árképzést használ a fizikai méretek alapján.  
6. Ebben a példában használja a súlyt. Ez már definiálva van a bemutató adatokban.
7. A listában válassza ki a kiemelt sorból a hivatkozást.
8. A **Részletek** szakasz kibontása.
9. Válassza az **Új** lehetőséget.
10. A **Lerakási hely irányítószáma – kezdő érték** mezőbe írja be a „30301” értéket.
11. A **Lerakási hely irányítószáma – befejező érték** mezőbe írja be a „30318” értéket.
12. A **Kiszállítási hely országa** mezőbe írja be az „USA” értéket.
13. A **<0,45 kg** mezőbe írja be a „100” értéket.
    * Adja meg a kilogrammonkénti költséget, ha a szállítmány teljes súlya kevesebb mint 0,45 kilogramm.  
14. A **<2,25 kg** mezőbe írja be a „300” értéket.
    * Adja meg a kilogrammonkénti költséget, ha a szállítmány teljes súlya kevesebb mint 2 kilogramm.  
15. A **<9 kg** mezőbe írja be a „500” értéket.
    * Adja meg a kilogrammonkénti költséget, ha a szállítmány teljes súlya kevesebb mint 9 kilogramm.  
16. A **<45 kg** mezőbe írja be a „1000” értéket.
    * Adja meg a kilogrammonkénti költséget, ha a szállítmány teljes súlya kevesebb mint 45 kilogramm.  
17. A **<450 kg** mezőbe írja be a „3000” értéket.
    * Adja meg a kilogrammonkénti költséget, ha a szállítmány teljes súlya kevesebb mint 450 kilogramm.  
18. Válassza a **Mentés** lehetőséget.
19. Zárja be a lapot.

## <a name="assign-rate-base"></a>Díjalap hozzárendelése

1. **Alapdíj hozzárendelés** szakasz kibontása vagy összecsukása.
2. Válassza az **Új** lehetőséget.
    * Mindegyik díjnyilvántartáshoz hozzárendelhet több díjalapot. Ez lehetővé teszi a különböző árpontok létrehozását az egyes szállítmányozók számára a céltól, a szolgáltatástól vagy a különböző alapdíjaktól függően. Ebben az eljárásban csak egy alapdíj-hozzárendelést hoz majd létre.  
3. Írjon be egy értéket a **Név** mezőbe.
4. Az **Alapdíj** mezőben válassza ki a legördítő nyilat a keresőlista megnyitásához.
5. A listában válassza ki a kiemelt sorból a hivatkozást.
6. A **Szolgáltatás** mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
7. Keresse meg és jelölje ki a kívánt rekordot a listán.
8. A listában válassza ki a kiemelt sorból a hivatkozást.
9. A **Felvételi hely irányítószáma** mezőbe írja be a „98052” értéket.
    * Válassza ki, hogy melyik irányítószámról legyen érvényes ez az alapdíj-hozzárendelés.
10. A **Felvételi hely országa** mezőbe írja be az „USA” értéket.
11. Válassza a **Mentés** lehetőséget.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]