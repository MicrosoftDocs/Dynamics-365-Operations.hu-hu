---
title: Munkarendelés típusai
description: Ez a témakör bemutatja az Eszközkezelésben a munkarendelések típusait.
author: johanhoffmann
ms.date: 08/13/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetWorkOrderType
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 12745960f903ebc14208f2c8a01f076ed27a38d3
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8891176"
---
# <a name="work-order-types"></a>Munkarendelés típusai

[!include [banner](../../includes/banner.md)]

 

A munkarendelés-típusok a munkarendelések kategorizálására szolgálnak. A munkarendelések kapcsolódhatnak például megelőző karbantartáshoz vagy hibaelhárító karbantartáshoz.

A munkarendelés-típus határozza meg egy munkarendelés életciklusmodelljéhez fűződő kapcsolatot. A munkarendelés életciklusmodellje határozza meg a munkarendelésen beállítható munkarendelés életciklus-állapotát. (A munkarendelés életciklus-állapota lehet például: **Létrehozva**, **Folyamatban** és **Befejezve**.)

A munkarendelés életciklus-állapotaival és projektfázisaival kapcsolatos további információért lásd: [Munkarendelés életciklus-állapotai](work-order-lifecycle-states.md).

1. Válassza ki az **Eszközkezelés** \> **Beállítás** \> **Munkarendelések** \> **Munkarendelés-típusai** elemet.
2. Válassza az **Új** lehetőséget egy új munkarendelés-típus létrehozásához.
3. A **Munkarendelés-típus** mezőben adja meg a munkarendelés típusának azonosítóját.
4. A **Név** mezőben adjon meg egy nevet.
5. Válasszon ki egy életciklusmodellt a **Munkarendelés életciklusmodellje** mezőben.
5. Állítsa az **Egy karbantartási dolgozó** beállítást **Igen** értékre, ha az adott típusú munkarendeléshez kapcsolódó összes munkarendelési feladatot ugyanahhoz a karbantartási dolgozóhoz kell ütemezni.
6. A **Költségtípus** mezőben válassza ki a megfelelőt: **Helyesbítő**, **Megelőző** vagy **Befektetés**. A munkarendelésen szereplő összes munkarendelési feladatnak ugyanolyan költségtípusúnak kell lennie.
7. A **Kötelező** szakaszban állítsa a megfelelő beállításokat **Igen** értékre, amellyel megadhatja, hogy az ilyen típusú munkarendeléshez milyen, a hibával vagy karbantartás miatti üzemkimaradással kapcsolatos információt adjon hozzá a rendszer.

    > [!NOTE]
    > A **Kötelező** szakasz beállításai a **Munkarendelés életciklus-állapotai** oldal **Ellenőrzés** gyorslapján található beállításokhoz kapcsolódnak (**Eszközkezelés** \> **Beállítás** \> **Munkarendelések** \> **Életciklus-állapotok**).

8. Válassza a **Mentés** lehetőséget.

![Munkarendelés típusai.](media/16-setup-for-work-orders.png)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]