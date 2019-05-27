---
title: SEPA beszedési megbízás beállítása
description: Az egységes eurófizetési térség (SEPA) beszedési megbízással a hitelező pénzt szedhet be a vevő bankszámlájáról, feltéve , ha a vevő aláírt meghatalmazást adott a hitelezőnek.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 01/12/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustParameters
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 59491
ms.assetid: 653a135f-c515-4ae3-9da2-82b5e1f103b5
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 757f3f6e0c5443054d2d6bd21381d9f692e1b9a5
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2019
ms.locfileid: "1565183"
---
# <a name="set-up-sepa-direct-debit-mandate"></a><span data-ttu-id="42c1a-103">SEPA beszedési megbízás beállítása</span><span class="sxs-lookup"><span data-stu-id="42c1a-103">Set up SEPA direct debit mandate</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="42c1a-104">Az egységes eurófizetési térség (SEPA) beszedési megbízással a hitelező pénzt szedhet be a vevő bankszámlájáról, feltéve , ha a vevő aláírt meghatalmazást adott a hitelezőnek.</span><span class="sxs-lookup"><span data-stu-id="42c1a-104">A Single Euro Payment Area (SEPA) direct debit lets a creditor collect funds from a customer's bank account, provided that the customer has granted a signed mandate to the creditor.</span></span> <span data-ttu-id="42c1a-105">A rendelet, amit a vevő aláírás engedélyez egy hitelezőnek, hogy gyűjtse össze a fizetéstést és utasítja a vevő bankját a beszedés kifizetésére.</span><span class="sxs-lookup"><span data-stu-id="42c1a-105">The mandate that the customer signs authorizes the creditor to collect a payment and instructs the customer's bank to pay the collection.</span></span> <span data-ttu-id="42c1a-106">A témakör célja, hogy bemutassa a SEPA beszedési megbízási felhatalmazások beállításának folyamatát.</span><span class="sxs-lookup"><span data-stu-id="42c1a-106">This topic is organized to show the process for setting up SEPA direct debit mandates.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="42c1a-107">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="42c1a-107">Prerequisites</span></span>
<span data-ttu-id="42c1a-108">Az alábbi táblázat bemutatja a munka megkezdése előtt biztosítandó előfeltételeket.</span><span class="sxs-lookup"><span data-stu-id="42c1a-108">The following table shows the prerequisites that must be in place before you start.</span></span>

| <span data-ttu-id="42c1a-109">Kategória</span><span class="sxs-lookup"><span data-stu-id="42c1a-109">Category</span></span>       | <span data-ttu-id="42c1a-110">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="42c1a-110">Prerequisite</span></span>                                                                                                                                              |
|----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="42c1a-111">Ország/régió</span><span class="sxs-lookup"><span data-stu-id="42c1a-111">Country/region</span></span> | <span data-ttu-id="42c1a-112">A jogi személy elsődleges címének a következő ország/régió valamelyikében kell lennie: Ausztria, Belgium, Németország, Spanyolország, Franciaország, Olaszország vagy Hollandia.</span><span class="sxs-lookup"><span data-stu-id="42c1a-112">The primary address for the legal entity must be in the following countries/regions: Austria, Belgium, Germany, Spain, France, Italy, or the Netherlands.</span></span> |

1. <span data-ttu-id="42c1a-113">Állítson be egy számsorozatok a beszedési megbízásoktól. Minden egyes beszedési megbízásnak egyedi számmal kell rendelkeznie.</span><span class="sxs-lookup"><span data-stu-id="42c1a-113">Set up a number sequence for direct debit mandates Each direct debit mandate must have a unique number.</span></span> <span data-ttu-id="42c1a-114">A **Számsorozatok** oldalon a beszedési megbízási meghatalmazások számára számsorozatot hozhat létre.</span><span class="sxs-lookup"><span data-stu-id="42c1a-114">Use the **Number sequences** page to create a number sequence for direct debit mandates.</span></span> <span data-ttu-id="42c1a-115">Ezzel az azonosítóval rendelheti hozzá a számsorozatot a beszedési megbízási felhatalmazás rendszeréhez a **Fiók Kinnlevőségek paraméterei** képernyőn.</span><span class="sxs-lookup"><span data-stu-id="42c1a-115">You will use this identifier to assign the number sequence to the direct debit mandate system on the **Accounts receivable parameters** page.</span></span>

2. <span data-ttu-id="42c1a-116">A beszedési megbízási meghatalmazásokhoz tartozó Kinnlevőségek modul paramétereinek beállítása Használja a **Kinnlevőségek paraméterei** oldalt a beszedési megbízási felhatalmazások paramétereinek beállítására.</span><span class="sxs-lookup"><span data-stu-id="42c1a-116">Set up Accounts receivable parameters for direct debit mandates Use the **Accounts receivable parameters** page to set up parameters for direct debit mandates.</span></span> <span data-ttu-id="42c1a-117">A paraméterek beállításához a **Beszedési megbízás** lapon módosítsa az alapértelmezett paramétereket igény szerint.</span><span class="sxs-lookup"><span data-stu-id="42c1a-117">To set up the parameters, on the **Direct debit** tab, change the default parameters as you require.</span></span> <span data-ttu-id="42c1a-118">Ezt követően, a **Számsorozatok** lapon frissítse a **Beszedési megbízási felhatalmazás azonosítója** mezőt a korábban megadott számsorozattal.</span><span class="sxs-lookup"><span data-stu-id="42c1a-118">Then, on the **Number sequences** tab, update the **Direct debit mandate ID** field with the number sequence that you set up earlier.</span></span>

3. <span data-ttu-id="42c1a-119">A beszedési megbízási felhatalmazások fizetési mód beállítása – A beszedési megbízási meghatalmazásokhoz fizetési módot is be kell állítani.</span><span class="sxs-lookup"><span data-stu-id="42c1a-119">Set up a method of payment for direct debit mandates You must set up a method of payment for direct debit mandates.</span></span> <span data-ttu-id="42c1a-120">Ezt a fizetési módot használhatja azon számlák lekérdezéseihez, amelyekhez beszedési megbízásos kifizetést kíván létrehozni.</span><span class="sxs-lookup"><span data-stu-id="42c1a-120">You use this method of payment to query for invoices to generate direct debit payments for.</span></span> <span data-ttu-id="42c1a-121">Hasznélja a **Fizetési módszerek** lapot a fizetési módszerek beállításához.</span><span class="sxs-lookup"><span data-stu-id="42c1a-121">Use the **Methods of payment** page to set up the method of payment.</span></span> <span data-ttu-id="42c1a-122">A beszedési megbízási felhatalmazások fizetési mód beállításához be kell tartani a fizetési mód következő lépéseit:</span><span class="sxs-lookup"><span data-stu-id="42c1a-122">To set up a method of payment for direct debit mandates, you must follow these additional steps for a method of payment:</span></span>

-   <span data-ttu-id="42c1a-123">A **Fizetés típus** mezőben válassza ki az **Elektronikus fizetés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="42c1a-123">In the **Payment type** field, select **Electronic payment**.</span></span>
-   <span data-ttu-id="42c1a-124">Opcionális lépés: Ha valószínűsíti, hogy vevői egynél több beszedési megbízást fognak fenntartani, akkor az **Időszak** mezőben a **Számla** beállítást válassza.</span><span class="sxs-lookup"><span data-stu-id="42c1a-124">Optional: If you expect each of your customers to have multiple mandates, in the **Period** field, select **Invoice**.</span></span> <span data-ttu-id="42c1a-125">Ez minden számlához külön kifizetést hoz létre, és minden kifizetés a számlában meghatározott meghatalmazást használja.</span><span class="sxs-lookup"><span data-stu-id="42c1a-125">A separate payment will be created for each invoice, and each payment will use the mandate that is specified for the invoice.</span></span>
-   <span data-ttu-id="42c1a-126">Válassza ki a **Felhatalmazás igénylése** lehetőséget a beszedési megbízási felhatalmazások használata által a kifizetések létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="42c1a-126">Select the **Require mandate** option to create payments by using direct debit mandates.</span></span> <span data-ttu-id="42c1a-127">A **Felhatalmazás igénylése** lehetőség csak akkor érhető el, ha az **Elektronikus fizetés** be van jelölve a **Fizetés típusa** mezőben.</span><span class="sxs-lookup"><span data-stu-id="42c1a-127">The **Require mandate** option is available only if you select **Electronic payment** in the **Payment type** field.</span></span>

<span data-ttu-id="42c1a-128">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="42c1a-128">Additional resources</span></span>

[<span data-ttu-id="42c1a-129">Beszedési megbízás – áttekintés</span><span class="sxs-lookup"><span data-stu-id="42c1a-129">Direct debit overview</span></span>](sepa-direct-debit-overview.md) 

[<span data-ttu-id="42c1a-130">Beszedési megbízási felhatalmazás létrehozása vevő részére</span><span class="sxs-lookup"><span data-stu-id="42c1a-130">Create a direct debit mandate for a customer</span></span>](tasks/create-direct-debit-mandate-customer.md) 

