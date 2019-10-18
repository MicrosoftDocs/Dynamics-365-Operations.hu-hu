---
title: Akkreditívek és importbeszedvények
description: Ez a cikk általános információt biztosít a hitellevéllel és az import-beszedésekkel kapcsolatban. A banki dokumentumok ezen két formáját gyakran alkalmazzák termékek nemzetközi beszerzésekor és értékesítésekor.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankLCImport
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 18321
ms.assetid: 5c97ab81-632b-4043-a940-674bcb496c80
ms.search.region: Global
ms.author: leguo
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 714cebc3d7aca60004af3418cdbb6a6576491b09
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/27/2019
ms.locfileid: "2178123"
---
# <a name="letters-of-credit-and-import-collections"></a><span data-ttu-id="c13b4-104">Akkreditívek és importbeszedvények</span><span class="sxs-lookup"><span data-stu-id="c13b4-104">Letters of credit and import collections</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c13b4-105">Ez a cikk általános információt biztosít a hitellevéllel és az import-beszedésekkel kapcsolatban.</span><span class="sxs-lookup"><span data-stu-id="c13b4-105">This article provides general information about letters of credit and import collections.</span></span> <span data-ttu-id="c13b4-106">A banki dokumentumok ezen két formáját gyakran alkalmazzák termékek nemzetközi beszerzésekor és értékesítésekor.</span><span class="sxs-lookup"><span data-stu-id="c13b4-106">Both types of bank document are often used for the purchase and sale of goods across international borders.</span></span>

<a name="letters-of-credit"></a><span data-ttu-id="c13b4-107">Akkreditívek</span><span class="sxs-lookup"><span data-stu-id="c13b4-107">Letters of credit</span></span>
-----------------

<span data-ttu-id="c13b4-108">A kifizetések végrehajtását garantálására szolgáló akkreditíveket nemzetközi tranzakciók használják.</span><span class="sxs-lookup"><span data-stu-id="c13b4-108">Letters of credit are used for international transactions and help guarantee that payments will be made.</span></span> <span data-ttu-id="c13b4-109">Az akkreditív egy bank által kiállított megállapodás, amelyben a bank garantálja a kifizetés teljesítését a vevő részéről, amennyiben a vevő és eladó közti megállapodás feltételei fennállnak.</span><span class="sxs-lookup"><span data-stu-id="c13b4-109">A letter of credit is an agreement that is issued by a bank, in which the bank agrees to guarantee payment on behalf of a buyer, provided that the terms of the agreement between the buyer and seller are met.</span></span> <span data-ttu-id="c13b4-110">Az akkreditívet okmányos meghitelezésnek (DC) is nevezik.</span><span class="sxs-lookup"><span data-stu-id="c13b4-110">A letter of credit is also referred to as a documentary credit (DC).</span></span>

<span data-ttu-id="c13b4-111">Az Importakkreditív a jogi személy esetében a vevő vagy a pályázó az akkreditíven való használathoz.</span><span class="sxs-lookup"><span data-stu-id="c13b4-111">For an import letter of credit, the legal entity is the buyer or the applicant for the letter of credit.</span></span> <span data-ttu-id="c13b4-112">Az Importakkreditív a jogi személy esetében a vevő vagy a pályázó az akkreditíven való használathoz.</span><span class="sxs-lookup"><span data-stu-id="c13b4-112">For an export letter of credit, the legal entity is the seller or the beneficiary of the letter of credit.</span></span> <span data-ttu-id="c13b4-113">Az akkreditívben a következő felek vesznek részt:</span><span class="sxs-lookup"><span data-stu-id="c13b4-113">The following parties are involved in a letter of credit:</span></span>

-   <span data-ttu-id="c13b4-114">A pályázó (személy beszerző) aki az árut kifizetni szándékozik</span><span class="sxs-lookup"><span data-stu-id="c13b4-114">The applicant (buyer) who intends to pay for the goods</span></span>
-   <span data-ttu-id="c13b4-115">A kedvezményezett (eladó) aki megkapja a fizetést</span><span class="sxs-lookup"><span data-stu-id="c13b4-115">The beneficiary (seller) who will receive the payment</span></span>
-   <span data-ttu-id="c13b4-116">A kiállító bank, amely kiadja az akkreditívet</span><span class="sxs-lookup"><span data-stu-id="c13b4-116">The issuing bank that issues the letter of credit</span></span>
-   <span data-ttu-id="c13b4-117">Az értesítő bank, amely végrehajtja a tranzakciót, a pályázó nevében</span><span class="sxs-lookup"><span data-stu-id="c13b4-117">The advising bank that carries out the transaction on behalf of the applicant</span></span>

<span data-ttu-id="c13b4-118">Az akkreditív tartalmaz egy leírást az áruról, az összes szükséges dokumentumot, a szállítási dátumot és a lejárati dátumot, amely után nem lehet fizetni.</span><span class="sxs-lookup"><span data-stu-id="c13b4-118">The letter of credit includes a description of the goods, any required documents, the date of shipment, and the expiration date after which payment won't be made.</span></span> <span data-ttu-id="c13b4-119">A kibocsátó bank szedi be tűréshatáron az akkreditíven való használathoz.</span><span class="sxs-lookup"><span data-stu-id="c13b4-119">The issuing bank collects a margin for the letter of credit.</span></span> 

<span data-ttu-id="c13b4-120">Az akkreditívek **visszavonható** vagy **visszavonhatatlan** típusúak lehetnek.</span><span class="sxs-lookup"><span data-stu-id="c13b4-120">A letter of credit can be **revocable** or **irrevocable**.</span></span> <span data-ttu-id="c13b4-121">Az akkreditív jellege lehet **átruházható**, **nem átruházható**, vagy **forgó**.</span><span class="sxs-lookup"><span data-stu-id="c13b4-121">The nature of a letter of credit can be **transferable**, **non-transferable**, or **revolving**.</span></span> <span data-ttu-id="c13b4-122">Az akkreditív általában visszavonhatatlan és visszaigazolt megállapodást, amely a kifizetés teljes és pontos szállítás dokumentáció benyújtása után egy adott kedvezményezett történik.</span><span class="sxs-lookup"><span data-stu-id="c13b4-122">Typically, a letter of credit is an irrevocable and confirmed agreement that payment will be made to a specific beneficiary upon submission of complete and accurate shipping documentation.</span></span>

## <a name="import-collections"></a><span data-ttu-id="c13b4-123">Importált felszólítások</span><span class="sxs-lookup"><span data-stu-id="c13b4-123">Import collections</span></span>
<span data-ttu-id="c13b4-124">Az importbeszedvény a bank és exportőr (eladó) közötti megállapodás, amelyben a bank pedig elfogadja, hogy a szállítási dokumentációt átadja a nemzetközi importőrnek (vevő).</span><span class="sxs-lookup"><span data-stu-id="c13b4-124">An import collection is an agreement between the bank and the exporter (seller), in which the bank agrees to deliver the shipping documentation to the international importer (buyer).</span></span> <span data-ttu-id="c13b4-125">A bank a szállítási dokumentációt a fizetés készpénzben történő megérkezésekor szállítja, vagy a fizetésről aláírt vázlat bevételezése után.</span><span class="sxs-lookup"><span data-stu-id="c13b4-125">The bank is expected to deliver the shipping documentation upon receipt of payment for the shipped goods in cash, or upon receipt of a signed draft toward the payment.</span></span> 

<span data-ttu-id="c13b4-126">Az importbeszedvény segítségével garantálható, hogy az eladó megkapja a fizetést, amikor a vevő átveszi a szállítási dokumentumokat, hogy átvegye az importált áruk szállítmányát.</span><span class="sxs-lookup"><span data-stu-id="c13b4-126">An import collection helps guarantee that the seller is paid when the buyer collects the shipping documents to take delivery of the imported goods.</span></span>



