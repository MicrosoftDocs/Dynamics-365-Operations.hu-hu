---
title: Integrált adó
description: Ez a témakör az adóügyi adatok integrációját ismerteti a Finance and Operations és a Common Data Service között.
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
ms.openlocfilehash: 0d32a5f7859f0200da823a73d94b9a6b2a9c8e7d
ms.sourcegitcommit: 54baab2a04e5c534fc2d1fd67b67e23a152d4e57
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/04/2020
ms.locfileid: "3019816"
---
# <a name="integrated-tax"></a><span data-ttu-id="be5f0-103">Integrált adó</span><span class="sxs-lookup"><span data-stu-id="be5f0-103">Integrated tax</span></span>

[!include [banner](../../includes/banner.md)]

[!include [preview-banner](../../includes/preview-banner.md)]

<span data-ttu-id="be5f0-104">Az adóadatok beállítása határozza meg mind a közvetett adók (áfa, GST), mind az adóelőleg beállításait.</span><span class="sxs-lookup"><span data-stu-id="be5f0-104">Tax setup data defines the setup for both indirect taxes (VAT, GST, Sales tax) and withholding tax.</span></span> <span data-ttu-id="be5f0-105">Leírja az adószámítási szabályt, az adókulcsot, az adókönyvelés és az elszámolás részleteit, illetve további fogalmakat.</span><span class="sxs-lookup"><span data-stu-id="be5f0-105">It describes the tax calculation rule, tax rate, tax accounting, settlement, and other concepts.</span></span>

## <a name="templates"></a><span data-ttu-id="be5f0-106">Sablonok</span><span class="sxs-lookup"><span data-stu-id="be5f0-106">Templates</span></span>

<span data-ttu-id="be5f0-107">Az adóadatok tartalmazzák azokat az entitásleképezéseket, amelyek – az alábbi táblázatban látható módon – együttműködnek az adatok interakciója során.</span><span class="sxs-lookup"><span data-stu-id="be5f0-107">Tax data includes a collection of entity maps that work together during data interaction, as shown in the following table.</span></span>

<span data-ttu-id="be5f0-108">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="be5f0-108">Finance and Operations</span></span>   | <span data-ttu-id="be5f0-109">Egyéb Dynamics 365 alkalmazások</span><span class="sxs-lookup"><span data-stu-id="be5f0-109">Other Dynamics 365 apps</span></span>
-------------------------|---------------------------------
<span data-ttu-id="be5f0-110">Adókódok</span><span class="sxs-lookup"><span data-stu-id="be5f0-110">Tax codes</span></span>                  | <span data-ttu-id="be5f0-111">msdyn\_taxcodes.md</span><span class="sxs-lookup"><span data-stu-id="be5f0-111">msdyn\_taxcodes.md</span></span>
<span data-ttu-id="be5f0-112">Adócsoportok</span><span class="sxs-lookup"><span data-stu-id="be5f0-112">Tax groups</span></span>               | <span data-ttu-id="be5f0-113">msdyn\_taxgroups.md</span><span class="sxs-lookup"><span data-stu-id="be5f0-113">msdyn\_taxgroups.md</span></span>
<span data-ttu-id="be5f0-114">Adócikkcsoportok</span><span class="sxs-lookup"><span data-stu-id="be5f0-114">Tax item groups</span></span>          | <span data-ttu-id="be5f0-115">msdyn\_taxitemgroups.md</span><span class="sxs-lookup"><span data-stu-id="be5f0-115">msdyn\_taxitemgroups.md</span></span>
<span data-ttu-id="be5f0-116">Adómentességek</span><span class="sxs-lookup"><span data-stu-id="be5f0-116">Tax Exemptions</span></span>           | <span data-ttu-id="be5f0-117">msdyn\_taxexemptcodes.md</span><span class="sxs-lookup"><span data-stu-id="be5f0-117">msdyn\_taxexemptcodes.md</span></span>
<span data-ttu-id="be5f0-118">Adóhatóságok</span><span class="sxs-lookup"><span data-stu-id="be5f0-118">Tax Authorities</span></span>          | <span data-ttu-id="be5f0-119">msdyn\_taxauthorities.md</span><span class="sxs-lookup"><span data-stu-id="be5f0-119">msdyn\_taxauthorities.md</span></span>
<span data-ttu-id="be5f0-120">Adóelőlegkódok</span><span class="sxs-lookup"><span data-stu-id="be5f0-120">Withholding tax codes</span></span>      | <span data-ttu-id="be5f0-121">msdyn\_withholdingtaxcodes.md</span><span class="sxs-lookup"><span data-stu-id="be5f0-121">msdyn\_withholdingtaxcodes.md</span></span>
<span data-ttu-id="be5f0-122">Adóelőleg-csoportok</span><span class="sxs-lookup"><span data-stu-id="be5f0-122">Withholding tax groups</span></span>   | <span data-ttu-id="be5f0-123">msdyn\_withholdingtaxgroups.md</span><span class="sxs-lookup"><span data-stu-id="be5f0-123">msdyn\_withholdingtaxgroups.md</span></span>
<span data-ttu-id="be5f0-124">Adó főkönyviszámla-csoportja</span><span class="sxs-lookup"><span data-stu-id="be5f0-124">Tax Ledger Account Group</span></span> | <span data-ttu-id="be5f0-125">msdyn\_taxpostinggroups</span><span class="sxs-lookup"><span data-stu-id="be5f0-125">msdyn\_taxpostinggroups</span></span>  

[!include [banner](../../includes/dual-write-symbols.md)]

[!include [Tax groups](includes/TaxGroupEntity-msdyn-taxgroups.md)]

[!include [Tax item groups](includes/TaxItemGroupHeadings-msdyn-taxitemgroups.md)]

[!include [Tax Exemptions](includes/CdsTaxExemptCodes-msdyn-taxexemptcodes.md)]

[!include [Tax Authorities](includes/SalesTaxAuthorities-msdyn-taxauthorities.md)]

[!include [Withholding tax codes](includes/WithholdingCode-msdyn-withholdingtaxcodes.md)]

[!include [Withholding tax groups](includes/WithholdingGroups-msdyn-withholdingtaxgroups.md)]

[!include [Tax Ledger Account Group](includes/TaxPostingGroupsV2--msdyn-taxpostinggroups.md)]

