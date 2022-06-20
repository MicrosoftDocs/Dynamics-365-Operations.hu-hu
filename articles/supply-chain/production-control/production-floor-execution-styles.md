---
title: A termelési üzem végrehajtási felületének kialakítása
description: A cikk bemutatja, hogyan kell konfigurálni az űrlapvezérlőket úgy, hogy a rendszer alkalmazza a termelés alapértelmezett végrehajtási stílusát.
author: johanhoffmann
ms.date: 11/08/2021
ms.topic: article
ms.search.form: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2021-02-22
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: ad6ecd591353fe8ddc1a5b9049d65491fb58e98a
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8859140"
---
# <a name="style-the-production-floor-execution-interface"></a>A termelési üzem végrehajtási felületének kialakítása

[!include [banner](../includes/banner.md)]

A cikk bemutatja, hogyan kell konfigurálni az űrlapvezérlőket úgy, hogy a rendszer alkalmazza a termelés alapértelmezett végrehajtási stílusát.

## <a name="forms-and-dialogs"></a>Űrlapok és párbeszédpanelek

A stílusokat csak akkor lehet alkalmazni egy űrlapra vagy párbeszédpanelre, ha teljesülnek a következő követelmények:

- Ha a képernyőnek meg kell egynie a jelentés folyamatjelző képernyőjéhez, akkor a képernyő vagy párbeszédpanel nevének a következővel kell kezdődnie:`JmgProductionFloorExecutionCustomInputDialog`
- Az űrlap vagy párbeszédpanel egy részletes űrlaprészt tartalmazhat. Ahhoz, hogy stílusokat alkalmazz, a részletképernyő nevének kezdetével kell kezdődnie `JmgProductionFloorExecutionCustomDetailsDialog`.
- Ha a képernyőnek vagy párbeszédpanelnek egyszerű nézetnek kell lennie, akkor az egyszerű nézet nevének a kezdetével kell kezdődnie `JmgProductionFloorExecutionCustomDialog`. Az egyszerű nézetű űrlapokra példa a kezdő űrlap és a közvetett tevékenység űrlap.
- A párbeszédpanelen látható összes vezérlőelemet a jelen cikknek megfelelően kell konfigurálni.

> [!IMPORTANT]
> A lista első két pontja által említett funkciókhoz a Supply Chain Management 10.0.19-es vagy újabb verziója szükséges.

A stílusokat csak akkor lehet alkalmazni az **OK** gombbal egy űrlapra vagy párbeszédpanelre, ha teljesülnek a következő követelmények:

- A gomb egy űrlapcsoporthoz tartozik.
- A csoportnév kezdete:`OkButtonGroup`

A stílusokat csak akkor lehet alkalmazni a **Mégse** gombra egy párbeszédpanelen, ha teljesülnek a következő követelmények:

- A gomb egy űrlapcsoporthoz tartozik.
- A csoportnév kezdete:`CancelButtonGroup`

### <a name="header"></a>Fejléc

A következő ábra egy jellemző képernyőt vagy párbeszédpanel-fejlécet mutat.

![Szokásos képernyő vagy párbeszédpanel fejléce.](media/pfe-styles-header.png "Szokásos képernyő vagy párbeszédpanel fejléce")

A Visual Studio fejlécek a következő példában látható szerkezettel jelennek meg.

![Tipikus kódstruktúra a fejlécek létrehozásához.](media/pfe-styles-header-code-structure.png "Tipikus kódstruktúra fejlécek létrehozásához")

Ha szöveget szeretne hozzáadni a fejléchez, használja a következő példaként használt kódot.

```xpp
private void setCaption()
{
    HeaderFieldWithSeparatorText1.text("Report Progress");
    HeaderFieldWithSeparatorText2.text(ProdId);

    …

    HeaderFieldText.text(OprNum);
}
```

A fejléckód megírásakor a következő szabályokat kell alkalmazni:

- A fő csoport nevének a következőnek kell lennie:`TableRowHeaderGroup`
- Minden szövegblokknak (felsorolással elválasztva) a következővel kell kezdődnie `HeaderFieldWithSeparatorText`:
- Az utolsó szöveg nevének a következővel kell kezdődnie:`HeaderFieldText`
- `CaptionImage` nem hagyható ki.

### <a name="progress-indicator"></a>Folyamatjelző

Az állapotjelző a fejléc jobb látható. A következő ábra egy folyamatjelzőt mutat be.

![Tipikus folyamatjelző.](media/pfe-styles-header-progress.png "Tipikus folyamatjelző")

Az állapotjelző csak akkor mutatja meg, ha a szövegmező neve ".`ShowProgress`

## <a name="grid"></a>Rács

A stílusok automatikusan vannak alkalmazva. Nincs szükség specifikus konfigurációra.

A rácsnak stílussal `TabularView` kell lennie, és `run()` felül kell írni az egyéni képernyőn található metódust, mivel az új rács még nem támogatott. Adja hozzá a következő kódot.

```xpp
public void run()
{
    super();
    // To opt out a page from the new grid
    this.forceLegacyGrid();
}
```

Ha fő nézetben szeretné frissíteni az adatokat, `this.parmParentForm().updateLayout();``click` akkor a művelet egy módszeréhez hasonlót érdemes használnia. (Példaként nézze meg az osztályt `JmgProductionFloorExecutionReportFeedbackAction` .) Győződjön meg róla, hogy `parmDataSource` be `init` van állítva az új képernyő (`formCaller.parmDataSource(this.dataSource(1));`) módszerében. Példaként nézze meg a képernyőt `JmgProductionFloorExecutionMainGrid`.

## <a name="card-view"></a>Kártyanézet

A stílusokat csak akkor lehet alkalmazni kártyanézet-vezérlőkre, ha teljesülnek a következő követelmények:

- Minden kártyanézet egy űrlapcsoportba tartozik.
- A csoportnév kezdete `CardGroup` (például `CardGroupJobsView`).

A következő ábra egy olyan kártyanézetet mutat, amelyben nincsenek vezérlőelemek.

![Kártyanézet elemek nélkül.](media/pfe-styles-empty-card.png)

A következő ábrák kártyanézeteteket mutatnak be, amelyekben vannak vezérlőelemek.

![Kártya Hz értéket mutató elemekkel.](media/pfe-styles-elements.png)

![Kártya karbantartási kérések elemeivel.](media/pfe-styles-elements-maintenance.png)

## <a name="business-card"></a>Névjegykártya

A stílusokat csak akkor lehet alkalmazni névjegykártya-vezérlőkre, ha teljesülnek a következő követelmények:

- Minden névjegykártya egy űrlapcsoportba tartozik.
- A csoportnév kezdete `BusinessCardGroup` (például `BusinessCardGroupJobsList`).

A következő tulajdonságokat állítsa be a névjegykártyán:

- **Stílus:** *lista*
- **Kiterjesztett stílus:** *cardList*
- **Többszörös kijelölés:** *Nem*
- **Oszlopcímkék megjelenítése:** *Nem*

![Névjegykártya.](media/pfe-styles-business-card.png)

## <a name="radio-button"></a>Választógomb

A stílusokat csak akkor lehet alkalmazni választógombokra, ha teljesülnek a következő követelmények:

- Az összes választógomb egy űrlapcsoporthoz tartozik.
- A csoportnév kezdete `RadioTextBelow` vagy – `RadioTextRight` attól függően, hogy hol szeretné megjelenni a szöveget.

A következő tulajdonságokat állítsa be a választógombon:

- **Váltógomb:** *Ellenőrzés*
- **Érték váltása:** *Be van jelölve*, ha ki kell választani a választógombot, egyébként, Ki *·*

A következő ábra egy példát mutat be arra, hogy hol jelenik meg a szöveg a választógombok alatt.

![Választógombok alattuk szöveggel.](media/pfe-styles-radio-text-below.png)

A következő ábra egy példát mutat be arra, hogy hol jelenik meg a szöveg a választógombok jobb oldalán.

![Választógombok szöveggel a jobb oldalon.](media/pfe-styles-radio-text-right.png)

### <a name="radio-buttons-in-internet-explorer"></a>Választógombok az Internet Explorerben

A választógombok stílusát nem támogatja az Internet Explorer. Az alábbi ábra azt mutatja, hogyan néznek ki a választógombok a Internet Explorer alkalmazásban.

![Választógombok az Internet Explorerben.](media/pfe-styles-browser.png)

## <a name="buttons"></a>Gombok

A stílusokat csak akkor lehet alkalmazni gombokra, ha teljesülnek a következő követelmények:

- Az összes gombcsoport egy űrlapcsoporthoz tartozik. A csoport minden gombja ugyanolyan stílusú lesz.
- Nincsenek követelmények a csoport nevével kapcsolatban.

A következő tulajdonságokat állítsa be a gombon:

- **Gomb megjelenítése:** *TextWithImageLeft*
- **Normál kép:** Ez a tulajdonság nem lehet üres. Például használja a *CoffeeScript* elemet.
- **Szöveg:** Ez a tulajdonság nem lehet üres. Például használja a *Törés kezdete* elemet.
- **Szélesség:** *Automatikus vagy* *SizeToContent*
- **Magasság:** *Automatikus vagy* *SizeToContent*

### <a name="primary-button"></a>Elsődleges gomb

A stílusokat csak akkor lehet alkalmazni elsődleges gombra, ha teljesülnek a következő követelmények:

- A gomb egy űrlapcsoporthoz tartozik.
- A csoportnév kezdete vagy `DefaultButtonGroup``PrimaryButtonGroup` (például `DefaultButtonGroup10`).

![Elsődleges gomb.](media/pfe-styles-first.png)

### <a name="secondary-button"></a>Másodlagos gomb

A stílusokat csak akkor lehet alkalmazni a másodlagos gombra, ha teljesülnek a következő követelmények:

- A gomb egy űrlapcsoporthoz tartozik.
- A csoport neve **Jobb panel**, vagy a csoport neve `SecondaryButtonGroup` a kezdete.

![Másodlagos gomb.](media/pfe-styles-second.png)

### <a name="third-group-button"></a>Harmadlagos gomb

A stílusokat csak akkor lehet alkalmazni a harmadlagos gombra, ha teljesülnek a következő követelmények:

- A gomb egy űrlapcsoporthoz tartozik.
- A csoport neve **Bal panel**, vagy a csoportnév kezdete:`ThirdButtonGroup`

![Harmadlagos gomb.](media/pfe-styles-third.png)

### <a name="fourth-group-button"></a>Negyedik gombcsoport

A stílusokat csak akkor lehet alkalmazni a negyedleges gombra, ha teljesülnek a következő követelmények:

- A gomb egy űrlapcsoporthoz tartozik.
- A csoportnév kezdete:`FourthButtonGroup`

A következő tulajdonságokat állítsa be a gombon:

- **Gomb megjelenítése:** *Csak szöveg*
- **Normál kép:** A tulajdonságnak üresnek kell lennie.
- **Szöveg:** Ez a tulajdonság nem lehet üres. Használhatja például a *Nézet* vagy a *Szerkesztés* gombot.
- **Szélesség:** *Automatikus*
- **Magasság:** *automatikus*

![Negyedik gombcsoport.](media/pfe-styles-fourth.png)

### <a name="flat-button"></a>Lapos gomb

A stílusokat csak akkor lehet alkalmazni lapos gombra, ha teljesülnek a következő követelmények:

- A gomb egy űrlapcsoporthoz tartozik.
- A csoportnév kezdete:`FlatButtonGroup`

A következő tulajdonságokat állítsa be a gombon:

- **Gomb megjelenítése:** *Képonly*
- **Normál kép:** Ez a tulajdonság nem lehet üres. Például használja a *CoffeeScript* elemet.
- **Szöveg:** A tulajdonságnak üresnek kell lennie.
- **Szélesség:** *Automatikus vagy* *SizeToContent*
- **Magasság:** *Automatikus vagy* *SizeToContent*

![Lapos gomb.](media/pfe-styles-flat-button.png)

### <a name="continue-button"></a>Folytatás gomb

A stílusok csak akkor alkalmazhatók a folytatási gombra, ha teljesülnek a következő követelmények:

- A gomb egy űrlapcsoporthoz tartozik.
- A csoportnév kezdete:`ContinueButtonGroup`

A következő tulajdonságokat állítsa be a gombon:

- **Gomb megjelenítése:** *Képonly*
- **Normál kép:** *Előre*
- **Szöveg:** A tulajdonságnak üresnek kell lennie.
- **Szélesség:** *Automatikus vagy* *SizeToContent*
- **Magasság:** *Automatikus vagy* *SizeToContent*

![Folytatás gomb](media/pfe-styles-continue-button.png)

## <a name="combo-box"></a>Kombinált lista

A kombinált lista három vezérlőelem együttesét jelenti: egy beviteli vezérlő, egy beviteli vezérlőt törlő a gomb, valamint egy, a keresést futtató gomb.

A stílusokat csak akkor lehet alkalmazni kombinált listákra, ha teljesülnek a következő követelmények:

- A kombinált lista egy űrlapcsoporthoz tartozik.
- A csoportnév kezdete:`Combobox`
- A csoporton belül az első vezérlőelem egy `AxFormStringControl` vezérlő. Ez a vezérlő mutatja az aktuális értéket, és itt adja meg a felhasználó a szükséges értéket.
- A második vezérlő egy vezérlő, a `CommonButton` neve pedig a következővel kezdődik:`ClearButton` Ennek a gombnak olyan kódot kell tartalmaznia, amely `enable` a tulajdonságot használja a gomb megjelenítése vagy elrejtése. Ha például, amikor a felhasználó a beviteli vezérlőbe beír egy adatokat, megjeleníti vagy elrejti a **Törlés** gombot, használhatja a következő kódot.

    ```xpp
    public void textChange()
    {
        super();
        ClearButtonSerial.enabled(this.text()? true : false);
    }
    ```

    Egy olyan metódust kell használnia, amelynél az adatok be vannak állítva a beviteli vezérlőben. A **Törlés** gombot engedélyezze ebben a metódusban. Íme, egy példa.

    ```xpp
    public void setSerialId(str _serialId)
    {
        JmgTmpJobBundleProdFeedback.InventSerial = _serialId;
        ClearButtonSerial.enabled(_serialId? true : false);

        if (_serialId)
        {
            this.addSerialNumber();
        }
    }
    ```

    A Clear gomb metódusa `clicked` a **következő kódot** használja.

    ```xpp
    public void clicked()
    {
        element.setSerialId('');
        InventSerialId.setFocus(); // set focus back to the input box
    }
    ```

    A beviteli vezérlő értékének beállítása, `AxFormStringControl` ha a képernyőt a módszerrel inicializálják `init`. Ha az érték nem üres, engedélyezze a **Törlés** gombot. Ha az érték nem üres letiltja a **Törlés** gombot.

- A harmadik vezérlőelem egy `CommonButton` vezérlő, a neve pedig a következővel kezdődik:`SearchButton`

A következő ábra két kombinált lista vezérlőelemet mutat be. A bal oldali kombinált listában egy üres szövegmező található, és a **Törlés** gomb nincs engedélyezve. A jobb oldali kombinált listában egy szövegmezőben szöveg található, és a **Törlés** gomb engedélyezve van.

![Kombinált listák Törlés gombbal és anélkül.](media/pfe-styles-combo.png)

## <a name="quick-filter"></a>Gyorsszűrő

A gyorsszűrő-vezérlő keresési mezőt ad az oldalhoz. A stílusokat akkor alkalmazhatja gyorsszűrőkre, ha teljesülnek a következő követelmények:

- A gyorsszűrő egy űrlapcsoporthoz tartozik.
- A csoportnév kezdete:`SearchInputGroup`
- A csoporton belül az első vezérlőelem egy `QuickFilter` vezérlő. (Itt adhatja meg a felhasználó a keresési karakterláncot.)
- A második vezérlőelem neve `FormStaticTextControl` .`NumberOfResults` (Ezt a vezérlőelemet nem kötelező megadni. Ha szerepel benne, akkor a talált cikkek számát is mutatja.)
- A harmadik vezérlőelem egy `CommonButton` vezérlő, a neve pedig a következővel kezdődik:`ClearButton`

A következő ábra két gyorsszűrő vezérlőelemet mutat be. A bal oldalon látható gyorsszűrő üres gyorsszűrővel rendelkezik, és az eredmények száma nem látható. A jobb oldalon található gyorsszűrő egy keresési sztringet tartalmaz, amely megjeleníti az eredmények számát.

![Példák gyorsszűrő vezérlőre keresési sztringgel és anélkül.](media/pfe-styles-quick-filter.png "Példák gyorsszűrő vezérlőre keresési sztringgel és anélkül")

## <a name="center-align-elements-on-a-tab"></a>Lap elemeinek középre igazítása

A lap középpontjában található elemek beállításának a csoport nevével kell kezdődnie, `TabContentGroup` és a csoportnak a következő tulajdonságokkal kell kezdődnie:

- **Szélesség módja:**`SizeToAvailable`
- **Magasság módja:**`SizeToAvailable`

## <a name="align-a-grid-detail-part-and-quick-filter"></a>Rács, részletrész és gyorsszűrő igazítása

Ha egy testreszabott rácsot, részlet alkatrészt és gyors szűrőt úgy lehet rendezni, hogy hasonlítanak a normál tervhez, akkor tartsa szem előtt a következő pontokat, amikor az összeset összerakja:

- Ha a rácsnak gyorsszűrője van, akkor a rácsnak és a gyorsszűrőnek is abban a csoportban kell lennie, amely a nevével kezdődik `GridGroup`.
- Ahhoz, hogy a stílusokat egy részletrészre alkalmazza, a csoport nevének a következővel kell kezdődnie:`DetailInformationGroup`

A következő ábra egy jellemző rácsot mutat be, amely gyorsszűrőt és a jobb oldalon egy részlet részletét tartalmazza.

![Tipikus rács, amely gyors szűrést és részletet foglal magában.](media/pfe-styles-align-grid.png "Tipikus rács, amely gyors szűrést és részletet tartalmaz")

A Visual Studio rácsban, a részletekben és a gyorsszűrőkben egy szerkezet – például az alábbi ábra – használatával lehet létrehozni.

![Tipikus kódstruktúra, amely egy rácsot, egy részlet részt és egy gyorsszűrőt igazított ki.](media/pfe-styles-header-code-structure2.png "Tipikus kódstruktúra, amely egy rácsot, egy részlet részt és egy gyorsszűrőt igazított ki")

## <a name="additional-resources"></a>További erőforrások

- [A termelési üzem végrehajtási felületének testreszabása](production-floor-execution-customize.md)
- [A termelési üzem végrehajtási felületének tervezése](production-floor-execution-tabs.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
