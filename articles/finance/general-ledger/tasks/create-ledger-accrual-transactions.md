---
title: Főkönyvi könyvelés tranzakcióinak létrehozása
description: Ez a feladat-útmutató bemutatja a könyvelési sémákon alapuló főkönyvi könyvelési tranzakciók létrehozását.
author: aprilolson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransDaily, LedgerJournalTransAccrual, LedgerJournalTransAccrualTrans
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6cbda1c535aad63df55d40bcbadccffc3f35b455
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4994640"
---
# <a name="create-ledger-accrual-transactions"></a><span data-ttu-id="4b4be-103">Főkönyvi könyvelés tranzakcióinak létrehozása</span><span class="sxs-lookup"><span data-stu-id="4b4be-103">Create ledger accrual transactions</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="4b4be-104">A feladat-útmutató bemutatja az olyan főkönyvi könyvelési tranzakciók létrehozását, amelyek alapját a könyvelési sémák adják</span><span class="sxs-lookup"><span data-stu-id="4b4be-104">This task guide steps through generating ledger accrual transactions that are based on accrual schemes</span></span>

1. <span data-ttu-id="4b4be-105">Ugorjon a Főkönyv > Naplóbejegyzések > Általános naplók pontra.</span><span class="sxs-lookup"><span data-stu-id="4b4be-105">Go to General ledger > Journal entries > General journals.</span></span>
2. <span data-ttu-id="4b4be-106">Keresse meg majd válassza ki a listából a kívánt naplót, vagy hozzon létre egyet.</span><span class="sxs-lookup"><span data-stu-id="4b4be-106">In the list, find and select the desired journal or create a new one.</span></span>
3. <span data-ttu-id="4b4be-107">Kattintson a Naplóköteg száma mezőben található hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="4b4be-107">Click to follow the link in the Journal batch number field.</span></span>
4. <span data-ttu-id="4b4be-108">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="4b4be-108">In the list, mark the selected row.</span></span>
5. <span data-ttu-id="4b4be-109">A Számla mezőben adja meg a kívánt értékeket.</span><span class="sxs-lookup"><span data-stu-id="4b4be-109">In the Account field, specify the desired values.</span></span>
    * <span data-ttu-id="4b4be-110">Ebben a példában a biztosításhoz a költséget határozzuk meg.</span><span class="sxs-lookup"><span data-stu-id="4b4be-110">In this example, we are defining the expense for the insurance.</span></span> <span data-ttu-id="4b4be-111">Ez időszakos kiadási összeg lesz.</span><span class="sxs-lookup"><span data-stu-id="4b4be-111">It will be come periodic expense amount.</span></span>  
6. <span data-ttu-id="4b4be-112">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="4b4be-112">In the Description field, type a value.</span></span>
7. <span data-ttu-id="4b4be-113">Adjon meg egy számot a Tartozik mezőben.</span><span class="sxs-lookup"><span data-stu-id="4b4be-113">In the Debit field, enter a number.</span></span>
8. <span data-ttu-id="4b4be-114">Az Ellenszámla mezőben adja meg a kívánt értékeket.</span><span class="sxs-lookup"><span data-stu-id="4b4be-114">In the Offset account field, specify the desired values.</span></span>
9. <span data-ttu-id="4b4be-115">Kattintson a Funkciók elemre.</span><span class="sxs-lookup"><span data-stu-id="4b4be-115">Click Functions.</span></span>
10. <span data-ttu-id="4b4be-116">Kattintson a Főkönyvi könyvelések elemre.</span><span class="sxs-lookup"><span data-stu-id="4b4be-116">Click Ledger accruals.</span></span>
11. <span data-ttu-id="4b4be-117">A Könyvelés azonosítója mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="4b4be-117">In the Accrual identification field, click the drop-down button to open the lookup.</span></span>
12. <span data-ttu-id="4b4be-118">A listában keresse meg és válassza ki az alkalmazni kívánt könyvelési sémát.</span><span class="sxs-lookup"><span data-stu-id="4b4be-118">In the list, find and select the accural scheme you want to apply.</span></span>
13. <span data-ttu-id="4b4be-119">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="4b4be-119">In the list, click the link in the selected row.</span></span>
14. <span data-ttu-id="4b4be-120">Adja meg a dátumot a Kezdő dátum mezőben.</span><span class="sxs-lookup"><span data-stu-id="4b4be-120">In the Start date field, enter a date.</span></span>
15. <span data-ttu-id="4b4be-121">Kattintson a Tranzakciók elemre.</span><span class="sxs-lookup"><span data-stu-id="4b4be-121">Click Transactions.</span></span>
16. <span data-ttu-id="4b4be-122">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="4b4be-122">Close the page.</span></span>
17. <span data-ttu-id="4b4be-123">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="4b4be-123">Click OK.</span></span>
18. <span data-ttu-id="4b4be-124">Kattintson a Feladás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="4b4be-124">Click Post.</span></span>

