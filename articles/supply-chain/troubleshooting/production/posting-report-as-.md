---
title: Hiba a Készre jelentés napló feladás a során
description: Amikor a Készre jelentés naplót közzéteszi, hibaüzenet jelenik meg, amely szerint a megrendelt mennyiség nem csökkenthető.
author: johanhoffmann
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ProdTableListPage, ProdParameters
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 55db7d0033dd66c1b973abf96671a20ab05d61d8
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026564"
---
# <a name="error-when-the-report-as-finished-journal-is-posted"></a>Hiba a Készre jelentés napló feladás a során

Tudásbáziscikk száma: 4612891

## <a name="symptoms"></a>Tünetek

Amikor a **Jelentés befejezettként** naplót feladja, hiba lép fel, és a következő hibaüzenet jelenik meg:

> A rendelt mennyiség nem csökkenthető, mert nincs elegendő nyitott készlettranzakció Rendelt állapottal. A cikkek: Vásárolt, Fogadott vagy Regisztrált.

Ez a hiba csak akkor fordul elő, ha a **Hibamennyiség** mező a **Jelentés befejezettként** napló első sorában be van állítva és a **Jó mennyiség** mező be van állítva az utolsó soron. Ha a **Hibamennyiség** mező az utolsó sorban van beállítva, nem történik hiba.

## <a name="resolution"></a>Felbontás

A hiba elkerülése érdekében nyissa meg a **Termelésvezérlés paraméterek** lapot, majd az **Általános** lapon állítsa be a **Fennmaradó mennyiség növelése a hibamennyiséggel** beállítás *Igen* értékre.
