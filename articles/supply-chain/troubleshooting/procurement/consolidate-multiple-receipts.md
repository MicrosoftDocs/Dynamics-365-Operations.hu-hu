---
title: Egyetlen beszerzési rendelésbe nem lehet több terméknyugtát egyesíteni
description: Egyetlen beszerzési rendelésbe nem lehet több terméknyugtát összesíteni, ha a különböző szállítólevél-sorok különböző könyvelési dátumokkal rendelkeznek.
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
ms.openlocfilehash: 485306279281ceb55a140526f4216af35574af42
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476521"
---
# <a name="you-cant-consolidate-multiple-product-receipts-into-a-single-purchase-order"></a>Egyetlen beszerzési rendelésbe nem lehet több terméknyugtát egyesíteni

## <a name="symptoms"></a>Tünetek

Egyetlen beszerzési rendelésbe nem lehet több terméknyugtát összesíteni, ha a különböző szállítólevél-sorok különböző könyvelési dátumokkal rendelkeznek.

## <a name="resolution"></a>Megoldás

A Dynamics 365 Supply Chain Management korábbi verzióiban a konszolidáció ebben a helyzetben engedélyezett volt. Ez a gyakorlat azonban hibákhoz vezethet. A létrejövő beszerzésirendelés-sorok könyvelési dátuma nem térhet el azon terméknyugta-sorok könyvelés dátumától, amelyek alapján ezeket a beszerzésirendelés-sorokat létrehozták. (A beszerzési rendelés sorainak könyvelési dátuma megegyezik a beszerzési rendelés fejlécében szereplő könyvelési dátummal.) Ezért a több nyugta egyetlen beszerzési rendelésbe történő konszolidációja már nem engedélyezett.

A könyvelési dátum például költségvetési foglalások és kötelezettségvállalások esetén használatos. Ezért a termék bevételezéséről a beszerzési rendelésre való áttérés során meg kell őrizni.
