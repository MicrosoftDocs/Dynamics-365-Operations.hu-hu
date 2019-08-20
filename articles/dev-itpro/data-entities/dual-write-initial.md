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
ms.openlocfilehash: b74bc2d3133af7e87663a4e6bafb8780e0a6a66f
ms.sourcegitcommit: efcc0dee8bde5f8f93f6291e7f059ad426843e57
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/31/2019
ms.locfileid: "1797298"
---
# <a name="execution-order-for-initial-sychronization-of-finance-and-operations-and-common-data-service"></a><span data-ttu-id="41656-103">Végrehajtási sorrend a Finance and Operations és a Common Data Service kezdeti szinkronizálásához</span><span class="sxs-lookup"><span data-stu-id="41656-103">Execution order for initial sychronization of Finance and Operations and Common Data Service</span></span>

<span data-ttu-id="41656-104">Az adatintegráció használata előtt létre kell hoznia a vevők, szállítók és kapcsolattartók számára szükséges kezdeti adatokat.</span><span class="sxs-lookup"><span data-stu-id="41656-104">Before you use data integration, you must create the initial data required for customers, vendors and contacts.</span></span> <span data-ttu-id="41656-105">Ha például **Új szállítói csoport** cikket szeretne létrehozni, és a **Fizetési feltételeket** **Net30** értékre szeretné beállítani akkor a **Szállítói csoport** cikk létrehozása előtt meg kell győződnie arról, hogy **Net30** létezik mind a Finance and Operations, mind a Common Data Service megoldásokban.</span><span class="sxs-lookup"><span data-stu-id="41656-105">For example, if you want to create a new **Vendor group** item and set its **Terms of Payment** as **Net30**, then before you attempt to create the **Vendor group** item you need to make sure that **Net30** exists in both Finance and Operations and Common Data Service.</span></span> <span data-ttu-id="41656-106">(Jövőben, kiadunk egy kettős írási funkciót, amelynek neve **Kezdeti szinkronizálás** lesz. Ez egy egyszeri adatszinkronizálást fog végezni a Finance and Operations és a Common Data Service között a kettős írás beállításának részeként.)</span><span class="sxs-lookup"><span data-stu-id="41656-106">(In the future, we will release a  dual-write platform functionality called **Initial Sync**. It will do a one-time data synchronization between Finance and Operations and Common Data Service as part of the dual-write setup.)</span></span>

<span data-ttu-id="41656-107">Tippek: Felszabadítunk egy kettős írású leképezést minden referenciaadathoz beleértve a **Fizetési feltételek** elemhez.</span><span class="sxs-lookup"><span data-stu-id="41656-107">Tips: We are releasing a dual-write map for all reference data including **Terms of Payment** (Payment Terms).</span></span> <span data-ttu-id="41656-108">Ha már rendelkezik a kezdeti adatokkal az egyik rendszerben, a rekordon végzett kis frissítési művelet elindíthatja a kettős írást az adott rekordra vonatkozóan.</span><span class="sxs-lookup"><span data-stu-id="41656-108">If you already have the initial data in one system, a small update operation on a record can trigger dual-write on that record.</span></span> 

<span data-ttu-id="41656-109">Kövesse az alábbi sorrendet, és győződjön meg arról, hogy a kezdeti adatok rendelkezésre állnak a Finance and Operations és a Common Data Service megoldásban is.</span><span class="sxs-lookup"><span data-stu-id="41656-109">You must follow the following order of precedence and make sure that the initial data is available on both Finance and Operations and Common Data Service.</span></span>   

## <a name="vendor"></a><span data-ttu-id="41656-110">Szállító</span><span class="sxs-lookup"><span data-stu-id="41656-110">Vendor</span></span>

<span data-ttu-id="41656-111">A végrehajtási sorrend Szállítóhoz:</span><span class="sxs-lookup"><span data-stu-id="41656-111">The order of execution for Vendor is:</span></span>

```
Vendor Group
    Terms of payment
        Payment day & lines
        Payment schedule
Vendor payment method
```

## <a name="customer-organization"></a><span data-ttu-id="41656-112">Ügyfél (Szervezet)</span><span class="sxs-lookup"><span data-stu-id="41656-112">Customer (Organization)</span></span>

<span data-ttu-id="41656-113">A végrehajtási sorrend az ügyfélhez:</span><span class="sxs-lookup"><span data-stu-id="41656-113">The order of execution for Customer is:</span></span>

```
Customer Group
    Terms of payment
        Payment day & lines
        Payment 
Customer payment method
```

## <a name="contact-person"></a><span data-ttu-id="41656-114">Kapcsolattartó (személy)</span><span class="sxs-lookup"><span data-stu-id="41656-114">Contact (Person)</span></span>

<span data-ttu-id="41656-115">A végrehajtási sorrend a Kapcsolattartóhoz:</span><span class="sxs-lookup"><span data-stu-id="41656-115">The order of execution for Contact is:</span></span>

```
Customer
Vendor               
```
