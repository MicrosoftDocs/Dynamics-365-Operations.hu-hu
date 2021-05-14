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
ms.openlocfilehash: 69d22c3321beaa2667ee20bff00acd746714b993
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/20/2021
ms.locfileid: "5920531"
---
# <a name="create-sales-price-selection-criteria"></a>Eladási ár kiválasztási feltételeinek létrehozása

[!include [banner](../../includes/banner.md)]

Ez az eljárás bemutatja, hogyan hozhat létre eladási ár kiválasztási feltételeket az attribútumalapú eladásiár-modellekhez. Az eljáráshoz előfeltétel, hogy legyen legalább egy elérhető eladásiár-modell. Ebben a példában a hangszóró megoldás eladásiár-modelljének ármodelljét használjuk a USMF bemutatócég esetében. Ezt az eljárást általában a termékmenedzser használja.

## <a name="add-a-new-criterion-for-an-existing-sales-price-model"></a>Új feltétel hozzáadása a meglévő eladásiár-modellhez

1. Lépjen a **Termékinformáció-kezelés \> Termékek \> Termékkonfigurációs modellek** elemre.
1. A listában jelölje ki a hangszóró megoldás termékmodelljének a sorát, de ne kattintson rá a modell nevének hivatkozására.
1. A Műveleti ablaktáblán kattintson a **Modell** elemre.
1. Válassza ki az **Ármodellfeltételek** lehetőséget.
1. Válassza az **Új** lehetőséget.
1. A **Név** mezőbe írja be a „10. vásárlócsoport” szöveget.
    * Az ármodellfeltétel nevének a használata segít azonosítani az alapul szolgáló kiválasztási feltételeket.  
1. Az **Ármodell** mezőben adjon meg vagy válasszon ki egy értéket.
1. A **Rendeléstípus** mezőben válassza ki az *Értékesítési rendelés* elemet.
    * A rendelés típusa határozza meg, hogy az adatbázis mely mezői állnak rendelkezésre a kiválasztási lekérdezéshez.  
1. Adja meg a dátumot az **Érvényesség kezdete** mezőben.
1. Az **Érvényesség vége** mezőben adjon meg egy dátumot.
1. Válassza a **Mentés** lehetőséget.

## <a name="create-the-query-for-the-selection-criteria"></a>A lekérdezés létrehozása a kiválasztási feltételekhez

1. Válassza ki a **Szerkesztés** opciót.
2. Válasszon ki **Vevőket** a *Tábla* mezőben.
3. A **Mező** mezőben válassza ki a *Vevőcsoportot*.
    * Ebben a példában egy bizonyos vevőcsoportot fogunk használni kiválasztási feltételnek.  
4. A **Feltétel** mezőben válassza ki a *10. vevőcsoportot*.
5. Válassza ki az **OK** lehetőséget.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]