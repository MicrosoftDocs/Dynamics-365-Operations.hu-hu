---
title: Juttatásra való jogosultsági irányelvek
description: Ez a cikk információt biztosít a juttatás alkalmassági irányelveit illetően, így segítve önt a különleges juttatásokra jogosult személyek meghatározásában.
author: andreabichsel
manager: tfehr
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
ms.search.form: HcmBenefitEligibilityDetail, SysPolicyListPage, SysPolicySourceDocumentRuleType, BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 16441
ms.assetid: 4ad0106f-5b07-4fd5-bc1a-5834fa9b198e
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: e0c0aa7eebf32fc404e0519c6068b4427e6b87b2
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/17/2021
ms.locfileid: "5465150"
---
# <a name="benefit-eligibility-policies"></a><span data-ttu-id="1a274-103">Juttatásra vonatkozó jogosultsági irányelvek</span><span class="sxs-lookup"><span data-stu-id="1a274-103">Benefit eligibility policies</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="1a274-104">Ez a cikk információt biztosít a juttatás alkalmassági irányelveit illetően, így segítve önt a különleges juttatásokra jogosult személyek meghatározásában.</span><span class="sxs-lookup"><span data-stu-id="1a274-104">This article provides information about benefit eligibility policies, which help you define who is eligible for specific benefits.</span></span>

<span data-ttu-id="1a274-105">Juttatások létrehozásakor eldöntheti, mely juttatások mely alkalmazottak számára lesz elérhető.</span><span class="sxs-lookup"><span data-stu-id="1a274-105">When you create benefits, you decide which benefits will be available to which employees.</span></span> <span data-ttu-id="1a274-106">Az alábbi táblázat példákat mutat juttatásokra, amelyeket elérhetővé tehet bizonyos alkalmazottaknak.</span><span class="sxs-lookup"><span data-stu-id="1a274-106">The following table shows examples of benefits that you might make available to specific employees.</span></span>

| <span data-ttu-id="1a274-107">Juttatás</span><span class="sxs-lookup"><span data-stu-id="1a274-107">Benefit</span></span>          | <span data-ttu-id="1a274-108">Akiknek elérhető a juttatás</span><span class="sxs-lookup"><span data-stu-id="1a274-108">Who the benefit is available to</span></span> |
|------------------|---------------------------------|
| <span data-ttu-id="1a274-109">Egészségbiztosítás</span><span class="sxs-lookup"><span data-stu-id="1a274-109">Health insurance</span></span> | <span data-ttu-id="1a274-110">Minden alkalmazott</span><span class="sxs-lookup"><span data-stu-id="1a274-110">All employees</span></span>                   |
| <span data-ttu-id="1a274-111">Mobiltelefon</span><span class="sxs-lookup"><span data-stu-id="1a274-111">Mobile phone</span></span>     | <span data-ttu-id="1a274-112">Értékesítési munkatársak, vezetők</span><span class="sxs-lookup"><span data-stu-id="1a274-112">Sales staff, executives</span></span>         |
| <span data-ttu-id="1a274-113">Parkolási engedélyek</span><span class="sxs-lookup"><span data-stu-id="1a274-113">Parking passes</span></span>   | <span data-ttu-id="1a274-114">Ügyintézők</span><span class="sxs-lookup"><span data-stu-id="1a274-114">Executives</span></span>                      |

<span data-ttu-id="1a274-115">A következő elemek használhatóak jogosultsági irányelvek létrehozására:</span><span class="sxs-lookup"><span data-stu-id="1a274-115">The following components in are used to create eligibility policies:</span></span>

-   <span data-ttu-id="1a274-116">Irányelvszabály típusai</span><span class="sxs-lookup"><span data-stu-id="1a274-116">Policy rule types</span></span>
-   <span data-ttu-id="1a274-117">Juttatásra való jogosultsági irányelvek</span><span class="sxs-lookup"><span data-stu-id="1a274-117">Benefit eligibility policies</span></span>

<span data-ttu-id="1a274-118">Az irányelvszabályok típusai definiálják az egyes irányelvszabályok kialakításakor használt lekérdezésparamétereket.</span><span class="sxs-lookup"><span data-stu-id="1a274-118">Policy rule types define the query parameters that are used when you develop specific policy rules.</span></span> <span data-ttu-id="1a274-119">Miután létrehozta az irányelvszabály-típusokat, juttatásra való jogosultsági irányelveket is létrehozhat.</span><span class="sxs-lookup"><span data-stu-id="1a274-119">After you create policy rule types, you can create benefit eligibility policies.</span></span> <span data-ttu-id="1a274-120">Az irányelvek lehetővé teszik szabálygyűjtemények létrehozását, amelyeket egy vagy több jogi személyre alkalmazhat.</span><span class="sxs-lookup"><span data-stu-id="1a274-120">The policies let you create a collection of rules that apply to one or more legal entities.</span></span> <span data-ttu-id="1a274-121">Minden irányelvben megnézheti a korábban létrehozott juttatásra való jogosultsági irányelvszabály-típusokat.</span><span class="sxs-lookup"><span data-stu-id="1a274-121">Within each policy, you can view any of the benefit eligibility policy rule types that you created earlier.</span></span> 

<span data-ttu-id="1a274-122">A szabály hatáskörét az irányelven belül lehet megadni.</span><span class="sxs-lookup"><span data-stu-id="1a274-122">You define the scope of the rule within the policy.</span></span> <span data-ttu-id="1a274-123">Például ha **Vezető** nevű juttatásra való jogosultsági irányelvszabály-típust hoz létre, megadhatjami a szabály az irányelven belül.</span><span class="sxs-lookup"><span data-stu-id="1a274-123">For example, if you create a benefit eligibility policy rule type that is named **Executive**, you can specify what the rule is within that policy.</span></span> <span data-ttu-id="1a274-124">Ebben a példában minden olyan beosztásra vonatkozik a szabály, amelyben szerepel a „vezető” szó.</span><span class="sxs-lookup"><span data-stu-id="1a274-124">In this example, the rule might state that any job title that contains the word "executive" should be included in the rule.</span></span> <span data-ttu-id="1a274-125">Miután megadta az irányelvben foglalt szabály, vagy szabályok paramétereit, hozzárendelhet egy specifikus szabályt a juttatáshoz.</span><span class="sxs-lookup"><span data-stu-id="1a274-125">After you've defined the parameters of the rule or rules that are included in the policy, you can assign a specific rule to the benefit.</span></span>






[!INCLUDE[footer-include](../includes/footer-banner.md)]