---
title: Költségobjektumok
description: Ez a cikk tájékoztatást ad a költségobjektumokról és elmagyarázza hogyan halmozódnak föl a költségek és a mennyiségek. Egy költségobjektum egy olyan entitás, amelyhez költségek és mennyiségek halmozódnak föl. A költségobjektum-entitás lehet egy termék vagy egy termékváltozat, úgy mint változatok a stílusra és színre.
author: JennySong-SH
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventCostOnhandItem
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19451
ms.assetid: ec776b98-813a-490d-848f-468452d98fac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yanansong
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 93220208384ccb1a3cc8ff43d83577293e1f029e
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/03/2022
ms.locfileid: "8672458"
---
# <a name="cost-objects"></a>Költségobjektumok

[!include [banner](../includes/banner.md)]

Ez a cikk tájékoztatást ad a költségobjektumokról és elmagyarázza hogyan halmozódnak föl a költségek és a mennyiségek. Egy költségobjektum egy olyan entitás, amelyhez költségek és mennyiségek halmozódnak föl. A költségobjektum-entitás lehet egy termék vagy egy termékváltozat, úgy mint változatok a stílusra és színre.  

## <a name="cost-objects"></a>Költségobjektumok

A **Költségobjektumok** lap felsorolja az összes költségobjektumot, ami regisztrálva van egy termékhez. A költségobjektumokat az alábbi forrásokból származó adatok határozzák meg:

-   Termék
-   Termékdimenzió-csoport
-   Tárolásidimenzió-csoport
-   Nyomonkövetésidimenzió-csoport

**Megjegyzés:** A költségobjektum csak a **Közvetlen anyag** költségösszetevőjének felel meg. A költségobjektum és a készletobjektum abban különböznek, hogy a költségobjektumot a pénzügyi készlet számára kiválasztott készletdimenzió határozza meg. Például egy cikk az alábbi konfigurációval rendelkezik:

-   **Webhely:** Tényleges készlet = Igen, Pénzügyi készlet = Igen
-   **Raktár:** Tényleges készlet = Igen, Pénzügyi készlet = Nem
-   **Köteg szám:** Tényleges készlet = Igen, Pénzügyi készlet = Nem

Az alábbi táblázat bemutatja, hogy mi a költségobjektum és mi a készletobjektum.

| Objektumtípus      | Cikkszám | Hely | Raktár | Kötegsz. |
|------------------|-------------|------|-----------|-----------|
| Költségobjektum      | x           | x    |           |           |
| Készletobjektum | x           | x    |  x        | x         |

## <a name="accumulation-of-costs-and-quantities"></a>A költség és mennyiség összevonása
-   Az érték az **Érték** mezőben az alábbi értékek összessége:
    -   Tényleges önköltségi érték
    -   Pénzügyi költség összege
    -   Kiigazítások
-   Az érték a **Mennyiség** mezőben az alábbi értékek összessége:
    -   Bevételezve
    -   Kiszállított
    -   Feladott mennyiség
-   Az **Átlagos egységenkénti költség** mező egy kiszámított mező. Az értékét az **Érték** mező **Mennyiség** mezővel való elosztásával kapjuk meg.

**Megjegyzés**: A **Tényleges érték beszámítása** paraméter nem befolyásolja az előző számításokat.

## <a name="additional-resources"></a>További erőforrások

[Termékdimenzió-csoport](/dynamicsax-2012/appuser-itpro/about-product-dimensions)

[Tárolásidimenzió-csoport](/dynamicsax-2012//storage-dimension-groups-form)

[Nyomonkövetésidimenzió-csoport](/dynamicsax-2012//tracking-dimension-groups-form)

[Új vagy módosult elemek](../../fin-ops-core/fin-ops/get-started/whats-new-changed.md)

[Költségbejegyzések](cost-entries.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]