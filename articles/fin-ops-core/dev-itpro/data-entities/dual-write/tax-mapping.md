---
title: Integrált adó
description: Ez a témakör az adóügyi adatok integrációját ismerteti a Finance and Operations és a Dataverse között.
author: robinarh
manager: AnnBe
ms.date: 09/06/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: rhaertle
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 7501ef21492a96c81b971e1d9077beaba9be897b
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/09/2021
ms.locfileid: "5560337"
---
# <a name="integrated-tax"></a><span data-ttu-id="80188-103">Integrált adó</span><span class="sxs-lookup"><span data-stu-id="80188-103">Integrated tax</span></span>

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]



<span data-ttu-id="80188-104">Az adóadatok beállítása határozza meg mind a közvetett adók (áfa, GST), mind az adóelőleg beállításait.</span><span class="sxs-lookup"><span data-stu-id="80188-104">Tax setup data defines the setup for both indirect taxes (VAT, GST, Sales tax) and withholding tax.</span></span> <span data-ttu-id="80188-105">Leírja az adószámítási szabályt, az adókulcsot, az adókönyvelés és az elszámolás részleteit, illetve további fogalmakat.</span><span class="sxs-lookup"><span data-stu-id="80188-105">It describes the tax calculation rule, tax rate, tax accounting, settlement, and other concepts.</span></span>

## <a name="templates"></a><span data-ttu-id="80188-106">Sablonok</span><span class="sxs-lookup"><span data-stu-id="80188-106">Templates</span></span>

<span data-ttu-id="80188-107">Az adóadatok tartalmazzák azokat a táblaleképezéseket, amelyek – az alábbi táblázatban látható módon – együttműködnek az adatok interakciója során.</span><span class="sxs-lookup"><span data-stu-id="80188-107">Tax data includes a collection of table maps that work together during data interaction, as shown in the following table.</span></span>

<span data-ttu-id="80188-108">Finance and Operations-alkalmazásoknak</span><span class="sxs-lookup"><span data-stu-id="80188-108">Finance and Operations apps</span></span> | <span data-ttu-id="80188-109">Modellvezérelt alkalmazások a Dynamics 365-ben</span><span class="sxs-lookup"><span data-stu-id="80188-109">Model-driven apps in Dynamics 365</span></span> | <span data-ttu-id="80188-110">Leírás</span><span class="sxs-lookup"><span data-stu-id="80188-110">Description</span></span> |
-------------------------|---------------------------------|----|
<span data-ttu-id="80188-111">Cikkáfacsoport</span><span class="sxs-lookup"><span data-stu-id="80188-111">Item sales tax group</span></span> | <span data-ttu-id="80188-112">msdyn_taxitemgroups</span><span class="sxs-lookup"><span data-stu-id="80188-112">msdyn_taxitemgroups</span></span> |
<span data-ttu-id="80188-113">Adóhatóságok</span><span class="sxs-lookup"><span data-stu-id="80188-113">Sales tax authorities</span></span> | <span data-ttu-id="80188-114">msdyn_taxauthorities</span><span class="sxs-lookup"><span data-stu-id="80188-114">msdyn_taxauthorities</span></span> |
<span data-ttu-id="80188-115">Áfamentességi kódentitáshoz tartozó CDS</span><span class="sxs-lookup"><span data-stu-id="80188-115">Sales tax exempt code entity CDS</span></span> | <span data-ttu-id="80188-116">msdyn_taxexemptcodes</span><span class="sxs-lookup"><span data-stu-id="80188-116">msdyn_taxexemptcodes</span></span> |
<span data-ttu-id="80188-117">Áfacsoportok</span><span class="sxs-lookup"><span data-stu-id="80188-117">Sales tax groups</span></span> | <span data-ttu-id="80188-118">msdyn_taxgroups</span><span class="sxs-lookup"><span data-stu-id="80188-118">msdyn_taxgroups</span></span> |
<span data-ttu-id="80188-119">Áfás főkönyvi feladási csoportok V2</span><span class="sxs-lookup"><span data-stu-id="80188-119">Sales tax ledger posting groups V2</span></span> | <span data-ttu-id="80188-120">msdyn_taxpostinggroups</span><span class="sxs-lookup"><span data-stu-id="80188-120">msdyn_taxpostinggroups</span></span> |
<span data-ttu-id="80188-121">Adóelőlegkódok</span><span class="sxs-lookup"><span data-stu-id="80188-121">Withholding tax codes</span></span> | <span data-ttu-id="80188-122">msdyn_withholdingtaxcodes</span><span class="sxs-lookup"><span data-stu-id="80188-122">msdyn_withholdingtaxcodes</span></span> |
<span data-ttu-id="80188-123">Adóelőleg-csoportok</span><span class="sxs-lookup"><span data-stu-id="80188-123">Withholding tax groups</span></span> | <span data-ttu-id="80188-124">msdyn_withholdingtaxgroups</span><span class="sxs-lookup"><span data-stu-id="80188-124">msdyn_withholdingtaxgroups</span></span> | 


[!include [banner](../../includes/dual-write-symbols.md)]

[!include [Tax item groups](includes/TaxItemGroupHeadings-msdyn-taxitemgroups.md)]

[!include [Tax Authorities](includes/SalesTaxAuthorities-msdyn-taxauthorities.md)]

[!include [Tax Exemptions](includes/CdsTaxExemptCodes-msdyn-taxexemptcodes.md)]

[!include [Tax groups](includes/TaxGroupEntity-msdyn-taxgroups.md)]

[!include [Tax Ledger Account Group](includes/TaxPostingGroupsV2--msdyn-taxpostinggroups.md)]

[!include [Withholding tax codes](includes/WithholdingCode-msdyn-withholdingtaxcodes.md)]

[!include [Withholding tax groups](includes/WithholdingGroups-msdyn-withholdingtaxgroups.md)]



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]