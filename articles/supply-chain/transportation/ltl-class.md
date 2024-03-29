---
title: Kevesebb mint a teherautóosztályok (LTL)
description: Ez a cikk bemutatja, hogy mi kevesebb a teherautók rakományosztályainál, és bemutatja, hogyan lehet ezeket beállítani a Microsoftnál Dynamics 365 Supply Chain Management.
author: Weijiesa
ms.date: 04/05/2021
ms.topic: article
ms.search.form: WHSLTLClass
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: weijiesa
ms.search.validFrom: 2021-04-05
ms.dyn365.ops.version: 10.0.8
ms.openlocfilehash: 9ab05e1bc5d0ae2c8b5d98dda32660d2436676e9
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8857199"
---
# <a name="less-than-truckload-ltl-classes"></a>Kevesebb mint a teherautóosztályok (LTL)

[!include [banner](../includes/banner.md)]

A teherautórakománynál (LTL) kisebb osztály olyan fuvarszállítási osztály, amely a szállítható cikkek osztályozására használható. Általában minden termék- vagy árucikktípushoz NMFC (National Motor Freight Classification) kód tartozik, amely az LTL-szállítmányok meghatározott fuvarosztály-számának felel meg. Az LTL-fuvarozási osztályok cikkkategóriákat képviselnek, míg az NMFC-kódok a 18 fuvarosztály mindegyikében meghatározott árukhoz kapcsolódnak.

A funkciók segítségével a rendszerrel az alábbi műveleteket végezeti el:

- A vállalatnál használt LTL-fuvarosztályok meghatározása.
- Minden LTL-osztályt NMFC-kódhoz rendelése az **NMFC-kódok** oldalon. További információ az [NMFC (National Motor Freight Classification) kódok](nmfc-codes.md) részben található.
- Rendeljen NMFC-kódot (és ennek megfelelően a termékhez társított LTL-kódot) minden termékhez a **Termékek** lapon.
- Az NMFC-kódhoz rendelt termékek LTL-osztályának pontos felmérése.
- Az egyes LTL-osztályok csomagolási követelményeinek meghatározása a nemzetközi LTL-szabványok ellenőrzésével. Így biztosíthatja, hogy a termékek megfelelő védelemben és biztonságban lesznek szállítva.
- Pontos szállítási becslések kérése az egyes termékek LTL-fuvarosztálya alapján.

Ez a témakör azt mutatja be, hogyan lehet LTL-osztályokat létrehozni a Microsoftban Dynamics 365 Supply Chain Management.

## <a name="create-an-ltl-class"></a>LTL-osztály létrehozása

LTL-osztály létrehozásához kövesse az alábbi lépéseket.

1. Tegye a következők egyikét:

    - Menjen a **Raktárkezelés \> Beállítás \> Készlet \> LTL-osztályok** elemre.
    - Ugorjon a **Szállításkezelés \> Beállítás \> Szállítmányozási standardok \> LTL-osztályok** lehetőségre.

2. Jelölje be a műveleti ablakban az **Új** lehetőséget az LTL-osztály létrehozásához. Majd, állítsa be a következő mezőket:

    - **LTL-osztály** – Adja meg a vállalat belső LTL-osztályazonosítóját (azonosító) az árucikk típusához. A legtöbb vállalat a nemzetközi szabványt használja. Ebben az esetben a mező értéke meg fog egyezni az **Osztály** mező értékével. Ha azonban a vállalat saját szabványt használ, adjon meg egy kódot, amely megfelel ennek a szabványnak.
    - **Név** – Adjon meg egy leíró nevet, amely segít Önnek és más felhasználóknak a megfelelő LTL-osztály kiválasztásában az egyes NMFC-kódokhoz.
    - **Osztály** – Adja meg az árucikk-típus nemzetközi szabványos LTL-osztályazonosítóját. Az itt beírott kódnak meg kell felelnie a hivatalos szabványnak.

## <a name="example-set-up-ltl-classes"></a>Példa: LTL-osztályok beállítása

A következő példa bemutatja, hogyan lehet két különböző LTL-osztályokat beállítani, amelyek különböző típusú termékekkel használhatók.

1. Menjen a **Raktárkezelés \> Beállítás \> Készlet \> LTL-osztályok** elemre.
1. A Műveleti ablaktáblán kattintson az **Új** elemre.
1. Az új sorban állítsa be a következő értékeket:

    - **LTL-osztály:** *92,5*
    - **Név:** *Számítógépek, monitorok, hűtők*
    - **Osztály:** *92,5*

1. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.
1. A Műveleti ablaktáblán kattintson az **Új** elemre.
1. Az új sorban állítsa be a következő értékeket:

    - **LTL-osztály:** *125*
    - **Név:** *Kis háztartási berendezések*
    - **Osztály:** *125*

1. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.

## <a name="additional-resources"></a>További erőforrások

- [NMFC (National Motor Freight Classification) kódok](nmfc-codes.md)
- [Fuvarlevél létrehozása](create-bill-of-lading.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
