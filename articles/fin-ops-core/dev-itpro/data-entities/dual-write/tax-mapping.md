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
ms.openlocfilehash: a4da37d45698290b40f6c72148f1500bef72127a
ms.sourcegitcommit: 68f1485de7d64a6c9eba1088af63bd07992d972d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/27/2020
ms.locfileid: "3173085"
---
# <a name="integrated-tax"></a><span data-ttu-id="d7ef0-103">Integrált adó</span><span class="sxs-lookup"><span data-stu-id="d7ef0-103">Integrated tax</span></span>

[!include [banner](../../includes/banner.md)]



<span data-ttu-id="d7ef0-104">Az adóadatok beállítása határozza meg mind a közvetett adók (áfa, GST), mind az adóelőleg beállításait.</span><span class="sxs-lookup"><span data-stu-id="d7ef0-104">Tax setup data defines the setup for both indirect taxes (VAT, GST, Sales tax) and withholding tax.</span></span> <span data-ttu-id="d7ef0-105">Leírja az adószámítási szabályt, az adókulcsot, az adókönyvelés és az elszámolás részleteit, illetve további fogalmakat.</span><span class="sxs-lookup"><span data-stu-id="d7ef0-105">It describes the tax calculation rule, tax rate, tax accounting, settlement, and other concepts.</span></span>

## <a name="templates"></a><span data-ttu-id="d7ef0-106">Sablonok</span><span class="sxs-lookup"><span data-stu-id="d7ef0-106">Templates</span></span>

<span data-ttu-id="d7ef0-107">Az adóadatok tartalmazzák azokat az entitásleképezéseket, amelyek – az alábbi táblázatban látható módon – együttműködnek az adatok interakciója során.</span><span class="sxs-lookup"><span data-stu-id="d7ef0-107">Tax data includes a collection of entity maps that work together during data interaction, as shown in the following table.</span></span>

| <span data-ttu-id="d7ef0-108">Finance and Operations-alkalmazásoknak</span><span class="sxs-lookup"><span data-stu-id="d7ef0-108">Finance and Operations apps</span></span> | <span data-ttu-id="d7ef0-109">Modellvezérelt alkalmazások a Dynamics 365-ben</span><span class="sxs-lookup"><span data-stu-id="d7ef0-109">Model-driven apps in Dynamics 365</span></span> | <span data-ttu-id="d7ef0-110">Leírás</span><span class="sxs-lookup"><span data-stu-id="d7ef0-110">Description</span></span> |
-------------------------|---------------------------------
<span data-ttu-id="d7ef0-111">Adókódok</span><span class="sxs-lookup"><span data-stu-id="d7ef0-111">Tax codes</span></span>                   | <span data-ttu-id="d7ef0-112">msdyn\_taxcodes.md</span><span class="sxs-lookup"><span data-stu-id="d7ef0-112">msdyn\_taxcodes.md</span></span> | 
<span data-ttu-id="d7ef0-113">Adócsoportok</span><span class="sxs-lookup"><span data-stu-id="d7ef0-113">Tax groups</span></span>                 | <span data-ttu-id="d7ef0-114">msdyn\_taxgroups.md</span><span class="sxs-lookup"><span data-stu-id="d7ef0-114">msdyn\_taxgroups.md</span></span> | 
<span data-ttu-id="d7ef0-115">Adócikkcsoportok</span><span class="sxs-lookup"><span data-stu-id="d7ef0-115">Tax item groups</span></span>             | <span data-ttu-id="d7ef0-116">msdyn\_taxitemgroups.md</span><span class="sxs-lookup"><span data-stu-id="d7ef0-116">msdyn\_taxitemgroups.md</span></span> | 
<span data-ttu-id="d7ef0-117">Adómentességek</span><span class="sxs-lookup"><span data-stu-id="d7ef0-117">Tax Exemptions</span></span>             | <span data-ttu-id="d7ef0-118">msdyn\_taxexemptcodes.md</span><span class="sxs-lookup"><span data-stu-id="d7ef0-118">msdyn\_taxexemptcodes.md</span></span> | 
<span data-ttu-id="d7ef0-119">Adóhatóságok</span><span class="sxs-lookup"><span data-stu-id="d7ef0-119">Tax Authorities</span></span>             | <span data-ttu-id="d7ef0-120">msdyn\_taxauthorities.md</span><span class="sxs-lookup"><span data-stu-id="d7ef0-120">msdyn\_taxauthorities.md</span></span> | 
<span data-ttu-id="d7ef0-121">Adóelőlegkódok</span><span class="sxs-lookup"><span data-stu-id="d7ef0-121">Withholding tax codes</span></span>       | <span data-ttu-id="d7ef0-122">msdyn\_withholdingtaxcodes.md</span><span class="sxs-lookup"><span data-stu-id="d7ef0-122">msdyn\_withholdingtaxcodes.md</span></span> | 
<span data-ttu-id="d7ef0-123">Adóelőleg-csoportok</span><span class="sxs-lookup"><span data-stu-id="d7ef0-123">Withholding tax groups</span></span>     | <span data-ttu-id="d7ef0-124">msdyn\_withholdingtaxgroups.md</span><span class="sxs-lookup"><span data-stu-id="d7ef0-124">msdyn\_withholdingtaxgroups.md</span></span> | 
<span data-ttu-id="d7ef0-125">Adó főkönyviszámla-csoportja</span><span class="sxs-lookup"><span data-stu-id="d7ef0-125">Tax Ledger Account Group</span></span> | <span data-ttu-id="d7ef0-126">msdyn\_taxpostinggroups</span><span class="sxs-lookup"><span data-stu-id="d7ef0-126">msdyn\_taxpostinggroups</span></span>     | 

[!include [banner](../../includes/dual-write-symbols.md)]

[!include [Tax groups](includes/TaxGroupEntity-msdyn-taxgroups.md)]

[!include [Tax item groups](includes/TaxItemGroupHeadings-msdyn-taxitemgroups.md)]

[!include [Tax Exemptions](includes/CdsTaxExemptCodes-msdyn-taxexemptcodes.md)]

[!include [Tax Authorities](includes/SalesTaxAuthorities-msdyn-taxauthorities.md)]

[!include [Withholding tax codes](includes/WithholdingCode-msdyn-withholdingtaxcodes.md)]

[!include [Withholding tax groups](includes/WithholdingGroups-msdyn-withholdingtaxgroups.md)]

[!include [Tax Ledger Account Group](includes/TaxPostingGroupsV2--msdyn-taxpostinggroups.md)]

