---
title: Egyeztetési okokból csak a főszámlát adhat hozzá hitelszámlaként
description: Ha a Szállításkezelésben egyeztetési okot állít be, csak a főszámlát adhat hozzá hitelszámlaként.
author: Henrikan
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: TMSFBDetailReconcile
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 708081370b27fd51ef9a2329d8392f4515353dcb
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026561"
---
# <a name="you-can-add-only-the-main-account-as-the-credit-account-for-reconciliation-reasons"></a>Egyeztetési okokból csak a főszámlát adhat hozzá hitelszámlaként

Tudásbáziscikk száma: 4603538

## <a name="symptoms"></a>Tünetek

Ha a Szállításkezelésben egyeztetési okot állít be, csak a főszámlát adhat hozzá hitelszámlaként. Nem adhat hozzá költségközpontot vagy más dimenziót hitelszámlaként. A terhelési számla azonban lehetővé teszi más dimenziók kiválasztását.

## <a name="resolution"></a>Felbontás

Ha az egyeztetés nem a szállító kifizetésével, hanem egy adott főszámlára történő jóváírással történik, a rendszer nem teszi lehetővé a hitelszámla pénzügyi dimenziójának kiválasztását az egyeztetési ok beállításakor.

Ha a számlastruktúra a hitel főszámlájának adott pénzügyi dimenzióértékét igényli, a kapott szállítói napló nem adható fel automatikusan, mert hiányzik a pénzügyi dimenzió értéke. Ezért először manuálisan kell megadnia a hitelszámlát a **Számlanapló** oldalon.

Mivel a hitelszámlához dimenzióérték szükséges, a szállítói számlanapló nem adható fel automatikusan. Manuálisan kell elküldenie, miután manuálisan hozzáadta a dimenzióértéket a hitelsor fő számlájához.
