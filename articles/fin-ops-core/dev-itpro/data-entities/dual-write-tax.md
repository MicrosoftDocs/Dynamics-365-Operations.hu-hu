---
title: Integrált adó
description: Ez a témakör az adóadatok Finance and Operations és Common Data Service közötti integrációját ismerteti.
author: robinarh
manager: AnnBe
ms.date: 09/06/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ''
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: b6be53e9a2065373ca37c2791568a8161823803f
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/06/2019
ms.locfileid: "2772410"
---
## <a name="integrated-tax"></a><span data-ttu-id="2538f-103">Integrált adó</span><span class="sxs-lookup"><span data-stu-id="2538f-103">Integrated tax</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2538f-104">Az adóadatok beállítása határozza meg mind a közvetett adók (áfa, GST), mind az adóelőleg beállításait.</span><span class="sxs-lookup"><span data-stu-id="2538f-104">Tax setup data defines the setup for both indirect taxes (VAT, GST, Sales tax) and withholding tax.</span></span> <span data-ttu-id="2538f-105">Leírja az adószámítási szabályt, az adókulcsot, az adókönyvelés és az elszámolás részleteit, illetve további fogalmakat.</span><span class="sxs-lookup"><span data-stu-id="2538f-105">It describes the tax calculation rule, tax rate, tax accounting, settlement, and other concepts.</span></span>

## <a name="templates"></a><span data-ttu-id="2538f-106">Sablonok</span><span class="sxs-lookup"><span data-stu-id="2538f-106">Templates</span></span>

<span data-ttu-id="2538f-107">Az adóadatok tartalmazzák azokat az entitásleképezéseket, amelyek – az alábbi táblázatban látható módon – együttműködnek az adatok interakciója során.</span><span class="sxs-lookup"><span data-stu-id="2538f-107">Tax data includes a collection of entity maps that work together during data interaction, as shown in the following table.</span></span>

<span data-ttu-id="2538f-108">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="2538f-108">Finance and Operations</span></span>   | <span data-ttu-id="2538f-109">Customer Engagement alkalmazás</span><span class="sxs-lookup"><span data-stu-id="2538f-109">Customer Engagement application</span></span>
-------------------------|---------------------------------
<span data-ttu-id="2538f-110">Adókódok</span><span class="sxs-lookup"><span data-stu-id="2538f-110">Tax codes</span></span>                  | <span data-ttu-id="2538f-111">msdyn\_taxcodes.md</span><span class="sxs-lookup"><span data-stu-id="2538f-111">msdyn\_taxcodes.md</span></span>
<span data-ttu-id="2538f-112">Adócsoportok</span><span class="sxs-lookup"><span data-stu-id="2538f-112">Tax groups</span></span>               | <span data-ttu-id="2538f-113">msdyn\_taxgroups.md</span><span class="sxs-lookup"><span data-stu-id="2538f-113">msdyn\_taxgroups.md</span></span>
<span data-ttu-id="2538f-114">Adócikkcsoportok</span><span class="sxs-lookup"><span data-stu-id="2538f-114">Tax item groups</span></span>          | <span data-ttu-id="2538f-115">msdyn\_taxitemgroups.md</span><span class="sxs-lookup"><span data-stu-id="2538f-115">msdyn\_taxitemgroups.md</span></span>
<span data-ttu-id="2538f-116">Adómentességek</span><span class="sxs-lookup"><span data-stu-id="2538f-116">Tax Exemptions</span></span>           | <span data-ttu-id="2538f-117">msdyn\_taxexemptcodes.md</span><span class="sxs-lookup"><span data-stu-id="2538f-117">msdyn\_taxexemptcodes.md</span></span>
<span data-ttu-id="2538f-118">Adóhatóságok</span><span class="sxs-lookup"><span data-stu-id="2538f-118">Tax Authorities</span></span>          | <span data-ttu-id="2538f-119">msdyn\_taxauthorities.md</span><span class="sxs-lookup"><span data-stu-id="2538f-119">msdyn\_taxauthorities.md</span></span>
<span data-ttu-id="2538f-120">Adóelőlegkódok</span><span class="sxs-lookup"><span data-stu-id="2538f-120">Withholding tax codes</span></span>      | <span data-ttu-id="2538f-121">msdyn\_withholdingtaxcodes.md</span><span class="sxs-lookup"><span data-stu-id="2538f-121">msdyn\_withholdingtaxcodes.md</span></span>
<span data-ttu-id="2538f-122">Adóelőleg-csoportok</span><span class="sxs-lookup"><span data-stu-id="2538f-122">Withholding tax groups</span></span>   | <span data-ttu-id="2538f-123">msdyn\_withholdingtaxgroups.md</span><span class="sxs-lookup"><span data-stu-id="2538f-123">msdyn\_withholdingtaxgroups.md</span></span>
<span data-ttu-id="2538f-124">Adó főkönyviszámla-csoportja</span><span class="sxs-lookup"><span data-stu-id="2538f-124">Tax Ledger Account Group</span></span> | <span data-ttu-id="2538f-125">msdyn\_taxpostinggroups</span><span class="sxs-lookup"><span data-stu-id="2538f-125">msdyn\_taxpostinggroups</span></span>  

[!include [banner](../includes/dual-write-symbols.md)]

[!include [Tax groups](dual-write/TaxGroupEntity-msdyn-taxgroups.md)]

[!include [Tax item groups](dual-write/TaxItemGroupHeadings-msdyn-taxitemgroups.md)]

[!include [Tax Exemptions](dual-write/CdsTaxExemptCodes-msdyn-taxexemptcodes.md)]

[!include [Tax Authorities](dual-write/SalesTaxAuthorities-msdyn-taxauthorities.md)]

[!include [Withholding tax codes](dual-write/WithholdingCode-msdyn-withholdingtaxcodes.md)]

[!include [Withholding tax groups](dual-write/WithholdingGroups-msdyn-withholdingtaxgroups.md)]

[!include [Tax Ledger Account Group](dual-write/TaxPostingGroupsV2--msdyn-taxpostinggroups.md)]

