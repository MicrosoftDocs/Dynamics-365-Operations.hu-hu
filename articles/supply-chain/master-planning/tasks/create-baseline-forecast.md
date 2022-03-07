---
title: 'Útmutató: Kiinduló előrejelzés létrehozása'
description: A termeléstervező létrehozhat egy kiinduló előrejelzést az idősorozat szerinti előrejelzési modell használatával vagy az igényelőzmények átmásolásával.
author: ChristianRytt
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ReqIntercompanyPlanningGroupSetup, ReqIntercompanyPlanningGroupAllocKeys, ReqDemPlanForecastParameters, ReqDemPlanCreateForecastDialog, SysQueryForm, ReqDemPlanForecastViewer
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 843e0b3827851e1251a2c77269859bb7903f69ec
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/29/2021
ms.locfileid: "7578320"
---
# <a name="guide-create-a-baseline-forecast"></a>Útmutató: Kiinduló előrejelzés létrehozása

[!include [banner](../../includes/banner.md)]

A termeléstervező létrehozhat egy kiinduló előrejelzést az idősorozat szerinti előrejelzési modell használatával vagy az igényelőzmények átmásolásával. Ez az eljárás bemutatja, hogyan hozhat létre kiinduló előrejelzést az egy cikkfelosztási kulcsot használó termékekhez az igényelőzmények átmásolásával.

## <a name="set-up-an-item-allocation-key"></a>Cikkfoglalási kulcs beállítása

1. Ugorjon az **Alaptervezés > Beállítás > Vállalatközi tervezőcsoportok** lehetőségre.
2. Rekordok kereséséhez használja a gyorsszűrőt. Például szűrjön a *Név* mezőben a *10* érték megadásával.
    * Az igény-előrejelzés a jogi személyek között történik. Ezért kell beállítania egy vállalatközi tervezőcsoportba az összes céget, amelyek számára előrejelzéseket kíván generálni.  
3. Keresse meg és jelölje ki a kívánt rekordot a listán.
4. Válassza a **Cikkfelosztási kulcsok** lehetőséget.
    * Válassza ki az összes cikkfelosztási kulcsot, amelyhez létre kívánja hozni az előrejelzést.  
5. A listában jelölje meg a kiválasztott sort.
    * Válassza ki a D_Aloc cikkfelosztási kulcsot.  
6. Válassza **>**.
7. Zárja be a lapot.
8. Zárja be a lapot.

## <a name="set-up-the-demand-forecasting-parameters"></a>Igény-előrejelzési paraméterek beállítása

1. Ugorjon az **Alaptervezés > Beállítás > Igény-előrejelzés > Igény-előrejelzési paraméterek** lehetőségre.
2. Bontsa ki az **Előrejelzési algoritmus paraméterei** szakaszt.
3. Az **Előrejelzés-generálási stratégia** mezőben válassza ki a **Korábbi igény átmásolása** lehetőséget.
4. Válassza a **Mentés** lehetőséget.

## <a name="create-a-baseline-forecast"></a>Kiinduló előrejelzés létrehozása

1. Ugorjon az **Alaptervezés > Előrejelzés > Igény-előrejelzés > Statisztikai kiinduló előrejelzés generálása** lehetőségre.
2. Adjon meg egy dátumot a **Kezdő dátum** mezőben.
    * Ha 2015. január 1-ei kezdődátumú értékesítési rendeléssel rendelkezik, adja meg ezt a dátumot. Ellenkező esetben adja meg az értékesítési rendelés legkorábbi dátumát.  
3. Adjon meg egy dátumot a **Záró dátum** mezőben.
    * Adja meg az értékesítési rendelések utolsó dátumát, például a *2015.03.31.* dátumot.  
4. Adjon meg egy dátumot a **Kezdő dátum** mezőben.
    * Adja meg a *2015.04.01.* dátumot. Ezt a napot automatikusan a következő előrejelzési időszak kezdő dátumaként használja majd a rendszer.  
5. Bontsa ki a **Szerepeltetni kívánt rekordok** szakaszt.
6. Válassza ki a **Szűrő** elemet.
7. A listában jelölje meg a kiválasztott sort.
    * Jelölje meg a sort, ahol a **Mező** = *Vállalatközi tervezési csoport*.  
8. Adjon meg egy értéket a **Feltétel** mezőben.
    * Adja meg az első feladatnál használt vállalatközi tervezési csoportot (például a *10*-es számmal).  
9. Keresse meg és jelölje ki a kívánt rekordot a listán.
    * Válassza ki a sort, ahol **Mező** = *Cikkfelosztási kulcs*.  
10. Adjon meg egy értéket a **Feltétel** mezőben.
11. Válassza ki az **OK** lehetőséget.
12. Bontsa ki a **Haladó paraméterek** szakaszt.
13. Az **Előrejelzési időszak** mezőben válassza ki a *Hónap* lehetőséget.
14. Az **Előrejelzési horizont** mezőbe írja be a *3* értéket.
15. A **Befagyasztási időkorlát** mezőbe írja be az *1* értéket.
16. Válassza ki az **OK** lehetőséget.

## <a name="visualize-the-demand-forecast"></a>Igény-előrejelzés megjelenítése

1. Ugorjon az **Alaptervezés > Előrejelzés > Igény-előrejelzés > Módosított igény-előrejelzés** lehetőségre.
2. Az összesített nézet táblázatban válassza ki a cellát az 1. sor 2. oszlopában. Ez a második hónap, amelyhez előrejelzést hozott létre.
3. Állítsa a **QtyCell** értékét *400*-ra.
    * A cellában adjon meg egy másik számot, mint amit az előrejelzés mutatott, például: 400.  
4. Manuálisan helyesbítette az előrejelzést. Figyelje meg a grafikus jelölést a következő lépésben.
5. Válassza az **Előrejelzési sor részletei** lehetőséget.
    * Ezen a lapon láthatja a pontossági értékeket, igényekkel kapcsolatos előzményeket és előrejelzéseket. Az előrejelzéseket is módosíthatja.  

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]