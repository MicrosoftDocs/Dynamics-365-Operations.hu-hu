---
title: A Súgórendszer csatlakoztatása
description: Ez a témakör bemutatja a Súgó rendszer komponenseit a Finance and Operations alkalmazásban, áttekinti azok kapcsolatát, valamint összefoglalja az egyéni súgó létrehozásának módszereit.
author: margoc
manager: AnnBe
ms.date: 10/02/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: SystemParameters
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 16141
ms.assetid: 0b9c8630-9474-4473-80fd-7db5d54b2275
ms.search.region: Global
ms.author: margoc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4427388d75c1aef40a978ce35c831d5b714f2562
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/03/2020
ms.locfileid: "3006172"
---
# <a name="connect-the-help-system"></a><span data-ttu-id="90941-103">A Súgórendszer csatlakoztatása</span><span class="sxs-lookup"><span data-stu-id="90941-103">Connect the Help system</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="90941-104">Ez a témakör a Finance and Operations alkalmazások – például Dynamics 365 Finance, Supply Chain Management, Commerce és Human Resources – súgórendszerének összetevőit ismerteti.</span><span class="sxs-lookup"><span data-stu-id="90941-104">This topic describes the components of the Help system for Finance and Operations apps, such as Dynamics 365 Finance, Supply Chain Management, Commerce, and Human Resources.</span></span> <span data-ttu-id="90941-105">Áttekinti ezen összetevők kapcsolatát, valamint összefoglalja az egyéni súgó létrehozásának módszereit.</span><span class="sxs-lookup"><span data-stu-id="90941-105">It provides an overview of how to connect these components and a summary of how to create custom help.</span></span>

## <a name="help-architecture"></a><span data-ttu-id="90941-106">Súgó-architektúra</span><span class="sxs-lookup"><span data-stu-id="90941-106">Help architecture</span></span>

<span data-ttu-id="90941-107">A következő ábrán a súgórendszer részei láthatók.</span><span class="sxs-lookup"><span data-stu-id="90941-107">The following illustration shows the parts of the Help system.</span></span> <span data-ttu-id="90941-108">A termék súgója a https://docs.microsoft.com webhelyről tölt le cikkeket, valamint az itt tárolt feladat-útmutatókat használja: Business Process Modeler in Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="90941-108">The in-product Help system pulls articles from https://docs.microsoft.com, as well as task guides stored in Business Process Modeler in Lifecycle Services (LCS).</span></span>

> [!NOTE]
> <span data-ttu-id="90941-109">A diagramban csillaggal (\*) szereplő funkciók tervbe vannak véve, de még nem érhetők el.</span><span class="sxs-lookup"><span data-stu-id="90941-109">The features listed in the diagram with an asterisk (\*) are planned, but are not available yet.</span></span>

<span data-ttu-id="90941-110">[![Súgó-architektúra](./media/help-architecture.png)](./media/help-architecture.png)</span><span class="sxs-lookup"><span data-stu-id="90941-110">[![Help architecture](./media/help-architecture.png)](./media/help-architecture.png)</span></span>

## <a name="connecting-the-help-system"></a><span data-ttu-id="90941-111">Csatlakozás a Súgó rendszerhez</span><span class="sxs-lookup"><span data-stu-id="90941-111">Connecting the Help system</span></span>

> [!NOTE]
> <span data-ttu-id="90941-112">A **Feladat-útmutatók** lap jelenleg nem érhető el a Microsoft Dynamics 365 Human Resources és Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="90941-112">The **Task guides** tab is currently not available in Dynamics 365 Human Resources or Commerce.</span></span> <span data-ttu-id="90941-113">Jelenleg azon dolgozunk, hogy a funkcionalitás engedélyezett legyen valamelyik jövőbeli programverzióban.</span><span class="sxs-lookup"><span data-stu-id="90941-113">We are currently working to enable this functionality in a future release.</span></span> <span data-ttu-id="90941-114">A Human Resources Első lépések részének feladat-útmutatói továbbra is rendelkezésre állnak az alapvető funkciók ismertetéséhez.</span><span class="sxs-lookup"><span data-stu-id="90941-114">The Task guides in the Getting Started experience in Human Resources remain available to cover basic functionality.</span></span> <span data-ttu-id="90941-115">Az eljárási Súgó a docs.microsoft.com webhelyről is elérhető, mind a Human Resources, mind a Commerce számára.</span><span class="sxs-lookup"><span data-stu-id="90941-115">Procedural help is also available on the docs.microsoft.com site for both Human Resources and Commerce.</span></span>

<span data-ttu-id="90941-116">A **Rendszerparaméterek** oldalon a rendszergazdák csatlakoztathatják a Súgó rendszer különböző darabjait az adott megvalósításhoz.</span><span class="sxs-lookup"><span data-stu-id="90941-116">Using the **System Parameters** page, system administrators connect the pieces of the Help system for an implementation.</span></span>

<span data-ttu-id="90941-117">[![Rendszerparaméterek űrlap – súgó beállításai](./media/system-parameters_ops-1024x437.png)](./media/system-parameters_ops.png)</span><span class="sxs-lookup"><span data-stu-id="90941-117">[![System Parameters form with Help settings](./media/system-parameters_ops-1024x437.png)](./media/system-parameters_ops.png)</span></span>

<span data-ttu-id="90941-118">A **Rendszer paraméterei** oldalon kövesse az alábbi lépéseket:</span><span class="sxs-lookup"><span data-stu-id="90941-118">On the **System parameters** page, follow these steps:</span></span>

> [!IMPORTANT]
> <span data-ttu-id="90941-119">Amikor első alkalommal nyitja meg a **Súgó** lapot, kapcsolódnia kell a Lifecycle Services szolgáltatáshoz.</span><span class="sxs-lookup"><span data-stu-id="90941-119">The first time that you open the **Help** tab, you must connect to Lifecycle Services.</span></span> <span data-ttu-id="90941-120">Ügyeljen arra, hogy az űrlap közepén levő hivatkozásra kattintson, várja meg a kapcsolatot, zárja be a párbeszédpanelt, majd kattintson az **OK** gombra a **Rendszerparaméterek** oldal eléréséhez.</span><span class="sxs-lookup"><span data-stu-id="90941-120">Be sure to click the link in the middle of the form, wait for the connection, close the dialog box, and then click **OK** to get to the **System Parameters** page.</span></span>
>
> <span data-ttu-id="90941-121">[![Kapcsolódás az LCS szolgáltatáshoz](./media/connect-to-lcs-crop-1024x365.png "Kapcsolódás az LCS szolgáltatáshoz")](./media/connect-to-lcs-crop.png)</span><span class="sxs-lookup"><span data-stu-id="90941-121">[![Connect to LCS](./media/connect-to-lcs-crop-1024x365.png "Connect to LCS")](./media/connect-to-lcs-crop.png)</span></span>

1. <span data-ttu-id="90941-122">A csatlakozáshoz válassza ki a Lifecycle Services-projektet.</span><span class="sxs-lookup"><span data-stu-id="90941-122">Select the Lifecycle Services project to connect to.</span></span>
2. <span data-ttu-id="90941-123">Válassza ki a BPM könyvtárakat (a kiválasztott projekten belül) amelyekből szeretné előhívni a rögzítéseket.</span><span class="sxs-lookup"><span data-stu-id="90941-123">Select the BPM libraries (within the selected project) to retrieve task recordings from.</span></span>
3. <span data-ttu-id="90941-124">Adja meg a BPM könyvtárak megjelenítési sorrendjét.</span><span class="sxs-lookup"><span data-stu-id="90941-124">Set the display order of the BPM libraries.</span></span> <span data-ttu-id="90941-125">Ez meghatározza a sorrendet, amelyben a feladatrögzítések megjelennek a **Súgó** ablakban.</span><span class="sxs-lookup"><span data-stu-id="90941-125">This determines the order in which task recordings from the libraries will appear in the **Help** pane.</span></span>

<span data-ttu-id="90941-126">Miután végrehajtotta ezeket a lépéseket, nyissa meg a **Súgó** ablakot, és kattintson a **Feladat-útmutatók** lapra. Ekkor megjelennek a Finance and Operations-alkalmazások aktuális oldalához kapcsolódó feladat-útmutatók.</span><span class="sxs-lookup"><span data-stu-id="90941-126">After you complete these steps, you can open the **Help** pane and click the **Task guides** tab. You'll now see the task guides that apply to the page that you're currently on in Finance and Operations apps.</span></span> <span data-ttu-id="90941-127">Amennyiben nem találhatók feladat-útmutatók, kulcsszavak beírásával módosíthatja a keresést.</span><span class="sxs-lookup"><span data-stu-id="90941-127">If no task guides are found, you can enter keywords to refine your search.</span></span>

### <a name="showing-translated-task-guides"></a><span data-ttu-id="90941-128">Lefordított feladat-útmutatók megjelenítése</span><span class="sxs-lookup"><span data-stu-id="90941-128">Showing translated task guides</span></span>

<span data-ttu-id="90941-129">A honosított feladat-útmutatók először a 2016. májusi APQC Egyesített könyvtárban, valamint az Első lépések könyvtárban lettek szállítva.</span><span class="sxs-lookup"><span data-stu-id="90941-129">Translated task guides were first shipped in the May 2016 APQC Unified Library, and the Getting Started library.</span></span> <span data-ttu-id="90941-130">Ha szeretné a honosított feladat-útmutató súgót látni a Finance and Operations-alkalmazásokban, győződjön meg róla, hogy csatlakozva van a Május könyvtárhoz.</span><span class="sxs-lookup"><span data-stu-id="90941-130">In Finance and Operations apps, to see localized task guide help, make sure that you are connected to the May library.</span></span> <span data-ttu-id="90941-131">Minden felhasználó esetében a **Beállítások** &gt; **Beállítások** menüben található nyelvi beállítások határozzák meg a feladat-útmutató nyelvét.</span><span class="sxs-lookup"><span data-stu-id="90941-131">The language that a task guide appears in is controlled for each user by the Language settings under **Options** &gt; **Preferences**.</span></span>

> [!NOTE]
> <span data-ttu-id="90941-132">Megjegyzés: Annak ellenére, hogy sok feladat-útmutató le van már fordítva, az ügyfél jelenleg nem jelzi a lefordított feladat-útmutatók neveit.</span><span class="sxs-lookup"><span data-stu-id="90941-132">Even though many task guides have been translated, right now the client is not showing the translated task guide names.</span></span> <span data-ttu-id="90941-133">Valamint csak a 2016. februárban megjelent feladat-útmutatók fordításai elérhetőek a májusi könyvtárban jelenleg.</span><span class="sxs-lookup"><span data-stu-id="90941-133">Also, only the task guides that were released in February 2016 are available in translation in the May library.</span></span> <span data-ttu-id="90941-134">További fordításokat tartalmazó frissített könyvtárat fogunk megjelentetni hamarosan.</span><span class="sxs-lookup"><span data-stu-id="90941-134">We will release an updated library with additional translations.</span></span>
>
> - <span data-ttu-id="90941-135">Ha egy feladat-útmutató le van fordítva, akkor a kiválasztott nyelven fog megjelenni a feladat-útmutató teljes szövege.</span><span class="sxs-lookup"><span data-stu-id="90941-135">If a task guide has been translated, when you open that task guide all the text of the task guide will appear in your selected language.</span></span>
> - <span data-ttu-id="90941-136">Ha egy feladat-útmutató még nincs lefordítva, akkor a kiválasztott nyelven csak néhány szöveg (a vezérlők szövegei) fog megjelenni.</span><span class="sxs-lookup"><span data-stu-id="90941-136">If a task guide has not yet been translated, when you open it, only some of the text (the text of the controls) will appear in your selected language.</span></span>

## <a name="creating-custom-help"></a><span data-ttu-id="90941-137">Egyéni súgó létrehozása</span><span class="sxs-lookup"><span data-stu-id="90941-137">Creating custom help</span></span>

<span data-ttu-id="90941-138">Használhatja a feladat-útmutatókat az egyéni súgó létrehozásáhot, vagy hozzákapcsolhat egy webhelyet a Súgópanelhez.</span><span class="sxs-lookup"><span data-stu-id="90941-138">You can use task guides to create custom help, or connect a website to the Help pane.</span></span>

### <a name="create-custom-help-with-task-guides"></a><span data-ttu-id="90941-139">Egyéni súgó létrehozása feladat-útmutatókkal</span><span class="sxs-lookup"><span data-stu-id="90941-139">Create custom help with task guides</span></span>

<span data-ttu-id="90941-140">Lehetősége van egyéni súgót létrehozni saját Finance, Supply Chain Management és Commerce példányához; ehhez létre kell hoznia az egyedi megoldásokat magukban foglaló feladatrögzítéseket, majd azokat egy LCS Üzletifolyamat-tárba kell mentenie.</span><span class="sxs-lookup"><span data-stu-id="90941-140">You can create custom help for Finance, Supply Chain Management, and Commerce by creating task recordings that reflect your implementation, and saving them to an LCS Business Process Library.</span></span> <span data-ttu-id="90941-141">A Human Resources rendszerben nem hozhat létre egyéni feladat-útmutatókat.</span><span class="sxs-lookup"><span data-stu-id="90941-141">You cannot create custom task guides for Human Resources.</span></span>

<span data-ttu-id="90941-142">Partnerekhez, ha egy tárat vállalati kódtár előléptetett, és helyezze el a megoldás lesz a felhasználók számára érhető el.</span><span class="sxs-lookup"><span data-stu-id="90941-142">For partners, if you promote a library to be a corporate library, and include it in a solution, it will be available to your customers.</span></span> <span data-ttu-id="90941-143">Ezenkívül az APQC Egyesített globális tárról is készíthet másolatot; megnyithatja a saját másolatot és az abban található feladatrögzítéseket, majd a módosítást követően elmentheti a rögzítéseket a változtatásokkal együtt.</span><span class="sxs-lookup"><span data-stu-id="90941-143">You can also make a copy of the APQC Unified global library, and then open your copy, open task recordings from it, modify them, and save the recordings with your changes.</span></span> <span data-ttu-id="90941-144">További tájékoztatás: [Feladatrögzítő erőforrásai](../../dev-itpro/user-interface/task-recorder.md).</span><span class="sxs-lookup"><span data-stu-id="90941-144">For more information, see [Task recorder resources](../../dev-itpro/user-interface/task-recorder.md).</span></span>

### <a name="connect-a-custom-site"></a><span data-ttu-id="90941-145">Egyéni webhely csatlakoztatása</span><span class="sxs-lookup"><span data-stu-id="90941-145">Connect a custom site</span></span>

<span data-ttu-id="90941-146">A Microsoft rendelkezésre bocsátott egy ismertetőt és mintakódot, amely leírja, hogy hogyan lehet egy egyéni súgówebhelyet létrehozni, és a Súgópanelhez csatlakoztatni.</span><span class="sxs-lookup"><span data-stu-id="90941-146">Microsoft has provided a white paper and sample code that describe how to create and connect a custom help site to the Help pane.</span></span> <span data-ttu-id="90941-147">További tájékoztatás:</span><span class="sxs-lookup"><span data-stu-id="90941-147">For more information, see:</span></span>

- [<span data-ttu-id="90941-148">Egyéni Súgó létrehozása a Finance and Operations-alkalmazásokhoz (ismertető)</span><span class="sxs-lookup"><span data-stu-id="90941-148">Create Custom Help for Finance and Operations apps (white paper)</span></span>](https://go.microsoft.com/fwlink/?linkid=2041185)
- [<span data-ttu-id="90941-149">Egyéni súgó GitHub-tárház</span><span class="sxs-lookup"><span data-stu-id="90941-149">Custom help GitHub repository</span></span>](https://github.com/microsoft/dynamics356f-o-custom-help)

## <a name="additional-resources"></a><span data-ttu-id="90941-150">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="90941-150">Additional resources</span></span>

[<span data-ttu-id="90941-151">Súgórendszer</span><span class="sxs-lookup"><span data-stu-id="90941-151">Help system</span></span>](help-overview.md)

[<span data-ttu-id="90941-152">Feladatrögzítő erőforrásai</span><span class="sxs-lookup"><span data-stu-id="90941-152">Task recorder resources</span></span>](../../dev-itpro/user-interface/task-recorder.md)

[<span data-ttu-id="90941-153">Dokumentáció vagy képzés létrehozása Feladatrögzítő segítségével</span><span class="sxs-lookup"><span data-stu-id="90941-153">Create documentation or training with Task Recorder</span></span>](../../dev-itpro/user-interface/task-recorder-training-docs.md)
