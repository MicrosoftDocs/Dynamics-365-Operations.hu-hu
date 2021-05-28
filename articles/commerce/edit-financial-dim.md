---
title: Kiskereskedelmi tranzakciók pénzügyi dimenzióinak szerkesztése
description: Ez a témakör azt ismerteti, hogyan szerkeszti a Microsoft kiskereskedelmi tranzakcióinak pénzügyi dimenzióit a Microsoft Dynamics 365 Commerce szolgáltatásban.
author: josaw1
ms.date: 11/04/2020
ms.topic: index-page
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2018-11-15
ms.dyn365.ops.version: ''
ms.openlocfilehash: 381d8bb0939f6c4c163477990e49382201487375
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/11/2021
ms.locfileid: "6019907"
---
# <a name="edit-financial-dimensions-for-retail-transactions"></a><span data-ttu-id="bef56-103">Kiskereskedelmi tranzakciók pénzügyi dimenzióinak szerkesztése</span><span class="sxs-lookup"><span data-stu-id="bef56-103">Edit financial dimensions for retail transactions</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="bef56-104">Ez a témakör azt ismerteti, hogyan szerkeszti a Microsoft kiskereskedelmi tranzakcióinak pénzügyi dimenzióit a Microsoft Dynamics 365 Commerce szolgáltatásban.</span><span class="sxs-lookup"><span data-stu-id="bef56-104">This topic describes how to edit financial dimensions for retail transactions in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="edit-financial-dimensions"></a><span data-ttu-id="bef56-105">Pénzügyi dimenziók szerkesztése</span><span class="sxs-lookup"><span data-stu-id="bef56-105">Edit financial dimensions</span></span>

<span data-ttu-id="bef56-106">A kiskereskedelmi tranzakcióik pénzügyi dimenzióinak szerkesztéséhez a Commerce központi felületén kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="bef56-106">To edit financial dimensions for retail transactions in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="bef56-107">Nyissa meg a **Pénzügyi dimenziók konfigurációja alkalmazások integrálásához** oldalt.</span><span class="sxs-lookup"><span data-stu-id="bef56-107">Open the **Financial dimensions configuration for integrating applications** page.</span></span>
1. <span data-ttu-id="bef56-108">Válassza ki az aktív **Alapértelmezett dimenzióintegráció** rekordot.</span><span class="sxs-lookup"><span data-stu-id="bef56-108">Select the active **Default dimensions integration** record.</span></span>
1. <span data-ttu-id="bef56-109">A **Pénzügyi dimenziók** gyorslapon győződjön meg arról, hogy az Excel-munkalapon szerkeszteni kívánt összes dimenzió megtalálható a **Kijelölt** listában.</span><span class="sxs-lookup"><span data-stu-id="bef56-109">On the **Financial dimensions** FastTab, make sure that all the dimensions that you want to edit in the Excel worksheet are present in the **Selected** list.</span></span> <span data-ttu-id="bef56-110">További tudnivalókért lásd: [Adatentitások](../fin-ops-core/dev-itpro/financial/financial-dimension-configuration-integration.md#data-entities).</span><span class="sxs-lookup"><span data-stu-id="bef56-110">For more information, see [Data entities](../fin-ops-core/dev-itpro/financial/financial-dimension-configuration-integration.md#data-entities).</span></span>
1. <span data-ttu-id="bef56-111">Töltse le és nyissa meg az Excel-fájlt a **Kimutatások** lapról, a **Kiskereskedelmi tranzakciók** lapról vagy a **Tranzakció-ellenőrzési hibák** csempéről az **Üzlet pénzügyi adatai** munkaterületen.</span><span class="sxs-lookup"><span data-stu-id="bef56-111">Download and open the Excel file from the **Statements** page, the **Retail transactions** page, or the **Transaction validation failures** tile in the **Store financials** workspace.</span></span>
1. <span data-ttu-id="bef56-112">A tranzakció pénzügyi dimenziójának módosításához válassza a **Tervezés** lehetőséget, majd a **Tranzakció (auditálható)** sor melletti ceruza szimbólumot.</span><span class="sxs-lookup"><span data-stu-id="bef56-112">To change the transaction financial dimension, select **Design**, and then select the pencil symbol next to the **Transaction (auditable)** row.</span></span>
1. <span data-ttu-id="bef56-113">Keresse meg, és jelölje ki a **FinancialDimensionDisplayValue** mezőt, jelöljön ki egy cellát az Excel-munkalap fejlécrészében, majd válassza a **Címke hozzáadása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="bef56-113">Find and select the **FinancialDimensionDisplayValue** field, select a cell in the header part of the Excel worksheet, and then select **Add label**.</span></span>
1. <span data-ttu-id="bef56-114">Jelöljön ki egy cellát az előző lépésben kijelölt cella alatt, válassza az **Érték hozzáadása**, majd a **Frissítés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="bef56-114">Select a cell below the cell that you selected in the previous step, select **Add Value**, and then select **Refresh**.</span></span> <span data-ttu-id="bef56-115">A rendszer hozzáadja a pénzügyi dimenziókat az Excel munkalaphoz, amelyek ezután szerkeszthetők és közzétehetők.</span><span class="sxs-lookup"><span data-stu-id="bef56-115">The financial dimensions are added to the Excel worksheet, and they can then be edited and published.</span></span>
1. <span data-ttu-id="bef56-116">A tranzakciósorok dimenzióinak módosításához jelölje ki az **Értékesítési tranzakciók (auditálható)** sort, jelölje ki a ceruza szimbólumot, majd ismételje meg a 6. és 7. lépést.</span><span class="sxs-lookup"><span data-stu-id="bef56-116">To change the dimensions on the transaction lines, select the **Sales transactions (auditable)** row, select the pencil symbol, and then repeat steps 6 and 7.</span></span>
1. <span data-ttu-id="bef56-117">A fizetési sorok dimenzióinak módosításához jelölje ki a **Fizetési tranzakciók (auditálható)** sort, jelölje ki a ceruza szimbólumot, majd ismételje meg a 6. és 7. lépést.</span><span class="sxs-lookup"><span data-stu-id="bef56-117">To change the dimensions on the payment lines, select the **Payment transactions (auditable)** row, select the pencil symbol, and then repeat steps 6 and 7.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="bef56-118">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="bef56-118">Additional resources</span></span>

[<span data-ttu-id="bef56-119">Készpénzzel fizetett, azonnal átvett és készpénzkezelési tranzakciók szerkesztése és auditálása</span><span class="sxs-lookup"><span data-stu-id="bef56-119">Edit and audit cash and carry and cash management transactions</span></span>](edit-cash-trans.md)

[<span data-ttu-id="bef56-120">Online rendeléses és aszinkron vevői rendeléses tranzakciók szerkesztése és auditálása</span><span class="sxs-lookup"><span data-stu-id="bef56-120">Edit and audit online order and asynchronous customer order transactions</span></span>](edit-order-trans.md)

[<span data-ttu-id="bef56-121">Excel-munkafüzet létrehozása a kiskereskedelmi tranzakciók szerkesztéséhez</span><span class="sxs-lookup"><span data-stu-id="bef56-121">Create an Excel workbook to edit retail transactions</span></span>](create-excel-edit.md)

[<span data-ttu-id="bef56-122">Mezők hozzáadása Excel-munkafüzethez a kiskereskedelmi tranzakciók szerkesztéséhez</span><span class="sxs-lookup"><span data-stu-id="bef56-122">Add fields to an Excel workbook to edit retail transactions</span></span>](add-fields-excel.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]