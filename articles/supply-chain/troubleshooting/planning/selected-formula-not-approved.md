---
title: A kijelölt receptúraszám nincs jóváhagyva kötegrendeléshez
description: Egy tervezett rendelés meghatározásakor olyan hibaüzenet jelenik meg, amely szerint a kiválasztott receptúraszám nincs jóváhagyva kötegrendeléshez.
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
ms.openlocfilehash: a41cf955d151726348bea83e52a24bc8784352c2d07268ced944e4cc6bf35491
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6712910"
---
# <a name="selected-formula-number-isnt-approved-for-a-batch-order"></a>A kijelölt receptúraszám nincs jóváhagyva kötegrendeléshez

Hibakód: PRO2614

## <a name="symptoms"></a>Tünetek

Amikor tervezett rendelést próbál megerősíteni, a következő hibaüzenetet kapja:

> A választott receptúraszám nincs jóváhagyva kötegrendeléshez.

## <a name="cause"></a>Ok

A rendszer ellenőrzi a meghatározási műveletet, hogy áll-e rendelkezésre jóváhagyott receptúra az aktív cikkhez. Önnek valószínűleg jóvá kell hagynia a receptúrát.

## <a name="resolution"></a>Megoldás

A receptúra jóváhagyásához hajtsa végre az alábbi lépéseket.

1. Lépjen a **Termékinformációk kezelése \> Anyagjegyzékek és receptúrák \> Receptúrák** részre.
1. Válassza ki a kívánt receptúrát.
1. A Művelet ablaktábla **Receptúra** lapján lévő **Karbantartás** csoportban válassza a **Receptúra jóváhagyása** lehetőséget.
1. A **DBJ vagy receptúra jóváhagyása** párbeszédpanelen válassza ki a jóváhagyót, és kattintson az **OK** gombra.
