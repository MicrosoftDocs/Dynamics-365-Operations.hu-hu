---
title: "Áfa átváltási arány áttekintése"
description: "Ez a témakör az áfaszámítás árfolyamairól nyújt tájékoztatást. Az áfa kiszámításához választott átváltási árfolyam eltérhet a vállalat könyvelési funkciói esetében alkalmazott átváltási árfolyamtól. Amikor külföldi pénznemben lévő dokumentumot adnak fel, az esetleges árfolyamkülönbségek a meghatározott főkönyvi számlákra kerülnek."
author: ShylaThompson
manager: AnnBe
ms.date: 04/10/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ExchangeRateCurrencyPairCalculationRules, LedgerParameters, SalesTaxExchangeRateType, TaxTmpWorkTrans
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 272703
ms.assetid: 2d1fad67-8234-49cc-b009-0f3cc29f5886
ms.search.region: Czech Republic, Hungary, Poland
ms.author: mrolecki
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: a91fa0b2952ef9baad43df63de2a39e00d7ac368
ms.contentlocale: hu-hu
ms.lasthandoff: 04/13/2018

---

# <a name="vat-exchange-rate-overview"></a><span data-ttu-id="16c30-105">Áfa átváltási arány áttekintése</span><span class="sxs-lookup"><span data-stu-id="16c30-105">VAT exchange rate overview</span></span>

[!INCLUDE [banner](../includes/banner.md)]

<span data-ttu-id="16c30-106">Ez a témakör az áfaszámítás árfolyamairól nyújt tájékoztatást.</span><span class="sxs-lookup"><span data-stu-id="16c30-106">This topic provides information about exchange rates for the VAT calculation.</span></span> <span data-ttu-id="16c30-107">Az áfa kiszámításához választott átváltási árfolyam eltérhet a vállalat könyvelési funkciói esetében alkalmazott átváltási árfolyamtól.</span><span class="sxs-lookup"><span data-stu-id="16c30-107">The exchange rate that is used for VAT calculation can differ from the exchange rate that is used for company accounting functions.</span></span> <span data-ttu-id="16c30-108">Amikor külföldi pénznemben lévő dokumentumot adnak fel, az esetleges árfolyamkülönbségek a meghatározott főkönyvi számlákra kerülnek.</span><span class="sxs-lookup"><span data-stu-id="16c30-108">When a document in a foreign currency is posted, any exchange rate differences that occur are posted to specific ledger accounts.</span></span>

<span data-ttu-id="16c30-109">A szervezet kiválaszthatja az áfa kiszámítására használni kívánt árfolyamot az áfabevallásokhoz.</span><span class="sxs-lookup"><span data-stu-id="16c30-109">Your organization can select the exchange rate that it uses to calculate value-added tax (VAT) for VAT statements.</span></span> <span data-ttu-id="16c30-110">Az árfolyam eltérhet attól az árfolyamtól, amelyet a szervezet a vállalati könyvelési feladatok során alkalmaz.</span><span class="sxs-lookup"><span data-stu-id="16c30-110">This exchange rate can differ from the exchange rate that your organization uses for company accounting functions.</span></span> <span data-ttu-id="16c30-111">A könyvelési feladatok közé tartozik az adókkal kapcsolatos következő dokumentumok előkészítése:</span><span class="sxs-lookup"><span data-stu-id="16c30-111">Accounting functions include the preparation of the following tax-related documents:</span></span>

-   <span data-ttu-id="16c30-112">Számlák</span><span class="sxs-lookup"><span data-stu-id="16c30-112">Invoices</span></span>
-   <span data-ttu-id="16c30-113">Szabadszöveges számlák</span><span class="sxs-lookup"><span data-stu-id="16c30-113">Free text invoices</span></span>
-   <span data-ttu-id="16c30-114">Beszerzési rendelések</span><span class="sxs-lookup"><span data-stu-id="16c30-114">Purchase orders</span></span>
-   <span data-ttu-id="16c30-115">Projektszámlák</span><span class="sxs-lookup"><span data-stu-id="16c30-115">Project invoices</span></span>
-   <span data-ttu-id="16c30-116">Jóváírások</span><span class="sxs-lookup"><span data-stu-id="16c30-116">Credit notes</span></span>
-   <span data-ttu-id="16c30-117">Helyesbítő számlák</span><span class="sxs-lookup"><span data-stu-id="16c30-117">Corrective invoices</span></span>

<span data-ttu-id="16c30-118">Amikor külföldi pénznemben lévő dokumentumot ad fel, az esetleges árfolyamkülönbségek a meghatározott főkönyvi számlákra kerülnek.</span><span class="sxs-lookup"><span data-stu-id="16c30-118">When you post a document that uses a foreign currency, any exchange rate differences that occur are posted to specific ledger accounts.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="16c30-119">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="16c30-119">Prerequisites</span></span>

<span data-ttu-id="16c30-120">Ahhoz, hogy ezt a funkciót használni tudja, konfigurálnia kell a rendszert.</span><span class="sxs-lookup"><span data-stu-id="16c30-120">Before you can use this functionality, you must configure the system.</span></span>

1.  <span data-ttu-id="16c30-121">Készítsen árfolyamtípusokat, és állítsa be az áfára vonatkozó átváltási árfolyamokat itt: **Főkönyv** &gt; **Pénznemek** &gt; **Árfolyamtípusok**.</span><span class="sxs-lookup"><span data-stu-id="16c30-121">Create exchange rate types and set up exchange rates for the sales tax at **General ledger** &gt; **Currencies** &gt; **Exchange rate types**.</span></span> <span data-ttu-id="16c30-122">Tetszőleges számú árfolyamtípust és devizaárfolyamot adhat meg.</span><span class="sxs-lookup"><span data-stu-id="16c30-122">You can define as many exchange rate types and as many exchange rates for pairs of currencies as you require.</span></span>
2.  <span data-ttu-id="16c30-123">Kapcsolja be az áfa átváltási arányainak kiszámítását a **Bank - árfolyam** paraméter bekapcsolásával, továbbá a beérkező és fizetendő áfa átváltásiárfolyam-típusainak meghatározásával itt: **Főkönyv** &gt; **Főkönyv beállításai** &gt; **Főkönyvi paraméterek**.</span><span class="sxs-lookup"><span data-stu-id="16c30-123">Enable the calculation of VAT exchange rates by turning on the **Bank exchange rate** parameter, and by defining sales tax receivable and sales tax payable exchange rate types, at **General ledger** &gt; **Ledger setup** &gt; **General ledger parameters**.</span></span>
3.  <span data-ttu-id="16c30-124">Állítsa be a pénznemek átváltási árfolyamtípusait az adott értékesítési és beszerzési tranzakciótípusokhoz itt: **Főkönyv** &gt; **Pénznemek** &gt; **Pénznemek árfolyamtípusai az áfához**.</span><span class="sxs-lookup"><span data-stu-id="16c30-124">Set up currency exchange rate types for specific sales and purchase transaction types at **General ledger** &gt; **Currencies** &gt; **Currency exchange rate types for sales tax**.</span></span>
4.  <span data-ttu-id="16c30-125">A felszámított és fizetendő áfa közötti különbség és az eltérések főkönyvi ellenszámlájának beállítása a főkönyv feladási csoportjaiban: **Áfa** &gt; **Beállítás** &gt; **Áfa** &gt; **Főkönyvi feladási csoportok**.</span><span class="sxs-lookup"><span data-stu-id="16c30-125">Set up sales tax receivable and sales tax payable difference and difference offset accounts in the ledger posting groups at **Tax** &gt; **Setup** &gt; **Sales tax** &gt; **Ledger posting groups**.</span></span>
5.  <span data-ttu-id="16c30-126">Nem kötelező: Állítsa be az árfolyam-számítási szabályt a pénznempárra vonatkozóan a **Főkönyv**&gt;**Pénznemek**&gt;**Pénznempárok árfolyam-számítási szabályai** pontra.</span><span class="sxs-lookup"><span data-stu-id="16c30-126">Optional: Set up an exchange rate calculation rule for a currency pair at **General ledger** &gt; **Currencies** &gt; **Exchange rate calculation rules for currency pairs**.</span></span> <span data-ttu-id="16c30-127">Az árfolyam-számítási szabályokat a devizában meghatározott értékesítési számlák áfaösszegének a cél pénznemre való konvertálása során alkalmazza a rendszer.</span><span class="sxs-lookup"><span data-stu-id="16c30-127">The exchange rate calculation rules are used to convert VAT amounts for foreign currency sales invoices to VAT amounts in a destination currency.</span></span>

## <a name="overview"></a><span data-ttu-id="16c30-128">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="16c30-128">Overview</span></span>

<span data-ttu-id="16c30-129">Miután beállította a rendszert az áfaárfolyamok használatára, ha be kell írnia a dokumentumot, vagy létre kell hoznia egy devizát használó megbízást, akkor az **Áfatranzakciók** oldalon kell beállítania az **Áfatételjegyzék dátuma** értéket, illetve megadnia az alapértelmezett **Áfa árfolyama** értéket.</span><span class="sxs-lookup"><span data-stu-id="16c30-129">After you've configured the system to use VAT exchange rates, if you must enter a document or create an order that uses a foreign currency, you can use **Sales tax transactions** page to set the **Date of VAT register** value to pick up and set the default **Sales tax exchange rate** value.</span></span> <span data-ttu-id="16c30-130">Mindkét mező szerkeszthető.</span><span class="sxs-lookup"><span data-stu-id="16c30-130">You can edit both fields.</span></span> <span data-ttu-id="16c30-131">Emellett használható a **Helyesbített eredeti összeg (áfaárfolyam)** vagy a **Helyesbített áfaösszeg (áfaárfolyam)** mező is a tényleges áfaösszegek megadására abba a helyi pénznemben, amely meg van határozva egy külső dokumentumban.</span><span class="sxs-lookup"><span data-stu-id="16c30-131">You can also use the **Adjusted amount origin (VAT exchange rate)** or **Adjusted sales tax amount (VAT exchange rate)** field to enter actual VAT amounts in the local currency that is stated in an external document.</span></span> <span data-ttu-id="16c30-132">A könyvelés áttekintésekor megtekintheti az áfakülönbségeket az **Analitikus napló** oldalon.</span><span class="sxs-lookup"><span data-stu-id="16c30-132">When you review the accounting, you can view sales tax difference amounts on the **Subledger journal** page.</span></span> <span data-ttu-id="16c30-133">Amikor a dokumentumot feladják, az olyan tranzakciók esetében, amelyeket az Ön által konfigurált főkönyvi számlákra adtak fel, megtekintheti az áfa összegének azon különbségeit, amelyek az áfa pénznemének átváltási árfolyama és a számlázási devizaárfolyam különbsége okoz a szervezeted számára.</span><span class="sxs-lookup"><span data-stu-id="16c30-133">When a document is posted, for transactions that are posted to the general ledger accounts that you've configured, you can view any differences in sales tax amounts that are caused by the difference between the VAT currency exchange rate and the accounting currency exchange rate for your organization.</span></span>





