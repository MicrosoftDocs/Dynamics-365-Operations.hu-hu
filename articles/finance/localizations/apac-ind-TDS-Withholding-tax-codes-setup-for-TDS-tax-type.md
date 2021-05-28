---
title: Adóelőlegkódok beállítása a TDS adótípusokhoz
description: Ez a témakör elmagyarázza, hogyan kell adókódokat beállítani a forrásnál levont adóhoz (TDS).
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
ms.openlocfilehash: d56a23f7af7633e1761a8a7c48f71381d6f14df2
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023310"
---
# <a name="set-up-withholding-tax-codes-for-the-tds-tax-type"></a><span data-ttu-id="5e04a-103">Adóelőlegkódok beállítása a TDS adótípusokhoz</span><span class="sxs-lookup"><span data-stu-id="5e04a-103">Set up withholding tax codes for the TDS tax type</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5e04a-104">Ez a témakör elmagyarázza, hogyan kell adókódokat beállítani a forrásnál levont adóhoz (TDS).</span><span class="sxs-lookup"><span data-stu-id="5e04a-104">This topic explains how to set up tax codes for Tax Deducted at Source (TDS).</span></span>

1. <span data-ttu-id="5e04a-105">Ugorjon az **Adó \> Közvetett adók \> Adóelőleg \> Adóelőlegkódok elemre**.</span><span class="sxs-lookup"><span data-stu-id="5e04a-105">Go to **Tax \> Indirect taxes \> Withholding tax \> Withholding tax codes**.</span></span>

    <span data-ttu-id="5e04a-106">[![Adóelőlegkódok oldal](./media/apac-ind-TDS-17.png)](./media/apac-ind-TDS-17.png)</span><span class="sxs-lookup"><span data-stu-id="5e04a-106">[![Withholding tax codes page](./media/apac-ind-TDS-17.png)](./media/apac-ind-TDS-17.png)</span></span>

2. <span data-ttu-id="5e04a-107">A Műveletablakban válassza az **Új** lehetőséget a TDS adóelőlegkód létrehozásához, és adja meg a szükséges adatokat.</span><span class="sxs-lookup"><span data-stu-id="5e04a-107">On the Action Pane, select **New** to create a withholding tax code for TDS, and enter the required details.</span></span>
3. <span data-ttu-id="5e04a-108">Az **Általános** gyorslapon mezőben az **Adótípusa** mezőben válassza a **TDS** lehetőséget az adókód TDS adókódként való kategorizálásához.</span><span class="sxs-lookup"><span data-stu-id="5e04a-108">On the **General** FastTab, in the **Tax type** field, select **TDS** to categorize the tax code as a TDS tax code.</span></span>
4. <span data-ttu-id="5e04a-109">Az **Elszámolási időszak** mezőben válassza ki a TDS elszámolási időszakot a TDS-adókódhoz.</span><span class="sxs-lookup"><span data-stu-id="5e04a-109">In the **Settlement period** field, select the TDS settlement period for the TDS tax code.</span></span>
5. <span data-ttu-id="5e04a-110">A **Főszámla** mezőben válassza ki azt a főkönyvi számlát, amelyre a TDS-összeget könyvelni kell.</span><span class="sxs-lookup"><span data-stu-id="5e04a-110">In the **Main account** field, select the ledger account that the TDS amount should be posted to.</span></span>
6. <span data-ttu-id="5e04a-111">A **Kintlévőség számla** mezőben válassza ki azt a kintlévőségi számlát, amelybe az értékesítési műveletekben levont TDS-összeget ki kell könyvelni.</span><span class="sxs-lookup"><span data-stu-id="5e04a-111">In the **Receivable account** field, select the receivable account that the TDS amount that is deducted in sales transactions should be posted to.</span></span>

    <span data-ttu-id="5e04a-112">Az **Eredet** mező automatikusan a **Bruttó összeg százaléka** értékre van állítva, és az érték nem módosítható.</span><span class="sxs-lookup"><span data-stu-id="5e04a-112">The **Origin** field is automatically set to **Percentage of gross amount**, and the value can't be changed.</span></span>

    > [!NOTE]
    > <span data-ttu-id="5e04a-113">Nem állíthatja be az eredetet a TDS adótípus adókódjaihoz a **Nettó összegének százaléka** értékre.</span><span class="sxs-lookup"><span data-stu-id="5e04a-113">You can't set the origin to **Percentage of net amount** for tax codes of the TDS tax type.</span></span>

7. <span data-ttu-id="5e04a-114">Az **Adóelőleg-összetevő** mezőben válassza ki a TDS-adóösszetevő lehetőséget a TDS-adókódhoz.</span><span class="sxs-lookup"><span data-stu-id="5e04a-114">In the **Withholding tax component** field, select the TDS tax component for the TDS tax code.</span></span>
8. <span data-ttu-id="5e04a-115">Válassza az **Értékek** elemet a műveleti panelen az **Adóelőleg-összegek** oldal megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="5e04a-115">On the Action Pane, select **Values** to open the **Withholding tax values** page.</span></span>
9. <span data-ttu-id="5e04a-116">A **Kezdő dátum** mezőben adja meg a TDS-összeg kezdő dátumát.</span><span class="sxs-lookup"><span data-stu-id="5e04a-116">In the **From date** field, enter the start date for the TDS value.</span></span> <span data-ttu-id="5e04a-117">Adja meg a befejező dátumot a **Befejező dátum** mezőben.</span><span class="sxs-lookup"><span data-stu-id="5e04a-117">In the **To date** field, enter the end date.</span></span>

    > [!NOTE]
    > <span data-ttu-id="5e04a-118">A TDS-adótípus adókódjaihoz nem érhetők el a **Minimális korlát**, **Felső korlát** és a **Kizárási %** mezők.</span><span class="sxs-lookup"><span data-stu-id="5e04a-118">The **Minimum limit**, **Upper limit**, and **Exclude %** fields aren't available for tax codes of the TDS tax type.</span></span>

10. <span data-ttu-id="5e04a-119">Az **Érték** mezőben adja meg a TDS adókódhoz a TDS százalékát.</span><span class="sxs-lookup"><span data-stu-id="5e04a-119">In the **Value** field, enter the percentage of TDS for the TDS tax code.</span></span>
11. <span data-ttu-id="5e04a-120">Az **Adóelőleg-értékek** lap bezárásával térjen vissza **Adóelőlegkódok** lapra.</span><span class="sxs-lookup"><span data-stu-id="5e04a-120">Close the **Withholding tax values** page to return to the **Withholding tax codes** page.</span></span>

    > [!NOTE]
    > <span data-ttu-id="5e04a-121">Az **Adóelőlegkódok** oldalon található **Korlátok** gomb nem érhető el a TDS-adótípus adókódjaihoz.</span><span class="sxs-lookup"><span data-stu-id="5e04a-121">The **Limits** button on the **Withholding tax codes** page isn't available for tax codes of the TDS tax type.</span></span>

12. <span data-ttu-id="5e04a-122">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="5e04a-122">Close the page.</span></span>
