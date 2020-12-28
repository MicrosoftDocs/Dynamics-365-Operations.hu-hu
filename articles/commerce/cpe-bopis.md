---
title: BOPIS konfigurálása Dynamics 365 Commerce értékelési környezetben
description: Ez a témakör azt mutatja be, hogyan lehet konfigurálni „online vásárlás, átvétel az áruházban” "(BOPIS) folyamatot a Microsoft Dynamics 365 Commerce értékelési környezetben a kiépítés után.
author: rubendel
manager: annbe
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: josaw
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: rubendel
ms.search.validFrom: 2020-04-20
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 62dabaa2610341cc8ad8e85812a317ac3123fcb1
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4412759"
---
# <a name="configure-bopis-in-a-dynamics-365-commerce-evaluation-environment"></a><span data-ttu-id="b8347-103">BOPIS konfigurálása Dynamics 365 Commerce értékelési környezetben</span><span class="sxs-lookup"><span data-stu-id="b8347-103">Configure BOPIS in a Dynamics 365 Commerce evaluation environment</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="b8347-104">Ez a témakör azt mutatja be, hogyan lehet konfigurálni „online vásárlás, átvétel az áruházban” "(BOPIS) folyamatot a Microsoft Dynamics 365 Commerce értékelési környezetben a környezet kiépítése után.</span><span class="sxs-lookup"><span data-stu-id="b8347-104">This topic explains how to configure buy online, pickup in store (BOPIS) in a Microsoft Dynamics 365 Commerce evaluation environment after the environment has been provisioned.</span></span>

## <a name="prerequisite"></a><span data-ttu-id="b8347-105">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="b8347-105">Prerequisite</span></span>

<span data-ttu-id="b8347-106">A jelen témakörben ismertetett eljárásokat csak a Commerce értékelési környezet létesítését és konfigurálását követően hajtsa végre.</span><span class="sxs-lookup"><span data-stu-id="b8347-106">Complete the procedures in this topic only after your Commerce evaluation environment has been provisioned and configured.</span></span> <span data-ttu-id="b8347-107">A környezet kiépítésével és konfigurálásával kapcsolatban lásd [Dynamics 365 Commerce értékelési környezet kiépítése](provisioning-guide.md) és [Dynamics 365 Commerce értékelési környezet konfigurálása](https://docs.microsoft.com/dynamics365/commerce/cpe-post-provisioning) című részeket.</span><span class="sxs-lookup"><span data-stu-id="b8347-107">For information about how to provision and configure your environment, see [Provision a Dynamics 365 Commerce evaluation environment](provisioning-guide.md) and [Configure a Dynamics 365 Commerce evaluation environment](https://docs.microsoft.com/dynamics365/commerce/cpe-post-provisioning).</span></span>

<span data-ttu-id="b8347-108">Miután kiépítette és konfigurálta a Commerce környezetet végponttól végpontig, ezzel a témakörrel engedélyezheti a BOPIS eseteket.</span><span class="sxs-lookup"><span data-stu-id="b8347-108">After your Commerce environment has been provisioned and configured end to end, you can use this topic to enable BOPIS scenarios.</span></span>

## <a name="configure-the-pos"></a><span data-ttu-id="b8347-109">Pénztár konfigurálása</span><span class="sxs-lookup"><span data-stu-id="b8347-109">Configure the POS</span></span>

### <a name="configure-modern-pos"></a><span data-ttu-id="b8347-110">Modern POS konfigurálása</span><span class="sxs-lookup"><span data-stu-id="b8347-110">Configure Modern POS</span></span>

<span data-ttu-id="b8347-111">A hitelkártyás fizetést tartalmazó BOPIS esetekhez hardverállomás szükséges.</span><span class="sxs-lookup"><span data-stu-id="b8347-111">BOPIS scenarios that involve a credit card payment require a hardware station.</span></span> <span data-ttu-id="b8347-112">A hardverállomás be van építve a Windows és Android klienseken futó Modern POS-programokba.</span><span class="sxs-lookup"><span data-stu-id="b8347-112">The hardware station is built into Modern POS for Windows and Android clients.</span></span> <span data-ttu-id="b8347-113">Ha Cloud POS vagy Modern POS szolgáltatást használ iOS rendszeren, a pénztár (POS) klient párosítani kell egy megosztott hardverállomással.</span><span class="sxs-lookup"><span data-stu-id="b8347-113">If you're using Cloud POS or Modern POS for iOS, the point of sale (POS) client must be paired with a shared hardware station.</span></span> <span data-ttu-id="b8347-114">Ez a témakör azt mutatja be, hogyan lehet konfigurálni a BOPIS-t Windows és Android klienseken.</span><span class="sxs-lookup"><span data-stu-id="b8347-114">This topic explains how to configure BOPIS for Windows and Android clients.</span></span> <span data-ttu-id="b8347-115">A megosztott hardverállomás beállításával kapcsolatos további tudnivalókért lásd: [Retail hardverállomás konfigurálása és telepítése](https://docs.microsoft.com/dynamics365/commerce/retail-hardware-station-configuration-installation).</span><span class="sxs-lookup"><span data-stu-id="b8347-115">For information about how to set up a shared hardware station, see [Configure and install Retail hardware station](https://docs.microsoft.com/dynamics365/commerce/retail-hardware-station-configuration-installation).</span></span>

1. <span data-ttu-id="b8347-116">Ugorjon a **Kiskereskedelem és kereskedelem \> Csatorna beállítása \> Pénztár beállítása \> Pénztárgépek** pontra.</span><span class="sxs-lookup"><span data-stu-id="b8347-116">Go to **Retail and Commerce \> Channel setup \> POS setup \> Registers**.</span></span>
2. <span data-ttu-id="b8347-117">Válassza ki a **SANFRAN-5** pénztárgépet, majd a **Szerkesztés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b8347-117">Select register **SANFRAN-5**, and then select **Edit**.</span></span>
3. <span data-ttu-id="b8347-118">Módosítsa a **Hardverprofil** mező értékét **HW002** értékről **HW001** értékre, majd válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b8347-118">Change the value of the **Hardware profile** field from **HW002** to **HW001**, and then select **Save**.</span></span>
4. <span data-ttu-id="b8347-119">A módosítások szinkronizálásához nyissa meg a **Retail és Commerce \> Retail és Commerce IT \> Elosztási ütemezés** menüpontot.</span><span class="sxs-lookup"><span data-stu-id="b8347-119">To synchronize the changes, go to **Retail and Commerce \> Retail and Commerce IT \> Distribution schedule**.</span></span>
5. <span data-ttu-id="b8347-120">Válassza ki az **1090** elosztási ütemezést, majd válassza a műveleti panelen a **Futtatás most** parancsot.</span><span class="sxs-lookup"><span data-stu-id="b8347-120">Select distribution schedule **1090**, and then, on the Action Pane, select **Run now**.</span></span>
6. <span data-ttu-id="b8347-121">Válassza az **Igen** lehetőséget, majd kattintson az **OK** gombra az adatszinkronizálás kezdeményezéséhez.</span><span class="sxs-lookup"><span data-stu-id="b8347-121">Select **Yes** and then **OK** to initiate data synchronization.</span></span> 

### <a name="install-modern-pos"></a><span data-ttu-id="b8347-122">Modern POS telepítése</span><span class="sxs-lookup"><span data-stu-id="b8347-122">Install Modern POS</span></span>

1. <span data-ttu-id="b8347-123">Ugorjon a **Kiskereskedelem és kereskedelem \> Csatorna beállítása \> Pénztár beállítása \> Eszközök** pontra.</span><span class="sxs-lookup"><span data-stu-id="b8347-123">Go to **Retail and Commerce \> Channel setup \> POS setup \> Devices**.</span></span>
2. <span data-ttu-id="b8347-124">Válassza ki a **SANFRANCIS-5** eszközt.</span><span class="sxs-lookup"><span data-stu-id="b8347-124">Select device **SANFRANCIS-5**.</span></span>
3. <span data-ttu-id="b8347-125">A műveleti ablaktáblán válassza a **Letöltés**, majd a **Konfigurációs fájl** elemet.</span><span class="sxs-lookup"><span data-stu-id="b8347-125">On the Action Pane, select **Download**, and then select **Configuration file**.</span></span>
4. <span data-ttu-id="b8347-126">Válassza a **Letöltés**, majd a **Retail Modern POS** elemet.</span><span class="sxs-lookup"><span data-stu-id="b8347-126">Select **Download**, and then select **Retail Modern POS**.</span></span> 
5. <span data-ttu-id="b8347-127">Amikor a **ModernPOSSetup.exe** fájl letöltése befejeződött, válassza a **Fájl megnyitása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b8347-127">When download of the **ModernPOSSetup.exe** file is completed, select **Open file**.</span></span>

    ![Fájl megnyitása](./dev-itpro/media/PAYMENTS/openfile.png)

6. <span data-ttu-id="b8347-129">Válassza a **Következő** elemet a telepítési folyamat végrehajtásához.</span><span class="sxs-lookup"><span data-stu-id="b8347-129">Select **Next** to go through the installation process.</span></span> <span data-ttu-id="b8347-130">Ha a telepítés befejeződött, válassza a **Bezárás** elemet.</span><span class="sxs-lookup"><span data-stu-id="b8347-130">When installation is completed, select **Close**.</span></span>

### <a name="activate-modern-pos"></a><span data-ttu-id="b8347-131">Modern POS aktiválása</span><span class="sxs-lookup"><span data-stu-id="b8347-131">Activate Modern POS</span></span>

1. <span data-ttu-id="b8347-132">A Windows asztalon válassza a **Start** gombot, és gépelje be a **Retail Modern POS** nevét.</span><span class="sxs-lookup"><span data-stu-id="b8347-132">On the Windows desktop, select the **Start** button, and enter **Retail Modern POS**.</span></span>
2. <span data-ttu-id="b8347-133">Az aktiválás indításához válassza a **Retail Modern POS** alkalmazást.</span><span class="sxs-lookup"><span data-stu-id="b8347-133">Select the **Retail Modern POS** application to initiate activation.</span></span>
3. <span data-ttu-id="b8347-134">Válassza ki **Következő** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b8347-134">Select **Next**.</span></span> <span data-ttu-id="b8347-135">A **Kiszolgáló URL-címe**, **Eszközazonosító** és **Pénztárgép száma** mezőket a rendszernek előzetesen be kell állítania az előző eljárásban letöltött konfigurációs fájlból származó adatokkal.</span><span class="sxs-lookup"><span data-stu-id="b8347-135">The **Server URL**, **Device ID**, and **Register number** fields should be preset by using information from the configuration file that you downloaded in the previous procedure.</span></span>
4. <span data-ttu-id="b8347-136">Válassza az **Aktiválás** lehetõséget.</span><span class="sxs-lookup"><span data-stu-id="b8347-136">Select **Activate**.</span></span>
5. <span data-ttu-id="b8347-137">Megjelenik egy hitelesítési párbeszédpanel.</span><span class="sxs-lookup"><span data-stu-id="b8347-137">An authentication dialog box appears.</span></span> <span data-ttu-id="b8347-138">Válassza ki azt a számlát, amely korábban a **000713 – Andrew Collette** nevű dolgozóhoz társított e-mail-címet használja.</span><span class="sxs-lookup"><span data-stu-id="b8347-138">Select the account that uses the email address that was previously associated with worker **000713 - Andrew Collette**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b8347-139">Ha még nem társított egy dolgozót az identitásához, az aktiválás sikertelen lesz.</span><span class="sxs-lookup"><span data-stu-id="b8347-139">If you haven't yet associated a worker with your identity, activation will be unsuccessful.</span></span> <span data-ttu-id="b8347-140">Ebben az esetben kövesse a „Dolgozó társítása az identitásához” szakaszban leírt lépéseket a [Dynamics 365 Commerce értékelési környezete konfigurálása](cpe-post-provisioning.md#associate-a-worker-with-your-identity) témakörben.</span><span class="sxs-lookup"><span data-stu-id="b8347-140">In this case, follow the steps under the "Associate a worker with your identity" section in the [Configure a Dynamics 365 Commerce evaluation environment](cpe-post-provisioning.md#associate-a-worker-with-your-identity) topic.</span></span>
    
6. <span data-ttu-id="b8347-141">Amikor a program rákérdez, hogy engedélyezze a szervezetnek az eszköz kezelését, válassza a **Csak ez az alkalmazás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b8347-141">When you're prompted to let your organization manage the device, select **This app only**.</span></span>
7. <span data-ttu-id="b8347-142">Az aktiválás befejezését követően válassza az **Indítás** elemet.</span><span class="sxs-lookup"><span data-stu-id="b8347-142">When activation is completed, select **Get started**.</span></span>

### <a name="enable-bopis-in-modern-pos"></a><span data-ttu-id="b8347-143">BOPIS engedélyezése a Modern POS rendszerben</span><span class="sxs-lookup"><span data-stu-id="b8347-143">Enable BOPIS in Modern POS</span></span>

1. <span data-ttu-id="b8347-144">Jelentkezzen be a Modern POS alkalmazásba a **000713** operátorazonosítóval és **123** jelszóval.</span><span class="sxs-lookup"><span data-stu-id="b8347-144">Sign in to Modern POS by using **000713** as the operator ID and **123** as the password.</span></span>
2. <span data-ttu-id="b8347-145">A bevezető útmutató videó lejátszása közben válassza a párbeszédablak bal alsó sarkában található két jelölőnégyzetet, majd zárja be a párbeszédablakot.</span><span class="sxs-lookup"><span data-stu-id="b8347-145">While the introductory walkthrough video is playing, select the two check boxes in the lower-left corner of the dialog box, and then close the dialog box.</span></span>
3. <span data-ttu-id="b8347-146">Ha a rendszer nem kéri fel a műszak lezárására, görgessen jobbra az **Üdvözlőlap** oldalon, válassza a **Műszak lezárása**, majd jelentkezzen be a pénztárba.</span><span class="sxs-lookup"><span data-stu-id="b8347-146">If you aren't prompted to close the shift, scroll to the right on the **Welcome** page, select **Close shift**, and then sign back in to the POS.</span></span>
4. <span data-ttu-id="b8347-147">Miután bejelentkezett a rendszerbe, a rákérdezéskor válassza a **Nem pénztárgépfiókkal kapcsolatos művelet végrehajtása** elemet.</span><span class="sxs-lookup"><span data-stu-id="b8347-147">After you're signed in, when you're prompted, select **Perform a non-drawer operation**.</span></span>
5. <span data-ttu-id="b8347-148">Az **Üdvözlőlap** oldalon görgessen jobbra, és válassza a **Hardverállomás kiválasztása** műveletet.</span><span class="sxs-lookup"><span data-stu-id="b8347-148">On the **Welcome** page, scroll to the right, and select the **Select hardware station** operation.</span></span>
6. <span data-ttu-id="b8347-149">Válassza a **Kezelés** lehetőséget, majd állítsa a **Hardverállomás használata** beállítást **Be** értékre, majd válassza az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b8347-149">Select **Manage**, set the **Use hardware station** option to **On**, and then select **OK**.</span></span>
7. <span data-ttu-id="b8347-150">Jelentkezzen ki a pénztárból, majd ismét jelentkezzen be.</span><span class="sxs-lookup"><span data-stu-id="b8347-150">Sign out of the POS, and then sign back in.</span></span>
8. <span data-ttu-id="b8347-151">Miután bejelentkezett, válassza az **Új műszak megnyitása** lehetőséget,majd válassza a **Pénztárgépfiók** elemet.</span><span class="sxs-lookup"><span data-stu-id="b8347-151">After you're signed in, select **Open a new shift**, and then select **Drawer**.</span></span>

## <a name="complete-a-bopis-scenario"></a><span data-ttu-id="b8347-152">BOPIS-eset végrehajtása</span><span class="sxs-lookup"><span data-stu-id="b8347-152">Complete a BOPIS scenario</span></span>

### <a name="create-a-storefront-order-for-in-store-pickup"></a><span data-ttu-id="b8347-153">Üzleti megrendelés létrehozása üzletbeli felvételhez</span><span class="sxs-lookup"><span data-stu-id="b8347-153">Create a storefront order for in-store pickup</span></span>

1. <span data-ttu-id="b8347-154">Nyissa meg az [E-kereskedelem indítása](https://docs.microsoft.com/dynamics365/commerce/provisioning-guide#initialize-e-commerce) lépésben a környezet konfigurációja során megadott URL-címet.</span><span class="sxs-lookup"><span data-stu-id="b8347-154">Go to the URL that you specified in the [Initialize e-Commerce](https://docs.microsoft.com/dynamics365/commerce/provisioning-guide#initialize-e-commerce) step during environment configuration.</span></span>
2. <span data-ttu-id="b8347-155">Válasszon egy cikket, majd válassza a **Hozzáadás a kosárhoz** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b8347-155">Select an item, and select **Add to cart**.</span></span>
3. <span data-ttu-id="b8347-156">A bevásárlótáska oldalon válassza az utoljára hozzáadott rendelési sorhoz tartozó **Cikk felvétele** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b8347-156">On the shopping bag page, select **Pick this up** for the order line that you just added.</span></span>
4. <span data-ttu-id="b8347-157">Az **Üzlet kiválasztása** párbeszédablakban adja meg a **San Francisco** értéket, majd válassza a **Keresés** gombot.</span><span class="sxs-lookup"><span data-stu-id="b8347-157">In the **Select a store** dialog box, enter **San Francisco**, and then select the **Search** button.</span></span>
5. <span data-ttu-id="b8347-158">A találatok listájában keresse meg a san franciscói üzletet, és válassza a **Felvétel itt** elemet.</span><span class="sxs-lookup"><span data-stu-id="b8347-158">In the list of results, find the San Francisco store, and select **Pick up here**.</span></span>
6. <span data-ttu-id="b8347-159">A bevásárlótáska oldalon válassza a **Fizetés vendégként**.</span><span class="sxs-lookup"><span data-stu-id="b8347-159">On the shopping bag page, select **Checkout as Guest**.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="b8347-160">A fizetés folytatásához el kell fogadnia a cookie-kről szóló értesítést.</span><span class="sxs-lookup"><span data-stu-id="b8347-160">To continue with checkout, you must accept the cookie notice.</span></span> <span data-ttu-id="b8347-161">A fizetés lap tetején egy értesítés jelenik meg szalagcímként.</span><span class="sxs-lookup"><span data-stu-id="b8347-161">This notice appears as a banner at the top of the checkout page.</span></span>

7. <span data-ttu-id="b8347-162">A hitelkártyás fizetési módnál adja meg az alábbi adatokat:</span><span class="sxs-lookup"><span data-stu-id="b8347-162">For the credit card payment method, enter the following details:</span></span>

    - <span data-ttu-id="b8347-163">**Kártyatulajdonos neve:** Adjon meg bármilyen nevet.</span><span class="sxs-lookup"><span data-stu-id="b8347-163">**Cardholder name:** Enter any name.</span></span>
    - <span data-ttu-id="b8347-164">**Kártyaszám:** Adja meg a **4111-1111-1111-1111** számot.</span><span class="sxs-lookup"><span data-stu-id="b8347-164">**Card number:** Enter **4111-1111-1111-1111**.</span></span>
    - <span data-ttu-id="b8347-165">**Lejárati dátum:** Adja meg: **10/20**.</span><span class="sxs-lookup"><span data-stu-id="b8347-165">**Expiration date:** Enter **10/20**.</span></span>
    - <span data-ttu-id="b8347-166">**Kártyaellenőrző kód (CVV):** Adja meg: **737**.</span><span class="sxs-lookup"><span data-stu-id="b8347-166">**Card verification value (CVV) code:** Enter **737**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="b8347-167">Semmilyen körülmények között ne próbáljon ki tényleges hitelkártya-adatokat a tesztoldalon.</span><span class="sxs-lookup"><span data-stu-id="b8347-167">Never, under any circumstances, try to use actual credit card information on the test site.</span></span>

8. <span data-ttu-id="b8347-168">Folytassa a fizetést a számlázási cím megadásával, majd válassza a **Mentés és folytatás** elemet.</span><span class="sxs-lookup"><span data-stu-id="b8347-168">Continue with checkout by entering details of the billing address, and then select **Save and continue**.</span></span>
9. <span data-ttu-id="b8347-169">Amikor készen áll a rendelés elküldésére, válassza a **Fizetés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b8347-169">When the order is ready to be placed, select **Checkout**.</span></span>

### <a name="synchronize-online-orders-to-the-back-office"></a><span data-ttu-id="b8347-170">Online rendelések szinkronizálása a háttérirodával</span><span class="sxs-lookup"><span data-stu-id="b8347-170">Synchronize online orders to the back office</span></span>

<span data-ttu-id="b8347-171">Az online rendelések szinkronizálásának módjával kapcsolatos információkért lásd: [Online értékesítések és kifizetések feladása](https://docs.microsoft.com/dynamics365/commerce/tasks/posting-online-sales-payments).</span><span class="sxs-lookup"><span data-stu-id="b8347-171">For information about how to synchronize online orders, see [Posting of online sales and payments](https://docs.microsoft.com/dynamics365/commerce/tasks/posting-online-sales-payments).</span></span>

### <a name="pick-up-an-order-in-the-store"></a><span data-ttu-id="b8347-172">Megrendelés felvéle az üzletben</span><span class="sxs-lookup"><span data-stu-id="b8347-172">Pick up an order in the store</span></span>

1. <span data-ttu-id="b8347-173">Bejelentkezés a pénztárba.</span><span class="sxs-lookup"><span data-stu-id="b8347-173">Sign in to the POS.</span></span>
2. <span data-ttu-id="b8347-174">Az **Üdvözlőlap** képernyőn válassza a **Rendelés teljesítése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b8347-174">On the **Welcome** screen, select **Order fulfillment**</span></span>
3. <span data-ttu-id="b8347-175">A felvehető cikkek listájában válassza az online elküldött megrendeléshez tartozó sort.</span><span class="sxs-lookup"><span data-stu-id="b8347-175">In the list of items for pickup, select the line from the order that was placed online.</span></span>
4. <span data-ttu-id="b8347-176">Miközben a rendelési sor ki van választva, válassza a **Felvétel** elemet.</span><span class="sxs-lookup"><span data-stu-id="b8347-176">While the order line is selected, select **Pick up**.</span></span>

    <span data-ttu-id="b8347-177">A sorcikket a rendszer hozzáadja a tranzakciós képernyőhöz, és az esedékes egyenlegnél **0,00 $** szerepel.</span><span class="sxs-lookup"><span data-stu-id="b8347-177">The line item is added to the transaction screen, and **$0.00** is shown as the balance that is due.</span></span>

5. <span data-ttu-id="b8347-178">Válassza a **0,00 $** értékű esedékes egyenleget, vagy válasszon bármilyen fizetési módot a tranzakció megkötéséhez.</span><span class="sxs-lookup"><span data-stu-id="b8347-178">Select the balance due of **$0.00**, or select any payment method to conclude the transaction.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="b8347-179">Hibaelhárítás</span><span class="sxs-lookup"><span data-stu-id="b8347-179">Troubleshooting</span></span>

### <a name="online-orders-that-are-retrieved-in-the-pos-have-a-non-zero-balance-due"></a><span data-ttu-id="b8347-180">A pénztárban beolvasott online rendelések nem 0 értékű esedékes egyenleggel rendelkeznek</span><span class="sxs-lookup"><span data-stu-id="b8347-180">Online orders that are retrieved in the POS have a non-zero balance due</span></span>

<span data-ttu-id="b8347-181">Ha egy rendelést üzletben való felvételre olvastak be, és az egyenleg nem 0 (nulla), ellenőrizze, hogy a Modern POS-t használják, és a hardverállomás aktív.</span><span class="sxs-lookup"><span data-stu-id="b8347-181">When an order is retrieved for in-store pickup, if the balance due isn't 0 (zero), make sure that Modern POS is being used, and that the hardware station is active.</span></span> <span data-ttu-id="b8347-182">Ha Cloud POS vagy Modern POS van használatban iOS rendszeren, ellenőrizze, hogy a megosztott hardverállomás aktív.</span><span class="sxs-lookup"><span data-stu-id="b8347-182">If Cloud POS or Modern POS for iOS is being used, make sure that a shared hardware station is active.</span></span> <span data-ttu-id="b8347-183">Az online végzett fizetésekhez beolvasásához valamilyen típusú aktív hardverállomás szükséges.</span><span class="sxs-lookup"><span data-stu-id="b8347-183">Some form of active hardware station is required to retrieve payments that were made online.</span></span>

### <a name="general-issues-with-payment-capture"></a><span data-ttu-id="b8347-184">Általános problémák a kifizetés rögzítésével</span><span class="sxs-lookup"><span data-stu-id="b8347-184">General issues with payment capture</span></span>

<span data-ttu-id="b8347-185">Minden általános probléma esetén első lépésként mindig tekintse át a Modern POS vagy az Internet Information Services (IIS) hardverállomás eseménynaplóit.</span><span class="sxs-lookup"><span data-stu-id="b8347-185">For all general issues, you should always consult the Modern POS or Internet Information Services (IIS) Hardware Station event logs as a first step.</span></span> <span data-ttu-id="b8347-186">Ezeket a naplókat a Windows eseménynaplókban a következő csomópontokban találja:</span><span class="sxs-lookup"><span data-stu-id="b8347-186">You can find these logs under the following nodes in the Windows event log:</span></span>

- <span data-ttu-id="b8347-187">Alkalmazási és szolgáltatási naplók \> Microsoft \> Dynamics \> Commerce-ModernPOS</span><span class="sxs-lookup"><span data-stu-id="b8347-187">Application and Services Logs \> Microsoft \> Dynamics \> Commerce-ModernPOS</span></span>
- <span data-ttu-id="b8347-188">Alkalmazási és szolgáltatási naplók \> Microsoft \> Dynamics \> Commerce-hardverállomás</span><span class="sxs-lookup"><span data-stu-id="b8347-188">Application and Services Logs \> Microsoft \> Dynamics \> Commerce-Hardware Station</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b8347-189">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="b8347-189">Additional resources</span></span>

[<span data-ttu-id="b8347-190">Dynamics 365 Commerce értékelési környezet áttekintése</span><span class="sxs-lookup"><span data-stu-id="b8347-190">Dynamics 365 Commerce evaluation environment overview</span></span>](cpe-overview.md)

[<span data-ttu-id="b8347-191">Dynamics 365 Commerce értékelési környezet kiépítése</span><span class="sxs-lookup"><span data-stu-id="b8347-191">Provision a Dynamics 365 Commerce evaluation environment</span></span>](provisioning-guide.md)

[<span data-ttu-id="b8347-192">Dynamics 365 Commerce értékelési környezet választható funkcióinak konfigurálása</span><span class="sxs-lookup"><span data-stu-id="b8347-192">Configure optional features for a Dynamics 365 Commerce evaluation environment</span></span>](cpe-optional-features.md)

[<span data-ttu-id="b8347-193">Dynamics 365 Commerce értékelési környezet GYIK</span><span class="sxs-lookup"><span data-stu-id="b8347-193">Dynamics 365 Commerce evaluation environment FAQ</span></span>](cpe-faq.md)

[<span data-ttu-id="b8347-194">Microsoft Lifecycle Services (LCS)</span><span class="sxs-lookup"><span data-stu-id="b8347-194">Microsoft Lifecycle Services (LCS)</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide)

[<span data-ttu-id="b8347-195">Retail Cloud Scale Unit (RCSU)</span><span class="sxs-lookup"><span data-stu-id="b8347-195">Retail Cloud Scale Unit (RCSU)</span></span>](https://docs.microsoft.com/business-applications-release-notes/october18/dynamics365-retail/retail-cloud-scale-unit)

[<span data-ttu-id="b8347-196">Microsoft Azure-portál</span><span class="sxs-lookup"><span data-stu-id="b8347-196">Microsoft Azure portal</span></span>](https://azure.microsoft.com/features/azure-portal)

[<span data-ttu-id="b8347-197">Dynamics 365 Commerce-webhely</span><span class="sxs-lookup"><span data-stu-id="b8347-197">Dynamics 365 Commerce website</span></span>](https://aka.ms/Dynamics365CommerceWebsite)

[<span data-ttu-id="b8347-198">Adyen fizetési összekötő</span><span class="sxs-lookup"><span data-stu-id="b8347-198">Adyen payment connector</span></span>](https://docs.microsoft.com/dynamics365/commerce/dev-itpro/adyen-connector?tabs=8-1-3)

[<span data-ttu-id="b8347-199">Online fizetési eszközök mentése az Adyen összekötővel</span><span class="sxs-lookup"><span data-stu-id="b8347-199">Saving online payment instruments with the Adyen connector</span></span>](https://docs.microsoft.com/dynamics365/commerce/dev-itpro/adyen-connector-listpi)

[<span data-ttu-id="b8347-200">Többcsatornás fizetések áttekintése</span><span class="sxs-lookup"><span data-stu-id="b8347-200">Omni-channel payments overview</span></span>](https://docs.microsoft.com/dynamics365/commerce/omni-channel-payments)
