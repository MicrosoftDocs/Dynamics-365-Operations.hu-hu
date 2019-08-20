---
title: Költségvetés létrehozása tranzakciószámlákból vagy összegző számlákból
description: Ez a cikk betekintést nyújt az összegző számlákon alapuló költségvetés-létrehozás folyamatába. Azt is bemutatja, hogyan kapcsolja be a költségvetés-ellenőrzést az összegző számlák esetében, már amennyiben szükséges a költségvetés-ellenőrzés.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BudgetControlConfiguration, BudgetPlanGenerate
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 13051
ms.assetid: fb1bb2d3-445c-402f-a9a3-aa6503eed78e
ms.search.region: Global
ms.author: sigitac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f60963bee790737c85161dff03278df0572e3abc
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/01/2019
ms.locfileid: "1834028"
---
# <a name="create-a-budget-from-transaction-accounts-and-total-accounts"></a><span data-ttu-id="4afe1-104">Költségvetés létrehozása tranzakciószámlákból vagy összegző számlákból</span><span class="sxs-lookup"><span data-stu-id="4afe1-104">Create a budget from transaction accounts and total accounts</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4afe1-105">Ez a cikk betekintést nyújt az összegző számlákon alapuló költségvetés-létrehozás folyamatába.</span><span class="sxs-lookup"><span data-stu-id="4afe1-105">This article provides an overview of the process for creating budgets based on total accounts.</span></span> <span data-ttu-id="4afe1-106">Azt is bemutatja, hogyan kapcsolja be a költségvetés-ellenőrzést az összegző számlák esetében, már amennyiben szükséges a költségvetés-ellenőrzés.</span><span class="sxs-lookup"><span data-stu-id="4afe1-106">It also explains how to turn on budget control for total accounts, if budget control is required.</span></span>

<span data-ttu-id="4afe1-107">A költségvetési terv és a költségvetési tételjegyzék-bejegyzés dokumentumaival olyan fő számlákra készíthet költségvetést, melyek típusa **Összesen**.</span><span class="sxs-lookup"><span data-stu-id="4afe1-107">Both budget plan and budget register entry documents allow for budgeting on main accounts that have a main account type of **Total**.</span></span> <span data-ttu-id="4afe1-108">A tényadatok csak tranzakciós fő számlákra adhatóak fel.</span><span class="sxs-lookup"><span data-stu-id="4afe1-108">Actuals can be posted only to transactional main accounts.</span></span> 

<span data-ttu-id="4afe1-109">A **Költségvetési terv létrehozása a Főkönyv alapján** időszakos folyamatnál a **Forrás** lapon lehet feltételként beállítani az **Összesen** típusú fő számlákat.</span><span class="sxs-lookup"><span data-stu-id="4afe1-109">For the **Generate budget plan from General ledger** periodic process, on the **Source** tab, you can specify the **Total** main account type as a criterion.</span></span> <span data-ttu-id="4afe1-110">Ebben az esetben minden összesen típusú főszámla szerepelni fog a cél költségvetési tervben, és az összeg megegyezik a tartományban kiválasztott fő számlák teljes összegével.</span><span class="sxs-lookup"><span data-stu-id="4afe1-110">In this case, each total main account will be included in the target budget plan, and the amount will equal the total amount of the range of selected main accounts.</span></span> 

<span data-ttu-id="4afe1-111">Költségvetés-ellenőrzést is aktiválhat az **Összesen** típusú fő számlákra.</span><span class="sxs-lookup"><span data-stu-id="4afe1-111">You can activate budget control for main accounts of the **Total** type.</span></span> <span data-ttu-id="4afe1-112">Ezt a funkciót a költségvetési csoportok használata támogatja.</span><span class="sxs-lookup"><span data-stu-id="4afe1-112">This functionality is supported through the use of budget groups.</span></span> <span data-ttu-id="4afe1-113">Minden összesen típusú fő számlánál egy költségvetési csoportnak kell vezérelnie a költségvetést, amelyet a **Költségvetés-ellenőrzési konfiguráció** oldalon lehet létrehozni.</span><span class="sxs-lookup"><span data-stu-id="4afe1-113">For each total main account, the budget that should be controlled for a budget group must be created on the \*\*Budget control configuration \*\*page.</span></span> <span data-ttu-id="4afe1-114">A kritériumok között meg kell adni az összesen típusú főszámlát és a számlatartományt.</span><span class="sxs-lookup"><span data-stu-id="4afe1-114">The criteria that you specify must include the total main account and the range of accounts.</span></span> <span data-ttu-id="4afe1-115">A költségvetési csoportok létrehozásának folyamata felgyorsítható a költségvetés-ellenőrzési csoportok adatentitásaival.</span><span class="sxs-lookup"><span data-stu-id="4afe1-115">To speed up the process of creating budget groups, you can take advantage of the Budget control groups data entity.</span></span> 

<span data-ttu-id="4afe1-116">Ha költségvetést használ jelentéseknél, például pénzügyi kimutatásokban, akkor az összegző számla költségvetési összege az alábbi összegekből áll:</span><span class="sxs-lookup"><span data-stu-id="4afe1-116">When a budget is used in reporting, such as on a financial statement, the budget sum for the total account consists of the following amounts:</span></span>

-   <span data-ttu-id="4afe1-117">Az összegző számla intervallumán belül az egyes főkönyvi tranzakciószámlákon elkönyvelt költségvetések.</span><span class="sxs-lookup"><span data-stu-id="4afe1-117">The budgets that are created from each transaction ledger account in the interval of the total account.</span></span>
-   <span data-ttu-id="4afe1-118">A közvetlenül az összegző számlán elkönyvelt költségvetési összeg.</span><span class="sxs-lookup"><span data-stu-id="4afe1-118">The budget amount that is entered directly on the total account.</span></span>

<span data-ttu-id="4afe1-119">Így lehet külön költségvetéseket létrehozni az összegző számla intervallumának legfontosabb tranzakciószámláihoz és hozzáadni a fennmaradó költségvetési összeget az összegző számlához.</span><span class="sxs-lookup"><span data-stu-id="4afe1-119">Therefore, you can create separate budgets for the most significant transaction accounts in the interval of the total account, and then add the available budget amount to the total account.</span></span>



