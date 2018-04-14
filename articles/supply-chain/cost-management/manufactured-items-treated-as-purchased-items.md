---
title: "Gyártható vagy beszerezhető termékek beállítása"
description: "A termékek több forrásból is származhatnak - előállíthatók (gyárthatók) vagy beszerezhetők (vásárolhatók). Ez a cikk néhány jellegzetes pontot ismertet, amelyeket figyelembe kell venni amikor a termékek többszörös forráshoz való konfigurálását végzi."
author: cvocph
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ReqGroup, ReqItemTable
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 21841
ms.assetid: acc608b7-2cad-4fba-afee-9b7cc93761ec
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 81f556dca0bfa17623bb1a0f1c712bfa5a4a2a9b
ms.contentlocale: hu-hu
ms.lasthandoff: 04/13/2018

---

# <a name="set-up-products-that-can-be-produced-or-procured"></a><span data-ttu-id="0057c-104">Gyártható vagy beszerezhető termékek beállítása</span><span class="sxs-lookup"><span data-stu-id="0057c-104">Set up products that can be produced or procured</span></span>

[!INCLUDE [banner](../includes/banner.md)]

<span data-ttu-id="0057c-105">A termékek több forrásból is származhatnak - előállíthatók (gyárthatók) vagy beszerezhetők (vásárolhatók).</span><span class="sxs-lookup"><span data-stu-id="0057c-105">Products can be sourced in various ways -  they can be produced (manufactured) or procured (purchased).</span></span> <span data-ttu-id="0057c-106">Ez a cikk néhány jellegzetes pontot ismertet, amelyeket figyelembe kell venni amikor a termékek többszörös forráshoz való konfigurálását végzi.</span><span class="sxs-lookup"><span data-stu-id="0057c-106">This article describes some typical points to consider when you configure products to support multi-sourcing.</span></span> 

<span data-ttu-id="0057c-107">Többszörös-forrás általában használatos egy beszerzett cikket időnként gyártanak, vagy a cikket, amelyet egy gyártott cikket elsődlegesen volt, hogy a jelenleg elsősorban a beszerzett cikk változásának.</span><span class="sxs-lookup"><span data-stu-id="0057c-107">Multi-sourcing is typically used for a purchased item that is occasionally manufactured, or when an item that was primarily a manufactured item is changed so that it's now primarily a purchased item.</span></span> <span data-ttu-id="0057c-108">A cikk kezdetben gyártott cikként lesz megadva az anyagjegyzék- és útvonal-információk megadásához, valamint a cikkre vonatkozó termelési rendelések alátámasztására.</span><span class="sxs-lookup"><span data-stu-id="0057c-108">The item is first designated as a manufactured item, so that bill of materials (BOM) and route information can be defined, and to support production orders for the item.</span></span> <span data-ttu-id="0057c-109">A termelés típusa értékre kell állítani **Anyagjegyzék** (vagy a gyártási folyamat, **Képlet** vagy **Társtermék**).</span><span class="sxs-lookup"><span data-stu-id="0057c-109">The production type should be set to **BOM** (or, for process manufacturing, **Formula** or **Co-Product**).</span></span>

<span data-ttu-id="0057c-110">Elszámolóár használata esetén a cikk-költség rekord kiszámítható a legyártott cikkre vonatkozóan.</span><span class="sxs-lookup"><span data-stu-id="0057c-110">When you use standard cost, the item cost record can be calculated for the manufactured item.</span></span> <span data-ttu-id="0057c-111">A szükséges elszámolóárat manuálisan kell bevinni, és aktiválni kell a cikk-költség rekordhoz.</span><span class="sxs-lookup"><span data-stu-id="0057c-111">However, the item cost record might not match the standard cost that you want for purchasing purposes.</span></span> <span data-ttu-id="0057c-112">A szükséges elszámolóárat manuálisan kell bevinni, és aktiválni kell a cikk-költség rekordhoz.</span><span class="sxs-lookup"><span data-stu-id="0057c-112">In this case, the standard cost must be manually entered and activated for the item cost record.</span></span> <span data-ttu-id="0057c-113">A költségszámítás a speciális Anyagjegyzék vagy útvonal csökkentése érdekében az eltéréseket, időbeli eloszlás szerint, a pénzügyi időszak során a termék a készletek kombinációs jelölő használatával figyelembe kell venni.</span><span class="sxs-lookup"><span data-stu-id="0057c-113">For the cost calculation, consider using a special BOM and route that represent the supply mix of the product over the course of a fiscal period, to minimize the variances over time.</span></span> <span data-ttu-id="0057c-114">Ezenkívül egy gyártott cikket az egyik helyen át lehet vinni egy másik helyen.</span><span class="sxs-lookup"><span data-stu-id="0057c-114">Additionally, a manufactured item at one site can be transferred to another site.</span></span> <span data-ttu-id="0057c-115">Emiatt a cikk-költség kell manuálisan megadott és a helyet, amelyhez a cikk átkerül aktiválva.</span><span class="sxs-lookup"><span data-stu-id="0057c-115">Therefore, the item's cost must be manually entered and activated for the site that the item is transferred to.</span></span> <span data-ttu-id="0057c-116">Amikor a legyártott cikket magasabb szintű termék összetevőjeként felhasználják, az összetevő költségeit beszerzett cikként kell kezelni attól függetlenül, hogy azok számítással vagy manuális bevitellel álltak elő.</span><span class="sxs-lookup"><span data-stu-id="0057c-116">When you use the manufactured item as a component in higher-level products, the component's costs should be treated as a purchased item.</span></span> <span data-ttu-id="0057c-117">Ezen iránymutatás vonatkozik, függetlenül attól, hogy az összetevő költségeit azt, hogy megtörtént kiszámított vagy manuálisan kell megadni.</span><span class="sxs-lookup"><span data-stu-id="0057c-117">This guideline applies, regardless of whether the component’s costs were calculated or manually entered.</span></span> <span data-ttu-id="0057c-118">Tehát az anyagjegyzék-számításnak a cikk költségét beszerzett összetevőként kell kezelnie ahelyett, hogy az anyagjegyzék és az útvonal adatai alapján kiszámítaná a költséget.</span><span class="sxs-lookup"><span data-stu-id="0057c-118">In other words, a BOM calculation should treat the item's costs as a purchased component instead of using the item's BOM and route information to calculate costs.</span></span> 

<span data-ttu-id="0057c-119">A számítást a cikkhez rendelt anyagjegyzék-számítási csoporthoz tartozó **Alábontást leállító** jelző beállításával lehet megakadályozni.</span><span class="sxs-lookup"><span data-stu-id="0057c-119">To prevent the calculation from occurring, select the **Stop explosion** flag that is embedded in the BOM calculation group that is assigned to the item.</span></span> <span data-ttu-id="0057c-120">Az alapütemezési számításoknál a cikken keresztül megakadályozható az igények alábontása, ha a cikkhez tartozó, (cikkfedezethez) alábontást leállító jelző 0 (nulla) napra van állítva.</span><span class="sxs-lookup"><span data-stu-id="0057c-120">To prevent master scheduling calculations from exploding requirements through the item, set the explosion fence to 0 (zero) days in item coverage or in the coverage group.</span></span> <span data-ttu-id="0057c-121">Az alapütemezés kiszámításában majd kezeli a cikk beszerzett cikként, és nem számításokat további a cikkhez tartozó Anyagjegyzék és útvonal-információkat.</span><span class="sxs-lookup"><span data-stu-id="0057c-121">The master scheduling calculation will then treat the item as a purchased item and won't perform more calculations for the item's BOM and route information.</span></span>






