--- 
title: "Fuvarlevél egyeztetése manuálisan"
description: "Ez az eljárás bemutatja, hogyan lehet manuálisan elvégezni a fuvaregyeztetést."
author: BibiSp
manager: AnnBe
ms.date: 10/13/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 9b947a02be981155053e33a4ef20e19bf2a194a5
ms.openlocfilehash: 28de4c720cd771f476f379d925e9500e41482aa6
ms.contentlocale: hu-hu
ms.lasthandoff: 07/27/2017

---
# <a name="reconcile-freight-manually"></a>Fuvarlevél egyeztetése manuálisan

[!include[task guide banner](../../includes/task-guide-banner.md)]

Ez az eljárás bemutatja, hogyan lehet manuálisan elvégezni a fuvaregyeztetést. Ezt általában egy szállítási koordinátor végzi. Az USMF bemutatócég adataiban használhatja ezt az eljárást.


## <a name="select-a-load-to-reconcile"></a>Válassza ki a rakományt az egyeztetéshez
1. Ugorjon a Szállításkezelés > Tervezés > Rakománytervező munkaterület elemre.
2. Törölje a Szállított és bevételezett elrejtése jelölőnégyzet jelölését. 
3. A listában jelölje ki a rakományt, amelynek a rakományazonosítója 00006.

## <a name="create-a-carrier-invoice"></a>Szállítói számla létrehozása
    * Ha manuálisan végzi a fuvaregyeztetést, és nem kapja meg automatikusan a szállítói számlákat, a fuvarlevél alapján számlát hozhat létre.  
1. Kattintson a Kapcsolódó információ lehetőségre.
2. Kattintson a Fuvarlevél részletei lehetőségre.
3. Kattintson a Fuvarlevélszámla generálása lehetőségre.
4. Érték beírása a Számla mezőbe.
5. Kattintson az OK gombra.

## <a name="reconcile-the-invoice"></a>Számla egyeztetése
    * Ha a fuvarlevél és a szállítói számla egyeztetését végzi, ez soronként történik.  
1. Kattintson a Fuvarlevelek és számlák egyeztetése lehetőségre.
2. Bontsa ki a Számla részletei szakaszt.
3. Bontsa ki a Nem egyeztetett fuvarlevél-adatok szakaszt.
4. A listában jelölje meg a kiválasztott sort.
5. Kattintson az Egyeztetés lehetőségre.
6. Bontsa ki az Egyeztetett fuvarlevél-adatok szakaszt.

## <a name="submit-the-invoice-for-approval"></a>A számla elküldése jóváhagyásra
1. Kattintson az Elküldés jóváhagyásra elemre.
2. Zárja be a lapot.
3. Szüntesse meg a Jóváhagyott elrejtése jelölőnégyzet bejelölését. 
4. Kattintson a Szállítói számlanaplók elemre.
5. Kattintson a Hivatkozási naplószám mezőben található hivatkozás megnyitásához.
6. Kattintson a Sorok pontra.


