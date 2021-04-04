---
title: Raktárfeltöltés – hibaelhárítás
description: Ez a témakör azt mutatja be, hogyan lehet megoldani gyakori problémákat, miközben a raktári feltöltési munkákat végzi a Microsoft Dynamics 365 Supply Chain Management szolgáltatásban.
author: perlynne
manager: tfehr
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 8dfb58c9156df106f58dfdc0ee2e0ef8defb9d9f
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5263204"
---
# <a name="troubleshoot-warehouse-replenishment"></a><span data-ttu-id="4f26f-103">Raktárfeltöltés – hibaelhárítás</span><span class="sxs-lookup"><span data-stu-id="4f26f-103">Troubleshoot warehouse replenishment</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4f26f-104">Ez a témakör azt mutatja be, hogyan lehet megoldani gyakori problémákat, miközben a raktári feltöltési munkákat végzi a Microsoft Dynamics 365 Supply Chain Management szolgáltatásban.</span><span class="sxs-lookup"><span data-stu-id="4f26f-104">This topic describes how to fix common issues that you might encounter while you work with warehouse replenishment in Microsoft Dynamics 365 Supply Chain Management.</span></span>

## <a name="i-receive-the-following-error-message-work-1-cannot-be-unblocked-because-it-has-unfinished-replenishment-work"></a><span data-ttu-id="4f26f-105">A következő hibaüzenet jelenik meg: „%1 munkaazonosító nem zárolható, mert befejezetlen feltöltési munkával rendelkezik".</span><span class="sxs-lookup"><span data-stu-id="4f26f-105">I receive the following error message: "Work %1 cannot be unblocked because it has unfinished replenishment work."</span></span>

### <a name="issue-description"></a><span data-ttu-id="4f26f-106">Probléma leírása</span><span class="sxs-lookup"><span data-stu-id="4f26f-106">Issue description</span></span>

<span data-ttu-id="4f26f-107">A kitárolási munka a függő feltöltési munka miatt le van zárolva.</span><span class="sxs-lookup"><span data-stu-id="4f26f-107">Picking work is blocked because of dependent replenishment work.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="4f26f-108">Probléma megoldása</span><span class="sxs-lookup"><span data-stu-id="4f26f-108">Issue resolution</span></span>

<span data-ttu-id="4f26f-109">Ha a kereslet szerinti feltöltést használja, akkor a rendszer a feltöltési munkát és a kitárolási munkát egyaránt létrehozza, ha a kitárolási helyet fel kell tölteni a forrásrendelés igényének kielégítésére.</span><span class="sxs-lookup"><span data-stu-id="4f26f-109">When you use wave demand replenishment, if a picking location must be replenished to fulfill the source order demand, the system creates both the replenishment work and the picking work.</span></span> <span data-ttu-id="4f26f-110">A kitárolási munkát azonban csak akkor zárolja, ha a feltöltési munka be van fejezve.</span><span class="sxs-lookup"><span data-stu-id="4f26f-110">However, it blocks the picking work until the replenishment work is completed.</span></span> <span data-ttu-id="4f26f-111">Ez a viselkedés szándékos, mert a kitárolási hely nem rendelkezik elegendő készlettel, ha a feltöltési munka be van fejezve.</span><span class="sxs-lookup"><span data-stu-id="4f26f-111">This behavior is intentional, because the picking location won't have enough inventory unless the replenishment work is completed.</span></span> <span data-ttu-id="4f26f-112">Fejezee be a feltöltési munkát, majd dolgozza fel a kitárolási munkát.</span><span class="sxs-lookup"><span data-stu-id="4f26f-112">Complete the replenishment work, and then process the picking work.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]