--- 
title: " Fizetéskonfiguráció kiskereskedelmi kimutatásokhoz"
description: "Ez az eljárás a Kiskereskedelmi kimutatások létrehozásának és feladásának módját befolyásoló Kiskereskedelmi üzlethez kapcsolódó fizetési módok konfigurációit mutatja be."
author: jashanno
manager: AnnBe
ms.date: 11/14/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 8bbdbf882f6f73d03be0a036cb975109396e4a0d
ms.openlocfilehash: 19f9c0b1c3a93ed9c84d66041814fd64951744b0
ms.contentlocale: hu-hu
ms.lasthandoff: 11/14/2017

---
# <a name="payment-configurations-for-retail-statements"></a><span data-ttu-id="5b1d8-103"> Fizetéskonfiguráció kiskereskedelmi kimutatásokhoz</span><span class="sxs-lookup"><span data-stu-id="5b1d8-103">Payment configurations for Retail statements</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="5b1d8-104">Ez az eljárás a Kiskereskedelmi kimutatások létrehozásának és feladásának módját befolyásoló Kiskereskedelmi üzlethez kapcsolódó fizetési módok konfigurációit mutatja be.</span><span class="sxs-lookup"><span data-stu-id="5b1d8-104">This procedure demonstrates configurations for Retail store payment methods, which affect how Retail statements get created and posted.</span></span>

<span data-ttu-id="5b1d8-105">Ez a felvétel az USRT bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="5b1d8-105">This recording uses the USRT demo company.</span></span>

1. <span data-ttu-id="5b1d8-106">Nyissa meg a következőt: Kiskereskedelem és kereskedelem > Csatornák > Kiskereskedelmi áruházak > Minden kiskereskedelmi üzlet.</span><span class="sxs-lookup"><span data-stu-id="5b1d8-106">Go to Retail and commerce > Channels > Retail stores > All retail stores.</span></span>
2. <span data-ttu-id="5b1d8-107">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="5b1d8-107">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="5b1d8-108">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="5b1d8-108">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="5b1d8-109">A műveleti ablaktáblán kattintson a Beállítások elemre.</span><span class="sxs-lookup"><span data-stu-id="5b1d8-109">On the Action Pane, click Set up.</span></span>
5. <span data-ttu-id="5b1d8-110">Kattintson a Kifizetési módok lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="5b1d8-110">Click Payment methods.</span></span>
6. <span data-ttu-id="5b1d8-111">Bontsa ki vagy csukja össze a Feladás szakaszt.</span><span class="sxs-lookup"><span data-stu-id="5b1d8-111">Expand or collapse the Posting section.</span></span>
7. <span data-ttu-id="5b1d8-112">Kattintson a Szerkesztés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="5b1d8-112">Click Edit.</span></span>
    * <span data-ttu-id="5b1d8-113">Adja meg, hogy a jelen fizetési mód kapcsán kézhez kapott összegek főkönyvi számlára vagy bankszámlára kerüljenek-e feladásra.</span><span class="sxs-lookup"><span data-stu-id="5b1d8-113">Select whether the amounts received for this payment method should be posted to a ledger account or bank account.</span></span>  
    * <span data-ttu-id="5b1d8-114">Válassza ki a jelen fizetési mód kapcsán kézhez kapott összegek feladásához használandó számlát.</span><span class="sxs-lookup"><span data-stu-id="5b1d8-114">Select the account that amounts received for this payment method should be posted to.</span></span>  
    * <span data-ttu-id="5b1d8-115">Válassza ki, hogy milyen számlára kerüljenek feladásra a tranzakció teljes kézhez kapott összege, illetve a fizetési mód kapcsán kiszámított összeg közötti esetleges különbségek.</span><span class="sxs-lookup"><span data-stu-id="5b1d8-115">Select an account to post possible differences between the total transaction amount received and the amount counted for this payment method.</span></span>  
    * <span data-ttu-id="5b1d8-116">Az ebben a mezőben megadott összegnek megfelelően fogja a rendszer más eltérésszámlára adni fel az adott eltérés összegét.</span><span class="sxs-lookup"><span data-stu-id="5b1d8-116">In this field you can enter an amount to control when the difference amount should be posted to another difference account.</span></span> <span data-ttu-id="5b1d8-117">Ez a funkció a jelentős eltérések nyomon követésére használható.</span><span class="sxs-lookup"><span data-stu-id="5b1d8-117">You can use this to track big differences.</span></span>  
    * <span data-ttu-id="5b1d8-118">Válassza ki, hogy milyen számlára kerüljenek feladásra a tranzakció teljes kézhez kapott összege, illetve a kiszámított összeg közötti esetleges különbségek, ha azok összege meghaladja az „Eltérés maximális összege" mezőben megadott értéket.</span><span class="sxs-lookup"><span data-stu-id="5b1d8-118">Select an account to post possible differences between the total transaction amount received and the amount counted, when it exceeds the value that is defined in the "Maximum difference amount" field.</span></span>  
    * <span data-ttu-id="5b1d8-119">Válassza az „Igen” lehetőséget, ha a banki befizetéses összegeket szeretné külön számlára adni fel.</span><span class="sxs-lookup"><span data-stu-id="5b1d8-119">Select "Yes" to post bank drop amounts to a separate account.</span></span>  
    * <span data-ttu-id="5b1d8-120">Ebben a mezőben megadhatja hogy a banki befizetéses összegek főkönyvi számlára vagy bankszámlára kerüljenek-e feladásra.</span><span class="sxs-lookup"><span data-stu-id="5b1d8-120">In this field you can select whether bank drop amounts should be posted to a ledger account or a bank account.</span></span>  
    * <span data-ttu-id="5b1d8-121">Válassza ki a banki befizetéses összegek feladásához használni kívánt számlát.</span><span class="sxs-lookup"><span data-stu-id="5b1d8-121">Select the account to post bank drop amounts into.</span></span>  
    * <span data-ttu-id="5b1d8-122">Válassza ki a banki befizetéses összegek, a bankszámlára történő feladásához használni kívánt tranzakciótípust.</span><span class="sxs-lookup"><span data-stu-id="5b1d8-122">Select the bank transaction type to use when posting bank drop amounts to the bank account.</span></span>  
    * <span data-ttu-id="5b1d8-123">Válassza az „Igen” lehetőséget, ha a széfes befizetéses összegeket szeretné külön számlára adni fel.</span><span class="sxs-lookup"><span data-stu-id="5b1d8-123">Select "Yes" to post safe drop amounts to a separate account.</span></span>  
    * <span data-ttu-id="5b1d8-124">Válassza ki, hogy a széfes befizetéses összegek a főkönyvi számlára vagy a bankszámlára kerüljenek-e feladásra.</span><span class="sxs-lookup"><span data-stu-id="5b1d8-124">Select whether safe drop amounts should be posted to the ledger account or the bank account.</span></span>  
    * <span data-ttu-id="5b1d8-125">Válassza ki a széfes befizetéses összegek feladásához használni kívánt számlát.</span><span class="sxs-lookup"><span data-stu-id="5b1d8-125">Select the account to post safe drop amounts into.</span></span>  
8. <span data-ttu-id="5b1d8-126">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="5b1d8-126">Click Save.</span></span>


