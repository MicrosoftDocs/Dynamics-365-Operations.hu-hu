---
title: Az aktuális készlet költségértékeinek korrekciója
description: Az Aktuális készlet korrekciója lapon beállíthatja az aktuális készlet mennyiségeinek költségértékét a készletzárási folyamat futtatása után.
author: AndersGirke
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventAdjInventOnHand
audience: Application User
ms.reviewer: kamaybac
ms.custom: 53231
ms.assetid: bc1fde9f-5ad9-4339-8ae8-e2839b792eb2
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: aevengir
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9ddb2962926e78fda80a9db7b9e5915550bc5965
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5842201"
---
# <a name="adjust-on-hand-inventory-cost-values"></a><span data-ttu-id="0cea5-103">Az aktuális készlet költségértékeinek korrekciója</span><span class="sxs-lookup"><span data-stu-id="0cea5-103">Adjust on-hand inventory cost values</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0cea5-104">Az Aktuális készlet korrekciója lapon beállíthatja az aktuális készlet mennyiségeinek költségértékét a készletzárási folyamat futtatása után.</span><span class="sxs-lookup"><span data-stu-id="0cea5-104">Use the Adjustment of on-hand inventory page to adjust the cost value of the on-hand inventory quantities after an inventory close process is run.</span></span>

<span data-ttu-id="0cea5-105">Az **Aktuális készlet korrekciója** oldalon módosíthatja az aktuális készlet mennyiségeinek költségértékét a készletzárási folyamat futtatása után.</span><span class="sxs-lookup"><span data-stu-id="0cea5-105">You can use the **Adjustment of on-hand inventory** page to adjust the cost value of on-hand inventory quantities after an inventory close process is run.</span></span> <span data-ttu-id="0cea5-106">**Megjegyzés**: az **Aktuális készlet korrekciója** oldalon a **Zárás és helyesbítés lapon** válasszon ki egy befejezett készletzárási folyamatrekordot, majd kattintson a **Korrekció** &gt; **Aktuális** elemre.</span><span class="sxs-lookup"><span data-stu-id="0cea5-106">**Note:** To open the **Adjustment of on-hand inventory** page, on the **Closing and adjustment** page, select the record of a completed inventory close process, and then click **Adjustment** &gt; **On-hand**.</span></span> <span data-ttu-id="0cea5-107">**Példa:** Februárban a következő tranzakciók voltak:</span><span class="sxs-lookup"><span data-stu-id="0cea5-107">**Example:** You have the following transactions in February:</span></span>

-   <span data-ttu-id="0cea5-108">Február 1.: pénzügyi bevételezés készletre, 2 mennyiséggel, 10,00 USD áron</span><span class="sxs-lookup"><span data-stu-id="0cea5-108">February 1: An inventory financial receipt for a quantity of 2 at a cost of USD 10.00</span></span>
-   <span data-ttu-id="0cea5-109">Február 5.: pénzügyi bevételezés készletre, 1 mennyiséggel, 13,00 USD áron</span><span class="sxs-lookup"><span data-stu-id="0cea5-109">February 5: An inventory financial receipt for a quantity of 1 at a cost of USD 13.00</span></span>
-   <span data-ttu-id="0cea5-110">Február 19.: pénzügyi kiadás készletről, 1 mennyiséggel, 11, 00 USD mozgóátlagon alapuló önköltségi áron</span><span class="sxs-lookup"><span data-stu-id="0cea5-110">February 19: An inventory financial issue for a quantity of 1 at a running average cost of USD 11.00</span></span>

<span data-ttu-id="0cea5-111">Ez a cikk az elsőként be, elsőként ki FIFO készletmodellhez van beállítva, február 28-án történik a készletzárás.</span><span class="sxs-lookup"><span data-stu-id="0cea5-111">This item was set up with the first in, first out (FIFO) inventory model, and inventory close was performed as of February 28.</span></span> <span data-ttu-id="0cea5-112">A 11,00 USD értékű pénzügyi kiadási tranzakció a február 1-jei pénzügyi bevételezéssel szemben lesz kiegyenlítve, 1,00 USD lesz a korrekció.</span><span class="sxs-lookup"><span data-stu-id="0cea5-112">The financial issue transaction of USD 11.00 will be settled against the financial receipt that is dated February 1, and an adjustment of USD 1.00 will be made.</span></span> <span data-ttu-id="0cea5-113">A következő készletbevételezések ekkor nyitott készletmennyiségeket tartalmaznak:</span><span class="sxs-lookup"><span data-stu-id="0cea5-113">The following inventory receipts will then contain open inventory quantities:</span></span>

-   <span data-ttu-id="0cea5-114">Febuár 1: mennyiség: 1, a költség 10,00 USD.</span><span class="sxs-lookup"><span data-stu-id="0cea5-114">February 1: A quantity of 1 at a cost of USD 10.00</span></span>
-   <span data-ttu-id="0cea5-115">Febuár 5: mennyiség: 1, a költség 13,00 USD.</span><span class="sxs-lookup"><span data-stu-id="0cea5-115">February 5: A quantity of 1 at a cost of USD 13.00</span></span>

<span data-ttu-id="0cea5-116">Ahhoz, hogy ennek a két cikknek az árát 15,00 USD értékre lehessen beállítani, az aktuális készlet módosítására használható funkcióval korrigálni kell a nyitott aktuális készletmennyiségeket a legutolsó készletzárási időszaknak megfelelően.</span><span class="sxs-lookup"><span data-stu-id="0cea5-116">To set the cost of these two items to USD 15.00, use the on-hand adjustment option to adjust the open on-hand quantities as of the last inventory close period.</span></span> <span data-ttu-id="0cea5-117">**Megjegyzés:** Az aktuális készletet korrigáló tranzakció feladási dátuma a legutóbbi készletzárás dátuma lesz.</span><span class="sxs-lookup"><span data-stu-id="0cea5-117">**Note:** The posting date of the on-hand adjustment transaction will be the date of the last inventory close.</span></span> <span data-ttu-id="0cea5-118">Ez a dátum nem módosítható.</span><span class="sxs-lookup"><span data-stu-id="0cea5-118">This date can't be modified.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]