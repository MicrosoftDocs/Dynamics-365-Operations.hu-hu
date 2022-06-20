---
title: Mértékegységek kezelése
description: Ez a témakör ismerteti, hogyan lehet definiálni egy mértékegységet, át lehet adni az egységet és annak leírását, valamint meg lehet adni a kapcsolódó egységek átváltási szabályait.
author: t-benebo
ms.date: 04/09/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResProductMaintainWorkspace, EcoResProductOpenCasesFormPart, UnitOfMeasure, UnitOfMeasureReportingTranslation, UnitOfMeasureTranslation, UnitOfMeasureConversion, UnitOfMeasureConversionEditOrCreate, UnitOfMeasureLookup, UnitOfMeasureCalculator, UnitOfMeasureWizard, UnitOfMeasureLookupTest
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8e2c21756b270ef7d914dc74a0cf61727953206a
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8863911"
---
# <a name="manage-units-of-measure"></a>Mértékegységek kezelése

[!include [banner](../../includes/banner.md)]

Ez a témakör ismerteti, hogyan lehet definiálni egy mértékegységet, át lehet adni az egységet és annak leírását, valamint meg lehet adni a kapcsolódó egységek átváltási szabályait.

## <a name="open-the-units-page"></a>Nyissa meg az Egységek lapot

A rendszerben elérhető mértékegységek létrehozásához és a velük való munkához kattintson a **Szervezet felügyelete \> Beállítás \> Mértékegységek\>** gombra.

A cikk további részei leírják, hogy mit lehet tenni az Egységek **lapon**.

## <a name="create-standard-units-and-conversions"></a>Szabványos mértékegységek és átváltások létrehozása

Ha a rendszer még nem tartalmazza a leggyakrabban használt mértékegységeket a metrikus rendszerhez és/vagy az USA-mértékegységrendszerhez (USCS), akkor az egységbeállítási varázsló segítségével gyorsan megismerkedhet az alapvető egységdefiníciókat és átváltásokat. A varázsló befejezéséhez válassza az **Egységlétrehozási varázsló** lehetőséget a munkaablakban, majd kövesse a képernyőn látható utasításokat.

## <a name="create-or-edit-a-unit-of-measure"></a>Mértékegység létrehozása vagy szerkesztése

A mértékegységek létrehozásához vagy szerkesztéséhez kövesse a következő lépéseket.

1. Tegye a következők egyikét:

    - Meglévő egység szerkesztéséhez jelölje ki azt a listaablakban.
    - Új egység létrehozásához válassza az **Új** lehetőséget a Művelet panelben.

1. A rekord fejlécen állítsa be a következő mezőket:

    - **Egység** – Adja meg a rendszer nyelvén az egységre való hivatkozási azonosítót vagy szimbólumot. Ez az azonosító vagy szimbólum általában az egység általános rövidítése, például az *ea* az egyes, a *cm* pedig a centiméter rövidítése.
    - **Leírás** – Írjon be egy jellemző nevet az egységnek a rendszer nyelvén. Ez a név általában az egység teljes neve, például *Egyes* vagy *Centiméter*.

1. Az **Általános** gyorslapon állítsa be a következő mezőket:<!-- KFM: confirm this:    - **Fixed unit assignment** and **Fixed unit** – These fields have an effect only if you're using the Microsoft Retail Essentials product. If the current unit can be mapped to one of the fixed units that are used by Retail Essentials, set the **Fixed unit assignment** option to *Yes*. Then select the fixed unit in the **Fixed unit** field. -->

    - **Egységosztály** – Válassza ki azt a tulajdonságot, amit az egység mér (például hossz, terület, tömeg vagy mennyiség).
    - **Mértékegységrendszer** – Válassza ki azt a mértékegységrendszert, amelyhez az egység tartozik (*Metrikus egységek* vagy *Egyesült államokbeli szokásos egységek*).
    - **Alapegység** – Akkor állítsa *Igen* értékre ezt a lehetőséget, ha az aktuális egységet használja az egységosztály alapegységeként. Ebben az esetben csak az alapegység és az egységosztályban található egyes további egységek közötti átváltási tényezőt kell megadni. A rendszer ezután átválthat az egységosztályban található összes egység között. Ezért könnyebb az átváltások beállítása.

        Ha például a gallon a *Térfogat* egységosztály alapegysége, akkor csak literből gallonba és pintből gallonba kell átváltási tényezőket beállítani. A rendszer ezután literből pintbe is tud átváltani.

        Egységosztályonként csak egy alapegység lehet.

    - **Rendszeregység** – Akkor állítsa *Igen* értékre ezt a lehetőséget, ha a becsült egységet használja az egységosztály összes meghatározatlan egységeként. Ha például egy mező, amibe eddig be lehetett írni mennyiséget nem teszi lehetővé az egység beállítását (ha a felhasználó nem választ ki egységet), akkor a rendszer azt az egységet használja, amely a *Mennyiség* egységosztály rendszeregységeként van beállítva. Egységosztályonként csak egy rendszeregység lehet.
    - **Tizedes pontosság** – Adja meg, hogy hány tizedesjegyre kell kerekíteni az aktuális egység számára megadott vagy az arra átalakítandó értékeket.

1. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.

## <a name="define-unit-translations"></a>Egység fordításainak meghatározása

A következő lépések követésével definiálhatja az azonosító vagy szimbólum fordítását, valamint a mértékegység leírását.

1. A fordítások létrehozásához használt egység létrehozása vagy kiválasztása.
1. Válassza a Művelet panelen az **Egységszövegek** lehetőséget.

    Megjelenik az **Egységszövegek** lap. Ezen a lapon meghatározhatja a kiválasztott egység azonosítójának vagy szimbólumának fordítását. Ezek a fordítások felhasználhatók a külső dokumentumokon a vevő- vagy szállítóspecifikus nyelveken.

1. A Műveleti ablaktáblán kattintson az **Új** elemre.
1. A **Nyelv** mezőben adja azt a nyelvet, amire le szeretné fordíttatni az egység azonosítóját vagy szimbólumát.
1. A **Szöveg** mezőbe írja be az egységazonosító vagy szimbólum fordítását a kiválasztott nyelven.
1. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.
1. Zárja be a lapot.
1. A **Művelet panelen** válassza az **Lefordított egységleírások** elemet.

    Megjelenik a **Lefordított egységleírások** lap. Ezen a lapon lehet a kiválasztott egység nyelvspecifikus leírását definiálni.

1. A Műveleti ablaktáblán kattintson az **Új** elemre.
1. A **Nyelv** mezőben adja azt a nyelvet, amire le szeretné fordíttatni az egység leírását.
1. A **Leírás** mezőbe írja be az egységleírás fordítását a kiválasztott nyelven.
1. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.
1. Zárja be a lapot.

## <a name="define-unit-conversion-rules"></a>Egység átváltási szabályok definiálása

A mértékegységek közötti átváltási szabályok meghatározásához kövesse ezeket a lépéseket.

1. Az átváltási szabályok mehatározásához használt egység létrehozása vagy kiválasztása.
1. Válassza a Művelet panelen az **Egységátváltás** lehetőséget.

    Megjelenik a **Mértékegység-átváltások** oldal. Arra használhatja ezt az oldalt, hogy szabályokat adjon meg a kiválasztott egységek átváltásához más egységekről és egységekre az egységosztályban.

1. A következő lapok közül választhat a beállítani kívánt átváltás típusától függően:

    - **Standard átváltások** – Az összes termékre vonatkozó normál átváltási szabályok beállítása.
    - **Osztályon belüli átváltások** – Termékspecifikus átváltási szabályok beállítása az ugyanabban az egységosztályban található egységekre.
    - **Osztályok közötti átváltások** – Termékspecifikus átváltási szabályok beállítása az egységosztályok között.

1. Tegye a következők egyikét:

    - Új átváltás létrehozásához válassza az **Új** lehetőséget az eszközsávban.
    - Meglévő átváltás szerkesztéséhez jelölje ki az átváltást a rácson, majd válassza az eszköztár **Szerkesztés** lehetőségét.

1. A legördülő párbeszédpanelen a következő mezőket állítsa be:

    - **Termék** – Válassza ki azt a terméket, amelyre az átváltás vonatkozik. Ez a mező csak osztályon belüli és osztályközi átalakítások esetén érhető el.
    - **Receptúraelrendezés** – Hagyja ezt a mezőt *Egyszerű* beállításban, és adjon meg egy egyszerű átváltási tényezőt. Állítsa *Speciális* értékre egy összetettebb egyenlet beállításhoz. A speciális egyenletek formátuma az egységosztálytól függően eltérő lehet.
    - **Kezdő egység** – Ez a mező a kiválasztott egységet mutatja. Általában nem szabad módosítani az értéket. (Ha módosítja az értéket, meg kell nyitnia az **Egységátváltási** lapot a kiválasztott egységhez, hogy megtekinthesse az új átváltást a mentés után.)
    - **Cél egység** – Válassza ki azt az egységet, amelybe át kell váltani.
    - **Kerekítés** – Válassza ki, hogyan legyenek kerekítve a törtek a kiválasztott egység **Tizedes pontosság** értéke alapján (*Legközelebbi*, *Fel* és *Le*).
    - **Átváltási képlet** – A legördülő párbeszédpanel tetején található további mezők használatával megadhatja a két egység közötti átváltási képletet. A választható mezők a kiválasztott egységosztálytól és receptúraelrendezéstől függően eltérőek.

1. Válassza ki az **OK** lehetőséget.
1. Zárja be a lapot.

> [!TIP]
> Termékváltozatonkénti egységátváltásokat is be lehet állítani. További információért lásd: [Mértékegység-átváltás termékváltozatonként](../uom-conversion-per-product-variant.md).

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
