---
title: Vonalkódtípusok kezelése
description: Ez az eljárás bemutatja, hogyan állíthat be egy új vonalkód-definíciót, amelyet aztán a komissiózási lista jelentés részeként használhat.
author: yufeihuang
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: BarcodeSetup, InventParameters
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b689d1fc85d59ac87efa1903fd7122ae5ff011da
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/29/2021
ms.locfileid: "7571113"
---
# <a name="maintain-bar-code-types"></a>Vonalkódtípusok kezelése

[!include [banner](../../includes/banner.md)]

Ez az eljárás bemutatja, hogyan állíthat be egy új vonalkód-definíciót, amelyet aztán a komissiózási lista jelentés részeként használhat. Ezt a folyamatot az USMF bemutatócégen vagy saját adata használatával is elvégezheti. A USMF használata esetén alkalmazhatja az itt megjelenő, példa jellegű értékeket. Ezeket a feladatokat jellemzően egy raktári vezető végzi el.

1. Menjen a **Vonalkódok** oldalra.
1. Válassza az **Új** lehetőséget.
1. A **Vonalkód beállítása** mezőbe írjon be egy értéket.
1. Írjon egy értéket a **Leírás** mezőbe.
1. A **Vonalkód típusa** mezőben válasszon ki egy lehetőséget.
    * Az USMF használata esetén választhatja az „39-es kódot”.
1. A **Maszkazonosító** mezőben adja meg a vonalkódmaszk azonosítóját. A vonalkódmaszkok vonalkódok létrehozására és a pénztári (POS) rendszerben beolvasott vonalkódok gyors azonosítására használhatók. A részleteket lásd: [Vonalkódmaszkok beállítása](../../../commerce/set-up-bar-code-masks.md).
1. A **Méret** mezőbe írjon be egy számot.
1. A **Maximális hossz** mezőbe írjon be egy számot.
1. Válassza a **Mentés** lehetőséget.
1. Zárja be a lapot.
1. Lépjen a **Készlet- és raktárkezelési paraméterek** menüpontra.
1. A **Vonalkód beállítása** mezőben írjon be vagy válasszon ki egy értéket.
    * Válassza ki a korábban létrehozott vonalkód-beállítást, de vegye figyelembe, hogy a vonalkód formátumának meg kell egyeznie a folyamatban használt rekordtípus egyedi azonosítójának formátumával. Például a kitárolási útvonalakhoz, a vonalkód formátumnak egyeznie kell a kitárolási útvonal hivatkozásával, amely általában egy számsorozat.  
1. Válassza a **Mentés** lehetőséget.
1. Zárja be a lapot.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
