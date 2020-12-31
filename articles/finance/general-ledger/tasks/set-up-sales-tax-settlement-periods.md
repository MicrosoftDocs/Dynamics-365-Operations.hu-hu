---
title: Áfafizetési időszakok beállítása
description: Ez a témakör bemutatja, hogyan állítsuk be az áfakiegyenlítési időszakokat a Dynamics 365 Finance szolgáltatásban.
author: twheeloc
manager: AnnBe
ms.date: 08/05/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxPeriod
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e5068c121e921c1586dc6ae003c0021bf41d2254
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4443983"
---
# <a name="set-up-sales-tax-settlement-periods"></a><span data-ttu-id="38cae-103">Áfafizetési időszakok beállítása</span><span class="sxs-lookup"><span data-stu-id="38cae-103">Set up sales tax settlement periods</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="38cae-104">Ez a témakör bemutatja, hogyan állítsuk be az áfakiegyenlítési időszakokat.</span><span class="sxs-lookup"><span data-stu-id="38cae-104">This topic explains how to set up sales tax settlement periods.</span></span> <span data-ttu-id="38cae-105">Az Áfakiegyenlítési időszakok információval rendelkeznek a periódusokról, hogy melyik áfát kell jelenteni és fizetni.</span><span class="sxs-lookup"><span data-stu-id="38cae-105">Sales tax settlement periods contain information about the period intervals for which sales tax needs to be reported and paid.</span></span> <span data-ttu-id="38cae-106">Egy kiegyenlítési folyamat futtatható egy kiegyenlítési időszak megadott intervallumában.</span><span class="sxs-lookup"><span data-stu-id="38cae-106">A settlement process can be run for a settlement period for a specific date interval.</span></span> <span data-ttu-id="38cae-107">Minden kiegyenlítési időszakhoz rendelt adókód kiegyenlítésre kerül.</span><span class="sxs-lookup"><span data-stu-id="38cae-107">All tax codes associated with the settlement period will be settled.</span></span> <span data-ttu-id="38cae-108">Az érintett Adóhatóság beállításaitól függően az adókötelezettség feladásra kerül a szállítóhoz vagy a Főkönyvi számlához.</span><span class="sxs-lookup"><span data-stu-id="38cae-108">Depending on the set up of the related Sales tax authority, the tax liability is posted either to a vendor or a General ledger account.</span></span>

<span data-ttu-id="38cae-109">Ez a feladat az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="38cae-109">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="38cae-110">A Navigációs ablaktáblán lépjen a **Modulok > Adó > Közvetett adók > Áfa > Áfakiegyenlítési időszakok** elemre.</span><span class="sxs-lookup"><span data-stu-id="38cae-110">In the navigation pane, go to **Modules > Tax > Indirect taxes > Sales tax > Sales tax settlement periods**.</span></span>
2. <span data-ttu-id="38cae-111">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="38cae-111">Select **New**.</span></span>
3. <span data-ttu-id="38cae-112">Írjon be egy értéket a **Kiegyenlítési időszak** meghatározása mezőbe.</span><span class="sxs-lookup"><span data-stu-id="38cae-112">In the **Settlement period** field, type a value.</span></span>
4. <span data-ttu-id="38cae-113">Írjon egy értéket a **Leírás** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="38cae-113">In the **Description** field, type a value.</span></span>
5. <span data-ttu-id="38cae-114">A **Hatóság mezőben** válassza ki azt az adóhatóságot, amely a kifizetési időszakhoz létrehozott jelentéseket és kifizetéseket kapja.</span><span class="sxs-lookup"><span data-stu-id="38cae-114">In the **Authority** field, select the sales tax authority that receives the reports and the payments that are created for the settlement period.</span></span>
6. <span data-ttu-id="38cae-115">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="38cae-115">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="38cae-116">A **Fizetési feltételek** mezőben válassza ki a kívánt rekordot a legördülő menüből.</span><span class="sxs-lookup"><span data-stu-id="38cae-116">In the **Terms of payment** field, select the desired record in the drop-down menu.</span></span> <span data-ttu-id="38cae-117">Az érintett Adóhatóság beállítható szállítóként és az Áfakiegyenlítés nyitott szállítói számlát hoz létre.</span><span class="sxs-lookup"><span data-stu-id="38cae-117">The related Sales tax authority can be set up as a vendor and the Sales tax settlement will create an open vendor invoice.</span></span> <span data-ttu-id="38cae-118">A Fizetés feltételei meghatározzák a Határidőt nyitott szállítói számla esetén.</span><span class="sxs-lookup"><span data-stu-id="38cae-118">The Terms of payment defines the Due date for the open vendor invoice.</span></span>  
8. <span data-ttu-id="38cae-119">Válasszon a kiegyenlítési időszakok időtartamaihoz egy típust.</span><span class="sxs-lookup"><span data-stu-id="38cae-119">Select a type for the settlement period intervals.</span></span>
9. <span data-ttu-id="38cae-120">Adja meg a Periódus időtartam egységek periódusokra vonatkoztatott számát.</span><span class="sxs-lookup"><span data-stu-id="38cae-120">Enter the number of Period interval units per period.</span></span> <span data-ttu-id="38cae-121">Például egy negyedév 3 hónapból áll.</span><span class="sxs-lookup"><span data-stu-id="38cae-121">For example, a quarter has 3 months.</span></span>
10. <span data-ttu-id="38cae-122">Jelölje be, vagy törölje a **Kötegelt feldolgozás használata az áfa kiegyenlítéséhez** jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="38cae-122">Select or clear the **Use batch processing for sales tax settlement** check box.</span></span> <span data-ttu-id="38cae-123">A kiegyenlítési időszakhoz tartozó kiegyenlítési folyamat kötegelt feladatként feldolgozható a háttérben.</span><span class="sxs-lookup"><span data-stu-id="38cae-123">The settlement process for the settlement period can be processed as batch job in the background.</span></span> <span data-ttu-id="38cae-124">Ez adott időszakban nagyszámú adótranzakcióhoz ajánlott.</span><span class="sxs-lookup"><span data-stu-id="38cae-124">This is recommended for a large number of tax transactions within a period interval.</span></span>  
    > [!NOTE]
    > <span data-ttu-id="38cae-125">Jelenleg nem támogatott Spanyolországban, Japánban és Hollandiában.</span><span class="sxs-lookup"><span data-stu-id="38cae-125">Currently this is not supported in Spain, Japan, and the Netherlands.</span></span>
11. <span data-ttu-id="38cae-126">Válassza ki, vagy törölje a jelölést **Az ellenoldali adótranzakciók létrehozásának megakadályozása**  jelölőnégyzetből.</span><span class="sxs-lookup"><span data-stu-id="38cae-126">Select or clear the **Prevent generating offset tax transactions** check box.</span></span> <span data-ttu-id="38cae-127">Alapértelmezés szerint a rendszer létrehozza az ellenoldali adótranzakciókat a kiegyenlítési folyamat során, amely teljesítményproblémákat, okozhat ha nagy számú adótranzakciók van egy időintervallumon belül.</span><span class="sxs-lookup"><span data-stu-id="38cae-127">By default, the system generates offset tax transactions during the settlement process, which cause can performance issue if there are a large number of tax transactions within a period interval.</span></span> <span data-ttu-id="38cae-128">Jelölje be ezt a jelölőnégyzetet ellenoldali adótranzakciók létrehozásának megakadályozásához.</span><span class="sxs-lookup"><span data-stu-id="38cae-128">Select this check box to prevent generating offset tax transactions.</span></span>
12. <span data-ttu-id="38cae-129">Bontsa ki az **Időszak időtartamai** fület.</span><span class="sxs-lookup"><span data-stu-id="38cae-129">Expand the **Period intervals** tab.</span></span>
13. <span data-ttu-id="38cae-130">Válassza a **Hozzáadás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="38cae-130">Select **Add**.</span></span>
14. <span data-ttu-id="38cae-131">A **Kezdő dátum** mező új sorában adja meg a dátumot.</span><span class="sxs-lookup"><span data-stu-id="38cae-131">In the **From date** field in the new row, enter a date.</span></span>
15. <span data-ttu-id="38cae-132">Adjon meg egy dátumot a **Záró dátum** mezőben.</span><span class="sxs-lookup"><span data-stu-id="38cae-132">In the **To date** field, enter a date.</span></span>
16. <span data-ttu-id="38cae-133">Válassza ki az **Új időszak intervalluma** elemet.</span><span class="sxs-lookup"><span data-stu-id="38cae-133">Select **New period interval**.</span></span> <span data-ttu-id="38cae-134">Amint megadta az első intervallumot az új időszakok automatikusan létrejönnek.</span><span class="sxs-lookup"><span data-stu-id="38cae-134">Once the first period interval has been entered, new periods can be created automatically.</span></span> <span data-ttu-id="38cae-135">Visszatérhet és szükség szerint új intervallumokat adhat hozzá.</span><span class="sxs-lookup"><span data-stu-id="38cae-135">You can come back and add new period intervals as required.</span></span>  
17. <span data-ttu-id="38cae-136">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="38cae-136">Close the page.</span></span>

