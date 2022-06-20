---
title: Vállalatközi szállítólevelek
description: Ez a cikk azt ismerteti, hogyan lehet vállalatközi tranzakciókhoz csomagjegyzékeket generálni és nyomtatni.
author: Henrikan
ms.date: 09/01/2021
ms.topic: article
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 3516058bbf925df4b0a0c75286a3d97457cc1e69
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8900854"
---
# <a name="intercompany-packing-slips"></a>Vállalatközi szállítólevelek

## <a name="generate-intercompany-packing-slips"></a>Vállalatközi szállítólevelek létrehozása

[!include [banner](../../includes/banner.md)]

Ha közvetlen kiszállítást alkalmaz, a csomagjegyzéknek a vállalatközi értékesítési rendelésre történő létrehozása esetén mindig automatikusan létre lehet hozni szállítólevelet a vállalatközi beszerzési rendeléshez és az eredeti értékesítési rendeléshez. A vállalatközi beszerzési rendelés számlája a korábban létrehozott vállalatközi beszerzési rendelési szállítólevélen alapul.

A vállalatközi értékesítési rendelés csomagjegyzékének frissítésekor a változtatások megjelennek a vállalatközi beszerzési rendelésen és az eredeti értékesítési rendelésen is.

Ha nem alkalmazza a közvetlen kiszállítás funkciót, akkor a vállalatközi értékesítési rendelésre, a vállalatközi beszerzési rendelésre és az eredeti értékesítési rendelésre is kézzel kell létrehozni a szállítólevelet.

## <a name="print-intercompany-packing-slips"></a>Vállalatközi szállítólevelek nyomtatása

[!include [banner](../../includes/banner.md)]

Ha közvetlen kiszállítást alkalmaz, a szállítólevélnek a vállalatközi értékesítési rendelésre történő feladása esetén automatikusan ki lehet nyomtatni a csomagjegyzéket a vállalatközi beszerzési rendeléshez és az eredeti értékesítési rendeléshez.

Ha automatikusan szeretné kinyomtatni a szállítóleveleket, a beszerzési rendelések **Vállalatközi** lapján jelölje be mindkét **Szállítólevél automatikus nyomtatása** mezőt.

A vállalatközi értékesítési rendelés szállítólevelének frissítésekor a változtatások automatikusan megjelennek a vállalatközi beszerzési rendelésen és az eredeti értékesítési rendelésen is.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
