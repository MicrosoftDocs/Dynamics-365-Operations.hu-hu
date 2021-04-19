---
title: Raktárfeltöltés – hibaelhárítás
description: Ez a témakör azt mutatja be, hogyan lehet megoldani gyakori problémákat, miközben a raktári feltöltési munkákat végzi a Microsoft Dynamics 365 Supply Chain Management szolgáltatásban.
author: perlynne
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 8940f729e1115405e8d6e50eccc92d9fffe37f3e
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5828082"
---
# <a name="troubleshoot-warehouse-replenishment"></a><span data-ttu-id="568ff-103">Raktárfeltöltés – hibaelhárítás</span><span class="sxs-lookup"><span data-stu-id="568ff-103">Troubleshoot warehouse replenishment</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="568ff-104">Ez a témakör azt mutatja be, hogyan lehet megoldani gyakori problémákat, miközben a raktári feltöltési munkákat végzi a Microsoft Dynamics 365 Supply Chain Management szolgáltatásban.</span><span class="sxs-lookup"><span data-stu-id="568ff-104">This topic describes how to fix common issues that you might encounter while you work with warehouse replenishment in Microsoft Dynamics 365 Supply Chain Management.</span></span>

## <a name="i-receive-the-following-error-message-work-1-cannot-be-unblocked-because-it-has-unfinished-replenishment-work"></a><span data-ttu-id="568ff-105">A következő hibaüzenet jelenik meg: „%1 munkaazonosító nem zárolható, mert befejezetlen feltöltési munkával rendelkezik".</span><span class="sxs-lookup"><span data-stu-id="568ff-105">I receive the following error message: "Work %1 cannot be unblocked because it has unfinished replenishment work."</span></span>

### <a name="issue-description"></a><span data-ttu-id="568ff-106">Probléma leírása</span><span class="sxs-lookup"><span data-stu-id="568ff-106">Issue description</span></span>

<span data-ttu-id="568ff-107">A kitárolási munka a függő feltöltési munka miatt le van zárolva.</span><span class="sxs-lookup"><span data-stu-id="568ff-107">Picking work is blocked because of dependent replenishment work.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="568ff-108">Probléma megoldása</span><span class="sxs-lookup"><span data-stu-id="568ff-108">Issue resolution</span></span>

<span data-ttu-id="568ff-109">Ha a kereslet szerinti feltöltést használja, akkor a rendszer a feltöltési munkát és a kitárolási munkát egyaránt létrehozza, ha a kitárolási helyet fel kell tölteni a forrásrendelés igényének kielégítésére.</span><span class="sxs-lookup"><span data-stu-id="568ff-109">When you use wave demand replenishment, if a picking location must be replenished to fulfill the source order demand, the system creates both the replenishment work and the picking work.</span></span> <span data-ttu-id="568ff-110">A kitárolási munkát azonban csak akkor zárolja, ha a feltöltési munka be van fejezve.</span><span class="sxs-lookup"><span data-stu-id="568ff-110">However, it blocks the picking work until the replenishment work is completed.</span></span> <span data-ttu-id="568ff-111">Ez a viselkedés szándékos, mert a kitárolási hely nem rendelkezik elegendő készlettel, ha a feltöltési munka be van fejezve.</span><span class="sxs-lookup"><span data-stu-id="568ff-111">This behavior is intentional, because the picking location won't have enough inventory unless the replenishment work is completed.</span></span> <span data-ttu-id="568ff-112">Fejezee be a feltöltési munkát, majd dolgozza fel a kitárolási munkát.</span><span class="sxs-lookup"><span data-stu-id="568ff-112">Complete the replenishment work, and then process the picking work.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]