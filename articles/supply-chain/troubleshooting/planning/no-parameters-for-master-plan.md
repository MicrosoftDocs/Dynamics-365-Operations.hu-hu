---
title: Az alapterv paraméterei nem léteznek
description: Amikor rendelést próbál megerősíteni, olyan hibaüzenetet kap, amely szerint az alaptervhez nincsenek paraméterek.
author: ankubik
ms.date: 06/10/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPo
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ankubik
ms.search.validFrom: 2021-06-10
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: d4b64af2e30109b8560d40c4c532504611528bbe
ms.sourcegitcommit: 18ca2df785e9656fdd4e8c0734eca2b2624fda10
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/22/2021
ms.locfileid: "6294094"
---
# <a name="parameters-for-the-master-plan-dont-exist"></a><span data-ttu-id="5005e-103">Az alapterv paraméterei nem léteznek</span><span class="sxs-lookup"><span data-stu-id="5005e-103">Parameters for the master plan don't exist</span></span>

<span data-ttu-id="5005e-104">Hibakód: SYS25368</span><span class="sxs-lookup"><span data-stu-id="5005e-104">Error code: SYS25368</span></span>

## <a name="symptoms"></a><span data-ttu-id="5005e-105">Tünetek</span><span class="sxs-lookup"><span data-stu-id="5005e-105">Symptoms</span></span>

<span data-ttu-id="5005e-106">Amikor tervezett rendelést próbál megerősíteni, a következő hibaüzenetet kapja:</span><span class="sxs-lookup"><span data-stu-id="5005e-106">When you try to firm a planned order, you receive the following error message:</span></span>

> <span data-ttu-id="5005e-107">A(z) %1 alapterv paraméterei nem léteznek.</span><span class="sxs-lookup"><span data-stu-id="5005e-107">Parameters for master plan %1 do not exist.</span></span>

## <a name="cause"></a><span data-ttu-id="5005e-108">Ok</span><span class="sxs-lookup"><span data-stu-id="5005e-108">Cause</span></span>

<span data-ttu-id="5005e-109">Konfigurációs problémák miatt a rendszer nem találja a megadott terv beállításait.</span><span class="sxs-lookup"><span data-stu-id="5005e-109">Because of configuration issues, the system can't find the settings for the specified plan.</span></span>

## <a name="resolution"></a><span data-ttu-id="5005e-110">Megoldás</span><span class="sxs-lookup"><span data-stu-id="5005e-110">Resolution</span></span>

- <span data-ttu-id="5005e-111">Lépjen az **Alaptervezés \> Beállítás \> Konstrukciók \> Alaptervek** részre, és győződjön meg róla, hogy létezik a megadott nevű terv.</span><span class="sxs-lookup"><span data-stu-id="5005e-111">Go to **Master planning \> Setup \> Plans \> Master plans**, and make sure that a plan that has the specified name exists.</span></span>
