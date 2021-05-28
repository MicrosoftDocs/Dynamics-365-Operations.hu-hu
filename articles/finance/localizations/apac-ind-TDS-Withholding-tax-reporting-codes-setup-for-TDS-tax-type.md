---
title: Adóelőleg jelentéskódok beállítása a TDS adótípusokhoz
description: Az adóelőleg jelentés kódok a Forrásnál levont adóról (TDS) szóló 26Q és 27Q űrlapkimutatások előállítására szolgálnak. Ez a témakör elmagyarázza, hogyan állíthatja be az adóelőleg jelentéskódokat, hogy beállíthassa a TDS-jelentéskódokat.
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: 1f9325d182f89b98e8b943ae047c55e7e1aeb02f
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023308"
---
# <a name="set-up-withholding-tax-reporting-codes-for-the-tds-tax-type"></a><span data-ttu-id="433d6-104">Adóelőleg jelentéskódok beállítása a TDS adótípusokhoz</span><span class="sxs-lookup"><span data-stu-id="433d6-104">Set up withholding tax reporting codes for the TDS tax type</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="433d6-105">Az adóelőleg jelentés kódok a Forrásnál levont adóról (TDS) szóló 26Q és 27Q űrlapkimutatások előállítására szolgálnak.</span><span class="sxs-lookup"><span data-stu-id="433d6-105">Withholding tax reporting codes are used to generate Form 26Q and Form 27Q statements for Tax Deducted at Source (TDS).</span></span> <span data-ttu-id="433d6-106">Ez a témakör elmagyarázza, hogyan állíthatja be az adóelőleg jelentéskódokat, hogy beállíthassa a TDS-jelentéskódokat.</span><span class="sxs-lookup"><span data-stu-id="433d6-106">This topic explains how to set up withholding tax reporting codes steps so that you can set up TDS reporting codes.</span></span>

1. <span data-ttu-id="433d6-107">Ugorjon az **Adó \> Beállítások \> Adóelőleg \> Adóelőleg jelentéskódok elemre**.</span><span class="sxs-lookup"><span data-stu-id="433d6-107">Go to **Tax \> Setup \> Withholding tax \> Withholding tax reporting codes**.</span></span>

    <span data-ttu-id="433d6-108">[![Adóelőleg jelentéskódok oldal](./media/apac-ind-TDS-16.png)](./media/apac-ind-TDS-16.png)</span><span class="sxs-lookup"><span data-stu-id="433d6-108">[![Withholding tax reporting codes page](./media/apac-ind-TDS-16.png)](./media/apac-ind-TDS-16.png)</span></span>

2. <span data-ttu-id="433d6-109">Az **Adótípus** mezőben válassza ki a **TDS** lehetőséget a TDS adótípus adóelőleg jelentéskódok definiálásához.</span><span class="sxs-lookup"><span data-stu-id="433d6-109">In the **Tax type** field, select **TDS** to define withholding tax reporting codes for the TDS tax type.</span></span>
3. <span data-ttu-id="433d6-110">Az **Adóelőleg-összetevő** mezőben válassza ki azt a TDS-összetevőt, amelyhez az adóelőleg jelentéskódot definiálja.</span><span class="sxs-lookup"><span data-stu-id="433d6-110">In the **Withholding tax component** field, select the TDS component to that you're defining the withholding tax reporting code for.</span></span> <span data-ttu-id="433d6-111">Az **Adóelőleg-összetevő csoport** mezője a definiált TDS-összetevőre definiált TDS-összetevőcsoportot mutatja.</span><span class="sxs-lookup"><span data-stu-id="433d6-111">The **Withholding tax component group** field shows the TDS component group that was defined for the TDS component that you're defining.</span></span>

    <span data-ttu-id="433d6-112">Az **Általános** gyorslap **Szakaszkód** mezője a TDS-összetevőcsoporthoz csatolt szakaszkódot mutatja.</span><span class="sxs-lookup"><span data-stu-id="433d6-112">The **Section code** field on the **General** FastTab shows the section code that is attached to the TDS component group.</span></span>

4. <span data-ttu-id="433d6-113">Az **Általános** gyorslap **Jelentéskód** mezőjében válasszon ki egy TDS jelentési kódot:</span><span class="sxs-lookup"><span data-stu-id="433d6-113">On the **General** FastTab, in the **Reporting code** field, select the TDS reporting code:</span></span>

    - <span data-ttu-id="433d6-114">TDS</span><span class="sxs-lookup"><span data-stu-id="433d6-114">TDS</span></span>
    - <span data-ttu-id="433d6-115">TCS</span><span class="sxs-lookup"><span data-stu-id="433d6-115">TCS</span></span>
    - <span data-ttu-id="433d6-116">Pótdíj</span><span class="sxs-lookup"><span data-stu-id="433d6-116">Surcharge</span></span>
    - <span data-ttu-id="433d6-117">PE\_Cess</span><span class="sxs-lookup"><span data-stu-id="433d6-117">PE\_Cess</span></span>
    - <span data-ttu-id="433d6-118">SHE\_Cess</span><span class="sxs-lookup"><span data-stu-id="433d6-118">SHE\_Cess</span></span>

5. <span data-ttu-id="433d6-119">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="433d6-119">Close the page.</span></span>
