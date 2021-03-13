---
title: Szállítók keresése
description: Útmutató a szállítók meghatározott feltételek alapján történő kereséhez.
author: RichardLuan
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendSearchCriterion, VendSearchAddCategory, VendSearchAddReviewCriterionGroup, VendSearchResults, VendSearchAddReviewCriterion
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7caa146532d2bce06b009c45da635327766a88d1
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/16/2021
ms.locfileid: "5020704"
---
# <a name="search-for-vendors"></a>Szállítók keresése

[!include [banner](../../includes/banner.md)]

Útmutató a szállítók meghatározott feltételek alapján történő kereséhez. Ez a példa bemutatja, hogyan lehet olyan szállítókat keresni, amelyek egy adott beszerzési kategóriához jóváhagyottak, és az elsődleges címük egy adott országban van. Ezt a folyamatot az USMF bemutatócéggel vagy saját adataival is futtathatja. Ezt a feladatot általában egy beszerzési szakember végzi el.

1. Ugorjon a Beszerzés és forrás > Szállítók > Szállítók keresése elemre.
2. Kattintson a pluszjelre a Beszerzési kategória választó oldal megnyitásához.  
3. A fán válassza a „CORP PROCUREMENT CATEGORIES\OFFICE MACHINES” pontot.
    * Ha a folyamatot feladat-útmutatóként használja, szükség lehet a Zárolás feloldása gombra, mielőtt a helyes csomópontot kiválaszthatja. Ha nem használ USMF-et, válassza a meglévő kategóriák egyikét.  
4. Kattintson a Hozzáadás gombra.
    * Itt egynél több kategóriát is kiválaszthat. Ha ezt teszi, a keresés megtalálja a kategóriák közül legalább egyhez engedélyezett szállítókat.  
5. Kattintson az OK gombra.
6. Írjon be egy értéket az Ország/régió mezőbe.
7. Kattintson az OK gombra.

