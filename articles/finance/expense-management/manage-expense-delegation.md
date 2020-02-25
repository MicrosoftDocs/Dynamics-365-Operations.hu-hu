---
title: Költségdelegálás kezelése
description: A költségdelegált felhasználó a szervezet egy másik alkalmazottjának nevében hozhat létre és kezelhet kiadási jelentéseket.
author: KimANelson
manager: AnnBe
ms.date: 01/10/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TrvParameters
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2020-01-10
ms.dyn365.ops.version: 10.0.9
ms.openlocfilehash: d792daa56d468830b56eb395fadda582b3b5bad6
ms.sourcegitcommit: 6a70f9ac296158edd065d52a12703b3ce85ce5ee
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/03/2020
ms.locfileid: "3015241"
---
# <a name="manage-expense-delegation"></a><span data-ttu-id="9721b-103">Költségdelegálás kezelése</span><span class="sxs-lookup"><span data-stu-id="9721b-103">Manage expense delegation</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]


<span data-ttu-id="9721b-104">A költségdelegált felhasználó a szervezet egy másik alkalmazottjának nevében hozhat létre és kezelhet kiadási jelentéseket.</span><span class="sxs-lookup"><span data-stu-id="9721b-104">An expense delegate user can create and manage expense reports on behalf of another employee in the organization.</span></span>

## <a name="configuring-expense-delegation"></a><span data-ttu-id="9721b-105">Költségdelegálás konfigurálása</span><span class="sxs-lookup"><span data-stu-id="9721b-105">Configuring expense delegation</span></span>

<span data-ttu-id="9721b-106">A felhasználó költségdelegáltként való beállításához nyissa meg a **Költséggazdálkodás > Beálítás > Általános > Delegáltak** pontot a **Delegáltak** lapon.</span><span class="sxs-lookup"><span data-stu-id="9721b-106">To set up a user as an expense delegate, go to **Expense management > Setup > General > Delegates** to open the **Delegates** page.</span></span> <span data-ttu-id="9721b-107">Válassza az **Új** lehetőséget, majd válassza ki azt az alkalmazottat, akinek delegáltat kíván megadni.</span><span class="sxs-lookup"><span data-stu-id="9721b-107">Select **New** and then select the employee that will have a delegate defined.</span></span> <span data-ttu-id="9721b-108">Adja meg a delegált felhasználó aliasát, valamint a delegálási időszak kezdő és záró dátumát.</span><span class="sxs-lookup"><span data-stu-id="9721b-108">Enter the alias of the delegate user and the start and end date for the delegation period.</span></span>

## <a name="managing-expense-delegation-on-behalf-of-another-employee"></a><span data-ttu-id="9721b-109">Költségdelegálás kezelése egy másik alkalmazott nevében</span><span class="sxs-lookup"><span data-stu-id="9721b-109">Managing expense delegation on behalf of another employee</span></span>

<span data-ttu-id="9721b-110">Ha engedélyezve van a **Költségdelegáltak listaoldalának engedélyezése** funkciókezelő kulcs, akkor a **Hozzám delegált költségek** listaoldal elérhető lesz a **Költséggazdálkodás > Költségeim > Hozzám delegált költségek** helyre navigálva.</span><span class="sxs-lookup"><span data-stu-id="9721b-110">If the feature management key **Enable expense delegates list page** is enabled, the **Expenses delegated to me** list page will be available by navigating to **Expense management > My expenses > Expenses delegated to me**.</span></span>

<span data-ttu-id="9721b-111">A delegált felhasználó gyorsan szűrheti és megkeresheti azokat a meglévő költségjelentéseket, amelyek a felhasználóhoz lettek delegálva.</span><span class="sxs-lookup"><span data-stu-id="9721b-111">A delegate user can quickly filter and search on existing expense reports that hae been delegated to the user.</span></span> <span data-ttu-id="9721b-112">A felhasználó más felhasználók nevében is gyorsan létrehozhat új költségjelentést, ha az **Új költségjelentés** elemre kattint.</span><span class="sxs-lookup"><span data-stu-id="9721b-112">The user can also quickly create a new expense report on behalf of other users by clicking **New expense report**.</span></span>

<span data-ttu-id="9721b-113">A delegált felhasználók egyéb alkalmazottak nevében is létrehozhatnak és kezelhetnek költségjelentéseket, ha a **Költséggazdálkodás > Költségeim > Költségjelentések** részre navigálnak, és a **Más felhasználók költségeinek megnyitása** gombra kattintanak.</span><span class="sxs-lookup"><span data-stu-id="9721b-113">Delegate users can also create and manage expense reports on behalf of other employees by navigating to **Expense management > My expenses > Expense reports** and clicking the **Open other user's expenses** button.</span></span>
