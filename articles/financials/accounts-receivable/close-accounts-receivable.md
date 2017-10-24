---
title: "Fiók kinnlevőségeinek bezárása"
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
ms.custom: 59372
ms.assetid: c18d83e5-4adb-422a-91be-82a665d8288b
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 2b2e827df0c679855af9624f8a2fb36cb23f359a
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---

# <a name="close-accounts-receivable"></a><span data-ttu-id="4d8f5-102">Fiók kinnlevőségeinek bezárása</span><span class="sxs-lookup"><span data-stu-id="4d8f5-102">Close Accounts receivable</span></span>

[!include[banner](../includes/banner.md)]




<span data-ttu-id="4d8f5-103">Az alábbi táblázat felsorolja azokat az oldalakat, amelyeken elvégezhetők a Fiók kinnlevőségeinek üzleti folyamat bezárása.</span><span class="sxs-lookup"><span data-stu-id="4d8f5-103">The following table lists the pages that support the close Accounts receivable business process.</span></span>

> [!NOTE] 
> <span data-ttu-id="4d8f5-104">Néhány, az asztalon lévő oldal megnyításához meg kell adni információkat vagy meg kell határozni paraméterbeállításokat.</span><span class="sxs-lookup"><span data-stu-id="4d8f5-104">To open some of the pages in the table, you must enter information or specify parameter settings.</span></span>

<span data-ttu-id="4d8f5-105">**Üzletifolyamat-összetevő feladat**</span><span class="sxs-lookup"><span data-stu-id="4d8f5-105">**Business process component task**</span></span>                   

<span data-ttu-id="4d8f5-106">Időszakok lezárása a főkönyvben</span><span class="sxs-lookup"><span data-stu-id="4d8f5-106">Close periods in the general ledger</span></span>

| <span data-ttu-id="4d8f5-107">Lapnév</span><span class="sxs-lookup"><span data-stu-id="4d8f5-107">Page name</span></span>                            | <span data-ttu-id="4d8f5-108">Használat</span><span class="sxs-lookup"><span data-stu-id="4d8f5-108">Usage</span></span>                                                                                      |
|--------------------------------------|--------------------------------------------------------------------------------------------|
|<span data-ttu-id="4d8f5-109">Kötegelt feladat</span><span class="sxs-lookup"><span data-stu-id="4d8f5-109">Batch job</span></span>                             | <span data-ttu-id="4d8f5-110">Kötegelt feladatok megjelenítése és létrehozása.</span><span class="sxs-lookup"><span data-stu-id="4d8f5-110">View or create batch jobs.</span></span> <span data-ttu-id="4d8f5-111">A kötegelt feladatok lehet, hogy nem lehet végrehajtani, és azt szeretné, győződjön meg arról, hogy minden feladás befejeződik.</span><span class="sxs-lookup"><span data-stu-id="4d8f5-111">Batch jobs might not be completed, and you want make sure that all posting is completed.</span></span>                                                                                                               |
|<span data-ttu-id="4d8f5-112">Értékesítési rendelés megerősítése</span><span class="sxs-lookup"><span data-stu-id="4d8f5-112">Confirm sales order</span></span>                   | <span data-ttu-id="4d8f5-113">Értékesítési rendelések módosítása</span><span class="sxs-lookup"><span data-stu-id="4d8f5-113">Update sales orders.</span></span>                                                                       |
|<span data-ttu-id="4d8f5-114">Devizaátértékelés</span><span class="sxs-lookup"><span data-stu-id="4d8f5-114">Foreign currency revaluation</span></span>          | <span data-ttu-id="4d8f5-115">Tranzakciók előállítása, amelyek a nyitott (ki nem egyenlített) és külföldi pénznemben lévő vevői tranzakciók értékét frissítik.</span><span class="sxs-lookup"><span data-stu-id="4d8f5-115">Generate transactions that update the value of open customer transactions in foreign currencies.</span></span>                                                                                                                         |
| <span data-ttu-id="4d8f5-116">Napló</span><span class="sxs-lookup"><span data-stu-id="4d8f5-116">Journal</span></span>                              | <span data-ttu-id="4d8f5-117">Számlák, kifizetések és kötelezvények feladása.</span><span class="sxs-lookup"><span data-stu-id="4d8f5-117">Post invoices, payments, and promissory notes.</span></span>                                             |
| <span data-ttu-id="4d8f5-118">Naplóbizonylat</span><span class="sxs-lookup"><span data-stu-id="4d8f5-118">Journal voucher</span></span>                      |<ul><li><span data-ttu-id="4d8f5-119">**Kifizetési napló** – kifizetések generálása, feldolgozása és feladása.</span><span class="sxs-lookup"><span data-stu-id="4d8f5-119">**Payment journal** – Generate, process, and post payments.</span></span></li><li><span data-ttu-id="4d8f5-120">**Váltónapló kiállítása** – a váltók feladása.</span><span class="sxs-lookup"><span data-stu-id="4d8f5-120">**Draw bill of exchange journal** – Post bills of exchange.</span></span></li><li><span data-ttu-id="4d8f5-121">**Váltónapló elutasítása** – az elutasított váltók feladása.</span><span class="sxs-lookup"><span data-stu-id="4d8f5-121">**Protest bill of exchange journal** – Post protested bills of exchange.</span></span></li><li><span data-ttu-id="4d8f5-122">**Váltónapló újbóli kiállítása** – az újból kiállított váltók feladása.</span><span class="sxs-lookup"><span data-stu-id="4d8f5-122">**Redraw bill of exchange journal** – Post redrawn bills of exchange.</span></span></li><li><span data-ttu-id="4d8f5-123">**Átutalási napló** – átutalások feladása.</span><span class="sxs-lookup"><span data-stu-id="4d8f5-123">**Remittance journal** – Post remittances.</span></span></li><li><span data-ttu-id="4d8f5-124">**Váltónapló kiegyenlítése** – a kiegyenlített váltók feladása.</span><span class="sxs-lookup"><span data-stu-id="4d8f5-124">**Settle bill of exchange journal** – Post settled bills of exchange</span></span></li></ul>                   |
| <span data-ttu-id="4d8f5-125">Szállítólevél feladása</span><span class="sxs-lookup"><span data-stu-id="4d8f5-125">Packing slip posting</span></span>                 | <span data-ttu-id="4d8f5-126">Értékesítési rendelések csomagjegyzékeinek frissítése.</span><span class="sxs-lookup"><span data-stu-id="4d8f5-126">Update packing slips for sales orders.</span></span>                                                     |
| <span data-ttu-id="4d8f5-127">Szabadszöveges számla feladása</span><span class="sxs-lookup"><span data-stu-id="4d8f5-127">Post free text invoice</span></span>               | <span data-ttu-id="4d8f5-128">Szabadszöveges számlák feladása</span><span class="sxs-lookup"><span data-stu-id="4d8f5-128">Post free text invoices.</span></span>                                                                   |
| <span data-ttu-id="4d8f5-129">Számla feladása</span><span class="sxs-lookup"><span data-stu-id="4d8f5-129">Posting invoice</span></span>                      | <span data-ttu-id="4d8f5-130">Értékesítési rendelési számlák feladása.</span><span class="sxs-lookup"><span data-stu-id="4d8f5-130">Post invoices for sales orders.</span></span>                                                            |
| <span data-ttu-id="4d8f5-131">Kitárolási lista feladása</span><span class="sxs-lookup"><span data-stu-id="4d8f5-131">Posting picking list</span></span>                 |<span data-ttu-id="4d8f5-132">Az értékesítési rendelések kitárolási listáinak frissítése.</span><span class="sxs-lookup"><span data-stu-id="4d8f5-132">Update picking lists for sales orders.</span></span>                                                      |

<span data-ttu-id="4d8f5-133">**Üzletifolyamat-összetevő feladat**</span><span class="sxs-lookup"><span data-stu-id="4d8f5-133">**Business process component task**</span></span>   

<span data-ttu-id="4d8f5-134">Az EU értékesítési lista létrehozása és küldése</span><span class="sxs-lookup"><span data-stu-id="4d8f5-134">Create and submit the EU sales list</span></span>

| <span data-ttu-id="4d8f5-135">Lapnév</span><span class="sxs-lookup"><span data-stu-id="4d8f5-135">Page name</span></span>                            | <span data-ttu-id="4d8f5-136">Használat</span><span class="sxs-lookup"><span data-stu-id="4d8f5-136">Usage</span></span>                                                                                      |
|--------------------------------------|--------------------------------------------------------------------------------------------|
|<span data-ttu-id="4d8f5-137">EU értékesítési lista</span><span class="sxs-lookup"><span data-stu-id="4d8f5-137">EU sales list</span></span>                         | <span data-ttu-id="4d8f5-138">A jelentés az Európai Unió (EU) értékesítéseskről szóló jelentés az általános forgalmi adó (áfa) adóhatósága számára áfa jelentése céljából.</span><span class="sxs-lookup"><span data-stu-id="4d8f5-138">Report on European Union (EU) sales to the tax authority for value-added tax (VAT) declaration purposes.</span></span>                                                                                                                           |






