---
title: Kísérlet állapotának áttekintése
description: Ez a témakör azt mutatja be, hogy a Dynamics 365 Commerce rendszeren belüli kísérletezési életciklusban mi lehet egy adott kísérlet állapota.
author: sushma-rao
manager: AnnBe
ms.date: 10/21/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: sushmar
ms.search.validFrom: 2020-09-30
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: ae459ddaf947db6c3de2602a706390edab49efa1
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5250858"
---
# <a name="review-the-status-of-an-experiment"></a><span data-ttu-id="04e0a-103">Kísérlet állapotának áttekintése</span><span class="sxs-lookup"><span data-stu-id="04e0a-103">Review the status of an experiment</span></span>
<span data-ttu-id="04e0a-104">A kísérletek Dynamics 365 Commerce rendszerben való beállítása és futtatása számos lépést igényel.</span><span class="sxs-lookup"><span data-stu-id="04e0a-104">There are many steps involved in setting up and running an experiment in Dynamics 365 Commerce.</span></span> <span data-ttu-id="04e0a-105">A kísérletezési életciklussal kapcsolatos tudnivalókért lásd: [Kísérletezés a Dynamics 365 Commerce rendszerben](experimentation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="04e0a-105">For information about the experimentation lifecycle, see [Experimentation in Dynamics 365 Commerce](experimentation-overview.md).</span></span>

<span data-ttu-id="04e0a-106">Ha meg szeretné tudni, hol tart egy kísérlet az életciklusban, a Commerce webhelykészítőben lépjen a **Kísérletek** fülre a bal oldali navigációs panelen.</span><span class="sxs-lookup"><span data-stu-id="04e0a-106">To learn where an experiment is in the lifecycle, in Commerce site builder select **Experiments** in the left navigation pane.</span></span> <span data-ttu-id="04e0a-107">A kísérletek listája az egyes kísérletek állapotával együtt megjelenik a Commerce modulban és a kísérletek létrehozásához, változatok hozzárendeléséhez és adatok elemzésére használt harmadik fél szolgáltatásban is.</span><span class="sxs-lookup"><span data-stu-id="04e0a-107">A list of experiments is displayed with the status of each experiment in both Commerce and the third-party service that is being used to enable the creation of experiments, assign variations, and analyze data.</span></span>

<span data-ttu-id="04e0a-108">A **Commerce állapot** oszlopban a következő értékek jelenhetnek meg.</span><span class="sxs-lookup"><span data-stu-id="04e0a-108">In the **Commerce status** column, the following values may be displayed.</span></span> 
- <span data-ttu-id="04e0a-109">**Piszkozat** – A kísérletet egy Commerce modulon belüli oldalhoz vagy töredékhez csatlakoztatták, és éppen a szerkesztése tart.</span><span class="sxs-lookup"><span data-stu-id="04e0a-109">**Draft** - The experiment is connected to a page or fragment in Commerce and is being edited.</span></span>
- <span data-ttu-id="04e0a-110">**Közzétéve** – A kísérlet változatai készen állnak a webhelyen való megjelenítésre.</span><span class="sxs-lookup"><span data-stu-id="04e0a-110">**Published** - The experiment variations are ready to be displayed on your website.</span></span> <span data-ttu-id="04e0a-111">Ha a kísérlet a harmadik féltől származó szolgáltatásban fut, akkor a webhely felhasználói az oldal vagy töredék harmadik fél szolgáltatás által kiválasztott változatát láthatják.</span><span class="sxs-lookup"><span data-stu-id="04e0a-111">If the experiment is running in the third-party service, website users will see a variation of the page or fragment as selected by the third-party service.</span></span>
- <span data-ttu-id="04e0a-112">**Nem közzétett** – A kísérlet már nem érhető el a webhelyen.</span><span class="sxs-lookup"><span data-stu-id="04e0a-112">**Unpublished** - The experiment is no longer available on your website.</span></span> <span data-ttu-id="04e0a-113">A webhely felhasználói csak az oldal vagy töredék alapértelmezett változatát láthatják, ha a kísérlet harmadik fél szolgáltatásban fut.</span><span class="sxs-lookup"><span data-stu-id="04e0a-113">Website users will only see the default version of the page or fragment even if the experiment is running in the third-party service.</span></span>
- <span data-ttu-id="04e0a-114">**Befejezett** – A kísérlet végbement, és a változatot élő állapotba léptették elő a webhely összes felhasználója számára.</span><span class="sxs-lookup"><span data-stu-id="04e0a-114">**Completed** - The experiment has run its course and a variation was promoted to live for all website users.</span></span>

<span data-ttu-id="04e0a-115">Hasonlóképpen a **Harmadik fél állapot** oszlopban a következő értékek jelenhetnek meg annak jelzésére, hogy milyen állapotúak a kísérletek a harmadik fél szolgáltatásban.</span><span class="sxs-lookup"><span data-stu-id="04e0a-115">Similarly, in the **third-party status** column, the following values may be displayed to indicate what status the experiments are in the third-party service.</span></span>
- <span data-ttu-id="04e0a-116">**Piszkozat** – A kísérletet a harmadik fél szolgáltatásban beállították, de még nem indították el.</span><span class="sxs-lookup"><span data-stu-id="04e0a-116">**Draft** - The experiment is set up in the third-party service but hasn't been started.</span></span>
- <span data-ttu-id="04e0a-117">**Fut** – A kísérletet elindították a harmadik fél szolgáltatásban, és éppen adatokat gyűjt.</span><span class="sxs-lookup"><span data-stu-id="04e0a-117">**Running** - The experiment was started in the third-party service and is collecting data.</span></span>
- <span data-ttu-id="04e0a-118">**Szüneteltetve** – A kísérlet szüneteltetve van, és nem gyűjt adatokat.</span><span class="sxs-lookup"><span data-stu-id="04e0a-118">**Paused** - The experiment is paused and not collecting data.</span></span> <span data-ttu-id="04e0a-119">A kísérletet folytatnia kell ahhoz, hogy újra elkezdjen adatokat gyűjteni.</span><span class="sxs-lookup"><span data-stu-id="04e0a-119">You must resume the experiment for it to collect data again.</span></span>
- <span data-ttu-id="04e0a-120">**Archivált** – A kísérlet végbement, és későbbi kikereshetőség érdekében katalogizálták a harmadik fél szolgáltatásban.</span><span class="sxs-lookup"><span data-stu-id="04e0a-120">**Archived** - The experiment has run its course and has been cataloged in the third-party service for future reference.</span></span>

<span data-ttu-id="04e0a-121">Az alábbi ábra a két állapotot mutatja be, valamint azt, hogy hogyan kapcsolódnak egymáshoz.</span><span class="sxs-lookup"><span data-stu-id="04e0a-121">The diagram below shows both sets of statuses and how they relate to each other.</span></span>

<span data-ttu-id="04e0a-122">[ ![Kísérletezés állapotai](./media/experimentation_statuses.svg) ](./media/experimentation_statuses.svg#lightbox)</span><span class="sxs-lookup"><span data-stu-id="04e0a-122">[ ![Experimentation statuses](./media/experimentation_statuses.svg) ](./media/experimentation_statuses.svg#lightbox)</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]