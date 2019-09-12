---
title: Végrehajtási sorrend a Finance and Operations és a Common Data Service kezdeti szinkronizálásához
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
ms.openlocfilehash: 1473c3bad55734d5f83ee3e4c1654921b872f3bb
ms.sourcegitcommit: 3f05ede8b8acdf0550240a83a013e093b4ad043d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/13/2019
ms.locfileid: "1873128"
---
# <a name="execution-order-for-initial-synchronization-of-finance-and-operations-and-common-data-service"></a><span data-ttu-id="2284e-103">Végrehajtási sorrend a Finance and Operations és a Common Data Service kezdeti szinkronizálásához</span><span class="sxs-lookup"><span data-stu-id="2284e-103">Execution order for initial synchronization of Finance and Operations and Common Data Service</span></span>

[!include [banner](../includes/banner.md)]

[!include [preview](../includes/preview-banner.md)]

<span data-ttu-id="2284e-104">Az adatintegráció használata előtt létre kell hoznia a vevők, szállítók és kapcsolattartók számára szükséges kezdeti adatokat.</span><span class="sxs-lookup"><span data-stu-id="2284e-104">Before you use data integration, you must create the initial data that is required for customers, vendors, and contacts.</span></span> <span data-ttu-id="2284e-105">Például hozzon létre egy új **Szállítói csoport** elemet, és adja meg a **fizetési feltételek** értékét a **Net30** értékre.</span><span class="sxs-lookup"><span data-stu-id="2284e-105">For example, you want to create a new **Vendor group** item and set its **Terms of Payment** value to **Net30**.</span></span> <span data-ttu-id="2284e-106">Ebben az esetben a **Szállítói csoport** elemének létrehozása előtt meg kell győződni arról, hogy **a Net30** mind a Microsoft Dynamics 365 for Finance and Operations mind a Common Data Service megoldásokban létezik.</span><span class="sxs-lookup"><span data-stu-id="2284e-106">In this case, before you try to create the **Vendor group** item, you must make sure that **Net30** exists in both Microsoft Dynamics 365 for Finance and Operations and Common Data Service.</span></span> <span data-ttu-id="2284e-107">(Jövőben, a Microsoft kiad egy kettős írási funkciót, amelynek neve Kezdeti szinkronizálás lesz. Ez a funkció egy egyszeri adatszinkronizálást fog végezni a Finance and Operations és a Common Data Service között a kettős írás beállításának részeként.)</span><span class="sxs-lookup"><span data-stu-id="2284e-107">(In the future, Microsoft will release dual-write platform functionality that is named Initial Sync. This functionality will do a one-time data synchronization between Finance and Operations and Common Data Service as part of the dual-write setup.)</span></span>

> [!TIP]
> <span data-ttu-id="2284e-108">A Microsoft kias kettős írású leképezést minden referenciaadathoz beleértve a **Fizetési feltételek** (Fizetési feltételek) elemhez.</span><span class="sxs-lookup"><span data-stu-id="2284e-108">Microsoft is releasing a dual-write map for all reference data, including **Terms of Payment** (payment terms).</span></span> <span data-ttu-id="2284e-109">Ha már rendelkezik a kezdeti adatokkal az egyik rendszerben, a rekordon végzett kis frissítési művelet elindíthatja a kettős írást az adott rekordra vonatkozóan.</span><span class="sxs-lookup"><span data-stu-id="2284e-109">If you already have the initial data in one system, a small update operation on a record can trigger dual-write on that record.</span></span>

<span data-ttu-id="2284e-110">Kövesse az alábbi sorrendet, és győződjön meg arról, hogy a kezdeti adatok rendelkezésre állnak a Finance and Operations és a Common Data Service megoldásban is.</span><span class="sxs-lookup"><span data-stu-id="2284e-110">You must follow the following order of precedence and make sure that the initial data is available in both Finance and Operations and Common Data Service.</span></span>

## <a name="vendor"></a><span data-ttu-id="2284e-111">Szállító</span><span class="sxs-lookup"><span data-stu-id="2284e-111">Vendor</span></span>

<span data-ttu-id="2284e-112">A **Szállító** entitás végrehajtásának sorrendje:</span><span class="sxs-lookup"><span data-stu-id="2284e-112">Here is the order of execution for the **Vendor** entity:</span></span>

1. <span data-ttu-id="2284e-113">Szállítói csoport</span><span class="sxs-lookup"><span data-stu-id="2284e-113">Vendor group</span></span>

    1. <span data-ttu-id="2284e-114">Fizetési feltételek</span><span class="sxs-lookup"><span data-stu-id="2284e-114">Terms of payment</span></span>

        1. <span data-ttu-id="2284e-115">Fizetési nap és sorok</span><span class="sxs-lookup"><span data-stu-id="2284e-115">Payment day and lines</span></span>
        2. <span data-ttu-id="2284e-116">Fizetési ütemezés</span><span class="sxs-lookup"><span data-stu-id="2284e-116">Payment schedule</span></span>

2. <span data-ttu-id="2284e-117">Szállítói fizetési mód</span><span class="sxs-lookup"><span data-stu-id="2284e-117">Vendor payment method</span></span>

## <a name="customer-organization"></a><span data-ttu-id="2284e-118">Ügyfél (Szervezet)</span><span class="sxs-lookup"><span data-stu-id="2284e-118">Customer (Organization)</span></span>

<span data-ttu-id="2284e-119">Az **Ügyfél** entitás végrehajtásának sorrendje:</span><span class="sxs-lookup"><span data-stu-id="2284e-119">Here is the order of execution for the **Customer** entity:</span></span>

1. <span data-ttu-id="2284e-120">Vevőcsoport</span><span class="sxs-lookup"><span data-stu-id="2284e-120">Customer group</span></span>

    1. <span data-ttu-id="2284e-121">Fizetési feltételek</span><span class="sxs-lookup"><span data-stu-id="2284e-121">Terms of payment</span></span>

        1. <span data-ttu-id="2284e-122">Fizetési nap és sorok</span><span class="sxs-lookup"><span data-stu-id="2284e-122">Payment day and lines</span></span>
        2. <span data-ttu-id="2284e-123">Fizetés</span><span class="sxs-lookup"><span data-stu-id="2284e-123">Payment</span></span> 

2. <span data-ttu-id="2284e-124">Vevő fizetési módszere</span><span class="sxs-lookup"><span data-stu-id="2284e-124">Customer payment method</span></span>

## <a name="contact-person"></a><span data-ttu-id="2284e-125">Kapcsolattartó (személy)</span><span class="sxs-lookup"><span data-stu-id="2284e-125">Contact (Person)</span></span>

<span data-ttu-id="2284e-126">A **Kapcsolattartó** entitás végrehajtásának sorrendje:</span><span class="sxs-lookup"><span data-stu-id="2284e-126">Here is the order of execution for the **Contact** entity:</span></span>

1. <span data-ttu-id="2284e-127">Vevő</span><span class="sxs-lookup"><span data-stu-id="2284e-127">Customer</span></span>
2. <span data-ttu-id="2284e-128">Szállító</span><span class="sxs-lookup"><span data-stu-id="2284e-128">Vendor</span></span>
