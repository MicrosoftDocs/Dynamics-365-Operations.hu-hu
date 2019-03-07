---
title: Fő számla kategóriáinak beállítása
description: A Főszámla-kategóriák használhatók a pénzügyi jelentések alapértelmezett jelentéseihez és a Power BI szolgáltatásban.
author: aprilolson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: MainAccountCategory, MainAccountCategoryLink
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e46c7c86b93a3471ba10ec7ae6789f227bc9779c
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2019
ms.locfileid: "311450"
---
# <a name="set-up-main-account-categories"></a><span data-ttu-id="0cbb4-103">Fő számla kategóriáinak beállítása</span><span class="sxs-lookup"><span data-stu-id="0cbb4-103">Set up main account categories</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="0cbb4-104">A Főszámla-kategóriák használhatók a pénzügyi jelentések alapértelmezett jelentéseihez és a Power BI szolgáltatásban.</span><span class="sxs-lookup"><span data-stu-id="0cbb4-104">Main account categories are used for the default reports in financial reporting and in Power BI.</span></span> <span data-ttu-id="0cbb4-105">Az alapértelmezés szerint létrejött Főszámla-kategóriákat át lehet nevezni, de nem lehet törölni.</span><span class="sxs-lookup"><span data-stu-id="0cbb4-105">Main account categories that are created by default can be renamed but not deleted.</span></span> <span data-ttu-id="0cbb4-106">További főkönyviszámla-kategóriákat hozhat létre, majd használhatja azokat jelentéshez és elemzéshez.</span><span class="sxs-lookup"><span data-stu-id="0cbb4-106">Additional account categories can be created and used for reporting and analysis purposes.</span></span> <span data-ttu-id="0cbb4-107">Ez a feladat az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="0cbb4-107">This task uses the USMF demo company.</span></span>


## <a name="create-a-main-account-category"></a><span data-ttu-id="0cbb4-108">Főszámla-kategória létrehozása</span><span class="sxs-lookup"><span data-stu-id="0cbb4-108">Create a main account category</span></span>
1. <span data-ttu-id="0cbb4-109">Ugrás a következő útvonalra: Főkönyv > Számlatükör > Számlák > Főszámla-kategóriák.</span><span class="sxs-lookup"><span data-stu-id="0cbb4-109">Go to General ledger > Chart of accounts > Accounts > Main account categories.</span></span>
2. <span data-ttu-id="0cbb4-110">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="0cbb4-110">Click New.</span></span>
3. <span data-ttu-id="0cbb4-111">A főszámla-kategória mezőben adjon meg egy egyedi nevet.</span><span class="sxs-lookup"><span data-stu-id="0cbb4-111">In the Main account category field, enter a unique name.</span></span>
4. <span data-ttu-id="0cbb4-112">A Leírás mezőben adja meg a főszámla-kategória leírását.</span><span class="sxs-lookup"><span data-stu-id="0cbb4-112">In the Description field, enter a description for the main account category.</span></span>
5. <span data-ttu-id="0cbb4-113">A Fő számla típusa mezőben válassza ki azt a főszámlatípust, amelyet össze kíván kapcsolni a kategóriával.</span><span class="sxs-lookup"><span data-stu-id="0cbb4-113">In the Main account type field, select the main account type that will be linked to the category.</span></span>

## <a name="link-main-accounts-to-account-category"></a><span data-ttu-id="0cbb4-114">Fő számlák csatolása számlakategóriához</span><span class="sxs-lookup"><span data-stu-id="0cbb4-114">Link main accounts to account category</span></span>
1. <span data-ttu-id="0cbb4-115">Kattintson a Fő számlák összekapcsolása elemre.</span><span class="sxs-lookup"><span data-stu-id="0cbb4-115">Click Link main accounts.</span></span>
2. <span data-ttu-id="0cbb4-116">A listában válassza ki azokat a fő számlákat, amelyeket hozzákapcsolna a kijelölt főszámla-kategóriához.</span><span class="sxs-lookup"><span data-stu-id="0cbb4-116">In the list, select the main accounts to assign to the main account category.</span></span>
    * <span data-ttu-id="0cbb4-117">Ha a fú számlákat hozzárendeli a fő számla kategóriájához, azzal összesíti a számlák egyenlegét, amikor a kategóriát pénzügyi jelentéshez és elemzéshez használja.</span><span class="sxs-lookup"><span data-stu-id="0cbb4-117">Assigning main accounts to a main account category will aggregate the balances of the accounts when that category is used for financial reporting and analysis.</span></span>  
3. <span data-ttu-id="0cbb4-118">Jelölje be, vagy törölje a jelölést az Összekapcsolt elem mellett a fő számlák kiválasztásához.</span><span class="sxs-lookup"><span data-stu-id="0cbb4-118">Select or clear the Linked option to choose the main accounts.</span></span>
4. <span data-ttu-id="0cbb4-119">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="0cbb4-119">Click OK.</span></span>
5. <span data-ttu-id="0cbb4-120">Kattintson az Igen gombra.</span><span class="sxs-lookup"><span data-stu-id="0cbb4-120">Click Yes.</span></span>

