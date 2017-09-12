---
title: "Rendelésvárakoztatások"
description: "Ez a témakör bemutatja a Dynamics 365 for Retail rendszer használatával történő rendelésvárakoztatást."
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
ms.custom: 79132
ms.assetid: 7c00dc35-73e5-400a-8587-22f37ddfc0e0
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: Human Translation
ms.sourcegitcommit: 08c38aada355583c5a6872f75b57db95d9b81786
ms.openlocfilehash: 14dab07075a3f042e0095b912e51768ccb086f0e
ms.contentlocale: hu-hu
ms.lasthandoff: 07/18/2017

---

# <a name="order-holds"></a><span data-ttu-id="09506-103">Rendelésvárakoztatások</span><span class="sxs-lookup"><span data-stu-id="09506-103">Order holds</span></span>

[!include[banner](includes/banner.md)]


<span data-ttu-id="09506-104">Ez a témakör bemutatja a Dynamics 365 for Retail rendszer használatával történő rendelésvárakoztatást.</span><span class="sxs-lookup"><span data-stu-id="09506-104">This topic describes holds on orders using Dynamics 365 for Retail.</span></span>

<span data-ttu-id="09506-105">Egy rendelés visszatartásának több oka is lehet.</span><span class="sxs-lookup"><span data-stu-id="09506-105">An order can be put on hold for various reasons.</span></span> <span data-ttu-id="09506-106">Például előfordulhat, hogy egy megrendelés mindaddig várakoztatva van, amíg a vevő címe, vagy a fizetési mód ellenőrzésre nem kerül, vagy amíg a vezető ellenőrzi a vevő hitelkeretét.</span><span class="sxs-lookup"><span data-stu-id="09506-106">For example, you might put an order on hold until the customer address or payment method can be verified, or until a manager can review the customer’s credit limit.</span></span> <span data-ttu-id="09506-107">Az értékesítési folyamat során vannak olyan időszakok, amikor várakoztatni kell az értékesítési rendeléseket.</span><span class="sxs-lookup"><span data-stu-id="09506-107">During the sales process, there are times when sales orders must be put on hold.</span></span> <span data-ttu-id="09506-108">Például egy értékesítési rendelés várakoztatásának oka lehet vevői kifizetéssel kapcsolatos probléma, csalás vagy a vezető felülvizsgálatára történő várakozás miatt.</span><span class="sxs-lookup"><span data-stu-id="09506-108">For example, a sales order might be put on hold because of issues with a customer payment, because of suspected fraud, or because a manager must review the order.</span></span> <span data-ttu-id="09506-109">Amikor az értékesítési rendelés várakoztatva van, egy rendelési várakoztatási kódot társítunk az értékesítési rendeléshez, hogy jelezze a várakoztatás okát.</span><span class="sxs-lookup"><span data-stu-id="09506-109">When a sales order is put on hold, an order hold code is assigned to the sales order to indicate the reason for the hold.</span></span> <span data-ttu-id="09506-110">Az értékesítési rendelések várakoztatási kódjai az **Értékesítés és marketing** &gt; **Beállítás** &gt; **Értékesítési rendelések** &gt; **Rendelésvárakoztatási kódok** részben konfigurálhatók.</span><span class="sxs-lookup"><span data-stu-id="09506-110">Sales order hold codes are configured at **Sales and marketing** &gt; **Setup** &gt; **Sales orders** &gt; **Order holds codes**.</span></span> <span data-ttu-id="09506-111">Egy értékesítési rendeléshez be lehet állítani a várakoztatást manuálisan a rendelések létrehozásakor vagy később.</span><span class="sxs-lookup"><span data-stu-id="09506-111">A sales order can be put on hold manually at the time of order creation or later.</span></span> <span data-ttu-id="09506-112">Emellett egy rendelés automatikusan is várakoztatható a csalási szabályok alapján.</span><span class="sxs-lookup"><span data-stu-id="09506-112">Additionally, an order can be put on hold automatically, based on fraud rules.</span></span> <span data-ttu-id="09506-113">Amíg egy értékesítési rendelés várakoztatva van, előfordulhat, hogy további információkkal kell frissíteni.</span><span class="sxs-lookup"><span data-stu-id="09506-113">While a sales order is on hold, you might have to update it with more information.</span></span> <span data-ttu-id="09506-114">Azt is megteheti, hogy kiveszi az értékesítési rendelést, miközben tovább dolgozik rajta.</span><span class="sxs-lookup"><span data-stu-id="09506-114">Alternatively, you might want to check out the sales order as you continue to work on it.</span></span> <span data-ttu-id="09506-115">Kivehet egy értékesítési rendelést, visszarakhatja, illetve felülbírálhat más felhasználók által végrehajtott kivételeket a rendelésvárakoztatási munkaterület segítségével (**Kiskereskedelem** &gt; **Vevők** &gt; **Rendelésvárakoztatások**).</span><span class="sxs-lookup"><span data-stu-id="09506-115">You can check out a sales order, check it back in, and even override the checkout of another user by using the order hold workbench (**Retail** &gt; **Customers** &gt; **Order holds**).</span></span> <span data-ttu-id="09506-116">Ha egy rendelést már be lehet fejezni, a befejezés előtt el kell távolítania a várakoztatást.</span><span class="sxs-lookup"><span data-stu-id="09506-116">When an order is ready to be completed, you must remove the hold before you can complete the order process.</span></span>




