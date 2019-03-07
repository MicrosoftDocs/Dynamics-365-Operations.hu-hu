---
title: Szállítók és szállítói bankszámlák beállítása ISO20022 típusú átutalásokhoz
description: Ez az eljárás bemutatja, hogyan állíthatja be a szállítót és a szállítóspecifikus bankszámlaadatokat az ISO20022 átutalási, illetve másmilyen szállítói fizetési fájl létrehozásához.
author: mrolecki
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendTable, VendBankAccounts
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 13b3c37f5d013dd896a456018813f20e5e70350b
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2019
ms.locfileid: "311611"
---
# <a name="set-up-vendors-and-vendor-bank-accounts-for-iso20022-credit-transfers"></a><span data-ttu-id="04b2e-103">Szállítók és szállítói bankszámlák beállítása ISO20022 típusú átutalásokhoz</span><span class="sxs-lookup"><span data-stu-id="04b2e-103">Set up vendors and vendor bank accounts for ISO20022 credit transfers</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="04b2e-104">Ez az eljárás bemutatja, hogyan állíthatja be a szállítót és a szállítóspecifikus bankszámlaadatokat az ISO20022 átutalási, illetve másmilyen szállítói fizetési fájl létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="04b2e-104">This procedure demonstrates how to set up the vendor and vendor specific bank account information required for ISO20022 Credit transfer or any other vendor payment file generation.</span></span> 

<span data-ttu-id="04b2e-105">Ez az eljárás az DEMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="04b2e-105">The demo data company used to create this procedure is DEMF.</span></span>
<span data-ttu-id="04b2e-106">Ez a negyedik azon öt eljárás közül, amelyek elektronikus jelentési beállítások használatával mutatják be a szállítói kifizetési folyamatot.</span><span class="sxs-lookup"><span data-stu-id="04b2e-106">This is the fourth procedure, out of five, that illustrates the vendor payment process using electronic reporting configurations.</span></span> <span data-ttu-id="04b2e-107">Az eljárás egy olyan szolgáltatáshoz tartozik, amely a Dynamics 365 for Operations 1611-es verziójában jelent meg.</span><span class="sxs-lookup"><span data-stu-id="04b2e-107">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="set-up-bank-details"></a><span data-ttu-id="04b2e-108">Bankadatok beállítása</span><span class="sxs-lookup"><span data-stu-id="04b2e-108">Set up bank details</span></span>
1. <span data-ttu-id="04b2e-109">Ugrás a Kötelezettségek > Szállítók > Minden szállító elemre.</span><span class="sxs-lookup"><span data-stu-id="04b2e-109">Go to Accounts payable > Vendors > All vendors.</span></span>
2. <span data-ttu-id="04b2e-110">Rekordok kereséséhez használja a gyorsszűrőt.</span><span class="sxs-lookup"><span data-stu-id="04b2e-110">Use the Quick Filter to find records.</span></span> <span data-ttu-id="04b2e-111">Például szűkítsen a Szállítói számla mezővel a „DE-001” értéket beírva.</span><span class="sxs-lookup"><span data-stu-id="04b2e-111">For example, filter on the Vendor account field with a value of 'DE-001'.</span></span>
3. <span data-ttu-id="04b2e-112">A szállítói adatok megadásához kattintson a DE-001 lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="04b2e-112">Click DE-001 to open vendor details.</span></span>
4. <span data-ttu-id="04b2e-113">A Művelet ablaktáblában kattintson a Szállító elemre.</span><span class="sxs-lookup"><span data-stu-id="04b2e-113">On the Action Pane, click Vendor.</span></span>
5. <span data-ttu-id="04b2e-114">Kattintson a Bankszámlák lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="04b2e-114">Click Bank accounts.</span></span>
6. <span data-ttu-id="04b2e-115">Kattintson a Szerkesztés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="04b2e-115">Click Edit.</span></span>
    * <span data-ttu-id="04b2e-116">Ha nincs elérhető bank, hozzon létre újat.</span><span class="sxs-lookup"><span data-stu-id="04b2e-116">If there is no bank account available, you need to create a new one.</span></span>  
7. <span data-ttu-id="04b2e-117">A SWIFT kód mezőbe írja be a „COBADEFFXXX” értéket.</span><span class="sxs-lookup"><span data-stu-id="04b2e-117">In the SWIFT code field, type 'COBADEFFXXX'.</span></span>
8. <span data-ttu-id="04b2e-118">Az IBAN mezőbe írja be a „DE36200400000628808808” értéket.</span><span class="sxs-lookup"><span data-stu-id="04b2e-118">In the IBAN field, type 'DE36200400000628808808'.</span></span>
9. <span data-ttu-id="04b2e-119">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="04b2e-119">Close the page.</span></span>

## <a name="set-up-a-method-of-payment-for-the-vendor"></a><span data-ttu-id="04b2e-120">A szállító fizetési módjának beállítása</span><span class="sxs-lookup"><span data-stu-id="04b2e-120">Set up a method of payment for the vendor</span></span>
1. <span data-ttu-id="04b2e-121">Kattintson a Szerkesztés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="04b2e-121">Click Edit.</span></span>
2. <span data-ttu-id="04b2e-122">Bontsa ki vagy zárja be a Kifizetés szakaszt.</span><span class="sxs-lookup"><span data-stu-id="04b2e-122">Expand or collapse the Payment section.</span></span>
3. <span data-ttu-id="04b2e-123">A Fizetési mód mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="04b2e-123">In the Method of payment field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="04b2e-124">A listában kattintson a SEPA CT sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="04b2e-124">In the list, click the link in the SEPA CT row.</span></span>
5. <span data-ttu-id="04b2e-125">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="04b2e-125">Click Save.</span></span>

