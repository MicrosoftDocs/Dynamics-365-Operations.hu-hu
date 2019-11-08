---
title: PowerApps alkalmazások beágyazása a Dynamics 365 – Core HR alkalmazásban
description: Ez a témakör ismerteti annak a problémának a megoldását, amikor a PowerApps menüelem eltűnik a Rendszerfelügyeleti modulból.
author: andreabichsel
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.openlocfilehash: b510c10ebfcf4939eb2e1297972d27aa1812ae5a
ms.sourcegitcommit: 75db3b75d35d27034f9b56e7119c9d0cb7666830
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/03/2019
ms.locfileid: "2551003"
---
# <a name="embed-powerapps-apps-in-dynamics-365---core-hr"></a><span data-ttu-id="dbe04-103">PowerApps alkalmazások beágyazása a Dynamics 365 – Core HR alkalmazásban</span><span class="sxs-lookup"><span data-stu-id="dbe04-103">Embed PowerApps apps in Dynamics 365 - Core HR</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="dbe04-104">**Kibocsátás**</span><span class="sxs-lookup"><span data-stu-id="dbe04-104">**Issue**</span></span>

<span data-ttu-id="dbe04-105">A **PowerApps** menüelem eltűnt a **Rendszerfelügyelet** modulból.</span><span class="sxs-lookup"><span data-stu-id="dbe04-105">The **PowerApps** menu item has disappeared from the **System administration** module.</span></span>

<span data-ttu-id="dbe04-106">**Ok**</span><span class="sxs-lookup"><span data-stu-id="dbe04-106">**Cause**</span></span>

<span data-ttu-id="dbe04-107">A felhasználói felület (UI) elrendezése megváltozott, a Microsoft PowerApps most már szerepel a szabványos testreszabási modellben.</span><span class="sxs-lookup"><span data-stu-id="dbe04-107">The user interface (UI) design has been changed, and Microsoft PowerApps is now included in the standard personalization model.</span></span>

<span data-ttu-id="dbe04-108">**Feloldás**</span><span class="sxs-lookup"><span data-stu-id="dbe04-108">**Resolution**</span></span>

<span data-ttu-id="dbe04-109">A PowerApps alkalmazások beágyazási módja megváltozott.</span><span class="sxs-lookup"><span data-stu-id="dbe04-109">The way that PowerApps apps are embedded has been changed.</span></span> <span data-ttu-id="dbe04-110">A PowerApps alkalmazásokat most a testreszabási modellen keresztül lehet hozzáadni.</span><span class="sxs-lookup"><span data-stu-id="dbe04-110">PowerApps apps are now added through the personalization model.</span></span> <span data-ttu-id="dbe04-111">Felvehet PowerApps alkalmazásokat a Microsoft Dynamics 365 Talent majdnem minden lapjára.</span><span class="sxs-lookup"><span data-stu-id="dbe04-111">You can add PowerApps apps to almost all pages in Microsoft Dynamics 365 Talent.</span></span>

<span data-ttu-id="dbe04-112">A PowerApps alkalmazások a Talent szolgáltatásban való beágyazásával kapcsolatos részletes tudnivalókat lásd: [A PowerApps alkalmazások beágyazása](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/embed-power-apps).</span><span class="sxs-lookup"><span data-stu-id="dbe04-112">For information about how to embed PowerApps apps in Talent, see [Embed PowerApps apps](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/embed-power-apps).</span></span>

<span data-ttu-id="dbe04-113">Minden PowerApps-vevőnek, aki beágyazott alkalmazásokat a módosítás előtt, már frissülnie kellett az új modellre.</span><span class="sxs-lookup"><span data-stu-id="dbe04-113">Any PowerApps customer who embedded apps before the change should have been upgraded to the new model.</span></span>

<span data-ttu-id="dbe04-114">A **PowerApps** gomb a Talent szolgáltatás majdnem minden oldalán megtalálható a jobb felső sarokban.</span><span class="sxs-lookup"><span data-stu-id="dbe04-114">The **PowerApps** button is in the upper-right corner of almost every page in Talent.</span></span> <span data-ttu-id="dbe04-115">Ez a gomb segítségével beszúrhat egy PowerApps alkalmazást.</span><span class="sxs-lookup"><span data-stu-id="dbe04-115">You can use this button to insert a PowerApps app.</span></span>

<span data-ttu-id="dbe04-116">Íme, egy példa.</span><span class="sxs-lookup"><span data-stu-id="dbe04-116">Here is an example.</span></span>

1. <span data-ttu-id="dbe04-117">Lépjen a **Személyzetkezelés \> Hivatkozások \> Dolgozók \> Alkalmazottak** menüpontra.</span><span class="sxs-lookup"><span data-stu-id="dbe04-117">Go to **Personnel management \> Links \> Workers \> Employees**.</span></span>
2. <span data-ttu-id="dbe04-118">Válassza ki a **PowerApps** gombot, majd válassza a **PowerApp beszúrása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="dbe04-118">Select the **PowerApps** button, and then select **Insert a PowerApp**.</span></span>

    ![PowerApps gomb](media/png.png)

3. <span data-ttu-id="dbe04-120">Töltse ki a mezőket a **PowerApp beszúrása** párbeszédpanelen.</span><span class="sxs-lookup"><span data-stu-id="dbe04-120">Complete the fields in the **Insert a PowerApp** dialog box.</span></span>

    ![PowerApp beszúrása párbeszédablak](media/insert-powerapp.png)

<span data-ttu-id="dbe04-122">A következő lépéseket is követheti.</span><span class="sxs-lookup"><span data-stu-id="dbe04-122">Alternatively, follow these steps.</span></span>

1. <span data-ttu-id="dbe04-123">Az oldal Művelet panelén a **Beállítások** lap **Személyre szabás** csoportjában válassza a **Képernyő személyre szabása** elemet.</span><span class="sxs-lookup"><span data-stu-id="dbe04-123">On the page's Action Pane, on the **Options** tab, in the **Personalize** group, select **Personalize this form**.</span></span>

    ![Csoport személyre szabása a Beállítások lapon](media/options.png)

    <span data-ttu-id="dbe04-125">Megjelenik a személyre szabási eszköztár.</span><span class="sxs-lookup"><span data-stu-id="dbe04-125">The personalization toolbar appears.</span></span>

2. <span data-ttu-id="dbe04-126">Az eszköztáron válassza a **Beszúrás \> PowerApp** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="dbe04-126">On the toolbar, select **Insert \> PowerApp**.</span></span>

    ![A PowerApps alkalmazás beszúrása a személyre szabási eszköztár segítségével](media/powerapp-bar.png)
