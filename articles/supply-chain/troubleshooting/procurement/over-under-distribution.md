---
title: A könyvelési felosztások túl- vagy alulosztottak.
description: Egy vagy több könyvelési felosztás túlzottan fel van osztva, vagy nincsen eléggé felosztva.
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
ms.openlocfilehash: 7ff0172469df50da9e4272b3fa3f75001a4eb7eb
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476550"
---
# <a name="accounting-distributions-are-either-over--or-under-distributed"></a>A könyvelési felosztások túl- vagy alulosztottak.


## <a name="symptoms"></a>Tünetek

A következő hibaüzenetet kaphatja:

> Egy vagy több könyvelési felosztás túlzottan fel van osztva, vagy nincsen eléggé felosztva

## <a name="cause"></a>Ok

Ez a hiba a beszerzési rendelések felosztásakor jelentkező ellentmondás miatt fordulhat elő.

## <a name="resolution"></a>Megoldás

A hiba blokkolásának feloldásához és a beszerzési rendelés *Vázlat* állapotra állításához nyissa meg a **Beszerzés és forrás \> Időszakos feladatok \> Tisztítás \> Beszerzési rendelés felosztásának visszaállítása** lehetőséget. A további tudnivalókat lásd a következő blogbejegyzésben: [Beszerzésirendelés-felosztási hibák megoldása a Dynamics 365 Supply Chain Management-alkalmazásban](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).
