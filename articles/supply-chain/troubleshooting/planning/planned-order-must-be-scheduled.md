---
title: A tervezett termelési rendelést ütemezni kell a megerősítés előtt
description: Amikor tervezett rendelést próbál megerősíteni, olyan hibaüzenet jelenik meg, amely szerint a rendelést ütemezni kell a megerősítés előtt.
author: ankubik
ms.date: 06/10/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPo
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ankubik
ms.search.validFrom: 2021-06-10
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: a89f5f98895be5b934dbdc1194fa58b9af34f9cbc7f5e2092f6f47791dd52400
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6777743"
---
# <a name="planned-production-order-must-be-scheduled-before-it-can-be-firmed"></a>A tervezett termelési rendelést ütemezni kell a megerősítés előtt

Hibakód: SYS309802

## <a name="symptoms"></a>Tünetek

Amikor tervezett rendelést próbál megerősíteni, a következő hibaüzenetet kapja:

> A tervezett termelési rendelést megerősítés előtt ütemezni kell.

## <a name="cause"></a>Ok

Az ütemezett kezdő és záró dátum nem lehet üres.

## <a name="resolution"></a>Megoldás

A tervezett rendelés kezdő és záró dátumának megadásához kövesse az alábbi lépéseket.

1. Ugorjon az **Alaptervezés \> Alaptervezés \> Tervezett rendelések** pontra.
1. Nyissa meg a megfelelő tervezett rendelést.
1. Az **Általános** gyorslap **Ütemezett** szakaszában adja meg a **Kezdő dátum** és a **Záró dátum** mező értékét.
