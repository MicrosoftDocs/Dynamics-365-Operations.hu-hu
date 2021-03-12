---
title: Raktáron belüli régebbi kötegek megjelenítésének konfigurálása mobileszközön
description: Ez a témakör leírja, hogy miként állítható be egy mobileszköz, hogy megjelenítse azoknak a helyeknek a listáját, ahol régebbi kötegek szerepelnek, mint egy munkasor jelenlegi helye.
author: Mirzaab
manager: tfehr
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSRFMenuItem
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 418ce3b320024780def0f7c5687b7c2e1c6b6f2b
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4996223"
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

