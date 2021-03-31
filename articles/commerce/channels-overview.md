---
title: Csatornák áttekintése
description: Ez a témakör áttekintést nyújt a csatornákról a Microsoft Dynamics 365 Commerce szolgáltatásban.
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
ms.openlocfilehash: 8ac188832bdaeba430eed7f08e91a9c2214a0e15
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5219101"
---
# <a name="channels-overview"></a><span data-ttu-id="32b4a-103">Csatornák áttekintése</span><span class="sxs-lookup"><span data-stu-id="32b4a-103">Channels overview</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="32b4a-104">Ez a témakör áttekintést nyújt a csatornákról a Microsoft Dynamics 365 Commerce szolgáltatásban.</span><span class="sxs-lookup"><span data-stu-id="32b4a-104">This topic presents an overview of channels in Microsoft Dynamics 365 Commerce.</span></span> <span data-ttu-id="32b4a-105">Az egyes csatornák beállítása előtt és után elvégzendő feladatokkal kapcsolatban is itt tájékozódhat.</span><span class="sxs-lookup"><span data-stu-id="32b4a-105">It includes information about the tasks that you must complete both before and after you set up each channel.</span></span>

## <a name="types-of-channels"></a><span data-ttu-id="32b4a-106">Csatornák típusai</span><span class="sxs-lookup"><span data-stu-id="32b4a-106">Types of Channels</span></span>

<span data-ttu-id="32b4a-107">Dynamics 365 Commerce három különböző típusú csatornát támogat: kiskereskedelmi, hívásközpont és online csatornákat.</span><span class="sxs-lookup"><span data-stu-id="32b4a-107">Dynamics 365 Commerce supports three different channel types: retail, call center, and online channels.</span></span>

### <a name="retail-channels"></a><span data-ttu-id="32b4a-108">Kiskereskedelmi csatornák</span><span class="sxs-lookup"><span data-stu-id="32b4a-108">Retail channels</span></span>

<span data-ttu-id="32b4a-109">A kiskereskedelmi csatornák megszokott, fizikai üzleteket jelentik.</span><span class="sxs-lookup"><span data-stu-id="32b4a-109">Retail channels represent standard brick-and-mortar stores.</span></span> <span data-ttu-id="32b4a-110">Az üzletek saját pénztárgépekkel (POS), bevételi és kiadási számlákkal, valamint munkatársakkal rendelkezhetnek.</span><span class="sxs-lookup"><span data-stu-id="32b4a-110">Each store can have its own point of sale (POS) registers, income and expense accounts, and staff.</span></span> 

### <a name="call-center-channels"></a><span data-ttu-id="32b4a-111">Hívásközponti csatornák</span><span class="sxs-lookup"><span data-stu-id="32b4a-111">Call center channels</span></span>

<span data-ttu-id="32b4a-112">A hívásközpont-csatornák a hívásközpontok rendelés- és ügyfélkezelését jelentik.</span><span class="sxs-lookup"><span data-stu-id="32b4a-112">Call center channels represent call center order and customer management.</span></span>

### <a name="online-channels"></a><span data-ttu-id="32b4a-113">Online csatornák</span><span class="sxs-lookup"><span data-stu-id="32b4a-113">Online channels</span></span>

<span data-ttu-id="32b4a-114">Az online csatornák online e-kereskedelmi üzleteket jelentenek.</span><span class="sxs-lookup"><span data-stu-id="32b4a-114">Online channels represent online e-Commerce storefronts.</span></span> <span data-ttu-id="32b4a-115">Online csatorna létrehozása után létre kell hozni egy webhelyet a Microsoft Dynamics 365 Commerce webhelykészítő eszközével vagy más külső fél e-kereskedelmi megoldásával.</span><span class="sxs-lookup"><span data-stu-id="32b4a-115">Once an online channel is created, a site must be created using the Microsoft Dynamics 365 Commerce Site Builder tool or other third-party e-Commerce solution.</span></span>

## <a name="channel-setup-basics"></a><span data-ttu-id="32b4a-116">Csatorna beállítása – alapvető tudnivalók</span><span class="sxs-lookup"><span data-stu-id="32b4a-116">Channel setup basics</span></span>

<span data-ttu-id="32b4a-117">A csatorna beállítása a Commerce eszközben történik.</span><span class="sxs-lookup"><span data-stu-id="32b4a-117">Channel set up is performed in the Commerce tool.</span></span> <span data-ttu-id="32b4a-118">Minden csatornához tartozhatnak saját fizetési módok, árcsoportok, termékhierarchiák, szortimentek és termékek készlete.</span><span class="sxs-lookup"><span data-stu-id="32b4a-118">Each channel can have its own payment methods, price groups, product hierarchies, assortments, and set of products.</span></span> <span data-ttu-id="32b4a-119">Miután létrehozta a csatornát, rendelje hozzá az üzlet által kezelendő és értékesítendő termékeket.</span><span class="sxs-lookup"><span data-stu-id="32b4a-119">After you create a channel, you assign the products that you want it to carry and sell.</span></span> <span data-ttu-id="32b4a-120">Minden csatorna típusának egyedi funkciói lehetnek, amelyekhez konfigurálni kell.</span><span class="sxs-lookup"><span data-stu-id="32b4a-120">Each channel type has a unique set of features that may need to be configured.</span></span> <span data-ttu-id="32b4a-121">Például egy kiskereskedelmi csatornához alkalmazottakat, pénztárgépeket és vevőket kell hozzárendelni.</span><span class="sxs-lookup"><span data-stu-id="32b4a-121">For example, a retail channel needs assigned employees, registers, and customers.</span></span> <span data-ttu-id="32b4a-122">Az új csatorna létrehozása után társítani kell hozzá egy szervezeti hierarchiát.</span><span class="sxs-lookup"><span data-stu-id="32b4a-122">Once a new channel is created, it needs to be assigned to an organization hierarchy.</span></span>

## <a name="channel-setup-prerequisites"></a><span data-ttu-id="32b4a-123">Csatornák beállításának előfeltételei</span><span class="sxs-lookup"><span data-stu-id="32b4a-123">Channel setup prerequisites</span></span>

<span data-ttu-id="32b4a-124">A csatorna beállítása előtt be kell fejeznie a csatorna típusától függő néhány előfeltétel-feladatot.</span><span class="sxs-lookup"><span data-stu-id="32b4a-124">Before you can set up a channel, you must complete some prerequisite tasks based on the channel type.</span></span> <span data-ttu-id="32b4a-125">További tájékoztatás: [Csatornabeállítási előfeltételek](channels-prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="32b4a-125">For more information, see [Channel setup prerequisites](channels-prerequisites.md).</span></span>

## <a name="set-up-a-channel"></a><span data-ttu-id="32b4a-126">Csatorna beállítása</span><span class="sxs-lookup"><span data-stu-id="32b4a-126">Set up a channel</span></span>

<span data-ttu-id="32b4a-127">Az előfeltétel-feladatok végrehajtása után a további beállítási útmutató a következő hivatkozásokkal érhető el.</span><span class="sxs-lookup"><span data-stu-id="32b4a-127">After you complete the prerequisite tasks, for further setup instructions, use the following links.</span></span>

- [<span data-ttu-id="32b4a-128">Kiskereskedelmi csatorna beállítása</span><span class="sxs-lookup"><span data-stu-id="32b4a-128">Set up a retail channel</span></span>](channel-setup-retail.md)
- [<span data-ttu-id="32b4a-129">Hívásközpont csatorna beállítása</span><span class="sxs-lookup"><span data-stu-id="32b4a-129">Set up a call center channel</span></span>](channel-setup-callcenter.md)
- [<span data-ttu-id="32b4a-130">Online csatorna beállítása</span><span class="sxs-lookup"><span data-stu-id="32b4a-130">Set up an online channel</span></span>](channel-setup-online.md)

<!--
## Post-channel configuration

After you create a channel, you may need to complete some of the below tasks:

- [Add channel to an organizational hierarchy](add-channel-org-hierarchy.md)
- Set up fulfillment groups. (LINK TBD)
- Configure the POS registers for the store. (LINK TBD)
- Assign product assortments to the store. (LINK TBD)
- Process assortments to generate the list of products that are included in the assortment and to make the products available in the retail store. (LINK TBD)
- Send data such as number sequences, hardware profiles, and POS screen layouts to the Retail POS registers.(LINK TBD)
- Publish the retail store to send store data to Retail POS. (LINK TBD)
- Run the jobs to send the store data to Retail POS. (LINK TBD)
-->

## <a name="additional-resources"></a><span data-ttu-id="32b4a-131">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="32b4a-131">Additional resources</span></span>

[<span data-ttu-id="32b4a-132">Csatornák beállításának előfeltételei</span><span class="sxs-lookup"><span data-stu-id="32b4a-132">Channel setup prerequisites</span></span>](channels-prerequisites.md)

[<span data-ttu-id="32b4a-133">Kiskereskedelmi csatorna beállítása</span><span class="sxs-lookup"><span data-stu-id="32b4a-133">Set up a retail channel</span></span>](channel-setup-retail.md)
    
[<span data-ttu-id="32b4a-134">Online csatorna beállítása</span><span class="sxs-lookup"><span data-stu-id="32b4a-134">Set up an online channel</span></span>](channel-setup-online.md)

[<span data-ttu-id="32b4a-135">Hívásközpont csatorna beállítása</span><span class="sxs-lookup"><span data-stu-id="32b4a-135">Set up a call center channel</span></span>](channel-setup-callcenter.md)

[<span data-ttu-id="32b4a-136">Szervezeti hierarchiák beállítása</span><span class="sxs-lookup"><span data-stu-id="32b4a-136">Set up organization hierarchies</span></span>](channels-org-hierarchies.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]