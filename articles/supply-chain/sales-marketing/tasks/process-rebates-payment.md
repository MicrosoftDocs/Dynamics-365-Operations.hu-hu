---
title: Kifizetés-visszatérítések feldolgozása
description: Ez az eljárás bemutatja, hogyan lehet jóváhagyott és feldolgozott Vevői visszatérítéseket jóváírásokká átalakítani.
author: omulvad
manager: tfehr
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b1d32d94daef570e37a1a36d948fe18cd4041e46
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4966155"
---
# <a name="process-rebates-for-payment"></a><span data-ttu-id="bd8da-103">Kifizetés-visszatérítések feldolgozása</span><span class="sxs-lookup"><span data-stu-id="bd8da-103">Process rebates for payment</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="bd8da-104">Ez az eljárás bemutatja, hogyan lehet jóváhagyott és feldolgozott Vevői visszatérítéseket jóváírásokká átalakítani.</span><span class="sxs-lookup"><span data-stu-id="bd8da-104">This procedure demonstrates how to convert approved and processed customer rebates to credit notes.</span></span> <span data-ttu-id="bd8da-105">Ezt az útmutatót használhatja az USMF bemutatócégben.</span><span class="sxs-lookup"><span data-stu-id="bd8da-105">You can use this guide in the USMF demo company.</span></span> <span data-ttu-id="bd8da-106">Az útmutató előfeltétele, hogy egy vagy több olyan visszatérítési igénnyel rendelkezzen, amelynek az állapota be van jelölve.</span><span class="sxs-lookup"><span data-stu-id="bd8da-106">The precondition for this guide is to have one or more rebate claims which have a status of Mark.</span></span> <span data-ttu-id="bd8da-107">Az USMF használatakor futtatnia kell a „Vevői visszatérítések létrehozása és feldolgozása” útmutatót, az útmutató megkezdése előtt.</span><span class="sxs-lookup"><span data-stu-id="bd8da-107">If you're using USMF you should run the "Generate and process customer rebates" guide before you start this guide.</span></span>


## <a name="convert-rebate-claims-to-credit-note"></a><span data-ttu-id="bd8da-108">Visszatérítési igények átalakítása jóváírássá</span><span class="sxs-lookup"><span data-stu-id="bd8da-108">Convert rebate claims to credit note</span></span>
1. <span data-ttu-id="bd8da-109">Ugorjon a Minden vevő elemre.</span><span class="sxs-lookup"><span data-stu-id="bd8da-109">Go to All customers.</span></span>
2. <span data-ttu-id="bd8da-110">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="bd8da-110">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="bd8da-111">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="bd8da-111">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="bd8da-112">A Művelet panelen kattintson a Beszed elemre.</span><span class="sxs-lookup"><span data-stu-id="bd8da-112">On the Action Pane, click Collect.</span></span>
5. <span data-ttu-id="bd8da-113">Kattintson a Tranzakcióinak kiegyenlítése gombra.</span><span class="sxs-lookup"><span data-stu-id="bd8da-113">Click Settle transactions.</span></span>
6. <span data-ttu-id="bd8da-114">Kattintson a Funkciók elemre.</span><span class="sxs-lookup"><span data-stu-id="bd8da-114">Click Functions.</span></span>
7. <span data-ttu-id="bd8da-115">Kattintson a Visszatérítési program elemre.</span><span class="sxs-lookup"><span data-stu-id="bd8da-115">Click Rebate program.</span></span>
    * <span data-ttu-id="bd8da-116">A Visszatérítés lapon láthatja azokat a visszatérítési igényléseket, amelyeket feldolgozott a vevői visszatérítési munkaterületen, és amelyek állapota be van jelölve.</span><span class="sxs-lookup"><span data-stu-id="bd8da-116">The Rebate page lists the rebate claims that you have processed in the customer rebate workbench and that are in status Mark.</span></span>    
8. <span data-ttu-id="bd8da-117">Kattintson a Szerkesztés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="bd8da-117">Click Edit.</span></span>
    * <span data-ttu-id="bd8da-118">A Jelölés mezőben jelölje be azoknak az igényléseknek a jelölőnégyzetét, amelyeket szerepeltetni szeretne a jóváírásban.</span><span class="sxs-lookup"><span data-stu-id="bd8da-118">Set checkmarks in the Mark field for the claims that you want to include into credit note.</span></span>   
9. <span data-ttu-id="bd8da-119">Kattintson a Funkciók elemre.</span><span class="sxs-lookup"><span data-stu-id="bd8da-119">Click Functions.</span></span>
10. <span data-ttu-id="bd8da-120">Kattintson a Jóváírás létrehozása elemre.</span><span class="sxs-lookup"><span data-stu-id="bd8da-120">Click Create credit note.</span></span>
    * <span data-ttu-id="bd8da-121">Megjelenik egy üzenet, amely arról tájékoztatja, hogy a napló feladása megtörtént (Ez a Kinnlevőség-felhasználási napló, ahogy az a Kinnlevőségek paraméterei lapon is szerepel).</span><span class="sxs-lookup"><span data-stu-id="bd8da-121">A message appears to inform you that a journal has been posted (This is the Accounts receivable consumption journal, as specified in the Accounts receivable parameters page).</span></span> <span data-ttu-id="bd8da-122">Ezzel a valós kötelezettség (hitel) összegét a vevő egyenlegébe helyezi át.</span><span class="sxs-lookup"><span data-stu-id="bd8da-122">This causes the real liability (credit) amount to be moved to the customer balance.</span></span> <span data-ttu-id="bd8da-123">Ez azt jelenti, hogy a rendszer a vevő számláját jóváírta, és a visszatérítés könyvelési számlát megterhelte.</span><span class="sxs-lookup"><span data-stu-id="bd8da-123">This means that the customer's account has been credited, and the Rebate accrual account has been debited.</span></span>  
11. <span data-ttu-id="bd8da-124">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="bd8da-124">Close the page.</span></span>
12. <span data-ttu-id="bd8da-125">Kattintson a Mégse gombra.</span><span class="sxs-lookup"><span data-stu-id="bd8da-125">Click Cancel.</span></span>
    * <span data-ttu-id="bd8da-126">Ezzel frissíti a lapot, így láthatja a frissítéseket.</span><span class="sxs-lookup"><span data-stu-id="bd8da-126">This refreshes the page so that you can see the updates.</span></span>  
13. <span data-ttu-id="bd8da-127">A Művelet panelen kattintson a Beszed elemre.</span><span class="sxs-lookup"><span data-stu-id="bd8da-127">On the Action Pane, click Collect.</span></span>
14. <span data-ttu-id="bd8da-128">Kattintson a Tranzakcióinak kiegyenlítése gombra.</span><span class="sxs-lookup"><span data-stu-id="bd8da-128">Click Settle transactions.</span></span>
    * <span data-ttu-id="bd8da-129">Vegye figyelembe, hogy a teljes visszatérítés összegét jelentő negatív összegű tranzakciót a rendszer számlahivatkozás nélkül hozzáadta a vevő egyenlegéhez.</span><span class="sxs-lookup"><span data-stu-id="bd8da-129">Note that a transaction for negative amount, representing the total rebate amount, without invoice reference has been added to the customer balance.</span></span>   
15. <span data-ttu-id="bd8da-130">Kattintson a Mégse gombra.</span><span class="sxs-lookup"><span data-stu-id="bd8da-130">Click Cancel.</span></span>

