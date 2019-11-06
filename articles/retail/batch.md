---
title: Kötegelt nyomkövetésű cikkek továbbfejlesztett kezelése
description: Ez a témakör azokat a fejlesztéseket mutatja be, amelyeket a kötegeknek a kötegelt nyomon követésű cikkek esetén, a kiskereskedelmi kimutatások feladási folyamata során történő kezelésével kapcsolatban vezettünk be.
author: josaw1
manager: AnnBe
ms.date: 10/14/2019
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-05-28
ms.dyn365.ops.version: 10
ms.openlocfilehash: 70d78f86f1df057d14d821a8c967e62eeeb4ff92
ms.sourcegitcommit: 0262a19e32b2c0c84c731d9f4fbe8ba91822afa3
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/15/2019
ms.locfileid: "2622550"
---
# <a name="improved-handling-of-batch-tracked-items"></a><span data-ttu-id="bfffc-103">Kötegelt nyomkövetésű cikkek továbbfejlesztett kezelése</span><span class="sxs-lookup"><span data-stu-id="bfffc-103">Improved handling of batch-tracked items</span></span>


[!include [banner](includes/banner.md)]

[!include [banner](includes/preview-banner.md)]


<span data-ttu-id="bfffc-104">A Retail POS (Pénztár) alkalmazásban a kötegelt nyomon követésű cikkek kötegszámai nem rögzíthetők az értékesítés pillanatában.</span><span class="sxs-lookup"><span data-stu-id="bfffc-104">In Retail Point of Sale (POS), batch numbers can't be captured for batch-tracked items at the time of sale.</span></span> <span data-ttu-id="bfffc-105">Bizonyos konfigurációk esetén azonban amikor az értékesítéseket a központban vevői rendeléseken vagy kimutatásfeladáson keresztül adják fel, a Microsoft Dynamics-rendszer arra számít, hogy a kötegelt nyomkövetésű cikkekhez léteznek érvényes kötegszámok, és ezeket használják majd a számlázási folyamat során.</span><span class="sxs-lookup"><span data-stu-id="bfffc-105">However, for specific configurations, when sales are posted in the headquarters through customer orders or statement posting, the Microsoft Dynamics system expects that valid batch numbers for batch-tracked items exist, and that they will be used during the invoicing process.</span></span>

<span data-ttu-id="bfffc-106">Ha a termékekhez léteznek érvényes kötegszámok, a rendszer ezeket használja a vevői rendelések számlázási folyamata és a kimutatásfeladásból származó értékesítési rendelés számlázási folyamata során.</span><span class="sxs-lookup"><span data-stu-id="bfffc-106">If valid batch numbers are available for products, the customer order invoicing process and the sales order invoicing process from statement posting use them.</span></span> <span data-ttu-id="bfffc-107">Ellenkező esetben a vevői rendelés számlázási folyamata nem képes a feladásra, és a pénztárfelhasználó számára hibaüzenet jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="bfffc-107">Otherwise, the customer order invoicing process can't post, and the POS user receives an error message.</span></span> <span data-ttu-id="bfffc-108">A kimutatásfeladás pedig hibás állapotba kerül.</span><span class="sxs-lookup"><span data-stu-id="bfffc-108">Statement posting then goes into an error state.</span></span> <span data-ttu-id="bfffc-109">Ez a hibás állapot akkor fordulhat elő, ha negatív készlet van bekapcsolva a termékekhez.</span><span class="sxs-lookup"><span data-stu-id="bfffc-109">This error state occurs even when negative inventory has been turned on for the products.</span></span>

<span data-ttu-id="bfffc-110">A Retail 10.0.4-es és újabb verzióiban végzett fejlesztésekkel biztosítható, hogy amikor negatív készlet van bekapcsolva a kötegelt nyomon követésű cikkekhez, a vevői rendelés és az értékesítési rendelés kimutatásfeladáson keresztül történő számlázása ne legyen zárolva az adott cikkekhez, ha a készlet 0 (nulla) vagy ha nincs elérhető kötegszám.</span><span class="sxs-lookup"><span data-stu-id="bfffc-110">Improvements that have been made in Retail version 10.0.4 and later help guarantee that, when negative inventory is turned on for batch-tracked items, customer order invoicing and sales order invoicing through statement posting aren't blocked for those items if the inventory is 0 (zero) or a batch number isn't available.</span></span> <span data-ttu-id="bfffc-111">Az új funkció alapértelmezett kötegazonosítót használ az értékesítési sorokhoz, ha nem találhatók kötegszámok.</span><span class="sxs-lookup"><span data-stu-id="bfffc-111">The new functionality uses a default batch ID for the sales lines when batch numbers aren't available.</span></span>

<span data-ttu-id="bfffc-112">A vevői rendelésekhez használt alapértelmezett kötegazonosító meghatározásához állítsa be az **Alapértelmezett kötegazonosító** mezőt a **Kiskereskedelmi paraméterek** lap **Vevői rendelések** fülének **Rendelés** gyorslapján.</span><span class="sxs-lookup"><span data-stu-id="bfffc-112">To define the default batch ID that is used for customer orders, on the **Retail parameters** page, on the **Customer orders** tab, on the **Order** FastTab, set the **Default batch id** field.</span></span>

<span data-ttu-id="bfffc-113">Az értékesítési rendelések kimutatásfeladáson keresztül történő számlázásához használt alapértelmezett kötegazonosító meghatározásához állítsa be az **Alapértelmezett kötegazonosító** mezőt a **Kiskereskedelmi paraméterek** lap **Feladás** fülének **Készletfrissítés** gyorslapján.</span><span class="sxs-lookup"><span data-stu-id="bfffc-113">To define the default batch ID that is used for sales order invoicing through statement posting, on the **Retail parameters** page, on the **Posting** tab, on the **Inventory update** FastTab, set the **Default batch id** field.</span></span>

> [!NOTE]
> <span data-ttu-id="bfffc-114">Ez a funkció csak akkor áll rendelkezésre, ha a megadott tárolási raktárhoz és cikkekhez be van kapcsolva a speciális raktárkezelés.</span><span class="sxs-lookup"><span data-stu-id="bfffc-114">This functionality is available only when advanced warehousing is turned on for the specific store warehouse and items.</span></span> <span data-ttu-id="bfffc-115">Egy későbbi kiadásban a funkció már olyan esetekben is támogatott lesz, ahol nem használják a speciális raktárkezelést.</span><span class="sxs-lookup"><span data-stu-id="bfffc-115">In a later release, the functionality will also be supported for scenarios where advanced warehouse management isn't used.</span></span>

> [!NOTE]
> <span data-ttu-id="bfffc-116">A kötegelt nyomkövetésű cikkek továbbfejlesztett kezelése a nem speciális raktárkezelési esetek kimutatásfeladása során a Retail 10.0.5 verziójában bevezetett funkció.</span><span class="sxs-lookup"><span data-stu-id="bfffc-116">Support for improved handling of batch-tracked items during statement posting for non-advanced warehouse management scenarios was introduced in Retail version 10.0.5.</span></span>
