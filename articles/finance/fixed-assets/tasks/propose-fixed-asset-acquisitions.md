---
title: Javaslat tárgyieszköz-beszerzésekre
description: Ez a témakör leírja, hogyan szerezhető be tárgyi eszköz a Tárgyi eszközök naplójában található Beszerzési javaslat segítségével.
author: saraschi2
ms.date: 03/17/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: AssetTable, AssetBook, LedgerJournalTable, LedgerJournalTransAsset, SysQueryForm
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d529cd53b41827a78b282afd4d2c69d2f2db555e
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5817166"
---
# <a name="propose-fixed-asset-acquisitions"></a><span data-ttu-id="8636b-103">Javaslat tárgyieszköz-beszerzésekre</span><span class="sxs-lookup"><span data-stu-id="8636b-103">Propose fixed asset acquisitions</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="8636b-104">Ez a témakör leírja, hogyan szerezhető be tárgyi eszköz a Tárgyi eszközök naplójában található Beszerzési javaslat segítségével.</span><span class="sxs-lookup"><span data-stu-id="8636b-104">This topic describes how to acquire a fixed asset using the acquisition proposal in the Fixed assets journal.</span></span> <span data-ttu-id="8636b-105">Ez a könyvelői szerepkört és a bemutató adatokat használja a USMF jogi személyhez.</span><span class="sxs-lookup"><span data-stu-id="8636b-105">It uses the accountant role and demo data for the USMF legal entity.</span></span> <span data-ttu-id="8636b-106">Ha tárgyi eszköz javaslati naplón keresztül kíván beszerezni egy tárgyi eszközt, először létre kell hoznia a tárgyi eszköz rekordját, majd meg kell határoznia a beszerzési árat a tárgyi eszköz könyvében.</span><span class="sxs-lookup"><span data-stu-id="8636b-106">To acquire a fixed asset through a fixed asset proposal journal, you must first create the fixed asset record, and then define the acquisition price in the asset book.</span></span>

## <a name="create-an-asset-acquisition-proposal"></a><span data-ttu-id="8636b-107">Eszközbeszerzési javaslat létrehozása</span><span class="sxs-lookup"><span data-stu-id="8636b-107">Create an asset acquisition proposal</span></span>

<span data-ttu-id="8636b-108">Eszközbeszerzési javaslat létrehozásához végezze el a következő lépéseket.</span><span class="sxs-lookup"><span data-stu-id="8636b-108">Complete the following steps to create an asset acquisition proposal.</span></span> 

1. <span data-ttu-id="8636b-109">A navigációs ablaktáblán nyissa meg a **Modulok > Tárgyi eszközök > Naplóbejegyzések > Tárgyi eszközök naplója** elemet.</span><span class="sxs-lookup"><span data-stu-id="8636b-109">In the navigation pane, go to **Modules > Fixed assets > Journal entries > Fixed assets journal**.</span></span>
2. <span data-ttu-id="8636b-110">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8636b-110">Select **New**.</span></span>
3. <span data-ttu-id="8636b-111">A **Név** mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="8636b-111">In the **Name** field, enter or select a value.</span></span>
4. <span data-ttu-id="8636b-112">A Műveleti ablaktáblán válassza a **Sorok** elemet.</span><span class="sxs-lookup"><span data-stu-id="8636b-112">In the Action Pane, select **Lines**.</span></span>
5. <span data-ttu-id="8636b-113">Válassza a **Javaslatok** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8636b-113">Select **Proposals**.</span></span>
6. <span data-ttu-id="8636b-114">Válassza a **Beszerzési javaslat** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8636b-114">Select **Acquisition proposal**.</span></span>
7. <span data-ttu-id="8636b-115">Válassza ki a **Szűrő** elemet.</span><span class="sxs-lookup"><span data-stu-id="8636b-115">Select **Filter**.</span></span> <span data-ttu-id="8636b-116">A korábbi értékek törléséhez kattintson az **Alaphelyzetbe állítás** pontra.</span><span class="sxs-lookup"><span data-stu-id="8636b-116">Select **Reset** to clear previous values.</span></span>
8. <span data-ttu-id="8636b-117">Válassza ki a **Tárgyieszköz-szám** elnevezésű sort.</span><span class="sxs-lookup"><span data-stu-id="8636b-117">Select the **Fixed asset number** row.</span></span>
9. <span data-ttu-id="8636b-118">A **Feltétel** mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="8636b-118">In the **Criteria** field, enter or select a value.</span></span> <span data-ttu-id="8636b-119">Állítsa be a javaslat kapcsán beszerezni kívánt tárgyi eszközökre vonatkozó további feltételeket.</span><span class="sxs-lookup"><span data-stu-id="8636b-119">Set the remaining criteria for the fixed assets that you want to acquire with this proposal.</span></span>  
10. <span data-ttu-id="8636b-120">A panelből való kilépéshez nyomja meg kétszer az **OK** gombot.</span><span class="sxs-lookup"><span data-stu-id="8636b-120">Select **OK** twice to exit out of the pane.</span></span>
- <span data-ttu-id="8636b-121">Erősítse meg a tranzakciós sorok létrehozását.</span><span class="sxs-lookup"><span data-stu-id="8636b-121">Verify that the transaction lines are created.</span></span>  
- <span data-ttu-id="8636b-122">A beszerzési javaslat kizárólag az értékmodellben beállított beszerzési dátummal és beszerzési árral rendelkező tárgyi eszközöket veszi figyelembe.</span><span class="sxs-lookup"><span data-stu-id="8636b-122">Only fixed assets with the acquisition date and acquisition price set on the book will be included in the acquisition proposal.</span></span>  
11. <span data-ttu-id="8636b-123">Az oldalon válassza a **Könyvek** lapot.</span><span class="sxs-lookup"><span data-stu-id="8636b-123">On the page, select the **Books** tab.</span></span>
12. <span data-ttu-id="8636b-124">Válassza a **Feladás** parancsot.</span><span class="sxs-lookup"><span data-stu-id="8636b-124">Select **Post**.</span></span>

## <a name="include-default-financial-dimensions-in-an-acquisition-proposal"></a><span data-ttu-id="8636b-125">Alapértelmezett pénzügyi dimenziók beépítése egy beszerzési javaslatba</span><span class="sxs-lookup"><span data-stu-id="8636b-125">Include default financial dimensions in an acquisition proposal</span></span>

<span data-ttu-id="8636b-126">A beszerzési tranzakció Excel-bővítményekkel is létrehozható a **Tárgyi eszközök > Naplórekordok > Tárgyieszköz napló** menüben.</span><span class="sxs-lookup"><span data-stu-id="8636b-126">The acquisition transaction can be created using Excel add-ins, by going to **Fixed assets > Journal entries > Fixed asset journal**.</span></span> <span data-ttu-id="8636b-127">Hozzon létre egy új naplót, és lépjen a lap **Sorok** szakaszára, és válassza az Excel ikont, majd válasszon egy Tárgyieszköznapló-sort.</span><span class="sxs-lookup"><span data-stu-id="8636b-127">Create a new journal and move to the **Lines** section on the page and select the Excel icon, and then select a Fixed asset journal line.</span></span> <span data-ttu-id="8636b-128">A rendszer létrehoz és megnyit egy naplósorokat ábrázoló Excel-sablont.</span><span class="sxs-lookup"><span data-stu-id="8636b-128">The system will create and open an Excel template representing journal lines.</span></span> <span data-ttu-id="8636b-129">Hozzáadhatja a sablonhoz hozzáadott naplósorok adatait, majd ezeket az adatokat újra közzéteheti a rendszerben.</span><span class="sxs-lookup"><span data-stu-id="8636b-129">You can add data for the journal lines you're adding into the template, and then publish that information back into the system.</span></span> 

<span data-ttu-id="8636b-130">Ha alapértelmezett dimenziókat állítottak be a kijelölt tárgyieszköz-könyvhöz és az Excel-sablonban megadott megfelelő tárgyi eszközökhöz, akkor a program az alapértelmezett pénzügyi dimenziókat az eszközkönyv törzsadatainak alapján nevezi meg, amikor a naplót közzéteszik az Excelből a rendszerbe.</span><span class="sxs-lookup"><span data-stu-id="8636b-130">If default dimensions have been set up for the selected asset book and the corresponding fixed assets that were entered in the Excel template, the default financial dimensions will be called from the asset book master data when the journal is published from the Excel to the system.</span></span> <span data-ttu-id="8636b-131">Ha a tárgyieszköz-napló Excel-bővítményből való közzétételekor automatikusan szerepeltetni szeretné a pénzügyi dimenziókat, az alapértelmezett dimenziókat előzetesen be kell állítani.</span><span class="sxs-lookup"><span data-stu-id="8636b-131">To include financial dimensions on an asset book automatically while publishing the fixed asset journal from the Excel add-in, the default dimensions must be set up in advance.</span></span>  


[!INCLUDE [footer-include](../../../includes/footer-banner.md)]
