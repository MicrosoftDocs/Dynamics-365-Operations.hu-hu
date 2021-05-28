---
title: Hiba lép fel, ha a helyet választanak ki a kitárolási lista regisztrációja során
description: Hiba lép fel, ha a helyet választanak ki a kitárolási lista regisztrációja során.
author: perlynne
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: WMSPickingRegistration
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: b7fc579821f9a80d94aea949fcc0301b9d8f6935
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026559"
---
# <a name="an-error-occurs-when-the-location-is-selected-during-picking-list-registration"></a><span data-ttu-id="8e112-103">Hiba lép fel, ha a helyet választanak ki a kitárolási lista regisztrációja során</span><span class="sxs-lookup"><span data-stu-id="8e112-103">An error occurs when the location is selected during picking list registration</span></span>

<span data-ttu-id="8e112-104">Tudásbáziscikk száma: 4613106</span><span class="sxs-lookup"><span data-stu-id="8e112-104">KB number: 4613106</span></span>

## <a name="symptoms"></a><span data-ttu-id="8e112-105">Tünetek</span><span class="sxs-lookup"><span data-stu-id="8e112-105">Symptoms</span></span>

<span data-ttu-id="8e112-106">Ez a probléma akkor jelentkezik, ha a rendszer úgy van beállítva, hogy automatikusan lefoglalja az értékesítési rendeléseket.</span><span class="sxs-lookup"><span data-stu-id="8e112-106">This issue occurs when your system is configured to automatically reserve sales orders.</span></span> <span data-ttu-id="8e112-107">Ha megpróbálja kiválasztani a kitárolási lista regisztrációs sorának helyét, a következő hibaüzenet jelenik meg a raktárkezelési (WMS) foglalási folyamatok használatakor:</span><span class="sxs-lookup"><span data-stu-id="8e112-107">If you try to select the location for a picking list registration line, you receive the following error message when you use warehouse management (WMS) reservation processes:</span></span>

> <span data-ttu-id="8e112-108">Nem frissíthető a mennyiség új dimenziókkal</span><span class="sxs-lookup"><span data-stu-id="8e112-108">Can't update quantity with new dimensions</span></span>

<span data-ttu-id="8e112-109">Ez a probléma azért fordulhat elő, mert nincs elég készlete egy megadott helyen.</span><span class="sxs-lookup"><span data-stu-id="8e112-109">This issue can occur because you don't have enough on-hand inventory at a specified location.</span></span>

## <a name="resolution"></a><span data-ttu-id="8e112-110">Felbontás</span><span class="sxs-lookup"><span data-stu-id="8e112-110">Resolution</span></span>

<span data-ttu-id="8e112-111">A rendszer úgy viselkedik, ahogy tervezték.</span><span class="sxs-lookup"><span data-stu-id="8e112-111">The system is behaving as designed.</span></span>

<span data-ttu-id="8e112-112">Azokban az esetekben, amikor a raktárszintű foglalási folyamatot használja, ha az aktuális készlet nem lesz lefoglalva az összes készletdimenziós szinten, és nincs elegendő akutális készlete egy megadott helyen, javasoljuk, hogy használja a kézi foglalási folyamatot a kitárolási sorból.</span><span class="sxs-lookup"><span data-stu-id="8e112-112">In scenarios where you use the warehouse-level reservation process, if the on-hand inventory won't be reserved on all inventory dimension levels, and you don't have enough on-hand inventory at a specified location, we recommend that you use the manual reservation process from the picking line.</span></span> <span data-ttu-id="8e112-113">Ezután az *Adag foglalása* funkcióval terjesztheti az alacsonyabb foglalásokat, például a helyeket az összes rendelkezésre álló aktuális mennyiségre.</span><span class="sxs-lookup"><span data-stu-id="8e112-113">You can then use the *Reserve lot* function to distribute the lower reservations, such as location, for all the available on-hand quantities.</span></span>
