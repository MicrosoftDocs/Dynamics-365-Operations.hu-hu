--- 
title: "Állítsa be a konfigurálható termékek attribútum-alapú árképzését"
description: "Ez az eljárás bemutatja, hogyan állítható be az attribútumalapú árképzés."
author: ShylaThompson
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCPriceModelList, PCPriceModel, PCConstraintEditor
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 88402bef6fd5dad38a74795cd31a4046085d6db7
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="set-up-attribute-based-pricing-for-configurable-products"></a>Állítsa be a konfigurálható termékek attribútum-alapú árképzését

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ez az eljárás bemutatja, hogyan állítható be az attribútumalapú árképzés. Előfeltételként rendelkeznie kell egy olyan termékkonfigurációs modellel, amelynek egy vagy több összetevője és attribútuma van. Ebben a példában a High End hangszóró termékmodellt használjuk a USMF bemutatócég esetében. Ezt az eljárást általában a termékmenedzser használja.


## <a name="create-a-new-price-model"></a>Új ármodell létrehozása
1. Kattintson a Termékváltozat modelldefinícióra.
2. Kattintson a Termékkonfigurációs modellek lehetőségre.
3. A listában válassza ki a High End hangszóró sort, de ne kattintson a név hivatkozására.
4. A Művelet panelen kattintson a Modell elemre.
5. Kattintson az Ármodellek lehetőségre.
6. Kattintson az Új lehetőségre.
7. Írjon be egy értéket az Ármodell neve mezőbe.
    * Olyan nevet használjon, amelyik könnyen azonosíthatóvá teszi a modellt.  
8. A Leírás mezőben adjon meg egy értéket.
9. Kattintson a Mentés gombra.

## <a name="add-price-elements"></a>Árelem hozzáadása
1. Kattintson a Szerkesztés lehetőségre.
    * A termékmodell minden egyes összetevőjéhez tartozhat egy alapár elem és tetszőleges számú árkifejezés-szabály. Különböző pénznemben szereplő árak is hozzáadhatók.  
2. Írjon be egy értéket az Alapár kifejezése mezőbe.
    * Például írja be a „100” értéket.   Az alapár kifejezése numerikus érték lehet, vagy számítás, amely magában foglal egy vagy több attribútumot.  
3. Kattintson a Hozzáadás gombra.
4. A Név mezőbe írja be a „Rosewood” szót.
    * Az árkifejezés neve azt segít azonosítani, amit az ár elem jelöl. Ebben a példában ár elemet hozunk létre a Rosewood hangszórókabinet befejezés opciójához.  
5. Kattintson a Feltétel szerkesztése elemre.
    * Ár feltétel segít garantálni, hogy az eladási árnak csak akkor legyen része az árkifejezés elem, ha jelen van az attribútumok egyedi kombinációja.  
6. A ConstraintBody mezőbe írja be a következőt: CabinetFinish=="Rosewood".
7. Kattintson az OK gombra.
8. A Kifejezés mezőben adjon meg egy értéket.
    * Például írja be a „50” értéket.  
9. Zárja be a lapot.
10. Zárja be a lapot.


