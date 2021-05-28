---
title: Partraszállási költség beszerzési és forrásparaméterei
description: Ez a témakör ismerteti, hogyan lehet beállítani a releváns beszerzési és forrásparamétereit a Partraszállási költség modul használata során.
author: sherry-zheng
ms.date: 12/09/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SrmParameters
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-12-09
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: ccda3bd769a646e2390711883b8e40bec50e4d6a
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/11/2021
ms.locfileid: "6020983"
---
# <a name="procurement-and-sourcing-parameters-for-landed-cost"></a><span data-ttu-id="e8088-103">Partraszállási költség beszerzési és forrásparaméterei</span><span class="sxs-lookup"><span data-stu-id="e8088-103">Procurement and sourcing parameters for Landed cost</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="e8088-104">A **Beszerzés és forrásparaméterek** oldalon néhány olyan beállítás is van, amelyek különösen fontosak a **Partraszállási költség** modul használatakor.</span><span class="sxs-lookup"><span data-stu-id="e8088-104">The **Procurement and sourcing parameters** page has a few settings that are especially relevant when you use the **Landed cost** module.</span></span> <span data-ttu-id="e8088-105">A **Beszerzési és forrásparaméterek** oldaláról megnyitott **Rendeléssorok frissítése** párbeszédpanellel megadhatja, hogy a beszerzésirendelés-sorokat a rendszer automatikusan frissítse, amikor módosítják a beszerzési rendelés fejlécét.</span><span class="sxs-lookup"><span data-stu-id="e8088-105">Use the **Update order lines** dialog box that is opened from the **Procurement and sourcing parameters** page to specify whether purchase order lines should automatically be updated when changes are made on the purchase order header.</span></span>

<span data-ttu-id="e8088-106">Ennek a beállításnak a befejezéséhez kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="e8088-106">To complete this setup, follow these steps.</span></span>

1. <span data-ttu-id="e8088-107">Nyissa meg a **Beszerzés és forrás \> Beállítás \> Beszerzés és forrás paraméterei** pontot.</span><span class="sxs-lookup"><span data-stu-id="e8088-107">Go to **Procurement and sourcing \> Setup \> Procurement and sourcing parameters**.</span></span>
1. <span data-ttu-id="e8088-108">Az **Általános** lapon válassza a **Rendeléssorok frissítése** hivatkozást.</span><span class="sxs-lookup"><span data-stu-id="e8088-108">On the **General** tab, select the **Update order lines** link.</span></span>
1. <span data-ttu-id="e8088-109">A **Rendeléssorok frissítése** párbeszédpanel felsorolja a rendelés fejlécében található mezőket, amelyek a rendeléssorok kapcsolódó mezőire automatikus frissítéseket is alkalmazhatnak.</span><span class="sxs-lookup"><span data-stu-id="e8088-109">The **Update order lines** dialog box lists the fields on the order header that can also apply automatic updates to related fields on the order lines.</span></span> <span data-ttu-id="e8088-110">A lista minden mezőjét a következő értékek egyikére állíthatja:</span><span class="sxs-lookup"><span data-stu-id="e8088-110">Set each field in the list to one of the following values:</span></span>

    - <span data-ttu-id="e8088-111">**Mindig** – A rendelésfejléc frissítése esetén a rendeléssoroknak automatikusan frissülniük kell.</span><span class="sxs-lookup"><span data-stu-id="e8088-111">**Always** – The order lines should automatically be updated when the order header is updated.</span></span>
    - <span data-ttu-id="e8088-112">**Soha** – A rendelésfejléc frissítése esetén a rendeléssoroknak sosem szabad frissülniük.</span><span class="sxs-lookup"><span data-stu-id="e8088-112">**Never** – The order lines should never be updated when the order header is updated.</span></span>
    - <span data-ttu-id="e8088-113">**Rákérdezés** – A program megkéri a felhasználót, hogy döntse el, hogy kell-e frissíteni a rendelési sorokat.</span><span class="sxs-lookup"><span data-stu-id="e8088-113">**Prompt** – The user will be prompted to select whether the order lines should be updated.</span></span>
