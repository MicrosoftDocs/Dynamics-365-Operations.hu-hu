---
title: Okkódok a szervizrendelésekhez
description: Okkódok segítségével magyarázhatja meg egy szervizrendelés státusát, amikor a szervizrendelés új fokozatba kerül.
author: ShylaThompson
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAStageTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: cdade89d07fec6a01926015a8c73bacce015fd7a
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2019
ms.locfileid: "363545"
---
# <a name="reason-codes-for-service-orders"></a><span data-ttu-id="a0722-103">Okkódok a szervizrendelésekhez</span><span class="sxs-lookup"><span data-stu-id="a0722-103">Reason codes for service orders</span></span>   

[!include [banner](../includes/banner.md)]


<span data-ttu-id="a0722-104">Okkódok segítségével magyarázhatja meg egy szervizrendelés státusát, amikor a szervizrendelés új fokozatba kerül.</span><span class="sxs-lookup"><span data-stu-id="a0722-104">You can use reason codes to help explain the status of a service order when the stage of a service order is updated.</span></span> <span data-ttu-id="a0722-105">Például ha visszavon egy szervizrendelést, akkor ennek az okkódját is megadhatja.</span><span class="sxs-lookup"><span data-stu-id="a0722-105">For example, if you cancel a service order, you can select a reason code for the cancellation.</span></span>

<span data-ttu-id="a0722-106">A szervizrendelés folyamatának nyomonkövetésében használt okkódok adatainak megtekintésére a Szervizrendelés folyamata jelentés használható.</span><span class="sxs-lookup"><span data-stu-id="a0722-106">To view information about reason codes that are used to track the progress of service orders, run the Service order progress report.</span></span> <span data-ttu-id="a0722-107">Ez a jelentés fokozatuktól függetlenül listázza az összes szervizrendelést, és a szervizrendelés fokozatának módosulásakor meghatározott okkódokat.</span><span class="sxs-lookup"><span data-stu-id="a0722-107">This report lists all service orders, regardless of their stage, and the reason codes that are specified when a service order stage is updated.</span></span>

## <a name="turn-reason-codes-on-or-off"></a><span data-ttu-id="a0722-108">Az okkódok be- és kikapcsolása</span><span class="sxs-lookup"><span data-stu-id="a0722-108">Turn reason codes on or off</span></span>

<span data-ttu-id="a0722-109">Az okkódok használata nem kötelező.</span><span class="sxs-lookup"><span data-stu-id="a0722-109">Reason codes are optional.</span></span> <span data-ttu-id="a0722-110">Szabadon el lehet dönteni, hogy egy szervizfokozat kérjen-e okkódot a szervizrendelés másik fokozatra való frissítésekor.</span><span class="sxs-lookup"><span data-stu-id="a0722-110">You can decide whether to require a reason code when you update a service order to a specific service stage.</span></span>

1.  <span data-ttu-id="a0722-111">Kattintson a **Szolgáltatáskezelés** \> **Beállítás** \> **Szervizrendelések** \> **Szerviz fokozatai** elemre.</span><span class="sxs-lookup"><span data-stu-id="a0722-111">Click **Service management** \> **Setup** \> **Service orders** \> **Service stages**.</span></span>

2.  <span data-ttu-id="a0722-112">A **Szerviz fokozatai** űrlapon válasszon ki egy szervizfokozatot, majd tegyen jelet az **Ok** jelölőmezőjébe.</span><span class="sxs-lookup"><span data-stu-id="a0722-112">In the **Service stages** form, select a service stage, and then select the **Reason** check box for the service stage.</span></span>

3.  <span data-ttu-id="a0722-113">A módosítások mentéséhez zárja be a képernyőt.</span><span class="sxs-lookup"><span data-stu-id="a0722-113">Close the form to save your changes.</span></span>

## <a name="see-also"></a><span data-ttu-id="a0722-114">Lásd még</span><span class="sxs-lookup"><span data-stu-id="a0722-114">See also</span></span>

[<span data-ttu-id="a0722-115">Szervizrendelési fokozatok beállítása</span><span class="sxs-lookup"><span data-stu-id="a0722-115">Set up service order stages</span></span>](set-up-service-order-stages.md)



