---
title: Mezők hozzáadása Excel-munkafüzethez a kiskereskedelmi tranzakciók szerkesztéséhez
description: Ez a témakör azt ismerteti, hogy miként adhat mezőket a Microsoft Excel-munkafüzethez a kiskereskedelmi tranzakciók szerkesztéséhez a Microsoft Dynamics 365 Commerce szolgáltatásban.
author: josaw1
manager: AnnBe
ms.date: 11/04/2020
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-365-retail
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
ms.openlocfilehash: fb0435a617585689a87caa76f80e9774182576cc
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5206319"
---
# <a name="add-fields-to-an-excel-workbook-to-edit-retail-transactions"></a><span data-ttu-id="b5a15-103">Mezők hozzáadása Excel-munkafüzethez a kiskereskedelmi tranzakciók szerkesztéséhez</span><span class="sxs-lookup"><span data-stu-id="b5a15-103">Add fields to an Excel workbook to edit retail transactions</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b5a15-104">Ez a témakör azt ismerteti, hogy miként adhat mezőket a Microsoft Excel-munkafüzethez a kiskereskedelmi tranzakciók szerkesztéséhez a Microsoft Dynamics 365 Commerce szolgáltatásban.</span><span class="sxs-lookup"><span data-stu-id="b5a15-104">This topic describes how to add fields to a Microsoft Excel workbook so that you can edit retail transactions in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="b5a15-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="b5a15-105">Overview</span></span>

<span data-ttu-id="b5a15-106">Ha a kiskereskedelmi tranzakciók szerkesztéséhez Excel-fájlt hoz létre, a fájl néhány alapértelmezett mezővel lesz kitöltve.</span><span class="sxs-lookup"><span data-stu-id="b5a15-106">When you generate an Excel file so that you can edit retail transactions, the file is filled with some default fields.</span></span> <span data-ttu-id="b5a15-107">Ha egy frissítendő mező alapértelmezés szerint nem látható a létrehozott Excel-fájlban, hozzáadhatja.</span><span class="sxs-lookup"><span data-stu-id="b5a15-107">If a field that must be updated isn't visible by default in the generated Excel file, you can add it.</span></span>

## <a name="add-fields-to-a-worksheet-in-an-excel-workbook"></a><span data-ttu-id="b5a15-108">Mezők hozzáadása munkalaphoz Excel-munkafüzetben</span><span class="sxs-lookup"><span data-stu-id="b5a15-108">Add fields to a worksheet in an Excel workbook</span></span>

<span data-ttu-id="b5a15-109">Ha mezőket szeretne hozzáadni egy Excel-munkafüzethez, hogy szerkeszthesse a kiskereskedelmi tranzakciókat, kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="b5a15-109">To add fields to an Excel workbook so that you can edit retail transactions, follow these steps.</span></span>

1. <span data-ttu-id="b5a15-110">Töltse le és nyissa meg az Excel-fájlt a **Kimutatások** lapról, a **Kiskereskedelmi tranzakciók** lapról vagy a **Tranzakció-ellenőrzési hibák** csempéről az **Üzlet pénzügyi adatai** munkaterületen.</span><span class="sxs-lookup"><span data-stu-id="b5a15-110">Download and open the Excel file from the **Statements** page, the **Retail transactions** page, or the **Transaction validation failures** tile in the **Store financials** workspace.</span></span>
1. <span data-ttu-id="b5a15-111">Válassza ki a **Tervezés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b5a15-111">Select **Design**.</span></span>
1. <span data-ttu-id="b5a15-112">Jelölje ki a kívánt tábla ceruzaszimbólumát, majd az elérhető mezők listájában keresse meg és jelölje ki a hozzáadni kívánt mezőt.</span><span class="sxs-lookup"><span data-stu-id="b5a15-112">Select the pencil symbol for the desired table, and then, in the list of available fields, find and select the field that you want to add.</span></span>
1. <span data-ttu-id="b5a15-113">Válassza ki a **Hozzáadás**, majd a **Frissítés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b5a15-113">Select **Add**, and then select **Update**.</span></span> <span data-ttu-id="b5a15-114">A mezőket átrendezheti.</span><span class="sxs-lookup"><span data-stu-id="b5a15-114">You can reorder fields.</span></span>
1. <span data-ttu-id="b5a15-115">A frissítés befejezése után válassza a **Frissítés** lehetőséget az új oszlop adatainak beolvasásához.</span><span class="sxs-lookup"><span data-stu-id="b5a15-115">After the update is completed, select **Refresh** to fetch the data for the new column.</span></span>

<span data-ttu-id="b5a15-116">Az új mezőnek és az adatoknak most már szerkeszthetőknek kell lenniük az Excelben.</span><span class="sxs-lookup"><span data-stu-id="b5a15-116">The new field and data for it should now be available for editing in Excel.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b5a15-117">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="b5a15-117">Additional resources</span></span>

[<span data-ttu-id="b5a15-118">Készpénzzel fizetett, azonnal átvett és készpénzkezelési tranzakciók szerkesztése és auditálása</span><span class="sxs-lookup"><span data-stu-id="b5a15-118">Edit and audit cash and carry and cash management transactions</span></span>](edit-cash-trans.md)

[<span data-ttu-id="b5a15-119">Online rendeléses és aszinkron vevői rendeléses tranzakciók szerkesztése és auditálása</span><span class="sxs-lookup"><span data-stu-id="b5a15-119">Edit and audit online order and asynchronous customer order transactions</span></span>](edit-order-trans.md)

[<span data-ttu-id="b5a15-120">Kiskereskedelmi tranzakciók pénzügyi dimenzióinak szerkesztése</span><span class="sxs-lookup"><span data-stu-id="b5a15-120">Edit financial dimensions for retail transactions</span></span>](edit-financial-dim.md)

[<span data-ttu-id="b5a15-121">Excel-munkafüzet létrehozása a kiskereskedelmi tranzakciók szerkesztéséhez</span><span class="sxs-lookup"><span data-stu-id="b5a15-121">Create an Excel workbook to edit retail transactions</span></span>](create-excel-edit.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]