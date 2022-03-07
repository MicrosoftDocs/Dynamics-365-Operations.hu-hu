---
title: A szállítási maradék törlése a beszerzési rendelést Visszaigazolt állapotba helyezi át
description: Ha szállítási maradék törlése egy olyan beszerzési rendelésen történik, amelyen a változáskezelés be van kapcsolva, a beszerzési rendelés Visszaigazolt állapotba kerül
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
ms.openlocfilehash: 1d8b331bc5699487dff3491d65daa36293f3212f
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476564"
---
# <a name="cancelling-delivery-remainder-moves-purchase-order-to-a-confirmed-state"></a>A szállítási maradék törlése a beszerzési rendelést Visszaigazolt állapotba helyezi át

## <a name="symptoms"></a>Tünetek

Olyan beszerzési rendelés esetében, amelyre a változáskezelés érvényes, ha az egyetlen kért módosítás a szállítási maradék törlése egy vagy több sorhoz, a beszerzési rendelés automatikusan *Megerősített* állapotba kerül, a jóváhagyást követően, és nem jön létre napló.

## <a name="resolution"></a>Megoldás

A szállítás maradék visszavonása nem befolyásolja a visszaigazolási napló tartalmát. Ezt a funkciót akkor kell használni, ha a sor részlegesen beérkezett, és a fennmaradó minőséget érvényteleníteni kell egy feldolgozási lépésben, miután a beszerzési rendelést a szállító megerősítette.

Ha ennek tükröződnie kell a beszerzési rendelés visszaigazolásán, akkor a mennyiséget helyesbíteni kell a beszerzési rendelés sorában, hogy a visszaigazolást legyen szükséges. Azt is megteheti, hogy ha a sorban nem érkezett be semmi, akkor a mennyiséget eltávolítja. Ebben az esetben visszaigazolás szükséges.
