---
title: Egyéni mezők megvalósítása a Microsoft Dynamics 365 Project Timesheet mobilalkalmazás számára iOS és Android rendszeren
description: Ez a témakör gyakori mintákat mutat be a bővítmények egyéni mezők megvalósításáról való használatával kapcsolatban.
author: KimANelson
manager: AnnBe
ms.date: 05/29/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Service industries
ms.author: knelson
ms.dyn365.ops.version: 10.0.3
ms.search.validFrom: 2019-05-29
ms.openlocfilehash: 4343c875da05641c57b7784bf52f1c814dd26d20
ms.sourcegitcommit: 19859d8566a8c7840066b2c10c6b08b67f1b83f4
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/04/2019
ms.locfileid: "1617996"
---
# <a name="implement-custom-fields-for-the-microsoft-dynamics-365-project-timesheet-mobile-app-on-ios-and-android"></a>Egyéni mezők megvalósítása a Microsoft Dynamics 365 Project Timesheet mobilalkalmazás számára iOS és Android rendszeren

[!include [banner](../includes/banner.md)]

Ez a témakör gyakori mintákat mutat be a bővítmények egyéni mezők megvalósításáról való használatával kapcsolatban. A következő témaköröket fedi le:

- A különböző adattípusok, amelyeket az egyénimező-keretrendszer támogat
- A munkaidő-nyilvántartási bejegyzések írásvédett vagy szerkeszthető mezőinek megjelenítése és a felhasználó által megadott értékek mentése az adatbázisba
- A munkaidő-nyilvántartás fejlécében szereplő írásvédett mezők megjelenítése
- Egyéb egyéni üzleti logika integrálása az alapértelmezett értékek mezőkbe történő beírásához és a további ellenőrzés elvégzéséhez

## <a name="audience"></a>Közönség

Ez a témakör azoknak a fejlesztőknek készült, akik egyéni mezőket integrálnak a Microsoft Dynamics 365 Project Timesheet mobilalkalmazásba, amely Apple iOS és Google Android rendszeren érhető el. A feltételezés az, hogy az olvasók ismerik az X++ fejlesztési és projekt-időnyilvántartási funkciókat.

## <a name="data-contract--tstimesheetcustomfield-x-class"></a>Adatszerződés – TSTimesheetCustomField X++ osztály

A **TSTimesheetCustomField** osztály az X++ adatszerződés-osztály, amely a munkaidő-nyilvántartási funkció egyéni mezőjével kapcsolatos információkat jeleníti meg. Az egyéni mezőobjektumok listái mind a TSTimesheetDetails-, mind a TSTimesheetEntry-adatszerződésben megjelennek a mobilalkalmazás egyéni mezőinek megjelenítéséhez.

- **TSTimesheetDetails** – Az időnyilvántartás fejlécének szerződése.
- **TSTimesheetEntry** – A munkaidő-nyilvántartási tranzakció szerződése. Ezeknek az objektumoknak az a csoportja, amelyek ugyanazzal a projektadatokkal és **timesheetLineRecId** értékkel rendelkeznek, egy sort alkotnak.

### <a name="fieldbasetype-types"></a>fieldBaseType (Típusok)

A **TsTimesheetCustom** objektum **FieldBaseType** tulajdonsága meghatározza az alkalmazásban megjelenő mező típusát. A következő **Típusok** értékek támogatottak.

| Típusok értéke | Típus              | Megjegyzések |
|-------------|-------------------|-------|
| 0           | Karakterlánc (és felsorolás) | A mező szöveges mezőként jelenik meg. |
| 1           | Egész           | Az érték tizedesjegyek nélküli számként jelenik meg. |
| 2           | Valós              | Az érték tizedesjegyekkel megadott számként jelenik meg.<p>Ha meg szeretné jeleníteni a tényleges értéket pénznemként az alkalmazásban, használja a **fieldExtenededType** tulajdonságot. A megjelenő tizedesjegyek számának megadására a **numberOfDecimals** tulajdonság használható.</p> |
| 3           | Dátum              | A dátumformátum meghatározása a felhasználó által a felhasználó által megadott **Dátum-, idő- és számformátum** beállítás alapján történik, amelyet a **Felhasználói beállítások** **Nyelv- és ország/régiópreferencia** pontban lehet megadni. |
| 4           | Logikai           | |
| 15          | GUID              | |
| 16          | Int64             | |

- Ha a **stringOptions** tulajdonság nem szerepel a **TSTimesheetCustomField** objektumban, a felhasználó számára egy szabad szöveges mezőt áll rendelkezésre.

    A **stringLength** tulajdonsággal beállítható a maximálisan megadható karakterlánc hossza.

- Ha a **stringOptions** tulajdonság szerepel a **TSTimesheetCustomField** objektumban, ezek a listaelemek az egyetlen értékek, amelyet a felhasználó a választási gombok (választógombok) használatával választhat ki.

    Ebben az esetben a karakterlánc-mező felsorolási értékként működhet a felhasználói bejegyzés céljához. Ha az értéket felsorolásként szeretné menteni az adatbázisba, akkor az adatbázisba történő mentés előtt manuálisan hozzá kell rendelnie a karakterlánc értékét a felsorolás értékéhez (lásd: „Parancslánc használata a TSTimesheetEntryService osztályon az időnyilvántartás-bejegyzés alkalmazásból az adatbázisba való mentéséhez” szakaszt később ebben a témakörben példaként).

### <a name="fieldextendedtype-tscustomfieldextendedtype"></a>fieldExtendedType (TSCustomFieldExtendedType)

Ez a tulajdonság a tényleges értékek pénznemként történő formázására használható. Ez a megközelítés csak akkor alkalmazható, ha a **fieldBaseType** értéke **Valódi**.

- **TSCustomFieldExtendedType:Nincs** – Nincs formázás alkalmazva.
- **TSCustomFieldExtendedType::Pénznem** – Az érték formázása fizetőeszközként.

    Ha aktív a pénznem formázása, akkor a **stringValue** mező felhasználható az alkalmazásban megjelenítendő pénznemkód elküldéséhez. Az érték írásvédett érték.

    A **realValue** mező az adatbázisba mentendő pénzösszeget tartalmazza.

### <a name="fieldsection-tscustomfieldsection"></a>fieldSection (TSCustomFieldSection)

Ezt a tulajdonságot akkor kell megadni, ha az egyéni mezőnek meg kell jelennie az alkalmazásban.

- **TSCustomFieldSection::Fejléc** – A mező az alkalmazás **További részletek megjelenítése** szakaszában fog megjelenni. Mindkettő mező mindig csak olvasható mező.
- **TSCustomFieldSection::Sor** – A mező a munkaidő-nyilvántartási bejegyzések összes beépített sormezője után fog megjelenni. Ezek a mezők lehetnek szerkeszthetők és írásvédettek is.

### <a name="fieldname-fieldnameshort"></a>fieldName (FieldNameShort)

Ez a tulajdonság azonosítja azt a mezőt, amikor az alkalmazás által biztosított értékeket visszamentették az adatbázisba.

### <a name="tablename-tablenameshort"></a>tableName (TableNameShort)

Ez a tulajdonság azonosítja azt a mezőt, amikor az alkalmazás által biztosított értékeket visszamentették az adatbázisba.

### <a name="iseditable-noyes"></a>isEditable (NoYes)

Ennek a tulajdonságnak az **Igen** értékre állításával megadhatja, hogy az időnyilvántartás-bejegyzés szakasz mezőjét a felhasználók szerkeszthetik-e. A tulajdonság **Nem** értékre állításával a mező írásvédett.

### <a name="ismandatory-noyes"></a>isMandatory (NoYes)

Ennek a tulajdonságnak az **Igen** értékre állításával megadhatja, hogy az időnyilvántartás-bejegyzés szakasz mezőjét kötelező-e megadni.

### <a name="label-str"></a>címke (str)

Ez a tulajdonság azt a címkét határozza meg, amely az alkalmazásban a mező mellett látható.

### <a name="stringoptions-list-of-strings"></a>stringOptions (Karakterláncok listája)

Ez a tulajdonság csak akkor használható, ha a **fieldBaseType** értéke **Karakterlánc**. Ha a **stringOptions** be van állítva, akkor a választógombokon keresztül választható karakterlánc-értékeket a lista karakterláncai határozzák meg. Ha nincsenek megadva karakterláncok, a karakterlánc mezőben szabad szöveges bejegyzés megengedett (lásd: „Parancslánc használata a TSTimesheetEntryService osztályon az időnyilvántartás-bejegyzés alkalmazásból az adatbázisba való mentéséhez” szakaszt később ebben a témakörben példaként).

### <a name="stringlength-int"></a>stringLength (int)

Ez a tulajdonság adja meg a karakterlánc-mező maximális hosszát. Csak akkor használható, ha a **fieldBaseType** értéke **Karakterlánc**.

### <a name="numberofdecimals-int"></a>numberOfDecimals (int)

Ez a tulajdonság a valódi mezőhöz megjelenített tizedesjegyek számát határozza meg. Csak akkor használható, ha a **fieldBaseType** értéke **Valódi**.

### <a name="ordersequence-int"></a>orderSequence (int)

Ez a tulajdonság határozza meg, hogy az egyéni mezők milyen sorrendben jelenjenek meg az alkalmazásban, ha egynél több egyéni mező van megadva. A kisebb számú mezőket kell elsőként megjeleníteni.

### <a name="booleanvalue-boolean"></a>booleanValue (boolean)

A **Logikai** típusú mezők esetében a tulajdonság a kiszolgáló és az alkalmazás között a mező logikai értékét adja át.

### <a name="guidvalue-guid"></a>guidValue (guid)

A **GUID** típusú mezők esetében a tulajdonság a kiszolgáló és az alkalmazás között a globális egyedi azonosító (GUID) értékét adja át.

### <a name="int64value-int64"></a>int64Value (int64)

Az **Int64** típusú mezők esetében a tulajdonság a kiszolgáló és az alkalmazás között a mező int64 értékét adja át.

### <a name="intvalue-int"></a>intValue (int)

Az **Int** típusú mezők esetében a tulajdonság a kiszolgáló és az alkalmazás között a mező int értékét adja át.

### <a name="realvalue-real"></a>realValue (valódi)

A **Valódi** típusú mezők esetében a tulajdonság a kiszolgáló és az alkalmazás között a mező valódi értékét adja át.

### <a name="stringvalue-str"></a>stringValue (str)

Az **Karakterlánc** típusú mezők esetében a tulajdonság a kiszolgáló és az alkalmazás között a mező karakterlánc-értékét adja át. Ez a pénznemként formázott **Valódi** típusú mezők esetében is használatos. Ezeknél a mezőknél a tulajdonság a pénznemkód az alkalmazásnak való átadására használatos.

### <a name="datevalue-date"></a>dateValue (dátum)

A **Dátum** típusú mezők esetében a tulajdonság a kiszolgáló és az alkalmazás között a mező dátumértékét adja át.

## <a name="show-and-save-a-custom-field-in-the-timesheet-entry-section"></a>Egyéni mező megjelenítése és mentése a munkaidő-nyilvántartási bejegyzés szakaszban

Alul látható egy képernyőkép az időnyilvántartás-bejegyzés létrehozásáról a mobilalkalmazásból. Ezen láthatók a beépített mezők és az egyéni mező az „Időbejegyzés” szakaszban „Tesztkarakterlánc” néven, beállított „Második lehetőség” felsorolási értékkel.

![Tesztkarakterlánc egyéni mezője az alkalmazásban](media/timesheet-entry.jpg)



Alul látható egy képernyőkép a mobilalkalmazásból, amelyen a felhasználó kiválasztja a „Tesztkarakterlánc” egyéni mezőkhöz rendelkezésre álló felsorolási lehetőségek egyikét.  A két lehetőség az „Első lehetőség” és a „Második lehetőség” választógombként jelenik meg. A második beállítás van jelenleg kiválasztva.

![Beállítógombok (választógombok) a tesztkarakterlánc egyéni mezőjéhez](media/enum-option.jpg)



### <a name="extend-the-tstimesheetline-table-so-that-it-has-a-custom-field"></a>A TSTimesheetLine táblájának bővítése, hogy egyéni mezőt tartalmazzon

A tipikus esetekben valószínű, hogy az időnyilvántartás-bejegyzési szakasz egyéni mezőjének adatait a TSTimesheetLine táblába menti a program. Más táblákat lehet azonban használni, ha az adatok beolvasása a megadott TSTimesheetTrans-rekord alapján történik, vagy ha nem rendelkezik konkrét rekord környezettel (például ha a mező értéke írásvédett a projekt paraméterei között).

Ne felejtse el, hogy az egyéni mezőknek nem kell biztonsági adatbázisrekordokkal rendelkezniük. Az X++ logika alapján dinamikusan generálhatók. Ez a megközelítés jól használható írásvédett helyzetekben (lásd: „Parancslánc használata a TSTimesheetDetails osztály buildCustomFieldListForHeader metódusán az időnyilvántartás-adatok kitöltésére” szakaszt a dinamikusan generált egyénimező-értékek példájaként).

Alul látható egy képernyőkép az Visual Studio alkalmazásobjektum-fáról. A TSTimesheetLine tábla bővítését jeleníti meg a TestLineString mezővel, amelyet egyéni mezőként adtak hozzá.

![Sor karakterlánca](media/b6756b4a3fc5298093327a088a7710fd.png)

### <a name="use-chain-of-command-on-the-buildcustomfieldlist-method-of-the-tstimesheetsettings-class-to-show-a-field-in-the-timesheet-entry-section"></a>A TSTimesheetSettings osztály buildCustomFieldList-metódusának parancsláncának használata az időnyilvántartás-bejegyzés szakasz mezőinek megjelenítésére

Ez a kód az alkalmazásban a mező megjelenítési beállításait vezérli. Például a mező típusát, a címkét, hogy a mezőt kötelező-e megadni, és azt, hogy milyen szakaszban jelenik meg a mező.

A következő példa egy karakterláncmezőt mutat be az időbejegyzéseken. Ennek a mezőnek két beállítása van, az **Első lehetőség** és a **Második lehetőség**, amely a beállításgombokon keresztül érhető el (választógombok). Az alkalmazás mezője az TSTimesheetLine táblához hozzáadott **TestLineString** mezőhöz van társítva.

Vegye figyelembe a **TSTimesheetCustomField::newFromMetatdata()** metódus használatával a következő egyéni mezőtulajdonságok inicializálásának egyszerűsítése lehetséges: **fieldBaseType**, **tableName**, **fieldname**, **label**, **isEditable**, **isMandatory**, **stringLength** és **numberOfDecimals**. Ezeket a paramétereket kézzel is be lehet állítani, ahogy szeretné.

```
...
[ExtensionOf(classStr(TsTimesheetSettings))]
final class TSTimesheetSettings_Extension
{
    protected List buildCustomFieldList()
    {
        List customFieldList = next buildCustomFieldList();
        TSTimesheetCustomField tsTimesheetCustomField;
        tsTimesheetCustomField =
        TSTimesheetCustomField::newFromMetadata(tableNum(TsTimesheetLine),
        fieldNum(TSTimesheetLine, TestLineString));
        tsTimesheetCustomField.parmFieldSection(TSCustomFieldSection::Line);
        tsTimesheetCustomField.parmOrderSequence(1);
        List stringOptions = new List(Types::String);
        stringOptions.addEnd('First option');
        stringOptions.addEnd('Second option');
        tsTimesheetCustomField.parmStringOptions(stringOptions);
        customFieldList.addEnd(tsTimesheetCustomField);
        return customFieldList;
    }
}
...
```

### <a name="use-chain-of-command-on-the-buildcustomfieldlistforentry-method-of-the-tstimesheetentry-class-to-enter-values-in-a-timesheet-entry"></a>A TSTimesheetEntry osztály buildCustomFieldListForEntry-metódusának parancsláncának használata az időnyilvántartás-bejegyzés adatainak megadására

A **buildCustomFieldListForEntry** metódus a mobilalkalmazásban a mentett időnyilvántartás soraiban szereplő értékek megadására szolgál. A TSTimesheetTrans-rekordot paraméterként veszi figyelembe. A rekord mezői felhasználhatók az alkalmazás egyéni mezőjéne értékének kitöltésére.

```
...
[ExtensionOf(classStr(TsTimesheetEntry))]
final class TsTimesheetEntry_Extension
{
    protected List buildCustomFieldListForEntry(TSTimesheetTrans _tsTimesheetTrans)
    {
        List customFieldList = next buildCustomFieldListForEntry(_tsTimesheetTrans);
        TSTimesheetLine tsTimesheetLine = _tsTimesheetTrans.timesheetLine();
        TSTimesheetCustomField tsTimesheetCustomField;
        tsTimesheetCustomField =
        TSTimesheetCustomField::newFromMetadata(tableNum(TsTimesheetLine),
        fieldNum(TSTimesheetLine, TestLineString));
        tsTimesheetCustomField.parmFieldSection(TSCustomFieldSection::Line);
        tsTimesheetCustomField.parmOrderSequence(1);
        tsTimesheetCustomField.parmStringValue(tsTimesheetLine.TestLineString);
        List stringOptions = new List(Types::String);
        stringOptions.addEnd('First option');
        stringOptions.addEnd('second option;);
        tsTimesheetCustomField.parmStringOptions(stringOptions);
        customFieldList.addEnd(tsTimesheetCustomField);
        return customFieldList;
    }
}
...
```

### <a name="use-chain-of-command-on-the-tstimesheetentryservice-class-to-save-a-timesheet-entry-from-the-app-back-to-the-database"></a>A TSTimesheetEntryService osztályon parancslánc segítségével mentheti az alkalmazásból az adatbázisba a munkaidő-nyilvántartási bejegyzést.

Ha azt szeretné, hogy a szokásos használat során mentse az egyéni mezőt az adatbázisba, több metódust kell bővíteni:

- A **timesheetLineNeedsUpdating** metódus annak meghatározására szolgál, hogy az alkalmazásban a felhasználó módosította-e a sor rekordját, és az adatbázisba kell menteni. Ha a teljesítmény fontos, akkor ez a módszer egyszerűsíthető úgy, hogy mindig **igaz** értéket ad vissza.
- A **populateTimesheetLineFromEntryDuringCreate** és a **populateTimesheetLineFromEntryDuringUpdate** metódusok kiterjeszthetők úgy, hogy megadjanak értékeket a TSTimesheetLine adatbázisrekordban a megadott TSTimesheetEntry adatszerződés-rekordba. A következő példában figyelje meg, hogy az adatbázis-mező és a beviteli mező között manuálisan történik az X++ kód használatával a megfeleltetés.
- A **populateTimesheetWeekFromEntry** metódus is bővíthető, ha a **TSTimesheetEntry** objektumhoz rendelt egyéni mezőnek vissza kell írnia a TSTimesheetLineweek adatbázistáblájába.

> [!NOTE]
> A következő példában a rendszer elmenti a **firstOption** vagy **secondOption** értéket, amelyet a felhasználó nyers karakterlánc-értékként választ az adatbázisra. Ha az adatbázis mező **Felsorolás** típusú mező, akkor ezek az értékek manuálisan is megfeleltethetők egy felsorolási értékre, majd az adatbázistábla felsorolási mezőjébe menthetők.

```
...
[ExtensionOf(classStr(TSTimesheetEntryService))]
final class TSTimesheetEntryService_Extension
{
    protected boolean timesheetLineNeedsUpdating(TSTimesheetLine _tsTimesheetLine,
    TsTimesheetEntry _tsTimesheetEntry)
    {
        boolean ret = next timesheetLineNeedsUpdating(_tsTimesheetLine,
        _tsTimesheetEntry);
        if (!ret)
        {
            */ Loop through custom fields to see if value needs updating*/
            ListEnumerator enumerator =  _tsTimesheetEntry.parmCustomFields().getEnumerator();
            while (enumerator.moveNext())
            {
                TSTimesheetCustomField customField = enumerator.current();
                if (customField.parmFieldName() == fieldId2Name(tableNum(TsTimesheetLine),
                fieldNum(TSTimesheetLine, TestLineString)))
                {
                    */ If Custom field value for TestLineString field has changed, We need to update the timesheet line.*/
                    if (_tsTimesheetLine.TestLineString != customField.parmStringValue())
                    {
                        ret = true;
                    }
                }
            }
        }
        return ret;
    }
    protected void populateTimesheetLineFromEntryDuringCreate(TSTimesheetLine
    _tsTimesheetLine, TSTimesheetEntry _tsTimesheetEntry)
    {
        next populateTimesheetLineFromEntryDuringCreate(_tsTimesheetLine,
        _tsTimesheetEntry);
        this.populateTimesheetLineFromCustomFields(_tsTimesheetLine,
        _tsTimesheetEntry);
        }
        protected void populateTimesheetLineFromEntryDuringUpdate(TSTimesheetLine
        \_tsTimesheetLine, TSTimesheetEntry _tsTimesheetEntry)
        {
            next populateTimesheetLineFromEntryDuringUpdate(_tsTimesheetLine,
            _tsTimesheetEntry);
            this.populateTimesheetLineFromCustomFields(_tsTimesheetLine,
            _tsTimesheetEntry);
        }
        private void populateTimesheetLineFromCustomFields(TSTimesheetLine
        _tsTimesheetLine, TSTimesheetEntry _tsTimesheetEntry)
        {
            ListEnumerator enumerator =
            _tsTimesheetEntry.parmCustomFields().getEnumerator();
            while (enumerator.moveNext())
            {
                TSTimesheetCustomField customField = enumerator.current();
                if (customField.parmFieldName() == fieldId2Name(tableNum(TsTimesheetLine),
                fieldNum(TSTimesheetLine, TestLineString)))
                {
                    _tsTimesheetLine.TestLineString = customField.parmStringValue();
                }
            }
        }
    }
...
```

## <a name="show-a-custom-field-in-the-timesheet-header-section"></a>Egyéni mező megjelenítése a munkaidő-nyilvántartás fejlécébe szakasz

Alul látható egy képernyőkép a mobilalkalmazásból egy felhasználóról, aki időnyilvántartást tekint meg. A jobb felső sarokban kiválasztotta a „További információ” gombot, hogy megjelenítse a "További részletek megtekintése" beállítást.  

![További részletek megtekintése parancs](media/show-more.png)



Alul látható egy képernyőkép a mobilalkalmazásból az időnyilvántartás „Továbbiak” szakaszáról. Az időnyilvántartás fejléc szakaszába hozzáadtak egy „Időnyilvántartás kihasználtsági rátája (számított egyéni mező)” egyéni mezőt. Egy írásvédett "0,667" értékű érték van megadva az egyéni mezőben.

![Továbbiak szakasz](media/more-section.jpg)



### <a name="extend-the-tstimesheettable-table-so-that-it-has-a-custom-field"></a>A TSTimesheetTable táblájának bővítése, hogy egyéni mezőt tartalmazzon

A tipikus esetekben valószínű, hogy a fejléc szakasz egyéni mezőjének adatait a TSTimesheetHeader táblából hívja le a program. Más táblákat lehet azonban használni, ha az adatok beolvasása a megadott TSTimesheetTable-rekord alapján történik, vagy ha nem rendelkezik konkrét rekord környezettel (például ha a mező értéke írásvédett a projekt paraméterei között).

Ne felejtse el, hogy az egyéni mezőknek nem kell biztonsági adatbázisrekordokkal rendelkezniük. Az X++ logika alapján dinamikusan generálhatók. A következő példa bemutatja ezt a megközelítést.

A fejléc szakasz mezői mindig csak olvashatók az alkalmazásban.

### <a name="use-chain-of-command-on-the-buildcustomfieldlist-method-of-the-tstimesheetsettings-class-to-show-a-field-in-the-header-section"></a>A TSTimesheetSettings osztály buildCustomFieldList-metódusának parancsláncának használata a fejléc szakasz mezőinek megjelenítésére

Ez a kód az alkalmazásban a mező megjelenítési beállításait vezérli. Például a mező típusát, a címkét, hogy a mezőt kötelező-e megadni, és azt, hogy milyen szakaszban jelenik meg a mező.

A következő példa egy számított értéket mutat be az alkalmazás fejléc szakaszában.

```
...
[ExtensionOf(classStr(TsTimesheetSettings))]
final class TSTimesheetSettings_Extension
{
    protected List buildCustomFieldList()
    {
        List customFieldList = next buildCustomFieldList();
        TSTimesheetCustomField tsTimesheetCustomField;

        */ Computed utilization rate*/
        tsTimesheetCustomField = new TSTimesheetCustomField();
        tsTimesheetCustomField.parmFieldBaseType(Types::Real);
        tsTimesheetCustomField.parmLabel("Utilization rate of this timesheet (computed
        custom field)");
        tsTimesheetCustomField.parmFieldSection(TSCustomFieldSection::Header);
        tsTimesheetCustomField.parmOrderSequence(2);
        tsTimesheetCustomField.parmNumberOfDecimals(3);
        customFieldList.addEnd(tsTimesheetCustomField);
        return customFieldList;
    }
}
...
```

### <a name="use-chain-of-command-on-the-buildcustomfieldlistforheader-method-of-the-tstimesheetdetails-class-to-fill-in-timesheet-details"></a>A TSTimesheetDetails osztály buildCustomFieldListForHeader-metódusának parancsláncának használata az időnyilvántartás adatainak kitöltésére

A **buildCustomFieldListForHeader** metódus a mobilalkalmazásban az időnyilvántartás fejlécadatainak kitöltésére szolgál. A TSTimesheetTable-rekordot paraméterként veszi figyelembe. A rekord mezői felhasználhatók az alkalmazás egyéni mezőjéne értékének kitöltésére. A következő példa nem olvas le értéket az adatbázisból. Helyette az X++ logikát használja egy számított érték előállítására, amelyet azután az alkalmazás megjelenít.


```
...
[ExtensionOf(classStr(TSTimesheetDetails))]
final class TSTimesheetDetails_Extension
{
    protected List buildCustomFieldListForHeader(TSTimesheetTable
    _tsTimesheetTable)
    {
        List customFieldList = next buildCustomFieldListForHeader(_tsTimesheetTable);
        TSTimesheetCustomField tsTimesheetCustomField;

        */ Computed utilization rate*/
        tsTimesheetCustomField = new TSTimesheetCustomField();
        tsTimesheetCustomField.parmFieldBaseType(Types::Real);
        tsTimesheetCustomField.parmLabel("Utilization rate of this timesheet (computed
        custom field)");
        tsTimesheetCustomField.parmFieldSection(TSCustomFieldSection::Header);
        tsTimesheetCustomField.parmOrderSequence(2);
        tsTimesheetCustomField.parmNumberOfDecimals(3);
        real utilizationRate = 0;
        if (_tsTimesheetTable.totalHours() != 0)
        {
            utilizationRate = _tsTimesheetTable.totalHoursBillable() /
            _tsTimesheetTable.totalHours();
        }
        tsTimesheetCustomField.parmRealValue(utilizationRate);
        customFieldList.addEnd(tsTimesheetCustomField);
        return customFieldList;
    }
}
...
```

## <a name="other-configurabilityextensibility-opportunities"></a>Egyéb konfigurálási és bővíthetőségi lehetőségek

### <a name="adding-additional-validation-for-the-app"></a>További ellenőrzés hozzáadása az alkalmazáshoz

Az adatbázis szintjén a munkaidő-nyilvántartási funkció meglévő logikája továbbra is a várt módon fog működni. Ha meg szeretné szakítani a mentés vagy küldés műveleteinek befejezését, és egy konkrét hibaüzenetet megjeleníteni, akkor a kódra vonatkozó parancslánc-kiterjesztéssel hozzáadhat egy **dobási hibát(„üzenet a felhasználónak”)**. Az alábbiakban három példát talál a hasznos bővíthető metódusokra:

- Ha a TSTimesheetLine tábla **validateWrite** tulajdonsága **hamis** értéket ad vissza egy időnyilvántartási sor mentési művelete során, akkor egy hibaüzenet jelenik meg a mobilalkalmazásban.
- Ha a TSTimesheetTable tábla **validateSubmit** tulajdonsága **hamis** értéket ad vissza egy időnyilvántartási elküldési művelete során az alkalmazásban, akkor egy hibaüzenet jelenik meg a felhasználónak.
- A program továbbra is futtatja a mezők kitöltésére szolgáló logikát (például **Sortulajdonság)** a TSTimesheetLine táblán a **beszúrás** metódus során.

### <a name="hiding-and-marking-out-of-box-fields-as-read-only-via-configuration"></a>Beépített mezők elrejtése és írásvédettként megjelenítése konfigurációval

A projekt paraméterei alapján a mobilalkalmazásban a beépített mezőket csak olvashatóvá vagy rejtetté teheti. Adja meg a **Projektkezelés és könyvelési paraméterek** oldal **Időnyilvántartás** lapjának **Mobil-időnyilvántartások** szakaszának beállításait.

![Projekt paraméterei](media/5753b8ecccd1d8bb2b002dd538b3f762.png)

### <a name="changing-the-activities-that-are-available-for-selection-via-extensions"></a>A rendelkezésre álló tevékenységek módosítása a bővítményeken keresztül

A projekthez választható tevékenységek a **getActivitiesForProject()** és a **getActivityQuery()** metódusokon keresztül kerülnek kitöltésre a **TsTimesheetProjectService** osztályban. A parancslánc használatával módosíthatja ezt a viselkedést, hogy megfeleljen az üzleti helyzetnek a tevékenységekhez, amelyek kiválaszthatók egy adott projekt esetében.

### <a name="entering-a-default-project-category-on-timesheet-entries"></a>Alapértelmezett projektkategória megadása a munkaidő-nyilvántartási bejegyzésekhez

Az időnyilvántartási bejegyzésekhez tartozó alapértelmezett projektkategória megadása három szinten történik. A parancslánc használatával bővítheti a viselkedést bármely vagy mind a három szinten a kívánt viselkedés eléréséhez. A rendszer a következő hierarchiát követi:

1. Az alkalmazás megpróbálja alkalmazni az alapértelmezett kategóriát a projekterőforrásból. Ez az alapértelmezett kategória a **getCurrentUserResource** és a **getDelegatedResourcesForCurrentUser** metódusokban van megadva a **TSTimesheetSettingsService** osztályban.
2. Ha az alapértelmezett kategória nem szerepel a projekterőforrás szintjén, akkor az alkalmazás megpróbálja lehívni azt a projekt tevékenységéből. Ez az alapértelmezett kategória a **TSTimesheetProjectService** osztály **getActivitiesForProject** metódusában van megadva.
3. Ha az alapértelmezett kategória nem szerepel a projekttevékenység szintjén, akkor az alapértelmezett kategóriát alkalmazás megpróbálja lehívni azt a projekt paramétereiből. Ez az alapértelmezett kategória a **TSTimesheetProjectService** osztály **getProjectDetailsbyRule** metódusában van megadva.
