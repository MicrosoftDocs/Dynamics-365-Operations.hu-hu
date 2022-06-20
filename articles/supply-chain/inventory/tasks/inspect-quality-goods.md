---
title: Áru minőségének ellenőrzése
description: Ez a témakör a minőségi rendelések feldolgozását ismerteti.
author: yufeihuang
ms.date: 03/23/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: InventQualityOrderTable, InventQualityOrderLineResults, HcmWorkerLookUp
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: eeb14a3b0a61f34819bdd8d524e65ac214a81c35
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8857576"
---
# <a name="inspect-the-quality-of-goods"></a>Áru minőségének ellenőrzése

[!include [banner](../../includes/banner.md)]

Ez a témakör a minőségi rendelések feldolgozását ismerteti. A minőségvizsgálatokat általában minőségadminisztrátorok végzik.

Ha telepítve vannak a szabványos bemutatóadatok, akkor az ebben a cikkben olvasható eljárásokat lehet használni. A bemutatóadatok használatához az *USMF* jogi személyt is ki kell választani a kezdés előtt. Ezt követően meg kell erősítenie a *000016-os* beszerzési rendelést, és fel kell adnia egy terméknyugtát. A minőségi rendelések automatikusan létre vannak hozva.

## <a name="step-1-select-a-quality-order"></a>1. lépés: Minőségi rendelés kiválasztása

A minőségi rendelés kiválasztásához kövesse az alábbi lépéseket.

1. Ugorjon a **Készletkezelés \> Időszakos feladatok \> Minőségkezelés \> Minőségi rendelések** lehetőségre.
1. Válassza ki az eljárás megkezdése előtt létrehozott minőségi rendelést.

## <a name="step-2-record-test-results"></a>2. lépés: Teszteredmények rögzítése

A teszteredmények rögzítéséhez kövesse az alábbi lépéseket.

1. Válassza az **Eredmények** lehetőséget.
1. Válassza ki a **Szerkesztés** opciót.
1. Az **Eredmény mennyisége** mezőben adjon meg egy számot.
1. A **Kimenet** mezőben válassza ki a rekordot. Ebben a példában az eredmény egy előre meghatározott eredményen alapul. Általában speciálisabb teszteredményeket rögzít majd, például egy méretet vagy más dimenziót.
1. Válassza a **Mentés** lehetőséget.
1. Zárja be a lapot.

## <a name="step-3-validate-the-quality-order"></a>3. lépés: A minőségi rendelés ellenőrzése

A minőségi rendelés ellenőrzéséhez kövesse az alábbi lépéseket.

1. A **Validálás** kiválasztása.
1. Az **Ellenőrzést végezte** mezőben válassza ki azt a felhasználót, aki az ellenőrzést elvégezte.
1. Válassza ki a **Kiválasztás** lehetőséget.
1. Válassza ki az **OK** lehetőséget.
1. Zárja be a lapot.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
