---
title: Raktáron belüli régebbi kötegek megjelenítésének konfigurálása mobileszközön
description: Ez a témakör leírja, hogy miként állítható be egy mobileszköz, hogy megjelenítse azoknak a helyeknek a listáját, ahol régebbi kötegek szerepelnek, mint egy munkasor jelenlegi helye.
author: Mirzaab
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSRFMenuItem
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3d23a259f4c16026ee36f73b427f7d2e610a4b8d938c2e21ec9715d8d2b8137b
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6727774"
---
# <a name="configure-display-older-batches-within-warehouse-on-a-mobile-device"></a>Raktáron belüli régebbi kötegek megjelenítésének konfigurálása mobileszközön

[!include [banner](../includes/banner.md)]

A **Raktáron belüli régebbi kötegek megjelenítése** konfiguráció lehetővé teszi azon helyek listájának megjelenítését, ahol olyan kötegek szerepelnek, amelyek régebbiek a munkasor jelenlegi helyénél. A megjelenített helyek listája tartalmazza a régebbi kötegekkel kapcsolatos információkat, az egyes tételek lejárati dátumával és fizikai készletével együtt. Kiválaszthatja, hogy a kitárolás új helyről történjen, vagy folytathatja a kitárolást az aktuális helyről is. 
- Kitárolás új helyről – Ha új helyet választ ki a kitárolásra, akkor az aktuális munkasor frissül az új hely használatával, és a munka az új helyszínen a szokásos módon folytatódik. Ahhoz, hogy az új hely érvényes legyen, elegendő mennyiséggel kell rendelkeznie a teljes munkasorra kiterjedően. Ha nem érhető el a szükséges mennyiség, akkor a munkasor nem frissül, és a lista jelenik meg. 
- Kitárolás folytatása a jelenlegi helyről – Ha folytatja az aktuális munkaterület használatát, akkor a munkasor mennyiségeit továbbra is az eredeti helyről tárolja ki a rendszer.

## <a name="where-it-applies"></a>Alkalmazási kör
A Raktáron belüli régebbi kötegek megjelenítésének konfigurálása a mobileszköz menüelemeiben történik, és a kitárolási köteg alatti elemekre van hatással.

## <a name="set-up-display-older-batches-within-warehouse"></a>Raktáron belüli régebbi kötegek megjelenítésének beállítása
A **Raktáron belüli régebbi kötegek megjelenítésének** konfigurálása akkor áll rendelkezésre mobileszközön menüelemek formájában, ha a **Legrégebbi köteg kitárolása** opció beállítása **Figyelmeztetés**.

- A **Raktárkezelés** > **Beállítás** > **Mobileszköz** > **Mobileszköz menüpontjai** lehetőségnél állítsa a **Meglévő munka használata** beállítást **Igen** értékre a menüpontra vonatkozóan, majd válassza ki a **Figyelmeztetés** beállítást a **Legrégebbi köteg kitárolása** mezőben. 



[!INCLUDE[footer-include](../../includes/footer-banner.md)]