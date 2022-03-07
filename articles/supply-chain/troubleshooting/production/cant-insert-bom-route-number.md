---
title: Nem lehet beszúrni az anyagjegyzék és az útvonalszámok aktív verzióját
description: Ha az alapértelmezett hely és raktár már meg van határozva egy kiválasztott termékhez, akkor a rendszer nem kéri a darabjegyzék és az útvonalszámok aktív verziójának beillesztését.
author: SmithaNataraj
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 241618d70f01c85df946a48493f5d84e0964218e
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476505"
---
# <a name="cant-insert-bill-of-material-and-route-when-creating-a-new-production-order"></a>Új termelési rendelés létrehozásakor nem lehet anyagjegyzéket és útvonalat beszúrni

## <a name="symptoms"></a>Tünetek

Új termelési rendelés létrehozásakor a cikkszám megadása után a **Hely** és **Raktár** mezők automatikusan a késztermékek **Alapértelmezett rendelési beállítások** lapján megadott alapértelmezett helyre és raktárra lesznek beállítva. Ezenkívül a program automatikusan beírta az aktív anyagjegyzékszámot és útvonalszámot, így nem jelenik meg a következő üzenet, amely ezeket az értékeket kéri:

> Szúrja be az aktív verziót az anyagjegyzékhez és az útvonalhoz?

## <a name="resolution"></a>Megoldás

Ha az **Alapértelmezett rendelési beállítások** lapon kiválaszt egy olyan terméket, amelyhez egy hely és egy raktár már meg van adva, a program nem kéri az anyagjegyzék- és útvonalszámok megadását. A program csak akkor kéri, ha ezek az értékek nincsenek megadva a kijelölt termékhez.
