---
title: "A Súgó rendszer csatlakoztatása"
description: "Ez a témakör bemutatja a Microsoft Dynamics 365 for Finance and Operations súgórendszer komponenseit, áttekinti azok kapcsolatát, valamint összefoglalja az egyéni súgó létrehozásának módszereit."
author: margoc
manager: AnnBe
ms.date: 09/11/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
ms.search.form: SystemParameters
audience: Application User, Developer, IT Pro
ms.reviewer: margoc
ms.search.scope: Core, Operations
ms.custom: 16141
ms.assetid: 0b9c8630-9474-4473-80fd-7db5d54b2275
ms.search.region: Global
ms.author: margoc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: c0942b66859da3659be49b19986bfd146ac43130
ms.contentlocale: hu-hu
ms.lasthandoff: 11/03/2017

---

# <a name="connect-the-help-system"></a><span data-ttu-id="0eee5-103">A Súgó rendszer csatlakoztatása</span><span class="sxs-lookup"><span data-stu-id="0eee5-103">Connect the Help system</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="0eee5-104">Ez a témakör a Microsoft Dynamics 365 for Finance and Operations súgórendszerének összetevőit írja le.</span><span class="sxs-lookup"><span data-stu-id="0eee5-104">This topic describes the components of the Help system for Microsoft Dynamics 365 for Finance and Operations.</span></span> <span data-ttu-id="0eee5-105">Áttekinti ezen összetevők kapcsolatát, valamint összefoglalja az egyéni súgó létrehozásának módszereit.</span><span class="sxs-lookup"><span data-stu-id="0eee5-105">It provides an overview of how to connect these components and a summary of how to create custom help.</span></span> 

## <a name="help-architecture"></a><span data-ttu-id="0eee5-106">Súgó-architektúra</span><span class="sxs-lookup"><span data-stu-id="0eee5-106">Help architecture</span></span>
<span data-ttu-id="0eee5-107">A következő ábra a Finance and Operations rendszer súgórendszerének részeit jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="0eee5-107">The following illustration shows the parts of the Finance and Operations Help system.</span></span> <span data-ttu-id="0eee5-108">A beépített súgórendszer lekéri a https://docs.microsoft.com Finance and Operations Súgó webhelyen található cikkeket, valamint a Lifecycle Services (LCS) Üzletifolyamat-modellezőjében tárolt feladat-útmutatókat.</span><span class="sxs-lookup"><span data-stu-id="0eee5-108">The in-product Help system pulls articles from the Finance and Operations site on https://docs.microsoft.com, as well as task guides stored in Business Process Modeler in Lifecycle Services (LCS).</span></span> 
> [!NOTE]
> <span data-ttu-id="0eee5-109">A diagramban csillaggal (\*) szereplő funkciók tervbe vannak véve, de még nem érhetők el.</span><span class="sxs-lookup"><span data-stu-id="0eee5-109">The features listed in the diagram with an asterisk (\*) are planned, but are not available yet.</span></span> <span data-ttu-id="0eee5-110">[![Súgó-architektúra](./media/help-architecture.png)](./media/help-architecture.png)</span><span class="sxs-lookup"><span data-stu-id="0eee5-110">[![Help architecture](./media/help-architecture.png)](./media/help-architecture.png)</span></span>


## <a name="connecting-the-help-system"></a><span data-ttu-id="0eee5-111">Csatlakozás a Súgó rendszerhez</span><span class="sxs-lookup"><span data-stu-id="0eee5-111">Connecting the Help system</span></span>
> [!NOTE]
> <span data-ttu-id="0eee5-112">A **Feladat-útmutatók** lap jelenleg nem áll rendelkezésre a Microsoft Dynamics 365 for Talent és a Microsoft Dynamics 365 for Retail esetében.</span><span class="sxs-lookup"><span data-stu-id="0eee5-112">The **Task guides** tab is currently not available in Microsoft Dynamics 365 for Talent and Microsoft Dynamics 365 for Retail.</span></span> <span data-ttu-id="0eee5-113">Jelenleg azon dolgozunk, hogy a funkcionalitás engedélyezett legyen valamelyik jövőbeli programverzióban.</span><span class="sxs-lookup"><span data-stu-id="0eee5-113">We are currently working to enable this functionality in a future release.</span></span> <span data-ttu-id="0eee5-114">A Talent Első lépések részének feladat-útmutatói továbbra is rendelkezésre állnak az alapvető funkciók ismertetéséhez.</span><span class="sxs-lookup"><span data-stu-id="0eee5-114">The Task guides in the Getting Started experience in Talent remain available to cover basic functionality.</span></span> <span data-ttu-id="0eee5-115">Az eljárások lépéseit ismertető súgó is elérhető a docs.microsoft.com webhelyen ([docs.microsoft.com/dynamics365/unified-operations](../../index.md)) mind a Retail, mind a Talent esetében.</span><span class="sxs-lookup"><span data-stu-id="0eee5-115">Procedural help is also available on the docs.microsoft.com site ([docs.microsoft.com/dynamics365/unified-operations](../../index.md)) for both Retail and Talent.</span></span>
 

<span data-ttu-id="0eee5-116">A **Rendszerparaméterek** oldalon a rendszergazdák csatlakoztathatják a Súgó rendszer különböző darabjait az adott megvalósításhoz.</span><span class="sxs-lookup"><span data-stu-id="0eee5-116">Using the **System Parameters** page, system administrators connect the pieces of the Help system for an implementation.</span></span> <span data-ttu-id="0eee5-117">[![Rendszerparaméterek – súgó beállításai](./media/system-parameters_ops-1024x437.png)](./media/system-parameters_ops.png) A **Rendszerparaméterek** lapon végezze el az alábbi lépéseket:</span><span class="sxs-lookup"><span data-stu-id="0eee5-117">[![System Parameters form with Help settings](./media/system-parameters_ops-1024x437.png)](./media/system-parameters_ops.png) On the **System parameters** page, follow these steps:</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0eee5-118">Amikor első alkalommal nyitja meg a **Súgó** lapot, kapcsolódnia kell a Lifecycle Services szolgáltatáshoz.</span><span class="sxs-lookup"><span data-stu-id="0eee5-118">The first time that you open the **Help** tab, you must connect to Lifecycle Services.</span></span> <span data-ttu-id="0eee5-119">Ügyeljen arra, hogy az űrlap közepén levő hivatkozásra kattintson, várja meg a kapcsolatot, zárja be a párbeszédpanelt, majd kattintson az **OK** gombra a **Rendszerparaméterek** oldal eléréséhez.[![Kapcsolódás az LCS szolgáltatáshoz](./media/connect-to-lcs-crop-1024x365.png "Kapcsolódás az LCS szolgáltatáshoz")](./media/connect-to-lcs-crop.png)</span><span class="sxs-lookup"><span data-stu-id="0eee5-119">Be sure to click the link in the middle of the form, wait for the connection, close the dialog box, and then click **OK** to get to the **System Parameters** page.[![Connect to LCS](./media/connect-to-lcs-crop-1024x365.png "Connect to LCS")](./media/connect-to-lcs-crop.png)</span></span>

1.  <span data-ttu-id="0eee5-120">A csatlakozáshoz válassza ki a Lifecycle Services-projektet.</span><span class="sxs-lookup"><span data-stu-id="0eee5-120">Select the Lifecycle Services project to connect to.</span></span>
2.  <span data-ttu-id="0eee5-121">Válassza ki a BPM könyvtárakat (a kiválasztott projekten belül) amelyekből szeretné előhívni a rögzítéseket.</span><span class="sxs-lookup"><span data-stu-id="0eee5-121">Select the BPM libraries (within the selected project) to retrieve task recordings from.</span></span>
    - <span data-ttu-id="0eee5-122">A Finance and Operations Microsoft-tartalom esetében válassza ki a legújabb Microsoft Dynamics 365 Finance and Operations APQC Egyesített könyvtárat.</span><span class="sxs-lookup"><span data-stu-id="0eee5-122">For Finance and Operations, for Microsoft content, select the most recent APQC Unified Library for Finance and Operations.</span></span> 
    - <span data-ttu-id="0eee5-123">A Retail esetében a könyvtárat a közeljövőben adjuk ki.</span><span class="sxs-lookup"><span data-stu-id="0eee5-123">For Retail, we will be releasing a library in the near future.</span></span> 
    - <span data-ttu-id="0eee5-124">A Talent esetében nem kell könyvtárat választani – a kapcsolatot a megfelelő könyvtárhoz létrehozzuk Önnek.</span><span class="sxs-lookup"><span data-stu-id="0eee5-124">You do not need to select a library for Talent—the connection to the correct library is established for you.</span></span> 

3.  <span data-ttu-id="0eee5-125">Adja meg a BPM könyvtárak megjelenítési sorrendjét.</span><span class="sxs-lookup"><span data-stu-id="0eee5-125">Set the display order of the BPM libraries.</span></span> <span data-ttu-id="0eee5-126">Ez meghatározza a sorrendet, amelyben a feladatrögzítések megjelennek a **Súgó** ablakban.</span><span class="sxs-lookup"><span data-stu-id="0eee5-126">This determines the order in which task recordings from the libraries will appear in the **Help** pane.</span></span>

<span data-ttu-id="0eee5-127">Miután végrehajtotta ezeket a lépéseket, nyissa meg a **Súgó** ablakot, és kattintson a **Feladat-útmutatók** lapra. Ekkor megjelennek a Finance and Operations aktuális oldalához kapcsolódó feladat-útmutatók.</span><span class="sxs-lookup"><span data-stu-id="0eee5-127">After you complete these steps, you can open the **Help** pane and click the **Task guides** tab. You'll now see the task guides that apply to the page that you’re currently on in Finance and Operations.</span></span> <span data-ttu-id="0eee5-128">Amennyiben nem találhatók feladat-útmutatók, kulcsszavak beírásával módosíthatja a keresést.</span><span class="sxs-lookup"><span data-stu-id="0eee5-128">If no task guides are found, you can enter keywords to refine your search.</span></span>

### <a name="showing-translated-task-guides"></a><span data-ttu-id="0eee5-129">Lefordított feladat-útmutatók megjelenítése</span><span class="sxs-lookup"><span data-stu-id="0eee5-129">Showing translated task guides</span></span>

<span data-ttu-id="0eee5-130">A honosított feladat-útmutatók először a 2016. májusi APQC Egyesített könyvtárban, valamint az Első lépések könyvtárban lettek szállítva.</span><span class="sxs-lookup"><span data-stu-id="0eee5-130">Translated task guides were first shipped in the May 2016 APQC Unified Library, and the Getting Started library.</span></span> <span data-ttu-id="0eee5-131">Ha szeretné a honosított feladat-útmutató súgót látni a Finance and Operationsben, győződjön meg arról, hogy csatlakozva van a májusi könyvtárhoz.</span><span class="sxs-lookup"><span data-stu-id="0eee5-131">In Finance and Operations, to see localized task guide help, make sure that you are connected to the May library.</span></span> <span data-ttu-id="0eee5-132">Minden felhasználó esetében a **Beállítások** &gt; **Beállítások** menüben található nyelvi beállítások határozzák meg a feladat-útmutató nyelvét.</span><span class="sxs-lookup"><span data-stu-id="0eee5-132">The language that a task guide appears in is controlled for each user by the Language settings under **Options** &gt; **Preferences**.</span></span> 

> [!NOTE]
> <span data-ttu-id="0eee5-133">Annak ellenére, hogy sok feladat-útmutató le van már fordítva, a Finance and Operations rendszer jelenleg nem jelzi a lefordított feladat-útmutatók neveit.</span><span class="sxs-lookup"><span data-stu-id="0eee5-133">Even though many task guides have been translated, right now the Finance and Operations client is not showing the translated task guide names.</span></span> <span data-ttu-id="0eee5-134">Valamint csak a 2016. februárban megjelent feladat-útmutatók fordításai elérhetőek a májusi könyvtárban jelenleg.</span><span class="sxs-lookup"><span data-stu-id="0eee5-134">Also, only the task guides that were released in February 2016 are available in translation in the May library.</span></span> <span data-ttu-id="0eee5-135">További fordításokat tartalmazó frissített könyvtárat fogunk megjelentetni hamarosan.</span><span class="sxs-lookup"><span data-stu-id="0eee5-135">We will release an updated library with additional translations.</span></span>
> -   <span data-ttu-id="0eee5-136">Ha egy feladat-útmutató le van fordítva, akkor a kiválasztott nyelven fog megjelenni a feladat-útmutató teljes szövege.</span><span class="sxs-lookup"><span data-stu-id="0eee5-136">If a task guide has been translated, when you open that task guide all the text of the task guide will appear in your selected language.</span></span>
> -   <span data-ttu-id="0eee5-137">Ha egy feladat-útmutató még nincs lefordítva, akkor a kiválasztott nyelven csak néhány szöveg (a vezérlők szövegei) fog megjelenni.</span><span class="sxs-lookup"><span data-stu-id="0eee5-137">If a task guide has not yet been translated, when you open it, only some of the text (the text of the controls) will appear in your selected language.</span></span>

## <a name="creating-custom-help"></a><span data-ttu-id="0eee5-138">Egyéni súgó létrehozása</span><span class="sxs-lookup"><span data-stu-id="0eee5-138">Creating custom help</span></span>
<span data-ttu-id="0eee5-139">Lehetősége van egyéni súgót létrehozni saját Finance and Operations és Retail példányához; ehhez létre kell hoznia az egyedi megoldásokat magukban foglaló feladatrögzítéseket, majd azokat egy LCS Üzletifolyamat-tárba kell mentenie.</span><span class="sxs-lookup"><span data-stu-id="0eee5-139">You can create custom help for Finance and Operations, and for Retail by creating task recordings that reflect your implementation, and saving them to an LCS Business Process Library.</span></span> <span data-ttu-id="0eee5-140">A Talent rendszerben nem hozhat létre egyéni feladat-útmutatókat.</span><span class="sxs-lookup"><span data-stu-id="0eee5-140">You cannot create custom task guides for Talent.</span></span> 

<span data-ttu-id="0eee5-141">Partnerekhez, ha egy tárat vállalati kódtár előléptetett, és helyezze el a megoldás lesz a felhasználók számára érhető el.</span><span class="sxs-lookup"><span data-stu-id="0eee5-141">For partners, if you promote a library to be a corporate library, and include it in a solution, it will be available to your customers.</span></span> <span data-ttu-id="0eee5-142">Ezenkívül az APQC Egyesített globális tárról is készíthet másolatot; megnyithatja a saját másolatot és az abban található feladatrögzítéseket, majd a módosítást követően elmentheti a rögzítéseket a változtatásokkal együtt.</span><span class="sxs-lookup"><span data-stu-id="0eee5-142">You can also make a copy of the APQC Unified global library, and then open your copy, open task recordings from it, modify them, and save the recordings with your changes.</span></span> <span data-ttu-id="0eee5-143">További tudnivalókért lásd: [Dokumentációként használandó feladatrögzítés vagy oktatás létrehozása](../../dev-itpro/user-interface/task-recorder.md).</span><span class="sxs-lookup"><span data-stu-id="0eee5-143">For more information, see [How to create a task recording to use as documentation or training](../../dev-itpro/user-interface/task-recorder.md).</span></span>

<a name="see-also"></a><span data-ttu-id="0eee5-144">Lásd még</span><span class="sxs-lookup"><span data-stu-id="0eee5-144">See also</span></span>
--------

[<span data-ttu-id="0eee5-145">Súgó áttekintése</span><span class="sxs-lookup"><span data-stu-id="0eee5-145">Help overview</span></span>](help-overview.md)

[<span data-ttu-id="0eee5-146">Feladatrögzítő áttekintése</span><span class="sxs-lookup"><span data-stu-id="0eee5-146">Task recorder overview</span></span>](../../dev-itpro/user-interface/task-recorder.md)

[<span data-ttu-id="0eee5-147">Feladatrögzítés létrehozása dokumentációként vagy képzésként való felhasználás céljából</span><span class="sxs-lookup"><span data-stu-id="0eee5-147">How to create a task recording to use as documentation or training</span></span>](../../dev-itpro/user-interface/task-recorder-training-docs.md)





