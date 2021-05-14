---
title: A munka nincs zárolva
description: A munka nincs zárolva
author: perlynne
ms.date: 04/15/2021
ms.topic: troubleshooting
ms.search.form: WHSWorkTable_WHSWorkUnblocking
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-05-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: d64ab282972e46e8857581b59e5705dd15667328
ms.sourcegitcommit: 5f5afb46431e1abd8fb6e92e0189914b598dc7fd
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/21/2021
ms.locfileid: "5924204"
---
# <a name="work-isnt-blocked"></a><span data-ttu-id="0fce7-103">A munka nincs zárolva</span><span class="sxs-lookup"><span data-stu-id="0fce7-103">Work isn't blocked</span></span>

<span data-ttu-id="0fce7-104">Hibakód: WHSUnblockNotBlockedWorkErrorMessage</span><span class="sxs-lookup"><span data-stu-id="0fce7-104">Error code: WHSUnblockNotBlockedWorkErrorMessage</span></span>

## <a name="symptoms"></a><span data-ttu-id="0fce7-105">Tünetek</span><span class="sxs-lookup"><span data-stu-id="0fce7-105">Symptoms</span></span>

<span data-ttu-id="0fce7-106">A rendszer a következő hibaüzenetet jeleníti meg:</span><span class="sxs-lookup"><span data-stu-id="0fce7-106">The system shows the following error message:</span></span>

> <span data-ttu-id="0fce7-107">A(z) %1 azonosítóval rendelkező munka nincs zárolva.</span><span class="sxs-lookup"><span data-stu-id="0fce7-107">Work with Id %1 is not blocked.</span></span>

## <a name="cause"></a><span data-ttu-id="0fce7-108">Ok</span><span class="sxs-lookup"><span data-stu-id="0fce7-108">Cause</span></span>

<span data-ttu-id="0fce7-109">A hullám **Blokkolt hullám** beállításának értéke *Nem*.</span><span class="sxs-lookup"><span data-stu-id="0fce7-109">The **Blocked wave** option on the wave is set to *No*.</span></span> <span data-ttu-id="0fce7-110">A munka zárolása nem oldható fel, mert jelenleg nincs zárolva.</span><span class="sxs-lookup"><span data-stu-id="0fce7-110">The work can't be unblocked because it isn't currently blocked.</span></span>

## <a name="resolution"></a><span data-ttu-id="0fce7-111">Felbontás</span><span class="sxs-lookup"><span data-stu-id="0fce7-111">Resolution</span></span>

 <span data-ttu-id="0fce7-112">Csak azok a munka zárolása oldható fel, amelyekben a **Blokkolt hullám** beállítása *Igen*.</span><span class="sxs-lookup"><span data-stu-id="0fce7-112">Only work where the **Blocked wave** option is set to *Yes* can be unblocked.</span></span>
