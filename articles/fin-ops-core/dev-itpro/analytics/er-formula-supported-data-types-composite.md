---
title: Támogatott összetett adattípusok az elektronikus jelentési képletekben
description: Ez a cikk az elektronikus jelentési (ER) képletekben támogatott összetett adattípusokkal kapcsolatban tartalmaz tájékoztatást.
author: NickSelin
ms.date: 06/02/2021
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: dc3fbe695d79eb0ec9796d471c4d2bb0bb7ab99d
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8869315"
---
# <a name="supported-composite-data-types-for-electronic-reporting-formulas"></a>Támogatott összetett adattípusok az elektronikus jelentési képletekben

[!include [banner](../includes/banner.md)]

Ez a cikk az [elektronikus jelentési (ER) kifejezésekben támogatott összetett adattípusokkal kapcsolatban](general-electronic-reporting.md) tartalmaz tájékoztatást. Az összetett adattípusok az [osztály](#class), [tároló](#container), [rekord](#record), [rekordlista](#record-list) és [objektum](#object).

## <a name="class"></a><a name="class"></a>Osztály

Az *osztály* adattípus egy nyilvános alkalmazásosztályra vonatkozik. Az ER-ben egy olyan [*rekordként*](#record) van ábrázolva, amely külön mezőt tartalmaz a hivatkozott osztály összes nyilvános metódusa számára. Ha a metódus hívása paraméterezett, meg kell adnia a metódus hívásához konfigurált ER-kifejezésben a megfelelő típusú szükséges argumentumokat is.

Az ER-leképezésekben és a formátumösszetevőkben **hozzáadhatja** az *adatforrásként megjelenő, osztálytípusnak megfelelő értéket eredményül adó Osztály adatforrást*. Ez az adatforrás az osztály nyilvános metódusait teszi elérhetővé, amelyek futásidőben hívhatóak.

> [!NOTE]
> Csak értékeket visszaadó metódusok hívhatóak meg ER-kifejezésekből.
>
> Csak nulla és nyolc közötti argumentummal rendelkező metódusokat lehet az ER-kifejezésből meghívni.

Az *osztály* alapértelmezett értéke **null**.

A következő ábra bemutatja, hogy a **Rendszerinformáció(xInfo)** adatforrást az **Osztály** típusból, hogyan van hozzáadva, hogy az **xInfo** alkalmazásosztály példányát létrehozza, és meghívja a **productName()** metódusát, hogy megkapja az aktuális alkalmazás nevét. Futási időben bekéri a rendszer az aktuális alkalmazás nevét az ER-adatmodell **Software name(SoftwareName)** mezőjéhez beállított `xInfo.productName` kötés végrehajtásával. Ez a kötés a jelenlegi modellleképezésben **system information(xInfo)** adatforrásként ábrázolt **xInfo** alkalmazásosztály `productName()`-metódusát hívja meg.

[![Az Osztály-adatforrás konfigurálása az ER modell-leképezés tervezőben.](./media/er-formula-supported-data-types-composite-class1.gif)](./media/er-formula-supported-data-types-composite-class1.gif)

A következő ábra bemutatja, hogy hogyan van beállítva az ER-formátum, hogy a megadott alkalmazásnevet a generált dokumentumokba helyezze. A használt adatmodell **Szoftvernév(SoftwareName)** mezőjét az ER-formátum **softwareUsed** XML eleme alá beágyazott **Sztring** összetevőhöz kötötték. Tehát az aktuális alkalmazás neve futásidőben kerül a létrehozott dokumentum XML-formátumú **softwareUsed** XML eleméhez.

[![Elektronikus kimenő dokumentum szerkezetének konfigurálása az ER formátumtervezőben.](./media/er-formula-supported-data-types-composite-class2.png)](./media/er-formula-supported-data-types-composite-class2.png)

## <a name="container"></a><a name="container"></a>Tároló

A *tároló* adattípus bináris tartalmat hordoz. A *tároló* értékek segítségével konkrét adatokat lehet átadni tárolóból a generált dokumentumoknak. Az ER keretrendszerben ez az adattípus gyakran használatos médiatartalom, például vállalati embléma generált dokumentumokba való beágyazása során.

> [!NOTE]
> Bár minden médiaelem ábrázolható *tároló* értékként, nem minden *tároló* érték képvisel médiaelemet. Ezért ha úgy konfigurálja az ER-formátumot, hogy egy *tároló* használatával ágyazza a képet a létrehozott dokumentumokba, de a hivatkozott *tároló* nem ad vissza médiatartalmat, a következő példához hasonló kivétel merülhet fel: "Hiba történt a kód végrehajtásakor: Bináris (objektum), érvénytelen paraméterekkel hívott constructFromContainer metódus."

Az *tároló* alapértelmezett értéke **null**.

A következő ábra bemutatja, hogy a **Tároló** típusú *Bitkép(kép)* mező hogyan van kötve az adatmodell **Embléma** mezőjéhez, ami **Tároló** típusú az **Értékesítési számla** modell-leképezésében. Ez a kötés teszi elérhetővé a vállalati emblémát bármely, a **SalesInvoice** gyökérdefinícióhoz készült ER-formátum számára, amely ezt a modell-leképezést használja futásidőben.

[![Tároló típusú mező kötése az ER modell-leképezés-tervezőben.](./media/er-formula-supported-data-types-composite-container.png)](./media/er-formula-supported-data-types-composite-container.png)

## <a name="record"></a><a name="record"></a>Rögzítés

A *rekord* elnevezett mezők gyűjteménye, amelyek mindegyikéhez egy [egyszerű](er-formula-supported-data-types-primitive.md) adattípus vagy egy összetett adattípus van társítva. Általában egy *rekord* egy rekordot képvisel egy rekordlistából. Ebben az esetben minden elem egyedi mezőket, metódusokat és kapcsolatokat képvisel.

Az *rekord* alapértelmezett értéke **üres**.

> [!NOTE]
> Ha üres *rekord* mezőjének értékét kéri le, akkor a program a megfelelő adattípus alapértelmezett értékét adja vissza.

A *rekord* értéke a következő függvényekkel kérdezhető le:

- [FIRST](er-functions-list-first.md)
- [FIRSTORNULL](er-functions-list-firstornull.md)
- [EMPTYRECORD](er-functions-record-emptyrecord.md)
- [NULLCONTAINER](er-functions-record-nullcontainer.md)

A *rekord* értékek átalakításával kapcsolatos további tudnivalókat lásd az [ER-függvények listája a lista kategóriában](er-functions-category-list.md) részben.

## <a name="record-list"></a><a name="record-list"></a>Rekordlista

A *rekordlista* a *rekord* típusba sorolt cikkek listáját tartalmazza. Általában egy *rekordlista* használatos egy adatbázistáblából beolvasásra használt rekordok listájának megjelenítésére.

Alapértelmezés szerint a *rekordlista* rekordjai egymást követő sorrendben lesznek elérve. Egy adott rekord eléréséhez használhatja az [INDEX](er-functions-list-index.md) függvényt és megadhatja az *egész szám* indexet.

Az *rekordlista* alapértelmezett értéke **üres**. Az [ISEMPTY](er-functions-list-isempty.md) függvénnyel kiértékelheti, hogy üres-e egy *rekordlista*.

> [!NOTE]
> Ha egy *rekordlista* üres, akkor a benne található *rekord* mezőértékének lekérésére irányuló kísérlet kivételt ad futásidőben. Ha meg szeretné tudni, hogyan lehet megakadályozni az ilyen típusú futásidejű kivételeket, olvassa el az [Üres listaesetek megfontolása](er-components-inspections.md#i9) részt.

A *rekordlista* értéke a következő függvényekkel kérdezhető le:

- [ALLITEMS](er-functions-list-allitems.md)
- [ALLITEMSQUERY](er-functions-list-allitemsquery.md)
- [EMPTYLIST](er-functions-list-emptylist.md)
- [LIST](er-functions-list-list.md)
- [LISTDISTINCT](er-functions-list-listdistinct.md)

A *rekordlista* értékek átalakításával kapcsolatos további tudnivalókat lásd az [ER-függvények listája a lista kategóriában](er-functions-category-list.md) részben. A *rekordlista* elemek bevezetésével, az alkalmazás adatokkal való feltöltésével, majd ezen adatok felhasználásával kapcsolatosan üzleti dokumentumokhoz lásd: [Új ER-megoldás megtervezése egyéni jelentés nyomtatásához](er-quick-start1-new-solution.md).

## <a name="object"></a><a name="object"></a>Objektum

Az *objektum* egy *osztály* állapottal rendelkező példányára vonatkozik. Egy *objektum* általában forráskódban van kezdeményezve. Ezt követően át lesz adva egy ER modell-leképezésnek, és részletezi a végrehajtási környezetet.

Egy *objektum* alapértelmezett értéke **null**.

A következő ábra bemutatja, hogy az **Objektum** típus *ReportDataContract* adatforrása hogyan lesz hozzáadva a létrehozott számla forráskód-adatoknak a **Projektszámla** modell-leképzéshez való átküldéshez. Például a számlapéldány szövege a végrehajtási környezet részeként lesz átadva. Ezt a szöveget futásidőben, a forráskódból veszi a rendszer az ER adatmodell **Megjegyzés** mezőjéhez beállított `ReportDataContract.parmInvoiceInstanceText` kötés végrehajtásával. Ez a kötés a jelenlegi modellleképezésben **ReportDataContract** adatforrásként ábrázolt **PSAProjInvoiceContract** alkalmazásosztály `parmInvoiceInstanceText()`-metódusát hívja meg.

[![Az Objektum adatforrás konfigurálása az ER modell-leképezés tervezőben.](./media/er-formula-supported-data-types-composite-object.gif)](./media/er-formula-supported-data-types-composite-object.gif)

A végrehajtási környezet forráskódról a futó ER-megoldásra való áthűtési részleteiről az [Alkalmazás-összetevők fejlesztése a megtervezett jelentés meghívásához](er-quick-start1-new-solution.md#DevelopCustomCode) rész tartalmaz további tudnivalókat.

## <a name="additional-resources"></a>További erőforrások

- [Elektronikus jelentések áttekintése](general-electronic-reporting.md)
- [Elektronikus jelentéskészítés képletének nyelve](er-formula-language.md)
- [Támogatott egyszerű adattípusok](er-formula-supported-data-types-primitive.md)
