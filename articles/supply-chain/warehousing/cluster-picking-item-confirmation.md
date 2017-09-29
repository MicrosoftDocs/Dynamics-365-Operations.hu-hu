---
title: "Termék-visszaigazolás fürt kitárolásához"
description: "Ez a téma azt írja le, hogyan állíthatja be az elemek hitelesítését a fürtök kiválasztásával együtt."
author: Mirzaab
manager: AnnBe
ms.date: 05/26/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 08c38aada355583c5a6872f75b57db95d9b81786
ms.openlocfilehash: 17f5761df4294abfea28e7cb8d50c86f1e3e136f
ms.contentlocale: hu-hu
ms.lasthandoff: 07/18/2017

---

[!include[banner](../includes/banner.md)]

# <a name="product-confirmation-for-cluster-picking"></a><span data-ttu-id="b7ea4-103">Termék-visszaigazolás fürt kitárolásához</span><span class="sxs-lookup"><span data-stu-id="b7ea4-103">Product confirmation for cluster picking</span></span>
<span data-ttu-id="b7ea4-104">A fürtkiválasztás lehetővé teszi, hogy egyszerre több megrendelést vegyen fel.</span><span class="sxs-lookup"><span data-stu-id="b7ea4-104">Cluster picking allows you to pick items for several orders at the same time.</span></span> <span data-ttu-id="b7ea4-105">Ha a fürtkiválasztást alkalmazzák, a cikkek megerősítése döntő fontosságú a fürtökhöz hozzáadott cikkek ellenőrzéséhez.</span><span class="sxs-lookup"><span data-stu-id="b7ea4-105">When cluster picking is applied, item confirmation is crucial to verify the items that are added to clusters.</span></span> <span data-ttu-id="b7ea4-106">A fürtkiválasztás folyamán ellenőrizheti a fürtkiválasztás cikkeit.</span><span class="sxs-lookup"><span data-stu-id="b7ea4-106">You can verify items in cluster picking during the cluster picking process.</span></span>

## <a name="where-it-applies"></a><span data-ttu-id="b7ea4-107">Alkalmazási kör</span><span class="sxs-lookup"><span data-stu-id="b7ea4-107">Where it applies</span></span>
<span data-ttu-id="b7ea4-108">A fürtkiválasztáshoz tartozó cikkek ellenőrzése ugyanúgy működik, mint a nem fürtkiválasztási folyamatok elemeinek ellenőrzése.</span><span class="sxs-lookup"><span data-stu-id="b7ea4-108">Item verification for cluster picking works the same way as when you verify items in a non-cluster picking processes.</span></span> <span data-ttu-id="b7ea4-109">A beállítás a termékvonalkód-beállításon alapul.</span><span class="sxs-lookup"><span data-stu-id="b7ea4-109">The setup is based on the product bar code setup.</span></span>

## <a name="set-up-item-verification-with-cluster-picking"></a><span data-ttu-id="b7ea4-110">Cikkellenőrzés beállítása a fürtkiválasztásnál</span><span class="sxs-lookup"><span data-stu-id="b7ea4-110">Set up item verification with cluster picking</span></span>
1.  <span data-ttu-id="b7ea4-111">A mobileszköz menüpontjában nyissa meg a munkamegerősítés beállítási képernyőjét: **Raktárkezelés** > **Raktárkezelés** > **Beállítás** > **Mobileszköz** > **Mobileszköz menüpontjai**.</span><span class="sxs-lookup"><span data-stu-id="b7ea4-111">On a mobile device menu item, open the setup form for work confirmation: **Warehouse management** > **Warehouse management** > **Setup** > **Mobile device** > **Mobile device menu items**.</span></span>
2.  <span data-ttu-id="b7ea4-112">A mobileszköz menüpontjából nyissa meg a **Munkamegerősítés beállítását**.</span><span class="sxs-lookup"><span data-stu-id="b7ea4-112">From the mobile device menu item, open **Work confirmation setup**.</span></span>

| <span data-ttu-id="b7ea4-113">Lehetőség</span><span class="sxs-lookup"><span data-stu-id="b7ea4-113">Option</span></span>        | <span data-ttu-id="b7ea4-114">Leírás</span><span class="sxs-lookup"><span data-stu-id="b7ea4-114">Description</span></span>   | 
| ------------- | ------------- |
|<span data-ttu-id="b7ea4-115">Termék visszaigazolása</span><span class="sxs-lookup"><span data-stu-id="b7ea4-115">Product confirmation</span></span> | <span data-ttu-id="b7ea4-116">Lehetővé teszi, hogy a mobileszközről ellenőrizze a készlet minden elemét a beolvasáskor.</span><span class="sxs-lookup"><span data-stu-id="b7ea4-116">Allows you to verify each piece of inventory from the mobile device when scanned.</span></span>|

