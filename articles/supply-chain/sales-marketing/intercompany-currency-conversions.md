---
title: Vállalatközi pénznem átváltása
description: Ez a cikk bemutatja a vállalatközi tranzakciók pénznemátváltását.
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
ms.openlocfilehash: 41bfafc0dcb3bd356931b67dc63b717c0d098116
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8851478"
---
# <a name="intercompany-currency-conversions"></a>Vállalatközi pénznem átváltása

[!include [banner](../../includes/banner.md)]

Ha az eredeti értékesítési rendelés és a vállalatközi beszerzési rendelés pénznemkódja eltér és a szinkronizálás engedélyezve van, akkor a program átváltja a következő mezők értékét az eltérő pénznemre.

- **Egységár**
- **Értékesítési költségek** vagy **Beszerzések költségei**
- **Kedvezmény**
- **Többsoros kedvezmény**

Ezek a mezők ezután szinkronizálva lesznek a vállalatközi értékesítési rendeléssorral.

Mivel a vállalatközi beszerzési rendelés és a vállalatközi értékesítési rendelés pénzneme mindig szinkronizált, ezért a következő mezők szinkronizálásakor nincs szükség átváltásra:

- **Egységár**
- **Értékesítési költségek** vagy **Beszerzések költségei**
- **Kedvezmény**
- **Engedményszázalék**
- **Többsoros kedvezmény**
- **Többsoros kedvezmény százaléka**

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
