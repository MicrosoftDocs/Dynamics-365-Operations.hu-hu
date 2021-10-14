---
title: Termékszám elnevezési rendszerének létrehozása konfigurált termékváltozatokhoz
description: Ez az eljárás bemutatja, hogyan állítható be termékszámozás-elnevezési rendszer konfigurált termékváltozatok számára, és hogyan rendelhető hozzá konfigurálható alaptermékhez.
author: t-benebo
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, EcoResNomenclature, EcoResProductListPage, EcoResProductDetails, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7711d9832288327e700acd47fb30cce0c76e5e9a
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/29/2021
ms.locfileid: "7568399"
---
# <a name="create-a-product-number-nomenclature-for-configured-product-variants"></a>Termékszám elnevezési rendszerének létrehozása konfigurált termékváltozatokhoz

[!include [banner](../../includes/banner.md)]

Ez az eljárás bemutatja, hogyan állítható be termékszámozás-elnevezési rendszer konfigurált termékváltozatok számára, és hogyan rendelhető hozzá konfigurálható alaptermékhez. Az eljárás emellett bemutatja, hogyan készíthető konfigurációelnevezési rendszer termékkonfigurációs modell összetevőjéhez. Ez az eljárás az USMF bemutatócéget használja. Az új termékszám-elnevezési rendszer a D0004 alaptermékhez van rendelve. Ezt a feladatot általában egy terméktervező végzi.

## <a name="create-a-product-number-nomenclature"></a>Termékszámozási rendszer létrehozása

1. Ugorjon a **Termékinformációk kezelése \> Beállítás \> Termék elnevezési rendszere** lehetőségre.
1. Válassza az **Új** lehetőséget.
1. Írjon be egy értéket a **Név** mezőbe.
1. Írjon egy értéket a **Leírás** mezőbe.
1. Válassza a **Hozzáadás** lehetőséget.
1. Válassza az **Alaptermék száma** lehetőséget.
1. Válassza a **Hozzáadás** lehetőséget.
1. Válassza a **Szöveges állandó** elemet.
1. A listában jelölje meg a kiválasztott sort.
1. Írjon be egy értéket a **Szöveg** mezőbe.
1. Válassza a **Hozzáadás** lehetőséget.
1. **Konfiguráció** kiválasztása.
1. Zárja be a lapot.

## <a name="assign-the-product-number-nomenclature-to-a-product-master"></a>Termékszámozási rendszer hozzárendelése az alaptermékhez

1. Ugorjon a **Termékinformációk kezelése \> Termékek \> Alaptermékek** lehetőségre.
1. Rekordok kereséséhez használja a gyorsszűrőt. Például szűkítsen a **Termékszám** mezőre a „D” értéket beírva.
1. A listában válassza ki a kiválasztott sorból a hivatkozást.
1. Válassza ki a **Szerkesztés** opciót.
1. Válassza az *Igen* lehetőséget az **Elnevezési rendszer használata** mezőben.
1. A **Termékváltozat-számozási rendszer** mezőben adjon meg, vagy válasszon ki egy értéket.
1. Zárja be a lapot.
1. Zárja be a lapot.

## <a name="create-nomenclature-for-a-product-configuration-model-component"></a>Elnevezési rendszer létrehozása egy termékkonfigurációs modell összetevőjéhez

1. Lépjen a **Termékinformáció-kezelés \> Termékek \> Termékkonfigurációs modellek** elemre.
1. Keresse meg és jelölje ki a kívánt rekordot a listán.
1. A listában válassza ki a kiválasztott sorból a hivatkozást.
1. Válassza ki a **Szerkesztés** opciót.
1. Válassza az *Igen* lehetőséget a **Konfiguráció elnevezési rendszerének használata** mezőben.
1. Válassza a **Hozzáadás** lehetőséget.
1. Válassza az **Attribútumérték** lehetőséget.
1. A listában jelölje meg a kiválasztott sort.
1. Az **Attribútum** mezőben adjon meg vagy válasszon ki egy értéket.
1. Válassza a **Hozzáadás** lehetőséget.
1. Válassza a **Szöveges állandó** elemet.
1. A listában jelölje meg a kiválasztott sort.
1. Írjon be egy értéket a **Szöveg** mezőbe.
1. Válassza a **Hozzáadás** lehetőséget.
1. Válassza az **Attribútumérték** lehetőséget.
1. A listában jelölje meg a kiválasztott sort.
1. Az **Attribútum** mezőben adjon meg vagy válasszon ki egy értéket.
1. Válassza a **Hozzáadás** lehetőséget.
1. Válassza a **Szöveges állandó** elemet.
1. A listában jelölje meg a kiválasztott sort.
1. Írjon be egy értéket a **Szöveg** mezőbe.
1. Válassza a **Hozzáadás** lehetőséget.
1. Válassza az **Attribútumérték** lehetőséget.
1. A listában jelölje meg a kiválasztott sort.
1. Az **Attribútum** mezőben adjon meg vagy válasszon ki egy értéket.
1. Válassza a **Hozzáadás** lehetőséget.
1. Válassza a **Szöveges állandó** elemet.
1. A listában jelölje meg a kiválasztott sort.
1. Írjon be egy értéket a **Szöveg** mezőbe.
1. Válassza a **Hozzáadás** lehetőséget.
1. Válassza az **Attribútumérték** lehetőséget.
1. A listában jelölje meg a kiválasztott sort.
1. Az **Attribútum** mezőben adjon meg vagy válasszon ki egy értéket.
1. Válassza a **Hozzáadás** lehetőséget.
1. Válassza a **Szöveges állandó** elemet.
1. A listában jelölje meg a kiválasztott sort.
1. Írjon be egy értéket a **Szöveg** mezőbe.
1. Válassza a **Hozzáadás** lehetőséget.
1. Válassza ki a **Számsorozat értéke** elemet.
1. A listában jelölje meg a kiválasztott sort.
1. A **Számsorrend** mezőben adjon meg vagy válasszon ki egy értéket.
1. Zárja be a lapot.
1. Zárja be a lapot.
1. Zárja be a lapot.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]