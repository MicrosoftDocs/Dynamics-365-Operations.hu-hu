---
title: "Tárgyi eszközök értékcsökkenése"
description: "Ez a cikk a tárgyi eszközök értékcsökkenéséről nyújt áttekintést."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AssetBonus, AssetBookTable
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 3121
ms.assetid: 98ff891f-e0e2-4184-b618-28107a50851f
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 536acd6b2c9f046c2459aec27a1e3b1b56fd5cc9
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---

# <a name="fixed-asset-depreciation"></a><span data-ttu-id="8b8a3-103">Tárgyi eszközök értékcsökkenése</span><span class="sxs-lookup"><span data-stu-id="8b8a3-103">Fixed asset depreciation</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="8b8a3-104">Ez a cikk a tárgyi eszközök értékcsökkenéséről nyújt áttekintést.</span><span class="sxs-lookup"><span data-stu-id="8b8a3-104">This article provides an overview of depreciation for fixed assets.</span></span>

<span data-ttu-id="8b8a3-105">Állítson be értékcsökkenést, ami egy ismétlődő tranzakció, és amely a mérlegszámlán csökkenti a tárgyi eszköz értékét, és a csökkenést kiadásként egy eredményszámlára terheli.</span><span class="sxs-lookup"><span data-stu-id="8b8a3-105">Depreciation is a periodic transaction that typically reduces the value of the fixed asset on the balance sheet, and is charged as an expenditure to a profit and loss account.</span></span> <span data-ttu-id="8b8a3-106">Ezért általában a fő számla szolgál a mérlegszámla időszakos értékcsökkenése jóváírására.</span><span class="sxs-lookup"><span data-stu-id="8b8a3-106">Therefore, a main account is typically used to credit the periodic depreciation on the balance sheet.</span></span> <span data-ttu-id="8b8a3-107">Az Ellenszámla pedig a a számlatükör eredményszámla részébe egy olyan számla.</span><span class="sxs-lookup"><span data-stu-id="8b8a3-107">An offset account is an account in the profit and loss part of the chart of accounts.</span></span>

## <a name="depreciation-adjustment"></a><span data-ttu-id="8b8a3-108">Értékcsökkenés helyesbítése</span><span class="sxs-lookup"><span data-stu-id="8b8a3-108">Depreciation adjustment</span></span>
<span data-ttu-id="8b8a3-109">Általában csak egy már feladott értékcsökkenési tranzakció helyesbítése adható fel úgy, mint az.</span><span class="sxs-lookup"><span data-stu-id="8b8a3-109">Usually, only a correction to a posted depreciation transaction is posted as a depreciation adjustment.</span></span> <span data-ttu-id="8b8a3-110">A fő számla és az ellenszámla beállításai így megegyeznek az értékcsökkenés számláival.</span><span class="sxs-lookup"><span data-stu-id="8b8a3-110">Therefore, both the main account and the offset account are set up just like the accounts for depreciation.</span></span> <span data-ttu-id="8b8a3-111">Az értékcsökkenési kiigazítás pozitív és negatív összeg is lehet, de a fő számla (mint mérlegszámla) és az ellenszámla (általában mint eredményszámla) működése nem változik.</span><span class="sxs-lookup"><span data-stu-id="8b8a3-111">A depreciation adjustment can be either a positive amount or a negative amount, but the functionality of the main account (as a balance sheet account) and the functionality of the offset account (usually as a profit and loss account) remain the same.</span></span>

## <a name="extraordinary-depreciation"></a><span data-ttu-id="8b8a3-112">Rendkívüli értékcsökkenés</span><span class="sxs-lookup"><span data-stu-id="8b8a3-112">Extraordinary depreciation</span></span>
<span data-ttu-id="8b8a3-113">A rendkívüli értékcsökkenés rendes értékcsökkenésként működik.</span><span class="sxs-lookup"><span data-stu-id="8b8a3-113">Extraordinary depreciation works like basic depreciation.</span></span> <span data-ttu-id="8b8a3-114">Ebben az esetben a fő számla használatos az értékcsökkenési összeg mérlegszámlára történő jóváírására és a tárgyi eszköz értékének csökkentésére.</span><span class="sxs-lookup"><span data-stu-id="8b8a3-114">Therefore, a main account is used to credit the depreciation amount to the balance sheet and reduce the value of the fixed asset.</span></span> <span data-ttu-id="8b8a3-115">Egy Ellenszámla típusú számlájára egy eredményszámla, ahol a pénzügyi időszakra kiszámított értékcsökkenés kiadásként.</span><span class="sxs-lookup"><span data-stu-id="8b8a3-115">An offset account is a profit and loss account, where the depreciation that is calculated for the fiscal period is charged as an expenditure.</span></span> 

<span data-ttu-id="8b8a3-116">A Rendkívüli értékcsökkenés a rendes értékcsökkenéstől függetlenül működik.</span><span class="sxs-lookup"><span data-stu-id="8b8a3-116">Extraordinary depreciation works independently of basic depreciation.</span></span> <span data-ttu-id="8b8a3-117">A külön tranzakciótípusnak számító különleges értékcsökkenés lehetővé teszi, hogy a rendes értékcsökkenésen kívül rendkívüli értékcsökkenést is feladhasson és jelenthessen.</span><span class="sxs-lookup"><span data-stu-id="8b8a3-117">By having extraordinary depreciation as a separate transaction type, you can post and report the extraordinary depreciation separately from the basic depreciation.</span></span>

## <a name="special-depreciation-allowance"></a><span data-ttu-id="8b8a3-118">Különleges értékcsökkenési keret</span><span class="sxs-lookup"><span data-stu-id="8b8a3-118">Special depreciation allowance</span></span>
<span data-ttu-id="8b8a3-119">A különleges értékcsökkenési keret segítségével különleges értékcsökkenési összegeket alkalmazhat egy eszköz üzembe helyezésének és értékcsökkenésének első évében.</span><span class="sxs-lookup"><span data-stu-id="8b8a3-119">You can use special depreciation allowances to take extra depreciation amounts during the first year that an asset is put in service and depreciated.</span></span> <span data-ttu-id="8b8a3-120">A különleges értékcsökkenési keretet a többi értékcsökkenési számítás előtt kell végrehajtani.</span><span class="sxs-lookup"><span data-stu-id="8b8a3-120">Special depreciation allowances must be taken before any other depreciation calculations.</span></span> <span data-ttu-id="8b8a3-121">Mivel a különleges értékcsökkenési keretek gyakran ismeretlenek a tárgyi eszköz élettartamának későbbi időpontjáig, célszerű ezt a típust nem a főkönyvbe feladott könyvvel használni.</span><span class="sxs-lookup"><span data-stu-id="8b8a3-121">Because special depreciation allowances are often unknown until later in the service life of the fixed asset, it's best to use this type of depreciation with a book that doesn't post to the general ledger.</span></span> <span data-ttu-id="8b8a3-122">Használhatja a Főkönyvbe fel nem adott tranzakciók törlése időszakos funkciót ezen könyvek előzménytranzakcióinak törléséhez.</span><span class="sxs-lookup"><span data-stu-id="8b8a3-122">You can use the Delete transactions not posted to general ledger periodic function to delete the transaction history for these books.</span></span> <span data-ttu-id="8b8a3-123">Törölheti a tárgyieszköz-könyv értékcsökkenési előzményeit, feladhatja a különleges értékcsökkenési keretet (amikor ismert), valamint feladhatja az adott évre fennmaradó értékcsökkenési tranzakciókat.</span><span class="sxs-lookup"><span data-stu-id="8b8a3-123">You can then delete the depreciation history for the fixed asset book, post the special depreciation allowance when it's known, and then post the remaining depreciation transactions for the year.</span></span> 

<span data-ttu-id="8b8a3-124">A létrehozható különleges értékcsökkenési keretekre vonatkozó rekordok száma korlátlan.</span><span class="sxs-lookup"><span data-stu-id="8b8a3-124">You can create an unlimited number of special depreciation allowance records.</span></span> <span data-ttu-id="8b8a3-125">Miután egy eszközcsoport könyvéhez társította a rekordokat, a program alkalmazza őket az eszköz könyvére.</span><span class="sxs-lookup"><span data-stu-id="8b8a3-125">After you assign those records to an asset group book, they are applied to the asset book.</span></span> 

<span data-ttu-id="8b8a3-126">A különleges értékcsökkenési keretet százalékként vagy rögzített összegként kell megadni.</span><span class="sxs-lookup"><span data-stu-id="8b8a3-126">A special depreciation allowance is entered as either a percentage or a fixed amount.</span></span> <span data-ttu-id="8b8a3-127">Ha értékcsökkenési javaslatot ad fel, akkor a program az értékcsökkenés tranzakcióitól különálló tranzakciókként adja fel a különleges értékcsökkenési keret tranzakcióit a könyvbe.</span><span class="sxs-lookup"><span data-stu-id="8b8a3-127">When you post depreciation proposals, special depreciation allowance transactions are posted to the book as transactions that are separate from the depreciation transactions.</span></span>

## <a name="depreciation-calendars"></a><span data-ttu-id="8b8a3-128"> Értékcsökkenési naptárak</span><span class="sxs-lookup"><span data-stu-id="8b8a3-128">Depreciation calendars</span></span>
<span data-ttu-id="8b8a3-129">Mindegyik könyvhöz tartozik egy, a tárgyi eszközök értékcsökkenésénél használt naptár.</span><span class="sxs-lookup"><span data-stu-id="8b8a3-129">Each book has a calendar that is used when you depreciate fixed assets.</span></span> <span data-ttu-id="8b8a3-130">A könyv a főkönyvi pénzügyi naptárat fogja használni alapértelmezés szerint, ha nem ad meg naptárat.</span><span class="sxs-lookup"><span data-stu-id="8b8a3-130">By default, if you don't indicate a calendar on the book, the book uses the ledger fiscal calendar.</span></span> <span data-ttu-id="8b8a3-131">Ha a könyvhöz kapcsolt értékcsökkenési profil pénzügyi értékcsökkenési évet használ, ki kell választani egy pénzügyi naptárat a könyvhöz.</span><span class="sxs-lookup"><span data-stu-id="8b8a3-131">You must select a fiscal calendar for a book when the depreciation profile that is associated with the book uses a fiscal depreciation year.</span></span> 

<span data-ttu-id="8b8a3-132">A Főkönyvben a **Pénzügyi naptárak** lapon megosztott naptárakat hozhat létre.</span><span class="sxs-lookup"><span data-stu-id="8b8a3-132">You can create shared calendars by using the **Fiscal calendars** page in General ledger.</span></span>

<span data-ttu-id="8b8a3-133">További tudnivalókért lásd: [Értékcsökkenési módszerek és szabályok](depreciation-methods-conventions.md).</span><span class="sxs-lookup"><span data-stu-id="8b8a3-133">For more informations, see [Depreciation methods and conventions](depreciation-methods-conventions.md).</span></span>



