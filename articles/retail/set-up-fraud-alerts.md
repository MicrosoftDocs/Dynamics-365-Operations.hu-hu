---
title: "Csalási figyelmeztetések beállítása"
description: "Ez a témakör ismerteti a szabályok beállítását az ügyfélszolgálati munkatársak figyelmeztetésére az esetleg csaló információról a rendelések feldolgozása során. Meghatározhat specifikus kódokat, hogy automatikusan vagy manuálisan várakoztassa a gyanús rendeléseket."
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: 79103
ms.assetid: e342af8d-7498-4d20-8483-ab368429c578
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 09d80015298c3d0219b6ffb290dc456990536a62
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---

# <a name="set-up-fraud-alerts"></a><span data-ttu-id="964e9-104">Csalási figyelmeztetések beállítása</span><span class="sxs-lookup"><span data-stu-id="964e9-104">Set up fraud alerts</span></span>

[!include[banner](includes/banner.md)]


<span data-ttu-id="964e9-105">Ez a témakör ismerteti a szabályok beállítását az ügyfélszolgálati munkatársak figyelmeztetésére az esetleg csaló információról a rendelések feldolgozása során.</span><span class="sxs-lookup"><span data-stu-id="964e9-105">This topic explains how to set up rules to alert customer service representatives of potentially fraudulent information when orders are processed.</span></span> <span data-ttu-id="964e9-106">Meghatározhat specifikus kódokat, hogy automatikusan vagy manuálisan várakoztassa a gyanús rendeléseket.</span><span class="sxs-lookup"><span data-stu-id="964e9-106">You can define specific codes to use to automatically or manually put suspicious orders on hold.</span></span> 

<span data-ttu-id="964e9-107">Mielőtt beállítja és használja a csalásellenőrzési szabályokat, engedélyeznie kell a csalásellenőrzést, és adja meg az alapvető csalásellenőrző értékeket a hívásközpont paramétereinél.</span><span class="sxs-lookup"><span data-stu-id="964e9-107">Before you set up and use fraud checking rules, you must enable fraud checking and define the basic fraud checking values in the call center parameters.</span></span> <span data-ttu-id="964e9-108">A csalási szabályok két típusa a következő:</span><span class="sxs-lookup"><span data-stu-id="964e9-108">There are two types of fraud rules:</span></span>

-   <span data-ttu-id="964e9-109">A **statikus szabályok** egy konkrét értéket használnak (például egy tiltólistára tett telefonszám).</span><span class="sxs-lookup"><span data-stu-id="964e9-109">**Static rules** use a specific value, such as a phone number that has been blacklisted.</span></span>
-   <span data-ttu-id="964e9-110">A **dinamikus szabályok** változókból és feltételekből állhatnak.</span><span class="sxs-lookup"><span data-stu-id="964e9-110">**Dynamic rules** can be composed from variables and conditions.</span></span>

<span data-ttu-id="964e9-111">Dinamikus szabály létrehozása előtt létre kell hoznia a változókat és a feltételeket, amelyek meghatározzák, kire vonatkozik a szabály, és a szabályt mikor kell alkalmazni.</span><span class="sxs-lookup"><span data-stu-id="964e9-111">Before you create a dynamic rule, you must create the variables and conditions that define who the rule applies to and when the rule should be applied.</span></span> <span data-ttu-id="964e9-112">Például szeretne létrehozni egy olyan szabályt, amely megköveteli, hogy, ha a 1202-es vevő elhelyez egy értékesítési rendelést, amely 1000,00-et vagy többet ér, akkor az értékesítési rendelést várakoztatni kell addig, amíg a vevői kifizetés igazolható nem lesz.</span><span class="sxs-lookup"><span data-stu-id="964e9-112">For example, you want to create a rule to require that any sales order that customer 1202 places that is worth 1,000.00 or more be put on hold until the customer payment can be verified.</span></span> <span data-ttu-id="964e9-113">Ebben a példában a változók a 1202-es vevő és az 1000,00 összrendelés.</span><span class="sxs-lookup"><span data-stu-id="964e9-113">In this case, the variables are customer 1202 and an order total of 1,000.00.</span></span> <span data-ttu-id="964e9-114">A feltétel szerint ha a 1202-es vevő felad egy rendelést, és a rendelés teljes összege 1000,00 vagy több, az értékesítési rendelést várakoztatni kell, amíg a vevői kifizetés ellenőrzése megtörténik.</span><span class="sxs-lookup"><span data-stu-id="964e9-114">The condition specifies that if customer 1202 places an order, and the total amount of the order is equal to or more than 1,000.00, the sales order must be put on hold until the customer payment can be verified.</span></span>



