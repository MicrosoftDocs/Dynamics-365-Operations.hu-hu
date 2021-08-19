---
title: Támogatott egyszerű adattípusok az elektronikus jelentési képletekben
description: A témakör tájékoztatást nyújt az Elektronikus jelentéskészítésben (ER) képleteiben támogatott egyszerű adattípusokról.
author: NickSelin
ms.date: 06/02/2021
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 72c372a4d9b6af337731ff0bbd750b3b58f27bb79cb3813a0b5e4f79707d9f5c
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6730607"
---
# <a name="supported-primitive-data-types-for-electronic-reporting-formulas"></a>Támogatott egyszerű adattípusok az elektronikus jelentési képletekben

[!include [banner](../includes/banner.md)]

A témakör tájékoztatást nyújt az [Elektronikus jelentéskészítésben (ER)](general-electronic-reporting.md) képleteiben támogatott egyszerű adattípusokról. Íme az egyszerű adattípusok listája:

- [logikai](#boolean)
- [dátum](#date)
- [datetime](#datetime)
- [felsorolás](#enumeration)
- [guid](#guid)
- [egész szám](#integer)
- [int64](#int64)
- [valós](#real)
- [sztring](#string)

## <a name="boolean"></a><a name="boolean"></a>Logikai

A *logikai* egyszerű adattípus olyan értéket tartalmaz, amely *igaz* vagy *hamis* értékű. A foglalt kulcsszavakat – **Igaz** és **Hamis** – használhatja ott, ahol *logikai* kifejezésre van szükség. Az alapértelmezett érték a *hamis*.

A *logikai érték* belső ábrázolása egy *egész szám*. A 0 (nulla) *egész* érték kiértékelése *hamis*, az összes többi *egész* érték kiértékelése *igaz*. Ha olyan konfigurált kifejezést [érvényesít](general-electronic-reporting-formula-designer.md#TestFormula), amely *logikai* értéket ad vissza az [ER képlettervezőben](er-advanced-formula-editor.md), a teszteredmények ablaktáblája *0* (nulla) értéket ad meg, ha a kifejezés eredménye *hamis*. Ellenkező esetben a teszteredmény panelen az *1* látható.

A *logikai érték* nem rendelkezik implicit átalakításokkal. Ugyanakkor a [TEXT](er-functions-text-text.md) függvényt használhatja arra, hogy explicit módon *sztringgé* alakítsa a *logikai* értéket:

- A *hamis* érték konvertálva van a **Hamis** szöveges karakterláncra.
- Az *igaz* érték konvertálva van **Igaz** szöveges karakterláncra.

> [!NOTE]
> Ez az átalakítás nem függ a megadott nyelvtől és kulturális [környezettől](er-design-multilingual-reports.md).

Az összehasonlítási [operátorok](er-formula-language.md#Operators) az egyetlen olyan operátortípus, amely a *logikai* adattípushoz használható. A következő operátorok használhatók két *logikai* érték összehasonlítására: \<\> és =.

## <a name="date"></a><a name="date"></a>Dátum

A *dátum* egyszerű adattípus az évet, a hónapot és a napot tartalmazza. A dátumok a következő függvényekkel kezdeményezhetőek:

- [DATEVALUE](er-functions-datetime-datevalue.md)
- [NULLDATE](er-functions-datetime-nulldate.md)
- [SESSIONTODAY](er-functions-datetime-sessiontoday.md)
- [TODAY](er-functions-datetime-today.md)

A *dátum* adattípus 1900. január 1. és 2154. december 31. közötti dátumokat képes tárolni. Az alapértelmezett érték **null**, és a belső ábrázolása az 1900. január 1. dátum.

A *dátum* érték nem rendelkezik implicit átalakításokkal. Használhatja azonban a következő explicit átváltási függvényeket:

- [DATEFORMAT](er-functions-datetime-dateformat.md)
- [DATETODATETIME](er-functions-datetime-datetodatetime.md)
- [TEXT](er-functions-text-text.md)

Az [ADDDAYS](er-functions-datetime-adddays.md) függvénnyel napokat adhat hozzá a dátumokhoz, és kivonhat napokat. Ily módon a megadott számú nappal a előbbre és későbbre mozgathatja át a dátumot. A [DAYS](er-functions-datetime-days.md) függvénnyel kivonhatók a dátumok a másikból, és kiszámítható a különbség a napban. A *dátum* értékek átalakításával kapcsolatos további tudnivalókat lásd az [ER-függvények listája a Dátum és idő kategóriában](er-functions-category-datetime.md) részben.

Az összehasonlítási [operátorok](er-formula-language.md#Operators) az egyetlen olyan operátortípus, amely a *dátum* adattípushoz használható. A következő operátorok használhatók két *dátum* érték összehasonlítására: \<\>, \<, \<=, =, \> és \>=.

## <a name="datetime"></a><a name="datetime"></a>Dátum és idő

A *datetime* egyszerű adattípus egyesíti a *dátum* típust és az éjfél óta eltelt időt képviselő értéket. Az idő órában, percben, másodpercben és másodpercek törtjében van kifejezve. A *datetime* érték az időzónára vonatkozó információkat is tartalmaz.

A *datetime* adattípus dátumokat tartalmazhat 1900. január 1. (1900-01-01T00:00:00.0000000+00:00 oda vissza [formátumban](/dotnet/standard/base-types/standard-date-and-time-format-strings)) és 2154. december 31. (2154/12/31T11:59:59.9999999+00:00 oda vissza formátumban) között. A legkisebb időegység egy *datetime* esetében a másodperc egy tízmilliomoda.

> [!NOTE]
> Ha az **óó** [formátumot](/dotnet/standard/base-types/standard-date-and-time-format-strings) használja az órákhoz, akkor a 12:59:59:9999999-nél nagyobb időértékek nem értelmezhetők érvényes időként.
>
> Ha az **ÓÓ** formátumot használja az órákhoz, akkor a 23:59:59:9999999-nél nagyobb időértékek nem értelmezhetők érvényes időként.

Az alapértelmezett érték **null**, és a belső megjelenítése az 1900. január 1. (1900-01-01T00:00:00.0000000+00:00 dátum a oda-vissza formátumban).

A datetime értékek a következő függvényekkel kezdeményezhetőek:

- [DATETIMEVALUE](er-functions-datetime-datetimevalue.md)
- [NULNULLDATETIMELDATE](er-functions-datetime-nulldatetime.md)
- [SESSIONNOW](er-functions-datetime-sessionnow.md)
- [NOW](er-functions-datetime-now.md)

A *datetime* érték nem rendelkezik implicit átalakításokkal. Használhatja azonban a következő explicit átváltási függvényeket:

- [DATETIMEFORMAT](er-functions-datetime-datetimeformat.md)
- [TEXT](er-functions-text-text.md)

A *datetime* értékek átalakításával kapcsolatos további tudnivalókat lásd az [ER-függvények listája a Dátum és idő kategóriában](er-functions-category-datetime.md) részben.

Az összehasonlítási [operátorok](er-formula-language.md#Operators) az egyetlen olyan operátortípus, amely a *datetime* adattípushoz használható. A következő operátorok használhatók két *datetime* érték összehasonlítására: \<\>, \<, \<=, =, \> és \>=.

## <a name="enumeration"></a><a name="enumeration"></a>Felsorolás

A *felsorolás* egyszerű adattípus szöveges konstansok listája. Az alkalmazás [forráskódja](../dev-ref/xpp-data-primitive.md#enum) által meghatározott felsorolásokat használhatja. A saját enumerációkat az ER [adatmodellben](general-electronic-reporting.md#data-model-and-model-mapping-components) és az ER [formátum](general-electronic-reporting.md#FormatComponentOutbound) összetevőkben is bevezetheti.

Az alkalmazás *enumerációja* bármely ER modellleképezés és ER-formátum kifejezésében használható.

A következő ábra bemutatja, hogyan lehet hozzáadni a **CustVendCorrectiveReasonCode** modell enumerációt a szerkeszthető ER adatmodellhez.

[![Modell enumerációjának konfigurálása az ER adatmodell-tervezőjében.](./media/er-formula-supported-data-types-primitive-enum1.gif)](./media/er-formula-supported-data-types-primitive-enum1.gif)

A modell *enumerációja* bármely olyan ER modellleképezés és ER-formátum kifejezésében használható, amely egy olyan adatmodell alapján jött létre, amelyben az *enumerációt* bevezették.

A következő ábra azt mutatja be, hogyan lehet hozzáadni a **Fordított Natura alkategóriák** fomátumfelsorolást a szerkeszthető ER-formátumhoz.

[![Formátum enumerációjának konfigurálása az ER formátumtervezőjében.](./media/er-formula-supported-data-types-primitive-enum2.gif)](./media/er-formula-supported-data-types-primitive-enum2.gif)

Formátum *enumeráció* csak abban az ER-formátumban használható, amelyben az *enumerációt* bevezették.

Ahhoz, hogy egy konfigurált ER-összetevőt konstansként vagy olyan értékként hozzon be a konfigurált ER-összetevőre, amely a párbeszédpanelen futás közben meghatározott ER-megoldást futtatja, a megfelelő ER-adatforrásokat kell használnia.

- Az alkalmazás enumerációi a **Dynamics 365 for Operations \ Felsorolás** és **Általános \ Felhasználói beviteli paraméterek** adatforrások használatával érhetők el. A következő ábra bemutatja, hogyan lehet hozzáadni a Szerkeszthető ER formátumhoz azokat az **appenumNoYes** és **uipNoYes** adatforrásokat, amelyek a **NoYes** alkalmazásenumerációra hivatkoznak.

    [![Alkalmazás enumerációs adatforrások hozzáadása az ER-formátumtervezőben.](./media/er-formula-supported-data-types-primitive-enum3a.gif)](./media/er-formula-supported-data-types-primitive-enum3a.gif)

- Az adatmodell enumerációi az **Adatmodell \ Felsorolás** és **Adatmodell \ Enumerációs felhasználói beviteli paraméterek** adatforrások használatával érhetők el. A következő ábra bemutatja, hogyan lehet hozzáadni a Szerkeszthető ER formátumhoz a **CustVendCorrectiveReasonCode** adatforrást, amely a **CustVendCorrectiveReasonCode** adatmodell enumerációra hivatkozik.

    [![Modellenumerációs adatforrások hozzáadása az ER-formátumtervezőben.](./media/er-formula-supported-data-types-primitive-enum3b.gif)](./media/er-formula-supported-data-types-primitive-enum3b.gif)

- A Formátum-enumerációk a **Formátum \ Enumeráció** és **Formátum \ Formátum felhasználói bemeneti paraméterek** adatforrások használatával érhetők el. A következő ábra bemutatja, hogyan lehet hozzáadni a Szerkeszthető ER formátumhoz a **NaturaReverseCharge** adatforrást, amely a **Natura fordított áfa alkategóriák** formátumenumerációra hivatkozik.

    [![Formátumenumerációs adatforrások hozzáadása az ER-formátumtervezőben.](./media/er-formula-supported-data-types-primitive-enum3c.gif)](./media/er-formula-supported-data-types-primitive-enum3c.gif)

Az *enumeráció* nem rendelkezik implicit átalakításokkal. A [TEXT](er-functions-text-text.md) átváltási függvénnyel azonban a *felsorolás* szöveg karakterlánccá alakítható. Ez az átalakítás nem nyelvfüggő. A *felsorolás* értéknek a megfelelő nyelvspecifikus címkékhez való társításának a elsajátításáról a [LISTOFFIELDS](er-functions-list-listoffields.md) és a [GETENUMVALUEBYNAME](er-functions-text-getenumvaluebyname.md) függvényekkel kapcsolatos példákban olvashat bővebben.

Az összehasonlítási [operátorok](er-formula-language.md#Operators) az egyetlen olyan operátortípus, amely a *felsorolás* adattípushoz használható. A következő operátorok használhatók két *felsorolás* érték összehasonlítására: \<\> és =.

## <a name="guid"></a><a name="guid"></a>Guid

A *guid* egyszerű adattípus egy globálisan egyedi azonosító (GUID) értéket tartalmaz. A GUID egy olyan érték, amely minden számítógépnél és hálózatnál használható, ahol egyedi azonosító szükséges. Nem valószínű, hogy a szám ismétlődik. Egy érvényes GUID megfelel a következő specifikációknak:

- 32 hexadecimális számjegynek kell lennie.
- Ezenkívül négy kötőjel karakternek kell lennie, amelyek a következő helyeken vannak beágyazva: 8-4-4-4-12.
- A karakterlánc elején és végén opcionális kapcsos zárójelek \{\} is hozzáadhatóak. Például a **\{2CDB0FE7-D7B3-4938-A0F0-FE28FB8FE212\}** és a **2CDB0FE7-D7B3-4938-A0F0-FE28FB8FE212** is érvényes GUID-sztringek.
- Így összesen 36 vagy 38 karakternek kell lennie attól függően, hogy hozzáadnak-e kapcsos zárójeleket.
- A hexadecimális számjegyként használt betűk nagybetűsek (A–F), kisbetűsek (a–f) vagy vegyesek is lehet.

A következő explicit átváltási függvények használhatók:

- [GUIDVALUE](er-functions-text-guidvalue.md)
- [TEXT](er-functions-text-text.md)

Az összehasonlítási [operátorok](er-formula-language.md#Operators) az egyetlen olyan operátortípus, amely a *guid* adattípushoz használható. A következő operátorok használhatók két *guid* érték összehasonlítására: \<\> és =.

## <a name="integer"></a><a name="integer"></a>Egész

Az *egész szám* egyszerű adattípus olyan számot jelent, amely tizedesjegyeket nem tartalmaz. Az egészek a vezérlőváltozókként használhatók ismétlődő utasításokban vagy rekordlisták indexeiként.

Az *egész szám* konstansérték az egész szám, ahogy az közvetlenül az ER [kifejezésbe](general-electronic-reporting-formula-designer.md#formula-designer-overview) (képlet) van megadva, például **12345**. Egy *egész szám* 32 bit széles. Az alapértelmezett érték **0**, a belső ábrázolása pedig egy hosszú szám. A program automatikusan *valós* számmá alakítja az *egész számot*.

Mindemelett a következő explicit átváltási függvények használhatók:

- [INTVALUE](er-functions-conversion-intvalue.md)
- [NUMBERFORMAT](er-functions-text-numberformat.md)
- [TEXT](er-functions-text-text.md)

Az *egész szám* tartománya \[-2 147 483 647 : 2 147 483 647\]. A tartomány összes egésze száma használható konstansértékként.

Az összes összehasonlító és matematikai [operátor](er-formula-language.md#Operators) használható az *egész szám* adattípussal.

## <a name="int64"></a><a name="int64"></a>Int64

Az *int64* egyszerű adattípus olyan számot jelent, amely tizedesjegyeket nem tartalmaz. Az *int64* értékek a vezérlőváltozókként használhatók ismétlődő utasításokban vagy rekordazonosítókban.

Egy *int64* 64 bit széles. Az alapértelmezett érték **0**, a belső ábrázolása pedig egy hosszú szám. A program automatikusan *valós* számmá alakítja az *int64* értéket.

Mindemelett a következő explicit átváltási függvények használhatók:

- [INT64VALUE](er-functions-conversion-int64value.md)
- [NUMBERFORMAT](er-functions-text-numberformat.md)
- [TEXT](er-functions-text-text.md)

Az *int64* tartománya \[-9,223,372,036,854,775,807 : 9,223,372,036,854,775,807\].

Az összes összehasonlító és matematikai [operátor](er-formula-language.md#Operators) használható az *int64* adattípussal.

## <a name="real"></a><a name="real"></a>Valós

A *valós* egyszerű adattípus az egész számokon kívül tizedesértékeket is képes tartalmazni. Tizedes konstansértékeket is használhat minden olyan helyhez, ahol *valós* értéket vár. A tizedes konstansérték a tizedes szám, ahogyan az közvetlenül meg van adva a kódban, például **2,19**.

> [!NOTE]
> Az ER kifejezésekben mindig egy pontot (.) használ a rendszer tizedeselválasztóként.

A valós számok minden kifejezésben használhatók, és összehasonlítással és számtani operátorokkal is használhatók. A *valós* szám pontossága 16 különálló számjegy. A *valós* alapértelmezett értéke **0.0**, a belső megjelenítés pedig egy bináris kódú digitális (BCD) szám. A BCD kódolás lehetővé teszi a 0,1 többszörös értékeinek pontos megjelenítését. A *valós* változó tartománya -(10)<sup>127</sup> és (10)<sup>127</sup> között lehet. A tartományban minden valós érték használható konstansértékként az ER-kifejezésekben.

A *valós* érték nem rendelkezik implicit átalakításokkal. Használhatja azonban a következő függvényekkel a *valós* adatok más adattípusok és egyéb adattípusok *valóssá* konvertálására:

- [INTVALUE](er-functions-conversion-intvalue.md)
- [INT64VALUE](er-functions-conversion-int64value.md)
- [NUMBERFORMAT](er-functions-text-numberformat.md)
- [TEXT](er-functions-text-text.md)
- [VALUE](er-functions-conversion-value.md)

Az összes összehasonlító és matematikai [operátor](er-formula-language.md#Operators) használható a *valós* adattípussal.

## <a name="string"></a><a name="string"></a>Sztring

A *sztring* egyszerű adattípus szövegek, számlaszámok, címek és telefonszámokként használt karakterek sorozatát jelöli.

A *sztring* konstansértékek idézőjelek ("") közé zárt karakterek. A *sztring* konstansértékek használhatók ott, ahol *sztring* értékek vártak az ER-kifejezésekben. A sztringeket logikai kifejezésekben, például összehasonlításban lehet használni. A *sztring* értékeket az **\&** operátorral vagy a [CONCATENATE](er-functions-text-concatenate.md) függvénnyel össze is lehet fűzni.

> [!NOTE]
> Ha két *sztring* értéket összefűz, és az eredményül kapott *sztring* egynél több sorra terjed ki, használjon az értékek közötti sortörés-elválasztót. A SZÖVEG kimenetnél ez az elválasztó karakter lehet a [CHAR](er-functions-text-char.md)(10) vagy a CHAR(13) kifejezés által generált karakter. HTML formátumban ez lehet a **\<br\>** címke.

A *sztring* alapértelmezett értéke üres szöveges karakterlánc, amely nem tartalmaz karaktereket, és a belső ábrázolása karakterek listája.

Nincsenek automatikus átváltások a sztringek számára. Használhatja azonban a következő explicit átváltási függvényeket:

- [CHAR](er-functions-text-char.md)
- [FORMAT](er-functions-text-format.md)
- [LEFT](er-functions-text-left.md)
- [LEN](er-functions-text-len.md)
- [MID](er-functions-text-mid.md)
- [PADLEFT](er-functions-text-padleft.md)
- [REPLACE](er-functions-text-replace.md)
- [RIGHT](er-functions-text-right.md)
- [TEXT](er-functions-text-text.md)
- [TRANSLATE](er-functions-text-translate.md)
- [TRIM](er-functions-text-trim.md)
- [UPPER](er-functions-text-upper.md)

A *sztring* értékek átalakításával kapcsolatos további tudnivalókat lásd az [ER-függvények listája a szöveg kategóriában](er-functions-category-text.md) részben.

A *sztring* bármilyen számú karaktert tartalmazhat.

Az összes [összehasonlító](er-formula-language.md#Operators) operátor használható a *sztring* adattípussal.

## <a name="additional-resources"></a>További erőforrások

- [Elektronikus jelentések áttekintése](general-electronic-reporting.md)
- [Elektronikus jelentéskészítés képletének nyelve](er-formula-language.md)
- [Támogatott összetett adattípusok](er-formula-supported-data-types-composite.md)
