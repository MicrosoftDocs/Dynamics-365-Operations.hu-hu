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
ms.search.scope: Operations, Retail
ms.custom: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rapraj
ms.search.validFrom: 2020-01-21
ms.dyn365.ops.version: Retail 10.0.9 update
ms.openlocfilehash: c2a9325f09ffe43c3436b7e0ca2ab511e1f57f83
ms.sourcegitcommit: 02640a0f63daa9e509146641824ed623c4d69c7f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/16/2020
ms.locfileid: "3265583"
---
# <a name="create-and-update-a-returns-and-refunds-policy-for-a-channel"></a><span data-ttu-id="1f632-103">Visszáruk és visszatérítések irányelvének létrehozása és frissítése a csatornához</span><span class="sxs-lookup"><span data-stu-id="1f632-103">Create and update a returns and refunds policy for a channel</span></span>

[!include [banner](includes/banner.md)]

## <a name="overview"></a><span data-ttu-id="1f632-104">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="1f632-104">Overview</span></span>

<span data-ttu-id="1f632-105">A csatorna visszaküldési irányelve a Dynamics 365 Commerce-ben lehetővé teszi a kiskereskedők számára, hogy olyan érvényesítéseket állítsanak be, amelyeknél engedélyezhetők a fizetőeszközök a megtérülés pénztári eszközöknél való feldolgozásához.</span><span class="sxs-lookup"><span data-stu-id="1f632-105">The channel return policy in Dynamics 365 Commerce enables retailers to set enforcements on which payment tenders can be allowed for processing a return on a point of sale (POS) device.</span></span>  

<span data-ttu-id="1f632-106">Ez a témakör annak lépéseit írja le, hogyan lehet beállítani egy csatorna visszárukra és visszatérítésekre vonatkozó irányelvét.</span><span class="sxs-lookup"><span data-stu-id="1f632-106">This topic describes the steps to set up a returns and refunds policy for a channel.</span></span>

<span data-ttu-id="1f632-107">Az irányelv hatálya jelenleg csak a csatornán megengedhető fizetőeszközök beállításához használható.</span><span class="sxs-lookup"><span data-stu-id="1f632-107">The scope of the policy is currently limited to setting the payment tenders that can be allowed for a channel.</span></span> <span data-ttu-id="1f632-108">A „megengedett” lista a beszerzés elkészítésekor használt fizetési módokon alapul.</span><span class="sxs-lookup"><span data-stu-id="1f632-108">The "allowed" list is based on the payment methods used to make the purchase.</span></span> <span data-ttu-id="1f632-109">Példa:</span><span class="sxs-lookup"><span data-stu-id="1f632-109">For example:</span></span>

- <span data-ttu-id="1f632-110">Ha egy beszerzéskor ajándékutalványt alkalmaznak, az áruházi irányelv célja, hogy csak egy új ajándékutalvány számára vagy üzleti hitel céljából dolgozza fel a visszatérítéseket.</span><span class="sxs-lookup"><span data-stu-id="1f632-110">If a purchase was made using a gift card, the store policy is to process refunds only to a new gift card or to give store credit.</span></span> 
- <span data-ttu-id="1f632-111">Ha az értékesítés készpénzes fizetéssel történik, akkor a visszatérítésre engedélyezett lehetőségek a készpénz, az ajándékutalvány és a vevői számla, a hitelkártya azonban nem.</span><span class="sxs-lookup"><span data-stu-id="1f632-111">If a sale is made using cash, the options allowed for refund are cash, gift card, and customer account, but not credit card.</span></span> 


## <a name="enable-return-policy"></a><span data-ttu-id="1f632-112">Visszatérítési irányelv engedélyezése</span><span class="sxs-lookup"><span data-stu-id="1f632-112">Enable return policy</span></span>

<span data-ttu-id="1f632-113">A csatorna-visszaküldési irányelvek funkcióinak engedélyezéséhez hajtsa végre a következőket:</span><span class="sxs-lookup"><span data-stu-id="1f632-113">To enable the channel return policy functionality, do the following:</span></span>

1. <span data-ttu-id="1f632-114">Ugorjon a **Funkciókezelés** munkaterülethez a Dynamics 365 Commerce-ben.</span><span class="sxs-lookup"><span data-stu-id="1f632-114">Go to the **Feature Management** workspace in Dynamics 365 Commerce.</span></span>
2. <span data-ttu-id="1f632-115">Keresse meg a **Csatornavisszaküldési irányelvek engedélyezése** funkciót a szolgáltatások neveinek listáján.</span><span class="sxs-lookup"><span data-stu-id="1f632-115">Search for the **Enable channel return policies** feature in the list of feature names.</span></span>
3. <span data-ttu-id="1f632-116">Válassza az **Engedélyezés most** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1f632-116">Select **Enable now**.</span></span> 

## <a name="configure-return-policy"></a><span data-ttu-id="1f632-117">Konfigurálja a visszaküldési irányelvet</span><span class="sxs-lookup"><span data-stu-id="1f632-117">Configure return policy</span></span>

<span data-ttu-id="1f632-118">Hajtsa végre a következő lépéseket a kiskereskedelmi üzlet vagy online kiskereskedelmi csatolna visszatérítési irányelvének konfigurálásához.</span><span class="sxs-lookup"><span data-stu-id="1f632-118">Follow these steps to configure a return policy for a retail store or online retail channel.</span></span>

1. <span data-ttu-id="1f632-119">Ugorjon a **Retail és Commerce** \> **Csatorna beállítása** \> **Visszáruk** \> **Csatorna-visszaküldési irányelv** elemre.</span><span class="sxs-lookup"><span data-stu-id="1f632-119">Go to **Retail and Commerce** \> **Channel Setup** \> **Returns** \> **Channel return policy**.</span></span>

2. <span data-ttu-id="1f632-120">Válassza az **Új** lehetőséget új visszaküldésiirányelv-sablon létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="1f632-120">Select **New** to create a new return policy template.</span></span> <span data-ttu-id="1f632-121">Meglévő sablon használatához válassza ki a sablont a bal oldali ablaktáblán.</span><span class="sxs-lookup"><span data-stu-id="1f632-121">To use an existing template, select the template in the left pane.</span></span> <span data-ttu-id="1f632-122">Új sablonok esetében adjon meg egy nevet és egy leírást, amely segítséget nyújt az irányelvnek a csatornára való alkalmazásakor.</span><span class="sxs-lookup"><span data-stu-id="1f632-122">For new templates, add a name and description that will help you identify the policy when it is being applied to the channel.</span></span>

   <span data-ttu-id="1f632-123">![Új visszaküldési irányelv hozzáadása](media/Return-policy-page1.png "Új visszaküldési irányelv hozzáadása")</span><span class="sxs-lookup"><span data-stu-id="1f632-123">![Add new return policy](media/Return-policy-page1.png "Add new return rolicy")</span></span>
     
   
3. <span data-ttu-id="1f632-124">Az **Engedélyezett visszatérítési mód** szakaszban határozza meg az egyes fizetési módokhoz **Engedélyezett** visszáru-kifizetési eszközöket.</span><span class="sxs-lookup"><span data-stu-id="1f632-124">In the **Allowed refund payment methods** section, define **Allowed** return payment tenders that are specific to each payment method.</span></span>
   <span data-ttu-id="1f632-125">![Fizetési módok hozzáadása](media/Return-policy-page2.PNG "Engedélyezett fizetési módok megadása fizetéstípusonként")</span><span class="sxs-lookup"><span data-stu-id="1f632-125">![Add payment methods](media/Return-policy-page2.PNG "Set allowed payment methods per payment type")</span></span>
   
    > [!IMPORTANT]
    > - <span data-ttu-id="1f632-126">A fizetési módok a szervezethez beállított fizetési módokból vannak származtatva.</span><span class="sxs-lookup"><span data-stu-id="1f632-126">The payment methods are derived from the payment methods set for the organization.</span></span>
    > - <span data-ttu-id="1f632-127">Ha egy engedélyezett visszárueszköz-típust ad meg mindegyik felsorolt kifizetési módhoz, akkor biztosítja, hogy a visszaküldések megvalósíthatók legyenek az engedélyezett visszárueszköz-típussal.</span><span class="sxs-lookup"><span data-stu-id="1f632-127">Adding an allowed return tender type for each listed payment method will ensure that returns can be made to the allowed return tender type.</span></span>
    
4. <span data-ttu-id="1f632-128">A visszaküldési irányelv sablonját társítsa azokkal az üzletekkel, ahol használatban lesz.</span><span class="sxs-lookup"><span data-stu-id="1f632-128">Associate the return policy template with the stores where it will be used.</span></span> <span data-ttu-id="1f632-129">Válassza **Hozzáadás** lehetőséget a **Kiskereskedelmi csatornák** lapon, majd társítsa az elérhető csatornákat.</span><span class="sxs-lookup"><span data-stu-id="1f632-129">Select **Add** in the **Retail Channels** tab and associate the available channels.</span></span> 

    - <span data-ttu-id="1f632-130">A **Szervezeti csomópontok kiválasztása** párbeszédpanelen válassza ki azokat az üzleteket, régiókat és szervezeteket, amelyekkel a sablont társítani szeretné.</span><span class="sxs-lookup"><span data-stu-id="1f632-130">In the **Choose organization nodes** dialog box, select the stores, regions, and organizations that the template should be associated with.</span></span>
    - <span data-ttu-id="1f632-131">Minden üzlethez csak egy visszaküldésiirányelv-sablon tartozhat.</span><span class="sxs-lookup"><span data-stu-id="1f632-131">Only one return policy template can be associated with each store.</span></span>
    - <span data-ttu-id="1f632-132">A nyílgombokkal válassza ki az üzleteket, régiókat vagy szervezeteket.</span><span class="sxs-lookup"><span data-stu-id="1f632-132">Use the arrow buttons to select stores, regions, or organizations.</span></span>
    - <span data-ttu-id="1f632-133">Az irányelv érvényességi dátuma az a dátum, amelyen a rendszer a csatornákra alkalmazza a szabályokat, és a csatorna feladatait futtatja.</span><span class="sxs-lookup"><span data-stu-id="1f632-133">The effective date on the policy will be the date on which the policies are applied to the channels and the channel jobs are run.</span></span> 

    <span data-ttu-id="1f632-134">![Szervezeti csomópontok párbeszédpanel kiválasztása](media/Return-policy-page3.PNG "Szervezeti csomópontok párbeszédpanel kiválasztása")</span><span class="sxs-lookup"><span data-stu-id="1f632-134">![Choose organization nodes dialog box](media/Return-policy-page3.PNG "Choose organization nodes dialog box")</span></span>

5. <span data-ttu-id="1f632-135">A **Felosztási ütemezés** lapon futtassa az **1070-es** feladatot, hogy a csatorna visszaküldési irányelve elérhető legyen a pénztár számára.</span><span class="sxs-lookup"><span data-stu-id="1f632-135">On the **Distribution schedule** page, run the **1070** job to make the channel return policy available to the POS.</span></span>

## <a name="preview-the-channel-return-policy-in-the-pos"></a><span data-ttu-id="1f632-136">A csatorna-visszaküldési irányelv előnézetének megtekintése a pénztárban</span><span class="sxs-lookup"><span data-stu-id="1f632-136">Preview the channel return policy in the POS</span></span>

<span data-ttu-id="1f632-137">Kövesse az alábbi lépések egyikét, ha a pénztárban engedélyezett visszárueszköz-típusokat szeretné megtekinteni.</span><span class="sxs-lookup"><span data-stu-id="1f632-137">Follow the steps in either of the following examples to view the allowed return tender types in POS.</span></span>

1. <span data-ttu-id="1f632-138">Jelentkezzen be a pénztárba pénztárosként vagy vezetőként.</span><span class="sxs-lookup"><span data-stu-id="1f632-138">Sign in to the POS as a cashier or manager.</span></span>
2. <span data-ttu-id="1f632-139">A **Műszak és a fiók**területen válassza a **Napló megjelenítése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1f632-139">Under **Shift and Drawer**, select **Show journal**.</span></span>
3. <span data-ttu-id="1f632-140">Válassza ki azt a tranzakciót, amely a visszáru része.</span><span class="sxs-lookup"><span data-stu-id="1f632-140">Select the transaction that is part of the return.</span></span> 
4. <span data-ttu-id="1f632-141">Válassza ki a visszatérítéshez használandó cikkeket, és válassza ki a fizetési módot.</span><span class="sxs-lookup"><span data-stu-id="1f632-141">Select the items to refund, and choose the payment method.</span></span>  
- <span data-ttu-id="1f632-142">Ha a kiválasztott fizetési mód szerepel a visszárueszköz-típusok engedélyezett listáján, a pénztáros elvégezheti a tranzakciót.</span><span class="sxs-lookup"><span data-stu-id="1f632-142">If the payment tender selected is in the allowed list of return tender types, the cashier can complete the transaction.</span></span>
- <span data-ttu-id="1f632-143">Ha a kiválasztott fizetési mód nem engedélyezett, akkor egy hibaüzenet jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="1f632-143">If the payment tender selected is not allowed, an error message is displayed.</span></span>
- <span data-ttu-id="1f632-144">Válassza ki az **Esedékes összeget** az összes engedélyezett visszárueszköz-típus listájának megjelenítéséhez.</span><span class="sxs-lookup"><span data-stu-id="1f632-144">Select **Amount Due** to display a list of all the allowed return tender types.</span></span>

<span data-ttu-id="1f632-145">– vagy –</span><span class="sxs-lookup"><span data-stu-id="1f632-145">-or-</span></span>

1. <span data-ttu-id="1f632-146">Jelentkezzen be a pénztárba pénztárosként vagy vezetőként.</span><span class="sxs-lookup"><span data-stu-id="1f632-146">Sign in to the POS as a cashier or manager.</span></span>
2. <span data-ttu-id="1f632-147">Válassza ki a **Visszáru-tranzakciót**, és írja be a nyugta azonosítóját vonalkód-beolvasással vagy manuális bevitellel.</span><span class="sxs-lookup"><span data-stu-id="1f632-147">Select **Return Transaction** and enter the receipt ID using a barcode scan or by manual entry.</span></span> 
3. <span data-ttu-id="1f632-148">Válassza ki azt a tranzakciót, amely a visszáru része.</span><span class="sxs-lookup"><span data-stu-id="1f632-148">Select the transaction that is part of the return.</span></span> 
4. <span data-ttu-id="1f632-149">Válassza ki a visszatérítéshez használandó cikkeket, és válassza ki a fizetési módot.</span><span class="sxs-lookup"><span data-stu-id="1f632-149">Select the items to refund, and choose the payment method.</span></span>  
- <span data-ttu-id="1f632-150">Ha a kiválasztott fizetési mód szerepel a visszárueszköz-típusok engedélyezett listáján, a pénztáros elvégezheti a tranzakciót.</span><span class="sxs-lookup"><span data-stu-id="1f632-150">If the payment tender selected is in the allowed list of return tender types, the cashier can complete the transaction.</span></span>
- <span data-ttu-id="1f632-151">Ha a kiválasztott fizetési mód nem engedélyezett, akkor egy hibaüzenet jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="1f632-151">If the payment tender selected is not allowed, an error message is displayed.</span></span>
- <span data-ttu-id="1f632-152">Válassza ki az **Esedékes összeget** az összes engedélyezett visszárueszköz-típus listájának megjelenítéséhez.</span><span class="sxs-lookup"><span data-stu-id="1f632-152">Select **Amount Due** to display a list of all the allowed return tender types.</span></span>

<span data-ttu-id="1f632-153">![Visszatérítés nem engedélyezett](media/Return-policy-page6.png "Nem engedélyezett visszatérítés-típus")</span><span class="sxs-lookup"><span data-stu-id="1f632-153">![Refund not allowed](media/Return-policy-page6.png "Refund type not allowed")</span></span>



<span data-ttu-id="1f632-154">![Fizetési módok listája](media/Return-policy-page5.PNG "Engedélyezett visszatérítés-típusok")</span><span class="sxs-lookup"><span data-stu-id="1f632-154">![List of payment methods](media/Return-policy-page5.PNG "Refund types allowed")</span></span>
