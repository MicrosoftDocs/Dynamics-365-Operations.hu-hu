---
title: Nincs Kezdő dátum érték a Cikkár lap Aktív árak lapján
description: Nincs Kezdő dátum érték a Cikkár lap Aktív árak lapján.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: InventItemPrice
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 3dd13f6a3e5ce3c894e96f420358d337f2e43dba
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026590"
---
# <a name="there-is-no-from-date-value-on-the-active-prices-tab-of-the-item-price-page"></a>Nincs Kezdő dátum érték a Cikkár lap Aktív árak lapján

Tudásbáziscikk száma: 4613548

## <a name="symptoms"></a>Tünetek

Nincs **Kezdő dátum** érték a **Cikkár lap** **Aktív árak** lapján.

## <a name="resolution"></a>Felbontás

A függő árhoz beállított **Kezdő dátum** (érvénybe lépés dátuma) nem kerül át az aktív árba.

A cikk-költségrekordok a legelső bevitelkor *Függőbben* állapottal és egy tervezett érvénybelépési dátummal rendelkeznek. A cikk-költség rekord aktiválásakor az állapot *Aktív* lesz, továbbá az érvénybelépési dátum az aktiválási dátumra módosul. Ennek megfelelően az aktív ár aktiválási dátuma mindig az aktiválás tényleges dátuma.

További információ: [Költségszámítási verziók áttekintése](../../cost-management/costing-versions.md).
