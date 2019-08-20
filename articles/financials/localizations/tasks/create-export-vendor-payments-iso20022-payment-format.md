---
title: Szállítói kifizetések létrehozása és exportálása ISO20022 fizetési formátumban
description: Ez az eljárás bemutatja, hogyan hozhat létre fizetési sorokat a szállítói kifizetési naplóban, és hogyan hozhat létre szállítói fizetési fájlt az ISO2022 átutalást használva példaként.
author: mrolecki
manager: AnnBe
ms.date: 01/17/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransVendPaym, SysQueryForm, VendPaymProposalEdit, BankAccountTableLookUp
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b70ad94014587ba8e55735192dbe0ab2e4adf4ee
ms.sourcegitcommit: 16bfa0fd08feec1647829630401ce62ce2ffa1a4
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/02/2019
ms.locfileid: "1848991"
---
# <a name="create-and-export-vendor-payments-using-iso20022-payment-format"></a><span data-ttu-id="98158-103">Szállítói kifizetések létrehozása és exportálása ISO20022 fizetési formátumban</span><span class="sxs-lookup"><span data-stu-id="98158-103">Create and export vendor payments using ISO20022 payment format</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="98158-104">Ez az témakör bemutatja, hogyan hozhat létre fizetési sorokat a szállítói kifizetési naplóban, és hogyan hozhat létre szállítói fizetési fájlt az ISO2022 átutalást használva példaként.</span><span class="sxs-lookup"><span data-stu-id="98158-104">This topic explains how to create payment lines in the vendor payment journal and generate a vendor payment file using ISO2022 Credit transfer example.</span></span>

<span data-ttu-id="98158-105">Ez az ötödik azon öt eljárás közül, amelyek elektronikus jelentési beállítások használatával mutatják be a szállítói kifizetési folyamatot.</span><span class="sxs-lookup"><span data-stu-id="98158-105">This is the fifth procedure, out of five, that illustrates the vendor payment process using electronic reporting configurations.</span></span> <span data-ttu-id="98158-106">Az DEMF bemutatóadatok segítségével végezze el ezt az példát.</span><span class="sxs-lookup"><span data-stu-id="98158-106">Use the DEMF demo data to complete this example.</span></span>

## <a name="example"></a><span data-ttu-id="98158-107">Példa</span><span class="sxs-lookup"><span data-stu-id="98158-107">Example</span></span>

1.  <span data-ttu-id="98158-108">Ugorjon a **Kötelezettségek > Fizetési beállítás > Fizetési napló** pontra.</span><span class="sxs-lookup"><span data-stu-id="98158-108">Go to **Accounts payable > Payments > Payment journal**.</span></span>
2.  <span data-ttu-id="98158-109">Kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="98158-109">Click **New**.</span></span>
3.  <span data-ttu-id="98158-110">A **Név** mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="98158-110">In the **Name** field, enter or select a value.</span></span>
4.  <span data-ttu-id="98158-111">Kattintson a **Sorok > Kifizetési javaslat > Fizetési javaslat létrehozása** menügombra.</span><span class="sxs-lookup"><span data-stu-id="98158-111">Click **Lines > Payment proposal > Create payment proposal**.</span></span>
5.  <span data-ttu-id="98158-112">Bontsa ki a **Szerepeltetni kívánt rekordok** szakaszt.</span><span class="sxs-lookup"><span data-stu-id="98158-112">Expand the **Records to include** section.</span></span>
6.  <span data-ttu-id="98158-113">Kattintson a **Szűrő** parancsra.</span><span class="sxs-lookup"><span data-stu-id="98158-113">Click **Filter**.</span></span>
7.  <span data-ttu-id="98158-114">A listában jelölje ki a **Szállítók táblára** és a **Szállítói számla mezőre** vonatkozó sort.</span><span class="sxs-lookup"><span data-stu-id="98158-114">In the list, select the row for **Vendors table** and **Vendor account field**.</span></span>
8.  <span data-ttu-id="98158-115">A **Feltétel** mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="98158-115">In the **Criteria** field, enter or select a value.</span></span> <span data-ttu-id="98158-116">Bármilyen feltétel alkalmazható a szállítói fizetési tranzakció kiválasztásához, ebben a példában a DE-001-et használjuk szállítói számlaként.</span><span class="sxs-lookup"><span data-stu-id="98158-116">You can apply any criteria for selecting vendor transactions to pay, for this example, use DE-001 as a vendor account.</span></span>
12. <span data-ttu-id="98158-117">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="98158-117">Click **OK**.</span></span>
13. <span data-ttu-id="98158-118">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="98158-118">Click **OK**.</span></span>
14. <span data-ttu-id="98158-119">Kattintson a **Fizetések létrehozása** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="98158-119">Click **Create payments**.</span></span>
15. <span data-ttu-id="98158-120">Hozzon létre egy ISO20022 típusú fizetési fájlt.</span><span class="sxs-lookup"><span data-stu-id="98158-120">Generate an ISO20022 payment file.</span></span>
    1.  <span data-ttu-id="98158-121">Kattintson a **Kifizetések létrehozása** elemre.</span><span class="sxs-lookup"><span data-stu-id="98158-121">Click **Generate payments**.</span></span>
    2.  <span data-ttu-id="98158-122">A **Fizetési mód** mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="98158-122">In the **Method of payment** field, enter or select a value.</span></span>
    3.  <span data-ttu-id="98158-123">Írjon be egy értéket a **Fájlnév** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="98158-123">In the **File name** field, type a value.</span></span> <span data-ttu-id="98158-124">Ebben a példában az euróban történő fizetés miatt a létrehozott fájl SEPA kompatibilis lesz.</span><span class="sxs-lookup"><span data-stu-id="98158-124">For this example, because of the EUR payment, the generated file will be SEPA compliant.</span></span> <span data-ttu-id="98158-125">A ISO20022 jóváírás-átutalás és a többi szállítói fizetési dormátum is használható a fizetések létrehozására más pénznemekben.</span><span class="sxs-lookup"><span data-stu-id="98158-125">ISO20022 credit transfer as well as other vendor payment formats can also be used for generating payments in other currencies.</span></span>
    4.  <span data-ttu-id="98158-126">A **Bankszámlák** mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="98158-126">In the **Bank account** field, enter or select a value.</span></span>

