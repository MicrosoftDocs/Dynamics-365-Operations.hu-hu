---
title: Vevői számlák és visszárukra vonatkozó értékesítési rendelések a kelet-európai országokban
description: Ez a témakör leírja, hogyan adja meg az adatokat a vevői számlákhoz és az értékesítési visszárurendelésekhez a közép-kelet-európai országok számára.
author: epopov
ms.date: 10/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: josaw
ms.search.region: Czech Republic, Estonia, Hungary, Latvia, Lithuania, Poland, Russia
ms.search.industry: Retail
ms.author: epopov
ms.search.validFrom: 2018-10-31
ms.dyn365.ops.version: 8.0999999999999996
ms.openlocfilehash: f79208b2508ed3879aa626389564b10a1d78c165
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5798825"
---
# <a name="customer-invoices-and-return-sales-orders-in-eastern-european-countries"></a><span data-ttu-id="e29d2-103">Vevői számlák és visszárukra vonatkozó értékesítési rendelések a kelet-európai országokban</span><span class="sxs-lookup"><span data-stu-id="e29d2-103">Customer invoices and return sales orders in Eastern European countries</span></span>


[!include [banner](../../includes/banner.md)]

<span data-ttu-id="e29d2-104">Ez a témakör leírja, hogyan adja meg az adatokat a vevői számlákhoz és az értékesítési visszárurendelésekhez a közép-kelet-európai országok számára.</span><span class="sxs-lookup"><span data-stu-id="e29d2-104">This topic describes how to set up information for customer invoices and return sales orders in Eastern European countries.</span></span>

<span data-ttu-id="e29d2-105">Az alábbi információkat állíthatja be a Retail POS rendszerben generált vevői számlákhoz és a visszáru típusú értékesítési rendelésekhez:</span><span class="sxs-lookup"><span data-stu-id="e29d2-105">You can set up the following information for customer invoices and return sales orders that are generated in Retail point of sale (POS).</span></span>

- <span data-ttu-id="e29d2-106">Áfacsoportok használhatók a visszaküldések értékesítési visszárurendelésekkel való feldolgozásában.</span><span class="sxs-lookup"><span data-stu-id="e29d2-106">You can use sales tax groups to process returns by using return sales orders.</span></span> <span data-ttu-id="e29d2-107">Menjen a **Kiskereskedelem és kereskedelem \> Központ beállítása \> Paraméterek \> Kiskereskedelmi paraméterek** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="e29d2-107">Go to **Retail and Commerce \> Headquarters setup \> Parameters \> Commerce parameters**.</span></span> <span data-ttu-id="e29d2-108">Nyissa meg a **Feladás \> Számla** lapot, és ezután állítsa a **Visszáruk áfacsoportjának használata** lehetőséget **Igen** beállításra.</span><span class="sxs-lookup"><span data-stu-id="e29d2-108">Open the **Posting \> Invoice** tab, and then set **Use sales tax group for returns** to **Yes**.</span></span>

    * <span data-ttu-id="e29d2-109">A vevői által a kiskereskedelmi értékesítési helyen visszaadott visszáruhoz tartozó áfacsoport megadásához az **Ügyfelek** lap **Kereskedelem** gyorslapján a **Visszáruk áfacsoportja** mezőben, válasszon ki egy áfacsoportot.</span><span class="sxs-lookup"><span data-stu-id="e29d2-109">To specify the sales tax group for returns that are made by a customer, on the **Customers** page, on the **Commerce** FastTab, in the **Sales tax group for returns** field, select a sales tax group.</span></span> <span data-ttu-id="e29d2-110">Egy vevői visszárurendelés feladásakor a visszárurendelés sorában frissül a visszáruhoz az **Ügyfelek** képernyőn megadott áfacsoport.</span><span class="sxs-lookup"><span data-stu-id="e29d2-110">When you post a return sales order for a customer, the return sales order line is updated with the sales tax group for returns that is specified in the **Customers** form.</span></span>
    * <span data-ttu-id="e29d2-111">A vevői által a Retail POS helyen visszaadott visszáruhoz tartozó áfacsoport megadásához az **Üzletek** lap **Általános** gyorslapján a **Visszáruk áfacsoportja** mezőben, válasszon ki egy áfacsoportot.</span><span class="sxs-lookup"><span data-stu-id="e29d2-111">To specify a sales tax group for returns that are made at a retail POS by a customer, on the **Stores** page, on the **General** FastTab, in the **Sales tax group for returns** field, select a sales tax group.</span></span> <span data-ttu-id="e29d2-112">Egy bolt vevői visszárurendelésének feladásakor a visszárurendelés sorában frissül a visszáruhoz az **Üzletek** lapon megadott áfacsoport.</span><span class="sxs-lookup"><span data-stu-id="e29d2-112">When you post a return sales order for a customer of a  store, the return sales order line is updated with the sales tax group for returns that are specified on the **Stores** page.</span></span>

- <span data-ttu-id="e29d2-113">Ha egy vevői számlának vagy visszáru típusú értékesítési rendelésnek nincs alapértelmezett értékesítési dátuma, akkor a számla vagy a visszáru feladási dátumát használhatja értékesítési dátumként.</span><span class="sxs-lookup"><span data-stu-id="e29d2-113">You can use the posting date of a customer invoice or a return sales order as the sales date of the invoice or return if the invoice or return does not have a default sales date.</span></span> <span data-ttu-id="e29d2-114">Menjen a **Kiskereskedelem és kereskedelem \> Központ beállítása \> Paraméterek \> Kiskereskedelmi paraméterek** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="e29d2-114">Go to **Retail and Commerce \> Headquarters setup \> Parameters \> Commerce parameters**.</span></span> <span data-ttu-id="e29d2-115">Nyissa meg a **Feladás \> Számla** lapot, és ezután állítsa **A feladási dátum használata értékesítési dátumként lehetőséget** **Igen** beállításra.</span><span class="sxs-lookup"><span data-stu-id="e29d2-115">Open the **Posting \> Invoice** tab, and then set **Use posting date as sales date** to **Yes**.</span></span>
- <span data-ttu-id="e29d2-116">Lett és litván vevői számlák és visszáru típusú értékesítési rendelések számozásához az adóhatóságtól kapott számtartományt használhatja.</span><span class="sxs-lookup"><span data-stu-id="e29d2-116">You can use the number range that is provided by the tax authorities to number Latvian and Lithuanian customer invoices and return sales orders.</span></span>

    * <span data-ttu-id="e29d2-117">Ugrás a **Szervezeti adminisztráció \> Számsorozatok \> Számlálókezelés elemre**.</span><span class="sxs-lookup"><span data-stu-id="e29d2-117">Go to **Organization administration \> Number sequences \> Counters management**.</span></span> <span data-ttu-id="e29d2-118">Rekordnak kell lennie ahol **Modul** = **Értékesítés** és **Típus** = **Számla**.</span><span class="sxs-lookup"><span data-stu-id="e29d2-118">There should be a record where **Module** = **Sales** and **Type** = **Invoice**.</span></span>
    * <span data-ttu-id="e29d2-119">Ugrás a **Szervezeti adminisztráció \> Számsorozatok \> Számlaszámozás beállítása elemre**.</span><span class="sxs-lookup"><span data-stu-id="e29d2-119">Go to **Organization administration \> Number sequences \> Invoice numbering setup**.</span></span> <span data-ttu-id="e29d2-120">Jelölje be a **Kereskedelem** jelölőmezőt annál a számsorozatnál, amellyel a vevői számlákat számozza.</span><span class="sxs-lookup"><span data-stu-id="e29d2-120">Select the **Commerce** check box for the number sequence line that is used to number the customer invoices.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]