---
title: Költségek a szabálytalansági műveletekhez kapcsolódóan
description: Ez a témakör azt ismerteti, hogyan lehet létrehozni a szabálytalanságok műveleteihez használható minőségi költségeket.
author: yufeihuang
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventTestMiscCharges
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 29520afca07adee49846d1be987685a1ece8283c
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8850728"
---
# <a name="charges-for-nonconformance-operations"></a>Költségek a szabálytalansági műveletekhez kapcsolódóan

[!include [banner](../includes/banner.md)]

Ez a témakör azt ismerteti, hogyan lehet létrehozni a szabálytalanságok műveleteihez használható minőségi költségeket.

A **Minőségi költségek** lapot használhatja azon költségtípusok meghatározásához, amelyeket hozzá lehet adni a szabálytalanságok műveleteihez. A költségekkel nyomon követheti a nem megfelelő termékekért a vevőnek fizetendő díjakat vagy költségeket, illetve azt, hogy a szállító tartozik-e Önnek a nem megfelelő termékek szállításáért. A költségek a külső szállítók vagy szolgáltatások műveleteihez szükséges költségek nyomon követésére is használhatók.

## <a name="examples-of-quality-charges"></a>Példák a minőségi költségekre

Egy gyártó cégnek dolgozik. A vállalat több szállítóval is szerződésben áll. Ezek a szerződések a cikkek időben való szállításának, károkkal és termékminőségének szabványait körvonalazzák. Hasonlóképpen számos vevővel is szerződésben áll a vállalata – a visszaküldéssel, a károkkal és a termékminőséggel kapcsolatos adatokat tartalmazza.

Az egyes körülményekhez díjszerkezet van definiálva, és a szerződésben meg van határozva. A minőségbiztosítási költségeket a különféle költségtípusok, például a *Károk*, a *Késedelmes szállítás* és a *Minőség* lehetőségben is beállíthatja. Szabálytalanság létrehozásakor egy vagy több műveletet kell hozzáadnia. Minden egyes művelethez a **Költségek** lehetőséget választva határozhatja meg a díjak adatait.

## <a name="create-a-quality-charge"></a>Minőségi költség létrehozása

1. Ugorjon a **Készletkezelés \> Beállítás \> Minőségkezelés \> Minőségi költségek** pontra.
1. A műveleti ablakpanelen válassza ki az **Új** lehetőséget, ha hozzá szeretne adni egy sort a rácshoz. Ezután új sorhoz állítsa be a következő mezőket:

    - **Költségkód** – Adja meg a minőségi költség egyedi azonosítóját vagy nevét.
    - **Leírás** – Adja meg a minőségi költség részletes leírását.

1. Zárja be a lapot.

## <a name="add-a-quality-charge-to-an-operation-for-a-nonconformance"></a>Minőségi költség hozzáadása szabálytalansági művelethez

A szabálytalanságok műveleteinek hozzáadásával és a költségek rájuk való alkalmazásával kapcsolatban lásd: [Műveletek a szabálytalanságokhoz](quality-operations.md).

## <a name="additional-resources"></a>További erőforrások

- [Minőségkezelés áttekintése](quality-management-processes.md)
- [A minőség- és a szabálytalanságkezelés engedélyezése](enable-quality-management.md)
- [A szabálytalanságok jóváhagyásáért felelős dolgozók](quality-responsible-workers.md)
- [A szabálytalanságok karanténzónái](quality-quarantine-zones.md)
- [A szabálytalanságok diagnosztikai típusai](quality-diagnostic-types.md)
- [Szabálytalanságok minőségi költségei](quality-charges.md)
- [Műveletek szabálytalanságokhoz kapcsolódóan](quality-operations.md)
- [Raktári folyamatok minőségkezelése](quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
