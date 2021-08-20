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
ms.openlocfilehash: 49faa2c68d496c5c0d8c7e4abfd93d9a917857220dd23c09a050fa3436e1d49a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6746867"
---
# <a name="physically-received-purchase-orders-dont-appear-on-the-inventory-closing-report"></a>A ténylegesen beérkezett beszerzési rendelések nem jelennek meg a készletzárási jelentésben

Tudásbáziscikk száma: 4612595

## <a name="symptoms"></a>Tünetek

A ténylegesen beérkezett beszerzési rendelések nem jelennek meg a **Nyitott mennyiségek ellenőrzése** készletzárási jelentésben.

## <a name="resolution"></a>Felbontás

A **Nyitott mennyiségek ellenőrzése** jelentés olyan kiadási tranzakciókat mutat, amelyek a pénzügyileg frissített készletbevételezésekkel szemben nem egyenlíthetők ki a kiválasztott zárási dátummal. A tényleges bevételezéseket is bele lehet foglalni a jelentésbe. Ebben az esetben a tényleges bevételezések megjelennek, ha fedezik a ki nem egyenlíthető kiadási tranzakciókat. További információ: [A készletzárás futtatásának előkészítése](/dynamicsax-2012/appuser-itpro/preparing-to-run-inventory-close).
