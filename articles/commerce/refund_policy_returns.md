---
title: Visszáruk és visszatérítések irányelvének létrehozása és frissítése a csatornához
description: Ez a témakör azt mutatja be, hogyan lehet beállítani egy csatorna visszárukra és visszatérítésekre vonatkozó irányelvét.
author: ShalabhjainMSFT
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rapraj
ms.search.validFrom: 2020-01-21
ms.dyn365.ops.version: Retail 10.0.9 update
ms.openlocfilehash: 03e46a7f8d110bd9ef3b353b150116bbf8a70ad5
ms.sourcegitcommit: c88b54ba13a4dfe39b844ffaced4dc435560c47d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/19/2021
ms.locfileid: "5478116"
---
# <a name="create-and-update-a-returns-and-refunds-policy-for-a-channel"></a><span data-ttu-id="b314d-103">Visszáruk és visszatérítések irányelvének létrehozása és frissítése a csatornához</span><span class="sxs-lookup"><span data-stu-id="b314d-103">Create and update a returns and refunds policy for a channel</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="b314d-104">A csatorna visszaküldési irányelve a Dynamics 365 Commerce-ben lehetővé teszi a kiskereskedők számára, hogy olyan érvényesítéseket állítsanak be, amelyeknél engedélyezhetők a fizetőeszközök a megtérülés pénztári eszközöknél való feldolgozásához.</span><span class="sxs-lookup"><span data-stu-id="b314d-104">The channel return policy in Dynamics 365 Commerce enables retailers to set enforcements on which payment tenders can be allowed for processing a return on a point of sale (POS) device.</span></span>  

<span data-ttu-id="b314d-105">Ez a témakör annak lépéseit írja le, hogyan lehet beállítani egy csatorna visszárukra és visszatérítésekre vonatkozó irányelvét.</span><span class="sxs-lookup"><span data-stu-id="b314d-105">This topic describes the steps to set up a returns and refunds policy for a channel.</span></span>

<span data-ttu-id="b314d-106">Az irányelv hatálya jelenleg csak a csatornán megengedhető fizetőeszközök beállításához használható.</span><span class="sxs-lookup"><span data-stu-id="b314d-106">The scope of the policy is currently limited to setting the payment tenders that can be allowed for a channel.</span></span> <span data-ttu-id="b314d-107">A „megengedett” lista a beszerzés elkészítésekor használt fizetési módokon alapul.</span><span class="sxs-lookup"><span data-stu-id="b314d-107">The "allowed" list is based on the payment methods used to make the purchase.</span></span> <span data-ttu-id="b314d-108">Példa:</span><span class="sxs-lookup"><span data-stu-id="b314d-108">For example:</span></span>

- <span data-ttu-id="b314d-109">Ha egy beszerzéskor ajándékutalványt alkalmaznak, az áruházi irányelv célja, hogy csak egy új ajándékutalvány számára vagy üzleti hitel céljából dolgozza fel a visszatérítéseket.</span><span class="sxs-lookup"><span data-stu-id="b314d-109">If a purchase was made using a gift card, the store policy is to process refunds only to a new gift card or to give store credit.</span></span> 
- <span data-ttu-id="b314d-110">Ha az értékesítés készpénzes fizetéssel történik, akkor a visszatérítésre engedélyezett lehetőségek a készpénz, az ajándékutalvány és a vevői számla, a hitelkártya azonban nem.</span><span class="sxs-lookup"><span data-stu-id="b314d-110">If a sale is made using cash, the options allowed for refund are cash, gift card, and customer account, but not credit card.</span></span> 


## <a name="enable-return-policy"></a><span data-ttu-id="b314d-111">Visszatérítési irányelv engedélyezése</span><span class="sxs-lookup"><span data-stu-id="b314d-111">Enable return policy</span></span>

<span data-ttu-id="b314d-112">A csatorna-visszaküldési irányelvek funkcióinak engedélyezéséhez hajtsa végre a következőket:</span><span class="sxs-lookup"><span data-stu-id="b314d-112">To enable the channel return policy functionality, do the following:</span></span>

1. <span data-ttu-id="b314d-113">Ugorjon a **Funkciókezelés** munkaterülethez a Dynamics 365 Commerce-ben.</span><span class="sxs-lookup"><span data-stu-id="b314d-113">Go to the **Feature Management** workspace in Dynamics 365 Commerce.</span></span>
2. <span data-ttu-id="b314d-114">Keresse meg a **Csatornavisszaküldési irányelvek engedélyezése** funkciót a szolgáltatások neveinek listáján.</span><span class="sxs-lookup"><span data-stu-id="b314d-114">Search for the **Enable channel return policies** feature in the list of feature names.</span></span>
3. <span data-ttu-id="b314d-115">Válassza az **Engedélyezés most** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b314d-115">Select **Enable now**.</span></span> 

## <a name="configure-return-policy"></a><span data-ttu-id="b314d-116">Konfigurálja a visszaküldési irányelvet</span><span class="sxs-lookup"><span data-stu-id="b314d-116">Configure return policy</span></span>

<span data-ttu-id="b314d-117">Hajtsa végre a következő lépéseket a kiskereskedelmi üzlet vagy online kiskereskedelmi csatolna visszatérítési irányelvének konfigurálásához.</span><span class="sxs-lookup"><span data-stu-id="b314d-117">Follow these steps to configure a return policy for a retail store or online retail channel.</span></span>

1. <span data-ttu-id="b314d-118">Ugorjon a **Retail és Commerce** \> **Csatorna beállítása** \> **Visszáruk** \> **Csatorna-visszaküldési irányelv** elemre.</span><span class="sxs-lookup"><span data-stu-id="b314d-118">Go to **Retail and Commerce** \> **Channel Setup** \> **Returns** \> **Channel return policy**.</span></span>

2. <span data-ttu-id="b314d-119">Válassza az **Új** lehetőséget új visszaküldésiirányelv-sablon létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="b314d-119">Select **New** to create a new return policy template.</span></span> <span data-ttu-id="b314d-120">Meglévő sablon használatához válassza ki a sablont a bal oldali ablaktáblán.</span><span class="sxs-lookup"><span data-stu-id="b314d-120">To use an existing template, select the template in the left pane.</span></span> <span data-ttu-id="b314d-121">Új sablonok esetében adjon meg egy nevet és egy leírást, amely segítséget nyújt az irányelvnek a csatornára való alkalmazásakor.</span><span class="sxs-lookup"><span data-stu-id="b314d-121">For new templates, add a name and description that will help you identify the policy when it is being applied to the channel.</span></span>

   <span data-ttu-id="b314d-122">![Új visszaküldési irányelv hozzáadása](media/Return-policy-page1.png "Új visszaküldési irányelv hozzáadása")</span><span class="sxs-lookup"><span data-stu-id="b314d-122">![Add new return policy](media/Return-policy-page1.png "Add new return rolicy")</span></span>
     
   
3. <span data-ttu-id="b314d-123">Az **Engedélyezett visszatérítési mód** szakaszban határozza meg az egyes fizetési módokhoz **Engedélyezett** visszáru-kifizetési eszközöket.</span><span class="sxs-lookup"><span data-stu-id="b314d-123">In the **Allowed refund payment methods** section, define **Allowed** return payment tenders that are specific to each payment method.</span></span>
   <span data-ttu-id="b314d-124">![Fizetési módok hozzáadása](media/Return-policy-page2.PNG "Engedélyezett fizetési módok megadása fizetéstípusonként")</span><span class="sxs-lookup"><span data-stu-id="b314d-124">![Add payment methods](media/Return-policy-page2.PNG "Set allowed payment methods per payment type")</span></span>
   
    > [!IMPORTANT]
    > - <span data-ttu-id="b314d-125">A fizetési módok a szervezethez beállított fizetési módokból vannak származtatva.</span><span class="sxs-lookup"><span data-stu-id="b314d-125">The payment methods are derived from the payment methods set for the organization.</span></span>
    > - <span data-ttu-id="b314d-126">Ha egy engedélyezett visszárueszköz-típust ad meg mindegyik felsorolt kifizetési módhoz, akkor biztosítja, hogy a visszaküldések megvalósíthatók legyenek az engedélyezett visszárueszköz-típussal.</span><span class="sxs-lookup"><span data-stu-id="b314d-126">Adding an allowed return tender type for each listed payment method will ensure that returns can be made to the allowed return tender type.</span></span>
    
4. <span data-ttu-id="b314d-127">A visszaküldési irányelv sablonját társítsa azokkal az üzletekkel, ahol használatban lesz.</span><span class="sxs-lookup"><span data-stu-id="b314d-127">Associate the return policy template with the stores where it will be used.</span></span> <span data-ttu-id="b314d-128">Válassza **Hozzáadás** lehetőséget a **Kiskereskedelmi csatornák** lapon, majd társítsa az elérhető csatornákat.</span><span class="sxs-lookup"><span data-stu-id="b314d-128">Select **Add** in the **Retail Channels** tab and associate the available channels.</span></span> 

    - <span data-ttu-id="b314d-129">A **Szervezeti csomópontok kiválasztása** párbeszédpanelen válassza ki azokat az üzleteket, régiókat és szervezeteket, amelyekkel a sablont társítani szeretné.</span><span class="sxs-lookup"><span data-stu-id="b314d-129">In the **Choose organization nodes** dialog box, select the stores, regions, and organizations that the template should be associated with.</span></span>
    - <span data-ttu-id="b314d-130">Minden üzlethez csak egy visszaküldésiirányelv-sablon tartozhat.</span><span class="sxs-lookup"><span data-stu-id="b314d-130">Only one return policy template can be associated with each store.</span></span>
    - <span data-ttu-id="b314d-131">A nyílgombokkal válassza ki az üzleteket, régiókat vagy szervezeteket.</span><span class="sxs-lookup"><span data-stu-id="b314d-131">Use the arrow buttons to select stores, regions, or organizations.</span></span>
    - <span data-ttu-id="b314d-132">Az irányelv érvényességi dátuma az a dátum, amelyen a rendszer a csatornákra alkalmazza a szabályokat, és a csatorna feladatait futtatja.</span><span class="sxs-lookup"><span data-stu-id="b314d-132">The effective date on the policy will be the date on which the policies are applied to the channels and the channel jobs are run.</span></span> 

    <span data-ttu-id="b314d-133">![Szervezeti csomópontok párbeszédpanel kiválasztása](media/Return-policy-page3.PNG "Szervezeti csomópontok párbeszédpanel kiválasztása")</span><span class="sxs-lookup"><span data-stu-id="b314d-133">![Choose organization nodes dialog box](media/Return-policy-page3.PNG "Choose organization nodes dialog box")</span></span>

5. <span data-ttu-id="b314d-134">A **Felosztási ütemezés** lapon futtassa az **1070-es** feladatot, hogy a csatorna visszaküldési irányelve elérhető legyen a pénztár számára.</span><span class="sxs-lookup"><span data-stu-id="b314d-134">On the **Distribution schedule** page, run the **1070** job to make the channel return policy available to the POS.</span></span>

## <a name="preview-the-channel-return-policy-in-the-pos"></a><span data-ttu-id="b314d-135">A csatorna-visszaküldési irányelv előnézetének megtekintése a pénztárban</span><span class="sxs-lookup"><span data-stu-id="b314d-135">Preview the channel return policy in the POS</span></span>

<span data-ttu-id="b314d-136">Kövesse az alábbi lépések egyikét, ha a pénztárban engedélyezett visszárueszköz-típusokat szeretné megtekinteni.</span><span class="sxs-lookup"><span data-stu-id="b314d-136">Follow the steps in either of the following examples to view the allowed return tender types in POS.</span></span>

1. <span data-ttu-id="b314d-137">Jelentkezzen be a pénztárba pénztárosként vagy vezetőként.</span><span class="sxs-lookup"><span data-stu-id="b314d-137">Sign in to the POS as a cashier or manager.</span></span>
2. <span data-ttu-id="b314d-138">A **Műszak és a fiók** területen válassza a **Napló megjelenítése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b314d-138">Under **Shift and Drawer**, select **Show journal**.</span></span>
3. <span data-ttu-id="b314d-139">Válassza ki azt a tranzakciót, amely a visszáru része.</span><span class="sxs-lookup"><span data-stu-id="b314d-139">Select the transaction that is part of the return.</span></span> 
4. <span data-ttu-id="b314d-140">Válassza ki a visszatérítéshez használandó cikkeket, és válassza ki a fizetési módot.</span><span class="sxs-lookup"><span data-stu-id="b314d-140">Select the items to refund, and choose the payment method.</span></span>  
- <span data-ttu-id="b314d-141">Ha a kiválasztott fizetési mód szerepel a visszárueszköz-típusok engedélyezett listáján, a pénztáros elvégezheti a tranzakciót.</span><span class="sxs-lookup"><span data-stu-id="b314d-141">If the payment tender selected is in the allowed list of return tender types, the cashier can complete the transaction.</span></span>
- <span data-ttu-id="b314d-142">Ha a kiválasztott fizetési mód nem engedélyezett, akkor egy hibaüzenet jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="b314d-142">If the payment tender selected is not allowed, an error message is displayed.</span></span>
- <span data-ttu-id="b314d-143">Válassza ki az **Esedékes összeget** az összes engedélyezett visszárueszköz-típus listájának megjelenítéséhez.</span><span class="sxs-lookup"><span data-stu-id="b314d-143">Select **Amount Due** to display a list of all the allowed return tender types.</span></span>

<span data-ttu-id="b314d-144">– vagy –</span><span class="sxs-lookup"><span data-stu-id="b314d-144">-or-</span></span>

1. <span data-ttu-id="b314d-145">Jelentkezzen be a pénztárba pénztárosként vagy vezetőként.</span><span class="sxs-lookup"><span data-stu-id="b314d-145">Sign in to the POS as a cashier or manager.</span></span>
2. <span data-ttu-id="b314d-146">Válassza ki a **Visszáru-tranzakciót**, és írja be a nyugta azonosítóját vonalkód-beolvasással vagy manuális bevitellel.</span><span class="sxs-lookup"><span data-stu-id="b314d-146">Select **Return Transaction** and enter the receipt ID using a barcode scan or by manual entry.</span></span> 
3. <span data-ttu-id="b314d-147">Válassza ki azt a tranzakciót, amely a visszáru része.</span><span class="sxs-lookup"><span data-stu-id="b314d-147">Select the transaction that is part of the return.</span></span> 
4. <span data-ttu-id="b314d-148">Válassza ki a visszatérítéshez használandó cikkeket, és válassza ki a fizetési módot.</span><span class="sxs-lookup"><span data-stu-id="b314d-148">Select the items to refund, and choose the payment method.</span></span>  
- <span data-ttu-id="b314d-149">Ha a kiválasztott fizetési mód szerepel a visszárueszköz-típusok engedélyezett listáján, a pénztáros elvégezheti a tranzakciót.</span><span class="sxs-lookup"><span data-stu-id="b314d-149">If the payment tender selected is in the allowed list of return tender types, the cashier can complete the transaction.</span></span>
- <span data-ttu-id="b314d-150">Ha a kiválasztott fizetési mód nem engedélyezett, akkor egy hibaüzenet jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="b314d-150">If the payment tender selected is not allowed, an error message is displayed.</span></span>
- <span data-ttu-id="b314d-151">Válassza ki az **Esedékes összeget** az összes engedélyezett visszárueszköz-típus listájának megjelenítéséhez.</span><span class="sxs-lookup"><span data-stu-id="b314d-151">Select **Amount Due** to display a list of all the allowed return tender types.</span></span>

<span data-ttu-id="b314d-152">![Visszatérítés nem engedélyezett](media/Return-policy-page6.png "Nem engedélyezett visszatérítés-típus")</span><span class="sxs-lookup"><span data-stu-id="b314d-152">![Refund not allowed](media/Return-policy-page6.png "Refund type not allowed")</span></span>



<span data-ttu-id="b314d-153">![Fizetési módok listája](media/Return-policy-page5.PNG "Engedélyezett visszatérítés-típusok")</span><span class="sxs-lookup"><span data-stu-id="b314d-153">![List of payment methods](media/Return-policy-page5.PNG "Refund types allowed")</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
