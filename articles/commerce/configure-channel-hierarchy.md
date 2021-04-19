---
title: Csatorna konfigurálása csatorna navigációs hierarchiájának használatára
description: Ez a témakör azt mutatja be, hogyan lehet konfigurálni egy csatornát a csatorna navigációs hierarchiájának használatára a Microsoft Dynamics 365 Commerce alkalmazásban.
author: samjarawan
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 94d38c5c3a091263b310f346f839e1a67d6c0609
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5796124"
---
# <a name="configure-a-channel-to-use-a-channel-navigation-hierarchy"></a><span data-ttu-id="773c2-103">Csatorna konfigurálása csatorna navigációs hierarchiájának használatára</span><span class="sxs-lookup"><span data-stu-id="773c2-103">Configure a channel to use a channel navigation hierarchy</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="773c2-104">Ez a témakör azt mutatja be, hogyan lehet konfigurálni egy csatornát a csatorna navigációs hierarchiájának használatára a Microsoft Dynamics 365 Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="773c2-104">This topic describes how to configure a channel to use a channel navigation hierarchy in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="773c2-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="773c2-105">Overview</span></span>

<span data-ttu-id="773c2-106">A csatornanavigációs hierarchiák kategóriákba rendezik a termékeket, így a termékek böngészhetők az e-kereskedelmi helyeken webhelyeken vagy az pénztárakban (POS).</span><span class="sxs-lookup"><span data-stu-id="773c2-106">Channel navigation hierarchies organize products into categories so that the products can be browsed on an e-Commerce site or at points of sale (POS).</span></span> <span data-ttu-id="773c2-107">A Kiskereskedelmi és online csatornákat csatornanavigációs hierarchiákkal kell konfigurálni.</span><span class="sxs-lookup"><span data-stu-id="773c2-107">Retail and online channels must be configured with channel navigation hierarchies.</span></span>

## <a name="configure-the-channel"></a><span data-ttu-id="773c2-108">A csatorna konfigurálása</span><span class="sxs-lookup"><span data-stu-id="773c2-108">Configure the channel</span></span>

<span data-ttu-id="773c2-109">Egy csatorna navigációs hierarchia használatára vonatkozó konfigurálásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="773c2-109">To configure a channel to use a channel navigation hierarchy, follow these steps.</span></span>

1. <span data-ttu-id="773c2-110">A navigációs ablaktáblán ugorjon a **Modulok \> Kiskereskedelem és kereskedelem \> Csatornabeállítás \> Csatornakategóriák és termékattribútumok** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="773c2-110">In the navigation pane, go to **Modules \> Retail and commerce \> Channel setup \> Channel categories and product attributes**.</span></span>
1. <span data-ttu-id="773c2-111">Válassza ki a konfigurálni kívánt csatornát.</span><span class="sxs-lookup"><span data-stu-id="773c2-111">Select the channel to configure.</span></span>
1. <span data-ttu-id="773c2-112">Válassza a műveleti ablakban az **Attribútum-metaadatok beállítása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="773c2-112">On the action pane, select **Set attribute metadata**.</span></span>
1. <span data-ttu-id="773c2-113">A **Kategóriahierarchia** legördülő listában válassza ki a megfelelő csatornanavigációs hierarchiát.</span><span class="sxs-lookup"><span data-stu-id="773c2-113">In the **Category hierarchy** drop-down list, select the appropriate channel navigation hierarchy.</span></span>
1. <span data-ttu-id="773c2-114">A műveleti ablaktáblán válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="773c2-114">On the action pane, select **Save**.</span></span>
1. <span data-ttu-id="773c2-115">Az **Attribútum csoportban** adja meg azokat az attribútum-csoportokat, amelyek az összes csomópont globális attribútumai lesznek.</span><span class="sxs-lookup"><span data-stu-id="773c2-115">Under **Attribute group**, add any attribute groups that will be global attributes for all nodes.</span></span>

<span data-ttu-id="773c2-116">A következő kép bemutatja egy csatorna konfigurálását csatorna navigációs hierarchia használatára.</span><span class="sxs-lookup"><span data-stu-id="773c2-116">The following image shows how to configure a channel to use a channel navigation hierarchy.</span></span>

![Példa csatorna konfigurálására](media/configure-channel-hierarchy-1.png)

## <a name="set-attribute-metadata"></a><span data-ttu-id="773c2-118">Attribútum-metaadatok beállítása</span><span class="sxs-lookup"><span data-stu-id="773c2-118">Set attribute metadata</span></span>

<span data-ttu-id="773c2-119">Az attribútum metaadatainak beállítása lehetővé teszi az egyes csomópontok attribútumainak konfigurálását.</span><span class="sxs-lookup"><span data-stu-id="773c2-119">Setting the attribute metadata will allow configuration of attributes on each node.</span></span>

<span data-ttu-id="773c2-120">Az attribútum-metaadatok beállításához hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="773c2-120">To set attribute metadata, follow these steps.</span></span>

1. <span data-ttu-id="773c2-121">Válassza a műveleti ablakban az **Attribútum-metaadatok beállítása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="773c2-121">On the action pane, select **Set attribute metadata**.</span></span>
1. <span data-ttu-id="773c2-122">Mindegyik csomóponthoz válassz a **Csatorna termékattribútumai** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="773c2-122">For each node select **Channel product attributes**.</span></span>
1. <span data-ttu-id="773c2-123">Az **Attribútum megjelenítése a csatornán** lehetőséget állítsa be **Igen** értékre, és a **Finomítható** elemet is **Igen** értékre, ha engedélyezni szeretné a finomítókat a csatornán.</span><span class="sxs-lookup"><span data-stu-id="773c2-123">Set **Show attribute on channel** to **Yes** and **Can be refined** to **Yes**, to enable refiners on that channel.</span></span>
1. <span data-ttu-id="773c2-124">A csomópontok kívánt beállításainak konfigurálása után a **Művelet** ablaktáblában válassza a **Mentés** gombot a mentéshez.</span><span class="sxs-lookup"><span data-stu-id="773c2-124">After configuring each node as desired, on the **Action pane**, select the **Save** button to save.</span></span>
1. <span data-ttu-id="773c2-125">Válassza ki a jobb felső sarokban látható **X** szimbólumot, ha a képernyőt a visszalépéshez a **Csatornakategóriák és termékattribútumok** lapra.</span><span class="sxs-lookup"><span data-stu-id="773c2-125">Select the **X** in the top right corner to exit this screen back to the **Channel categories and product attributes** page.</span></span>

<span data-ttu-id="773c2-126">A következő képen látható csatorna termékattribútumok halmazának példája, amelyek konfigurálva vannak egy csatornakategória-csomóponton.</span><span class="sxs-lookup"><span data-stu-id="773c2-126">The following image shows an example set of channel product attributes configured on a channel category node.</span></span>

![Csatorna attribútumok egy csatornakategória-csomóponton](media/configure-channel-hierarchy-2.png)

## <a name="publish-changes"></a><span data-ttu-id="773c2-128">Változások közzététele</span><span class="sxs-lookup"><span data-stu-id="773c2-128">Publish changes</span></span>

<span data-ttu-id="773c2-129">A változtatások életbe lépéséhez közzé kell tennie a változtatásokat.</span><span class="sxs-lookup"><span data-stu-id="773c2-129">For changes to take effect, you will need to publish the changes.</span></span>

<span data-ttu-id="773c2-130">A változatások közzétételéhez kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="773c2-130">To publish changes, follow these steps.</span></span>

1. <span data-ttu-id="773c2-131">A műveleti ablaktáblán válassza a **Csatorna frissítéseinek közzététele** elemet.</span><span class="sxs-lookup"><span data-stu-id="773c2-131">On the action pane, select **Publish channel updates**.</span></span>
1. <span data-ttu-id="773c2-132">A **Csatorna frissítéseinek közzététele** ablaktáblán válassza az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="773c2-132">In the **Publish channel updates** pane, select **OK**.</span></span>

<span data-ttu-id="773c2-133">A következő képen a csatornák frissítéseinek közzétételének módja látható.</span><span class="sxs-lookup"><span data-stu-id="773c2-133">The following image shows how to publish channel updates.</span></span>

![Csatornafrissítések közzététele](media/configure-channel-hierarchy-3.png)

## <a name="additional-resources"></a><span data-ttu-id="773c2-135">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="773c2-135">Additional resources</span></span>

[<span data-ttu-id="773c2-136">Csatorna navigációs hierarchiájának létrehozása</span><span class="sxs-lookup"><span data-stu-id="773c2-136">Create a channel navigation hierarchy</span></span>](create-channel-hierarchy.md)




[!INCLUDE[footer-include](../includes/footer-banner.md)]