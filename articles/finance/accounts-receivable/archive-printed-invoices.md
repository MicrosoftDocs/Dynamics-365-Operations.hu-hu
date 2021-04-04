---
title: Nyomtatott vevői számlák archiválása kivonatszámokkal
description: Ez a témakör bemutatja, hogyan engedélyezheti az archiválást a nyomtatott, kivonatszámokat is tartalmazó vevői számlák tárolására.
author: ilyako
manager: AnnBe
ms.date: 03/05/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 539093
ms.search.region: Global
ms.author: ilyako
ms.search.validFrom: 2021-03-05
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: d502ec5d286573c72e207419b66f283183009c09
ms.sourcegitcommit: 08ac570bece3e4ee4a0f632f51623e328536dfcf
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/08/2021
ms.locfileid: "5557480"
---
# <a name="archive-printed-customer-invoices-with-hash-numbers"></a><span data-ttu-id="1b30c-103">Nyomtatott vevői számlák archiválása kivonatszámokkal</span><span class="sxs-lookup"><span data-stu-id="1b30c-103">Archive printed customer invoices with hash numbers</span></span>

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

<span data-ttu-id="1b30c-104">Egyes országokban jogszabályi előírás a kiszámított kivonatszámok tárolása a rendszerben, bizonyos dokumentumok kinyomtatott változatával együtt.</span><span class="sxs-lookup"><span data-stu-id="1b30c-104">In some countries, there is a legal requirement to store calculated hash numbers in the system together with printouts of some documents.</span></span> <span data-ttu-id="1b30c-105">A kivonatszámok a hatóságoknak való jelentésre és a könyvvizsgálatok során használhatók.</span><span class="sxs-lookup"><span data-stu-id="1b30c-105">Hash numbers can be used for reporting to authorities and during audits.</span></span>

<span data-ttu-id="1b30c-106">Ez a témakör bemutatja, hogyan konfigurálhatja az archiválást a nyomtatott, kivonatszámokat is tartalmazó vevői számlák tárolására.</span><span class="sxs-lookup"><span data-stu-id="1b30c-106">This topic explains how to configure archiving in order to store printed customer invoices with hash numbers.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="1b30c-107">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="1b30c-107">Prerequisites</span></span>

- <span data-ttu-id="1b30c-108">A **Funkciókezelés** munkaterületen kapcsolja be a **Nyomtatott, kivonatszámokat is tartalmazó vevői számlák archiválása** funkciót.</span><span class="sxs-lookup"><span data-stu-id="1b30c-108">In the **Feature management** workspace, turn on the feature, **Archive printed customer invoices with hash numbers**.</span></span> <span data-ttu-id="1b30c-109">További tájékoztatás: [Funkciókezelés – áttekintés](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).</span><span class="sxs-lookup"><span data-stu-id="1b30c-109">For more information, see [Feature management overview](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).</span></span>
- <span data-ttu-id="1b30c-110">A szükséges dokumentumok nyomtatható formátumait a **Nyomtatáskezelés** lehetőségben konfigurálhatja.</span><span class="sxs-lookup"><span data-stu-id="1b30c-110">Configure the printable formats of required documents in **Print management**.</span></span>

<span data-ttu-id="1b30c-111">Ez a funkció a következő dokumentumokra alkalmazható.</span><span class="sxs-lookup"><span data-stu-id="1b30c-111">This functionality is applicable to the following documents.</span></span>

<span data-ttu-id="1b30c-112">**Kinnlevőségek**</span><span class="sxs-lookup"><span data-stu-id="1b30c-112">**Accounts receivable**</span></span>
- <span data-ttu-id="1b30c-113">Vevői számla</span><span class="sxs-lookup"><span data-stu-id="1b30c-113">Customer invoice</span></span>
- <span data-ttu-id="1b30c-114">Vevői jóváírás</span><span class="sxs-lookup"><span data-stu-id="1b30c-114">Customer credit note</span></span>
- <span data-ttu-id="1b30c-115">Szabadszöveges számla</span><span class="sxs-lookup"><span data-stu-id="1b30c-115">Free text invoice</span></span>
- <span data-ttu-id="1b30c-116">Szabadszövegű jóváírás</span><span class="sxs-lookup"><span data-stu-id="1b30c-116">Free text credit note</span></span>

<span data-ttu-id="1b30c-117">**Projektvezetés és könyvelés**</span><span class="sxs-lookup"><span data-stu-id="1b30c-117">**Project management and accounting**</span></span>
- <span data-ttu-id="1b30c-118">Projektszámla</span><span class="sxs-lookup"><span data-stu-id="1b30c-118">Project invoice</span></span>
- <span data-ttu-id="1b30c-119">Projekt jóváírása</span><span class="sxs-lookup"><span data-stu-id="1b30c-119">Project credit note</span></span>

## <a name="configure-customer-master-data"></a><span data-ttu-id="1b30c-120">Vevők alapadatainak konfigurálása</span><span class="sxs-lookup"><span data-stu-id="1b30c-120">Configure customer master data</span></span>
<span data-ttu-id="1b30c-121">A következő lépések szerint konfigurálhatja a vevőadatokat és bekapcsolhatja a nyomtatott számlák mellékletként való automatikus mentésének lehetőségét.</span><span class="sxs-lookup"><span data-stu-id="1b30c-121">Complete the following steps to configure customer data and turn on the ability to automatically save printed invoices as attachments.</span></span>

1. <span data-ttu-id="1b30c-122">Ugorjon a **Kinnlevőségek** > **Minden vevő** pontra.</span><span class="sxs-lookup"><span data-stu-id="1b30c-122">Go to **Accounts receivable** > **All customers**.</span></span> 
2. <span data-ttu-id="1b30c-123">Válasszon ki egy vevőt, és a **Számlázás és szállítás** gyorslapon az **E-SZÁMLÁZÁS** szakaszban az **e-számlamelléklet** mezőben válassza az **Igen** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1b30c-123">Select a customer, and on the **Invoice and delivery** FastTab, in the **E-INVOCE** section, in the **eInvoice attachment** field, select **Yes**.</span></span>

## <a name="print-invoices"></a><span data-ttu-id="1b30c-124">Számlák nyomtatása</span><span class="sxs-lookup"><span data-stu-id="1b30c-124">Print invoices</span></span>
<span data-ttu-id="1b30c-125">Az előző eljárásban konfigurált vevő számára bármilyen szabadszöveget, vevőt, projektszámlát vagy jóváírást feladhat és nyomtathat.</span><span class="sxs-lookup"><span data-stu-id="1b30c-125">You can post and print any free text, customer, and project invoice or credit note for the customer configured in the previous procedure.</span></span>

<span data-ttu-id="1b30c-126">Nyissa meg nyomtatott számla **Mellékletek** oldalát.</span><span class="sxs-lookup"><span data-stu-id="1b30c-126">Open the **Attachments** page for the printed invoice.</span></span> <span data-ttu-id="1b30c-127">A **Melléklet** gyorslap **További részletek** mezőcsoportjának a **Dokumentum kivonatszáma** mezőjében keresse meg a nyomtatott számlához kiszámított tárolt kivonatszámot.</span><span class="sxs-lookup"><span data-stu-id="1b30c-127">On the **Attachment** FastTab, in the **Additional details** field group, in **Document hash number** field, find the stored hash number calculated for the printed invoice.</span></span>

![Melléklet kivonatszáma](media/attach-hash-num.jpg)

