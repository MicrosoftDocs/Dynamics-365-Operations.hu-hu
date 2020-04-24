---
title: Kiinduló előrejelzés létrehozása
description: A termeléstervező létrehozhat egy kiinduló előrejelzést az idősorozat szerinti előrejelzési modell használatával vagy az igényelőzmények átmásolásával.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqIntercompanyPlanningGroupSetup, ReqIntercompanyPlanningGroupAllocKeys, ReqDemPlanForecastParameters, ReqDemPlanCreateForecastDialog, SysQueryForm, ReqDemPlanForecastViewer
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3ea5e269f9216fa1dfcaa4377beb7ef52ef153b5
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/02/2020
ms.locfileid: "3209720"
---
# <a name="create-a-baseline-forecast"></a>Kiinduló előrejelzés létrehozása

[!include [banner](../../includes/banner.md)]

A termeléstervező létrehozhat egy kiinduló előrejelzést az idősorozat szerinti előrejelzési modell használatával vagy az igényelőzmények átmásolásával. Ez az eljárás bemutatja, hogyan hozhat létre kiinduló előrejelzést az egy cikkfelosztási kulcsot használó termékekhez az igényelőzmények átmásolásával. 


## <a name="set-up-an-item-allocation-key"></a>Cikkfoglalási kulcs beállítása
1. Ugorjon az Alaptervezés > Beállítás > Vállalatközi tervezőcsoportok lehetőségre.
2. Rekordok kereséséhez használja a gyorsszűrőt. Például szűrjön a Név mezőben a „10” érték megadásával.
    * Az igény-előrejelzés a jogi személyek között történik. Ezért kell beállítania egy vállalatközi tervezőcsoportba az összes céget, amelyek számára előrejelzéseket kíván generálni.  
3. Keresse meg és jelölje ki a kívánt rekordot a listán.
4. Kattintson a Cikkfelosztási kulcsok lehetőségre.
    * Válassza ki az összes cikkfelosztási kulcsot, amelyhez létre kívánja hozni az előrejelzést.  
5. A listában jelölje meg a kiválasztott sort.
    * Válassza ki a D_Aloc cikkfelosztási kulcsot.  
6. Kattintson > .
7. Zárja be a lapot.
8. Zárja be a lapot.

## <a name="set-up-the-demand-forecasting-paramters"></a>Igény-előrejelzési paraméterek beállítása
1. Ugorjon az Alaptervezés > Beállítás > Igény-előrejelzés > Igény-előrejelzési paraméterek lehetőségre.
2. Bontsa ki Az előrejelzési algoritmus paraméterei szakaszt.
3. Az Előrejelzés-generálási stratégia mezőben válassza ki a „Korábbi igény átmásolása” lehetőséget.
4. Kattintson a Mentés gombra.

## <a name="create-a-baseline-forecast"></a>Kiinduló előrejelzés létrehozása
1. Ugorjon az Alaptervezés > Előrejelzés > Igény-előrejelzés > Statisztikai kiinduló előrejelzés generálása lehetőségre.
2. Adjon meg egy dátumot a Kezdő dátum mezőben.
    * Ha 2015. január 1-ei kezdődátumú értékesítési rendeléssel rendelkezik, adja meg ezt a dátumot. Ellenkező esetben adja meg az értékesítési rendelés legkorábbi dátumát.  
3. Adja meg a dátumot a „Záró dátum” mezőben.
    * Adja meg az értékesítési rendelések utolsó dátumát, például a „2015.03.31.” dátumot.  
4. Adjon meg egy dátumot a Kezdő dátum mezőben.
    * Adja meg a „2015.04.01.” dátumot. Ezt a napot automatikusan a következő előrejelzési időszak kezdő dátumaként használja majd a rendszer.  
5. Bontsa ki a Szerepeltetni kívánt rekordok szakaszt.
6. Kattintson a Szűrő parancsra.
7. A listában jelölje meg a kiválasztott sort.
    * Jelölje meg a sort, ahol a Mező = Vállalatközi tervezési csoport.  
8. Érték beírása a Feltétel mezőbe.
    * Adja meg az első feladatnál használt vállalatközi tervezési csoportot, például a 10-es számmal.  
9. Keresse meg és jelölje ki a kívánt rekordot a listán.
    * Válassza ki a sort, ahol Mező = Cikkfelosztási kulcs.  
10. Érték beírása a Feltétel mezőbe.
11. Kattintson az OK gombra.
12. Bontsa ki a Fejlett paraméterek szakaszt.
13. Az Előrejelzési időszak mezőben válassza ki a „Hónap” lehetőséget.
14. Az Előrejelzési horizont mezőbe írja be a „3” értéket.
15. A Befagyasztási időkorlát mezőbe írja be az „1” értéket.
16. Kattintson az OK gombra.

## <a name="visualize-the-demand-forecast"></a>Igény-előrejelzés megjelenítése
1. Ugorjon az Alaptervezés > Előrejelzés > Igény-előrejelzés > Módosított igény-előrejelzés lehetőségre.
2. Az összesített nézet táblázatban válassza ki a cellát az 1. sor 2. oszlopában. Ez a második hónap, amelyhez előrejelzést hozott létre.
3. Állítsa a QtyCell értékét „400”-ra.
    * A cellában adjon meg egy másik számot, mint amit az előrejelzés mutatott, például: 400.  
4. Manuálisan helyesbítette az előrejelzést. Figyelje meg a grafikus jelölést a következő lépésben.
5. Kattintson az Előrejelzési sor részletei lehetőségre.
    * Ezen a lapon láthatja a pontossági értékeket, igényekkel kapcsolatos előzményeket és előrejelzéseket. Az előrejelzéseket is módosíthatja.  

