---
title: Integrált főkönyv
description: Ez a témakör a főkönyvi adatok Finance and Operations és más Dynamics 365 alkalmazások közötti, a Common Data Service használatával történő integrációját ismerteti.
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
ms.openlocfilehash: 4a0a8f2f52cf9a73efc3557b63793201a7a3f8b8
ms.sourcegitcommit: d0322d1ed6c798301058e44dae76227a0e1f49ac
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2019
ms.locfileid: "2853882"
---
# <a name="integrated-ledger"></a><span data-ttu-id="c12d8-103">Integrált főkönyv</span><span class="sxs-lookup"><span data-stu-id="c12d8-103">Integrated ledger</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c12d8-104">Egy üzleti pályázatban a főkönyvi adatok határozzák meg a vállalat üzleti tevékenységének alapbeállítását.</span><span class="sxs-lookup"><span data-stu-id="c12d8-104">In a business application, ledger data defines the core set up for how a company does business.</span></span> <span data-ttu-id="c12d8-105">A főkönyvi adatok például tartalmazzák a vállalat üzleti évét, a tranzakciók pénznemét és a vállalat által használt számlákat.</span><span class="sxs-lookup"><span data-stu-id="c12d8-105">For example, ledger data describes the fiscal year the company follows, the currencies it transacts in, and the accounts it uses.</span></span> <span data-ttu-id="c12d8-106">Ez a témakör az alapvető pénzügyi adatok integrálását írja le.</span><span class="sxs-lookup"><span data-stu-id="c12d8-106">This topic describes the integration of this core financial data.</span></span>

## <a name="templates"></a><span data-ttu-id="c12d8-107">Sablonok</span><span class="sxs-lookup"><span data-stu-id="c12d8-107">Templates</span></span>

<span data-ttu-id="c12d8-108">A főkönyvi adatok tartalmazzák azokat a központi pénzügyi entitásleképezéseket, amelyek – az alábbi táblázatban látható módon – együttműködnek az adatok interakciója során.</span><span class="sxs-lookup"><span data-stu-id="c12d8-108">Ledger data includes a collection of core financial entity maps that work together during data interaction, as shown in the following table.</span></span>

<span data-ttu-id="c12d8-109">Finance and Operations alkalmazások</span><span class="sxs-lookup"><span data-stu-id="c12d8-109">Finance and Operations apps</span></span>      | <span data-ttu-id="c12d8-110">Egyéb Dynamics 365 alkalmazások</span><span class="sxs-lookup"><span data-stu-id="c12d8-110">Other Dynamics 365 apps</span></span>
---------------------------------|---------------------------------
<span data-ttu-id="c12d8-111">Pénznemek</span><span class="sxs-lookup"><span data-stu-id="c12d8-111">Currencies</span></span>                       | <span data-ttu-id="c12d8-112">transactioncurrencies</span><span class="sxs-lookup"><span data-stu-id="c12d8-112">transactioncurrencies</span></span>
<span data-ttu-id="c12d8-113">FiscalCalendar</span><span class="sxs-lookup"><span data-stu-id="c12d8-113">FiscalCalendar</span></span>                   | <span data-ttu-id="c12d8-114">msdyn\_fiscalcalendars</span><span class="sxs-lookup"><span data-stu-id="c12d8-114">msdyn\_fiscalcalendars</span></span>
<span data-ttu-id="c12d8-115">FiscalCalendarYear</span><span class="sxs-lookup"><span data-stu-id="c12d8-115">FiscalCalendarYear</span></span>               | <span data-ttu-id="c12d8-116">msdyn\_fiscalcalendaryears</span><span class="sxs-lookup"><span data-stu-id="c12d8-116">msdyn\_fiscalcalendaryears</span></span>
<span data-ttu-id="c12d8-117">ExchRateType</span><span class="sxs-lookup"><span data-stu-id="c12d8-117">ExchRateType</span></span>                     | <span data-ttu-id="c12d8-118">msdyn\_exchangeratetypes</span><span class="sxs-lookup"><span data-stu-id="c12d8-118">msdyn\_exchangeratetypes</span></span>
<span data-ttu-id="c12d8-119">ExchangeRateCurrencyPair</span><span class="sxs-lookup"><span data-stu-id="c12d8-119">ExchangeRateCurrencyPair</span></span>         | <span data-ttu-id="c12d8-120">msdyn\_currencyexchangeratepairs</span><span class="sxs-lookup"><span data-stu-id="c12d8-120">msdyn\_currencyexchangeratepairs</span></span>
<span data-ttu-id="c12d8-121">FiscalPeriodEntity</span><span class="sxs-lookup"><span data-stu-id="c12d8-121">FiscalPeriodEntity</span></span>               | <span data-ttu-id="c12d8-122">msdyn\_fiscalcalendarperiods</span><span class="sxs-lookup"><span data-stu-id="c12d8-122">msdyn\_fiscalcalendarperiods</span></span>
<span data-ttu-id="c12d8-123">MainAccountCategory</span><span class="sxs-lookup"><span data-stu-id="c12d8-123">MainAccountCategory</span></span>              | <span data-ttu-id="c12d8-124">msdyn\_mainaccountcategory</span><span class="sxs-lookup"><span data-stu-id="c12d8-124">msdyn\_mainaccountcategory</span></span>
<span data-ttu-id="c12d8-125">MainAccount</span><span class="sxs-lookup"><span data-stu-id="c12d8-125">MainAccount</span></span>                      | <span data-ttu-id="c12d8-126">msdyn\_mainaccounts</span><span class="sxs-lookup"><span data-stu-id="c12d8-126">msdyn\_mainaccounts</span></span>
<span data-ttu-id="c12d8-127">Főkönyv</span><span class="sxs-lookup"><span data-stu-id="c12d8-127">Ledger</span></span>                           | <span data-ttu-id="c12d8-128">msdyn\_ledgers</span><span class="sxs-lookup"><span data-stu-id="c12d8-128">msdyn\_ledgers</span></span>
<span data-ttu-id="c12d8-129">ExchangeRates</span><span class="sxs-lookup"><span data-stu-id="c12d8-129">ExchangeRates</span></span>                    | <span data-ttu-id="c12d8-130">msdyn\_currencyexchangerates</span><span class="sxs-lookup"><span data-stu-id="c12d8-130">msdyn\_currencyexchangerates</span></span>
<span data-ttu-id="c12d8-131">FinancialCalendarPeriod</span><span class="sxs-lookup"><span data-stu-id="c12d8-131">FinancialCalendarPeriod</span></span>          | <span data-ttu-id="c12d8-132">msdyn\_fiscalcalendarperiods</span><span class="sxs-lookup"><span data-stu-id="c12d8-132">msdyn\_fiscalcalendarperiods</span></span>
<span data-ttu-id="c12d8-133">DimensionAttributeEntity</span><span class="sxs-lookup"><span data-stu-id="c12d8-133">DimensionAttributeEntity</span></span>         | <span data-ttu-id="c12d8-134">msdyn\_dimensionattributes.md</span><span class="sxs-lookup"><span data-stu-id="c12d8-134">msdyn\_dimensionattributes.md</span></span>
<span data-ttu-id="c12d8-135">DimensionIntegrationFormatEntity</span><span class="sxs-lookup"><span data-stu-id="c12d8-135">DimensionIntegrationFormatEntity</span></span> | <span data-ttu-id="c12d8-136">msdyn\_financialdimensionformats.md</span><span class="sxs-lookup"><span data-stu-id="c12d8-136">msdyn\_financialdimensionformats.md</span></span>
<span data-ttu-id="c12d8-137">LedgerChartOfAccounts</span><span class="sxs-lookup"><span data-stu-id="c12d8-137">LedgerChartOfAccounts</span></span>            | <span data-ttu-id="c12d8-138">msdyn\_chartofaccounts.md</span><span class="sxs-lookup"><span data-stu-id="c12d8-138">msdyn\_chartofaccounts.md</span></span>


[!include [banner](../includes/dual-write-symbols.md)]

[!include [Currency](dual-write/Currencies-transactioncurrencies.md)]

[!include [Fiscal calendar](dual-write/FiscalCalendar-msdyn-fiscalcalendars.md)]

[!include [Fiscal calendar year](dual-write/FiscalCalendarYear-msdyn-fiscalcalendaryears.md)]

[!include [Exchange rate types](dual-write/ExchRateType-msdyn-exchangeratetypes.md)]

[!include [Exchange rate pair](dual-write/ExchangeRateCurrencyPair-msdyn-currencyexchangeratepairs.md)]

[!include [Ledger fiscal periods](dual-write/FiscalPeriodEntity-msdyn-fiscalcalendarperiods.md)]

[!include [Main account category](dual-write/MainAccountCategory-msdyn-mainaccountcategory.md)]

[!include [Main account](dual-write/MainAccount-msdyn-mainaccounts.md)]

[!include [Ledger](dual-write/Ledger-msdyn-ledgers.md)]

[!include [Exchange rates](dual-write/ExchangeRates-msdyn-currencyexchangerates.md)]

[!include [Financial Calendar Period](dual-write/FiscalPeriodEntity-msdyn-fiscalcalendarperiods.md)]

[!include [Dimension attribute](dual-write/DimensionAttributeEntity-msdyn-dimensionattributes.md)]

[!include [Dimension integration format](dual-write/DimensionIntegrationFormatEntity-msdyn-financialdimensionformats.md)]

[!include [Chart Of Account](dual-write/LedgerChartOfAccounts-msdyn-chartofaccounts.md)]




