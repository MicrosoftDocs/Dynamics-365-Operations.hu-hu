---
title: Szakasz okkódjainak használata
description: Okkód használatával jelezheti, hogy miért történt egy szolgáltatásiszint-szerződés visszavonása, vagy egy szervizrendelés miért lépte túl a szolgáltatásiszint-szerződésben megadott időkorlátot.
author: ShylaThompson
ms.date: 05/07/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAServiceOrderTable, SMAParameters
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 307e6b3e67de702135662e047aef00fd181d4749
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5824246"
---
# <a name="use-stage-reason-codes"></a><span data-ttu-id="6afa3-103">Szakasz okkódjainak használata</span><span class="sxs-lookup"><span data-stu-id="6afa3-103">Use stage reason codes</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="6afa3-104">Okkód használatával jelezheti, hogy miért történt egy szolgáltatásiszint-szerződés visszavonása, vagy egy szervizrendelés miért lépte túl a szolgáltatásiszint-szerződésben megadott időkorlátot.</span><span class="sxs-lookup"><span data-stu-id="6afa3-104">You use a reason code to indicate why a service level agreement (SLA) has been canceled, or why a service order has exceeded the time limit that is you define in the SLA.</span></span>

<span data-ttu-id="6afa3-105">Előírhatja, hogy okkódot kell megadni a szolgáltatásiszint-szerződés visszavonásakor, vagy ha a szervizrendelés túllépi a szolgáltatásiszint-szerződésben megadott időkorlátot.</span><span class="sxs-lookup"><span data-stu-id="6afa3-105">You can also specify that a reason code is required when an SLA is canceled, or when the time limit exceeds the time that is specified in the SLA for the service order.</span></span>

<span data-ttu-id="6afa3-106">Ha előírta az okkód használatát, akkor a következő esetekben kötelező az okkód megadása:</span><span class="sxs-lookup"><span data-stu-id="6afa3-106">If you have specified that a reason code is required, you must enter a reason code in the following situations:</span></span>

  - <span data-ttu-id="6afa3-107">Ha a szervizrendelés olyan fokozatba került, amelyben leáll a kapcsolódó szolgáltatásiszint-szerződésben beállított határ elérését figyelő időrögzítés.</span><span class="sxs-lookup"><span data-stu-id="6afa3-107">When a service order is moved to a stage that stops time recording against the SLA for the service order.</span></span>

  - <span data-ttu-id="6afa3-108">Ha megtörténik a szervizrendelés láttamozása.</span><span class="sxs-lookup"><span data-stu-id="6afa3-108">When the service order is signed off.</span></span>

  - <span data-ttu-id="6afa3-109">Ha manuálisan leállítják az időrögzítést.</span><span class="sxs-lookup"><span data-stu-id="6afa3-109">When time recording is manually stopped.</span></span>

## <a name="set-up-reason-codes"></a><span data-ttu-id="6afa3-110">Okkódok beállítása</span><span class="sxs-lookup"><span data-stu-id="6afa3-110">Set up reason codes</span></span>

1.  <span data-ttu-id="6afa3-111">Kattintson a **Szolgáltatáskezelés** \> **Beállítás** \> **Szervizrendelések** \> **Fokozat okkódjai** elemre.</span><span class="sxs-lookup"><span data-stu-id="6afa3-111">Click **Service management** \> **Setup** \> **Service orders** \> **Stage reason codes**.</span></span>

2.  <span data-ttu-id="6afa3-112">Az **Állapot okkódjai** képernyőn új okkód létrehozásához kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="6afa3-112">In the **Stage reason codes** form, click **New** to create a new reason code.</span></span>

3.  <span data-ttu-id="6afa3-113">Az **Állapot okkódjai** mezőbe írjon be egy egyedi okkódot a fokozathoz.</span><span class="sxs-lookup"><span data-stu-id="6afa3-113">In the **Stage reason code** field, enter a unique stage reason code.</span></span>

4.  <span data-ttu-id="6afa3-114">A **Leírás** mezőbe írja be a fokozat okkódjának leírását.</span><span class="sxs-lookup"><span data-stu-id="6afa3-114">In the **Description** field, enter a description of the stage reason code.</span></span>

5.  <span data-ttu-id="6afa3-115">A módosítások mentéséhez zárja be a képernyőt.</span><span class="sxs-lookup"><span data-stu-id="6afa3-115">Close the form to save your changes.</span></span>

## <a name="require-reason-codes-when-a-service-level-agreement-is-canceled"></a><span data-ttu-id="6afa3-116">Okkódok megkövetelése szolgáltatásiszint-szerződés visszavonása esetén</span><span class="sxs-lookup"><span data-stu-id="6afa3-116">Require reason codes when a service level agreement is canceled</span></span>

1.  <span data-ttu-id="6afa3-117">Kattintson a **Szolgáltatáskezelés** \> **Beállítás** \> **Szolgáltatáskezelési paraméterek** pontra.</span><span class="sxs-lookup"><span data-stu-id="6afa3-117">Click **Service management** \> **Setup** \> **Service management parameters**.</span></span>

2.  <span data-ttu-id="6afa3-118">A **Szolgáltatáskezelés paraméterei** képernyőn, kattintson az **Általános** hivatkozásra, és jelölje be az **Okkód visszavonás esetén** jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="6afa3-118">In the **Service management parameters** form, click the **General** link, and then select the **Reason code on canceling** check box.</span></span>

## <a name="require-reason-codes-when-the-a-service-order-exceeds-the-time-limit-that-is-set-by-the-service-level-agreement"></a><span data-ttu-id="6afa3-119">Okkódok előírása, ha a szervizrendelés túllépi a szolgáltatásiszint-szerződésben beállított időhatárt</span><span class="sxs-lookup"><span data-stu-id="6afa3-119">Require reason codes when the a service order exceeds the time limit that is set by the service level agreement</span></span>

1.  <span data-ttu-id="6afa3-120">Kattintson a **Szolgáltatáskezelés** \> **Beállítás** \> **Szolgáltatáskezelési paraméterek** pontra.</span><span class="sxs-lookup"><span data-stu-id="6afa3-120">Click **Service management** \> **Setup** \> **Service management parameters**.</span></span>

2.  <span data-ttu-id="6afa3-121">A **Szolgáltatáskezelés paraméterei** képernyőn, kattintson az **Általános** hivatkozásra, és jelölje be az **Okkód időtúllépés esetén** jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="6afa3-121">In the **Service management parameters** form, click the **General** link, and then select the **Reason code on exceeding time** check box.</span></span>

## <a name="see-also"></a><span data-ttu-id="6afa3-122">Lásd még</span><span class="sxs-lookup"><span data-stu-id="6afa3-122">See also</span></span>

[<span data-ttu-id="6afa3-123">Szervizrendeléshez kapcsolódó időrögzítés elindítása és leállítása</span><span class="sxs-lookup"><span data-stu-id="6afa3-123">Start and stop time recording on a service order</span></span>](start-and-stop-time-recording-on-a-service-order.md)

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]