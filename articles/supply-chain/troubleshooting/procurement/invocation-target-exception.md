---
title: Kivétel történik a szállítói számla feladása közben.
description: 'A szállítói számla feladása során kivétel történik: „Kivétel történt a meghívás célja felől”.'
author: kamaybac
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: PurchTable, PurchTablePart
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: ecc63cb7d0d2392105d8e4290f8e837945ae0781
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476548"
---
# <a name="an-exception-occurs-during-vendor-invoice-posting"></a>Kivétel történik a szállítói számla feladása közben.


## <a name="symptoms"></a>Tünetek

Szállítói számla feladásakor a következő kivételt kapja:

> Kivétel történt a meghívás célja felől

## <a name="cause"></a>Ok

Ez a hiba a beszerzési rendelések felosztásakor jelentkező ellentmondás miatt fordulhat elő.

## <a name="resolution"></a>Megoldás

A hiba blokkolásának feloldásához és a beszerzési rendelés *Vázlat* állapotra állításához nyissa meg a **Beszerzés és forrás \> Időszakos feladatok \> Tisztítás \> Beszerzési rendelés felosztásának visszaállítása** lehetőséget. A további tudnivalókat lásd a következő blogbejegyzésben: [Beszerzésirendelés-felosztási hibák megoldása a Dynamics 365 Supply Chain Management-alkalmazásban](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).
