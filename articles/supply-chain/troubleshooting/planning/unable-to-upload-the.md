---
title: Az előre jelzett egységköltség nem frissítheti az igény-előrejelzési rekordok importálása során
description: Ha adatentitásokat használ az igény-előrejelzési rekordok importálására, a meglévő rekordok önköltségi ára nem frissül úgy, hogy az megegyezzen az importált adatokkal.
author: ChristianRytt
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: DataManagementWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: angarmas
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: c8ea8322a6c7bafe2dfcaaee3e9989f753c85e2a
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026579"
---
# <a name="you-cant-update-the-forecasted-unit-cost-when-you-import-demand-forecast-records"></a><span data-ttu-id="2dcfc-103">Az előre jelzett egységköltség nem frissítheti az igény-előrejelzési rekordok importálása során</span><span class="sxs-lookup"><span data-stu-id="2dcfc-103">You can't update the forecasted unit cost when you import demand forecast records</span></span>

<span data-ttu-id="2dcfc-104">Tudásbáziscikk száma: 4614109</span><span class="sxs-lookup"><span data-stu-id="2dcfc-104">KB number: 4614109</span></span>

## <a name="symptoms"></a><span data-ttu-id="2dcfc-105">Tünetek</span><span class="sxs-lookup"><span data-stu-id="2dcfc-105">Symptoms</span></span>

<span data-ttu-id="2dcfc-106">Ha adatentitásokat használ az igény-előrejelzési rekordok importálására, a meglévő rekordok **Előre jelzett egységára** nem frissül úgy, hogy az megegyezzen az importált adatokkal.</span><span class="sxs-lookup"><span data-stu-id="2dcfc-106">When you use data entities to import demand forecast records, the **Forecasted unit cost** value for existing records isn't updated so that it matches the imported data.</span></span>

## <a name="cause"></a><span data-ttu-id="2dcfc-107">Ok</span><span class="sxs-lookup"><span data-stu-id="2dcfc-107">Cause</span></span>

<span data-ttu-id="2dcfc-108">**Az előre jelzett egységár** csak olvasható mező.</span><span class="sxs-lookup"><span data-stu-id="2dcfc-108">**Forecasted unit cost** is a read-only field.</span></span> <span data-ttu-id="2dcfc-109">Az érték a termék egységárán alapul, és nem lehet közvetlenül beállítani az importálás során.</span><span class="sxs-lookup"><span data-stu-id="2dcfc-109">The value is based on the product unit cost and can't be set directly through import.</span></span>

## <a name="resolution"></a><span data-ttu-id="2dcfc-110">Felbontás</span><span class="sxs-lookup"><span data-stu-id="2dcfc-110">Resolution</span></span>

<span data-ttu-id="2dcfc-111">Mivel a mező csak olvasható, ezért nem importálhat hozzá értékeket.</span><span class="sxs-lookup"><span data-stu-id="2dcfc-111">Because the field is read only, you can't import values for it.</span></span> <span data-ttu-id="2dcfc-112">Az érték számítása a meglévő üzleti logika szerint történik.</span><span class="sxs-lookup"><span data-stu-id="2dcfc-112">The value will be calculated according to the existing business logic.</span></span>
