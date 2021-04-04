---
title: Karbantartáskérési jelentések
description: Ez a témakör azt mutatja be, hogyan lehet a karbantartási kérésekkel kapcsolatos jelentéseket létrehozni az Eszközkezelés modulban.
author: josaw1
manager: tfehr
ms.date: 10/31/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 9e10327ad65b712cf7713eb3e25713ac5dae950e
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5253302"
---
# <a name="maintenance-request-reports"></a><span data-ttu-id="04577-103">Karbantartáskérési jelentések</span><span class="sxs-lookup"><span data-stu-id="04577-103">Maintenance request reports</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="04577-104">Az Eszközkezelés modulban két olyan jelentést lehet létrehozni, amelyek a karbantartási kérésekhez kapcsolódnak.</span><span class="sxs-lookup"><span data-stu-id="04577-104">In Asset Management, you can generate two reports that are related to maintenance requests.</span></span> <span data-ttu-id="04577-105">Egy jelentés a részleteket tartalmazza, a másik jelentés pedig egy listát, amely a tervezéshez és a nyomon követéshez használható.</span><span class="sxs-lookup"><span data-stu-id="04577-105">One report shows details, and the other report provides a list that can be used for planning and follow-up.</span></span>

## <a name="create-a-maintenance-request-details-report"></a><span data-ttu-id="04577-106">Karbantartási kérés részletes jelentésének létrehozása</span><span class="sxs-lookup"><span data-stu-id="04577-106">Create a Maintenance request details report</span></span>

<span data-ttu-id="04577-107">A **Karbantartási kérés részletei** jelentés a karbantartási kérésekkel kapcsolatos különféle információkat tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="04577-107">The **Maintenance request details** report shows various information that is related to maintenance requests.</span></span>

1. <span data-ttu-id="04577-108">Válassza az **Eszközkezelés** \> **Jelentések** \> **Karbantartási kérések** \> **Karbantartási kérés részletei** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="04577-108">Select **Asset management** \> **Reports** \> **Maintenance requests** \> **Maintenance request details**.</span></span>
2. <span data-ttu-id="04577-109">A **Szerepeltetni kívánt rekordok** gyorslapján kiválaszthatja a jelentésbe foglalandó konkrét karbantartási kéréseket.</span><span class="sxs-lookup"><span data-stu-id="04577-109">On the **Records to include** FastTab, you can select specific maintenance requests to include on the report.</span></span>
3. <span data-ttu-id="04577-110">A **Futtatás a háttérben** gyorslapon szükség szerint kötegelt feladatként is beállíthatja a jelentéskészítést.</span><span class="sxs-lookup"><span data-stu-id="04577-110">On the **Run in the background** FastTab, you can set up report generation as a batch job, as you require.</span></span>
4. <span data-ttu-id="04577-111">A jelentés előállításához válassza az **OK** gombot.</span><span class="sxs-lookup"><span data-stu-id="04577-111">Select **OK** to generate the report.</span></span>

<span data-ttu-id="04577-112">A következő ábra egy példát mutat be a **Karbantartási kérés részletei** jelentésre.</span><span class="sxs-lookup"><span data-stu-id="04577-112">The following illustration shows an example of the **Maintenance request details** report.</span></span>

![Karbantartási kérés részletei jelentés](media/09-manage-maintenance-requests.png)

## <a name="create-a-maintenance-request-list-report"></a><span data-ttu-id="04577-114">Karbantartási kérés listája jelentés létrehozása</span><span class="sxs-lookup"><span data-stu-id="04577-114">Create a Maintenance request list report</span></span>

<span data-ttu-id="04577-115">A **Karbantartási kérések listája** jelentés megjeleníti az azonos kéréstípusú karbantartási kérések listáját.</span><span class="sxs-lookup"><span data-stu-id="04577-115">The **Maintenance request list** report shows a list of all maintenance requests of the same request type.</span></span>

1. <span data-ttu-id="04577-116">Válassza az **Eszközkezelés** \> **Jelentések** \> **Karbantartási kérések** \> **Karbantartási kérések listája** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="04577-116">Select **Asset management** \> **Reports** \> **Maintenance requests** \> **Maintenance request list**.</span></span>
2. <span data-ttu-id="04577-117">A **Szerepeltetni kívánt rekordok** gyorslapján való kiválasztással meghatározhatja a jelentésbe foglalandó konkrét karbantartási kéréseket.</span><span class="sxs-lookup"><span data-stu-id="04577-117">On the **Records to include** FastTab, you can make selections to define which maintenance requests are included on the report.</span></span>
3. <span data-ttu-id="04577-118">A **Futtatás a háttérben** gyorslapon szükség szerint kötegelt feladatként is beállíthatja a jelentéskészítést.</span><span class="sxs-lookup"><span data-stu-id="04577-118">On the **Run in the background** FastTab, you can set up report generation as a batch job, as you require.</span></span>
4. <span data-ttu-id="04577-119">A jelentés előállításához válassza az **OK** gombot.</span><span class="sxs-lookup"><span data-stu-id="04577-119">Select **OK** to generate the report.</span></span>

<span data-ttu-id="04577-120">A következő ábra egy példát mutat be a **Karbantartási kérések listája** jelentésre az összes aktív karbantartási kérés esetében.</span><span class="sxs-lookup"><span data-stu-id="04577-120">The following illustration shows an example of the **Maintenance request list** report for all active maintenance requests.</span></span>

![Karbantartási kérés lista jelentései](media/10-manage-maintenance-requests.png)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]