---
title: Online funkcióprofil létrehozása
description: Ez a témakör azt mutatja be, hogyan lehet egy online funkcióprofilt létrehozni a Microsoft Dynamics 365 Commerce alkalmazásban.
author: samjarawan
manager: annbe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 1b0afeabfecb60672156692f3cd809445624020c
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4969976"
---
# <a name="create-an-online-functionality-profile"></a><span data-ttu-id="439db-103">Online funkcióprofil létrehozása</span><span class="sxs-lookup"><span data-stu-id="439db-103">Create an online functionality profile</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="439db-104">Ez a témakör áttekintést nyújt a Microsoft Dynamics 365 Commerce online funkcióprofiljainak beállításáról.</span><span class="sxs-lookup"><span data-stu-id="439db-104">This topic presents an overview of setting up an online functionality profile for Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="439db-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="439db-105">Overview</span></span>

<span data-ttu-id="439db-106">Az online funkcióprofil különböző beállításokat biztosít az online csatornákhoz.</span><span class="sxs-lookup"><span data-stu-id="439db-106">The online functionality profile provides various settings used for online channels.</span></span> <span data-ttu-id="439db-107">Minden online csatornának meg kell adnia egy online funkcióprofilt.</span><span class="sxs-lookup"><span data-stu-id="439db-107">Each online channel must specify an online functionality profile.</span></span>

## <a name="create-an-online-functionality-profile"></a><span data-ttu-id="439db-108">Online funkcióprofil létrehozása</span><span class="sxs-lookup"><span data-stu-id="439db-108">Create an online functionality profile</span></span>

<span data-ttu-id="439db-109">A következő eljárás bemutatja, hogyan lehet online funkcióprofilt létrehozni a Commerce Headquarters alkalmazásból.</span><span class="sxs-lookup"><span data-stu-id="439db-109">The following procedure explains how to create an online functionality profile from within Commerce Headquarters app.</span></span>

1. <span data-ttu-id="439db-110">A navigációs ablaktáblán ugorjon a **Modulok \> Csatorna beállítás \> Online áruház beállítása \> Funkcióprofilok** elemre.</span><span class="sxs-lookup"><span data-stu-id="439db-110">In the navigation pane, go to **Modules \> Channel setup \> Online store setup \> Functionality profiles**.</span></span>
1. <span data-ttu-id="439db-111">A műveleti ablaktáblán kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="439db-111">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="439db-112">A **Profil** mezőbe írja be a profil azonosítóját.</span><span class="sxs-lookup"><span data-stu-id="439db-112">In the **Profile** field, enter an ID for the profile.</span></span>
1. <span data-ttu-id="439db-113">A **Leírás** mezőbe írjon be egy értéket (a lenti példában szereplő képen: „Kalandorbolt-profil”).</span><span class="sxs-lookup"><span data-stu-id="439db-113">In the **Description** field, enter a value ("Adventure Works Profile" in the example image below).</span></span>
1. <span data-ttu-id="439db-114">A **Funkciók** részben szükség szerint módosítsa a **KOSÁR**, **KISKERESKEDELMI VEVŐK** vagy **PÉNZTÁR** beállításokat.</span><span class="sxs-lookup"><span data-stu-id="439db-114">In the **Functions** section, modify the **CART**, **RETAIL CUSTOMERS**, or **CHECKOUT** settings, as needed.</span></span>
1. <span data-ttu-id="439db-115">A műveleti ablaktáblán válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="439db-115">On the action pane, select **Save**.</span></span>

<span data-ttu-id="439db-116">A következő kép egy példát mutat az online funkcióprofilra.</span><span class="sxs-lookup"><span data-stu-id="439db-116">The following image shows an example online functionality profile.</span></span>
  
![Példa az online funkcióprofilra](media/online-functionality-profile.png)

## <a name="functions"></a><span data-ttu-id="439db-118">Függvények</span><span class="sxs-lookup"><span data-stu-id="439db-118">Functions</span></span>

- <span data-ttu-id="439db-119">**Összesített termékek**: Ha engedélyezve van, ez a funkció lehetővé teszi a kosár számára, hogy frissítse a mennyiséget, ha ugyanazt a tételt többször hozáadták.</span><span class="sxs-lookup"><span data-stu-id="439db-119">**Aggregate products**: When enabled, this function allows the cart to update quantity when the same item is added multiple times.</span></span>
- <span data-ttu-id="439db-120">**Fizetés nélküli pénztár engedélyezése**: Ha be van jelölve, ez a funkció kezeli a helyzetet, amikor a kosárba felvett cikkek ára 0,00 USD.</span><span class="sxs-lookup"><span data-stu-id="439db-120">**Allow checkout with no payments**: When enabled, this function handles the scenario when items added to cart have a price $0.00.</span></span>
- <span data-ttu-id="439db-121">**Vevő létrehozása aszinkron módban**: Ez egy örökölt beállítás, amely harmadik fél e-Commerce csatornákra vonatkozik, és nem alkalmazható a Dynamics 365 e-Commerce webhelyre.</span><span class="sxs-lookup"><span data-stu-id="439db-121">**Create customer in async mode**: This is a legacy setting applicable to third-party e-Commerce channels and is not applicable to the Dynamics 365 e-Commerce site.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="439db-122">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="439db-122">Additional resources</span></span>

[<span data-ttu-id="439db-123">Csatornák áttekintése</span><span class="sxs-lookup"><span data-stu-id="439db-123">Channels overview</span></span>](channels-overview.md)

[<span data-ttu-id="439db-124">Csatornák beállításának előfeltételei</span><span class="sxs-lookup"><span data-stu-id="439db-124">Channel setup prerequisites</span></span>](channels-prerequisites.md)

[<span data-ttu-id="439db-125">Online csatorna beállítása</span><span class="sxs-lookup"><span data-stu-id="439db-125">Set up an online channel</span></span>](channel-setup-online.md)

[<span data-ttu-id="439db-126">Kiskereskedelmi csatorna beállítása</span><span class="sxs-lookup"><span data-stu-id="439db-126">Set up a retail channel</span></span>](channel-setup-retail.md)

[<span data-ttu-id="439db-127">Hívásközpont csatorna beállítása</span><span class="sxs-lookup"><span data-stu-id="439db-127">Set up a call center channel</span></span>](channel-setup-callcenter.md)
