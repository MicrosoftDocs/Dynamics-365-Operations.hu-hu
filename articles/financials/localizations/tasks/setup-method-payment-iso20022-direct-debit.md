---
title: Fizetési mód beállítása ISO20022 beszedési megbízáshoz
description: Ez az eljárás bemutatja, hogyan állítható be a vevői fizetési módja ISO20022 beszedési megbízásra vagy egyéb fizetési típusra elektronikus jelentéskészítés használatával.
author: mrolecki
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustPaymMode
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 953a3cffc356ab44163944318e7e7d542a113112
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2019
ms.locfileid: "1559339"
---
# <a name="setup-method-of-payment-for-iso20022-direct-debit"></a><span data-ttu-id="65a7d-103">Fizetési mód beállítása ISO20022 beszedési megbízáshoz</span><span class="sxs-lookup"><span data-stu-id="65a7d-103">Setup method of payment for ISO20022 direct debit</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="65a7d-104">Ez az eljárás bemutatja, hogyan állítható be a vevői fizetési módja ISO20022 beszedési megbízásra vagy egyéb fizetési típusra elektronikus jelentéskészítés használatával.</span><span class="sxs-lookup"><span data-stu-id="65a7d-104">This procedure shows how to set up the customer method of payment for ISO20022 direct debit or any other payment type using electronic reporting.</span></span> 



<span data-ttu-id="65a7d-105">A feladat elvégzése előtt be kell állítania a formátumkonfigurációkat és a fizetési számlákat.</span><span class="sxs-lookup"><span data-stu-id="65a7d-105">Before you complete this task, you must set up export format configurations and payment accounts.</span></span>



<span data-ttu-id="65a7d-106">Ez az eljárás a DEMF bemutatócég segítségével lett létrehozva.</span><span class="sxs-lookup"><span data-stu-id="65a7d-106">This procedure was created using the demo data company DEMF.</span></span>



<span data-ttu-id="65a7d-107">Ez a harmadik azon öt eljárás közül, amelyek elektronikus jelentési beállítások használatával mutatják be a vevői kifizetési folyamatot.</span><span class="sxs-lookup"><span data-stu-id="65a7d-107">This is the third of five procedures that demonstrate the customer payment process using electronic reporting configurations.</span></span>

1. <span data-ttu-id="65a7d-108">Ugorjon a Kinnlevőségek > Fizetési beállítás > Fizetési mód pontra.</span><span class="sxs-lookup"><span data-stu-id="65a7d-108">Go to Accounts receivable > Payments setup > Methods of payment.</span></span>
2. <span data-ttu-id="65a7d-109">Rekordok kereséséhez használja a gyorsszűrőt.</span><span class="sxs-lookup"><span data-stu-id="65a7d-109">Use the Quick Filter to find records.</span></span> <span data-ttu-id="65a7d-110">Például szűkítsen a „Fizetési mód” mezővel az „ELEKTRONIKUS” értéket beírva.</span><span class="sxs-lookup"><span data-stu-id="65a7d-110">For example, filter on the Method of payment field with a value of 'ELECTRONIC'.</span></span>
3. <span data-ttu-id="65a7d-111">Kattintson a Szerkesztés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="65a7d-111">Click Edit.</span></span>
4. <span data-ttu-id="65a7d-112">A Fizetési számla mezőben adja meg a „DEMF OPER” értékeket.</span><span class="sxs-lookup"><span data-stu-id="65a7d-112">In the Payment account field, specify the values 'DEMF OPER'.</span></span>
5. <span data-ttu-id="65a7d-113">Bontsa ki a Fájlformátumok szakaszt.</span><span class="sxs-lookup"><span data-stu-id="65a7d-113">Expand the File formats section.</span></span>
6. <span data-ttu-id="65a7d-114">Válassza az Igen beállítást az Általános elektronikus jelentéskészítés mezőben.</span><span class="sxs-lookup"><span data-stu-id="65a7d-114">Select Yes in the Generic electronic reporting field.</span></span>
7. <span data-ttu-id="65a7d-115">Az Exportformátum konfigurációja mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="65a7d-115">In the Export format configuration field, enter or select a value.</span></span>
    * <span data-ttu-id="65a7d-116">A listán válassza ki az ISO20022 beszedési megbízást (DE).</span><span class="sxs-lookup"><span data-stu-id="65a7d-116">In the list, select ISO20022 Direct debit (DE).</span></span>  <span data-ttu-id="65a7d-117">Ha a lista üres, a vevői kifizetésnek nincs importált és aktivált exportálási konfigurációja.</span><span class="sxs-lookup"><span data-stu-id="65a7d-117">If the list is empty, the customer payment export format configuration has not been imported and active.</span></span>  
8. <span data-ttu-id="65a7d-118">Válassza az Igen lehetőséget a Felhatalmazás szükséges mezőben.</span><span class="sxs-lookup"><span data-stu-id="65a7d-118">Select Yes in the Require mandate field.</span></span>
    * <span data-ttu-id="65a7d-119">Válassza ki a Felhatalmazás szükséges paramétert az olyan vevői fizetési formátumokhoz, amelyekhez felhatalmazási adat megadása szükséges a fizetési üzenethez, ahogyan a SEPA beszedési megbízás esetén.</span><span class="sxs-lookup"><span data-stu-id="65a7d-119">Select the Require mandate parameter for customer payment formats, which require including mandate information in the payment message, like SEPA direct debit.</span></span>  
9. <span data-ttu-id="65a7d-120">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="65a7d-120">Click Save.</span></span>

