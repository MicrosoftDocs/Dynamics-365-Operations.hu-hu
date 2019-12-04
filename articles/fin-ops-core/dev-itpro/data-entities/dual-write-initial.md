---
title: Végrehajtási sorrend a Finance and Operations alkalmazások és a Common Data Service kezdeti szinkronizálásához
description: Ez a témakör azt a szinkronizálási sorrendet határozza meg, amelyet a kezdeti adatok létrehozásához követnie kell.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: cf444ef1192fed3a6a49282da37374dd8c443356
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/06/2019
ms.locfileid: "2769637"
---
# <a name="execution-order-for-initial-synchronization-of-finance-and-operations-apps-and-common-data-service"></a><span data-ttu-id="ad8bb-103">Végrehajtási sorrend a Finance and Operations alkalmazások és a Common Data Service kezdeti szinkronizálásához</span><span class="sxs-lookup"><span data-stu-id="ad8bb-103">Execution order for initial synchronization of Finance and Operations apps and Common Data Service</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ad8bb-104">Az adatintegráció használata előtt létre kell hoznia a vevők, szállítók és kapcsolattartók számára szükséges kezdeti adatokat.</span><span class="sxs-lookup"><span data-stu-id="ad8bb-104">Before you use data integration, you must create the initial data that is required for customers, vendors, and contacts.</span></span> <span data-ttu-id="ad8bb-105">Például hozzon létre egy új **Szállítói csoport** elemet, és adja meg a **fizetési feltételek** értékét a **Net30** értékre.</span><span class="sxs-lookup"><span data-stu-id="ad8bb-105">For example, you want to create a new **Vendor group** item and set its **Terms of Payment** value to **Net30**.</span></span> <span data-ttu-id="ad8bb-106">Ebben az esetben a **Szállítói csoport** elemének létrehozása előtt meg kell győződni arról, hogy a **Net30** mind az alkalmazásban mind a Common Data Service szolgáltatásban létezik.</span><span class="sxs-lookup"><span data-stu-id="ad8bb-106">In this case, before you try to create the **Vendor group** item, you must make sure that **Net30** exists in both the application and Common Data Service.</span></span> <span data-ttu-id="ad8bb-107">(Jövőben, a Microsoft kiad egy kettős írási funkciót, amelynek neve Kezdeti szinkronizálás lesz. Ez a funkció egy egyszeri adatszinkronizálást fog végezni az alkalmazások és a Common Data Service között a kettős írás beállításának részeként.)</span><span class="sxs-lookup"><span data-stu-id="ad8bb-107">(In the future, Microsoft will release dual-write platform functionality that is named Initial Sync. This functionality will do a one-time data synchronization between the application and Common Data Service as part of the dual-write setup.)</span></span>

> [!TIP]
> <span data-ttu-id="ad8bb-108">A Microsoft kias kettős írású leképezést minden referenciaadathoz beleértve a **Fizetési feltételek** (Fizetési feltételek) elemhez.</span><span class="sxs-lookup"><span data-stu-id="ad8bb-108">Microsoft is releasing a dual-write map for all reference data, including **Terms of Payment** (payment terms).</span></span> <span data-ttu-id="ad8bb-109">Ha már rendelkezik a kezdeti adatokkal az egyik rendszerben, a rekordon végzett kis frissítési művelet elindíthatja a kettős írást az adott rekordra vonatkozóan.</span><span class="sxs-lookup"><span data-stu-id="ad8bb-109">If you already have the initial data in one system, a small update operation on a record can trigger dual-write on that record.</span></span>

<span data-ttu-id="ad8bb-110">Kövesse az alábbi sorrendet, és győződjön meg arról, hogy a kezdeti adatok rendelkezésre állnak az alkalmazásban és a Common Data Service megoldásban is.</span><span class="sxs-lookup"><span data-stu-id="ad8bb-110">You must follow the following order of precedence and make sure that the initial data is available in the application and Common Data Service.</span></span>

## <a name="vendor"></a><span data-ttu-id="ad8bb-111">Szállító</span><span class="sxs-lookup"><span data-stu-id="ad8bb-111">Vendor</span></span>

<span data-ttu-id="ad8bb-112">A **Szállító** entitás végrehajtásának sorrendje:</span><span class="sxs-lookup"><span data-stu-id="ad8bb-112">Here is the order of execution for the **Vendor** entity:</span></span>

1. <span data-ttu-id="ad8bb-113">Szállítói csoport</span><span class="sxs-lookup"><span data-stu-id="ad8bb-113">Vendor group</span></span>

    1. <span data-ttu-id="ad8bb-114">Fizetési feltételek</span><span class="sxs-lookup"><span data-stu-id="ad8bb-114">Terms of payment</span></span>

        1. <span data-ttu-id="ad8bb-115">Fizetési nap és sorok</span><span class="sxs-lookup"><span data-stu-id="ad8bb-115">Payment day and lines</span></span>
        2. <span data-ttu-id="ad8bb-116">Fizetési ütemezés</span><span class="sxs-lookup"><span data-stu-id="ad8bb-116">Payment schedule</span></span>

2. <span data-ttu-id="ad8bb-117">Szállítói fizetési mód</span><span class="sxs-lookup"><span data-stu-id="ad8bb-117">Vendor payment method</span></span>

## <a name="customer-organization"></a><span data-ttu-id="ad8bb-118">Ügyfél (Szervezet)</span><span class="sxs-lookup"><span data-stu-id="ad8bb-118">Customer (Organization)</span></span>

<span data-ttu-id="ad8bb-119">Az **Ügyfél** entitás végrehajtásának sorrendje:</span><span class="sxs-lookup"><span data-stu-id="ad8bb-119">Here is the order of execution for the **Customer** entity:</span></span>

1. <span data-ttu-id="ad8bb-120">Vevőcsoport</span><span class="sxs-lookup"><span data-stu-id="ad8bb-120">Customer group</span></span>

    1. <span data-ttu-id="ad8bb-121">Fizetési feltételek</span><span class="sxs-lookup"><span data-stu-id="ad8bb-121">Terms of payment</span></span>

        1. <span data-ttu-id="ad8bb-122">Fizetési nap és sorok</span><span class="sxs-lookup"><span data-stu-id="ad8bb-122">Payment day and lines</span></span>
        2. <span data-ttu-id="ad8bb-123">Fizetés</span><span class="sxs-lookup"><span data-stu-id="ad8bb-123">Payment</span></span> 

2. <span data-ttu-id="ad8bb-124">Vevő fizetési módszere</span><span class="sxs-lookup"><span data-stu-id="ad8bb-124">Customer payment method</span></span>

## <a name="contact-person"></a><span data-ttu-id="ad8bb-125">Kapcsolattartó (személy)</span><span class="sxs-lookup"><span data-stu-id="ad8bb-125">Contact (Person)</span></span>

<span data-ttu-id="ad8bb-126">A **Kapcsolattartó** entitás végrehajtásának sorrendje:</span><span class="sxs-lookup"><span data-stu-id="ad8bb-126">Here is the order of execution for the **Contact** entity:</span></span>

1. <span data-ttu-id="ad8bb-127">Vevő</span><span class="sxs-lookup"><span data-stu-id="ad8bb-127">Customer</span></span>
2. <span data-ttu-id="ad8bb-128">Szállító</span><span class="sxs-lookup"><span data-stu-id="ad8bb-128">Vendor</span></span>
