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
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1d84520413659db32713711ad5ac980f1e8b5519
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5217173"
---
# <a name="condition-assessment"></a><span data-ttu-id="f89e4-103">Állapotfelmérés</span><span class="sxs-lookup"><span data-stu-id="f89e4-103">Condition assessment</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="f89e4-104">Ez a témakör azt ismerteti, hogy miként hozhat létre állapotfelmérő sablont és regisztrációt egy eszközhöz az Eszközkezelés segítségével.</span><span class="sxs-lookup"><span data-stu-id="f89e4-104">This topic explains how to create a condition assessment template and registration on an asset in Asset Management.</span></span> <span data-ttu-id="f89e4-105">Az állapot felmérését szabályos időközönként végzik, és az elsődleges cél az eszközökre vonatkozó állapotadatok létrehozása és karbantartása.</span><span class="sxs-lookup"><span data-stu-id="f89e4-105">Condition assessment is performed at regular intervals, and the primary objective is to create and maintain condition data on assets.</span></span> <span data-ttu-id="f89e4-106">A megelőző karbantartás szempontjából, fontos, hogy figyelemmel kísérjék legfontosabb információkat, mint a jelenlegi állapot, és a fennmaradó élettartam.</span><span class="sxs-lookup"><span data-stu-id="f89e4-106">Seen from a preventive maintenance perspective, it is important to monitor key information such as current condition, and remaining life span.</span></span> <span data-ttu-id="f89e4-107">Továbbá, ha rendszeres időközönként elvégzi az állapotfelmérést, megfigyelheti és összehasonlíthatja a gépek állapotát a gyárban.</span><span class="sxs-lookup"><span data-stu-id="f89e4-107">Furthermore, if you carry out condition assessment at regular intervals, you will be able to monitor and compare conditions on the machinery in your factory.</span></span>

<span data-ttu-id="f89e4-108">Az állapotfelmérés segítségével számos feltételt mérhetnek és figyelhetnek a berendezésekben.</span><span class="sxs-lookup"><span data-stu-id="f89e4-108">Condition assessment can be used to measure and monitor many conditions on your equipment.</span></span> <span data-ttu-id="f89e4-109">Példa: Mérheti a rezgéseket egy gépen.</span><span class="sxs-lookup"><span data-stu-id="f89e4-109">Example: You could measure vibrations on your machinery.</span></span> <span data-ttu-id="f89e4-110">Miután vibrációs méréseket regisztrált az Eszközkezelésben több különböző géphez, kereshet a legújabb regisztrált felmérésre, és megtekintheti a legújabb vibrációs méréseket.</span><span class="sxs-lookup"><span data-stu-id="f89e4-110">After you have registered vibration measurements in Asset Management on various types of equipment, you can search for the latest registered assessment and view vibration measurements.</span></span>

<span data-ttu-id="f89e4-111">Az állapotfelmérés eszközökre vonatkozóan készül.</span><span class="sxs-lookup"><span data-stu-id="f89e4-111">Condition assessment is created on assets.</span></span> <span data-ttu-id="f89e4-112">Állapotfelmérési eljárás végrehajtása előtt be kell állítania egy állapotfelmérési sablont egy eszköztípusra.</span><span class="sxs-lookup"><span data-stu-id="f89e4-112">You set up a condition assessment template on an asset type before you carry out the condition assessment procedure.</span></span> <span data-ttu-id="f89e4-113">A sablonok használatának oka az állapotfelméréshez az, hogy elkerülhető legyen a hasonló eszközökre vonatkozó állapotadatok eltérése.</span><span class="sxs-lookup"><span data-stu-id="f89e4-113">The reason for using templates for condition assessment is to avoid variation of condition data on similar assets.</span></span> <span data-ttu-id="f89e4-114">Az Eszközkezelésben az állapotfelmérés létrehozásának és használatának sorrendje: Először beállítja a szükséges állapotfelmérési sablonokat.</span><span class="sxs-lookup"><span data-stu-id="f89e4-114">The sequence for setting up and using condition assessment in Asset Management is: First you set up the required condition assessment templates.</span></span> <span data-ttu-id="f89e4-115">Ezt követően társítja a sablonokat az **Eszköztípusok** képernyőn található eszköztípusokkal.</span><span class="sxs-lookup"><span data-stu-id="f89e4-115">Next, you associate templates with asset types in the **Asset types** form.</span></span> <span data-ttu-id="f89e4-116">Végül az **Eszköz** űrlapon szereplő eszközökhöz létrehozhat állapotfelmérési regisztrációkat.</span><span class="sxs-lookup"><span data-stu-id="f89e4-116">Finally, you can create condition assessment registrations on an asset in the **Asset** form.</span></span>

## <a name="create-a-condition-assessment-template"></a><span data-ttu-id="f89e4-117">Állapotfelmérési sablon létrehozása</span><span class="sxs-lookup"><span data-stu-id="f89e4-117">Create a condition assessment template</span></span>

1. <span data-ttu-id="f89e4-118">Válassza az **Eszközkezelés** > **Beállítások** > **Eszköztípusok** > **Állapotfelmérés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f89e4-118">Select **Asset management** > **Setup** > **Asset types** > **Condition assessment**.</span></span>
2. <span data-ttu-id="f89e4-119">Válassza az **Új** lehetőséget egy új sablon létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="f89e4-119">Select **New** to create a new template.</span></span>
3. <span data-ttu-id="f89e4-120">A **Sablonazonosító** mezőbe írja be a sablon azonosítóját.</span><span class="sxs-lookup"><span data-stu-id="f89e4-120">Insert and ID for the template in the **Template** field.</span></span>
4. <span data-ttu-id="f89e4-121">Adjon meg egy nevet a sablonnak a **Név** mezőben.</span><span class="sxs-lookup"><span data-stu-id="f89e4-121">Insert a name for the template in the **Name** field.</span></span>
5. <span data-ttu-id="f89e4-122">Az **Állapotfelmérési sorok** gyorslapon adja hozzá az állapotfelméréshez szükséges sorokat, beleértve a megfelelő feltételtípus és mértékegység kiválasztását.</span><span class="sxs-lookup"><span data-stu-id="f89e4-122">On the **Condition assessment lines** FastFab, add the lines required for the condition assessment, including selection of the appropriate condition type and measurement unit.</span></span>
6. <span data-ttu-id="f89e4-123">Az **Eszköztípusok** gyorslapon adja meg azokat az eszköztípusokat, amelyeket az állapotfelmérési-sablon használhat.</span><span class="sxs-lookup"><span data-stu-id="f89e4-123">On the **Asset types** FastTab, add the asset types that should use the condition assessment template.</span></span>
7. <span data-ttu-id="f89e4-124">A **Sorok** és **Eszköztípusok** mezőkben a **Részletek** csoportban sorokban a kiválasztott állapotfelmérő sablonhoz kapcsolódó felmérési sorok és eszköztípusok száma látható.</span><span class="sxs-lookup"><span data-stu-id="f89e4-124">In the **Lines** and **Asset types** fields in the **Details** group at the top of the screen, you will see the number of assessment lines and asset types related to the selected condition assessment template.</span></span>


## <a name="create-condition-assessment-registration-on-an-asset"></a><span data-ttu-id="f89e4-125">Állapotfelmérés regisztrációjának létrehozása egy eszközhöz</span><span class="sxs-lookup"><span data-stu-id="f89e4-125">Create condition assessment registration on an asset</span></span>

1. <span data-ttu-id="f89e4-126">Válassza ki az **Eszközkezelés** > **Általános** > **Eszközök** > **Összes eszköz** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f89e4-126">Select **Asset management** > **Common** > **Assets** > **All Assets**.</span></span>
2. <span data-ttu-id="f89e4-127">A listáról válassza ki azt az eszközt, amelyhez állapotfelmérés-regisztrációt szeretne létrehozni.</span><span class="sxs-lookup"><span data-stu-id="f89e4-127">In the list, select the asset for which you want to create a condition assessment registration.</span></span>
3. <span data-ttu-id="f89e4-128">Az **Általános** lapon kattintson az **Állapotfelmérés** gombra.</span><span class="sxs-lookup"><span data-stu-id="f89e4-128">On the **General** tab, click **Condition assessment**.</span></span>
4. <span data-ttu-id="f89e4-129">Új regisztráció létrehozásához kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="f89e4-129">Click **New** to make a new registration.</span></span>
5. <span data-ttu-id="f89e4-130">Válassza ki a **Dátum** mezőben az állapotfelmérés dátumát.</span><span class="sxs-lookup"><span data-stu-id="f89e4-130">Select the date for the condition assessment in the **Date** field.</span></span>
6. <span data-ttu-id="f89e4-131">Válassza ki annak a munkavállalónak a nevét, a **Dolgozó** mezőben a állapotfelmérést végezte.</span><span class="sxs-lookup"><span data-stu-id="f89e4-131">Select the name of the worker who carried out the assessment registration in the **Worker** field.</span></span>
7. <span data-ttu-id="f89e4-132">A **Sorok** mezőben az állapotfelméréshez beállított felmérési sorok száma látható.</span><span class="sxs-lookup"><span data-stu-id="f89e4-132">In the **Lines** field, you see the number of assessment lines set up on the condition assessment.</span></span>
8. <span data-ttu-id="f89e4-133">Válassza ki a **Sablon** mezőben az állapotfelmérés sablonját.</span><span class="sxs-lookup"><span data-stu-id="f89e4-133">Select a template for the condition assessment in the **Template** field.</span></span> <span data-ttu-id="f89e4-134">A program automatikusan beszúrja a sablon nevét a **Név** mezőbe, és a kapcsolódó regisztrációs sorokat beilleszti az **Állapotfelmérés-sorok** gyorslapra.</span><span class="sxs-lookup"><span data-stu-id="f89e4-134">The name of the template is automatically inserted in the **Name** field, and the related registration lines are inserted on the **Condition assessment lines** FastTab.</span></span>
9. <span data-ttu-id="f89e4-135">A kiválasztott állapotfelmérésre vonatkozó megjegyzéseket a **Megjegyzések** gyorslapon illeszthet be.</span><span class="sxs-lookup"><span data-stu-id="f89e4-135">You can insert notes relating to the selected condition assessment on the **Notes** FastTab.</span></span>
10. <span data-ttu-id="f89e4-136">Az egyes állapootfelérési sorok esetében írja be a mérési adatokat az **Érték** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="f89e4-136">For each condition assessment line, insert measurement data in the **Value** field.</span></span>
11. <span data-ttu-id="f89e4-137">A kiválasztott regisztrációs sorhoz kapcsolódó megjegyzést az **Állapotfelmérési sorok** gyorslap > **Megjegyzések** mezőjében lehet beszúrni.</span><span class="sxs-lookup"><span data-stu-id="f89e4-137">You can insert a comment relating to the selected registration line on the **Condition assessment lines** FastTab > **Comments** field.</span></span> <span data-ttu-id="f89e4-138">Ha megjegyzést fűz egy sorhoz, a **Megjegyzés** jelölőnégyzet automatikusan be lesz jelölve.</span><span class="sxs-lookup"><span data-stu-id="f89e4-138">If you add a comment on a line, the **Comment** check box is automatically selected.</span></span>

<span data-ttu-id="f89e4-139">Ha egy eszközhöz állapotfelmérés-regisztrációt végzett, kinyomtathat egy állapotértékelő jelentést.</span><span class="sxs-lookup"><span data-stu-id="f89e4-139">After you have made a condition assessment registration on an asset, you can print a condition assessment report.</span></span>

>[!NOTE]
><span data-ttu-id="f89e4-140">Az állapotfelmérést regisztrálhatja egy munkarendelésen is (**Eszközkezelés** > **Közös** > **Munkarendelések** > **Összes munkarendelés** > **Állapotfelmérések** gomb.)</span><span class="sxs-lookup"><span data-stu-id="f89e4-140">You can also register condition assessment on a work order (**Asset management** > **Common** > **Work orders** > **All Work orders** > **Condition assessment** button.)</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]