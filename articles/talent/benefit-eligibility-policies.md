---
title: Juttatásra való jogosultsági irányelvek
description: Ez a cikk információt biztosít a juttatás alkalmassági irányelveit illetően, így segítve önt a különleges juttatásokra jogosult személyek meghatározásában.
author: andreabichsel
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: HcmBenefitEligibilityDetail, SysPolicyListPage, SysPolicySourceDocumentRuleType
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Talent
ms.custom: 16441
ms.assetid: 4ad0106f-5b07-4fd5-bc1a-5834fa9b198e
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Talent July 2017 update
ms.openlocfilehash: ad179e505d045dc40898105e1cfd090daafa09a8
ms.sourcegitcommit: 608e68b603afef9eb98d8fb25e90109c2473ef87
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/19/2019
ms.locfileid: "855962"
---
# <a name="benefit-eligibility-policies"></a><span data-ttu-id="28788-103">Juttatásra való jogosultsági irányelvek</span><span class="sxs-lookup"><span data-stu-id="28788-103">Benefit eligibility policies</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="28788-104">Ez a témakör információt biztosít a juttatás alkalmassági irányelveit illetően, így segítve Önt a különleges juttatásokra jogosult személyek meghatározásában.</span><span class="sxs-lookup"><span data-stu-id="28788-104">This topic provides information about benefit eligibility policies, which help you define who is eligible for specific benefits.</span></span>

<span data-ttu-id="28788-105">Juttatások létrehozásakor eldöntheti, mely juttatások mely alkalmazottak számára lesz elérhető.</span><span class="sxs-lookup"><span data-stu-id="28788-105">When you create benefits, you decide which benefits will be available to which employees.</span></span> <span data-ttu-id="28788-106">Az alábbi táblázat példákat mutat juttatásokra, amelyeket elérhetővé tehet bizonyos alkalmazottaknak.</span><span class="sxs-lookup"><span data-stu-id="28788-106">The following table shows examples of benefits that you might make available to specific employees.</span></span>

| <span data-ttu-id="28788-107">Juttatás</span><span class="sxs-lookup"><span data-stu-id="28788-107">Benefit</span></span>          | <span data-ttu-id="28788-108">Akiknek elérhető a juttatás</span><span class="sxs-lookup"><span data-stu-id="28788-108">Who the benefit is available to</span></span> |
|------------------|---------------------------------|
| <span data-ttu-id="28788-109">Egészségbiztosítás</span><span class="sxs-lookup"><span data-stu-id="28788-109">Health insurance</span></span> | <span data-ttu-id="28788-110">Minden alkalmazott</span><span class="sxs-lookup"><span data-stu-id="28788-110">All employees</span></span>                   |
| <span data-ttu-id="28788-111">Mobiltelefon</span><span class="sxs-lookup"><span data-stu-id="28788-111">Mobile phone</span></span>     | <span data-ttu-id="28788-112">Értékesítési munkatársak, vezetők</span><span class="sxs-lookup"><span data-stu-id="28788-112">Sales staff, executives</span></span>         |
| <span data-ttu-id="28788-113">Parkolási engedélyek</span><span class="sxs-lookup"><span data-stu-id="28788-113">Parking passes</span></span>   | <span data-ttu-id="28788-114">Ügyintézők</span><span class="sxs-lookup"><span data-stu-id="28788-114">Executives</span></span>                      |

<span data-ttu-id="28788-115">A következő elemek használhatóak jogosultsági irányelvek létrehozására:</span><span class="sxs-lookup"><span data-stu-id="28788-115">The following components in are used to create eligibility policies:</span></span>

-   <span data-ttu-id="28788-116">Irányelvszabály típusai</span><span class="sxs-lookup"><span data-stu-id="28788-116">Policy rule types</span></span>
-   <span data-ttu-id="28788-117">Juttatásra való jogosultsági irányelvek</span><span class="sxs-lookup"><span data-stu-id="28788-117">Benefit eligibility policies</span></span>

<span data-ttu-id="28788-118">Az irányelvszabályok típusai definiálják az egyes irányelvszabályok kialakításakor használt lekérdezésparamétereket.</span><span class="sxs-lookup"><span data-stu-id="28788-118">Policy rule types define the query parameters that are used when you develop specific policy rules.</span></span> <span data-ttu-id="28788-119">Miután létrehozta az irányelvszabály-típusokat, juttatásra való jogosultsági irányelveket is létrehozhat.</span><span class="sxs-lookup"><span data-stu-id="28788-119">After you create policy rule types, you can create benefit eligibility policies.</span></span> <span data-ttu-id="28788-120">Az irányelvek lehetővé teszik szabálygyűjtemények létrehozását, amelyeket egy vagy több jogi személyre alkalmazhat.</span><span class="sxs-lookup"><span data-stu-id="28788-120">The policies let you create a collection of rules that apply to one or more legal entities.</span></span> <span data-ttu-id="28788-121">Minden irányelvben megnézheti a korábban létrehozott juttatásra való jogosultsági irányelvszabály-típusokat.</span><span class="sxs-lookup"><span data-stu-id="28788-121">Within each policy, you can view any of the benefit eligibility policy rule types that you created earlier.</span></span> 

<span data-ttu-id="28788-122">A szabály hatáskörét az irányelven belül lehet megadni.</span><span class="sxs-lookup"><span data-stu-id="28788-122">You define the scope of the rule within the policy.</span></span> <span data-ttu-id="28788-123">Például ha **Vezető** nevű juttatásra való jogosultsági irányelvszabály-típust hoz létre, megadhatjami a szabály az irányelven belül.</span><span class="sxs-lookup"><span data-stu-id="28788-123">For example, if you create a benefit eligibility policy rule type that is named **Executive**, you can specify what the rule is within that policy.</span></span> <span data-ttu-id="28788-124">Ebben a példában minden olyan beosztásra vonatkozik a szabály, amelyben szerepel a „vezető” szó.</span><span class="sxs-lookup"><span data-stu-id="28788-124">In this example, the rule might state that any job title that contains the word “executive” should be included in the rule.</span></span> <span data-ttu-id="28788-125">Miután megadta az irányelvben foglalt szabály, vagy szabályok paramétereit, hozzárendelhet egy specifikus szabályt a juttatáshoz.</span><span class="sxs-lookup"><span data-stu-id="28788-125">After you've defined the parameters of the rule or rules that are included in the policy, you can assign a specific rule to the benefit.</span></span>

<a name="additional-resources"></a><span data-ttu-id="28788-126">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="28788-126">Additional resources</span></span>
--------

[<span data-ttu-id="28788-127">Juttatási program meghatározása és kezelése</span><span class="sxs-lookup"><span data-stu-id="28788-127">Defining and managing a benefit program</span></span>](manage-benefit-program.md)



