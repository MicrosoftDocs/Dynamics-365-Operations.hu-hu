---
title: Áfafizetés kód szerint jelentés nyomtatása
description: Ez a témakör olyan beállításokat és műveleteket tartalmaz, amelyek szükségesek az Áfa kifizetése kód szerinti jelentés szerinti kinyomtatásához a könyvelés vagy adózási kód pénznemében.
author: anasyash
manager: AnnBe
ms.date: 05/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: anasyash
ms.search.validFrom: 2020-04-08
ms.dyn365.ops.version: 10.0.11
ms.openlocfilehash: 7033999f7258e9ddd1d01620f9ad416e94ef3111
ms.sourcegitcommit: 39981582778b0a62567324452485a6721ca18284
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/27/2020
ms.locfileid: "3407475"
---
# <a name="print-the-sales-tax-payment-by-code-report"></a><span data-ttu-id="c2edb-103">Áfafizetés kód szerint jelentés nyomtatása</span><span class="sxs-lookup"><span data-stu-id="c2edb-103">Print the Sales tax payment by code report</span></span> 

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c2edb-104">Az **Áfafizetés kód szerint** jelentés kinyomtatásához nyissa meg az **Adó** \> **Lekérdezések és jelentések** \> **Áfajelentések** \> **Áfafizetés kód szerint** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c2edb-104">To print the **Sales tax payment by code** report, go to **Tax** \> **Inquiries and reports** \> **Sales tax reports** \> **Sales tax payment by code**.</span></span> <span data-ttu-id="c2edb-105">Alapértelmezés szerint a jelentés összegeit a program a jogi személy könyvelési pénznemében generálja az összes jelentési kód esetében, amelyek az **Áfajelentési kódok** oldalon be van állítva.</span><span class="sxs-lookup"><span data-stu-id="c2edb-105">By default, report amounts are generated in the accounting currency of the legal entity for all reporting codes that are set up on the **Sales tax reporting codes** page.</span></span>

<span data-ttu-id="c2edb-106">Ezt a jelentést úgy is generálhatja, hogy az áfakód pénznemében megjelenített forgalmiadó-összegeket minden olyan jelentési kód esetében megjeleníti, amelyek az **Áfakód** lapon hozzá vannak rendelve az áfakódokhoz.</span><span class="sxs-lookup"><span data-stu-id="c2edb-106">You can also generate this report so that it shows the sales tax payment amounts in the currencies of sales tax codes for all reporting codes that are assigned to sales tax codes on the **Sales tax codes** page.</span></span>

## <a name="turn-on-the-feature"></a><span data-ttu-id="c2edb-107">A funkció bekapcsolása</span><span class="sxs-lookup"><span data-stu-id="c2edb-107">Turn on the feature</span></span>

<span data-ttu-id="c2edb-108">A **Funkciókezelés** munkaterületen kapcsolja be a következő funkciót: **Áfafizetés kód szerint jelentés generálása az áfakód pénznemében**.</span><span class="sxs-lookup"><span data-stu-id="c2edb-108">In the **Feature management** workspace, turn on the following feature: **Generate the Sales tax payment by code report in the sales tax code currency**.</span></span>

## <a name="run-the-report"></a><span data-ttu-id="c2edb-109">A jelentés futtatása</span><span class="sxs-lookup"><span data-stu-id="c2edb-109">Run the report</span></span>

1. <span data-ttu-id="c2edb-110">Ugorjon az **Adó** \> **Lekérdezések és jelentések** \> **Áfajelentések** \> **Áfafizetés kód szerint** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="c2edb-110">Go to **Tax** \> **Inquiries and reports** \> **Sales tax reports** \> **Sales tax payment by code**.</span></span>
2. <span data-ttu-id="c2edb-111">A **Jelentés pénzneme** mezőben válassza a következő értékek egyikét:</span><span class="sxs-lookup"><span data-stu-id="c2edb-111">In the **Report currency** field, select one of the following values:</span></span>

    - <span data-ttu-id="c2edb-112">**Könyvelési pénznem** – A jelentés összegeinek nyomtatása a könyvelési pénznemben.</span><span class="sxs-lookup"><span data-stu-id="c2edb-112">**Accounting currency** – Print the report amounts in the accounting currency.</span></span>
    - <span data-ttu-id="c2edb-113">**Áfakód pénzneme** – A jelentés összegének nyomtatása az áfakód pénznemében.</span><span class="sxs-lookup"><span data-stu-id="c2edb-113">**Sales tax code currency** – Print the report amounts in the currencies of sales tax codes.</span></span>

    ![Áfafizetés kód szerint párbeszédpanel](media/Sales-tax-payment-by-code.png)

<span data-ttu-id="c2edb-115">A következő ábra egy példát mutat be a generált jelentésre.</span><span class="sxs-lookup"><span data-stu-id="c2edb-115">The following illustration shows an example of the report that is generated.</span></span> <span data-ttu-id="c2edb-116">A jelentés azt jeleníti meg , hogy a **101** jelentési kód az pénzneme **EUR** ha az **Áfa pénzneme mező** **EUR** értékre van állítva az áfakódhoz, amelyhez a jelentési kód hozzá van rendelve.</span><span class="sxs-lookup"><span data-stu-id="c2edb-116">The report shows that reporting code **101** has the **EUR** currency if the **Sales tax currency** field is set to **EUR** for the sales tax code that the reporting code is assigned to.</span></span>

![Áfafizetés kód szerint jelentés nyomtatása példája](media/Sales-tax-payment-by-code-2.png)
