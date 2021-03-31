---
title: Csatorna konfigurálása csatorna navigációs hierarchiájának használatára
description: Ez a témakör azt mutatja be, hogyan lehet konfigurálni egy csatornát a csatorna navigációs hierarchiájának használatára a Microsoft Dynamics 365 Commerce alkalmazásban.
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
ms.openlocfilehash: ceb6aa65c2ed5bc8d4224bdaf7095fba769181e8
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5220582"
---
# <a name="configure-a-channel-to-use-a-channel-navigation-hierarchy"></a><span data-ttu-id="e14a8-103">Csatorna konfigurálása csatorna navigációs hierarchiájának használatára</span><span class="sxs-lookup"><span data-stu-id="e14a8-103">Configure a channel to use a channel navigation hierarchy</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="e14a8-104">Ez a témakör azt mutatja be, hogyan lehet konfigurálni egy csatornát a csatorna navigációs hierarchiájának használatára a Microsoft Dynamics 365 Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="e14a8-104">This topic describes how to configure a channel to use a channel navigation hierarchy in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="e14a8-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="e14a8-105">Overview</span></span>

<span data-ttu-id="e14a8-106">A csatornanavigációs hierarchiák kategóriákba rendezik a termékeket, így a termékek böngészhetők az e-kereskedelmi helyeken webhelyeken vagy az pénztárakban (POS).</span><span class="sxs-lookup"><span data-stu-id="e14a8-106">Channel navigation hierarchies organize products into categories so that the products can be browsed on an e-Commerce site or at points of sale (POS).</span></span> <span data-ttu-id="e14a8-107">A Kiskereskedelmi és online csatornákat csatornanavigációs hierarchiákkal kell konfigurálni.</span><span class="sxs-lookup"><span data-stu-id="e14a8-107">Retail and online channels must be configured with channel navigation hierarchies.</span></span>

## <a name="configure-the-channel"></a><span data-ttu-id="e14a8-108">A csatorna konfigurálása</span><span class="sxs-lookup"><span data-stu-id="e14a8-108">Configure the channel</span></span>

<span data-ttu-id="e14a8-109">Egy csatorna navigációs hierarchia használatára vonatkozó konfigurálásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="e14a8-109">To configure a channel to use a channel navigation hierarchy, follow these steps.</span></span>

1. <span data-ttu-id="e14a8-110">A navigációs ablaktáblán ugorjon a **Modulok \> Kiskereskedelem és kereskedelem \> Csatornabeállítás \> Csatornakategóriák és termékattribútumok** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="e14a8-110">In the navigation pane, go to **Modules \> Retail and commerce \> Channel setup \> Channel categories and product attributes**.</span></span>
1. <span data-ttu-id="e14a8-111">Válassza ki a konfigurálni kívánt csatornát.</span><span class="sxs-lookup"><span data-stu-id="e14a8-111">Select the channel to configure.</span></span>
1. <span data-ttu-id="e14a8-112">Válassza a műveleti ablakban az **Attribútum-metaadatok beállítása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="e14a8-112">On the action pane, select **Set attribute metadata**.</span></span>
1. <span data-ttu-id="e14a8-113">A **Kategóriahierarchia** legördülő listában válassza ki a megfelelő csatornanavigációs hierarchiát.</span><span class="sxs-lookup"><span data-stu-id="e14a8-113">In the **Category hierarchy** drop-down list, select the appropriate channel navigation hierarchy.</span></span>
1. <span data-ttu-id="e14a8-114">A műveleti ablaktáblán válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="e14a8-114">On the action pane, select **Save**.</span></span>
1. <span data-ttu-id="e14a8-115">Az **Attribútum csoportban** adja meg azokat az attribútum-csoportokat, amelyek az összes csomópont globális attribútumai lesznek.</span><span class="sxs-lookup"><span data-stu-id="e14a8-115">Under **Attribute group**, add any attribute groups that will be global attributes for all nodes.</span></span>

<span data-ttu-id="e14a8-116">A következő kép bemutatja egy csatorna konfigurálását csatorna navigációs hierarchia használatára.</span><span class="sxs-lookup"><span data-stu-id="e14a8-116">The following image shows how to configure a channel to use a channel navigation hierarchy.</span></span>

![Példa csatorna konfigurálására](media/configure-channel-hierarchy-1.png)

## <a name="set-attribute-metadata"></a><span data-ttu-id="e14a8-118">Attribútum-metaadatok beállítása</span><span class="sxs-lookup"><span data-stu-id="e14a8-118">Set attribute metadata</span></span>

<span data-ttu-id="e14a8-119">Az attribútum metaadatainak beállítása lehetővé teszi az egyes csomópontok attribútumainak konfigurálását.</span><span class="sxs-lookup"><span data-stu-id="e14a8-119">Setting the attribute metadata will allow configuration of attributes on each node.</span></span>

<span data-ttu-id="e14a8-120">Az attribútum-metaadatok beállításához hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="e14a8-120">To set attribute metadata, follow these steps.</span></span>

1. <span data-ttu-id="e14a8-121">Válassza a műveleti ablakban az **Attribútum-metaadatok beállítása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="e14a8-121">On the action pane, select **Set attribute metadata**.</span></span>
1. <span data-ttu-id="e14a8-122">Mindegyik csomóponthoz válassz a **Csatorna termékattribútumai** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="e14a8-122">For each node select **Channel product attributes**.</span></span>
1. <span data-ttu-id="e14a8-123">Az **Attribútum megjelenítése a csatornán** lehetőséget állítsa be **Igen** értékre, és a **Finomítható** elemet is **Igen** értékre, ha engedélyezni szeretné a finomítókat a csatornán.</span><span class="sxs-lookup"><span data-stu-id="e14a8-123">Set **Show attribute on channel** to **Yes** and **Can be refined** to **Yes**, to enable refiners on that channel.</span></span>
1. <span data-ttu-id="e14a8-124">A csomópontok kívánt beállításainak konfigurálása után a **Művelet** ablaktáblában válassza a **Mentés** gombot a mentéshez.</span><span class="sxs-lookup"><span data-stu-id="e14a8-124">After configuring each node as desired, on the **Action pane**, select the **Save** button to save.</span></span>
1. <span data-ttu-id="e14a8-125">Válassza ki a jobb felső sarokban látható **X** szimbólumot, ha a képernyőt a visszalépéshez a **Csatornakategóriák és termékattribútumok** lapra.</span><span class="sxs-lookup"><span data-stu-id="e14a8-125">Select the **X** in the top right corner to exit this screen back to the **Channel categories and product attributes** page.</span></span>

<span data-ttu-id="e14a8-126">A következő képen látható csatorna termékattribútumok halmazának példája, amelyek konfigurálva vannak egy csatornakategória-csomóponton.</span><span class="sxs-lookup"><span data-stu-id="e14a8-126">The following image shows an example set of channel product attributes configured on a channel category node.</span></span>

![Csatorna attribútumok egy csatornakategória-csomóponton](media/configure-channel-hierarchy-2.png)

## <a name="publish-changes"></a><span data-ttu-id="e14a8-128">Változások közzététele</span><span class="sxs-lookup"><span data-stu-id="e14a8-128">Publish changes</span></span>

<span data-ttu-id="e14a8-129">A változtatások életbe lépéséhez közzé kell tennie a változtatásokat.</span><span class="sxs-lookup"><span data-stu-id="e14a8-129">For changes to take effect, you will need to publish the changes.</span></span>

<span data-ttu-id="e14a8-130">A változatások közzétételéhez kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="e14a8-130">To publish changes, follow these steps.</span></span>

1. <span data-ttu-id="e14a8-131">A műveleti ablaktáblán válassza a **Csatorna frissítéseinek közzététele** elemet.</span><span class="sxs-lookup"><span data-stu-id="e14a8-131">On the action pane, select **Publish channel updates**.</span></span>
1. <span data-ttu-id="e14a8-132">A **Csatorna frissítéseinek közzététele** ablaktáblán válassza az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="e14a8-132">In the **Publish channel updates** pane, select **OK**.</span></span>

<span data-ttu-id="e14a8-133">A következő képen a csatornák frissítéseinek közzétételének módja látható.</span><span class="sxs-lookup"><span data-stu-id="e14a8-133">The following image shows how to publish channel updates.</span></span>

![Csatornafrissítések közzététele](media/configure-channel-hierarchy-3.png)

## <a name="additional-resources"></a><span data-ttu-id="e14a8-135">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="e14a8-135">Additional resources</span></span>

[<span data-ttu-id="e14a8-136">Csatorna navigációs hierarchiájának létrehozása</span><span class="sxs-lookup"><span data-stu-id="e14a8-136">Create a channel navigation hierarchy</span></span>](create-channel-hierarchy.md)




[!INCLUDE[footer-include](../includes/footer-banner.md)]