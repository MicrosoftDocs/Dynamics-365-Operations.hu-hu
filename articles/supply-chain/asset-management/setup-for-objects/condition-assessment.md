---
title: Állapotfelmérés
description: Ez a témakör azt ismerteti, hogy miként hozhat létre állapotfelmérő sablont és regisztrációt egy eszközhöz az Eszközkezelés segítségével.
author: josaw1
manager: tfehr
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetObjectCondition, EntAssetConditionTemplate
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 774c788959c5ebea69b4d22c886ac673f50b97f5
ms.sourcegitcommit: c986d5234b81d31cc6d054298be6f6ec92c1754c
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/25/2020
ms.locfileid: "3889793"
---
# <a name="condition-assessment"></a><span data-ttu-id="e5f1b-103">Állapotfelmérés</span><span class="sxs-lookup"><span data-stu-id="e5f1b-103">Condition assessment</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="e5f1b-104">Ez a témakör azt ismerteti, hogy miként hozhat létre állapotfelmérő sablont és regisztrációt egy eszközhöz az Eszközkezelés segítségével.</span><span class="sxs-lookup"><span data-stu-id="e5f1b-104">This topic explains how to create a condition assessment template and registration on an asset in Asset Management.</span></span> <span data-ttu-id="e5f1b-105">Az állapot felmérését szabályos időközönként végzik, és az elsődleges cél az eszközökre vonatkozó állapotadatok létrehozása és karbantartása.</span><span class="sxs-lookup"><span data-stu-id="e5f1b-105">Condition assessment is performed at regular intervals, and the primary objective is to create and maintain condition data on assets.</span></span> <span data-ttu-id="e5f1b-106">A megelőző karbantartás szempontjából, fontos, hogy figyelemmel kísérjék legfontosabb információkat, mint a jelenlegi állapot, és a fennmaradó élettartam.</span><span class="sxs-lookup"><span data-stu-id="e5f1b-106">Seen from a preventive maintenance perspective, it is important to monitor key information such as current condition, and remaining life span.</span></span> <span data-ttu-id="e5f1b-107">Továbbá, ha rendszeres időközönként elvégzi az állapotfelmérést, megfigyelheti és összehasonlíthatja a gépek állapotát a gyárban.</span><span class="sxs-lookup"><span data-stu-id="e5f1b-107">Furthermore, if you carry out condition assessment at regular intervals, you will be able to monitor and compare conditions on the machinery in your factory.</span></span>

<span data-ttu-id="e5f1b-108">Az állapotfelmérés segítségével számos feltételt mérhetnek és figyelhetnek a berendezésekben.</span><span class="sxs-lookup"><span data-stu-id="e5f1b-108">Condition assessment can be used to measure and monitor many conditions on your equipment.</span></span> <span data-ttu-id="e5f1b-109">Példa: Mérheti a rezgéseket egy gépen.</span><span class="sxs-lookup"><span data-stu-id="e5f1b-109">Example: You could measure vibrations on your machinery.</span></span> <span data-ttu-id="e5f1b-110">Miután vibrációs méréseket regisztrált az Eszközkezelésben több különböző géphez, kereshet a legújabb regisztrált felmérésre, és megtekintheti a legújabb vibrációs méréseket.</span><span class="sxs-lookup"><span data-stu-id="e5f1b-110">After you have registered vibration measurements in Asset Management on various types of equipment, you can search for the latest registered assessment and view vibration measurements.</span></span>

<span data-ttu-id="e5f1b-111">Az állapotfelmérés eszközökre vonatkozóan készül.</span><span class="sxs-lookup"><span data-stu-id="e5f1b-111">Condition assessment is created on assets.</span></span> <span data-ttu-id="e5f1b-112">Állapotfelmérési eljárás végrehajtása előtt be kell állítania egy állapotfelmérési sablont egy eszköztípusra.</span><span class="sxs-lookup"><span data-stu-id="e5f1b-112">You set up a condition assessment template on an asset type before you carry out the condition assessment procedure.</span></span> <span data-ttu-id="e5f1b-113">A sablonok használatának oka az állapotfelméréshez az, hogy elkerülhető legyen a hasonló eszközökre vonatkozó állapotadatok eltérése.</span><span class="sxs-lookup"><span data-stu-id="e5f1b-113">The reason for using templates for condition assessment is to avoid variation of condition data on similar assets.</span></span> <span data-ttu-id="e5f1b-114">Az Eszközkezelésben az állapotfelmérés létrehozásának és használatának sorrendje: Először beállítja a szükséges állapotfelmérési sablonokat.</span><span class="sxs-lookup"><span data-stu-id="e5f1b-114">The sequence for setting up and using condition assessment in Asset Management is: First you set up the required condition assessment templates.</span></span> <span data-ttu-id="e5f1b-115">Ezt követően társítja a sablonokat az **Eszköztípusok** képernyőn található eszköztípusokkal.</span><span class="sxs-lookup"><span data-stu-id="e5f1b-115">Next, you associate templates with asset types in the **Asset types** form.</span></span> <span data-ttu-id="e5f1b-116">Végül az **Eszköz** űrlapon szereplő eszközökhöz létrehozhat állapotfelmérési regisztrációkat.</span><span class="sxs-lookup"><span data-stu-id="e5f1b-116">Finally, you can create condition assessment registrations on an asset in the **Asset** form.</span></span>

## <a name="create-a-condition-assessment-template"></a><span data-ttu-id="e5f1b-117">Állapotfelmérési sablon létrehozása</span><span class="sxs-lookup"><span data-stu-id="e5f1b-117">Create a condition assessment template</span></span>

1. <span data-ttu-id="e5f1b-118">Válassza az **Eszközkezelés** > **Beállítások** > **Eszköztípusok** > **Állapotfelmérés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="e5f1b-118">Select **Asset management** > **Setup** > **Asset types** > **Condition assessment**.</span></span>
2. <span data-ttu-id="e5f1b-119">Válassza az **Új** lehetőséget egy új sablon létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="e5f1b-119">Select **New** to create a new template.</span></span>
3. <span data-ttu-id="e5f1b-120">A **Sablonazonosító** mezőbe írja be a sablon azonosítóját.</span><span class="sxs-lookup"><span data-stu-id="e5f1b-120">Insert and ID for the template in the **Template** field.</span></span>
4. <span data-ttu-id="e5f1b-121">Adjon meg egy nevet a sablonnak a **Név** mezőben.</span><span class="sxs-lookup"><span data-stu-id="e5f1b-121">Insert a name for the template in the **Name** field.</span></span>
5. <span data-ttu-id="e5f1b-122">Az **Állapotfelmérési sorok** gyorslapon adja hozzá az állapotfelméréshez szükséges sorokat, beleértve a megfelelő feltételtípus és mértékegység kiválasztását.</span><span class="sxs-lookup"><span data-stu-id="e5f1b-122">On the **Condition assessment lines** FastFab, add the lines required for the condition assessment, including selection of the appropriate condition type and measurement unit.</span></span>
6. <span data-ttu-id="e5f1b-123">Az **Eszköztípusok** gyorslapon adja meg azokat az eszköztípusokat, amelyeket az állapotfelmérési-sablon használhat.</span><span class="sxs-lookup"><span data-stu-id="e5f1b-123">On the **Asset types** FastTab, add the asset types that should use the condition assessment template.</span></span>
7. <span data-ttu-id="e5f1b-124">A **Sorok** és **Eszköztípusok** mezőkben a **Részletek** csoportban sorokban a kiválasztott állapotfelmérő sablonhoz kapcsolódó felmérési sorok és eszköztípusok száma látható.</span><span class="sxs-lookup"><span data-stu-id="e5f1b-124">In the **Lines** and **Asset types** fields in the **Details** group at the top of the screen, you will see the number of assessment lines and asset types related to the selected condition assessment template.</span></span>


## <a name="create-condition-assessment-registration-on-an-asset"></a><span data-ttu-id="e5f1b-125">Állapotfelmérés regisztrációjának létrehozása egy eszközhöz</span><span class="sxs-lookup"><span data-stu-id="e5f1b-125">Create condition assessment registration on an asset</span></span>

1. <span data-ttu-id="e5f1b-126">Válassza ki az **Eszközkezelés** > **Általános** > **Eszközök** > **Összes eszköz** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="e5f1b-126">Select **Asset management** > **Common** > **Assets** > **All Assets**.</span></span>
2. <span data-ttu-id="e5f1b-127">A listáról válassza ki azt az eszközt, amelyhez állapotfelmérés-regisztrációt szeretne létrehozni.</span><span class="sxs-lookup"><span data-stu-id="e5f1b-127">In the list, select the asset for which you want to create a condition assessment registration.</span></span>
3. <span data-ttu-id="e5f1b-128">Az **Általános** lapon kattintson az **Állapotfelmérés** gombra.</span><span class="sxs-lookup"><span data-stu-id="e5f1b-128">On the **General** tab, click **Condition assessment**.</span></span>
4. <span data-ttu-id="e5f1b-129">Új regisztráció létrehozásához kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="e5f1b-129">Click **New** to make a new registration.</span></span>
5. <span data-ttu-id="e5f1b-130">Válassza ki a **Dátum** mezőben az állapotfelmérés dátumát.</span><span class="sxs-lookup"><span data-stu-id="e5f1b-130">Select the date for the condition assessment in the **Date** field.</span></span>
6. <span data-ttu-id="e5f1b-131">Válassza ki annak a munkavállalónak a nevét, a **Dolgozó** mezőben a állapotfelmérést végezte.</span><span class="sxs-lookup"><span data-stu-id="e5f1b-131">Select the name of the worker who carried out the assessment registration in the **Worker** field.</span></span>
7. <span data-ttu-id="e5f1b-132">A **Sorok** mezőben az állapotfelméréshez beállított felmérési sorok száma látható.</span><span class="sxs-lookup"><span data-stu-id="e5f1b-132">In the **Lines** field, you see the number of assessment lines set up on the condition assessment.</span></span>
8. <span data-ttu-id="e5f1b-133">Válassza ki a **Sablon** mezőben az állapotfelmérés sablonját.</span><span class="sxs-lookup"><span data-stu-id="e5f1b-133">Select a template for the condition assessment in the **Template** field.</span></span> <span data-ttu-id="e5f1b-134">A program automatikusan beszúrja a sablon nevét a **Név** mezőbe, és a kapcsolódó regisztrációs sorokat beilleszti az **Állapotfelmérés-sorok** gyorslapra.</span><span class="sxs-lookup"><span data-stu-id="e5f1b-134">The name of the template is automatically inserted in the **Name** field, and the related registration lines are inserted on the **Condition assessment lines** FastTab.</span></span>
9. <span data-ttu-id="e5f1b-135">A kiválasztott állapotfelmérésre vonatkozó megjegyzéseket a **Megjegyzések** gyorslapon illeszthet be.</span><span class="sxs-lookup"><span data-stu-id="e5f1b-135">You can insert notes relating to the selected condition assessment on the **Notes** FastTab.</span></span>
10. <span data-ttu-id="e5f1b-136">Az egyes állapootfelérési sorok esetében írja be a mérési adatokat az **Érték** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="e5f1b-136">For each condition assessment line, insert measurement data in the **Value** field.</span></span>
11. <span data-ttu-id="e5f1b-137">A kiválasztott regisztrációs sorhoz kapcsolódó megjegyzést az **Állapotfelmérési sorok** gyorslap > **Megjegyzések** mezőjében lehet beszúrni.</span><span class="sxs-lookup"><span data-stu-id="e5f1b-137">You can insert a comment relating to the selected registration line on the **Condition assessment lines** FastTab > **Comments** field.</span></span> <span data-ttu-id="e5f1b-138">Ha megjegyzést fűz egy sorhoz, a **Megjegyzés** jelölőnégyzet automatikusan be lesz jelölve.</span><span class="sxs-lookup"><span data-stu-id="e5f1b-138">If you add a comment on a line, the **Comment** check box is automatically selected.</span></span>

<span data-ttu-id="e5f1b-139">Ha egy eszközhöz állapotfelmérés-regisztrációt végzett, kinyomtathat egy állapotértékelő jelentést.</span><span class="sxs-lookup"><span data-stu-id="e5f1b-139">After you have made a condition assessment registration on an asset, you can print a condition assessment report.</span></span>

>[!NOTE]
><span data-ttu-id="e5f1b-140">Az állapotfelmérést regisztrálhatja egy munkarendelésen is (**Eszközkezelés** > **Közös** > **Munkarendelések** > **Összes munkarendelés** > **Állapotfelmérések** gomb.)</span><span class="sxs-lookup"><span data-stu-id="e5f1b-140">You can also register condition assessment on a work order (**Asset management** > **Common** > **Work orders** > **All Work orders** > **Condition assessment** button.)</span></span>
