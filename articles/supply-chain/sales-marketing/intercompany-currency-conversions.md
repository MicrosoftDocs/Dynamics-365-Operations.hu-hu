---
title: Vállalatközi pénznem átváltása
description: Ez a témakör bemutatja a vállalatközi tranzakciók pénznemátváltásait
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
ms.openlocfilehash: f0af05c324bb67744ba6650e3d7a4ba8b958040e
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/03/2022
ms.locfileid: "8671898"
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
