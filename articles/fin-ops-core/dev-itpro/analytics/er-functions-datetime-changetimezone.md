---
title: CHANGETIMEZONE ER-függvény
description: A témakör tájékoztatást nyújt a CHANGETIMEZONE Elektronikus jelentéskészítési (ER) függvény használatának módjáról.
author: NickSelin
ms.date: 09/09/2021
ms.prod: ''
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 58771
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: AX 10.0.23
ms.openlocfilehash: 48e96cfbc19503daf6a20363c4520c765f11a249
ms.sourcegitcommit: 9e8d7536de7e1f01a3a707589f5cd8ca478d657b
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/18/2021
ms.locfileid: "7647937"
---
# <a name="changetimezone-er-function"></a>CHANGETIMEZONE ER-függvény

[!include [banner](../includes/banner.md)]

A `CHANGETIMEZONE` függvény egy *[DateTime](er-formula-supported-data-types-primitive.md#datetime)* értéket ad eredményül az Egyezményes Koordinált Világidő (Greenwichi középidő \[GMT\]) szerint amely át lett váltva az egyik időzóna adott dátum/idő értékéről egy másik időzóna dátum/idő értékére.

## <a name="syntax"></a>Szintaxis

```vb
CHANGETIMEZONE (datetime, base time zone, target time zone)
```

## <a name="arguments"></a>Argumentumok

`datetime`: *DateTime*

Az egyezményes világidő időzónában az a dátum-idő érték, amely az átalakítás dátumát/idejét jelzi.

`base time zone`: *[Sztring](er-formula-supported-data-types-primitive.md#string)*

Annak az időzónának a neve, amelybe az átalakítás előtt egy adott dátum/idő érték el van tolva.

`target time zone`: *Karakterlánc*

Annak az időzónának a neve, amelybe az átváltott dátum/idő érték el van tolva az átváltás során.

## <a name="return-values"></a>Visszatérési értékek

*DateTime*

Az eredményül kapott dátum/idő az egyezményes világidő időzónában.

## <a name="usage-notes"></a>Használati megjegyzések

A forrás- és a cél-időzónák megadásához használhatja az [Internet Assigned Numbers Authority (IANA)](https://www.iana.org/) által [biztosított](https://data.iana.org/time-zones/releases/) időzónaneveket, amelyeket a Microsoft Windows [támogat](/windows-hardware/manufacture/desktop/default-time-zones).

Futáskor a rendszer az "Időzóna '\<time zone name\>' nem létezik" kivételt adja, ha a megadott név nem található az IANA listában vagy a Windows beállításjegyzékében.

Olyan időzónák esetén, ahol a téli időszámítást figyelembe van venni, a konverzió az egyezményes világidő óraátállítását figyelembe veszi. Az óraátállítással kapcsolatos legújabb információkat használja a rendszer a konverzió során.

## <a name="example-1"></a>1. példa

Ebben a példában a Windows időzóna-nevei használatosak.

Konfigurálja a **DSX** adatforrást a **Számított mező** típusból. A következő kifejezést tartalmazza.

```vb
CONCATENATE(
    DATETIMEFORMAT( DSY, "O"), 
    " -> ", 
    DATETIMEFORMAT( CHANGETIMEZONE(DSY, "E. Europe Standard Time", "Hawaiian Standard Time"), "O")
)
```

Ha a **Számított mező** típus **DSY** adatforrásának kifejezését úgy konfigurálja, hogy `DATETIMEVALUE ("01-Jun-2021 12:55:00", "dd-MMM-yyyy HH:mm:ss", "EN")` a **DSX** adatforrás a **2021-06-01T12:55:00.0000000+00:00 -> 2021-05-31T23:55:00.0000000+00:00** szöveget adja eredményül. Ez a szöveg azt mutatja, hogy a június 1-én megadott két időzóna közötti időkülönbség több mint 24 óra. Emiatt az átváltott dátum-idő érték egy nappal korábbi a megadott dátum-idő értéknél egy nappal korábbi, mivel az alap időzóna megelőzi a cél időzónát.

Ha a **Számított mező** típus **DSY** adatforrásának kifejezését úgy konfigurálja, hogy `DATETIMEVALUE ("01-Dec-2021 12:55:00", "dd-MMM-yyyy HH:mm:ss", "EN")` a **DSX** adatforrás a **2021-12-01T12:55:00.0000000+00:00 -> 2021-12-01T00:55:00.0000000+00:00** szöveget adja eredményül. Ez a szöveg azt mutatja, hogy a december 1-én megadott két időzóna közötti időkülönbség kevesebb mint 24 óra. Ezért az átváltott dátum/idő érték megegyezik a megadott dátum/idő értékkel.

> [!NOTE]
> Ugyanez a kifejezés eltérő eltérést ad vissza ugyanannak az időzónáknak a megadott és átváltott dátum/idő értékei között, mivel a megadott időzónákhoz megadott időzónáknál egy eltérő, egyezményes világidő szerinti téli időszámítási eltérést figyel meg a program egy adott dátumon/időpontban.

## <a name="example-2"></a>2. példa

Ebben a példában a IANA időzóna-nevei használatosak.

Konfigurálja a **DSX** adatforrást a **Számított mező** típusból. A következő kifejezést tartalmazza.

```vb
CONCATENATE(
    DATETIMEFORMAT( DSY, "O"), 
    " -> ", 
    DATETIMEFORMAT( CHANGETIMEZONE(DSY, "Europe/Athens", "US/Hawaii"), "O")
)
```

Ha a **Számított mező** típus **DSY** adatforrásának kifejezését úgy konfigurálja, hogy `DATETIMEVALUE ("01-Jun-2021 12:55:00", "dd-MMM-yyyy HH:mm:ss", "EN")` a **DSX** adatforrás a **2021-06-01T12:55:00.0000000+00:00 -> 2021-05-31T23:55:00.0000000+00:00** szöveget adja eredményül. Ez a szöveg azt mutatja, hogy a június 1-én megadott két időzóna közötti időkülönbség több mint 24 óra. Emiatt az átváltott dátum-idő érték egy nappal korábbi a megadott dátum-idő értéknél egy nappal korábbi, mivel az alap időzóna megelőzi a cél időzónát.

Ha a **Számított mező** típus **DSY** adatforrásának kifejezését úgy konfigurálja, hogy `DATETIMEVALUE ("01-Dec-2021 12:55:00", "dd-MMM-yyyy HH:mm:ss", "EN")` a **DSX** adatforrás a **2021-12-01T12:55:00.0000000+00:00 -> 2021-12-01T00:55:00.0000000+00:00** szöveget adja eredményül. Ez a szöveg azt mutatja, hogy a december 1-én megadott két időzóna közötti időkülönbség kevesebb mint 24 óra. Ezért az átváltott dátum/idő érték megegyezik a megadott dátum/idő értékkel.

## <a name="example-3"></a>3. példa

Konfigurálja a **DSX** adatforrást a **Számított mező** típusból. A következő kifejezést tartalmazza.

```vb
CONCATENATE(
    DATETIMEFORMAT( DSY, "O"), 
    " -> ", 
    DATETIMEFORMAT( CHANGETIMEZONE(DSY, "US/Hawaii", "Europe/Athens"), "O")
)
```

Ha a **Számított mező** típus **DSY** adatforrásának kifejezését úgy konfigurálja, hogy `DATETIMEVALUE ("01-Jun-2021 12:55:00", "dd-MMM-yyyy HH:mm:ss", "EN")` a **DSX** adatforrás a **2021-06-01T12:55:00.0000000+00:00 -> 2021-06-02T01:55:00.0000000+00:00'** szöveget adja eredményül. Ez a szöveg azt mutatja, hogy a június 1-én megadott két időzóna közötti időkülönbség több mint 24 óra. Emiatt az átváltott dátum-idő érték egy nappal későbbi a megadott dátum-idő értéknél egy nappal korábbi, mivel a cél időzóna megelőzi az alap időzónát.

## <a name="example-4"></a>4. példa

Előfordulhat, hogy egy külső forrásból olyan dátum-/időbélyegzőt kap, amely nem tartalmaz időzóna-információkat. Ugyanakkor lehet, hogy tudja, hogy milyen időzónában működik a forrás. A dátum-/időbélyegzőt például **01/12/2021 12:55:00** egy Spanyolországban működő szolgáltatástól. A dátum-/időérték adatbázisba történő megfelelő mentéshez a következő átváltást kell végrehajtani:

- Állítsa be a **Számított mező** típusú **DSY** adatforrást úgy, hogy a dátumot/időbélyeget szövegből egyezményes világidő formátumra konvertálja.

    `DATETIMEVALUE ("01/12/2021 12:55:00", "dd/MM/yyyy HH:mm:ss", "ES")`

- Úgy állítsa be a **Számított mező** típusú **DSX** adatforrást, hogy az egyezményes világidő átalakított dátum/idő értékét eltolja a külső forrás dátum/idő értékének megfelelően.

    `CHANGETIMEZONE(DSY, "Romance Standard Time", "GMT Standard Time")`

> [!NOTE]
> Ha a `CHANGETIMEZONE` függvényt dátum-/időátváltáshoz használja, ne feledje, hogy a rendszer a dátum-/időértékeket az adatbázisban tárolja az egyezményes világ időidőzónában használt értékként. Mielőtt ez az érték megjeleníthető lenne az alkalmazásoldalakon át lesz alakítva. Az átalakítás azt az időzónát veszi figyelembe, amely preferált zónaként van [beállítva](../../fin-ops/organization-administration/tasks/set-users-preferred-time-zone.md) az aktuálisan bejelentkezett alkalmazásfelhasználó számára.

## <a name="additional-resources"></a>További erőforrások

[Dátum- és időfüggvények](er-functions-category-datetime.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
