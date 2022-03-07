---
title: A termékkonfigurációs modellek kiszámításakor az egész számok kerekítése hibás
description: A termékkonfigurációs modellek kiszámításakor az egész számok kerekítése nem mindig helyes. Javítsa ki a problémát egy további tizedes attribútummal és számítással.
author: SmithaNataraj
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: b17145d7d17cb784fe11b3fbf65ddf5aa5530f27
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476571"
---
# <a name="integers-incorrectly-rounded-when-product-configuration-models-are-calculated"></a>A termékkonfigurációs modellek kiszámításakor az egész számok kerekítése hibás

## <a name="symptoms"></a>Tünetek

Ez a probléma a következő műveletek végrehajtásakor fordulhat elő:

1. Állítsa be ezeket az attribútumokat egy termelési konfigurációs modellen:

    - Bemenet (egész szám)
    - Százalék (tizedesérték)
    - Eredmény (egész szám)

2. Hozzon létre egy kalkulációt, amelynek kifejezései a következők:

    *Eredmény* = *Bevitel* × *Százalék* ÷ 100

Ebben az esetben az egész szám eredmény nem mindig megfelelően van kerekítve. Ha például a bevitel 1000, és a százalékos érték 2,40, akkor az egész eredményre 24-et számít, mivel az 1000 2,40 százaléka 24 (vagy tizedes formájában 24,00). Ehelyett az eredmény 23-ként jelenik meg. Ha azonban a százalék 2,39, akkor a kalkuláció 24-re lesz kerekítve 23 helyett. Ha a százalék 2,50, akkor a kalkuláció a vártnak megfelelően 25 lesz.

## <a name="cause"></a>Ok

Ez a probléma amiatt fordul elő, mert a Microsoft Solver Foundation számokat a törtszámokkal, belső használatra jeleníti meg. Az előző példában a számítás eredménye, ahol a százalék 2,40 volt, így jelenik meg: 27021597764222975 ÷ 1125899906842624 = 23,99999999999999911182158029987476766109466552734375. Amikor a .NET egész számként adja meg ezt az értéket, 23-ra fog visszatérni.

## <a name="resolution"></a>Megoldás

Ez a viselkedés nem változik, mert más forgatókönyvek függnek tőle. Az előző példában a problémát egy további tizedes attribútum és kalkulációk bevezetésével oldhatja meg.

Például állítsa be a következő attribútumokat egy termelési konfigurációs modellen:

- Bemenet (egész szám)
- Százalék (tizedesérték)
- EredményTizedesérték (tizedesérték)
- EredményEgészszám (egész szám)

A következő kalkulációkat adhatja hozzá ezután:

- *EredményTizedesérték* = *Bemeneti* × *Százalék* ÷ 100
- *EredményEgészszám* = *EredményTizedesérték*
