---
title: Az automatikus foglalásra vonatkozó kérdés megjelenik a rendelkezésre álló készlettel
description: Ha azonban olyan cikket használ egy raktárban, ahol a raktári folyamatok nincsenek engedélyezve, az automatikus foglalási kérdés megjelenik. Adja meg a hely fölötti dimenziókat.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: a15502ce8c5bc61d37cedd746985176408a2f362
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476589"
---
# <a name="auto-reservation-prompt-for-batch-number-is-shown-even-with-available-inventory"></a>A kötegszámhoz kapcsolódó, automatikus foglalásra vonatkozó kérdés megjelenik a rendelkezésre álló készlettel együtt

## <a name="symptoms"></a>Tünetek

Ha olyan cikket használ, amely *köteg-felett* foglalási hierarchiával rendelkezik egy olyan raktárban, amely nem engedélyezte a raktári folyamatokat, és az automatikus foglalás engedélyezve van, a kötegszám automatikus foglalási kérése akkor is megjelenik, ha csak egy köteg áll rendelkezésre kitárolásra.

Ha azonban ugyanazt a cikket használja egy raktárban, ahol a raktári folyamatok engedélyezve vannak, az automatikus foglalási kérdés nem jelenik meg.

## <a name="resolution"></a>Megoldás

Ha a foglalási hierarchia meghatározása *köteg-felett* vagy *sorozat-felett*, a hivatkozott dimenziót (**Kötegszám** vagy **Sorozatszám**) mindig meg kell adni igény szerinti rendeléseknél. A raktári folyamatok akkor tölthetik ki az adatokat, ha egyetlen köteg- vagy sorozatszám áll rendelkezésre. Mivel azonban a raktár nincs engedélyezve a raktári folyamatokhoz, a felhasználónak mindig meg kell adnia az összes **Hely** feletti dimenziót.
