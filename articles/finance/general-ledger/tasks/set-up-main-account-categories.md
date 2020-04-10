---
title: Fő számla kategóriáinak beállítása
description: Ez a témakör bemutatja, hogyan állítsa be a főszámla-kategóriákat a Dynamics 365 Finance szolgáltatásban.
author: aprilolson
manager: AnnBe
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: MainAccountCategory, MainAccountCategoryLink
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9e0a015283064af2287013bccc065b4467a308c5
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/18/2020
ms.locfileid: "3144789"
---
# <a name="set-up-main-account-categories"></a><span data-ttu-id="54f66-103">Fő számla kategóriáinak beállítása</span><span class="sxs-lookup"><span data-stu-id="54f66-103">Set up main account categories</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="54f66-104">Ez a témakör bemutatja, hogyan állítsa be a főszámla-kategóriákat.</span><span class="sxs-lookup"><span data-stu-id="54f66-104">This topic explains how to set up main account categories.</span></span> <span data-ttu-id="54f66-105">A Főszámla-kategóriák használhatók a pénzügyi jelentések alapértelmezett jelentéseihez és a Power BI szolgáltatásban.</span><span class="sxs-lookup"><span data-stu-id="54f66-105">Main account categories are used for the default reports in financial reporting and in Power BI.</span></span> <span data-ttu-id="54f66-106">Az alapértelmezés szerint létrejött Főszámla-kategóriákat át lehet nevezni, de nem lehet törölni.</span><span class="sxs-lookup"><span data-stu-id="54f66-106">Main account categories that are created by default can be renamed but not deleted.</span></span> <span data-ttu-id="54f66-107">További főkönyviszámla-kategóriákat hozhat létre, majd használhatja azokat jelentéshez és elemzéshez.</span><span class="sxs-lookup"><span data-stu-id="54f66-107">Additional account categories can be created and used for reporting and analysis purposes.</span></span> <span data-ttu-id="54f66-108">A témakörben az USMF bemutatóvállalat szerepel.</span><span class="sxs-lookup"><span data-stu-id="54f66-108">This topic uses the USMF demo company.</span></span>

## <a name="create-a-main-account-category"></a><span data-ttu-id="54f66-109">Főszámla-kategória létrehozása</span><span class="sxs-lookup"><span data-stu-id="54f66-109">Create a main account category</span></span>
1. <span data-ttu-id="54f66-110">Ugorjon a navigációs ablaktáblán a **Modulok > Főkönyv > Számlatükör > Számlák > Főszámla-kategóriák lehetőségre**.</span><span class="sxs-lookup"><span data-stu-id="54f66-110">In the navigation pane, go to **Modules > General Ledger > Chart of accounts > Accounts > Main account categories**.</span></span>
2. <span data-ttu-id="54f66-111">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="54f66-111">Select **New**.</span></span>
3. <span data-ttu-id="54f66-112">A **Főszámla-kategória** mezőben adjon meg egy egyedi nevet.</span><span class="sxs-lookup"><span data-stu-id="54f66-112">In the **Main account category** field, enter a unique name.</span></span>
4. <span data-ttu-id="54f66-113">A **Leírás mezőben** adja meg a főszámla-kategória leírását.</span><span class="sxs-lookup"><span data-stu-id="54f66-113">In the **Description field**, enter a description for the main account category.</span></span>
5. <span data-ttu-id="54f66-114">A **Fő számla típusa** mezőben válassza ki azt a főszámlatípust, amelyet össze kíván kapcsolni a kategóriával.</span><span class="sxs-lookup"><span data-stu-id="54f66-114">In the **Main account type** field, select the main account type that will be linked to the category.</span></span>

## <a name="link-main-accounts-to-account-category"></a><span data-ttu-id="54f66-115">Fő számlák csatolása számlakategóriához</span><span class="sxs-lookup"><span data-stu-id="54f66-115">Link main accounts to account category</span></span>
1. <span data-ttu-id="54f66-116">Kattintson a **Fő számlák összekapcsolása** elemre.</span><span class="sxs-lookup"><span data-stu-id="54f66-116">Click **Link main accounts**.</span></span>
2. <span data-ttu-id="54f66-117">Az **Összekapcsolt** oszlopban található jelölőnégyzet bejelölésével válassza ki azokat a fő számlákat a listáról, amelyeket a főszámla-kategóriához kíván rendelni.</span><span class="sxs-lookup"><span data-stu-id="54f66-117">In the list, select the main accounts to assign to the main account category by checking the boxes in the **Linked** column.</span></span> <span data-ttu-id="54f66-118">Ha a fú számlákat hozzárendeli a fő számla kategóriájához, azzal összesíti a számlák egyenlegét, amikor a kategóriát pénzügyi jelentéshez és elemzéshez használja.</span><span class="sxs-lookup"><span data-stu-id="54f66-118">Assigning main accounts to a main account category will aggregate the balances of the accounts when that category is used for financial reporting and analysis.</span></span>  
3. <span data-ttu-id="54f66-119">A fő számlák kiválasztásához jelölje be, vagy törölje a jelölést az **Összekapcsolt** elemnél.</span><span class="sxs-lookup"><span data-stu-id="54f66-119">Select or clear the **Linked** option to choose the main accounts.</span></span>
4. <span data-ttu-id="54f66-120">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="54f66-120">Select **OK**.</span></span>
5. <span data-ttu-id="54f66-121">Válassza ki az **Igen** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="54f66-121">Select **Yes**.</span></span>
