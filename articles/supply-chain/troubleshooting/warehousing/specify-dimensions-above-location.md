---
title: Köteg fölötti hierarchiával rendelkező részleges mennyiséghez nem adható ki rakomány.
description: Ha köteg fölötti foglalási hierarchiával rendelkező cikket használ, akkor a rakománysoroknak meg kell határozniuk a hely feletti dimenziókat, hogy a készletet fel lehessen osztani.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: eb7e71cc271903cb689c33777b72862246f2dd42
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476527"
---
# <a name="cant-release-a-load-for-partial-quantity-with-batch-above-reservation-hierarchy"></a>Köteg fölötti foglalási hierarchiával rendelkező részleges mennyiséghez nem adható ki rakomány.

## <a name="symptoms"></a>Tünetek

Ha olyan cikket használ, amelyben a *köteg-felett* foglalási hierarchia szerepel, akkor a **Rakománytervezési munkaterület** oldal **Kiadás a raktárba** parancsa nem működik, amikor részleges mennyiségre próbál kiadni egy rakományt. A következő hibaüzenetet kaphatja:

> A hullámhoz hozzárendelni kívánt soroknak meg kell adni a hely fölötti dimenzióit. Ezeknek a dimenzióknak a hozzárendeléséhez foglalja le és hozza létre újból a rakománysort.

Azonban ha olyan cikket használ, amelyben a *köteg-alatt* foglalási hierarchia szerepel, akkor kiadhat egy rakományt részleges mennyiségre a **Rakománytervezési munkaterület** oldaláról.

## <a name="cause"></a>Ok

Ha a foglalási hierarchiában a **Hely** dimenzió felett található egy dimenzió, akkor azt a raktárba történő kiadás előtt meg kell határozni. A készlet csak akkor osztható fel sikeresen, ha a hely feletti dimenziókban nincsenek rések.

## <a name="resolution"></a>Megoldás

Gondoskodjon róla, hogy a **Hely** fölötti összes dimenzió hozzá legyen rendelve a rakománysor foglalása és újbóli létrehozása által.
