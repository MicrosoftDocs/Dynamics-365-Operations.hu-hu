---
title: Online rendeléses és aszinkron vevői rendeléses tranzakciók szerkesztése és auditálása
description: Ez a témakör azt ismerteti, hogy miként szerkesztheti és auditálhatja az online rendeléses és aszinkron vevői rendeléses tranzakciókat a Microsoft Dynamics 365 Commerce szolgáltatásban.
author: josaw1
manager: AnnBe
ms.date: 11/04/2020
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2018-11-15
ms.dyn365.ops.version: ''
ms.openlocfilehash: 0fee5ef7ad61e9581e7b2797bb1bd26b1a48ddbd
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5221774"
---
# <a name="edit-and-audit-online-order-and-asynchronous-customer-order-transactions"></a><span data-ttu-id="0d47d-103">Online rendeléses és aszinkron vevői rendeléses tranzakciók szerkesztése és auditálása</span><span class="sxs-lookup"><span data-stu-id="0d47d-103">Edit and audit online order and asynchronous customer order transactions</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0d47d-104">Ez a témakör azt ismerteti, hogy miként szerkesztheti és auditálhatja az online rendeléses és aszinkron vevői rendeléses tranzakciókat a Microsoft Dynamics 365 Commerce szolgáltatásban.</span><span class="sxs-lookup"><span data-stu-id="0d47d-104">This topic describes how to edit and audit online order and asynchronous customer order transactions in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="0d47d-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="0d47d-105">Overview</span></span>

<span data-ttu-id="0d47d-106">A 10.0.5-ös és 10.0.6-os Commerce verziók között hozzáadták a készpénzzel fizetett, azonnal átvett tranzakciók (például értékesítés és visszaküldés) és a készpénzkezelési tranzakciók (például váltópénz betétele és fizetőeszköz kivétele) szerkesztésének támogatását.</span><span class="sxs-lookup"><span data-stu-id="0d47d-106">Between Commerce versions 10.0.5 and 10.0.6, support was added for editing cash and carry transactions (such as sales and returns) and cash management transactions (such as float entry and tender removal).</span></span> <span data-ttu-id="0d47d-107">A Commerce 10.0.7-es verziója az online rendeléses tranzakciók és az aszinkron vevői rendeléses tranzakciók szerkesztését is támogatja.</span><span class="sxs-lookup"><span data-stu-id="0d47d-107">In Commerce version 10.0.7, support was added for editing online order transactions and asynchronous customer order transactions.</span></span>

## <a name="edit-and-audit-order-transactions"></a><span data-ttu-id="0d47d-108">Rendelési tranzakciók szerkesztése és auditálása</span><span class="sxs-lookup"><span data-stu-id="0d47d-108">Edit and audit order transactions</span></span>

<span data-ttu-id="0d47d-109">A rendelési tranzakciók szerkesztéséhez és auditálásához a Commerce központi felületén kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="0d47d-109">To edit and audit order transactions in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="0d47d-110">Telepítse a [Microsoft Dynamics Office Add-in](https://appsource.microsoft.com/product/office/WA104379629?tab=Overview) programot.</span><span class="sxs-lookup"><span data-stu-id="0d47d-110">Install the [Microsoft Dynamics Office Add-in](https://appsource.microsoft.com/product/office/WA104379629?tab=Overview).</span></span>
1. <span data-ttu-id="0d47d-111">A **Kiskereskedelmi paraméterek** lap **Vevői rendelések** lapfülén, a **Rendelés** gyorslapon adjon meg egy várakoztatási kódot a **Rendelésszinkronizálási hibák várakoztatási kódja** pont alatt.</span><span class="sxs-lookup"><span data-stu-id="0d47d-111">On the **Retail parameters** page, on the **Customer orders** tab, on the **Order** FastTab, specify a hold code for **Hold code for order synchronization errors**.</span></span>
1. <span data-ttu-id="0d47d-112">Nyissa meg az **Üzlet pénzügyi adatai** munkaterületet.</span><span class="sxs-lookup"><span data-stu-id="0d47d-112">Open the **Store financials** workspace.</span></span> <span data-ttu-id="0d47d-113">Az **Online rendelések szinkronizálási hibái** és a **Vevői rendelések szinkronizálási hibái** csempék előre szűrt nézetet biztosítanak a kiskereskedelmi tranzakciólapról.</span><span class="sxs-lookup"><span data-stu-id="0d47d-113">The **Online order synchronization errors** and **Customer order synchronization errors** tiles provide a prefiltered view of the retail transaction page.</span></span> <span data-ttu-id="0d47d-114">Mindegyik azokat a tranzakciórekordokat jeleníti meg, amelyek szinkronizálása sikertelen volt a megfelelő rendeléstípus esetében.</span><span class="sxs-lookup"><span data-stu-id="0d47d-114">Each shows the transaction records that have failed synchronization for the corresponding order type.</span></span>
1. <span data-ttu-id="0d47d-115">Nyissa meg az **Online rendelések szinkronizálási hibái** vagy a **Vevői rendelések szinkronizálási hibái** lapot.</span><span class="sxs-lookup"><span data-stu-id="0d47d-115">Open either the **Online order synchronization errors** page or the **Customer order synchronization errors** page.</span></span> <span data-ttu-id="0d47d-116">Jelöljön ki egy rekordot a szinkronizálási hiba részleteinek megtekintéséhez.</span><span class="sxs-lookup"><span data-stu-id="0d47d-116">Select a record to view the synchronization error details.</span></span> <span data-ttu-id="0d47d-117">A **Szinkronizálás állapota** gyorslap a következő hibaadatokat tartalmazza:</span><span class="sxs-lookup"><span data-stu-id="0d47d-117">The **Synchronization status** FastTab provides the following error details:</span></span>

    - <span data-ttu-id="0d47d-118">Függő rendelési állapot</span><span class="sxs-lookup"><span data-stu-id="0d47d-118">Pending order status</span></span>
    - <span data-ttu-id="0d47d-119">Rendelési hiba részletei</span><span class="sxs-lookup"><span data-stu-id="0d47d-119">Order error details</span></span>
    - <span data-ttu-id="0d47d-120">Módosítás dátuma és időpontja</span><span class="sxs-lookup"><span data-stu-id="0d47d-120">Modified date and time</span></span>
    - <span data-ttu-id="0d47d-121">Újrapróbálkozások száma</span><span class="sxs-lookup"><span data-stu-id="0d47d-121">Retry count</span></span>

1. <span data-ttu-id="0d47d-122">Ha a hiba részletei azt jelzik, hogy a rekordot ki kell javítani, válassza az **Office-bővítmény**, majd a **Kijelölt tranzakció szerkesztése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0d47d-122">If the error details indicate that the record must be fixed, select **Office Add in**, and then select **Edit selected transaction**.</span></span> <span data-ttu-id="0d47d-123">Megnyílik egy Excel-fájl, amely a kijelölt tranzakció részleteit mutatja.</span><span class="sxs-lookup"><span data-stu-id="0d47d-123">An Excel file that shows the details of the selected transaction is opened.</span></span>

    - <span data-ttu-id="0d47d-124">Ha a szerkesztett tranzakció online rendelési tranzakció, az Excel-fájl a következő munkalapokat tartalmazza:</span><span class="sxs-lookup"><span data-stu-id="0d47d-124">If the transaction that is being edited is an online order transaction, the Excel file contains the following worksheets:</span></span>

        - <span data-ttu-id="0d47d-125">**Tranzakció** – Ezen a munkalapon szerepelnek a tranzakció fejlécadatai.</span><span class="sxs-lookup"><span data-stu-id="0d47d-125">**Transaction** – This worksheet has the header details for the transaction.</span></span>
        - <span data-ttu-id="0d47d-126">**Értékesítési tranzakció** – Ezen a munkalapon szerepelnek a tranzakció soradatai.</span><span class="sxs-lookup"><span data-stu-id="0d47d-126">**Sales transaction** – This worksheet has the line details for the transaction.</span></span>
        - <span data-ttu-id="0d47d-127">**Fizetési tranzakciók** – Ez a munkalap a tranzakció fizetési sorainak részleteit tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="0d47d-127">**Payment transactions** – This worksheet has the details of the payment lines for the transaction.</span></span>
        - <span data-ttu-id="0d47d-128">**Engedményes tranzakciók** – Ezen a munkalapon szerepelnek a tranzakció engedménnyel kapcsolatos részletei.</span><span class="sxs-lookup"><span data-stu-id="0d47d-128">**Discount transactions** – This worksheet has the discount-related details for the transaction.</span></span>
        - <span data-ttu-id="0d47d-129">**Adótranzakciók** – Ezen a munkalapon szerepelnek a tranzakció adókkal kapcsolatos részletei.</span><span class="sxs-lookup"><span data-stu-id="0d47d-129">**Tax transactions** – This worksheet has the tax-related details for the transaction.</span></span>
        - <span data-ttu-id="0d47d-130">**Költségtranzakciók** – Ezen a munkalapon szerepelnek a tranzakció költségekkel kapcsolatos adatai.</span><span class="sxs-lookup"><span data-stu-id="0d47d-130">**Charges transactions** – This worksheet has the charges-related data for the transaction.</span></span>

    - <span data-ttu-id="0d47d-131">Ha a szerkesztett tranzakció aszinkron vevői rendeléses tranzakció, az Excel-fájl a következő munkalapokat tartalmazza:</span><span class="sxs-lookup"><span data-stu-id="0d47d-131">If the transaction that is being edited is an asynchronous customer order transaction, the Excel file contains the following worksheets:</span></span>

        - <span data-ttu-id="0d47d-132">**Sorok** – Ezen a munkalapon szerepelnek a tranzakció fejléc- és soradatai.</span><span class="sxs-lookup"><span data-stu-id="0d47d-132">**Lines** – This worksheet has the header and line details for the transaction.</span></span>
        - <span data-ttu-id="0d47d-133">**Fizetések** – Ez a munkalap a tranzakció fizetési sorainak részleteit tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="0d47d-133">**Payments** – This worksheet has the details of the payment lines for the transaction.</span></span>
        - <span data-ttu-id="0d47d-134">**Engedmények** – Ezen a munkalapon szerepelnek a tranzakció engedménnyel kapcsolatos részletei.</span><span class="sxs-lookup"><span data-stu-id="0d47d-134">**Discounts** – This worksheet has the discount-related details for the transaction.</span></span>
        - <span data-ttu-id="0d47d-135">**Adók** – Ezen a munkalapon szerepelnek a tranzakció adókkal kapcsolatos részletei.</span><span class="sxs-lookup"><span data-stu-id="0d47d-135">**Taxes** – This worksheet has the tax-related details for the transaction.</span></span>
        - <span data-ttu-id="0d47d-136">**Költségek** – Ezen a munkalapon szerepelnek a tranzakció költségekkel kapcsolatos adatai.</span><span class="sxs-lookup"><span data-stu-id="0d47d-136">**Charges** – This worksheet has the charges-related data for the transaction.</span></span>

1. <span data-ttu-id="0d47d-137">Az Excel-fájl **Függő rendelési állapot** mezőjébe írja be a **Szerkesztés** parancsot, majd tegye közzé a módosítást.</span><span class="sxs-lookup"><span data-stu-id="0d47d-137">In the Excel file, in the **Pending order status** field, enter **Editing**, and then publish the change.</span></span> <span data-ttu-id="0d47d-138">Így megakadályozhatja, hogy a kötegelt módban futó **Rendelés szinkronizálása** feladat kihagyja ezt a rekordot a feldolgozás során.</span><span class="sxs-lookup"><span data-stu-id="0d47d-138">In this way, you prevent the **Synchronize order** job that is running in batch mode from skipping this record during processing.</span></span>
1. <span data-ttu-id="0d47d-139">Az Excel-fájlban módosítsa a megfelelő mezőket, majd töltse vissza az adatokat a Commerce központi felületére a Dynamics Excel-bővítmény közzétételi funkciója segítségével.</span><span class="sxs-lookup"><span data-stu-id="0d47d-139">In the Excel file, modify the appropriate fields, and then upload the data back into Commerce headquarters by using the publishing functionality of the Dynamics Excel Add-in.</span></span> <span data-ttu-id="0d47d-140">Az adatok közzététel után a módosítások a rendszerben is megjelennek.</span><span class="sxs-lookup"><span data-stu-id="0d47d-140">After the data is published, the changes will be reflected in the system.</span></span> <span data-ttu-id="0d47d-141">A közzététel során a rendszer nem végez ellenőrzést a felhasználó által végrehajtott módosításokra.</span><span class="sxs-lookup"><span data-stu-id="0d47d-141">During publication, no validation is done for changes that users make.</span></span>
1. <span data-ttu-id="0d47d-142">A módosítások teljeskörű auditnaplóját megtekintheti, ha kiválasztja a **Kiskereskedelmi tranzakció** fejlécben (fejlécszintű adatok esetén) vagy az adott tranzakció oldalán a megfelelő szakaszban és rekordnál az **Auditnapló megtekintése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0d47d-142">You can view a complete audit trail of the changes by selecting **View audit trail** in the **Retail transaction** header for the header-level changes, and in the relevant section and record on the appropriate transaction page.</span></span> <span data-ttu-id="0d47d-143">Például az értékesítési sorokhoz kapcsolódó összes változás megjelenik az **Értékesítési tranzakciók** lapon, és a kifizetésekhez kapcsolódó összes változás megjelenik a **Fizetési tranzakciók** lapon.</span><span class="sxs-lookup"><span data-stu-id="0d47d-143">For example, all changes that are related to sales lines will be shown on the **Sales transactions** page, and all changes that are related to payments will be shown on the **Payment transactions** page.</span></span> <span data-ttu-id="0d47d-144">A módosításokra vonatkozóan a következő auditadatokat tartjuk meg:</span><span class="sxs-lookup"><span data-stu-id="0d47d-144">The following audit details are maintained for the changes:</span></span>

    - <span data-ttu-id="0d47d-145">Módosítás dátuma és időpontja</span><span class="sxs-lookup"><span data-stu-id="0d47d-145">Modified date and time</span></span>
    - <span data-ttu-id="0d47d-146">Mező</span><span class="sxs-lookup"><span data-stu-id="0d47d-146">Field</span></span>
    - <span data-ttu-id="0d47d-147">Régi érték</span><span class="sxs-lookup"><span data-stu-id="0d47d-147">Old value</span></span>
    - <span data-ttu-id="0d47d-148">Új érték</span><span class="sxs-lookup"><span data-stu-id="0d47d-148">New value</span></span>
    - <span data-ttu-id="0d47d-149">Módosította</span><span class="sxs-lookup"><span data-stu-id="0d47d-149">Modified by</span></span>

1. <span data-ttu-id="0d47d-150">A módosítások végrehajtása és közzététele után válassza a **Rendelés szinkronizálása** lehetőséget a szinkronizálási folyamat azonnali elindításához.</span><span class="sxs-lookup"><span data-stu-id="0d47d-150">After you've made and published your changes, select **Synchronize order** to immediately start the synchronization process.</span></span> <span data-ttu-id="0d47d-151">Másik lehetőségként megvárhatja, míg a kötegelt módban futó szinkronizálási folyamat feldolgozza a tranzakciót.</span><span class="sxs-lookup"><span data-stu-id="0d47d-151">Alternatively, you can wait for the synchronization process that is running in batch mode to process the transaction.</span></span>

<span data-ttu-id="0d47d-152">Alapértelmezés szerint a rendelések a sikeres szinkronizálása után a Commerce paraméterekben meghatározott várakoztatási kód alapján várakoztatási állapotba kerülnek.</span><span class="sxs-lookup"><span data-stu-id="0d47d-152">By default, after the orders are successfully synced, they are put in a hold status, based on the hold code that is defined in the Commerce parameters.</span></span> <span data-ttu-id="0d47d-153">A rendelések várakoztatását el kell távolítani a rendelések teljesítés vagy egyéb műveletek céljából történő további feldolgozása előtt.</span><span class="sxs-lookup"><span data-stu-id="0d47d-153">The hold on the orders must be removed before the orders can be processed further for fulfillment or other operations.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="0d47d-154">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="0d47d-154">Additional resources</span></span>

[<span data-ttu-id="0d47d-155">Készpénzzel fizetett, azonnal átvett és készpénzkezelési tranzakciók szerkesztése és auditálása</span><span class="sxs-lookup"><span data-stu-id="0d47d-155">Edit and audit cash and carry and cash management transactions</span></span>](edit-cash-trans.md)

[<span data-ttu-id="0d47d-156">Kiskereskedelmi tranzakciók pénzügyi dimenzióinak szerkesztése</span><span class="sxs-lookup"><span data-stu-id="0d47d-156">Edit financial dimensions for retail transactions</span></span>](edit-financial-dim.md)

[<span data-ttu-id="0d47d-157">Excel-munkafüzet létrehozása a kiskereskedelmi tranzakciók szerkesztéséhez</span><span class="sxs-lookup"><span data-stu-id="0d47d-157">Create an Excel workbook to edit retail transactions</span></span>](create-excel-edit.md)

[<span data-ttu-id="0d47d-158">Mezők hozzáadása Excel-munkafüzethez a kiskereskedelmi tranzakciók szerkesztéséhez</span><span class="sxs-lookup"><span data-stu-id="0d47d-158">Add fields to an Excel workbook to edit retail transactions</span></span>](add-fields-excel.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]