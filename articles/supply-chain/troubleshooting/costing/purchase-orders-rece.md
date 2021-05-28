---
title: A ténylegesen beérkezett beszerzési rendelések nem jelennek meg a készletzárási jelentésben
description: A ténylegesen beérkezett beszerzési rendelések nem jelennek meg a Nyitott mennyiségek ellenőrzése készletzárási jelentésben.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: InventOpenQtyCritical
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 9508d6d75d8ebee7ca10140ed4c4215d7ad1dda7
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026575"
---
# <a name="physically-received-purchase-orders-dont-appear-on-the-inventory-closing-report"></a>A ténylegesen beérkezett beszerzési rendelések nem jelennek meg a készletzárási jelentésben

Tudásbáziscikk száma: 4612595

## <a name="symptoms"></a>Tünetek

A ténylegesen beérkezett beszerzési rendelések nem jelennek meg a **Nyitott mennyiségek ellenőrzése** készletzárási jelentésben.

## <a name="resolution"></a>Felbontás

A **Nyitott mennyiségek ellenőrzése** jelentés olyan kiadási tranzakciókat mutat, amelyek a pénzügyileg frissített készletbevételezésekkel szemben nem egyenlíthetők ki a kiválasztott zárási dátummal. A tényleges bevételezéseket is bele lehet foglalni a jelentésbe. Ebben az esetben a tényleges bevételezések megjelennek, ha fedezik a ki nem egyenlíthető kiadási tranzakciókat. További információ: [A készletzárás futtatásának előkészítése](/dynamicsax-2012/appuser-itpro/preparing-to-run-inventory-close).
