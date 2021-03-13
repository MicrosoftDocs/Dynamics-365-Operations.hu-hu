---
title: Tranzakciós e-mailek testreszabása kézbesítési mód szerint
description: Ez a témakör azt ismerteti, hogy miként állíthat be egyéni e-mail sablonokat a Microsoft Dynamics 365 Commerce adott értesítési típusaihoz és kézbesítési módjaihoz.
author: stuharg
manager: annbe
ms.date: 11/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: stuharg
ms.search.validFrom: 2020-10-26
ms.dyn365.ops.version: Release 10.0.16
ms.openlocfilehash: f4ecb990cfe792e92142f922c43c71ef8494e117
ms.sourcegitcommit: da17648c296b22d517eadb2f71c7803672e5648d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/19/2021
ms.locfileid: "5031848"
---
# <a name="customize-transactional-emails-by-mode-of-delivery"></a><span data-ttu-id="54ef9-103">Tranzakciós e-mailek testreszabása kézbesítési mód szerint</span><span class="sxs-lookup"><span data-stu-id="54ef9-103">Customize transactional emails by mode of delivery</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="54ef9-104">Ez a témakör azt ismerteti, hogy miként állíthat be egyéni e-mail sablonokat a Microsoft Dynamics 365 Commerce adott értesítési típusaihoz és kézbesítési módjaihoz.</span><span class="sxs-lookup"><span data-stu-id="54ef9-104">This topic describes how to set up custom email templates for specific notification types and modes of delivery in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="54ef9-105">A tranzakciós e-mailek mostantól testreszabhatók egy értesítési típus (például **Rendelés létrehozva**, **Rendelés csomagolva** vagy **Rendelés számlázva**) és egy kézbesítési mód (pl. egynapos, átvétel üzletben, átvétel utcán) kombinációjára vonatkozóan.</span><span class="sxs-lookup"><span data-stu-id="54ef9-105">Transactional emails can now be customized for a combination of a notification type (for example, **Order created**, **Order packed**, or **Order invoiced**) and a mode of delivery (for example, overnight, in-store pickup, or curbside pickup).</span></span> <span data-ttu-id="54ef9-106">Az egyéni tranzakciós e-mailek lehetővé teszik a kiskereskedők számára, hogy ügyfeleik rendeléseinek olyan teljesítési élményeket nyújtsanak, amelyek a megrendelés szállítási módjához igazodnak.</span><span class="sxs-lookup"><span data-stu-id="54ef9-106">Custom transactional emails let retailers provide their customers order with fulfillment experiences that are tailored to the order's mode of delivery.</span></span> <span data-ttu-id="54ef9-107">A "rendelés csomagolva" esemény például testre szabható, így útszéli felvételi utasításokat biztosít azoknak az ügyfeleknek, akik a járdaszéli felvételeket választják.</span><span class="sxs-lookup"><span data-stu-id="54ef9-107">For example, the "order packed" event can be customized so that it provides curbside pickup instructions for customers who choose curbside pickup.</span></span> <span data-ttu-id="54ef9-108">Másik lehetőségként szállítmányozói és szállítási információkat is biztosíthat azoknak az ügyfeleknek, akik úgy döntenek, hogy a rendelésüket szállíttatják.</span><span class="sxs-lookup"><span data-stu-id="54ef9-108">Alternatively, it can provide shipping carrier and delivery information for customers who choose to have their order shipped.</span></span>

> [!NOTE]
> <span data-ttu-id="54ef9-109">A testreszabott tranzakciós e-mailek funkcióinak használatához először be kell kapcsolnia a **Tranzakciós e-mail sablonok testreszabása kézbesítési mód szerint** funkciót a Commerce központ **Munkaterületek \> Funkciókezelés** megnyitásával.</span><span class="sxs-lookup"><span data-stu-id="54ef9-109">To use the functionality for customized transactional emails, you first must turn on the **Customize transactional email templates by mode of delivery** feature by going to **Workspaces \> Feature management** in Commerce headquarters.</span></span>

<span data-ttu-id="54ef9-110">Az e-mailek a következő értesítési típusoknál szabhatók testre a kézbesítési mód szerint:</span><span class="sxs-lookup"><span data-stu-id="54ef9-110">Emails can be customized by mode of delivery for the following notification types:</span></span>

- <span data-ttu-id="54ef9-111">**Rendelés törlése** – Ez az e-mail értesítéstípus új.</span><span class="sxs-lookup"><span data-stu-id="54ef9-111">**Order cancellation** – This email notification type is new.</span></span>
- <span data-ttu-id="54ef9-112">**Rendelés létrehozva**</span><span class="sxs-lookup"><span data-stu-id="54ef9-112">**Order created**</span></span>
- <span data-ttu-id="54ef9-113">**Rendelés visszaigazolva**</span><span class="sxs-lookup"><span data-stu-id="54ef9-113">**Order confirmed**</span></span>
- <span data-ttu-id="54ef9-114">**Rendelés számlázva** – Ez az e-mail értesítéstípus új.</span><span class="sxs-lookup"><span data-stu-id="54ef9-114">**Order invoiced** – This email notification type is new.</span></span> <span data-ttu-id="54ef9-115">Ez a **Rendelés szállítva** értesítési típus helyett használható, amely értesítést küld bármely olyan számlázási esemény esetén, amelynél a kézbesítési mód szállítva (nem átvétel, nem azonnali szállítás vagy elektronikus szállítási mód).</span><span class="sxs-lookup"><span data-stu-id="54ef9-115">It can be used instead of the **Order shipped** notification type that will send a notification for any invoice event that has a shipped mode of delivery (not a pickup, carry out, or electronic mode of delivery).</span></span>
- <span data-ttu-id="54ef9-116">**Rendelés kitárolva**</span><span class="sxs-lookup"><span data-stu-id="54ef9-116">**Order picked**</span></span>
- <span data-ttu-id="54ef9-117">**Rendelés csomagolva**</span><span class="sxs-lookup"><span data-stu-id="54ef9-117">**Order packed**</span></span>
- <span data-ttu-id="54ef9-118">**Rendelésre kitárolásra kész** – Ez az értesítési típus testreszabható kézbesítési mód szerint, csak akkor ha a **Több felvételi szállítási mód engedélyezése** funkció be van kapcsolva.</span><span class="sxs-lookup"><span data-stu-id="54ef9-118">**Order ready for pickup** – This notification type can be customized by mode of delivery only if the **Support for multiple pickup delivery modes** feature is turned on.</span></span> <span data-ttu-id="54ef9-119">Ebben az esetben ez az értesítéstípus funkcionálisan egyenértékű a **Rendelés csomagolva** értesítéstípussal.</span><span class="sxs-lookup"><span data-stu-id="54ef9-119">In that case, this notification type is functionally equivalent to the **Order packed** notification type.</span></span>
- <span data-ttu-id="54ef9-120">**Fizetés sikertelen**</span><span class="sxs-lookup"><span data-stu-id="54ef9-120">**Payment failed**</span></span>
- <span data-ttu-id="54ef9-121">**Csererendelés létrehozva**</span><span class="sxs-lookup"><span data-stu-id="54ef9-121">**Replacement order created**</span></span>

## <a name="configure-email-templates-for-specific-modes-of-delivery"></a><span data-ttu-id="54ef9-122">E-mail sablonok konfigurálása adott kézbesítési módokhoz</span><span class="sxs-lookup"><span data-stu-id="54ef9-122">Configure email templates for specific modes of delivery</span></span>

<span data-ttu-id="54ef9-123">Ebben az eljárásban a feltételezés az, hogy már létrehozta az új, egyéni e-mail sablonokat, és hozzáadta őket a **Szervezet e-mail sablonok** laphoz.</span><span class="sxs-lookup"><span data-stu-id="54ef9-123">For this procedure, the assumption is that you've already created your new, custom email templates and added them to the **Organization email templates** page.</span></span> <span data-ttu-id="54ef9-124">Az e-mail-sablonok létrehozásáról és feltöltéséről a [E-mail-sablonok létrehozása tranzakciós eseményekhez](email-templates-transactions.md).</span><span class="sxs-lookup"><span data-stu-id="54ef9-124">For information about how to create and upload email templates, see [Create email templates for transactional events](email-templates-transactions.md).</span></span>

<span data-ttu-id="54ef9-125">Ha a Commerce központban bizonyos kézbesítési módokhoz szeretne e-mail sablonokat beállítani, kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="54ef9-125">To configure email templates for specific modes of delivery in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="54ef9-126">Nyissa meg a **Commerce e-mail értesítési profilját**.</span><span class="sxs-lookup"><span data-stu-id="54ef9-126">Go to **Commerce email notification profile**.</span></span>
1. <span data-ttu-id="54ef9-127">A **Kiskereskedelmi esemény értesítési beállításai** részben válasszon ki egy meglévő értesítéstípust.</span><span class="sxs-lookup"><span data-stu-id="54ef9-127">Under **Retail event notification settings**, select an existing notification type.</span></span>
1. <span data-ttu-id="54ef9-128">Amíg az értesítés típusa még mindig ki van jelölve, válassza a **Szállítási módok konfigurálása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="54ef9-128">While the notification type is still selected, select **Configure modes of delivery**.</span></span>
1. <span data-ttu-id="54ef9-129">A **Szállítási módok** párbeszédablakban válassza az **Új** elemet.</span><span class="sxs-lookup"><span data-stu-id="54ef9-129">In the **Modes of delivery** dialog box, select **New**.</span></span>
1. <span data-ttu-id="54ef9-130">Az új sorban a **Szállítás módja** mezőben válassza ki a szállítási módot.</span><span class="sxs-lookup"><span data-stu-id="54ef9-130">In the new row, in the **Mode of delivery** field, select a mode of delivery.</span></span>
1. <span data-ttu-id="54ef9-131">Az **E-mail-azonosító** mezőben válassza ki azt az e-mail sablont, amelyet a kézbesítés módhoz szeretne leképezni.</span><span class="sxs-lookup"><span data-stu-id="54ef9-131">In the **Email ID** field, select the email template to map to the mode of delivery.</span></span>
1. <span data-ttu-id="54ef9-132">Jelölje be az **Aktív** jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="54ef9-132">Select the **Active** check box.</span></span>
1. <span data-ttu-id="54ef9-133">Ismételje meg a 4-7. lépéseket a többi kézbesítési módok hozzáadásához.</span><span class="sxs-lookup"><span data-stu-id="54ef9-133">Repeat steps 4 through 7 to add more modes of delivery.</span></span>
1. <span data-ttu-id="54ef9-134">Amikor elkészült, válassza az **OK** elemet.</span><span class="sxs-lookup"><span data-stu-id="54ef9-134">When you've finished, select **OK**.</span></span>

> [!NOTE]
> - <span data-ttu-id="54ef9-135">Ha egy értékesítési rendelés sorai között egynél több szállítási mód van jelen, a program az alapértelmezett sablont fogja használni.</span><span class="sxs-lookup"><span data-stu-id="54ef9-135">When more than one mode of delivery is present across lines in a sales order, the default template will be used.</span></span> <span data-ttu-id="54ef9-136">Az alapértelmezett sablon az a sablon, amely le van képezve az értesítési típushoz a **Commerce e-mail értesítési profil** oldalán.</span><span class="sxs-lookup"><span data-stu-id="54ef9-136">The default template is the template that is mapped to the notification type on the **Commerce email notification profile** page.</span></span>
> - <span data-ttu-id="54ef9-137">Ha egy értékesítési rendelés kézbesítési módja nincs beállítva egyéni e-mail sablonhoz, a rendszer az alapértelmezett e-mail sablont fogja használni.</span><span class="sxs-lookup"><span data-stu-id="54ef9-137">If a sales order has a mode of delivery that hasn't been configured for a custom email template, the default email template will be used.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="54ef9-138">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="54ef9-138">Additional resources</span></span>

[<span data-ttu-id="54ef9-139">Hívásközponti rendelések létrehozása</span><span class="sxs-lookup"><span data-stu-id="54ef9-139">Create call center orders</span></span>](tasks/create-call-center-orders.md)

[<span data-ttu-id="54ef9-140">Szállítási mód módosítása a pénztárban</span><span class="sxs-lookup"><span data-stu-id="54ef9-140">Change mode of delivery in POS</span></span>](pos-change-delivery-mode.md)
