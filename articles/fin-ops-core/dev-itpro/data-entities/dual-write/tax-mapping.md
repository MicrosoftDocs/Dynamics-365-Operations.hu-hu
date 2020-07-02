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
ms.openlocfilehash: 69521ec8c664a7025050c94105eca58f7f2c5c00
ms.sourcegitcommit: 7d943499f302298c6ff127f56cecc34af6cee289
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/08/2020
ms.locfileid: "3435560"
---
# <a name="integrated-tax"></a><span data-ttu-id="14047-103">Integrált adó</span><span class="sxs-lookup"><span data-stu-id="14047-103">Integrated tax</span></span>

[!include [banner](../../includes/banner.md)]



<span data-ttu-id="14047-104">Az adóadatok beállítása határozza meg mind a közvetett adók (áfa, GST), mind az adóelőleg beállításait.</span><span class="sxs-lookup"><span data-stu-id="14047-104">Tax setup data defines the setup for both indirect taxes (VAT, GST, Sales tax) and withholding tax.</span></span> <span data-ttu-id="14047-105">Leírja az adószámítási szabályt, az adókulcsot, az adókönyvelés és az elszámolás részleteit, illetve további fogalmakat.</span><span class="sxs-lookup"><span data-stu-id="14047-105">It describes the tax calculation rule, tax rate, tax accounting, settlement, and other concepts.</span></span>

## <a name="templates"></a><span data-ttu-id="14047-106">Sablonok</span><span class="sxs-lookup"><span data-stu-id="14047-106">Templates</span></span>

<span data-ttu-id="14047-107">Az adóadatok tartalmazzák azokat az entitásleképezéseket, amelyek – az alábbi táblázatban látható módon – együttműködnek az adatok interakciója során.</span><span class="sxs-lookup"><span data-stu-id="14047-107">Tax data includes a collection of entity maps that work together during data interaction, as shown in the following table.</span></span>

<span data-ttu-id="14047-108">Finance and Operations-alkalmazásoknak</span><span class="sxs-lookup"><span data-stu-id="14047-108">Finance and Operations apps</span></span> | <span data-ttu-id="14047-109">Modellvezérelt alkalmazások a Dynamics 365-ben</span><span class="sxs-lookup"><span data-stu-id="14047-109">Model-driven apps in Dynamics 365</span></span> | <span data-ttu-id="14047-110">Leírás</span><span class="sxs-lookup"><span data-stu-id="14047-110">Description</span></span> |
-------------------------|---------------------------------|----|
<span data-ttu-id="14047-111">Cikkáfacsoport</span><span class="sxs-lookup"><span data-stu-id="14047-111">Item sales tax group</span></span> | <span data-ttu-id="14047-112">msdyn_taxitemgroups</span><span class="sxs-lookup"><span data-stu-id="14047-112">msdyn_taxitemgroups</span></span> |
<span data-ttu-id="14047-113">Adóhatóságok</span><span class="sxs-lookup"><span data-stu-id="14047-113">Sales tax authorities</span></span> | <span data-ttu-id="14047-114">msdyn_taxauthorities</span><span class="sxs-lookup"><span data-stu-id="14047-114">msdyn_taxauthorities</span></span> |
<span data-ttu-id="14047-115">Áfamentességi kódentitáshoz tartozó CDS</span><span class="sxs-lookup"><span data-stu-id="14047-115">Sales tax exempt code entity CDS</span></span> | <span data-ttu-id="14047-116">msdyn_taxexemptcodes</span><span class="sxs-lookup"><span data-stu-id="14047-116">msdyn_taxexemptcodes</span></span> |
<span data-ttu-id="14047-117">Áfacsoportok</span><span class="sxs-lookup"><span data-stu-id="14047-117">Sales tax groups</span></span> | <span data-ttu-id="14047-118">msdyn_taxgroups</span><span class="sxs-lookup"><span data-stu-id="14047-118">msdyn_taxgroups</span></span> |
<span data-ttu-id="14047-119">Áfás főkönyvi feladási csoportok V2</span><span class="sxs-lookup"><span data-stu-id="14047-119">Sales tax ledger posting groups V2</span></span> | <span data-ttu-id="14047-120">msdyn_taxpostinggroups</span><span class="sxs-lookup"><span data-stu-id="14047-120">msdyn_taxpostinggroups</span></span> |
<span data-ttu-id="14047-121">Adóelőlegkódok</span><span class="sxs-lookup"><span data-stu-id="14047-121">Withholding tax codes</span></span> | <span data-ttu-id="14047-122">msdyn_withholdingtaxcodes</span><span class="sxs-lookup"><span data-stu-id="14047-122">msdyn_withholdingtaxcodes</span></span> |
<span data-ttu-id="14047-123">Adóelőleg-csoportok</span><span class="sxs-lookup"><span data-stu-id="14047-123">Withholding tax groups</span></span> | <span data-ttu-id="14047-124">msdyn_withholdingtaxgroups</span><span class="sxs-lookup"><span data-stu-id="14047-124">msdyn_withholdingtaxgroups</span></span> | 


[!include [banner](../../includes/dual-write-symbols.md)]

[!include [Tax item groups](includes/TaxItemGroupHeadings-msdyn-taxitemgroups.md)]

[!include [Tax Authorities](includes/SalesTaxAuthorities-msdyn-taxauthorities.md)]

[!include [Tax Exemptions](includes/CdsTaxExemptCodes-msdyn-taxexemptcodes.md)]

[!include [Tax groups](includes/TaxGroupEntity-msdyn-taxgroups.md)]

[!include [Tax Ledger Account Group](includes/TaxPostingGroupsV2--msdyn-taxpostinggroups.md)]

[!include [Withholding tax codes](includes/WithholdingCode-msdyn-withholdingtaxcodes.md)]

[!include [Withholding tax groups](includes/WithholdingGroups-msdyn-withholdingtaxgroups.md)]

