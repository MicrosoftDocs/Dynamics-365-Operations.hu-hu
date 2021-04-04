---
title: Új dokumentum felhasználói felület az üzleti dokumentumkezelés modulban
description: Ez a témakör azt mutatja be, hogyan lehet használni az új dokumentum felhasználói felületet az elektronikus jelentések üzleti dokumentumkezelő funkciójában.
author: v-anamir
manager: AnnBe
ms.date: 05/12/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERBDWorkspace, ERBDParameters
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: v-anamir
ms.search.validFrom: 2019-08-01
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 7f8099f2f6872c34c30de918a6fc5fd27bcde958
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/09/2021
ms.locfileid: "5565710"
---
# <a name="new-document-user-interface-in-business-document-management"></a><span data-ttu-id="6da61-103">Új dokumentum-felhasználói felület az üzleti Dokumentumkezelés modulban</span><span class="sxs-lookup"><span data-stu-id="6da61-103">New document user interface in Business document management</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6da61-104">Az Üzleti dokumentumkezelés lehetővé teszi az üzleti felhasználók számára, hogy a Microsoft 365 szolgáltatás vagy a megfelelő Microsoft Office asztali alkalmazások segítségével szerkesszék az üzleti dokumentumok sablonjait.</span><span class="sxs-lookup"><span data-stu-id="6da61-104">Business document management lets business users edit business document templates by using a Microsoft 365 service or the appropriate Microsoft Office desktop application.</span></span> <span data-ttu-id="6da61-105">A szerkesztések lehetnek tervezési változtatások vagy új telepítések, illetve a felhasználók hozzáadhatnak helyőrzőket, hogy a forráskód módosítása nélkül is hozzáadhatók legyenek további adatok.</span><span class="sxs-lookup"><span data-stu-id="6da61-105">Edits might include design changes or new deployments, or users might add placeholders to include additional data without having to change the source code.</span></span> <span data-ttu-id="6da61-106">Az üzleti dokumentumkezelés működésével kapcsolatos további tudnivalókat lásd: [Üzleti dokumentumkezelés – áttekintés.](er-business-document-management.md).</span><span class="sxs-lookup"><span data-stu-id="6da61-106">For more information about how to work with Business document management, see [Business document management overview](er-business-document-management.md).</span></span>

<span data-ttu-id="6da61-107">Az új dokumentum felhasználói felület (UI) egyértelműbb és kényelmesebben használható.</span><span class="sxs-lookup"><span data-stu-id="6da61-107">The new document user interface (UI) is clearer and more comfortable to use.</span></span> <span data-ttu-id="6da61-108">Az **Üzleti dokumentum** terület csak az aktuális szolgáltatóhoz rendelkezésre álló sablonokat jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="6da61-108">The **Business document** area shows only the templates that are available for the current provider.</span></span>

<span data-ttu-id="6da61-109">Az **Új dokumentum** gomb lehetővé teszi a felhasználók számára, hogy egy másik szolgáltató által biztosított elektronikus jelentési (ER) formátum konfigurációban hozzanak létre és szerkesszenek egy sablont.</span><span class="sxs-lookup"><span data-stu-id="6da61-109">The **New document** button lets users create and edit a template in an Electronic reporting (ER) format configuration that is provided by another provider.</span></span> <span data-ttu-id="6da61-110">Az ebben a témakörben szereplő példában a szolgáltató a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6da61-110">In the example in this topic, the provider is Microsoft.</span></span>

## <a name="make-the-new-document-ui-in-business-document-management-available"></a><span data-ttu-id="6da61-111">Az új dokumentum kezelőfelület elérhetővé tétele az üzleti dokumentumkezelés modulban</span><span class="sxs-lookup"><span data-stu-id="6da61-111">Make the new document UI in Business document management available</span></span>

<span data-ttu-id="6da61-112">Ha azt szeretné, hogy a program az új dokumentum kezelőfelületet használja az üzleti dokumentumkezelés modulban, akkor be kell kapcsolni az **Office-szerű UI-élmény az üzleti Dokumentumkezelés számára** funkciót a **Funkciókezelés** munkaterületen.</span><span class="sxs-lookup"><span data-stu-id="6da61-112">To start to use the new document UI in Business document management, you must turn on the **Office-like UI experience for Business document management** feature in the **Feature management** workspace.</span></span>

<span data-ttu-id="6da61-113">Kövesse az alábbi lépéseket a funkció bekapcsolásához az összes jogi személynél.</span><span class="sxs-lookup"><span data-stu-id="6da61-113">Follow these steps to turn on this feature for all legal entities.</span></span>

1. <span data-ttu-id="6da61-114">A **Funkciókezelés** munkaterületen, az **Új** lapon válassza ki a listán az **Office-szerű UI-élmény az üzleti Dokumentumkezelés számára** funkciót.</span><span class="sxs-lookup"><span data-stu-id="6da61-114">In the **Feature management** workspace, on the **New** tab, select the **Office-like UI experience for Business document management** feature in the list.</span></span>
2. <span data-ttu-id="6da61-115">Válassza az **Engedélyezés most** lehetőséget a kiválasztott funkció bekapcsolásához.</span><span class="sxs-lookup"><span data-stu-id="6da61-115">Select **Enable now** to turn on the selected feature.</span></span>
3. <span data-ttu-id="6da61-116">Az új funkció eléréséhez frissítse a lapot.</span><span class="sxs-lookup"><span data-stu-id="6da61-116">Refresh the page to access the new feature.</span></span>

### <a name="edit-templates-that-are-owned-by-other-providers"></a><span data-ttu-id="6da61-117">Más szolgáltatók tulajdonában lévő sablonok szerkesztése</span><span class="sxs-lookup"><span data-stu-id="6da61-117">Edit templates that are owned by other providers</span></span>

1. <span data-ttu-id="6da61-118">Az **Üzleti dokumentumkezelés** munkaterületen válassza az **Új dokumentum** elemet.</span><span class="sxs-lookup"><span data-stu-id="6da61-118">In the **Business document management** workspace, select **New document**.</span></span>

    ![Üzletidokumentum-kezelés munkaterület](./media/BDM_overview_new_template1.png)

2. <span data-ttu-id="6da61-120">A párbeszédpanelen válassza ki a sablonként használni kívánt dokumentumot, majd válassza a **Dokumentum létrehozása** elemet.</span><span class="sxs-lookup"><span data-stu-id="6da61-120">In the dialog box, select the document to use as a template, and then select **Create document**.</span></span>

    ![Üzleti dokumentumok párbeszédpanel](./media/BDM_overview_new_template2.png)

3. <span data-ttu-id="6da61-122">Az új párbeszédpanelen, a **Cím** mezőben, módosítsa a címet szükség szerint.</span><span class="sxs-lookup"><span data-stu-id="6da61-122">In the new dialog box, in the **Title** field, change the title as you require.</span></span> <span data-ttu-id="6da61-123">A program az automatikusan létrehozott új ER-formátumkonfiguráció elnevezésére használja a címszöveget.</span><span class="sxs-lookup"><span data-stu-id="6da61-123">The title text is used to name the new ER format configuration that is automatically created.</span></span> <span data-ttu-id="6da61-124">A konfiguráció vázlatverziója (**Customer FTI report (GER) másolata**) tartalmazza a szerkesztett sablont, és az ER-formátum futtatásá lesz használva az aktuális felhasználóhoz.</span><span class="sxs-lookup"><span data-stu-id="6da61-124">The draft version of this configuration (**Customer FTI report (GER) Copy**) will contain the edited template and will be used to run this ER format for the current user.</span></span> <span data-ttu-id="6da61-125">A rendszer alap ER formátumból származó nem módosított eredeti sablon alapján futtatja ezt az ER formátumot bármely más felhasználó számára.</span><span class="sxs-lookup"><span data-stu-id="6da61-125">The original template from the base ER format configuration will be used to run this ER format for every other user.</span></span>
4. <span data-ttu-id="6da61-126">A **Név** mezőben módosítsa az automatikusan létrehozandó szerkeszthető sablon első verziójának nevét.</span><span class="sxs-lookup"><span data-stu-id="6da61-126">In the **Name** field, change the name of the first revision of the editable template that will be automatically created.</span></span>
5. <span data-ttu-id="6da61-127">A **Megjegyzés** mezőben módosítsa a szerkeszthető sablon automatikusan létrehozott verziójának megjegyzéseit.</span><span class="sxs-lookup"><span data-stu-id="6da61-127">In the **Comment** field, update the remarks for the revision of the editable template that will be automatically created.</span></span>
6. <span data-ttu-id="6da61-128">A szerkesztési folyamat kezdetének jóváhagyásához kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="6da61-128">Select **OK** to confirm the start of the editing process.</span></span>

    ![Dokumentum-létrehozás párbeszédpanel](./media/BDM_overview_new_template3.png)

<span data-ttu-id="6da61-130">Az **Új dokumentum** gomb lehetővé teszi, hogy egy másik szolgáltató által biztosított elektronikus jelentési (ER) formátum konfigurációban hozzunk létre és szerkesszünk egy sablont.</span><span class="sxs-lookup"><span data-stu-id="6da61-130">The **New document** button is used to create and edit a template in an ER format configuration that is provided by another provider.</span></span> <span data-ttu-id="6da61-131">Ebben a példában a szolgáltató a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6da61-131">In this example, the provider is Microsoft.</span></span> <span data-ttu-id="6da61-132">Az **Új dokumentum** elem kiválasztásakor az aktuális és más szolgáltatók által birtokolt összes sablon látható.</span><span class="sxs-lookup"><span data-stu-id="6da61-132">When you select **New document**, you can view all the templates that are owned by current and other providers.</span></span> <span data-ttu-id="6da61-133">Miután kiválasztja a sablont, szerkesztésre megnyílik.</span><span class="sxs-lookup"><span data-stu-id="6da61-133">After you select the template, it's opened for editing.</span></span> <span data-ttu-id="6da61-134">Ezt követően a szerkesztett sablon egy új, automatikusan létrejövő ER formátumkonfigurációban lesz tárolva.</span><span class="sxs-lookup"><span data-stu-id="6da61-134">The edited template will then be stored in a new ER format configuration that is automatically generated.</span></span>

<span data-ttu-id="6da61-135">További tájékoztatás: [Üzleti dokumentumkezelés – áttekintés](er-business-document-management.md).</span><span class="sxs-lookup"><span data-stu-id="6da61-135">For more information, see [Business document management overview](er-business-document-management.md).</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]