---
title: Az online rendelések adói helytelenül vannak kiszámítva
description: Ez a témakör olyan hibaelhárítási útmutatást tartalmaz, amely segítséget jelenthet az online rendelések adójának helytelen számítása vagy az értékesítési sorban beállított adócsoport helytelen beállítása esetén.
author: Reza-Assadi
ms.date: 02/16/2022
ms.topic: Troubleshooting
ms.prod: ''
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
ms.openlocfilehash: eefcfc983a7b3861caa4b4362d2813082b7963a6
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8901621"
---
# <a name="taxes-on-online-orders-are-incorrectly-calculated"></a>Az online rendelések adói helytelenül vannak kiszámítva

[!include [banner](../../includes/banner.md)]

Ez a témakör olyan hibaelhárítási útmutatást tartalmaz, amely segítséget jelenthet az online rendelések adójának helytelen számítása vagy az értékesítési sorban beállított adócsoport helytelen beállítása esetén.

## <a name="description"></a>Leírás

Az e-kereskedelmi rendelések leadása esetén a program helytelenül számítja ki az adót, vagy helytelenül van beállítva az értékesítési sorban beállított áfacsoport.

## <a name="resolution"></a>Megoldás

### <a name="configure-general-sales-tax-groups-in-commerce-headquarters"></a>Általános áfacsoportok konfigurálása a Commerce központi felületén

Az általános áfacsoportok Commerce központi felületén történő konfigurálásához kövesse az alábbi lépéseket.

1. Ugorjon az **Adó \> Közvetett adók \> Áfa \> Áfakódcsoportok** pontra.
1. A bal oldali navigációs ablakban válassza ki a konfigurálni kívánt adócsoportot.
1. A **Kiskereskedelmi célalapú adó** gyorslapon konfigurálja az áfacsoport adóit.

> [!NOTE]
> Olyan szállítás esetén, amely nem tartalmaz áfás adót, amelyet a vevő címe határoz meg, a sor szállítási címe és az adócsoporthoz beállított célon alapuló adók határozzák meg az áfacsoportot. További információ: [Online áruházak adóinak beállítása cél alapján](/dynamicsax-2012/appuser-itpro/set-up-taxes-for-online-stores-based-on-destination) című témakörben olvashat.

### <a name="configure-the-sales-tax-for-a-retail-store-in-commerce-headquarters"></a>Kiskereskedelmi áruház áfájának konfigurálása a Commerce központi felületén

Egy kiskereskedelmi áruház áfájának konfigurálásához a Commerce központi felületén kövesse ezeket a lépéseket.

1. Ugorjon a következő oldalra: **Retail és Commerce \> Csatornák \> Minden üzlet**.
1. Válassza ki azt az üzletet, amelyhez konfigurálni akarja az áfát.
1. Az **Általános** gyorslapon az **Áfa** részben konfigurálja az üzlet áfainformációit.

> [!NOTE]
> Termék üzletből való felvétele esetén az áfacsoport a felvételre kiválasztott üzletből származik. További információk: [Üzletek egyéb adóbeállításainak megadása](/dynamicsax-2012/appuser-itpro/set-other-tax-options-for-stores).

### <a name="configure-the-sales-tax-for-a-customers-address-in-commerce-headquarters"></a>Ügyfél címéhez kapcsolódó áfa konfigurálása a Commerce központi felületén

Egy ügyfél címéhez kapcsolódó áfa konfigurálásához a Commerce központi felületén kövesse ezeket a lépéseket.

1. Nyissa meg a **Kinnlevőségek \> Vevők \> Minden vevő** lehetőséget.
1. Válassza ki azt a vevőt, amelyhez áfát szeretne konfigurálni.
1. A **Címek** gyorslapon válassza ki azt a címet, amelyhez áfát szeretne konfigurálni, válassza ki a **További beállítások** lehetőséget, majd válassza a **Speciális** lehetőséget.
1. Az **Általános** gyorslapon válassza az **Áfacsoport** lehetőséget.
1. Válassza ki a megfelelő értéket az **Áfa** mezőben.

> [!NOTE]
> Olyan szállítások esetén, amelyek a vevő címéhez kapcsolódóan áfát tartalmaznak, a sor szállítási címe határozza meg a sor áfacsoportját. Ha a vevő olyan létező címre szállít, amelyhez már konfigurált áfacsoport tartozik, a rendszer a meglévő áfacsoportot használja. A címek alapértelmezés szerint létrehozáskor nem rendelkeznek áfacsoporttal.

## <a name="additional-resources"></a>További erőforrások

[Az online rendelések áfájának konfigurálása](../sales-tax-config.md)
