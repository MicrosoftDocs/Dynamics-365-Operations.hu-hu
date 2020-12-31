---
title: Állítsa be és dolgozza fel az ismétlődő számlákat
description: Ez a cikk ismerteti az ismétlődő számlák beállítását és feldolgozását. Használhat ismétlődő számlákat, amennyiben a vevők részére rendszeresen azonos összegű számlákat kell kiállítania.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustInvoiceTemplate
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 14011
ms.assetid: 9cc37003-adf1-413d-b2b2-2badcf512e3b
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4b443630d1612b5095fefa74b5ed6d057be534b7
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4443876"
---
# <a name="set-up-and-process-recurring-invoices"></a><span data-ttu-id="19249-104">Állítsa be és dolgozza fel az ismétlődő számlákat</span><span class="sxs-lookup"><span data-stu-id="19249-104">Set up and process recurring invoices</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="19249-105">Ez a cikk ismerteti az ismétlődő számlák beállítását és feldolgozását.</span><span class="sxs-lookup"><span data-stu-id="19249-105">This article explains how to set up and process recurring invoices.</span></span> <span data-ttu-id="19249-106">Használhat ismétlődő számlákat, amennyiben a vevők részére rendszeresen azonos összegű számlákat kell kiállítania.</span><span class="sxs-lookup"><span data-stu-id="19249-106">You can use recurring invoices if you must invoice customers for the same amount on a regular basis.</span></span>

<a name="create-a-recurring-free-text-invoice-template"></a><span data-ttu-id="19249-107">Ismétlődő szabadszöveges számlák sablonjának létrehozása</span><span class="sxs-lookup"><span data-stu-id="19249-107">Create a recurring free text invoice template</span></span>
---------------------------------------------

<span data-ttu-id="19249-108">Vevőknek rendszeres, ugyanazon szolgáltatások számlázásához, hozzon lére szabadszöveges számlasablont, amelyet újra lehet használni további számlák létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="19249-108">To invoice customers for the same services on a regular basis, you must define a free text invoice template that can be reused to create the invoices.</span></span> <span data-ttu-id="19249-109">Ez a sablon a következő információkat tartalmazza:</span><span class="sxs-lookup"><span data-stu-id="19249-109">This template contains the following information:</span></span>

-   <span data-ttu-id="19249-110">Fejlécadatok, például az adócsoportok, fizetési feltételeket és fizetési mód</span><span class="sxs-lookup"><span data-stu-id="19249-110">Header information, such as tax groups, terms of payment, and the method of payment</span></span>
-   <span data-ttu-id="19249-111">Soradatok, például a szolgáltatásleírás, a bevételi számlák, az egységár és a számla összege</span><span class="sxs-lookup"><span data-stu-id="19249-111">Line information, such as the service description, revenue accounts, unit price, and invoice amount</span></span>
-   <span data-ttu-id="19249-112">Szállítási és kezelési költségek</span><span class="sxs-lookup"><span data-stu-id="19249-112">Charges for shipping or handling</span></span>
-   <span data-ttu-id="19249-113">Könyvelési felosztások a pénzügyi dimenzió adataival, például a költséghelyek és az üzleti egységek</span><span class="sxs-lookup"><span data-stu-id="19249-113">Accounting distributions together with financial dimension information, such as cost centers and business units</span></span>

<span data-ttu-id="19249-114">Így létrehoz egy teljes számlát és sablonként menti el.</span><span class="sxs-lookup"><span data-stu-id="19249-114">In effect, you're creating an entire invoice and saving it as a template.</span></span> <span data-ttu-id="19249-115">A sablonokat beállíthatja az **Ismétlődő számlák** oldalon.</span><span class="sxs-lookup"><span data-stu-id="19249-115">You can set up the templates using the **Recurring invoices** page.</span></span>

## <a name="assign-a-free-text-invoice-template-to-a-customer-and-enter-recurrence-details"></a><span data-ttu-id="19249-116">Szabadszöveges számlasablon hozzárendelése vevőhöz és az ismétlődés részleteinek megadása</span><span class="sxs-lookup"><span data-stu-id="19249-116">Assign a free text invoice template to a customer and enter recurrence details</span></span>
<span data-ttu-id="19249-117">A sablon létrehozása után hozzárendelni kell a sablont a számlázandó vevőhöz.</span><span class="sxs-lookup"><span data-stu-id="19249-117">After the template is created, you must assign the template to the customers that you want to invoice.</span></span> <span data-ttu-id="19249-118">Ezenkívül meg kell adnia, mikor és milyen gyakran lesz a számla használva.</span><span class="sxs-lookup"><span data-stu-id="19249-118">Additionally, you must specify when and how often the invoice will be used.</span></span> <span data-ttu-id="19249-119">A sablonokat hozzárendelheti a **Vevők** oldal **Számla** lapjá .</span><span class="sxs-lookup"><span data-stu-id="19249-119">You can assign the templates on the **Invoice** tab of the **Customers** page.</span></span> <span data-ttu-id="19249-120">Adja hozzá a sablont a listához, és frissítése a következő adatokat:</span><span class="sxs-lookup"><span data-stu-id="19249-120">Add the template to the list, and update the following information:</span></span>

-   <span data-ttu-id="19249-121">A kezdő dátum, illetve az ismétlődő számlázás záró dátuma</span><span class="sxs-lookup"><span data-stu-id="19249-121">The start date and, optionally, the end date for the recurring billing</span></span>
-   <span data-ttu-id="19249-122">Az ismétlődő számlázás gyakorisága (például minden nap vagy havonta egyszer)</span><span class="sxs-lookup"><span data-stu-id="19249-122">The frequency of the recurring billing (for example, every day or once a month)</span></span>
-   <span data-ttu-id="19249-123">A maximális számlázási összeg (ha ezt az információt kötelező megadni)</span><span class="sxs-lookup"><span data-stu-id="19249-123">The maximum billing amount (if this information is required)</span></span>

<span data-ttu-id="19249-124">Egy vevőnek lehet több, eltérő gyakorisággal rendelkező sablonja.</span><span class="sxs-lookup"><span data-stu-id="19249-124">A customer can have multiple templates that have different frequencies.</span></span>

## <a name="generate-the-recurring-invoices"></a><span data-ttu-id="19249-125">Az ismétlődő számlák létrehozása</span><span class="sxs-lookup"><span data-stu-id="19249-125">Generate the recurring invoices</span></span>
<span data-ttu-id="19249-126">Az **ismétlődő számlák** oldalon van egy olyan feladat, amely az ismétlődő számlasablonokat dolgozza fel.</span><span class="sxs-lookup"><span data-stu-id="19249-126">On the **Recurring invoices** page, there is a task that processes recurring invoice templates.</span></span> <span data-ttu-id="19249-127">Meghatározhatja a számla dátumát és a sablont a számlák létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="19249-127">You specify the invoice date and the template to generate the invoices from.</span></span> <span data-ttu-id="19249-128">A számlák létrejönnek és feldolgozott minden számlacsoporthoz egy ismétlődő azonosítószám rendelődik.</span><span class="sxs-lookup"><span data-stu-id="19249-128">Invoices will be generated and assigned a single recurrence ID number for each group of invoices that is processed.</span></span>

<a name="post-recurring-free-text-invoices"></a><span data-ttu-id="19249-129">Szabadszöveges ismétlődő számlák feladása</span><span class="sxs-lookup"><span data-stu-id="19249-129">Post recurring free text invoices</span></span>
---------------------------------

<span data-ttu-id="19249-130">Ismétlődő számlák generálása után a számla ismétlődés azonosító jelenik meg a feladási feladatban az **Ismétlődő számlák** oldalon.</span><span class="sxs-lookup"><span data-stu-id="19249-130">After recurring invoices are generated, the invoice recurrence IDs appear in a posting task on the **Recurring invoices** page.</span></span> <span data-ttu-id="19249-131">Megtekintheti az ismétlődés azonosító összes számláját a hivatkozásra kattintva.</span><span class="sxs-lookup"><span data-stu-id="19249-131">You can view all of the invoices for a recurrence ID by clicking the link.</span></span> <span data-ttu-id="19249-132">Az ismétlődés azonosító számláiak ellenőrzése során törölheti az egyes számlákat.</span><span class="sxs-lookup"><span data-stu-id="19249-132">During your review of the invoices for the recurrence ID, you can delete individual invoices.</span></span> <span data-ttu-id="19249-133">A vevő ismétlődési beállításai a sablon beállításaira áll, így azt újra lehet generálni később.</span><span class="sxs-lookup"><span data-stu-id="19249-133">The customer's recurrence settings will be reset for that template, so that it can be regenerated later.</span></span> <span data-ttu-id="19249-134">Feladhat egy, több, vagy az összes ismétlődés azonosítót.</span><span class="sxs-lookup"><span data-stu-id="19249-134">You can post one, many, or all of the invoices for a recurrence ID.</span></span> <span data-ttu-id="19249-135">Ha engedélyezve vannak a munkafolyamatok, rá kell kattintania **Küldés** lehetőségre a számlák feladása előtt.</span><span class="sxs-lookup"><span data-stu-id="19249-135">If workflows are enabled, you must click **Submit** before you can post the invoices.</span></span>

<a name="print-recurring-free-text-invoices"></a><span data-ttu-id="19249-136">Szabadszöveges ismétlődő számlák nyomtatása</span><span class="sxs-lookup"><span data-stu-id="19249-136">Print recurring free text invoices</span></span>
----------------------------------

<span data-ttu-id="19249-137">Ismétlődő számlák feladása után, kinyomtathatja a számlákat a szabadszöveges számla listaoldalról.</span><span class="sxs-lookup"><span data-stu-id="19249-137">After recurring invoices are posted, you can print the invoices from the free text invoice list page.</span></span> <span data-ttu-id="19249-138">A kijelölt számlákat ki lehet nyomtatni, vagy kiválaszthat egy számlatartományt nyomtatásra.</span><span class="sxs-lookup"><span data-stu-id="19249-138">You can print the invoices that are selected, or you can select a range of invoices to print.</span></span>



