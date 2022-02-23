---
title: Munkarendelés típusai
description: Ez a témakör a munkarendelés-típusokat mutatja be az Eszközkezelésben.
author: josaw1
manager: tfehr
ms.date: 08/13/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetWorkOrderType
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 9111ffa552059883696cf8248a02dfe70bc12ee7
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/16/2021
ms.locfileid: "5021529"
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

![Munkarendelés típusai](media/16-setup-for-work-orders.png)
