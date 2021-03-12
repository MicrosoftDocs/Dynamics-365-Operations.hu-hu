---
title: Szállítói együttműködési számlázás munkaterület
description: Ez a témakör bemutatja, hogyan tekintheti meg a szállítói számlákat, és hogyan küldheti be a számlákat a szállítói együttműködési számlázás munkaterületen.
author: abruer
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendInvoiceWorkspace
audience: Application User
ms.reviewer: roschlom
ms.custom: 221534
ms.assetid: c4ed62f3-d351-41d7-a2ad-790576cde4ab
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 30e9012845838a4d1df5f1308740b356a64433e9
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4993163"
---
# <a name="vendor-collaboration-invoicing-workspace"></a><span data-ttu-id="fd0c0-103">Szállítói együttműködési számlázás munkaterület</span><span class="sxs-lookup"><span data-stu-id="fd0c0-103">Vendor collaboration invoicing workspace</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="fd0c0-104">Ez a témakör bemutatja, hogyan tekintheti meg a szállítói számlákat, és hogyan küldheti be a számlákat a szállítói együttműködési számlázás munkaterületen.</span><span class="sxs-lookup"><span data-stu-id="fd0c0-104">This topic explains how you can view vendor invoices and submit invoices from the vendor collaboration invoicing workspace.</span></span>

<span data-ttu-id="fd0c0-105">A **Szállítói együttműködési számlázás** munkaterület a szállítói számla adatainak megtekintésére, és a számlák rendszerbe küldésére használható a munkafolyamat-lehetőségeinek használatával.</span><span class="sxs-lookup"><span data-stu-id="fd0c0-105">The **Vendor collaboration invoicing** workspace can be used to view vendor invoice information and to submit invoices to the system using workflow capabilities.</span></span>


<a name="vendor-collaboration-invoicing-workspace"></a><span data-ttu-id="fd0c0-106">Szállítói együttműködés számlázási munkaterülete</span><span class="sxs-lookup"><span data-stu-id="fd0c0-106">Vendor collaboration invoicing workspace</span></span>
----------------------------------------

### <a name="summary-tiles"></a><span data-ttu-id="fd0c0-107">Összesítő csempék</span><span class="sxs-lookup"><span data-stu-id="fd0c0-107">Summary tiles</span></span>

<span data-ttu-id="fd0c0-108">Az **Összesítés** csempék áttekintést adnak a kiválasztott szállító számláiról.</span><span class="sxs-lookup"><span data-stu-id="fd0c0-108">The **Summary** tiles give an overview of the invoices for the selected vendor.</span></span> <span data-ttu-id="fd0c0-109">A számlák állapotuk szerint tekinthetők meg.</span><span class="sxs-lookup"><span data-stu-id="fd0c0-109">You can view invoices by their state.</span></span>
-   <span data-ttu-id="fd0c0-110">A vázlat számlák nem lettek elküldve a munkafolyamatba.</span><span class="sxs-lookup"><span data-stu-id="fd0c0-110">Draft invoices have not been submitted to workflow.</span></span>
-   <span data-ttu-id="fd0c0-111">Az elküldött, nem jóváhagyott számlák olyan számlák, amelyeket a szállító már benyújtott, de még nincsenek feladva az alkalmazásba.</span><span class="sxs-lookup"><span data-stu-id="fd0c0-111">Submitted, not approved invoices are those invoices that the vendor has submitted, but they have not been posted in the application.</span></span>
-   <span data-ttu-id="fd0c0-112">A jóváhagyott, nem fizetett számlák olyan számlák, amelyeknek a feladása már megtörtént, de még nincsenek teljes mértékben kifizetve.</span><span class="sxs-lookup"><span data-stu-id="fd0c0-112">Approved, not paid invoices are those that have been posted, but they have not yet been fully paid.</span></span>
-   <span data-ttu-id="fd0c0-113">A kifizetett számlák olyan számlák, amelyeket teljes mértékben kifizettek az alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="fd0c0-113">Paid invoices are those that have been fully paid in the application.</span></span>

<span data-ttu-id="fd0c0-114">Kattintson egy csempére, és megnyílik a **Számlalisták** lap szűrt nézete.</span><span class="sxs-lookup"><span data-stu-id="fd0c0-114">Clicking on a tile will open a filtered view of the **Invoices list** page.</span></span>

### <a name="tabular-lists"></a><span data-ttu-id="fd0c0-115">Táblázatos listák</span><span class="sxs-lookup"><span data-stu-id="fd0c0-115">Tabular lists</span></span>

<span data-ttu-id="fd0c0-116">A **táblázatos listák** szakaszban a számlázás állapotának bontása megegyezik az összesítés csempékével: Vázlat és Elküldött, jóváhagyással még nem rendelkező listák.</span><span class="sxs-lookup"><span data-stu-id="fd0c0-116">In the **Tabular lists** section, the status of the invoicing is broken down in similar ways as the summary tiles: Draft and Submitted, not approved lists.</span></span> <span data-ttu-id="fd0c0-117">Vázlat állapotban a számlát be lehet küldeni a munkafolyamatba, vagy törölni lehet.</span><span class="sxs-lookup"><span data-stu-id="fd0c0-117">While in the Draft state, an invoice can be submitted to workflow or deleted.</span></span> <span data-ttu-id="fd0c0-118">Az utolsó táblázatos lista a számlák keresésére szolgáló beállítás.</span><span class="sxs-lookup"><span data-stu-id="fd0c0-118">The last tabular list is an option to find invoices.</span></span> <span data-ttu-id="fd0c0-119">A gyorsabb keresés érdekében lehetőség van a keresés közbeni szűrésre.</span><span class="sxs-lookup"><span data-stu-id="fd0c0-119">You can filter as you search, to allow for faster searches.</span></span>

### <a name="all-vendor-invoices-list-page"></a><span data-ttu-id="fd0c0-120">Az összes szállítói számla listaoldal</span><span class="sxs-lookup"><span data-stu-id="fd0c0-120">All vendor invoices list page</span></span>

<span data-ttu-id="fd0c0-121">Minden feladott és feladatlan szállítói számla megtekinthető a **Szállítói együttműködési számlák** listaoldalon.</span><span class="sxs-lookup"><span data-stu-id="fd0c0-121">You can view all posted and unposted vendor invoices on the **Vendor collaboration invoices** list page.</span></span> <span data-ttu-id="fd0c0-122">A listaoldal segítségével a számlák fizetési állapota jeleníthető meg.</span><span class="sxs-lookup"><span data-stu-id="fd0c0-122">You can use this list page to view the payment status of the invoices.</span></span> <span data-ttu-id="fd0c0-123">A kifizetés állapota lehet Feladatlan, Kifizetetlen, Részben fizetve és Teljesen kifizetve.</span><span class="sxs-lookup"><span data-stu-id="fd0c0-123">The payment statuses include Unposted, Unpaid, Partially paid, and Fully paid.</span></span>
<span data-ttu-id="fd0c0-124">Új számla létrehozása beszerzési rendelés alapján</span><span class="sxs-lookup"><span data-stu-id="fd0c0-124">Creating a new invoice from a purchase order</span></span>

<span data-ttu-id="fd0c0-125">Létrehozhat egy új szállítói számlát a következő kiválasztásával: **Új** a **Szállítói együttműködési számlázás** munkaterületen.</span><span class="sxs-lookup"><span data-stu-id="fd0c0-125">You can create a new vendor invoice by selecting the **New** action on the **Vendor collaboration invoicing** workspace.</span></span> <span data-ttu-id="fd0c0-126">A beszerzési rendelés számát és számlaszámát a szállítónak kell megadnia.</span><span class="sxs-lookup"><span data-stu-id="fd0c0-126">The purchase order number and invoice number must be provided by the vendor.</span></span> <span data-ttu-id="fd0c0-127">Alapértelmezés szerint a szállító beszerzési rendelésének összes sora meg fog jelenni az új számlán.</span><span class="sxs-lookup"><span data-stu-id="fd0c0-127">By default, all of the lines from the vendor's purchase order will appear on the new invoice.</span></span> <span data-ttu-id="fd0c0-128">A mennyiség- és költségadatokat a szállítói számla munkafolyamatba küldése előtt lehet szerkeszteni.</span><span class="sxs-lookup"><span data-stu-id="fd0c0-128">The quantity and cost information can be edited prior to submitting the vendor invoice to workflow.</span></span> <span data-ttu-id="fd0c0-129">A számlához a beküldése előtt fájlokat, megjegyzéseket, képeket és URL-címeket csatolhat.</span><span class="sxs-lookup"><span data-stu-id="fd0c0-129">You can attach files, notes, images, and URLs to an invoice before submitting it.</span></span>

<span data-ttu-id="fd0c0-130">További tájékoztatás: [A külső szállítókkal történő szállítói együttműködés](../../supply-chain/procurement/vendor-collaboration-work-external-vendors.md)</span><span class="sxs-lookup"><span data-stu-id="fd0c0-130">For more information, see [Vendor collaboration with external vendors](../../supply-chain/procurement/vendor-collaboration-work-external-vendors.md)</span></span>



