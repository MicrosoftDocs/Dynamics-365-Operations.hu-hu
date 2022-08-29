---
title: Az ügyfélrekordok nem jelennek meg a Commerce headquartersben
description: Ez a cikk olyan hibaelhárítási útmutatást tartalmaz, amely segítséget nyújt abban az esetben, ha a vevőrekordok nem jelennek meg azonnal a Commerce Headquarters alkalmazásnál.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.custom: ''
ms.assetid: ''
ms.search.industry: Retail
ms.openlocfilehash: f1ad1f45abbc95cbf6d41b3c8681db781c6c9d23
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9268838"
---
# <a name="customer-records-dont-appear-in-commerce-headquarters"></a>Az ügyfélrekordok nem jelennek meg a Commerce headquartersben

[!include [banner](../../includes/banner.md)]

Ez a cikk olyan hibaelhárítási útmutatást tartalmaz, amely segítséget nyújt abban az esetben, ha a vevőrekordok nem jelennek meg azonnal a Commerce Headquarters alkalmazásnál.

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
