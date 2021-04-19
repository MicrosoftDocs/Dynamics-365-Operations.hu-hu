---
title: A B2B e-commerce webhelyekhez használt vevői számlafizetési mód konfigurálása
description: Ez a témakör azt ismerteti, hogyan kell konfigurálni a B2B e-commerce webhelyekhez használt vevői számlafizetési módot.
author: josaw1
ms.date: 01/20/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailOperations
audience: Application User, IT Pro
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: retail
ms.author: josaw
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 62e8f4949dcea1cb201bece171991047ce28da04
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5799805"
---
# <a name="configure-the-customer-account-payment-method-for-b2b-e-commerce-sites"></a><span data-ttu-id="e775b-103">A B2B e-commerce webhelyekhez használt vevői számlafizetési mód konfigurálása</span><span class="sxs-lookup"><span data-stu-id="e775b-103">Configure the customer account payment method for B2B e-commerce sites</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="e775b-104">Ez a témakör azt ismerteti, hogyan kell konfigurálni a B2B e-commerce webhelyekhez használt vevői számlafizetési módot.</span><span class="sxs-lookup"><span data-stu-id="e775b-104">This topic describes how to configure the customer account payment method for business-to-business (B2B) e-commerce sites.</span></span>

<span data-ttu-id="e775b-105">A kiskereskedők különböző típusú kifizetéseket fogadhatnak el e-kereskedelmi csatornán értékesített termékeikért és szolgáltatásaikért.</span><span class="sxs-lookup"><span data-stu-id="e775b-105">Retailers can accept various types of payment in exchange for the products and services that they sell in an e-commerce channel.</span></span> <span data-ttu-id="e775b-106">Minden egyes fizetéstípust, amelyet egy kiskereskedő elfogad, konfigurálni kell a Microsoft Dynamics 365 Commerce rendszer beállításakor.</span><span class="sxs-lookup"><span data-stu-id="e775b-106">Each payment type that a retailer accepts must be configured in Microsoft Dynamics 365 Commerce when the system is set up.</span></span> <span data-ttu-id="e775b-107">A vevői számla (vagy részszámlázás) fizetési módnak támogatottnak kell lennie a B2B e-kereskedelmi webhelyeken.</span><span class="sxs-lookup"><span data-stu-id="e775b-107">The customer account (or "on account") payment method must be supported on B2B e-commerce sites.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="e775b-108">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="e775b-108">Prerequisites</span></span>

1. <span data-ttu-id="e775b-109">Adja hozzá a vevői számlafizetési módot a Commerce központi felületéhez.</span><span class="sxs-lookup"><span data-stu-id="e775b-109">Add the customer account payment method in Commerce headquarters.</span></span>
2. <span data-ttu-id="e775b-110">Társítsa a vevői számlafizetési módot egy e-kereskedelmi csatornához.</span><span class="sxs-lookup"><span data-stu-id="e775b-110">Associate the customer account payment method with the e-commerce channel.</span></span>
3. <span data-ttu-id="e775b-111">Győződjön meg róla, hogy a **Részszámlázás engedélyezése** aktív a vevő számára a **Kiskereskedelem és kereskedelem \> Vevők \> Összes vevő \> Fizetés alapértelmezései** pontban a Commerce központi felületén.</span><span class="sxs-lookup"><span data-stu-id="e775b-111">Make sure that **Allow on account** is enabled for the customer at **Retail and Commerce \> Customers \> All customers \> Payment defaults** in Commerce headquarters.</span></span> <span data-ttu-id="e775b-112">Győződjön meg arról is, hogy a **Hitelkeret** paraméterei megfelelően legyenek beállítva a vevőhöz a **Kiskereskedelem és kereskedelem \> Vevők \> Összes vevő \> Követelések és beszedések** pontban a Commerce központi felületén.</span><span class="sxs-lookup"><span data-stu-id="e775b-112">Also make sure that **Credit limit** parameters are set appropriately for the customer at **Retail and Commerce \> Customers \> All customers \> Credit and Collections** in Commerce headquarters.</span></span> 

## <a name="enable-the-customer-account-payment-method-in-commerce-site-builder"></a><span data-ttu-id="e775b-113">A vevői számlafizetési mód engedélyezése a Commerce webhelykészítőben</span><span class="sxs-lookup"><span data-stu-id="e775b-113">Enable the customer account payment method in Commerce site builder</span></span> 

<span data-ttu-id="e775b-114">A vevői számlafizetési mód Commerce webhelykészítőben való engedélyezéséhez kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="e775b-114">To enable the customer account payment method in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="e775b-115">Lépjen a **Webhelybeállítások \> Bővítmények** pontra.</span><span class="sxs-lookup"><span data-stu-id="e775b-115">Go to **Site Settings \> Extensions**.</span></span>
1. <span data-ttu-id="e775b-116">Állítsa a **Vevői számlafizetések engedélyezése** tulajdonságot **Engedélyezve B2B vevők esetében** értékre.</span><span class="sxs-lookup"><span data-stu-id="e775b-116">Set the **Enable customer account payments** property to **Enabled for B2B customers**.</span></span> 
1. <span data-ttu-id="e775b-117">Válassza a **Mentés és közzététel** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="e775b-117">Select **Save and Publish**.</span></span>

> [!NOTE]
> <span data-ttu-id="e775b-118">Az új webhelybeállítások csak az app.settings.json fájl frissítése után lépnek hatályba.</span><span class="sxs-lookup"><span data-stu-id="e775b-118">The new site settings take effect only after the app.settings.json file is updated.</span></span> <span data-ttu-id="e775b-119">A további tudnivalókat lásd itt: [SDK- és modultár-frissítések](../e-commerce-extensibility/sdk-updates.md).</span><span class="sxs-lookup"><span data-stu-id="e775b-119">For more information, see [SDK and Module library updates](../e-commerce-extensibility/sdk-updates.md).</span></span>

## <a name="enable-the-customer-account-payment-method-on-the-checkout-page-for-the-b2b-e-commerce-site"></a><span data-ttu-id="e775b-120">A vevői számlás fizetési mód engedélyezése a B2B e-kereskedelmi webhely pénztároldalán</span><span class="sxs-lookup"><span data-stu-id="e775b-120">Enable the customer account payment method on the checkout page for the B2B e-commerce site</span></span>

<span data-ttu-id="e775b-121">A vevői számlás fizetési mód B2B e-kereskedelmi webhely pénztároldalán való engedélyezéséhez kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="e775b-121">To enable the customer account payment method on the checkout page for the B2B e-commerce site, follow these steps.</span></span>

1. <span data-ttu-id="e775b-122">A Commerce webhelykészítőben keresse meg és szerkessze a B2B e-kereskedelmi webhely pénztármodulját tartalmazó pénztároldalt vagy töredéket.</span><span class="sxs-lookup"><span data-stu-id="e775b-122">In Commerce site builder, find and edit the checkout page or fragment that contains the checkout module for the B2B e-commerce site.</span></span>
1. <span data-ttu-id="e775b-123">A **Fizetési szakasz tárolója** helyen válassza a **Modul hozzáadása** lehetőséget, majd adjon hozzá egy **Vevői számlafizetés** modult.</span><span class="sxs-lookup"><span data-stu-id="e775b-123">In the **Checkout section container** slot, select **Add Module**, and then add a **Customer account payment** module.</span></span>
1. <span data-ttu-id="e775b-124">A **Vevői számlafizetés** modult úgy pozicionálja, hogy kijelöli a három pontot (**...**), majd a **Felfelé** vagy a **Lefelé** nyíl kiválasztásával állítsa be a pozíciót.</span><span class="sxs-lookup"><span data-stu-id="e775b-124">Position the **Customer account payment** module by selecting the ellipsis (**...**), and then selecting **Move Up** or **Move Down** as required.</span></span>
1. <span data-ttu-id="e775b-125">Válassza a **Mentés** elemet, válassza a **Szerkesztés befejezése** parancsot az oldal ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.</span><span class="sxs-lookup"><span data-stu-id="e775b-125">Select **Save**, select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

## <a name="confirm-that-the-customer-account-payment-method-has-been-enabled-and-published"></a><span data-ttu-id="e775b-126">A vevői számlafizetési mód engedélyezésének és közzétételének megerősítése</span><span class="sxs-lookup"><span data-stu-id="e775b-126">Confirm that the customer account payment method has been enabled and published</span></span>

<span data-ttu-id="e775b-127">A vevői számlafizetési mód engedélyezésének megerősítéséhez kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="e775b-127">To confirm that the customer account payment method has been enabled, follow these steps.</span></span>

1. <span data-ttu-id="e775b-128">Jelentkezzen be az e-kereskedelmi webhelyre.</span><span class="sxs-lookup"><span data-stu-id="e775b-128">Sign in to the e-commerce site.</span></span>
1. <span data-ttu-id="e775b-129">Adjon hozzá egy terméket a kosárhoz.</span><span class="sxs-lookup"><span data-stu-id="e775b-129">Add a product to the cart.</span></span>
1. <span data-ttu-id="e775b-130">Lépjen a pénztároldalra.</span><span class="sxs-lookup"><span data-stu-id="e775b-130">Go to the checkout page.</span></span> <span data-ttu-id="e775b-131">Itt látnia kell az új **Vevői számla** fizetési módot.</span><span class="sxs-lookup"><span data-stu-id="e775b-131">You should see the new **Customer Account** payment method.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="e775b-132">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="e775b-132">Additional resources</span></span>

[<span data-ttu-id="e775b-133">B2B e-kereskedelmi webhely beállítása</span><span class="sxs-lookup"><span data-stu-id="e775b-133">Set up a B2B e-commerce site</span></span>](set-up-b2b-site.md)

[<span data-ttu-id="e775b-134">Szervezeti modellezési hierarchiák létrehozása B2B szervezetek számára</span><span class="sxs-lookup"><span data-stu-id="e775b-134">Create org modeling hierarchies for B2B organizations</span></span>](org-model.md)

[<span data-ttu-id="e775b-135">Üzleti partner típusú felhasználók kezelése a B2B e-kereskedelmi webhelyeken</span><span class="sxs-lookup"><span data-stu-id="e775b-135">Manage business partner users on B2B e-commerce sites</span></span>](manage-b2b-users.md)

[<span data-ttu-id="e775b-136">Termékmennyiség-korlátok beállítása B2B e-kereskedelmi webhelyekhez</span><span class="sxs-lookup"><span data-stu-id="e775b-136">Set product quantity limits for B2B e-commerce sites</span></span>](quantity-limits.md)

[<span data-ttu-id="e775b-137">SDK- és modulkönyvtár-frissítések</span><span class="sxs-lookup"><span data-stu-id="e775b-137">SDK and Module library updates</span></span>](../e-commerce-extensibility/sdk-updates.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]