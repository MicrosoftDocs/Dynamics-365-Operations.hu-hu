---
title: A Finance and Operations alkalmazások súgóélményének konfigurálása
description: Ez a témakör néhány Microsoft Dynamics 365 alkalmazáshoz tartalmaz tájékoztatást a Súgó rendszer összetevőiről. Bemutatja az alkalmazások csatlakoztatásának módját, valamint az egyéni súgó létrehozási folyamatának összegzését.
author: margoc
manager: AnnBe
ms.date: 05/11/2020
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
ms.openlocfilehash: 827d4cd14f497b79c85fb084a6295af13c5eb0c7
ms.sourcegitcommit: 89022f39502b19c24c0997ae3a01a64b93280f42
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/12/2020
ms.locfileid: "3367384"
---
# <a name="configure-the-help-experience-for-finance-and-operations-apps"></a><span data-ttu-id="c0fa4-104">A Finance and Operations alkalmazások súgóélményének konfigurálása</span><span class="sxs-lookup"><span data-stu-id="c0fa4-104">Configure the Help experience for Finance and Operations apps</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c0fa4-105">Ebben a témakörben egy áttekintést talál a Finance and Operations alkalmazások súgórendszerének összetevőiről, például a Microsoft Dynamics 365 Finance, a Dynamics 365 Supply Chain Management, a Dynamics 365 Commerce és a Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="c0fa4-105">In this topic, you will find an overview of the components of the Help system for Finance and Operations apps, such as Microsoft Dynamics 365 Finance, Dynamics 365 Supply Chain Management, Dynamics 365 Commerce, and Dynamics 365 Human Resources.</span></span> <span data-ttu-id="c0fa4-106">A témakör emellett bemutatja az összetevők csatlakoztatásának módját, valamint az egyéni súgó létrehozási folyamatának összegzését.</span><span class="sxs-lookup"><span data-stu-id="c0fa4-106">The topic also explains how to connect these components and provides a summary of the process for creating custom Help.</span></span>

## <a name="help-architecture"></a><span data-ttu-id="c0fa4-107">Súgó-architektúra</span><span class="sxs-lookup"><span data-stu-id="c0fa4-107">Help architecture</span></span>

<span data-ttu-id="c0fa4-108">A Finance and Operations alkalmazások fogalmi áttekintéseket és egyéb témaköröket tartalmaznak, amelyek a [https://docs.microsoft.com/dynamics365](/dynamics365/) webhelyen vannak közzétéve.</span><span class="sxs-lookup"><span data-stu-id="c0fa4-108">Finance and Operations apps include conceptual overviews and other topics that are published to the [https://docs.microsoft.com/dynamics365](/dynamics365/) site.</span></span> <span data-ttu-id="c0fa4-109">Ez a tartalom később a termék **Súgó** paneljéből érthető el.</span><span class="sxs-lookup"><span data-stu-id="c0fa4-109">This content can then be accessed from the in-product **Help** pane.</span></span> <span data-ttu-id="c0fa4-110">A következő ábrán a súgórendszer részei láthatók.</span><span class="sxs-lookup"><span data-stu-id="c0fa4-110">The following illustration shows the parts of the Help system.</span></span>

<span data-ttu-id="c0fa4-111">[![Súgó-architektúra](./media/help-architecture.png)](./media/help-architecture.png)</span><span class="sxs-lookup"><span data-stu-id="c0fa4-111">[![Help architecture](./media/help-architecture.png)](./media/help-architecture.png)</span></span>

<span data-ttu-id="c0fa4-112">A terméken belüli súgórendszer a docs.microsoft.com webhelyről és egyéb kapcsolódó webhelyekről olvas be cikkeket.</span><span class="sxs-lookup"><span data-stu-id="c0fa4-112">The in-product Help system pulls articles from docs.microsoft.com and other connected websites.</span></span> <span data-ttu-id="c0fa4-113">Ezenkívül a Microsoft Dynamics Lifecycle Services (LCS) Üzletifolyamat-modellező (BPM) alkalmazásában tárolt feladat-útmutatókat is beolvas.</span><span class="sxs-lookup"><span data-stu-id="c0fa4-113">It also pulls in task guides that are stored in Business process modeler (BPM) in Microsoft Dynamics Lifecycle Services (LCS).</span></span>

## <a name="adding-task-guides"></a><span data-ttu-id="c0fa4-114">Feladat-útmutatók hozzáadása</span><span class="sxs-lookup"><span data-stu-id="c0fa4-114">Adding task guides</span></span>

> [!NOTE]
> <span data-ttu-id="c0fa4-115">A **Feladat-útmutatók** lap jelenleg nem érhető el az Human Resources vagy a Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="c0fa4-115">The **Task guides** tab isn't currently available in Human Resources or Commerce.</span></span> <!--We are currently working to enable this functionality in a future release.--> <span data-ttu-id="c0fa4-116">A Human Resources Első lépések részének feladat-útmutatói azonban továbbra is rendelkezésre állnak az alapvető funkciók ismertetéséhez.</span><span class="sxs-lookup"><span data-stu-id="c0fa4-116">However, the task guides in the Getting Started experience in Human Resources remain available to cover basic functionality.</span></span> <span data-ttu-id="c0fa4-117">Az eljárási Súgó a [https://docs.microsoft.com/dynamics365](/dynamics365/) webhelyről is elérhető, mind a Human Resources, mind a Commerce számára.</span><span class="sxs-lookup"><span data-stu-id="c0fa4-117">For both Human Resources and Commerce, procedural Help is available on the [https://docs.microsoft.com/dynamics365](/dynamics365/) site.</span></span>

<span data-ttu-id="c0fa4-118">A **Rendszerparaméterek** oldalon a rendszeradminisztrátorok konfigurálhatják egy megvalósítás releváns feladat-útmutató könyvtáraihoz való hozzáférést.</span><span class="sxs-lookup"><span data-stu-id="c0fa4-118">On the **System parameters** page, system admins can configure access to the relevant task guide libraries for an implementation.</span></span>

> [!NOTE]
> - <span data-ttu-id="c0fa4-119">A Súgó konfigurálásához be kell lépnie egy ugyanattól a bérlőtől származó fiókba, amiben az alkalmazás is telepítve van.</span><span class="sxs-lookup"><span data-stu-id="c0fa4-119">To configure Help, you must sign in by using an account in the same tenant as the tenant where the app is deployed.</span></span>
> - <span data-ttu-id="c0fa4-120">Helyi virtuális merevlemezen (VHD) futó alkalmazáspéldánnyal nem lehet csatlakozni az LCS könyvtárhoz.</span><span class="sxs-lookup"><span data-stu-id="c0fa4-120">An LCS library can't be connected from an instance of the app that is running on a local virtual hard drive (VHD).</span></span>

<span data-ttu-id="c0fa4-121">[![Rendszerparaméterek űrlap – súgó beállításai](./media/system-parameters_ops-1024x437.png)](./media/system-parameters_ops.png)</span><span class="sxs-lookup"><span data-stu-id="c0fa4-121">[![System Parameters form with Help settings](./media/system-parameters_ops-1024x437.png)](./media/system-parameters_ops.png)</span></span>

<span data-ttu-id="c0fa4-122">A megoldás feladat-útmutatóinak konfigurálásához kövesse az alábbi lépéseket a **Rendszerparaméterek** oldalon.</span><span class="sxs-lookup"><span data-stu-id="c0fa4-122">To configure task guides for a solution, follow these steps on the **System parameters** page.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c0fa4-123">Amikor első alkalommal nyitja meg a **Súgó** lapot, kapcsolódnia kell a Lifecycle Services szolgáltatáshoz.</span><span class="sxs-lookup"><span data-stu-id="c0fa4-123">The first time that you open the **Help** tab, you must connect to Lifecycle Services.</span></span> <span data-ttu-id="c0fa4-124">Ügyeljen arra, hogy az űrlap közepén levő hivatkozásra kattintson, várja meg a kapcsolatot, zárja be a párbeszédpanelt, majd kattintson az **OK** gombra a **Rendszerparaméterek** oldal eléréséhez.</span><span class="sxs-lookup"><span data-stu-id="c0fa4-124">Be sure to select the link in the middle of the form, wait for the connection, close the dialog box, and then select **OK** to get to the **System Parameters** page.</span></span>
>
> <span data-ttu-id="c0fa4-125">[![Kapcsolódás az LCS szolgáltatáshoz](./media/connect-to-lcs-crop-1024x365.png "Kapcsolódás az LCS szolgáltatáshoz")](./media/connect-to-lcs-crop.png)</span><span class="sxs-lookup"><span data-stu-id="c0fa4-125">[![Connect to LCS](./media/connect-to-lcs-crop-1024x365.png "Connect to LCS")](./media/connect-to-lcs-crop.png)</span></span>

1. <span data-ttu-id="c0fa4-126">A csatlakozáshoz válassza ki a Lifecycle Services-projektet.</span><span class="sxs-lookup"><span data-stu-id="c0fa4-126">Select the Lifecycle Services project to connect to.</span></span>
2. <span data-ttu-id="c0fa4-127">Válassza ki a BPM könyvtárakat (a kiválasztott projekten belül) amelyekből szeretné előhívni a rögzítéseket.</span><span class="sxs-lookup"><span data-stu-id="c0fa4-127">Select the BPM libraries (within the selected project) to retrieve task recordings from.</span></span>
3. <span data-ttu-id="c0fa4-128">Adja meg a BPM könyvtárak megjelenítési sorrendjét.</span><span class="sxs-lookup"><span data-stu-id="c0fa4-128">Set the display order of the BPM libraries.</span></span> <span data-ttu-id="c0fa4-129">A megjelenítési sorrend meghatározza a sorrendet, amelyben a feladatrögzítések megjelennek a **Súgó** ablakban.</span><span class="sxs-lookup"><span data-stu-id="c0fa4-129">The display order defines the order in which task recordings from the libraries will appear in the **Help** pane.</span></span>

<span data-ttu-id="c0fa4-130">Miután végrehajtotta ezeket a lépéseket, nyissa meg a **Súgó** ablakot, és kattintson a **Feladat-útmutatók** lapra. Ekkor megjelennek a Finance and Operations-alkalmazások aktuális oldalához kapcsolódó feladat-útmutatók.</span><span class="sxs-lookup"><span data-stu-id="c0fa4-130">After you complete these steps, you can open the **Help** pane and select the **Task guides** tab. You'll now see the task guides that apply to the page that you're currently on in Finance and Operations apps.</span></span> <span data-ttu-id="c0fa4-131">Amennyiben nem találhatók feladat-útmutatók, kulcsszavak beírásával módosíthatja a keresést.</span><span class="sxs-lookup"><span data-stu-id="c0fa4-131">If no task guides are found, you can enter keywords to refine your search.</span></span>

### <a name="showing-translated-task-guides"></a><span data-ttu-id="c0fa4-132">Lefordított feladat-útmutatók megjelenítése</span><span class="sxs-lookup"><span data-stu-id="c0fa4-132">Showing translated task guides</span></span>

<span data-ttu-id="c0fa4-133">A honosított feladat-útmutatók először a 2016. májusi APQC Egyesített könyvtárban, valamint az Első lépések könyvtárban lettek szállítva.</span><span class="sxs-lookup"><span data-stu-id="c0fa4-133">Translated task guides were first released in the May 2016 APQC Unified Library and in the Getting Started library.</span></span> <span data-ttu-id="c0fa4-134">Ha szeretné a honosított feladat-útmutató súgóját látni, győződjön meg róla, hogy a Dynamics 365 megoldása csatlakoztatva van a 2016. május könyvtárhoz.</span><span class="sxs-lookup"><span data-stu-id="c0fa4-134">To view localized task guide Help, make sure that your Dynamics 365 solution is connected to the May 2016 library.</span></span> <span data-ttu-id="c0fa4-135">A felhasználók a **Beállítások** &gt; **Beállítások** menüben található nyelvi beállítások alatt módosíthatják a feladat-útmutató megjelenítési nyelvét.</span><span class="sxs-lookup"><span data-stu-id="c0fa4-135">Users can change the language that a task guide appears in by changing the language settings under **Options** &gt; **Preferences**.</span></span>

> [!NOTE]
> <span data-ttu-id="c0fa4-136">Annak ellenére, hogy sok feladat-útmutató le van már fordítva, az ügyfél jelenleg nem jelzi a lefordított feladat-útmutatók neveit.</span><span class="sxs-lookup"><span data-stu-id="c0fa4-136">Although many task guides have been translated, the client doesn't currently show the translated task guide names.</span></span> <span data-ttu-id="c0fa4-137">Valamint csak a 2016. februárban megjelent feladat-útmutatók fordításai elérhetőek a 2016. május könyvtárban jelenleg.</span><span class="sxs-lookup"><span data-stu-id="c0fa4-137">Additionally, in the May 2016 library, translations are available only for the task guides that were released in February 2016.</span></span> <span data-ttu-id="c0fa4-138">A Microsoft további fordításokat tartalmazó frissített könyvtárat fog megjelentetni hamarosan.</span><span class="sxs-lookup"><span data-stu-id="c0fa4-138">Microsoft will release an updated library that includes additional translations.</span></span>
>
> - <span data-ttu-id="c0fa4-139">Ha egy feladat-útmutató le van fordítva, akkor a kiválasztott nyelven fog megjelenni a feladat-útmutató teljes szövege.</span><span class="sxs-lookup"><span data-stu-id="c0fa4-139">If a task guide has been translated, when you open that task guide all the text of the task guide will appear in your selected language.</span></span>
> - <span data-ttu-id="c0fa4-140">Ha egy feladat-útmutató még nincs lefordítva, akkor a kiválasztott nyelven csak néhány szöveg (a vezérlők szövegei) fog megjelenni.</span><span class="sxs-lookup"><span data-stu-id="c0fa4-140">If a task guide has not yet been translated, when you open it, only some of the text (the text of the controls) will appear in your selected language.</span></span>

## <a name="adding-custom-help"></a><span data-ttu-id="c0fa4-141">Egyéni súgó hozzáadása</span><span class="sxs-lookup"><span data-stu-id="c0fa4-141">Adding custom Help</span></span>

<span data-ttu-id="c0fa4-142">A feladat-útmutatók használatával egyéni súgót hozhat létre, vagy csatlakoztathat egy egyéni Súgó webhelyet a **Súgó** panelhez.</span><span class="sxs-lookup"><span data-stu-id="c0fa4-142">You can use task guides to create custom Help, or you can connect a custom Help website to the **Help** pane.</span></span>

### <a name="create-custom-help-by-using-task-guides"></a><span data-ttu-id="c0fa4-143">Egyéni súgó létrehozása feladat-útmutatókkal</span><span class="sxs-lookup"><span data-stu-id="c0fa4-143">Create custom Help by using task guides</span></span>

<span data-ttu-id="c0fa4-144">Lehetősége van egyéni súgót létrehozni a támogatott alkalmazásokhoz; ehhez létre kell hoznia az egyedi megoldásokat magukban foglaló feladatrögzítéseket, majd azokat egy LCS Üzletifolyamat-tárba kell mentenie.</span><span class="sxs-lookup"><span data-stu-id="c0fa4-144">You can create custom Help for the supported apps by creating task recordings that reflect your implementation and then saving them to a Business process library in LCS.</span></span> <span data-ttu-id="c0fa4-145">A Human Resources rendszerben nem hozhat létre egyéni feladat-útmutatókat.</span><span class="sxs-lookup"><span data-stu-id="c0fa4-145">You can't create custom task guides for Human Resources.</span></span>

<span data-ttu-id="c0fa4-146">Ha partnerként hozzájárul egy könyvtárral egy vállalati tár kialakításához, valamint beilleszti azt egy megoldásba, akkor az a vevői számára elérhetővé válik.</span><span class="sxs-lookup"><span data-stu-id="c0fa4-146">If you're a partner, and you promote a library to a corporate library and include it in a solution, it will be available to your customers.</span></span> <span data-ttu-id="c0fa4-147">Ezenkívül az APQC Egyesített globális tárról is készíthet másolatot; megnyithatja a saját másolatot és az abban található feladatrögzítéseket, szerkesztheti őket, majd elmentheti a módosításait.</span><span class="sxs-lookup"><span data-stu-id="c0fa4-147">You can also make a copy of the APQC Unified Library, and then open the task recordings in the copy, edit them, and save your changes.</span></span> <span data-ttu-id="c0fa4-148">További tájékoztatás: [Feladatrögzítő erőforrásai](../../dev-itpro/user-interface/task-recorder.md).</span><span class="sxs-lookup"><span data-stu-id="c0fa4-148">For more information, see [Task recorder resources](../../dev-itpro/user-interface/task-recorder.md).</span></span>

### <a name="connect-a-custom-help-site"></a><span data-ttu-id="c0fa4-149">Egyéni súgóoldal csatlakoztatása</span><span class="sxs-lookup"><span data-stu-id="c0fa4-149">Connect a custom Help site</span></span>

<span data-ttu-id="c0fa4-150">A Finance and Operations alkalmazások ritkán használatosak a gyári állapotukban.</span><span class="sxs-lookup"><span data-stu-id="c0fa4-150">Finance and Operations apps are rarely used in their out-of-box form.</span></span> <span data-ttu-id="c0fa4-151">Helyette a megoldást testreszabják, és kiterjesztik, hogy megfeleljen a szervezet igényeihez.</span><span class="sxs-lookup"><span data-stu-id="c0fa4-151">Instead, the solution is customized and extended to fit the organization's needs.</span></span> <span data-ttu-id="c0fa4-152">A Súgó élményét testreszabhatja és ki is bővítheti.</span><span class="sxs-lookup"><span data-stu-id="c0fa4-152">You can also customize and extend the Help experience.</span></span> <span data-ttu-id="c0fa4-153">Lehetőség van például egyéni súgó hozzáadására a terméken belüli **Súgó** panelen.</span><span class="sxs-lookup"><span data-stu-id="c0fa4-153">For example, you can add custom Help to the in-product **Help** pane.</span></span>

<span data-ttu-id="c0fa4-154">A Microsoft egy eszközkészletet biztosít egyéni súgók telepítéséhez és csatlakoztatásához a **Súgó** panelen.</span><span class="sxs-lookup"><span data-stu-id="c0fa4-154">Microsoft has provided a toolkit to help you deploy and connect custom Help to the **Help** pane.</span></span> <span data-ttu-id="c0fa4-155">A **Súgó** panelhez kapcsolt egyéni súgótartalom beállításával kapcsolatos tudnivalókat lásd: [Egyéni Súgó – áttekintés](../../dev-itpro/help/custom-help-overview.md).</span><span class="sxs-lookup"><span data-stu-id="c0fa4-155">For information about how you can set up a custom Help solution that is connected to the **Help** pane, see [Custom Help overview](../../dev-itpro/help/custom-help-overview.md).</span></span>

<span data-ttu-id="c0fa4-156">Ha együtt szeretne működni a Microsofttal a Súgó testreszabásához szükséges eszközökkel és folyamatokkal kapcsolatban, töltse ki a következő címen található űrlapot: [https://aka.ms/customhelpfeedback](https://aka.ms/customhelpfeedback).</span><span class="sxs-lookup"><span data-stu-id="c0fa4-156">If you want to collaborate with Microsoft on tools and processes for customizing Help, fill in the form at [https://aka.ms/customhelpfeedback](https://aka.ms/customhelpfeedback).</span></span>

## <a name="see-also"></a><span data-ttu-id="c0fa4-157">Lásd még</span><span class="sxs-lookup"><span data-stu-id="c0fa4-157">See also</span></span>

[<span data-ttu-id="c0fa4-158">Súgórendszer</span><span class="sxs-lookup"><span data-stu-id="c0fa4-158">Help system</span></span>](help-overview.md)  
[<span data-ttu-id="c0fa4-159">Egyéni Súgó – áttekintés</span><span class="sxs-lookup"><span data-stu-id="c0fa4-159">Custom Help overview</span></span>](../../dev-itpro/help/custom-help-overview.md)  
[<span data-ttu-id="c0fa4-160">Feladatrögzítő erőforrásai</span><span class="sxs-lookup"><span data-stu-id="c0fa4-160">Task recorder resources</span></span>](../../dev-itpro/user-interface/task-recorder.md)  
[<span data-ttu-id="c0fa4-161">Dokumentáció vagy képzés létrehozása Feladatrögzítő segítségével</span><span class="sxs-lookup"><span data-stu-id="c0fa4-161">Create documentation or training with Task Recorder</span></span>](../../dev-itpro/user-interface/task-recorder-training-docs.md)  
[<span data-ttu-id="c0fa4-162">Egyéni súgó GitHub-tárház</span><span class="sxs-lookup"><span data-stu-id="c0fa4-162">Custom Help GitHub repository</span></span>](https://github.com/microsoft/dynamics356f-o-custom-help)  
