---
title: Nem lehet érvényteleníteni egy értékesítési rendeléshez kapcsolódó vállalatközi beszerzési rendelést
description: A Microsoft Dynamics 365 Supply Chain Management 10.0.13-as verziójában és a későbbi verziókban már érvényteleníteni lehet egy értékesítési rendeléshez kapcsolódó vállalatközi beszerzési rendelést.
author: SmithaNataraj
ms.date: 06/24/2021
ms.topic: troubleshooting
ms.search.form: SalesTable, SalesTableListPage, SalesTableListPage_SalesCancelOrder
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 5041ef377d9bf2c21e191c3cf1950f47eeba8555
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476539"
---
# <a name="cant-cancel-an-intercompany-purchase-order-thats-linked-to-a-sales-order"></a>Nem lehet érvényteleníteni egy értékesítési rendeléshez kapcsolódó vállalatközi beszerzési rendelést

## <a name="symptoms"></a>Tünetek

Ha olyan vállalatközi beszerzési rendelést próbál érvényteleníteni, amely értékesítési rendeléshez kapcsolódik, akkor a következő hibaüzenet jelenik meg:

> A mennyiség nem csökkenthető, mert a fennmaradó módosítási mennyiség előjele megváltozik.

## <a name="resolution"></a>Megoldás

Ez a probléma a Microsoft Dynamics 365 Supply Chain Management 10.0.13-as verziójában javítva lett. Ebben a verzióban és a későbbi verziókban már érvényteleníteni lehet egy értékesítési rendeléshez kapcsolódó vállalatközi beszerzési rendelést.
