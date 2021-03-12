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
ms.openlocfilehash: 7748a18d2b6f612b3ac9ac1a75efb6ae5f13859a
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4993879"
---
# <a name="troubleshoot-warehouse-replenishment"></a><span data-ttu-id="6aa40-103">Raktárfeltöltés – hibaelhárítás</span><span class="sxs-lookup"><span data-stu-id="6aa40-103">Troubleshoot warehouse replenishment</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6aa40-104">Ez a témakör azt mutatja be, hogyan lehet megoldani gyakori problémákat, miközben a raktári feltöltési munkákat végzi a Microsoft Dynamics 365 Supply Chain Management szolgáltatásban.</span><span class="sxs-lookup"><span data-stu-id="6aa40-104">This topic describes how to fix common issues that you might encounter while you work with warehouse replenishment in Microsoft Dynamics 365 Supply Chain Management.</span></span>

## <a name="i-receive-the-following-error-message-work-1-cannot-be-unblocked-because-it-has-unfinished-replenishment-work"></a><span data-ttu-id="6aa40-105">A következő hibaüzenet jelenik meg: „%1 munkaazonosító nem zárolható, mert befejezetlen feltöltési munkával rendelkezik".</span><span class="sxs-lookup"><span data-stu-id="6aa40-105">I receive the following error message: "Work %1 cannot be unblocked because it has unfinished replenishment work."</span></span>

### <a name="issue-description"></a><span data-ttu-id="6aa40-106">Probléma leírása</span><span class="sxs-lookup"><span data-stu-id="6aa40-106">Issue description</span></span>

<span data-ttu-id="6aa40-107">A kitárolási munka a függő feltöltési munka miatt le van zárolva.</span><span class="sxs-lookup"><span data-stu-id="6aa40-107">Picking work is blocked because of dependent replenishment work.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="6aa40-108">Probléma megoldása</span><span class="sxs-lookup"><span data-stu-id="6aa40-108">Issue resolution</span></span>

<span data-ttu-id="6aa40-109">Ha a kereslet szerinti feltöltést használja, akkor a rendszer a feltöltési munkát és a kitárolási munkát egyaránt létrehozza, ha a kitárolási helyet fel kell tölteni a forrásrendelés igényének kielégítésére.</span><span class="sxs-lookup"><span data-stu-id="6aa40-109">When you use wave demand replenishment, if a picking location must be replenished to fulfill the source order demand, the system creates both the replenishment work and the picking work.</span></span> <span data-ttu-id="6aa40-110">A kitárolási munkát azonban csak akkor zárolja, ha a feltöltési munka be van fejezve.</span><span class="sxs-lookup"><span data-stu-id="6aa40-110">However, it blocks the picking work until the replenishment work is completed.</span></span> <span data-ttu-id="6aa40-111">Ez a viselkedés szándékos, mert a kitárolási hely nem rendelkezik elegendő készlettel, ha a feltöltési munka be van fejezve.</span><span class="sxs-lookup"><span data-stu-id="6aa40-111">This behavior is intentional, because the picking location won't have enough inventory unless the replenishment work is completed.</span></span> <span data-ttu-id="6aa40-112">Fejezee be a feltöltési munkát, majd dolgozza fel a kitárolási munkát.</span><span class="sxs-lookup"><span data-stu-id="6aa40-112">Complete the replenishment work, and then process the picking work.</span></span>
