---
title: Eszközök és eszköztípusok garanciái
description: Ez a témakör azt mutatja be, hogyan lehet eszközökre és eszköztípusokra garanciákat beállítani az Eszközkezelés modulban.
author: johanhoffmann
ms.date: 08/30/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: f05f5af76aeb037d606d38a368a49d011f0d2bd6
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5825566"
---
# <a name="warranties-on-assets-and-asset-types"></a><span data-ttu-id="2ff2d-103">Eszközök és eszköztípusok garanciái</span><span class="sxs-lookup"><span data-stu-id="2ff2d-103">Warranties on assets and asset types</span></span>

[!include [banner](../../includes/banner.md)]

 


<span data-ttu-id="2ff2d-104">Ez a témakör azt mutatja be, hogyan lehet eszközökre és eszköztípusokra garanciákat beállítani az Eszközkezelés modulban.</span><span class="sxs-lookup"><span data-stu-id="2ff2d-104">This topic explains how to set up warranties on assets and asset types in Asset Management.</span></span>

## <a name="set-up-a-warranty-on-an-asset-type"></a><span data-ttu-id="2ff2d-105">Garancia beállítása egy eszköztípusra</span><span class="sxs-lookup"><span data-stu-id="2ff2d-105">Set up a warranty on an asset type</span></span>

1. <span data-ttu-id="2ff2d-106">Válassza ki az **Eszközkezelés** \> **Beállítás** \> **Eszköztípusok** \> **Eszköztípusok** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="2ff2d-106">Select **Asset management** \> **Setup** \> **Asset types** \> **Asset types**.</span></span>
2. <span data-ttu-id="2ff2d-107">A bal oldali ablaktáblában válassza ki azt a eszköztípust, amelyhez szállítói garanciamegállapodást kíván csatolni, majdválassza ki az **Eszköztípus alapértelmezései** elemet.</span><span class="sxs-lookup"><span data-stu-id="2ff2d-107">In the left pane, select the asset type to attach a vendor warranty agreement to, and then select **Asset type defaults**.</span></span>
3. <span data-ttu-id="2ff2d-108">Az **Általános** gyorslapon a **Szállítói garancia** mezőben válassza ki a szerződést.</span><span class="sxs-lookup"><span data-stu-id="2ff2d-108">On the **General** FastTab, in the **Vendor warranty** field, select the agreement.</span></span>

## <a name="set-up-a-warranty-on-an-asset"></a><span data-ttu-id="2ff2d-109">Garancia beállítása egy eszközre</span><span class="sxs-lookup"><span data-stu-id="2ff2d-109">Set up a warranty on an asset</span></span>

1. <span data-ttu-id="2ff2d-110">Válassza ki az **Eszközkezelés** \> **Általános** \> **Eszközök** \> **Összes eszköz** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="2ff2d-110">Select **Asset management** \> **Common** \> **Assets** \> **All assets**.</span></span>
2. <span data-ttu-id="2ff2d-111">Jelöljön ki egy eszközt, és kattintson a **Szerkesztés** gombra.</span><span class="sxs-lookup"><span data-stu-id="2ff2d-111">Select the asset, and then select **Edit**.</span></span>
3. <span data-ttu-id="2ff2d-112">A **Szállító** gyorslap **Szállítói garancia** szakaszának **Garancia** mezőjében válassza ki a garanciaszerződést.</span><span class="sxs-lookup"><span data-stu-id="2ff2d-112">On the **Vendor** FastTab, in the **Vendor warranty** section, in the **Warranty** field, select the warranty agreement.</span></span>
4. <span data-ttu-id="2ff2d-113">Válassza ki a kezdési és befejezési dátumokat a **Garancia kezdete** és **Garancia vége** mezőkben.</span><span class="sxs-lookup"><span data-stu-id="2ff2d-113">In the **Warranty start** and **Warranty end** fields, select the start and end dates.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="2ff2d-114">Ha egy munkarendelésen kiválasztottak egy dátumot a **Garancia kezdete** mezőben, akkor a munkarendelésre vonatkozó garancia az adott dátumon érvénybe lép.</span><span class="sxs-lookup"><span data-stu-id="2ff2d-114">If a date is selected in the **Warranty start** field on a work order, the warranty becomes valid for the work order on that date.</span></span> <span data-ttu-id="2ff2d-115">A munkarendelések létrehozásakor a rendszer a **Garancia kezdete** mezőt automatikusan a létrehozás dátumára állítja.</span><span class="sxs-lookup"><span data-stu-id="2ff2d-115">When you create a work order, the **Warranty start** field is automatically set to the date of creation.</span></span> <span data-ttu-id="2ff2d-116">A dátum azonban módosítható úgy, hogy a megfelel például a garanciaszerződés kezdő dátumának.</span><span class="sxs-lookup"><span data-stu-id="2ff2d-116">However, you can change the date so that it corresponds to, for example, the start date of a warranty agreement.</span></span>
    >
    > ![Munkarendelés lap](media/02-warranty.png)

> [!NOTE]
> <span data-ttu-id="2ff2d-118">Amikor egy szállítói garancia által fedezett eszközhöz hoz létre munkarendelést, ha a munkarendelés elvárt kezdési dátummal rendelkezik a garanciaidőszak folyamán, akkor értesítést kap a garanciaszerződésről.</span><span class="sxs-lookup"><span data-stu-id="2ff2d-118">When you create a work order for an asset that is covered by a vendor warranty, if the work order has an expected start date during the warranty period, you receive a notification about the warranty agreement.</span></span> <span data-ttu-id="2ff2d-119">Ezután szükség esetén a munkarendelést érvényteleníteni lehet.</span><span class="sxs-lookup"><span data-stu-id="2ff2d-119">You can then cancel the work order, as you require.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]