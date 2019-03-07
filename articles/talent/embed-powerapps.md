---
title: PowerApps alkalmazások beágyazása a Core HR alkalmazásban
description: Ez a témakör ismerteti annak a problémának a megoldását, amikor a PowerApps menüelem eltűnik a Rendszerfelügyeleti modulból.
author: Darinkramer
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 197b553f0b202ee29ad42274e2c0e03446ec782c
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2019
ms.locfileid: "304713"
---
# <a name="embed-powerapps-apps-in-core-hr"></a><span data-ttu-id="ff648-103">PowerApps alkalmazások beágyazása a Core HR alkalmazásban</span><span class="sxs-lookup"><span data-stu-id="ff648-103">Embed PowerApps apps in Core HR</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="ff648-104">**Probléma**</span><span class="sxs-lookup"><span data-stu-id="ff648-104">**Issue**</span></span>

<span data-ttu-id="ff648-105">A **PowerApps** menüelem eltűnt a **Rendszerfelügyelet** modulból.</span><span class="sxs-lookup"><span data-stu-id="ff648-105">The **PowerApps** menu item has disappeared from the **System administration** module.</span></span>

<span data-ttu-id="ff648-106">**Ok**</span><span class="sxs-lookup"><span data-stu-id="ff648-106">**Cause**</span></span>

<span data-ttu-id="ff648-107">A felhasználói felület (UI) elrendezése megváltozott, a Microsoft PowerApps most már szerepel a szabványos testreszabási modellben.</span><span class="sxs-lookup"><span data-stu-id="ff648-107">The user interface (UI) design has been changed, and Microsoft PowerApps is now included in the standard personalization model.</span></span>

<span data-ttu-id="ff648-108">**Felbontás**</span><span class="sxs-lookup"><span data-stu-id="ff648-108">**Resolution**</span></span>

<span data-ttu-id="ff648-109">A PowerApps alkalmazások beágyazási módja megváltozott.</span><span class="sxs-lookup"><span data-stu-id="ff648-109">The way that PowerApps apps are embedded has been changed.</span></span> <span data-ttu-id="ff648-110">A PowerApps alkalmazásokat most a testreszabási modellen keresztül lehet hozzáadni.</span><span class="sxs-lookup"><span data-stu-id="ff648-110">PowerApps apps are now added through the personalization model.</span></span> <span data-ttu-id="ff648-111">Felvehet PowerApps alkalmazásokat a Microsoft Dynamics 365 for Talent majdnem minden lapjára.</span><span class="sxs-lookup"><span data-stu-id="ff648-111">You can add PowerApps apps to almost all pages in Microsoft Dynamics 365 for Talent.</span></span>

<span data-ttu-id="ff648-112">A PowerApps alkalmazások a Talent szolgáltatásban való beágyazásával kapcsolatos részletes tudnivalókat lásd: [PowerApps alkalmazások beágyazása](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/get-started/embed-power-apps).</span><span class="sxs-lookup"><span data-stu-id="ff648-112">For information about how to embed PowerApps apps in Talent, see [Embed PowerApps apps](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/get-started/embed-power-apps).</span></span>

<span data-ttu-id="ff648-113">Minden PowerApps-vevőnek, aki beágyazott alkalmazásokat a módosítás előtt, már frissülnie kellett az új modellre.</span><span class="sxs-lookup"><span data-stu-id="ff648-113">Any PowerApps customer who embedded apps before the change should have been upgraded to the new model.</span></span>

<span data-ttu-id="ff648-114">A **PowerApps** gomb a Talent szolgáltatás majdnem minden oldalán megtalálható a jobb felső sarokban.</span><span class="sxs-lookup"><span data-stu-id="ff648-114">The **PowerApps** button is in the upper-right corner of almost every page in Talent.</span></span> <span data-ttu-id="ff648-115">Ez a gomb segítségével beszúrhat egy PowerApps alkalmazást.</span><span class="sxs-lookup"><span data-stu-id="ff648-115">You can use this button to insert a PowerApps app.</span></span>

<span data-ttu-id="ff648-116">Íme, egy példa.</span><span class="sxs-lookup"><span data-stu-id="ff648-116">Here is an example.</span></span>

1. <span data-ttu-id="ff648-117">Lépjen a **Személyzetkezelés \> Hivatkozások \> Dolgozók \> Alkalmazottak** menüpontra.</span><span class="sxs-lookup"><span data-stu-id="ff648-117">Go to **Personnel management \> Links \> Workers \> Employees**.</span></span>
2. <span data-ttu-id="ff648-118">Válassza ki a **PowerApps** gombot, majd válassza a **PowerApp beszúrása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ff648-118">Select the **PowerApps** button, and then select **Insert a PowerApp**.</span></span>

    ![PowerApps gomb](media/png.png)

3. <span data-ttu-id="ff648-120">Töltse ki a mezőket a **PowerApp beszúrása** párbeszédpanelen.</span><span class="sxs-lookup"><span data-stu-id="ff648-120">Complete the fields in the **Insert a PowerApp** dialog box.</span></span>

    ![PowerApp beszúrása párbeszédablak](media/insert-powerapp.png)

<span data-ttu-id="ff648-122">A következő lépéseket is követheti.</span><span class="sxs-lookup"><span data-stu-id="ff648-122">Alternatively, follow these steps.</span></span>

1. <span data-ttu-id="ff648-123">Az oldal Művelet panelén a **Beállítások** lap **Személyre szabás** csoportjában válassza a **Képernyő személyre szabása** elemet.</span><span class="sxs-lookup"><span data-stu-id="ff648-123">On the page's Action Pane, on the **Options** tab, in the **Personalize** group, select **Personalize this form**.</span></span>

    ![Csoport személyre szabása a Beállítások lapon](media/options.png)

    <span data-ttu-id="ff648-125">Megjelenik a személyre szabási eszköztár.</span><span class="sxs-lookup"><span data-stu-id="ff648-125">The personalization toolbar appears.</span></span>

2. <span data-ttu-id="ff648-126">Az eszköztáron válassza a **Beszúrás \> PowerApp** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ff648-126">On the toolbar, select **Insert \> PowerApp**.</span></span>

    ![A PowerApps-alkalmazás beszúrása a személyre szabási eszköztár segítségével](media/powerapp-bar.png)
