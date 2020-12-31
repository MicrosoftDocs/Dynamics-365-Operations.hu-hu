---
title: Javaslat tárgyieszköz-beszerzésekre
description: Ez a témakör leírja, hogyan szerezhető be tárgyi eszköz a Tárgyi eszközök naplójában található Beszerzési javaslat segítségével.
author: saraschi2
manager: AnnBe
ms.date: 07/27/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetTable, AssetBook, LedgerJournalTable, LedgerJournalTransAsset, SysQueryForm
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0997af638c141661afb677e2407a90a883168aed
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4443833"
---
# <a name="propose-fixed-asset-acquisitions"></a><span data-ttu-id="01947-103">Javaslat tárgyieszköz-beszerzésekre</span><span class="sxs-lookup"><span data-stu-id="01947-103">Propose fixed asset acquisitions</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="01947-104">Ez a témakör leírja, hogyan szerezhető be tárgyi eszköz a Tárgyi eszközök naplójában található Beszerzési javaslat segítségével.</span><span class="sxs-lookup"><span data-stu-id="01947-104">This topic describes how to acquire a fixed asset using the acquisition proposal in the Fixed assets journal.</span></span> <span data-ttu-id="01947-105">Ez a könyvelői szerepkört és a bemutató adatokat használja a USMF jogi személyhez.</span><span class="sxs-lookup"><span data-stu-id="01947-105">It uses the accountant role and demo data for the USMF legal entity.</span></span> <span data-ttu-id="01947-106">Ha tárgyi eszköz javaslati naplón keresztül kíván beszerezni egy tárgyi eszközt, először létre kell hoznia a tárgyi eszköz rekordját, majd meg kell határoznia a beszerzési árat a tárgyi eszköz könyvében.</span><span class="sxs-lookup"><span data-stu-id="01947-106">To acquire a fixed asset through a fixed asset proposal journal, you must first create the fixed asset record, and then define the acquisition price in the asset book.</span></span>

1. <span data-ttu-id="01947-107">A navigációs ablaktáblán nyissa meg a **Modulok > Tárgyi eszközök > Naplóbejegyzések > Tárgyi eszközök naplója** elemet.</span><span class="sxs-lookup"><span data-stu-id="01947-107">In the navigation pane, go to **Modules > Fixed assets > Journal entries > Fixed assets journal**.</span></span>
2. <span data-ttu-id="01947-108">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="01947-108">Select **New**.</span></span>
3. <span data-ttu-id="01947-109">A **Név** mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="01947-109">In the **Name** field, enter or select a value.</span></span>
4. <span data-ttu-id="01947-110">A Műveleti ablaktáblán válassza a **Sorok** elemet.</span><span class="sxs-lookup"><span data-stu-id="01947-110">In the action pane, select **Lines**.</span></span>
5. <span data-ttu-id="01947-111">Válassza a **Javaslatok** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="01947-111">Select **Proposals**.</span></span>
6. <span data-ttu-id="01947-112">Válassza a **Beszerzési javaslat** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="01947-112">Select **Acquisition proposal**.</span></span>
7. <span data-ttu-id="01947-113">Válassza a **Szűrő** elemet.</span><span class="sxs-lookup"><span data-stu-id="01947-113">Select **Filter**.</span></span> <span data-ttu-id="01947-114">A korábbi értékek törléséhez kattintson az **Alaphelyzetbe állítás** pontra.</span><span class="sxs-lookup"><span data-stu-id="01947-114">Select **Reset** to clear out previous values.</span></span>
8. <span data-ttu-id="01947-115">Válassza ki a **Tárgyieszköz-szám** elnevezésű sort.</span><span class="sxs-lookup"><span data-stu-id="01947-115">Select the **Fixed asset number** row.</span></span>
9. <span data-ttu-id="01947-116">A **Feltétel** mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="01947-116">In the **Criteria** field, enter or select a value.</span></span> <span data-ttu-id="01947-117">Állítsa be a javaslat kapcsán beszerezni kívánt tárgyi eszközökre vonatkozó további feltételeket.</span><span class="sxs-lookup"><span data-stu-id="01947-117">Set the remaining criteria for the fixed assets that you want to acquire with this proposal.</span></span>  
10. <span data-ttu-id="01947-118">A panelből való kilépéshez nyomja meg kétszer az **OK** gombot.</span><span class="sxs-lookup"><span data-stu-id="01947-118">Select **OK** twice to exit out of the pane.</span></span>
- <span data-ttu-id="01947-119">Erősítse meg a létrehozott tranzakciós sorokat.</span><span class="sxs-lookup"><span data-stu-id="01947-119">Verify the transaction lines created.</span></span>  
- <span data-ttu-id="01947-120">A beszerzési javaslat kizárólag az értékmodellben beállított beszerzési dátummal és beszerzési árral rendelkező tárgyi eszközöket veszi figyelembe.</span><span class="sxs-lookup"><span data-stu-id="01947-120">Only fixed assets with the acquisition date and acquisition price set on the book will be included in the acquisition proposal.</span></span>  
11. <span data-ttu-id="01947-121">Az oldalon válassza a **Könyvek** lapot.</span><span class="sxs-lookup"><span data-stu-id="01947-121">On the page, select the **Books** tab.</span></span>
12. <span data-ttu-id="01947-122">Válassza a **Feladás** parancsot.</span><span class="sxs-lookup"><span data-stu-id="01947-122">Select **Post**.</span></span>
