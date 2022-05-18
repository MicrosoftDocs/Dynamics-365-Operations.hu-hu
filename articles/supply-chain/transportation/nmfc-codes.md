---
title: NMFC (National Motor Freight Classification) kódok
description: Ez a témakör azt mutatja be, hogyan lehet dolgozni az NMFC (National Motor Freight Classification) kódokkal a Microsoft Dynamics 365 Supply Chain Management szolgáltatásban
author: Weijiesa
ms.date: 04/22/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: weijiesa
ms.search.validFrom: 2021-04-22
ms.dyn365.ops.version: 10.0.8
ms.openlocfilehash: 5127e132a8c06815e9ecd11338c729cd8bb87f18
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/03/2022
ms.locfileid: "8670580"
---
# <a name="national-motor-freight-classification-nmfc-codes"></a>NMFC (National Motor Freight Classification) kódok

[!include [banner](../includes/banner.md)]

A NMFC (National Motor Freight Classification) kódok segítségével osztályozhatja a szállítható cikkeket. Az NMFC-kód az áruk csoportosítására használható. Lehetővé teszi a szállítmányozási vállalatok számára, hogy a cikkek osztályozása során figyelembe vehessék például a termékek teherautóhoz való illeszkedését, az esetleg felmerülő rakodási és kezelési problémákat, illetve a romlandóságot. Az áruk 18 fuvarosztályba vannak sorolva 50 és 500 közötti számokkal való rangsorolás segítségével. Az árucikkeket négy szállítási jellemző – a sűrűség, a tárolhatóság, a kezelhetőség és a felelősség – kiértékelése alapján csoportosítják. Ezek a jellemzők együttesen határozzák meg az árucikk szállíthatóságát.

NMFC-kód van társítva minden olyan kisebb cikkhez, amely egy teherautórakománynál (LTL) kisebb. Például lehet, hogy egy hordozható számítógéphez egy 2,5-ös NMFC van hozzárendelve, míg a elektromos vezetékek hozzárendelhetőek egy 65-ös osztályú NMFC-hez.

Ez a funkció segít a dolgozóknak az NMFC-kódok használatával az LTL-szállítási cikkek osztályozásában. Íme néhány példa:

- Ha a vállalat fuvarleírást is ad a fuvarlevélhez (BOL), akkor a szállítmányozónak valamilyen elképzelése arról, hogy mit is szállít. A szállítmány osztályozása azért fontos, mert sok szállítmányozó vállalat az egész üzleti modelljét az általuk szállított fuvarozási típusokra alapozza.
- Ez az osztályozás fontos lehet a vállalat számára, mivel ez az adott rakomány költségének megállapítására használható.
- Vállalata azonosíthatja egy LTL-logisztikai és szállítmányozási vállalat nyereségességét.

Ez a témakör az NMFC-kódokkal végzett munkát mutatja be a Microsoft Dynamics 365 Supply Chain Management alkalmazásban.

## <a name="prerequisites"></a>Előfeltételek

Az NMFC-kódok létrehozása előtt be kell állítani az összes olyan LTL-fuvarozási sztályt, amelyet le kell képezni a számukra. Az LTL-fuvarozási osztályok cikkkategóriákat képviselnek, míg az NMFC-kódok a 18 fuvarosztály mindegyikében meghatározott árukhoz kapcsolódnak. Az LTL-osztályok használatával kapcsolatos további tudnivalókat lásd a [Kisebb, mint egy teherautórakomány (LTL) osztályok](ltl-class.md) részben.

## <a name="create-an-nmfc-code"></a>NMFC-kód létrehozása

NMFC-kód létrehozásához kövesse az alábbi lépéseket.

1. Tegye a következők egyikét:

    - Menjen a **Raktárkezelés \> Beállítás \> Készlet \> NMFC-kódok** elemre.
    - Ugorjon a **Szállításkezelés \> Beállítás \> Szállítmányozási standardok \> NMFC-kódok** lehetőségre.

1. Válassza ki az **Új** lehetőséget egy NMFC-kód létrehozásához. Majd, állítsa be a következő mezőket:

    - **NMFC-kód** – Adja meg a mezőben az árucikk-típus NMFC-kódját.
    - **Név** – Adjon egy nevet az NMFC-kódnak.
    - **LTL-osztály** – Az NMFC-kódhoz társított LTL-osztály kiválasztása.
    - **Fuvarlevélkezelési egység** – A szállítmány alapértelmezett kezelési típusának meghatározása.

## <a name="example-set-up-nmfc-codes"></a>Példa: NMFC-kódok beállítása

A következő példa bemutatja, hogyan lehet két különböző NMFC-kódot beállítani, amelyek különböző termékekkel használhatók.

1. Menjen a **Raktárkezelés \> Beállítás \> Készlet \> NMFC-kódok** elemre.
1. A Műveleti ablaktáblán kattintson az **Új** elemre.
1. Az új sorban állítsa be a következő értékeket:

    - **NMFC-kód:** *92,5*
    - **Név:** *Számítógépek*
    - **LTL-osztály:** *92,5*
    - **Fuvarlevél anyagkezelési egység:** *Egység*

1. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.
1. A Műveleti ablaktáblán kattintson az **Új** elemre.
1. Az új sorban állítsa be a következő értékeket:

    - **NMFC-kód:** *125*
    - **Név:** *Mobiltelefonok*
    - **LTL-osztály:** *125*
    - **Fuvarlevél anyagkezelési egység:** *Egység*

1. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.

## <a name="additional-resources"></a>További erőforrások

- [Kevesebb mint a teherautóosztályok (LTL)](ltl-class.md)
- [Fuvarlevél létrehozása](create-bill-of-lading.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
