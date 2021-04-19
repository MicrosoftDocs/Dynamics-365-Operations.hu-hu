---
title: Az online rendelések adói helytelenül vannak kiszámítva
description: Ez a témakör olyan hibaelhárítási útmutatást tartalmaz, amely segítséget jelenthet az online rendelések adójának helytelen kiszámítása vagy az értékesítési sorban beállított áfacsoport helytelen beállítása esetén.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 7f71add679e1d24f80db8ce3990058b591128ec1
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5801411"
---
# <a name="taxes-on-online-orders-are-incorrectly-calculated"></a>Az online rendelések adói helytelenül vannak kiszámítva

[!include [banner](../../includes/banner.md)]

Ez a témakör olyan hibaelhárítási útmutatást tartalmaz, amely segítséget jelenthet az online rendelések adójának helytelen kiszámítása vagy az értékesítési sorban beállított áfacsoport helytelen beállítása esetén.

## <a name="description"></a>Leírás

Az e-kereskedelmi rendelések leadása esetén a program helytelenül számítja ki az adót, vagy helytelenül van beállítva az értékesítési sorban beállított áfacsoport.

## <a name="resolution"></a>Felbontás

### <a name="configure-the-sales-tax-for-a-retail-store-in-commerce-headquarters"></a>Kiskereskedelmi áruház áfájának konfigurálása a Commerce központi felületén

Egy kiskereskedelmi áruház áfájának konfigurálásához a Commerce központi felületén kövesse ezeket a lépéseket.

1. Ugorjon a következő oldalra: **Retail és Commerce \> Csatornák \> Minden üzlet**.
1. Válassza ki azt az üzletet, amelyhez konfigurálni akarja az áfát.
1. Az **Általános** gyorslapon az **Áfa** részben konfigurálja az üzlet áfainformációit.

> [!NOTE]
> Termék üzletből való felvétele esetén az áfacsoport a felvételre kiválasztott üzletből származik. További információk: [Üzletek egyéb adóbeállításainak megadása](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-other-tax-options-for-stores).

### <a name="configure-the-sales-tax-for-a-customers-address-in-commerce-headquarters"></a>Ügyfél címéhez kapcsolódó áfa konfigurálása a Commerce központi felületén

Egy ügyfél címéhez kapcsolódó áfa konfigurálásához a Commerce központi felületén kövesse ezeket a lépéseket.

1. Nyissa meg a **Kinnlevőségek \> Vevők \> Minden vevő** lehetőséget.
1. Válassza ki azt a vevőt, amelyhez áfát szeretne konfigurálni.
1. A **Címek** gyorslapon válassza ki azt a címet, amelyhez áfát szeretne konfigurálni, válassza ki a **További beállítások** lehetőséget, majd válassza a **Speciális** lehetőséget.
1. Az **Általános** gyorslapon válassza az **Áfacsoport** lehetőséget.
1. Válassza ki a megfelelő értéket az **Áfa** mezőben.

> [!NOTE]
> Olyan szállítások esetén, amelyek a vevő címéhez kapcsolódóan áfát tartalmaznak, a sor szállítási címe határozza meg a sor áfacsoportját. Ha a vevő olyan létező címre szállít, amelyhez már konfigurált áfacsoport tartozik, a rendszer a meglévő áfacsoportot használja. A címek alapértelmezés szerint létrehozáskor nem rendelkeznek áfacsoporttal.

### <a name="configure-general-sales-tax-groups-in-commerce-headquarters"></a>Általános áfacsoportok konfigurálása a Commerce központi felületén

Az általános áfacsoportok Commerce központi felületén történő konfigurálásához kövesse az alábbi lépéseket.

1. Ugorjon az **Adó \> Közvetett adók \> Áfa \> Áfakódcsoportok** pontra.
1. A bal oldali navigációs részben válassza ki a konfigurálni kívánt áfacsoportot.
1. A **Kiskereskedelmi célalapú adó** gyorslapon konfigurálja az áfacsoport adóit.

> [!NOTE]
> Olyan szállítások esetén, amelyek nem tartalmaznak áfát a vevő címében, a sor szállítási címe és az áfacsoporthoz beállított célalapú adók határozzák meg az áfacsoportot. További információ: [Online áruházak adóinak beállítása cél alapján](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-taxes-for-online-stores-based-on-destination) című témakörben olvashat.

## <a name="additional-resources"></a>További erőforrások

[Az online rendelések áfájának konfigurálása](../sales-tax-config.md)
