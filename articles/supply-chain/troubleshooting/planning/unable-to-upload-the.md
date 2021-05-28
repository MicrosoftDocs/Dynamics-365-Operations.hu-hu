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
# <a name="you-cant-update-the-forecasted-unit-cost-when-you-import-demand-forecast-records"></a>Az előre jelzett egységköltség nem frissítheti az igény-előrejelzési rekordok importálása során

Tudásbáziscikk száma: 4614109

## <a name="symptoms"></a>Tünetek

Ha adatentitásokat használ az igény-előrejelzési rekordok importálására, a meglévő rekordok **Előre jelzett egységára** nem frissül úgy, hogy az megegyezzen az importált adatokkal.

## <a name="cause"></a>Ok

**Az előre jelzett egységár** csak olvasható mező. Az érték a termék egységárán alapul, és nem lehet közvetlenül beállítani az importálás során.

## <a name="resolution"></a>Felbontás

Mivel a mező csak olvasható, ezért nem importálhat hozzá értékeket. Az érték számítása a meglévő üzleti logika szerint történik.
