---
title: Fő számlaadatok a kötelezettségekbe jóváhagyási napló használatával
description: Ez a témakör bemutatja hogy kell használni a számlajegyzéket számlák létrehozásához, majd hogyan kell a kiadási számlákat frissíteni a jóváhagyási napló segítségével.
author: abruer
manager: AnnBe
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransInvoiceRegister, HcmWorkerLookUp, LedgerJournalTransApprove, LedgerJournalTransApproveFetchVouchers, LedgerTransVoucher
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f19c31a3ca20ad4b11e2529bdcb9db351c37f6c2
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4971878"
---
# <a name="key-invoice-data-into-accounts-payable-using-an-approval-journal"></a><span data-ttu-id="7ce68-103">Fő számlaadatok a kötelezettségekbe jóváhagyási napló használatával</span><span class="sxs-lookup"><span data-stu-id="7ce68-103">Key invoice data into accounts payable using an approval journal</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="7ce68-104">Ez a témakör bemutatja hogy kell használni a számlajegyzéket számlák létrehozásához, majd hogyan kell a kiadási számlákat frissíteni a jóváhagyási napló segítségével.</span><span class="sxs-lookup"><span data-stu-id="7ce68-104">This topic explains how to use the invoice register to create invoices and then use the approval journal to update the expense accounts.</span></span>

## <a name="create-and-post-and-invoice"></a><span data-ttu-id="7ce68-105">Számla létrehozása és feladása</span><span class="sxs-lookup"><span data-stu-id="7ce68-105">Create and post and invoice</span></span>
1. <span data-ttu-id="7ce68-106">Anavigációs ablaktáblán válassza a **Modulok > Kötelezettségek > számlák > Számlajegyzék** elemre.</span><span class="sxs-lookup"><span data-stu-id="7ce68-106">In the navigation pan, go to **Modules > Accounts payable > Invoices > Invoice register**.</span></span>
2. <span data-ttu-id="7ce68-107">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7ce68-107">Select **New**.</span></span>
3. <span data-ttu-id="7ce68-108">Válassza ki a használni kívánt számlajegyzék nevét.</span><span class="sxs-lookup"><span data-stu-id="7ce68-108">Select the name of the invoice register that you want to use.</span></span>
4. <span data-ttu-id="7ce68-109">Kattintson a **Sorokra** a jegyzék megnyitásához, adjon meg költségsorokat.</span><span class="sxs-lookup"><span data-stu-id="7ce68-109">Select **Lines** to open the register and enter expense lines.</span></span>
5. <span data-ttu-id="7ce68-110">Válasszon ki egy szállítót.</span><span class="sxs-lookup"><span data-stu-id="7ce68-110">Select a vendor.</span></span> <span data-ttu-id="7ce68-111">Például adja a `US-104` értéket</span><span class="sxs-lookup"><span data-stu-id="7ce68-111">For example, enter or select `US-104`.</span></span>
6. <span data-ttu-id="7ce68-112">Írjon be egy értéket a **Számla** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="7ce68-112">In the **Invoice** field, type a value.</span></span>
7. <span data-ttu-id="7ce68-113">Írjon egy értéket a **Leírás** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="7ce68-113">In the **Description** field, type a value.</span></span>
8. <span data-ttu-id="7ce68-114">A **Hitelkeret** mezőben adjon meg egy számot.</span><span class="sxs-lookup"><span data-stu-id="7ce68-114">In the **Credit** field, enter a number.</span></span>
9. <span data-ttu-id="7ce68-115">Az **Jóváhagyó** mezőben válasszon ki egy jóváhagyót a legördülő menüben.</span><span class="sxs-lookup"><span data-stu-id="7ce68-115">In the **Approved by** field, select an approver from the drop-down menu.</span></span>
10. <span data-ttu-id="7ce68-116">Válassza a **Feladás** parancsot.</span><span class="sxs-lookup"><span data-stu-id="7ce68-116">Select **Post**.</span></span>

## <a name="approve-an-invoice"></a><span data-ttu-id="7ce68-117">Számla jóváhagyása</span><span class="sxs-lookup"><span data-stu-id="7ce68-117">Approve an invoice</span></span>
1. <span data-ttu-id="7ce68-118">Anavigációs ablaktáblán válassza a **Modulok > Kötelezettségek > számlák > Számlajóváhagyás** elemre.</span><span class="sxs-lookup"><span data-stu-id="7ce68-118">In the navigation pane, go to **Modules > Accounts payable > Invoices > Invoice approval**.</span></span>
2. <span data-ttu-id="7ce68-119">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7ce68-119">Select **New**.</span></span>
3. <span data-ttu-id="7ce68-120">Válassza ki a használni kívánt számlajóváhagyás-jegyzék nevét.</span><span class="sxs-lookup"><span data-stu-id="7ce68-120">Select the name of the invoice approval journal that you want to use.</span></span>
4. <span data-ttu-id="7ce68-121">Kattintson a **Sorokra** az oldal megjelenítéséhez, ahol kiválaszthatja a jóváhagyni kívánt számlákat.</span><span class="sxs-lookup"><span data-stu-id="7ce68-121">Select **Lines** to display a page where you will be able to select the invoices that you want to approve.</span></span>
5. <span data-ttu-id="7ce68-122">Válassza ki a **Bizonylatok keresése** lehetőséget az összes jóváhagyható számla megjelenítéséhez.</span><span class="sxs-lookup"><span data-stu-id="7ce68-122">Select **Find Vouchers** to display all of the invoices that are ready for approval.</span></span>
6. <span data-ttu-id="7ce68-123">Jelölje meg a létrehozott számlát, majd kattintson a **Kiválasztás** gombra.</span><span class="sxs-lookup"><span data-stu-id="7ce68-123">Mark the invoice that you created, then click **Select**.</span></span> <span data-ttu-id="7ce68-124">A fent kiválasztott bizonylatok erre a listára kerülnek.</span><span class="sxs-lookup"><span data-stu-id="7ce68-124">The vouchers that you selected above are moved to this list after you select them.</span></span>  
7. <span data-ttu-id="7ce68-125">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7ce68-125">Select **OK**.</span></span>
8. <span data-ttu-id="7ce68-126">Kattintson a **számlaszám mezőre**, ha szeretne a számlához költségszámlát adni.</span><span class="sxs-lookup"><span data-stu-id="7ce68-126">Select the **account number** field to add an expense account to the invoice.</span></span>
9. <span data-ttu-id="7ce68-127">Adjon meg egy számlaszámot és lépjen ki a mezőből.</span><span class="sxs-lookup"><span data-stu-id="7ce68-127">Enter an account number and tab off of the field.</span></span> <span data-ttu-id="7ce68-128">Például írja be, hogy `600120`.</span><span class="sxs-lookup"><span data-stu-id="7ce68-128">For example, enter `600120`.</span></span>
10. <span data-ttu-id="7ce68-129">Válassza a **Feladás** parancsot.</span><span class="sxs-lookup"><span data-stu-id="7ce68-129">Select **Post**.</span></span>
11. <span data-ttu-id="7ce68-130">Kattintson a **Bizonylat** lehetőségre, hogy megtekintse hova kerültek feladásra a bejegyzések.</span><span class="sxs-lookup"><span data-stu-id="7ce68-130">Select **Voucher** to view the entries that were posted.</span></span> <span data-ttu-id="7ce68-131">A Függőben lévő számla visszavonásra kerül és egy tényleges költségszámla jön létre helyette.</span><span class="sxs-lookup"><span data-stu-id="7ce68-131">The Invoice Pending Approval account is reversed and replaced with the actual expense account.</span></span>  

