---
title: Integrált főkönyv
description: Ez a témakör a főkönyvi adatok Finance and Operations és más Dynamics 365 alkalmazások közötti, a Dataverse használatával történő integrációját ismerteti.
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
ms.openlocfilehash: f8095b0a755e40e5665d951d33ea4ce60e749165
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/09/2021
ms.locfileid: "5567696"
---
# <a name="integrated-ledger"></a><span data-ttu-id="da85f-103">Integrált főkönyv</span><span class="sxs-lookup"><span data-stu-id="da85f-103">Integrated ledger</span></span>

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]



<span data-ttu-id="da85f-104">Egy üzleti pályázatban a főkönyvi adatok határozzák meg a vállalat üzleti tevékenységének alapbeállítását.</span><span class="sxs-lookup"><span data-stu-id="da85f-104">In a business application, ledger data defines the core set up for how a company does business.</span></span> <span data-ttu-id="da85f-105">A főkönyvi adatok például tartalmazzák a vállalat üzleti évét, a tranzakciók pénznemét és a vállalat által használt számlákat.</span><span class="sxs-lookup"><span data-stu-id="da85f-105">For example, ledger data describes the fiscal year the company follows, the currencies it transacts in, and the accounts it uses.</span></span> <span data-ttu-id="da85f-106">Ez a témakör az alapvető pénzügyi adatok integrálását írja le.</span><span class="sxs-lookup"><span data-stu-id="da85f-106">This topic describes the integration of this core financial data.</span></span>

## <a name="templates"></a><span data-ttu-id="da85f-107">Sablonok</span><span class="sxs-lookup"><span data-stu-id="da85f-107">Templates</span></span>

<span data-ttu-id="da85f-108">A főkönyvi adatok tartalmazzák azokat a központi pénzügyi táblaleképezéseket, amelyek – az alábbi táblázatban látható módon – együttműködnek az adatok interakciója során.</span><span class="sxs-lookup"><span data-stu-id="da85f-108">Ledger data includes a collection of core financial table maps that work together during data interaction, as shown in the following table.</span></span>

<span data-ttu-id="da85f-109">Finance and Operations-alkalmazásoknak</span><span class="sxs-lookup"><span data-stu-id="da85f-109">Finance and Operations apps</span></span>      | <span data-ttu-id="da85f-110">Modellvezérelt alkalmazás a Dynamics 365-ben</span><span class="sxs-lookup"><span data-stu-id="da85f-110">Model-driven app in Dynamics 365</span></span> | <span data-ttu-id="da85f-111">Leírás</span><span class="sxs-lookup"><span data-stu-id="da85f-111">Description</span></span>
---------------------------------|----------------------------------|------------
<span data-ttu-id="da85f-112">Pénznemek</span><span class="sxs-lookup"><span data-stu-id="da85f-112">Currencies</span></span>                       | <span data-ttu-id="da85f-113">transactioncurrencies</span><span class="sxs-lookup"><span data-stu-id="da85f-113">transactioncurrencies</span></span>            |
<span data-ttu-id="da85f-114">FiscalCalendar</span><span class="sxs-lookup"><span data-stu-id="da85f-114">FiscalCalendar</span></span>                   | <span data-ttu-id="da85f-115">msdyn\_fiscalcalendars</span><span class="sxs-lookup"><span data-stu-id="da85f-115">msdyn\_fiscalcalendars</span></span>        |
<span data-ttu-id="da85f-116">FiscalCalendarYear</span><span class="sxs-lookup"><span data-stu-id="da85f-116">FiscalCalendarYear</span></span>               | <span data-ttu-id="da85f-117">msdyn\_fiscalcalendaryears</span><span class="sxs-lookup"><span data-stu-id="da85f-117">msdyn\_fiscalcalendaryears</span></span>        |
<span data-ttu-id="da85f-118">ExchRateType</span><span class="sxs-lookup"><span data-stu-id="da85f-118">ExchRateType</span></span>                     | <span data-ttu-id="da85f-119">msdyn\_exchangeratetypes</span><span class="sxs-lookup"><span data-stu-id="da85f-119">msdyn\_exchangeratetypes</span></span>        |
<span data-ttu-id="da85f-120">ExchangeRateCurrencyPair</span><span class="sxs-lookup"><span data-stu-id="da85f-120">ExchangeRateCurrencyPair</span></span>         | <span data-ttu-id="da85f-121">msdyn\_currencyexchangeratepairs</span><span class="sxs-lookup"><span data-stu-id="da85f-121">msdyn\_currencyexchangeratepairs</span></span>        |
<span data-ttu-id="da85f-122">FiscalPeriodEntity</span><span class="sxs-lookup"><span data-stu-id="da85f-122">FiscalPeriodEntity</span></span>               | <span data-ttu-id="da85f-123">msdyn\_fiscalcalendarperiods</span><span class="sxs-lookup"><span data-stu-id="da85f-123">msdyn\_fiscalcalendarperiods</span></span>        |
<span data-ttu-id="da85f-124">MainAccountCategory</span><span class="sxs-lookup"><span data-stu-id="da85f-124">MainAccountCategory</span></span>              | <span data-ttu-id="da85f-125">msdyn\_mainaccountcategory</span><span class="sxs-lookup"><span data-stu-id="da85f-125">msdyn\_mainaccountcategory</span></span>        |
<span data-ttu-id="da85f-126">MainAccount</span><span class="sxs-lookup"><span data-stu-id="da85f-126">MainAccount</span></span>                      | <span data-ttu-id="da85f-127">msdyn\_mainaccounts</span><span class="sxs-lookup"><span data-stu-id="da85f-127">msdyn\_mainaccounts</span></span>        |
<span data-ttu-id="da85f-128">Főkönyv</span><span class="sxs-lookup"><span data-stu-id="da85f-128">Ledger</span></span>                           | <span data-ttu-id="da85f-129">msdyn\_ledgers</span><span class="sxs-lookup"><span data-stu-id="da85f-129">msdyn\_ledgers</span></span>        |
<span data-ttu-id="da85f-130">ExchangeRates</span><span class="sxs-lookup"><span data-stu-id="da85f-130">ExchangeRates</span></span>                    | <span data-ttu-id="da85f-131">msdyn\_currencyexchangerates</span><span class="sxs-lookup"><span data-stu-id="da85f-131">msdyn\_currencyexchangerates</span></span>        |
<span data-ttu-id="da85f-132">FinancialCalendarPeriod</span><span class="sxs-lookup"><span data-stu-id="da85f-132">FinancialCalendarPeriod</span></span>          | <span data-ttu-id="da85f-133">msdyn\_fiscalcalendarperiods</span><span class="sxs-lookup"><span data-stu-id="da85f-133">msdyn\_fiscalcalendarperiods</span></span>        |
<span data-ttu-id="da85f-134">DimensionAttributeEntity</span><span class="sxs-lookup"><span data-stu-id="da85f-134">DimensionAttributeEntity</span></span>         | <span data-ttu-id="da85f-135">msdyn\_dimensionattributes</span><span class="sxs-lookup"><span data-stu-id="da85f-135">msdyn\_dimensionattributes</span></span>        |
<span data-ttu-id="da85f-136">DimensionIntegrationFormatEntity</span><span class="sxs-lookup"><span data-stu-id="da85f-136">DimensionIntegrationFormatEntity</span></span> | <span data-ttu-id="da85f-137">msdyn\_financialdimensionformats</span><span class="sxs-lookup"><span data-stu-id="da85f-137">msdyn\_financialdimensionformats</span></span>        |
<span data-ttu-id="da85f-138">LedgerChartOfAccounts</span><span class="sxs-lookup"><span data-stu-id="da85f-138">LedgerChartOfAccounts</span></span>            | <span data-ttu-id="da85f-139">msdyn\_chartofaccounts</span><span class="sxs-lookup"><span data-stu-id="da85f-139">msdyn\_chartofaccounts</span></span>        |


[!include [banner](../../includes/dual-write-symbols.md)]

[!include [Currency](includes/Currencies-transactioncurrencies.md)]

[!include [Fiscal calendar](includes/FiscalCalendar-msdyn-fiscalcalendars.md)]

[!include [Fiscal calendar year](includes/FiscalCalendarYear-msdyn-fiscalcalendaryears.md)]

[!include [Exchange rate types](includes/ExchRateType-msdyn-exchangeratetypes.md)]

[!include [Exchange rate pair](includes/ExchangeRateCurrencyPair-msdyn-currencyexchangeratepairs.md)]

[!include [Main account category](includes/MainAccountCategory-msdyn-mainaccountcategory.md)]

[!include [Main account](includes/MainAccount-msdyn-mainaccounts.md)]

[!include [Ledger](includes/Ledger-msdyn-ledgers.md)]

[!include [Exchange rates](includes/ExchangeRates-msdyn-currencyexchangerates.md)]

[!include [Financial Calendar Period](includes/FiscalPeriodEntity-msdyn-fiscalcalendarperiods.md)]

[!include [Dimension attribute](includes/DimensionAttributeEntity-msdyn-dimensionattributes.md)]

[!include [Dimension integration format](includes/DimensionIntegrationFormatEntity-msdyn-financialdimensionformats.md)]

[!include [Chart Of Account](includes/LedgerChartOfAccounts-msdyn-chartofaccounts.md)]






[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]