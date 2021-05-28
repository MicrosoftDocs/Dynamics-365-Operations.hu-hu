---
title: Az anyagjegyzéksorok ürülési elvének beállításai nem teljesülnek
description: Az anyagjegyzék (BOM) sorok ürülési elvének beállításai nem teljesülnek.
author: johanhoffmann
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: PurchTable,ProdParameters
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 84a84728016119a2a02f59f6903171afbceb48e7
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026577"
---
# <a name="flushing-principle-settings-on-bom-lines-arent-respected"></a><span data-ttu-id="8e283-103">Az anyagjegyzéksorok ürülési elvének beállításai nem teljesülnek</span><span class="sxs-lookup"><span data-stu-id="8e283-103">Flushing principle settings on BOM lines aren't respected</span></span>

<span data-ttu-id="8e283-104">Tudásbáziscikk száma: 4612725</span><span class="sxs-lookup"><span data-stu-id="8e283-104">KB number: 4612725</span></span>

## <a name="symptoms"></a><span data-ttu-id="8e283-105">Tünetek</span><span class="sxs-lookup"><span data-stu-id="8e283-105">Symptoms</span></span>

<span data-ttu-id="8e283-106">Eza problémára akkor merül fel, ha a **Termelésvezérlés paraméterei** oldal **Automatikus frissítés** lapjának **Automatikus anyagjegyzék-felhasználás** mezője *Ürülési elv* értékre van beállítva.</span><span class="sxs-lookup"><span data-stu-id="8e283-106">This issue occurs when the **Automatic BOM consumption** field on the **Automatic update** tab of the **Production control parameters** page is set to *Flushing principle*.</span></span> <span data-ttu-id="8e283-107">Ez a beállítás azt jelzi, hogy minden anyagjegyzék (BOM) sorok automatikusan fel vannak használva, ha beszerzési rendelés érkezik.</span><span class="sxs-lookup"><span data-stu-id="8e283-107">This setting indicates that all bill of materials (BOM) lines should automatically be consumed when a purchase order is received.</span></span> <span data-ttu-id="8e283-108">Ha az anyagjegyzéksorok **Ürülési elv** mezője kifejezetten *Manuális* beállítású, akkor arra lehet számítani, hogy az anyagjegyzéksorok nem lesznek automatikusan felhasználva.</span><span class="sxs-lookup"><span data-stu-id="8e283-108">If the **Flushing principle** field on BOM lines is explicitly set to *Manual*, you might expect that the BOM lines won't automatically be consumed.</span></span> <span data-ttu-id="8e283-109">Amikor azonban bekövetkezik ez a probléma, azok az Anyagjegyzéksorok, amelyekben az **Ürülési elv** mező beállítása *Manuális*, automatikusan felhasználja a program.</span><span class="sxs-lookup"><span data-stu-id="8e283-109">However, when this issue occurs, BOM lines where the **Flushing principle** field is set to *Manual* are automatically consumed anyway.</span></span>

## <a name="resolution"></a><span data-ttu-id="8e283-110">Felbontás</span><span class="sxs-lookup"><span data-stu-id="8e283-110">Resolution</span></span>

<span data-ttu-id="8e283-111">Ha ezt a problémát tapasztalja, előfordulhat, hogy a termelésellenőrzés paraméterei úgy vannak beállítva, hogy felülbírálja az anyagjegyzéksorok **Ürülési elv** beállítását.</span><span class="sxs-lookup"><span data-stu-id="8e283-111">If you're experiencing this issue, your production control parameters might be set up to override the **Flushing principle** setting on BOM lines.</span></span> <span data-ttu-id="8e283-112">A **Gyártásvezérlés paraméterei** lapon, az **Automatikus frissítés** lapon ellenőrizze az **Automatikus anyagjegyzék-felhasználás** mező értékét.</span><span class="sxs-lookup"><span data-stu-id="8e283-112">On the **Production control parameters** page, on the **Automatic update** tab, check the value of the **Automatic BOM consumption** field.</span></span> <span data-ttu-id="8e283-113">Ha a beállítás *Mindig*, a rendszer figyelmen kívül hagyja az összes anyagjegyzéksor **Ürülési elv** beállítását, és mindig üríti a sorokat.</span><span class="sxs-lookup"><span data-stu-id="8e283-113">If it's set to *Always*, the system will disregard the **Flushing principle** setting on all BOM lines and will always flush the lines.</span></span> <span data-ttu-id="8e283-114">Ha azt szeretné, hogy a rendszer tiszteletben tartsa az **Ürülési elv** beállítást az anyagjegyzéksorokon, módosítsa az **Automatikus anyagjegyzék felhasználás** mezőt *Ürülési elv* értékre.</span><span class="sxs-lookup"><span data-stu-id="8e283-114">To make the system respect the **Flushing principle** setting on BOM lines, change the value of the **Automatic BOM consumption** field to *Flushing principle*.</span></span>
