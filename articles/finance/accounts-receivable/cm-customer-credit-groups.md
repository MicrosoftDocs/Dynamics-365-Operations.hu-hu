---
title: Vevői hitelcsoportok
description: Ez a témakör a vevői hitelcsoportokkal kapcsolatban tartalmaz információkat.
author: mikefalkner
manager: AnnBe
ms.date: 04/14/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschloma
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 76b1e93d562e66cb8d4c5819a749459ea8783b1e
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5237542"
---
# <a name="customer-credit-groups"></a><span data-ttu-id="3ff02-103">Vevői hitelcsoportok</span><span class="sxs-lookup"><span data-stu-id="3ff02-103">Customer credit groups</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="3ff02-104">Meghatározhatja a vevők olyan csoportjait, akiknek megosztott hitelkerete van.</span><span class="sxs-lookup"><span data-stu-id="3ff02-104">You can define groups of customers who have a shared credit limit.</span></span> <span data-ttu-id="3ff02-105">A program a vevői számlafiókjában megadott egyéni hitelkeretet is figyelembe veszi.</span><span class="sxs-lookup"><span data-stu-id="3ff02-105">The individual credit limit that is defined on the customer invoice account is also considered.</span></span>

<span data-ttu-id="3ff02-106">A vevői hitelcsoport tagjait különböző jogi személyek közül lehet kiválasztani.</span><span class="sxs-lookup"><span data-stu-id="3ff02-106">Members of a customer credit group can be selected from different legal entities.</span></span> <span data-ttu-id="3ff02-107">Amikor egy vevőt ad hozzá a vevők listájához a vevői hitelcsoportban, akkor az egyes vevők hitelkeretének lejárati dátuma a csoporthoz rendelt lejárati dátumra módosul.</span><span class="sxs-lookup"><span data-stu-id="3ff02-107">When you add a customer to the list of customers in the customer credit group, the expiration date of the credit limit for each customer is changed to the expiration date that is assigned to the group.</span></span>

<span data-ttu-id="3ff02-108">Beállíthat vevői hitelcsoportokat a **Vevői hitelcsoportok** oldalon (**Hitelkezelés \> Vevői hitelcsoportok \> Vevői hitelcsoportok**).</span><span class="sxs-lookup"><span data-stu-id="3ff02-108">You can set up customer credit groups on the **Customer credit groups** page (**Credit management \> Customer credit groups \> Customer credit groups**).</span></span>

1. <span data-ttu-id="3ff02-109">A **Csoport száma** és **Leírás** mezőkben adja meg a csoport azonosítóját és leírását.</span><span class="sxs-lookup"><span data-stu-id="3ff02-109">In the **Group number** and **Description** fields, enter an identifier and description for the group.</span></span>
2. <span data-ttu-id="3ff02-110">A **Hitelkeret** és a **Pénznem** mezőkben adja meg azt a hitelkeretet és pénznemet, amelyet akkor kell használni, amikor a rendszer a csoport bármely tagja számára ellenőrzi a hitelkeretet.</span><span class="sxs-lookup"><span data-stu-id="3ff02-110">In the **Credit limit** and **Currency** fields, enter the credit limit and currency that should be used when the system checks the credit limit for any member of the group.</span></span>
3. <span data-ttu-id="3ff02-111">A **Hitelkeret dátuma** mezőbe írja be a dátumot, amikor a hitelkeret lejár.</span><span class="sxs-lookup"><span data-stu-id="3ff02-111">In the **Credit limit to date** field, enter the date when the credit limit expires.</span></span> <span data-ttu-id="3ff02-112">A vevői hitelcsoportoknak lejárati dátummal kell rendelkezniük.</span><span class="sxs-lookup"><span data-stu-id="3ff02-112">Customer credit groups must have an expiration date.</span></span>

<span data-ttu-id="3ff02-113">Miután befejezte a vevői hitelcsoport beállítását, vevőket adhat hozzá azok jogi személyének és vevői számlaazonosítójának meghatározásával.</span><span class="sxs-lookup"><span data-stu-id="3ff02-113">After you've finished setting up a customer credit group, you can add customers to it by specifying their legal entity and customer account ID.</span></span> <span data-ttu-id="3ff02-114">Amikor új vevőt ad hozzá egy vevői hitelcsoporthoz, a rendszer az összes jogi személy között ugyanarra a vevői számlára keres, és a felkéri, hogy adja hozzá a vevői hitelcsoporthoz.</span><span class="sxs-lookup"><span data-stu-id="3ff02-114">When you add a new customer to a customer credit group, the system searches for the same customer account across all legal entities and prompts you to add it to the customer credit group.</span></span>

<span data-ttu-id="3ff02-115">A **Korosított egyenlegek** menü használatával megtekintheti a vevői hitelcsoportban szereplő összes számlaügyfél korosítási egyenlegének adatait.</span><span class="sxs-lookup"><span data-stu-id="3ff02-115">Use the **Aged balances** menu to view the details of the aging balance for all invoice customers in a customer credit group.</span></span> <span data-ttu-id="3ff02-116">A **Korosítási egyenleg** lap a korosított egyenlegek összegzését jeleníti meg a számlaügyfél-fiókokhoz.</span><span class="sxs-lookup"><span data-stu-id="3ff02-116">The **Aging balance** page shows a summary of the aged balances for the invoice customer accounts.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]