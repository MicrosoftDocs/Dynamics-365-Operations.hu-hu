---
title: Termék-visszaigazolás fürt kitárolásához
description: Ez a téma azt írja le, hogyan állíthatja be az elemek hitelesítését a fürtök kiválasztásával együtt.
author: Mirzaab
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSRFAutoConfirm
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 530129ba6877c68475217d3a035775e25930cd07
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5808870"
---
# <a name="product-confirmation-for-cluster-picking"></a><span data-ttu-id="578b5-103">Termék-visszaigazolás fürt kitárolásához</span><span class="sxs-lookup"><span data-stu-id="578b5-103">Product confirmation for cluster picking</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="578b5-104">A fürtkiválasztás lehetővé teszi, hogy egyszerre több megrendelést vegyen fel.</span><span class="sxs-lookup"><span data-stu-id="578b5-104">Cluster picking allows you to pick items for several orders at the same time.</span></span> <span data-ttu-id="578b5-105">Ha a fürtkiválasztást alkalmazzák, a cikkek megerősítése döntő fontosságú a fürtökhöz hozzáadott cikkek ellenőrzéséhez.</span><span class="sxs-lookup"><span data-stu-id="578b5-105">When cluster picking is applied, item confirmation is crucial to verify the items that are added to clusters.</span></span> <span data-ttu-id="578b5-106">A fürtkiválasztás folyamán ellenőrizheti a fürtkiválasztás cikkeit.</span><span class="sxs-lookup"><span data-stu-id="578b5-106">You can verify items in cluster picking during the cluster picking process.</span></span>

## <a name="where-it-applies"></a><span data-ttu-id="578b5-107">Alkalmazási kör</span><span class="sxs-lookup"><span data-stu-id="578b5-107">Where it applies</span></span>

<span data-ttu-id="578b5-108">A fürtkiválasztáshoz tartozó cikkek ellenőrzése ugyanúgy működik, mint a nem fürtkiválasztási folyamatok elemeinek ellenőrzése.</span><span class="sxs-lookup"><span data-stu-id="578b5-108">Item verification for cluster picking works the same way as when you verify items in a non-cluster picking processes.</span></span> <span data-ttu-id="578b5-109">A beállítás a termékvonalkód-beállításon alapul.</span><span class="sxs-lookup"><span data-stu-id="578b5-109">The setup is based on the product bar code setup.</span></span>

## <a name="set-up-item-verification-with-cluster-picking"></a><span data-ttu-id="578b5-110">Cikkellenőrzés beállítása a fürtkiválasztásnál</span><span class="sxs-lookup"><span data-stu-id="578b5-110">Set up item verification with cluster picking</span></span>

1. <span data-ttu-id="578b5-111">A mobileszköz menüpontjában nyissa meg a munkamegerősítés beállítási képernyőjét: **Raktárkezelés** > **Raktárkezelés** > **Beállítás** > **Mobileszköz** > **Mobileszköz menüpontjai**.</span><span class="sxs-lookup"><span data-stu-id="578b5-111">On a mobile device menu item, open the setup form for work confirmation: **Warehouse management** > **Warehouse management** > **Setup** > **Mobile device** > **Mobile device menu items**.</span></span>
1. <span data-ttu-id="578b5-112">A mobileszköz menüpontjából nyissa meg a **Munkamegerősítés beállítását**.</span><span class="sxs-lookup"><span data-stu-id="578b5-112">From the mobile device menu item, open **Work confirmation setup**.</span></span>

|        <span data-ttu-id="578b5-113">Lehetőség</span><span class="sxs-lookup"><span data-stu-id="578b5-113">Option</span></span>        |                                    <span data-ttu-id="578b5-114">Leírás</span><span class="sxs-lookup"><span data-stu-id="578b5-114">Description</span></span>                                    |
|----------------------|-----------------------------------------------------------------------------------|
| <span data-ttu-id="578b5-115">Termék visszaigazolása</span><span class="sxs-lookup"><span data-stu-id="578b5-115">Product confirmation</span></span> | <span data-ttu-id="578b5-116">Lehetővé teszi, hogy a mobileszközről ellenőrizze a készlet minden elemét a beolvasáskor.</span><span class="sxs-lookup"><span data-stu-id="578b5-116">Allows you to verify each piece of inventory from the mobile device when scanned.</span></span> |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]