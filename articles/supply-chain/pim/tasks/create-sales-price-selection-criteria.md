---
title: Eladási ár kiválasztási feltételeinek létrehozása
description: Ez az eljárás bemutatja, hogyan hozhat létre eladási ár kiválasztási feltételeket az attribútumalapú eladásiár-modellekhez.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCPriceModelSelectionCriteria, SysQueryForm, SysQueryTableLookUp, SysQueryFieldLookUp
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5a616dcfdd755efc9bf0473e9239acb9127f11f8
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5818157"
---
# <a name="create-sales-price-selection-criteria"></a>Eladási ár kiválasztási feltételeinek létrehozása

[!include [banner](../../includes/banner.md)]

Ez az eljárás bemutatja, hogyan hozhat létre eladási ár kiválasztási feltételeket az attribútumalapú eladásiár-modellekhez. Az eljáráshoz előfeltétel, hogy legyen legalább egy elérhető eladásiár-modell. Ebben a példában a hangszóró megoldás eladásiár-modelljének ármodelljét használjuk a USMF bemutatócég esetében. Ezt az eljárást általában a termékmenedzser használja.


## <a name="add-a-new-criterion-for-an-existing-sales-price-model"></a>Új feltétel hozzáadása a meglévő eladásiár-modellhez
1. Kattintson a Termékváltozat modelldefinícióra.
2. Kattintson a Termékkonfigurációs modellek lehetőségre.
3. A listában jelölje ki a hangszóró megoldás termékmodelljének a sorát, de ne kattintson a modell nevének hivatkozására.
4. A Művelet panelen kattintson a Modell elemre.
5. Kattintson az Ármodellfeltételek lehetőségre.
6. Kattintson az Új elemre.
7. A Név mezőbe írja be a „10. vásárlócsoport” szöveget.
    * Az ármodellfeltétel nevének a használata segít azonosítani az alapul szolgáló kiválasztási feltételeket.  
8. Az Ármodell mezőben adjon meg vagy válasszon ki egy értéket.
9. A Rendeléstípus mezőben válassza ki az Értékesítési rendelés elemet.
    * A rendelés típusa határozza meg, hogy az adatbázis mely mezői állnak rendelkezésre a kiválasztási lekérdezéshez.  
10. Adja meg a dátumot az Érvényesség kezdete mezőben.
11. Az Érvényesség vége mezőben adjon meg egy dátumot.
12. Kattintson a Mentés gombra.

## <a name="create-the-query-for-the-selection-criteria"></a>A lekérdezés létrehozása a kiválasztási feltételekhez
1. Kattintson a Szerkesztés lehetőségre.
2. Válasszon ki vevőket a Tábla mezőben. 
3. A Mező mezőben válassza ki a Vevőcsoportot.
    * Ebben a példában egy bizonyos vevőcsoportot fogunk használni kiválasztási feltételnek.  
4. A Feltétel mezőben válassza ki a 10. vevőcsoportot. 
5. Kattintson az OK gombra.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]