---
title: A készként jelentés frissítése sikertelen, hiányzó mennyiség hibával
description: Ha próbál befejezni egy termelési rendelést, miközben a hibás mennyiséget jelenti, de az idő vagy az anyag mennyiségét nem, a készként való jelentés frissítése hibás lesz.
author: SmithaNataraj
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 7785549c47063727f2749749940c1a96a351e70f
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476523"
---
# <a name="report-as-finished-update-fails-with-a-missing-quantity-error"></a>A készként jelentés frissítése sikertelen, hiányzó mennyiség hibával

## <a name="symptoms"></a>Tünetek

A termelési rendelést készként próbálja jelenteni, amíg a hibamennyiséget jelenti, de az idő- vagy anyagmennyiséget nem jelenti. A készként jelentett frissítés sikertelen lesz, amikor megpróbálja lemondani a termelési rendelést, és a következő hibaüzenet jelenik meg:

> Hiányzó befejezettként jelentett mennyiség.

## <a name="resolution"></a>Megoldás

Ha a hibamennyiséget jelenti egy termelési rendelésen, akkor az áru mennyiségét is jelentenie kell.
