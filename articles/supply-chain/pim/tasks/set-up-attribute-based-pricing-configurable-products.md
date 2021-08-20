---
title: Állítsa be a konfigurálható termékek attribútum-alapú árképzését
description: Ez a témakör azt ismerteti, hogyan állítható be az attribútumalapú árképzés.
author: ShylaThompson
ms.date: 08/20/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCPriceModelList, PCPriceModel, PCConstraintEditor
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5abb2e7dc33b46589c1a3699e70b56af6f694aed49294eb81a2122db6d414a96
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6743554"
---
# <a name="set-up-attribute-based-pricing-for-configurable-products"></a>Állítsa be a konfigurálható termékek attribútum-alapú árképzését

[!include [banner](../../includes/banner.md)]

Ez a témakör azt ismerteti, hogyan állítható be az attribútumalapú árképzés. Előfeltételként rendelkeznie kell egy olyan termékkonfigurációs modellel, amelynek egy vagy több összetevője és attribútuma van. Ebben a példában a High End hangszóró termékmodellt használjuk a USMF bemutatócég esetében. Ezt az eljárást általában a termékmenedzser használja.


## <a name="create-a-new-price-model"></a>Új ármodell létrehozása

1. Lépjen a **Termékinformáció-kezelés \> Termékek \> Termékkonfigurációs modellek** elemre.
1. A listában válassza ki a **High End hangszóró** sort, de ne válassza ki a név hivatkozását.
1. A Műveleti ablaktáblán kattintson a **Modell** elemre.
1. Válassza ki az **Ármodellek** lehetőséget.
1. Válassza az **Új** lehetőséget.
1. Írjon be egy értéket az **Ármodell neve** mezőbe. Olyan nevet használjon, amelyik könnyen azonosíthatóvá teszi a modellt.  
1. Írjon egy értéket a **Leírás** mezőbe.
1. Válassza a **Mentés** lehetőséget.

## <a name="add-price-elements"></a>Árelem hozzáadása

1. Válassza ki a **Szerkesztés** opciót. A termékmodell minden egyes összetevőjéhez tartozhat egy alapár elem és tetszőleges számú árkifejezés-szabály. Különböző pénznemben szereplő árak is hozzáadhatók.  
2. Írjon be egy értéket az **Alapár kifejezése** mezőbe. Például írja be a „100” értéket. Az alapár kifejezése numerikus érték lehet, vagy számítás, amely magában foglal egy vagy több attribútumot.  
3. Válassza a **Hozzáadás** lehetőséget.
4. A **Név** mezőbe írja be a `Rosewood` kifejezést. Az árkifejezés neve azt segít azonosítani, amit az ár elem jelöl. Ebben a példában ár elemet hozunk létre a Rosewood hangszórókabinet befejezés opciójához.  
5. Válassza ki a **Szerkesztési feltétel** lehetőséget. Ár feltétel segít garantálni, hogy az eladási árnak csak akkor legyen része az árkifejezés elem, ha jelen van az attribútumok egyedi kombinációja.  
6. A **ConstraintBody** mezőben adja meg a `CabinetFinish=="Rosewood"` értéket.
7. Válassza ki az **OK** lehetőséget.
8. Adjon meg egy értéket a **Kifejezés** mezőben. Például írja be a `50` értéket. 
9. Zárja be a lapot.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]