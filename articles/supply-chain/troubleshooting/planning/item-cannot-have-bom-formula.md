---
title: A cikkhez nem tartozhat anyagjegyzék vagy receptúra
description: Amikor rendelést próbál megerősíteni, hibaüzenetet kap a cikk ellenőrzése során. A hibaüzenetben az áll, hogy a cikkhez nem tartozhat anyagjegyzék vagy receptúra.
author: ankubik
ms.date: 06/10/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPO
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ankubik
ms.search.validFrom: 2021-06-10
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 6739b8b1e4d080055a2a0501427eac1c2e8a96c5
ms.sourcegitcommit: 18ca2df785e9656fdd4e8c0734eca2b2624fda10
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/22/2021
ms.locfileid: "6294092"
---
# <a name="item-cant-have-a-bom-or-formula"></a><span data-ttu-id="d10dd-104">A cikkhez nem tartozhat anyagjegyzék vagy receptúra</span><span class="sxs-lookup"><span data-stu-id="d10dd-104">Item can't have a BOM or formula</span></span>

<span data-ttu-id="d10dd-105">Hibakód: PRO2614</span><span class="sxs-lookup"><span data-stu-id="d10dd-105">Error code: PRO2614</span></span>

## <a name="symptoms"></a><span data-ttu-id="d10dd-106">Tünetek</span><span class="sxs-lookup"><span data-stu-id="d10dd-106">Symptoms</span></span>

<span data-ttu-id="d10dd-107">Amikor rendelést próbál megerősíteni, a köetkező hibaüzenetet kapja a cikk ellenőrzése során:</span><span class="sxs-lookup"><span data-stu-id="d10dd-107">When you try to firm an order, you receive the following error message during item validation:</span></span>

> <span data-ttu-id="d10dd-108">A cikkhez nem tartozhat anyagjegyzék vagy receptúra</span><span class="sxs-lookup"><span data-stu-id="d10dd-108">Item cannot have a BOM or formula</span></span>

## <a name="resolution"></a><span data-ttu-id="d10dd-109">Megoldás</span><span class="sxs-lookup"><span data-stu-id="d10dd-109">Resolution</span></span>

<span data-ttu-id="d10dd-110">Az anyagjegyzékkel vagy receptúrával rendelkező cikkeknek *Tervezési cikk*, *Anyagjegyzék* vagy *Receptúra* típusúnak kell lenniük.</span><span class="sxs-lookup"><span data-stu-id="d10dd-110">Items that have a bill of materials (BOM) or formula must be of the *Planning item*, *BOM*, or *formula* type.</span></span> <span data-ttu-id="d10dd-111">A cikkek típusa a következőképpen módosítható.</span><span class="sxs-lookup"><span data-stu-id="d10dd-111">To change the type of an item, follow these steps.</span></span>

1. <span data-ttu-id="d10dd-112">Kattintson a **Termékinformációk kezelése \> Termékek \> Kiadott termékek** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="d10dd-112">Go to **Product information management \> Products \> Released products**.</span></span>
1. <span data-ttu-id="d10dd-113">Nyissa mega releváns terméket.</span><span class="sxs-lookup"><span data-stu-id="d10dd-113">Open the relevant product.</span></span>
1. <span data-ttu-id="d10dd-114">A **Mérnöki feladatok** gyorslap **Termelés típusa** mezőjében adja meg a *Tervezési cikk*, az *Anyagjegyzék* vagy a *Receptúra* elemet.</span><span class="sxs-lookup"><span data-stu-id="d10dd-114">On the **Engineer** FastTab, set the **Production type** field to *Planning item*, *BOM*, or *formula*.</span></span>
