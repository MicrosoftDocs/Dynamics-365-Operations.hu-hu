---
title: "SEPA beszedési megbízás beállítása"
description: 
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 59491
ms.assetid: 653a135f-c515-4ae3-9da2-82b5e1f103b5
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 8b50c2d585c7e0bcd8dc15aa70446cd7346ad33c
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---

# <a name="set-up-sepa-direct-debit-mandate"></a><span data-ttu-id="d4592-102">SEPA beszedési megbízás beállítása</span><span class="sxs-lookup"><span data-stu-id="d4592-102">Set up SEPA direct debit mandate</span></span>

[!include[banner](../includes/banner.md)]




<span data-ttu-id="d4592-103">Az egységes eurófizetési térség (SEPA) beszedési megbízással a hitelező pénzt szedhet be a vevő bankszámlájáról, feltéve , ha a vevő aláírt meghatalmazást adott a hitelezőnek.</span><span class="sxs-lookup"><span data-stu-id="d4592-103">A Single Euro Payment Area (SEPA) direct debit lets a creditor collect funds from a customer's bank account, provided that the customer has granted a signed mandate to the creditor.</span></span> <span data-ttu-id="d4592-104">A rendelet, amit a vevő aláírás engedélyez egy hitelezőnek, hogy gyűjtse össze a fizetéstést és utasítja a vevő bankját a beszedés kifizetésére.</span><span class="sxs-lookup"><span data-stu-id="d4592-104">The mandate that the customer signs authorizes the creditor to collect a payment and instructs the customer's bank to pay the collection.</span></span> <span data-ttu-id="d4592-105">A témakör célja, hogy bemutassa a SEPA beszedési megbízási felhatalmazások beállításának folyamatát.</span><span class="sxs-lookup"><span data-stu-id="d4592-105">This topic is organized to show the process for setting up SEPA direct debit mandates.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d4592-106">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="d4592-106">Prerequisites</span></span>
<span data-ttu-id="d4592-107">Az alábbi táblázat bemutatja a munka megkezdése előtt biztosítandó előfeltételeket.</span><span class="sxs-lookup"><span data-stu-id="d4592-107">The following table shows the prerequisites that must be in place before you start.</span></span>

| <span data-ttu-id="d4592-108">Kategória</span><span class="sxs-lookup"><span data-stu-id="d4592-108">Category</span></span>       | <span data-ttu-id="d4592-109">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="d4592-109">Prerequisite</span></span>                                                                                                                                              |
|----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="d4592-110">Ország/régió</span><span class="sxs-lookup"><span data-stu-id="d4592-110">Country/region</span></span> | <span data-ttu-id="d4592-111">A jogi személy elsődleges címének a következő ország/régió valamelyikében kell lennie: Ausztria, Belgium, Németország, Spanyolország, Franciaország, Olaszország vagy Hollandia.</span><span class="sxs-lookup"><span data-stu-id="d4592-111">The primary address for the legal entity must be in the following countries/regions: Austria, Belgium, Germany, Spain, France, Italy, or the Netherlands.</span></span> |

1. <span data-ttu-id="d4592-112">Állítson be egy számsorozatok a beszedési megbízásoktól. Minden egyes beszedési megbízásnak egyedi számmal kell rendelkeznie.</span><span class="sxs-lookup"><span data-stu-id="d4592-112">Set up a number sequence for direct debit mandates Each direct debit mandate must have a unique number.</span></span> <span data-ttu-id="d4592-113">A **Számsorozatok** oldalon a beszedési megbízási meghatalmazások számára számsorozatot hozhat létre.</span><span class="sxs-lookup"><span data-stu-id="d4592-113">Use the **Number sequences** page to create a number sequence for direct debit mandates.</span></span> <span data-ttu-id="d4592-114">Ezzel az azonosítóval rendelheti hozzá a számsorozatot a beszedési megbízási felhatalmazás rendszeréhez a **Fiók Kinnlevőségek paraméterei** képernyőn.</span><span class="sxs-lookup"><span data-stu-id="d4592-114">You will use this identifier to assign the number sequence to the direct debit mandate system on the **Accounts receivable parameters** page.</span></span>

2. <span data-ttu-id="d4592-115">A beszedési megbízási meghatalmazásokhoz tartozó Kinnlevőségek modul paramétereinek beállítása Használja a **Kinnlevőségek paraméterei** oldalt a beszedési megbízási felhatalmazások paramétereinek beállítására.</span><span class="sxs-lookup"><span data-stu-id="d4592-115">Set up Accounts receivable parameters for direct debit mandates Use the **Accounts receivable parameters** page to set up parameters for direct debit mandates.</span></span> <span data-ttu-id="d4592-116">A paraméterek beállításához a **Beszedési megbízás** lapon módosítsa az alapértelmezett paramétereket igény szerint.</span><span class="sxs-lookup"><span data-stu-id="d4592-116">To set up the parameters, on the **Direct debit** tab, change the default parameters as you require.</span></span> <span data-ttu-id="d4592-117">Ezt követően, a **Számsorozatok** lapon frissítse a **Beszedési megbízási felhatalmazás azonosítója** mezőt a korábban megadott számsorozattal.</span><span class="sxs-lookup"><span data-stu-id="d4592-117">Then, on the **Number sequences** tab, update the **Direct debit mandate ID** field with the number sequence that you set up earlier.</span></span>

3. <span data-ttu-id="d4592-118">A beszedési megbízási felhatalmazások fizetési mód beállítása – A beszedési megbízási meghatalmazásokhoz fizetési módot is be kell állítani.</span><span class="sxs-lookup"><span data-stu-id="d4592-118">Set up a method of payment for direct debit mandates You must set up a method of payment for direct debit mandates.</span></span> <span data-ttu-id="d4592-119">Ezt a fizetési módot használhatja azon számlák lekérdezéseihez, amelyekhez beszedési megbízásos kifizetést kíván létrehozni.</span><span class="sxs-lookup"><span data-stu-id="d4592-119">You use this method of payment to query for invoices to generate direct debit payments for.</span></span> <span data-ttu-id="d4592-120">Hasznélja a **Fizetési módszerek** lapot a fizetési módszerek beállításához.</span><span class="sxs-lookup"><span data-stu-id="d4592-120">Use the **Methods of payment** page to set up the method of payment.</span></span> <span data-ttu-id="d4592-121">A beszedési megbízási felhatalmazások fizetési mód beállításához be kell tartani a fizetési mód következő lépéseit:</span><span class="sxs-lookup"><span data-stu-id="d4592-121">To set up a method of payment for direct debit mandates, you must follow these additional steps for a method of payment:</span></span>

-   <span data-ttu-id="d4592-122">A **Fizetés típus** mezőben válassza ki az **Elektronikus fizetés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d4592-122">In the **Payment type** field, select **Electronic payment**.</span></span>
-   <span data-ttu-id="d4592-123">Opcionális lépés: Ha valószínűsíti, hogy vevői egynél több beszedési megbízást fognak fenntartani, akkor az **Időszak** mezőben a **Számla** beállítást válassza.</span><span class="sxs-lookup"><span data-stu-id="d4592-123">Optional: If you expect each of your customers to have multiple mandates, in the **Period** field, select **Invoice**.</span></span> <span data-ttu-id="d4592-124">Ez minden számlához külön kifizetést hoz létre, és minden kifizetés a számlában meghatározott meghatalmazást használja.</span><span class="sxs-lookup"><span data-stu-id="d4592-124">A separate payment will be created for each invoice, and each payment will use the mandate that is specified for the invoice.</span></span>
-   <span data-ttu-id="d4592-125">Válassza ki a **Felhatalmazás igénylése** lehetőséget a beszedési megbízási felhatalmazások használata által a kifizetések létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="d4592-125">Select the **Require mandate** option to create payments by using direct debit mandates.</span></span> <span data-ttu-id="d4592-126">A **Felhatalmazás igénylése** lehetőség csak akkor érhető el, ha az **Elektronikus fizetés** be van jelölve a **Fizetés típusa** mezőben.</span><span class="sxs-lookup"><span data-stu-id="d4592-126">The **Require mandate** option is available only if you select **Electronic payment** in the **Payment type** field.</span></span>

<span data-ttu-id="d4592-127">Lásd még</span><span class="sxs-lookup"><span data-stu-id="d4592-127">See Also</span></span>

[<span data-ttu-id="d4592-128">Beszedési megbízás – áttekintés</span><span class="sxs-lookup"><span data-stu-id="d4592-128">Direct debit overview</span></span>](sepa-direct-debit-overview.md) 

[<span data-ttu-id="d4592-129">Beszedési megbízási felhatalmazás létrehozása vevő részére</span><span class="sxs-lookup"><span data-stu-id="d4592-129">Create a direct debit mandate for a customer</span></span>](tasks/create-direct-debit-mandate-customer.md) 


