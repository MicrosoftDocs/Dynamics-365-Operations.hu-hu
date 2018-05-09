--- 
title: "Szállítói kifizetések létrehozása és exportálása ISO20022 fizetési formátumban"
description: "Ez az eljárás bemutatja, hogyan hozhat létre fizetési sorokat a szállítói kifizetési naplóban, és hogyan hozhat létre szállítói fizetési fájlt az ISO2022 átutalást használva példaként."
author: mrolecki
manager: AnnBe
ms.date: 10/24/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 906f9611370e19ad4f063d15608d3564c5292c96
ms.contentlocale: hu-hu
ms.lasthandoff: 05/08/2018

---
# <a name="create-and-export-vendor-payments-using-iso20022-payment-format"></a><span data-ttu-id="0449f-103">Szállítói kifizetések létrehozása és exportálása ISO20022 fizetési formátumban</span><span class="sxs-lookup"><span data-stu-id="0449f-103">Create and export vendor payments using ISO20022 payment format</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="0449f-104">Ez az eljárás bemutatja, hogyan hozhat létre fizetési sorokat a szállítói kifizetési naplóban, és hogyan hozhat létre szállítói fizetési fájlt az ISO2022 átutalást használva példaként.</span><span class="sxs-lookup"><span data-stu-id="0449f-104">This procedure shows how to create payment lines in the vendor payment journal and generate a vendor payment file using ISO2022 Credit transfer example.</span></span> 

<span data-ttu-id="0449f-105">Ez az eljárás az DEMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="0449f-105">The demo data company used to create this procedure is DEMF.</span></span>

<span data-ttu-id="0449f-106">Ez az ötödik azon öt eljárás közül, amelyek elektronikus jelentési beállítások használatával mutatják be a szállítói kifizetési folyamatot.</span><span class="sxs-lookup"><span data-stu-id="0449f-106">This is the fifth procedure, out of five, that illustrates the vendor payment process using electronic reporting configurations.</span></span> <span data-ttu-id="0449f-107">Ez az eljárás egy olyan funkcióra vonatkozik, amely a Dynamics 365 for Operations 1611-es verziójába került be.</span><span class="sxs-lookup"><span data-stu-id="0449f-107">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="create-payment-lines"></a><span data-ttu-id="0449f-108">Fizetési sorok létrehozása</span><span class="sxs-lookup"><span data-stu-id="0449f-108">Create payment lines</span></span>
1. <span data-ttu-id="0449f-109">Ugorjon a Kötelezettségek > Fizetési beállítás > Fizetési napló pontra.</span><span class="sxs-lookup"><span data-stu-id="0449f-109">Go to Accounts payable > Payments > Payment journal.</span></span>
2. <span data-ttu-id="0449f-110">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="0449f-110">Click New.</span></span>
3. <span data-ttu-id="0449f-111">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="0449f-111">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="0449f-112">A Név mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="0449f-112">In the Name field, enter or select a value.</span></span>
5. <span data-ttu-id="0449f-113">Kattintson a Sorok pontra.</span><span class="sxs-lookup"><span data-stu-id="0449f-113">Click Lines.</span></span>
6. <span data-ttu-id="0449f-114">Kattintson a Fizetési javaslat lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="0449f-114">Click Payment proposal.</span></span>
7. <span data-ttu-id="0449f-115">Kattintson a Fizetési javaslat létrehozása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="0449f-115">Click Create payment proposal.</span></span>
8. <span data-ttu-id="0449f-116">Bontsa ki a Szerepeltetni kívánt rekordok szakaszt.</span><span class="sxs-lookup"><span data-stu-id="0449f-116">Expand the Records to include section.</span></span>
9. <span data-ttu-id="0449f-117">Kattintson a Szűrő parancsra.</span><span class="sxs-lookup"><span data-stu-id="0449f-117">Click Filter.</span></span>
10. <span data-ttu-id="0449f-118">A listában jelölje ki a Szállítók táblára és a Szállítói számla mezőre vonatkozó sort.</span><span class="sxs-lookup"><span data-stu-id="0449f-118">In the list, select the row for Vendors table and Vendor account field.</span></span>
11. <span data-ttu-id="0449f-119">A Feltétel mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="0449f-119">In the Criteria field, enter or select a value.</span></span>
    * <span data-ttu-id="0449f-120">Bármilyen feltétel alkalmazható a szállítói fizetési tranzakció kiválasztásához - ebben a példában a DE-001-et használjuk szállítói számlaként.</span><span class="sxs-lookup"><span data-stu-id="0449f-120">You can apply any criteria for selecting vendor transactions to pay, for this example use DE-001 as a vendor account.</span></span>  
12. <span data-ttu-id="0449f-121">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="0449f-121">Click OK.</span></span>
13. <span data-ttu-id="0449f-122">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="0449f-122">Click OK.</span></span>
14. <span data-ttu-id="0449f-123">Kattintson a Fizetések létrehozása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="0449f-123">Click Create payments.</span></span>

## <a name="generate-an-iso20022-payment-file"></a><span data-ttu-id="0449f-124">ISO20022 típusú fizetési fájl létrehozása</span><span class="sxs-lookup"><span data-stu-id="0449f-124">Generate an ISO20022 payment file</span></span>


