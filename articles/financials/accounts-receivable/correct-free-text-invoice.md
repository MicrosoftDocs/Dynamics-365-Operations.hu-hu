---
title: "Szabadszöveges számla helyesbítése"
description: "Ez a cikk a már feladott szabadszöveges számlák kijavításának és azok javított számlaként való újbóli kiadásának módszereit mutatja be."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CustFreeInvoice
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 13991
ms.assetid: 2a0a4789-8619-4974-bef9-0923cc848420
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: d9747ba144d56c9410846769e5465372c89ea111
ms.openlocfilehash: c8c1b90b7b2c02a53e53cc13d70445a237b126d4
ms.contentlocale: hu-hu
ms.lasthandoff: 08/07/2018

---

# <a name="correct-a-free-text-invoice"></a><span data-ttu-id="9f5f9-103">Szabadszöveges számla helyesbítése</span><span class="sxs-lookup"><span data-stu-id="9f5f9-103">Correct a free text invoice</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9f5f9-104">Ez a cikk a már feladott szabadszöveges számlák kijavításának és azok javított számlaként való újbóli kiadásának módszereit mutatja be.</span><span class="sxs-lookup"><span data-stu-id="9f5f9-104">This article explains how to correct a free text invoice that has been posted and reissue it as a corrected invoice.</span></span>

<span data-ttu-id="9f5f9-105">Már elkönyvelt szabadszöveges számla javításához nyissa meg a könyvelt szabadszöveges számlát.</span><span class="sxs-lookup"><span data-stu-id="9f5f9-105">To correct a free text invoice that has already been posted, open the posted free text invoice.</span></span> <span data-ttu-id="9f5f9-106">A **Számla** lapon válassza a **Mégse** elemet, majd a **Helyes számla** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="9f5f9-106">On the **Invoice** page, select **Cancel**, and then select **Correct invoice**.</span></span> <span data-ttu-id="9f5f9-107">Válassza ki az okkódot, és adjon hozzá megjegyzéseket és válassza ki az új javított számla dátumát.</span><span class="sxs-lookup"><span data-stu-id="9f5f9-107">Select a reason code, add comments, and select the date for new corrected invoice.</span></span> <span data-ttu-id="9f5f9-108">Módosíthatja és feladhatja a javított számlát.</span><span class="sxs-lookup"><span data-stu-id="9f5f9-108">You can modify the corrected invoice, and post it.</span></span> 

<span data-ttu-id="9f5f9-109">A javított számla feladásakor egy érvénytelenítő számla jön létrea hitel összeghez, amit kiegyenlíti az eredeti számla összeget.</span><span class="sxs-lookup"><span data-stu-id="9f5f9-109">When you post the corrected invoice, a canceling invoice is created for a credit amount that equals the original invoice amount.</span></span> <span data-ttu-id="9f5f9-110">Ezért az eredeti és az érvénytelenítő számla kombinált egyenlege 0 (nulla).</span><span class="sxs-lookup"><span data-stu-id="9f5f9-110">Therefore, the combined balance of the original invoice and the canceling invoice is 0 (zero).</span></span> <span data-ttu-id="9f5f9-111">Az érvénytelenítő számlát az eredeti számlával szemben számolnak el.</span><span class="sxs-lookup"><span data-stu-id="9f5f9-111">The canceling invoice is settled against the original invoice.</span></span> 

<span data-ttu-id="9f5f9-112">A javított számla feladásakor, három számlája lesz:</span><span class="sxs-lookup"><span data-stu-id="9f5f9-112">After you post the corrected invoice, you will have three invoices:</span></span>

-   <span data-ttu-id="9f5f9-113">**Eredeti számla** – Az a számla, amely a javítandó adatokat tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="9f5f9-113">**Original invoice** – The invoice that includes the information that you're correcting.</span></span>
-   <span data-ttu-id="9f5f9-114">**Érvénytelenítési számla** – A rendszer által előállított jóváíró számla, amely a legutoljára helyesbített számla érvénytelenítéséhez lett létrehozva.</span><span class="sxs-lookup"><span data-stu-id="9f5f9-114">**Canceling invoice** – The system-generated credit invoice that was created to cancel the invoice that was most recently corrected.</span></span>
-   <span data-ttu-id="9f5f9-115">**Javított számla** – Az a számla, amely a helyesbített számlaadatokat tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="9f5f9-115">**Corrected invoice** – The invoice that contains the corrected invoice information.</span></span>

<span data-ttu-id="9f5f9-116">Kétféle módon határozhatja meg a számlák érvénytelenítését és javítását:</span><span class="sxs-lookup"><span data-stu-id="9f5f9-116">You can identify canceling and correcting invoices in two ways:</span></span>

-   <span data-ttu-id="9f5f9-117">Az **összes szabadszöveges számlák** lap tartalmazza a **Javítás** oszlopot, amelyen megtekintheti, hogy mely számlák érvénytelenítési számlák és javított számlák.</span><span class="sxs-lookup"><span data-stu-id="9f5f9-117">The **All free text invoices** page includes a **Correction** column, where you can see which invoices are canceling invoices and corrected invoices.</span></span>
-   <span data-ttu-id="9f5f9-118">A szabadszöveges számla fejlécének állapotjelzője **Érvénytelenítési számla '\[számlaszám\]'** vagy **Javított számla '\[számlaszám\]'**.</span><span class="sxs-lookup"><span data-stu-id="9f5f9-118">The header of the free text invoice shows a status of **Cancelling invoice '\[invoice number\]'** or **Corrected invoice '\[invoice number\]'**.</span></span>

> [!NOTE]
> <span data-ttu-id="9f5f9-119">Ez a funkció csak akkor használható, ha be van állítva a **Szabadszöveges számla javítása** konfigurációs kulcs.</span><span class="sxs-lookup"><span data-stu-id="9f5f9-119">This feature is available only if the **Free text invoice correction** configuration key is selected.</span></span>




