---
title: Kifizetés-visszatérítések feldolgozása
description: Ez az eljárás bemutatja, hogyan lehet jóváhagyott és feldolgozott Vevői visszatérítéseket jóváírásokká átalakítani.
author: omulvad
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b2d97a59ae782af0a3d5ab71903961ef244a8e62
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2019
ms.locfileid: "1570716"
---
# <a name="process-rebates-for-payment"></a><span data-ttu-id="a9266-103">Kifizetés-visszatérítések feldolgozása</span><span class="sxs-lookup"><span data-stu-id="a9266-103">Process rebates for payment</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="a9266-104">Ez az eljárás bemutatja, hogyan lehet jóváhagyott és feldolgozott Vevői visszatérítéseket jóváírásokká átalakítani.</span><span class="sxs-lookup"><span data-stu-id="a9266-104">This procedure demonstrates how to convert approved and processed customer rebates to credit notes.</span></span> <span data-ttu-id="a9266-105">Ezt az útmutatót használhatja az USMF bemutatócégben.</span><span class="sxs-lookup"><span data-stu-id="a9266-105">You can use this guide in the USMF demo company.</span></span> <span data-ttu-id="a9266-106">Az útmutató előfeltétele, hogy egy vagy több olyan visszatérítési igénnyel rendelkezzen, amelynek az állapota be van jelölve.</span><span class="sxs-lookup"><span data-stu-id="a9266-106">The precondition for this guide is to have one or more rebate claims which have a status of Mark.</span></span> <span data-ttu-id="a9266-107">Az USMF használatakor futtatnia kell a „Vevői visszatérítések létrehozása és feldolgozása” útmutatót, az útmutató megkezdése előtt.</span><span class="sxs-lookup"><span data-stu-id="a9266-107">If you’re using USMF you should run the "Generate and process customer rebates" guide before you start this guide.</span></span>


## <a name="convert-rebate-claims-to-credit-note"></a><span data-ttu-id="a9266-108">Visszatérítési igények átalakítása jóváírássá</span><span class="sxs-lookup"><span data-stu-id="a9266-108">Convert rebate claims to credit note</span></span>
1. <span data-ttu-id="a9266-109">Ugorjon a Minden vevő elemre.</span><span class="sxs-lookup"><span data-stu-id="a9266-109">Go to All customers.</span></span>
2. <span data-ttu-id="a9266-110">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="a9266-110">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="a9266-111">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="a9266-111">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="a9266-112">A Művelet panelen kattintson a Beszed elemre.</span><span class="sxs-lookup"><span data-stu-id="a9266-112">On the Action Pane, click Collect.</span></span>
5. <span data-ttu-id="a9266-113">Kattintson a Tranzakcióinak kiegyenlítése gombra.</span><span class="sxs-lookup"><span data-stu-id="a9266-113">Click Settle transactions.</span></span>
6. <span data-ttu-id="a9266-114">Kattintson a Funkciók elemre.</span><span class="sxs-lookup"><span data-stu-id="a9266-114">Click Functions.</span></span>
7. <span data-ttu-id="a9266-115">Kattintson a Visszatérítési program elemre.</span><span class="sxs-lookup"><span data-stu-id="a9266-115">Click Rebate program.</span></span>
    * <span data-ttu-id="a9266-116">A Visszatérítés lapon láthatja azokat a visszatérítési igényléseket, amelyeket feldolgozott a vevői visszatérítési munkaterületen, és amelyek állapota be van jelölve.</span><span class="sxs-lookup"><span data-stu-id="a9266-116">The Rebate page lists the rebate claims that you have processed in the customer rebate workbench and that are in status Mark.</span></span>    
8. <span data-ttu-id="a9266-117">Kattintson a Szerkesztés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="a9266-117">Click Edit.</span></span>
    * <span data-ttu-id="a9266-118">A Jelölés mezőben jelölje be azoknak az igényléseknek a jelölőnégyzetét, amelyeket szerepeltetni szeretne a jóváírásban.</span><span class="sxs-lookup"><span data-stu-id="a9266-118">Set checkmarks in the Mark field for the claims that you want to include into credit note.</span></span>   
9. <span data-ttu-id="a9266-119">Kattintson a Funkciók elemre.</span><span class="sxs-lookup"><span data-stu-id="a9266-119">Click Functions.</span></span>
10. <span data-ttu-id="a9266-120">Kattintson a Jóváírás létrehozása elemre.</span><span class="sxs-lookup"><span data-stu-id="a9266-120">Click Create credit note.</span></span>
    * <span data-ttu-id="a9266-121">Megjelenik egy üzenet, amely arról tájékoztatja, hogy a napló feladása megtörtént (Ez a Kinnlevőség-felhasználási napló, ahogy az a Kinnlevőségek paraméterei lapon is szerepel).</span><span class="sxs-lookup"><span data-stu-id="a9266-121">A message appears to inform you that a journal has been posted (This is the Accounts receivable consumption journal, as specified in the Accounts receivable parameters page).</span></span> <span data-ttu-id="a9266-122">Ezzel a valós kötelezettség (hitel) összegét a vevő egyenlegébe helyezi át.</span><span class="sxs-lookup"><span data-stu-id="a9266-122">This causes the real liability (credit) amount to be moved to the customer balance.</span></span> <span data-ttu-id="a9266-123">Ez azt jelenti, hogy a rendszer a vevő számláját jóváírta, és a visszatérítés könyvelési számlát megterhelte.</span><span class="sxs-lookup"><span data-stu-id="a9266-123">This means that the customer’s account has been credited, and the Rebate accrual account has been debited.</span></span>  
11. <span data-ttu-id="a9266-124">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="a9266-124">Close the page.</span></span>
12. <span data-ttu-id="a9266-125">Kattintson a Mégse gombra.</span><span class="sxs-lookup"><span data-stu-id="a9266-125">Click Cancel.</span></span>
    * <span data-ttu-id="a9266-126">Ezzel frissíti a lapot, így láthatja a frissítéseket.</span><span class="sxs-lookup"><span data-stu-id="a9266-126">This refreshes the page so that you can see the updates.</span></span>  
13. <span data-ttu-id="a9266-127">A Művelet panelen kattintson a Beszed elemre.</span><span class="sxs-lookup"><span data-stu-id="a9266-127">On the Action Pane, click Collect.</span></span>
14. <span data-ttu-id="a9266-128">Kattintson a Tranzakcióinak kiegyenlítése gombra.</span><span class="sxs-lookup"><span data-stu-id="a9266-128">Click Settle transactions.</span></span>
    * <span data-ttu-id="a9266-129">Vegye figyelembe, hogy a teljes visszatérítés összegét jelentő negatív összegű tranzakciót a rendszer számlahivatkozás nélkül hozzáadta a vevő egyenlegéhez.</span><span class="sxs-lookup"><span data-stu-id="a9266-129">Note that a transaction for negative amount, representing the total rebate amount, without invoice reference has been added to the customer balance.</span></span>   
15. <span data-ttu-id="a9266-130">Kattintson a Mégse gombra.</span><span class="sxs-lookup"><span data-stu-id="a9266-130">Click Cancel.</span></span>

