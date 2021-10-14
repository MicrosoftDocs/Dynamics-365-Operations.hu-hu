---
title: Vállalatközi pénznem átváltása
description: Ez a témakör bemutatja a vállalatközi tranzakciók pénznemátváltásait
author: GalynaFedorova
ms.date: 09/01/2021
ms.topic: article
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 540849003d532ef2f0905c18332d9cb82a04cf7c
ms.sourcegitcommit: fcfd85a508c0de52cfe11d1986892219e39ef406
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/23/2021
ms.locfileid: "7548318"
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
