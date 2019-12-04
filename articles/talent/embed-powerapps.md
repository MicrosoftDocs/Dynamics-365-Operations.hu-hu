---
title: Power Apps alkalmazások beágyazása a Dynamics 365 – Core HR alkalmazásban
description: Ez a témakör ismerteti annak a problémának a megoldását, amikor a Microsoft Power Apps menüelem eltűnik a Rendszerfelügyeleti modulból.
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
ms.openlocfilehash: 6d1b7f1dd71e6bcbf10c4d91fe33e9494b041a2c
ms.sourcegitcommit: ae0efac749ab34d423fac44d00a597801c143fbb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/22/2019
ms.locfileid: "2830209"
---
# <a name="embed-power-apps-apps-in-dynamics-365---core-hr"></a><span data-ttu-id="47c89-103">Power Apps alkalmazások beágyazása a Dynamics 365 – Core HR alkalmazásban</span><span class="sxs-lookup"><span data-stu-id="47c89-103">Embed Power Apps apps in Dynamics 365 - Core HR</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="47c89-104">**Kibocsátás**</span><span class="sxs-lookup"><span data-stu-id="47c89-104">**Issue**</span></span>

<span data-ttu-id="47c89-105">A **Power Apps** menüelem eltűnt a **Rendszerfelügyelet** modulból.</span><span class="sxs-lookup"><span data-stu-id="47c89-105">The **Power Apps** menu item has disappeared from the **System administration** module.</span></span>

<span data-ttu-id="47c89-106">**Ok**</span><span class="sxs-lookup"><span data-stu-id="47c89-106">**Cause**</span></span>

<span data-ttu-id="47c89-107">A felhasználói felület (UI) elrendezése megváltozott, a Microsoft Power Apps most már szerepel a szabványos testreszabási modellben.</span><span class="sxs-lookup"><span data-stu-id="47c89-107">The user interface (UI) design has been changed, and Microsoft Power Apps is now included in the standard personalization model.</span></span>

<span data-ttu-id="47c89-108">**Feloldás**</span><span class="sxs-lookup"><span data-stu-id="47c89-108">**Resolution**</span></span>

<span data-ttu-id="47c89-109">A Power Apps beágyazási módja megváltozott.</span><span class="sxs-lookup"><span data-stu-id="47c89-109">The way that Power Apps are embedded has been changed.</span></span> <span data-ttu-id="47c89-110">A Power Apps alkalmazást most a testreszabási modellen keresztül lehet hozzáadni.</span><span class="sxs-lookup"><span data-stu-id="47c89-110">Power Apps are now added through the personalization model.</span></span> <span data-ttu-id="47c89-111">A Power Apps a Microsoft Dynamics 365 Talent majdnem minden lapjához hozzáadható.</span><span class="sxs-lookup"><span data-stu-id="47c89-111">You can add Power Apps to almost all pages in Microsoft Dynamics 365 Talent.</span></span>

<span data-ttu-id="47c89-112">További információ a Power Apps Talent szolgáltatásban történő beágyazásáról: [A Microsoft Power Apps beágyazása](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/embed-power-apps).</span><span class="sxs-lookup"><span data-stu-id="47c89-112">For information about how to embed Power Apps in Talent, see [Embed Microsoft Power Apps](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/embed-power-apps).</span></span>

<span data-ttu-id="47c89-113">Minden Power Apps-vevőnek, aki beágyazott alkalmazásokat a módosítás előtt, már frissülnie kellett az új modellre.</span><span class="sxs-lookup"><span data-stu-id="47c89-113">Any Power Apps customer who embedded apps before the change should have been upgraded to the new model.</span></span>

<span data-ttu-id="47c89-114">A **Power Apps** gomb a Talent szolgáltatás majdnem minden oldalán megtalálható a jobb felső sarokban.</span><span class="sxs-lookup"><span data-stu-id="47c89-114">The **Power Apps** button is in the upper-right corner of almost every page in Talent.</span></span> <span data-ttu-id="47c89-115">Ezzel a gombbal lehetséges a Power Apps beszúrása.</span><span class="sxs-lookup"><span data-stu-id="47c89-115">You can use this button to insert Power Apps.</span></span>

<span data-ttu-id="47c89-116">Íme, egy példa.</span><span class="sxs-lookup"><span data-stu-id="47c89-116">Here is an example.</span></span>

1. <span data-ttu-id="47c89-117">Lépjen a **Személyzetkezelés \> Hivatkozások \> Dolgozók \> Alkalmazottak** menüpontra.</span><span class="sxs-lookup"><span data-stu-id="47c89-117">Go to **Personnel management \> Links \> Workers \> Employees**.</span></span>
2. <span data-ttu-id="47c89-118">Válassza ki a **Power Apps** gombot, majd válassza a **PowerApp beszúrása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="47c89-118">Select the **Power Apps** button, and then select **Insert a PowerApp**.</span></span>

    ![Power Apps gomb](media/png.png)

3. <span data-ttu-id="47c89-120">Töltse ki a mezőket a **PowerApp beszúrása** párbeszédpanelen.</span><span class="sxs-lookup"><span data-stu-id="47c89-120">Complete the fields in the **Insert a PowerApp** dialog box.</span></span>

    ![PowerApp beszúrása párbeszédablak](media/insert-powerapp.png)

<span data-ttu-id="47c89-122">A következő lépéseket is követheti.</span><span class="sxs-lookup"><span data-stu-id="47c89-122">Alternatively, follow these steps.</span></span>

1. <span data-ttu-id="47c89-123">Az oldal Művelet panelén a **Beállítások** lap **Személyre szabás** csoportjában válassza a **Képernyő személyre szabása** elemet.</span><span class="sxs-lookup"><span data-stu-id="47c89-123">On the page's Action Pane, on the **Options** tab, in the **Personalize** group, select **Personalize this form**.</span></span>

    ![Csoport személyre szabása a Beállítások lapon](media/options.png)

    <span data-ttu-id="47c89-125">Megjelenik a személyre szabási eszköztár.</span><span class="sxs-lookup"><span data-stu-id="47c89-125">The personalization toolbar appears.</span></span>

2. <span data-ttu-id="47c89-126">Az eszköztáron válassza a **Beszúrás \> PowerApp** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="47c89-126">On the toolbar, select **Insert \> PowerApp**.</span></span>

    ![A Power Apps alkalmazás beszúrása a személyre szabási eszköztár segítségével](media/powerapp-bar.png)
