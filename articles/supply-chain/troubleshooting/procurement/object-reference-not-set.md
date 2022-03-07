---
title: „Objektumhivatkozás nincs beállítva” hiba a beszerzési rendelés megerősítése során.
description: „Objektumhivatkozás nincs beállítva” hiba a beszerzési rendelés megerősítése során.
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
ms.openlocfilehash: 78e5e365f7197c1a0c25bf6eb63bcd5bd0f482ed
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476573"
---
# <a name="error-object-reference-not-set-occurs-during-purchase-order-confirmation"></a>„Objektumhivatkozás nincs beállítva” hiba a beszerzési rendelés megerősítése során.

## <a name="symptoms"></a>Tünetek

Beszerzési rendelés megerősítésekor a következő kivételt kapja:

> Az objektumhivatkozás nincs beállítva

## <a name="cause"></a>Ok

Ez a hiba a beszerzési rendelések felosztásakor jelentkező ellentmondás miatt fordulhat elő.

## <a name="resolution"></a>Megoldás

A hiba blokkolásának feloldásához és a beszerzési rendelés *Vázlat* állapotra állításához nyissa meg a **Beszerzés és forrás \> Időszakos feladatok \> Tisztítás \> Beszerzési rendelés felosztásának visszaállítása** lehetőséget. A további tudnivalókat lásd a következő blogbejegyzésben: [Beszerzésirendelés-felosztási hibák megoldása a Dynamics 365 Supply Chain Management-alkalmazásban](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).
