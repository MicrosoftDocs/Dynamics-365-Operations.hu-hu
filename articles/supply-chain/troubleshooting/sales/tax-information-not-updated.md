---
title: Az adóinformációk nem frissülnek, ha megváltozik az értékesítési rendelés helye
description: Ha a hely, a raktár vagy a szállítási cím egy értékesítési rendelés fejlécében módosul, akkor a program nem frissíti az eset adózási információit a sorokban. Ezt manuálisan kell elvégeznie.
author: SmithaNataraj
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 77a73a787ff8a174c575f3b4f75694ded45d5712
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476556"
---
# <a name="tax-information-isnt-updated-if-location-on-a-sales-order-header-is-changed"></a>Az adózási információk nem frissülnek, ha módosítom a helyet egy értékesítési rendelés fejlécében

## <a name="symptoms"></a>Tünetek

Ha a hely, a raktár vagy a szállítási cím egy értékesítési rendelés fejlécében módosul, akkor a program nem frissíti az eset adózási információit a sorokban.

## <a name="resolution"></a>Megoldás

Ez szándékosan van. A probléma oka az, hogy a szállítási cím, a hely és a raktár nem változik meg automatikusan a sor szintjén. Ezeket manuálisan kell frissítenie.
