---
title: A Vevőrekordok nem jelennek meg a Commerce központi felületén
description: Ez a témakör olyan hibaelhárítási útmutatást tartalmaz, amely segítséget nyújt abban az esetben, ha a vevőrekordok nem jelennek meg azonnal a Commerce központi felületén.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: b8d065dd104df616ba8f10f7813e74c900fdcf77
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/11/2021
ms.locfileid: "6018482"
---
# <a name="customer-records-dont-appear-in-commerce-headquarters"></a>A Vevőrekordok nem jelennek meg a Commerce központi felületén

[!include [banner](../../includes/banner.md)]

Ez a témakör olyan hibaelhárítási útmutatást tartalmaz, amely segítséget nyújt abban az esetben, ha a vevőrekordok nem jelennek meg azonnal a Commerce központi felületén.

## <a name="description"></a>Leírás

Amikor új vevőrekordot hoz létre az e-kereskedelmi üzlet bejelentkezési folyamatának használatával, a megfelelő vevőrekord nem jelenik meg azonnal a Commerce központi felületén.

## <a name="resolution"></a>Felbontás

### <a name="disable-customer-creation-in-async-mode"></a>Vevő létrehozásának letiltása aszinkron módban

> [!IMPORTANT]
> Ha letiltja az aszinkron vevőlétrehozást, ez hatással lehet a rendszer teljesítményére, mivel minden rekord létrehozása valós idejű igénylést eredményez a Commerce központi felülete felé. Ezenkívül ha a Commerce központi felülete nem üzemel (például a szervizelési folyamatok közben), az új vevőlétrehozási folyamatok hibákat okoznak.

A következő lépésekkel tilthatja le az aszinkron vevőlétrehozást a Commerce központi felületén.

1. Ugorjon a következő elemre: **Retail és Commerce \> Csatorna beállítása \> Online üzet beállítása \> Funkcióprofilok**.
1. Ha még nem használ funkcióprofilt az online csatornához, hozzon létre egyet.
1. Győződjön meg arról, hogy a **Vevő létrehozása aszinkron módban** beállítás értéke **Nem** legyen.
1. Nyissa meg a következőt: **Retail és Commerce \> Csatornák \> Online áruházak**.
1. Válassza ki azt az online áruházat, amelynél le szeretné tiltani az aszinkron vevőlétrehozást.
1. Az **Általános** lapon győződjön meg arról, hogy a **Funkcióprofil** mezőben az online csatorna által használt funkcióprofil legyen beállítva.

## <a name="additional-resources"></a>További erőforrások

[B2C-bérlő beállítása a Commerce alkalmazásban](../set-up-b2c-tenant.md)
