---
title: Új dokumentum felhasználói felület az üzleti dokumentumkezelés modulban
description: Ez a témakör azt mutatja be, hogyan lehet használni az új dokumentum felhasználói felületet (UI) az elektronikus jelentési (ER) keretrendszer üzleti dokumentumkezelő funkciójában.
author: v-anamir
manager: AnnBe
ms.date: 05/12/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERBDWorkspace, ERBDParameters
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: v-anamir
ms.search.validFrom: 2019-08-01
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 4acde9703c721ab7c20d1603299a10dda91b23c4
ms.sourcegitcommit: b8f8ccab2cd9d848e5ecd71caaf0a63237e2236b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2020
ms.locfileid: "2957063"
---
# <a name="new-document-user-interface-in-business-document-management"></a><span data-ttu-id="72bf4-103">Új dokumentum felhasználói felület az üzleti dokumentumkezelés modulban</span><span class="sxs-lookup"><span data-stu-id="72bf4-103">New document user interface in Business document management</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="72bf4-104">Az Üzleti dokumentumkezelés lehetővé teszi az üzleti felhasználók számára, hogy a Microsoft Office 365 szolgáltatás vagy a megfelelő Microsoft Office asztali alkalmazások segítségével szerkesszék az üzleti dokumentumok sablonjait.</span><span class="sxs-lookup"><span data-stu-id="72bf4-104">Business document management lets business users edit business document templates by using a Microsoft Office 365 service or the appropriate Microsoft Office desktop application.</span></span> <span data-ttu-id="72bf4-105">A szerkesztések lehetnek tervezési változtatások vagy új telepítések, illetve a felhasználók hozzáadhatnak helyőrzőket, hogy a forráskód módosítása nélkül is hozzáadhatók legyenek további adatok.</span><span class="sxs-lookup"><span data-stu-id="72bf4-105">Edits might include design changes or new deployments, or users might add placeholders to include additional data without having to change the source code.</span></span> <span data-ttu-id="72bf4-106">Az üzleti dokumentumkezelés működésével kapcsolatos további tudnivalókat lásd: [Üzleti dokumentumkezelés – áttekintés.](er-business-document-management.md).</span><span class="sxs-lookup"><span data-stu-id="72bf4-106">For more information about how to work with Business document management, see [Business document management overview](er-business-document-management.md).</span></span>

<span data-ttu-id="72bf4-107">Az új dokumentum felhasználói felület (UI) egyértelműbb és kényelmesebben használható.</span><span class="sxs-lookup"><span data-stu-id="72bf4-107">The new document user interface (UI) is clearer and more comfortable to use.</span></span> <span data-ttu-id="72bf4-108">Az **Üzleti dokumentum** terület csak az aktuális szolgáltatóhoz rendelkezésre álló sablonokat jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="72bf4-108">The **Business document** area shows only the templates that are available for the current provider.</span></span>

<span data-ttu-id="72bf4-109">Az **Új dokumentum** gomb lehetővé teszi a felhasználók számára, hogy egy másik szolgáltató által biztosított elektronikus jelentési (ER) formátum konfigurációban hozzanak létre és szerkesszenek egy sablont.</span><span class="sxs-lookup"><span data-stu-id="72bf4-109">The **New document** button lets users create and edit a template in an Electronic reporting (ER) format configuration that is provided by another provider.</span></span> <span data-ttu-id="72bf4-110">Az ebben a témakörben szereplő példában a szolgáltató a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="72bf4-110">In the example in this topic, the provider is Microsoft.</span></span>

## <a name="make-the-new-document-ui-in-business-document-management-available"></a><span data-ttu-id="72bf4-111">Az új dokumentum kezelőfelület elérhetővé tétele az üzleti dokumentumkezelés modulban</span><span class="sxs-lookup"><span data-stu-id="72bf4-111">Make the new document UI in Business document management available</span></span>

<span data-ttu-id="72bf4-112">Ha azt szeretné, hogy a program az új dokumentum kezelőfelületet használja az üzleti dokumentumkezelés modulban, akkor be kell kapcsolni az **Office-szerű UI-élmény az üzleti Dokumentumkezelés számára** funkciót a **Funkciókezelés** munkaterületen.</span><span class="sxs-lookup"><span data-stu-id="72bf4-112">To start to use the new document UI in Business document management, you must turn on the **Office-like UI experience for Business document management** feature in the **Feature management** workspace.</span></span>

<span data-ttu-id="72bf4-113">Kövesse az alábbi lépéseket a funkció bekapcsolásához az összes jogi személynél.</span><span class="sxs-lookup"><span data-stu-id="72bf4-113">Follow these steps to turn on this feature for all legal entities.</span></span>

1. <span data-ttu-id="72bf4-114">A **Funkciókezelés** munkaterületen, az **Új** lapon válassza ki a listán az **Office-szerű UI-élmény az üzleti Dokumentumkezelés számára** funkciót.</span><span class="sxs-lookup"><span data-stu-id="72bf4-114">In the **Feature management** workspace, on the **New** tab, select the **Office-like UI experience for Business document management** feature in the list.</span></span>
2. <span data-ttu-id="72bf4-115">Válassza az **Engedélyezés most** lehetőséget a kiválasztott funkció bekapcsolásához.</span><span class="sxs-lookup"><span data-stu-id="72bf4-115">Select **Enable now** to turn on the selected feature.</span></span>
3. <span data-ttu-id="72bf4-116">Az új funkció eléréséhez frissítse a lapot.</span><span class="sxs-lookup"><span data-stu-id="72bf4-116">Refresh the page to access the new feature.</span></span>

### <a name="edit-templates-that-are-owned-by-other-providers"></a><span data-ttu-id="72bf4-117">Más szolgáltatók tulajdonában lévő sablonok szerkesztése</span><span class="sxs-lookup"><span data-stu-id="72bf4-117">Edit templates that are owned by other providers</span></span>

1. <span data-ttu-id="72bf4-118">Az **Üzleti dokumentumkezelés** munkaterületen válassza az **Új dokumentum** elemet.</span><span class="sxs-lookup"><span data-stu-id="72bf4-118">In the **Business document management** workspace, select **New document**.</span></span>

    ![Üzletidokumentum-kezelés munkaterület](./media/BDM_overview_new_template1.png)

2. <span data-ttu-id="72bf4-120">A párbeszédpanelen válassza ki a sablonként használni kívánt dokumentumot, majd válassza a **Dokumentum létrehozása** elemet.</span><span class="sxs-lookup"><span data-stu-id="72bf4-120">In the dialog box, select the document to use as a template, and then select **Create document**.</span></span>

    ![Üzleti dokumentumok párbeszédpanel](./media/BDM_overview_new_template2.png)

3. <span data-ttu-id="72bf4-122">Az új párbeszédpanelen, a **Cím** mezőben, módosítsa a címet szükség szerint.</span><span class="sxs-lookup"><span data-stu-id="72bf4-122">In the new dialog box, in the **Title** field, change the title as you require.</span></span> <span data-ttu-id="72bf4-123">A program az automatikusan létrehozott új ER-formátumkonfiguráció elnevezésére használja a címszöveget.</span><span class="sxs-lookup"><span data-stu-id="72bf4-123">The title text is used to name the new ER format configuration that is automatically created.</span></span> <span data-ttu-id="72bf4-124">A konfiguráció vázlatverziója (**Customer FTI report (GER) másolata**) tartalmazza a szerkesztett sablont, és az ER-formátum futtatásá lesz használva az aktuális felhasználóhoz.</span><span class="sxs-lookup"><span data-stu-id="72bf4-124">The draft version of this configuration (**Customer FTI report (GER) Copy**) will contain the edited template and will be used to run this ER format for the current user.</span></span> <span data-ttu-id="72bf4-125">A rendszer alap ER formátumból származó nem módosított eredeti sablon alapján futtatja ezt az ER formátumot bármely más felhasználó számára.</span><span class="sxs-lookup"><span data-stu-id="72bf4-125">The original template from the base ER format configuration will be used to run this ER format for every other user.</span></span>
4. <span data-ttu-id="72bf4-126">A **Név** mezőben módosítsa az automatikusan létrehozandó szerkeszthető sablon első verziójának nevét.</span><span class="sxs-lookup"><span data-stu-id="72bf4-126">In the **Name** field, change the name of the first revision of the editable template that will be automatically created.</span></span>
5. <span data-ttu-id="72bf4-127">A **Megjegyzés** mezőben módosítsa a szerkeszthető sablon automatikusan létrehozott verziójának megjegyzéseit.</span><span class="sxs-lookup"><span data-stu-id="72bf4-127">In the **Comment** field, update the remarks for the revision of the editable template that will be automatically created.</span></span>
6. <span data-ttu-id="72bf4-128">A szerkesztési folyamat kezdetének jóváhagyásához kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="72bf4-128">Select **OK** to confirm the start of the editing process.</span></span>

    ![Dokumentum-létrehozás párbeszédpanel](./media/BDM_overview_new_template3.png)

<span data-ttu-id="72bf4-130">Az **Új dokumentum** gomb lehetővé teszi, hogy egy másik szolgáltató által biztosított elektronikus jelentési (ER) formátum konfigurációban hozzunk létre és szerkesszünk egy sablont.</span><span class="sxs-lookup"><span data-stu-id="72bf4-130">The **New document** button is used to create and edit a template in an ER format configuration that is provided by another provider.</span></span> <span data-ttu-id="72bf4-131">Ebben a példában a szolgáltató a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="72bf4-131">In this example, the provider is Microsoft.</span></span> <span data-ttu-id="72bf4-132">Az **Új dokumentum** elem kiválasztásakor az aktuális és más szolgáltatók által birtokolt összes sablon látható.</span><span class="sxs-lookup"><span data-stu-id="72bf4-132">When you select **New document**, you can view all the templates that are owned by current and other providers.</span></span> <span data-ttu-id="72bf4-133">Miután kiválasztja a sablont, szerkesztésre megnyílik.</span><span class="sxs-lookup"><span data-stu-id="72bf4-133">After you select the template, it's opened for editing.</span></span> <span data-ttu-id="72bf4-134">Ezt követően a szerkesztett sablon egy új, automatikusan létrejövő ER formátumkonfigurációban lesz tárolva.</span><span class="sxs-lookup"><span data-stu-id="72bf4-134">The edited template will then be stored in a new ER format configuration that is automatically generated.</span></span>

<span data-ttu-id="72bf4-135">További tájékoztatás: [Üzleti dokumentumkezelés – áttekintés](er-business-document-management.md).</span><span class="sxs-lookup"><span data-stu-id="72bf4-135">For more information, see [Business document management overview](er-business-document-management.md).</span></span>
