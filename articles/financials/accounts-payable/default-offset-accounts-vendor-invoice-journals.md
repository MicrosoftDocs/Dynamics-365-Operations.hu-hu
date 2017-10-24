---
title: "Alapértelmezett ellenszámlák szállítóiszámla-naplók és számla-jóváhagyási naplók"
description: 
author: ShivamPandey-msft
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 62093
ms.assetid: 553933ca-928d-4031-bb8c-f9cff458320b
ms.search.region: global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: c2b62eafc71b5d1ad4eaaf252efd1dcbb97b86f3
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---

# <a name="default-offset-accounts-for-vendor-invoice-journals-and-invoice-approval-journals"></a><span data-ttu-id="638a8-102">Alapértelmezett ellenszámlák szállítóiszámla-naplók és számla-jóváhagyási naplók</span><span class="sxs-lookup"><span data-stu-id="638a8-102">Default offset accounts for vendor invoice journals and invoice approval journals</span></span>

[!include[banner](../includes/banner.md)]




<span data-ttu-id="638a8-103">Az alapértelmezett ellenszámlák a következő szállítói számla naplóoldalakon használatosak:</span><span class="sxs-lookup"><span data-stu-id="638a8-103">Default offset accounts are used on the following vendor invoice journal pages:</span></span>

-   <span data-ttu-id="638a8-104">Számlanapló</span><span class="sxs-lookup"><span data-stu-id="638a8-104">Invoice journal</span></span>
-   <span data-ttu-id="638a8-105">Számla-jóváhagyási napló</span><span class="sxs-lookup"><span data-stu-id="638a8-105">Invoice approval journal</span></span>

<span data-ttu-id="638a8-106">Az alábbi táblázat segítségével eldöntheti, hogy hová rendelje hozzá az alapértelmezett számlákat a számlanaplókhoz.</span><span class="sxs-lookup"><span data-stu-id="638a8-106">Use the following table to help decide where you should assign default accounts for invoice journals.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="638a8-107">Alapértelmezett számlák beállítása itt</span><span class="sxs-lookup"><span data-stu-id="638a8-107">Set up default accounts here</span></span></th>
<th><span data-ttu-id="638a8-108">Hol vannak az alapértelmezett számlák</span><span class="sxs-lookup"><span data-stu-id="638a8-108">Where default accounts are provided</span></span></th>
<th><span data-ttu-id="638a8-109">Hogyan befolyásolja ez a lehetőség a feldolgozást</span><span class="sxs-lookup"><span data-stu-id="638a8-109">How this option affects processing</span></span></th>
<th><span data-ttu-id="638a8-110">Mikor kell használni ezt a lehetőséget</span><span class="sxs-lookup"><span data-stu-id="638a8-110">When you should use this option</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="638a8-111"><strong>Szállítócsoport</strong> – Állítsa be az alapértelmezett ellenszámlákat a szállítócsoportoknak az <strong>Alapértelmezett számla beállítása</strong> lapon, amelyet a <strong>Szállítócsoportok</strong> oldalról tud megnyitni.</span><span class="sxs-lookup"><span data-stu-id="638a8-111"><strong>Vendor group</strong> – Set up default offset accounts for vendor groups on the <strong>Default account setup</strong> page, which you can open from the <strong>Vendor groups</strong> page.</span></span></td>
<td><ul>
<li><span data-ttu-id="638a8-112">Szállítói számla</span><span class="sxs-lookup"><span data-stu-id="638a8-112">Vendor account</span></span></li>
<li><span data-ttu-id="638a8-113">Naplóbejegyzések szállítói számlákhoz a szállítói csoportban, ha az alapértelmezett számlák nincsenek megadva a szállítói számlákhoz</span><span class="sxs-lookup"><span data-stu-id="638a8-113">Journal entries for vendor accounts in the vendor group, if default accounts aren’t specified for vendor accounts</span></span></li>
</ul></td>
<td><span data-ttu-id="638a8-114">Az alapértelmezett ellenszámlák szállítócsoportok számára szállítói alapértelmezett ellenszámlákként jelennek meg az <strong>Alapértelmezett számla beállítása</strong> oldalon.</span><span class="sxs-lookup"><span data-stu-id="638a8-114">The default offset accounts for vendor groups are shown as default offset accounts for vendors on the <strong>Default account setup</strong> page.</span></span> <span data-ttu-id="638a8-115">Ezt a lapot megnyithatja az <strong>Összes szállító</strong> listaoldaláról.</span><span class="sxs-lookup"><span data-stu-id="638a8-115">You can open this page from the <strong>All vendors</strong> list page.</span></span></td>
<td><span data-ttu-id="638a8-116">Ezt a lehetőséget akkor használja, ha általában azonos típusú elemeket szokott fizetni, azonos szállítói csoportok esetében.</span><span class="sxs-lookup"><span data-stu-id="638a8-116">Use this option if you typically pay for the same types of things from the same vendor groups over time.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="638a8-117"><strong>Szállítói számla</strong> – Állítsa be az alapértelmezett számlákat a szállítói számlákhoz az <strong>Alapértelmezett számla beállítása</strong> lapon, amelyet a <strong>Szállítók</strong> oldalról tud megnyitni.</span><span class="sxs-lookup"><span data-stu-id="638a8-117"><strong>Vendor account</strong> – Set up default accounts for vendor accounts on the <strong>Default account setup</strong> page, which you can open from the <strong>Vendors</strong> page.</span></span></td>
<td><span data-ttu-id="638a8-118">A szállítói számlához tartozó naplóbejegyzések</span><span class="sxs-lookup"><span data-stu-id="638a8-118">Journal entries for the vendor account</span></span></td>
<td><span data-ttu-id="638a8-119">A szállítói számlák alapértelmezett ellenszámlái alapértelmezett ellenszámlaként jelennek meg a naplóbejegyzésekben a szállítói számlánál.</span><span class="sxs-lookup"><span data-stu-id="638a8-119">The default offset accounts for vendor accounts are shown as default offset accounts for journal entries for the vendor account.</span></span></td>
<td><span data-ttu-id="638a8-120">Ezt a lehetőséget akkor használja, ha általában azonos típusú elemeket szokott fizetni, ugyanazoktól a szállítóktól.</span><span class="sxs-lookup"><span data-stu-id="638a8-120">Use this option if you typically pay for the same types of things from the same vendors over time.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="638a8-121"><strong>Naplónevek</strong> – Állítsa be az alapértelmezett ellenszámlákat a naplókhoz a <strong>Naplónevek</strong> oldalon.</span><span class="sxs-lookup"><span data-stu-id="638a8-121"><strong>Journal names</strong> – Set up default offset accounts for journals on the <strong>Journal names</strong> page.</span></span> <span data-ttu-id="638a8-122">Válassza ki a <strong>Rögzített ellenszámla</strong> lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="638a8-122">Select the <strong>Fixed offset account</strong> option.</span></span> <span data-ttu-id="638a8-123">Vegye figyelembe, hogy nem adhat meg alapértelmezett ellenszámlákat a naplóneveken, ha a naplónevek naplótípusa <strong>Számlaregiszter</strong> vagy <strong>Jóváhagyás</strong>.</span><span class="sxs-lookup"><span data-stu-id="638a8-123">Note that you can't specify default offset accounts on journal names if the journal type of the journal names is <strong>Invoice register</strong> or <strong>Approval</strong>.</span></span></td>
<td><ul>
<li><span data-ttu-id="638a8-124">Naplófejléc, amely a naplónevet használja.</span><span class="sxs-lookup"><span data-stu-id="638a8-124">Journal header that uses the journal name</span></span></li>
<li><span data-ttu-id="638a8-125">Naplóbejegyzések a naplókban, amelyek a naplónevet használják</span><span class="sxs-lookup"><span data-stu-id="638a8-125">Journal entries in journals that use the journal name</span></span></li>
</ul></td>
<td><span data-ttu-id="638a8-126">Ha a <strong>Rögzített ellenszámla</strong> opció a <strong>Naplónevek</strong> lapon be van jelölve, a naplónévhez megadott ellenszámla felülbírálja a szállítóhoz vagy szállítócsoporthoz tartozó alapértelmezett ellenszámlát.</span><span class="sxs-lookup"><span data-stu-id="638a8-126">If the <strong>Fixed offset account</strong> option on the <strong>Journal names</strong> page is selected, the offset account for the journal name overrides the default offset account for the vendor or vendor group.</span></span></td>
<td><span data-ttu-id="638a8-127">Az opció segítségével naplókat állíthat be meghatározott költségekre és kiadásokra, amelyek bizonyos számlákat terhelnek, függetlenül attól, hogy ki a szállító vagy mely szállítói csoporthoz tartozik.</span><span class="sxs-lookup"><span data-stu-id="638a8-127">Use this option to set up journals for specific costs and expenses that are charged to specific accounts, regardless of the vendor or the vendor group that the vendor belongs to.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="638a8-128"><strong>Naplónevek</strong> – Állítsa be az alapértelmezett ellenszámlákat a naplókhoz a <strong>Naplónevek</strong> oldalon.</span><span class="sxs-lookup"><span data-stu-id="638a8-128"><strong>Journal names</strong> – Set up default offset accounts for journals on the <strong>Journal names</strong> page.</span></span> <span data-ttu-id="638a8-129">Törölje a <strong>Rögzített ellenszámla</strong> lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="638a8-129">Clear the <strong>Fixed offset account</strong> option.</span></span> <span data-ttu-id="638a8-130">Vegye figyelembe, hogy nem adhat meg alapértelmezett ellenszámlákat a naplóneveken, ha a naplónevek naplótípusa <strong>Számlaregiszter</strong> vagy <strong>Jóváhagyás</strong>.</span><span class="sxs-lookup"><span data-stu-id="638a8-130">Note that you can't specify default offset accounts on journal names if the journal type of the journal names is <strong>Invoice register</strong> or <strong>Approval</strong>.</span></span></td>
<td><ul>
<li><span data-ttu-id="638a8-131">Napló fejléce</span><span class="sxs-lookup"><span data-stu-id="638a8-131">Journal header</span></span></li>
<li><span data-ttu-id="638a8-132">Naplóbejegyzések a naplókban, amelyek a naplónevet használják</span><span class="sxs-lookup"><span data-stu-id="638a8-132">Journal entries in journals that use the journal name</span></span></li>
</ul></td>
<td><span data-ttu-id="638a8-133">Az alapértelmezett bejegyzések a napló fejlécének oldalain használatosak és az ellenszámla a napló fejlécének oldalán egy alapértelmezett bejegyzésként használatos a napló bizonylat oldalakon.</span><span class="sxs-lookup"><span data-stu-id="638a8-133">These default entries are used on journal header pages, and the offset account on the journal header page is used as a default entry on the journal voucher pages.</span></span> <span data-ttu-id="638a8-134">Alapértelmezett számlák a <strong>Naplónevek </strong>oldalon csak akkor használatosak, ha az alapértelmezett számlák nincsenek beállítva a szállítói számlára.</span><span class="sxs-lookup"><span data-stu-id="638a8-134">Default accounts from the <strong>Journal names </strong>page are used only if default accounts aren’t set up for the vendor account.</span></span></td>
<td><span data-ttu-id="638a8-135">Használja ezt az opciót az alapértelmezett számlák beállításához, amelyeket akkor használ, amikor az alapértelmezett szállítói ellenszámla nincs hozzárendelve.</span><span class="sxs-lookup"><span data-stu-id="638a8-135">Use this option to set up default accounts that are used when a default vendor offset account isn't assigned.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="638a8-136"><strong>Napló fejléce</strong> – Állítson be alapértelmezett ellenszámlát egy naplóhoz, amelyet alapértelmezett bejegyzésként használhat a napló bizonylat oldalakon.</span><span class="sxs-lookup"><span data-stu-id="638a8-136"><strong>Journal header</strong> – Set up a default offset account for a journal as a default entry on the journal voucher pages.</span></span> <span data-ttu-id="638a8-137">Vegye figyelembe, hogy nem adhat meg alapértelmezett ellenszámlákat a napló fejlécén, ha a naplónevek naplótípusa <strong>Számlaregiszter</strong> vagy <strong>Jóváhagyás</strong>.</span><span class="sxs-lookup"><span data-stu-id="638a8-137">Note that you can't specify default offset accounts on the journal header if the journal type of the journal names is <strong>Invoice register</strong> or <strong>Approval</strong>.</span></span></td>
<td><span data-ttu-id="638a8-138">A napló naplóbejegyzések a naplóban</span><span class="sxs-lookup"><span data-stu-id="638a8-138">Journal entries in the journal</span></span></td>
<td><span data-ttu-id="638a8-139">Az alapértelmezett ellenszámla egy naplóhoz alapértelmezett bejegyzésként használatos a napló bizonylat oldalakon.</span><span class="sxs-lookup"><span data-stu-id="638a8-139">The default offset account for a journal is used as the default entry on the journal voucher pages.</span></span></td>
<td><span data-ttu-id="638a8-140">A beállítás segítségével felgyorsítható az adatbevitel, ha a naplóban lévő legtöbb bejegyzés ugyanazzal az ellenszámlával rendelkezik.</span><span class="sxs-lookup"><span data-stu-id="638a8-140">Use this option to help speed up data entry if most entries in a journal have the same offset account.</span></span></td>
</tr>
</tbody>
</table>





