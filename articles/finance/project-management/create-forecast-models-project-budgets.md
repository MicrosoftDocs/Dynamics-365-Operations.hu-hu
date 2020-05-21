---
title: Előrejelzési modellek létrehozása projektköltségvetésekhez
description: Ez a témakör azt mutatja be, hogyan lehet előrejelzési modellt létrehozni a fennmaradó költségvetésekhez.
author: RadhikaRS
manager: AnnBe
ms.date: 04/24/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Service industries
ms.author: v-radsh
ms.dyn365.ops.version: 7
ms.search.validFrom: 2019-01-15
ms.openlocfilehash: 07e540f23a668b40a54906a67d87552fe991825a
ms.sourcegitcommit: 5de75c61c33e57c813944f1ab6100aceb020d432
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/29/2020
ms.locfileid: "3321779"
---
# <a name="create-forecast-models-for-project-budgets"></a>Előrejelzési modellek létrehozása projektköltségvetésekhez 

[!include [banner](../includes/banner.md)]

Ez a témakör azt mutatja be, hogyan lehet előrejelzési modellt létrehozni a fennmaradó költségvetésekhez. A költségvetési ellenőrzés tárgyát képező projektekhez a költségvetések két típusa használható: az eredeti és a fennmaradó. A projektköltségvetések létrehozásakor meg kell adnia az eredeti és a fennmaradó költségvetés előrejelzési modelljeit, amelyek az **Előrejelzési modellek** oldalon lettek létrehozva. A megadott modelleken alapuló projektköltségvetések a projektköltségvetés véglegesítésekor jönnek létre.

> [!NOTE]
> A költségvetés-ellenőrzéshez használt előrejelzési modellekhez nem tartozhatnak részmodellek, illetve ezek a modellek részmodellként sem használhatók.

1. Válassza ki a **Projektvezetés és a könyvelés** > **Beállítás** > **Előrejelzések**  > **Előrejelzési modellek** lehetőséget.
2. Válassza az **Új** elemet egy új előrejelzési modell létrehozásához, majd adja meg az új modell azonosítószámát és nevét. 
3. Állítsa a **Leállítva** beállítást **Igen** értékre előrejelzés soraiban történt módosítások megakadályozása érdekében. 
4. Ha a modellhez rendelt előrejelzési soroknak pénzforgalmi előrejelzéseket kell létrehozniuk a főkönyvben, állítsa az **Költségvetések szerepeltetése pénzforgalmi előrejelzésekben** **Igen** értékre. 
5. Ha azt szeretné, hogy a projekt dátuma a számla dátuma legyen, akkor az **Előrejelzési számladátum** beállítást állítsa **Igen** értékre. 
6. A **Költségvetés típusa** mezőben jelöljön ki egyet a következő modelltípusok közül:

   - **Eredeti költségvetés** Az eredeti költségvetési összegek használata, amelyek a kezdeti költségvetés létrehozásakor és jóváhagyásakor véglegesíthetők.
   - **Fennmaradó költségvetés**: A fennmaradó költségvetési összegek felhasználása a projekt élettartama során. Ebben az előrejelzési modellben a tényleges tranzakciók csökkentik, a költségvetés-verziók pedig növelik vagy csökkentik az egyenlegeket.
   - **Átvitel**: A projekt áthozott költségvetési összegeinek használata. Az átvitel egy választható folyamat, amelynek futtatásával a nem használt költségvetési összegek átvihetők egyik pénzügyi évből a másikba.

7. Szükség szerint adja meg a következő beállításokat:

   - Ha azt szeretné, hogy a projekt dátuma a számla dátuma legyen, akkor engedélyezze az **Előrejelzési számladátum** beállítást.
   - Engedélyezze az **Előrejelzés befejezetlen termeléssel** a z előrejelzéshez folyamatban lévő munkák (WIP) alapján, majd válassza ki a WIP típusát. 
   - Az alapértelmezett **Költségvetési típust** **Nem** értéken hagyhatja vagy megadhat egy új típust is. A költségvetés típusa nem módosítható egy rekord módosítása után.     
    > [!NOTE]
    > Ha módosítja az alapértelmezett költségvetéstípust, akkor semmilyen további beállítás nem lesz elérhető a frissítésekhez, és ezt az előrejelzési modellt nem lehet újra felhasználni. 
   


 

