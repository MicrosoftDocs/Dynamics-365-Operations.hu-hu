---
title: Termék-visszaigazolás fürt kitárolásához
description: Ez a téma azt írja le, hogyan állíthatja be az elemek hitelesítését a fürtök kiválasztásával együtt.
author: Mirzaab
manager: tfehr
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSRFAutoConfirm
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 272c3a13b68e2b862faf20cc269ca790322b61de
ms.sourcegitcommit: 89022f39502b19c24c0997ae3a01a64b93280f42
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/12/2020
ms.locfileid: "3367292"
---
# <a name="product-confirmation-for-cluster-picking"></a>Termék-visszaigazolás fürt kitárolásához

[!include [banner](../includes/banner.md)]

A fürtkiválasztás lehetővé teszi, hogy egyszerre több megrendelést vegyen fel. Ha a fürtkiválasztást alkalmazzák, a cikkek megerősítése döntő fontosságú a fürtökhöz hozzáadott cikkek ellenőrzéséhez. A fürtkiválasztás folyamán ellenőrizheti a fürtkiválasztás cikkeit.

## <a name="where-it-applies"></a>Alkalmazási kör

A fürtkiválasztáshoz tartozó cikkek ellenőrzése ugyanúgy működik, mint a nem fürtkiválasztási folyamatok elemeinek ellenőrzése. A beállítás a termékvonalkód-beállításon alapul.

## <a name="set-up-item-verification-with-cluster-picking"></a>Cikkellenőrzés beállítása a fürtkiválasztásnál

1. A mobileszköz menüpontjában nyissa meg a munkamegerősítés beállítási képernyőjét: **Raktárkezelés** > **Raktárkezelés** > **Beállítás** > **Mobileszköz** > **Mobileszköz menüpontjai**.
1. A mobileszköz menüpontjából nyissa meg a **Munkamegerősítés beállítását**.

|        Lehetőség        |                                    Leírás                                    |
|----------------------|-----------------------------------------------------------------------------------|
| Termék visszaigazolása | Lehetővé teszi, hogy a mobileszközről ellenőrizze a készlet minden elemét a beolvasáskor. |
