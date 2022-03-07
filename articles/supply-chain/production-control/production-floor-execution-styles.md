---
title: A termelési üzem végrehajtási felületének kialakítása
description: A témakör bemutatja, hogyan kell konfigurálni az űrlapvezérlőket úgy, hogy a rendszer alkalmazza a termelési üzem alapértelmezett végrehajtási stílusát.
author: johanhoffmann
ms.date: 02/22/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2021-02-22
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 32e49458f6ea7c484bc4200e414d930381b31891
ms.sourcegitcommit: 614d79cba238e466d445767a7d0a012e785a9861
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/19/2021
ms.locfileid: "7652006"
---
# <a name="style-the-production-floor-execution-interface"></a>A termelési üzem végrehajtási felületének kialakítása

[!include [banner](../includes/banner.md)]

A témakör bemutatja, hogyan kell konfigurálni az űrlapvezérlőket úgy, hogy a rendszer alkalmazza a termelési üzem alapértelmezett végrehajtási stílusát.

## <a name="forms-and-dialogs"></a>Űrlapok és párbeszédpanelek

A stílusokat csak akkor lehet alkalmazni egy űrlapra vagy párbeszédpanelre, ha teljesülnek a következő követelmények:

- Ha az űrlapnak hasonlítania kell a meglévő jelentés folyamatjelző űrlapjához, akkor az űrlap vagy párbeszédpanel nevének a **JmgProductionFloorExecutionCustomInputDialog** kifejezéssel kell kezdődnie.
- Az űrlap vagy párbeszédpanel egy részletes űrlaprészt tartalmazhat. Ahhoz, hogy stílusokat alkalmazhasson, a részletes űrlap nevének a **JmgProductionFloorExecutionCustomDetailsDialog** kifejezéssel kell kezdődnie.
- Ha az űrlapnak vagy párbeszédpanelnek egyszerű nézetűnek kell lennie, akkor az egyszerű nézet nevének a **JmgProductionFloorExecutionCustomDialog** kifejezéssel kell kezdődnie. Az egyszerű nézetű űrlapokra példa a kezdő űrlap és a közvetett tevékenység űrlap.
- A párbeszédpanelen található összes vezérlőelemet az ebben a témakörben leírt módon kell konfigurálni.

> [!IMPORTANT]
> A lista első két pontja által említett funkciókhoz a Supply Chain Management 10.0.19-es vagy újabb verziója szükséges.

A stílusokat csak akkor lehet alkalmazni az **OK** gombbal egy űrlapra vagy párbeszédpanelre, ha teljesülnek a következő követelmények:

- A gomb egy űrlapcsoporthoz tartozik.
- A csoportnév az **OkButtonGroup** kifejezéssel kezdődik.

A stílusokat csak akkor lehet alkalmazni a **Mégse** gombra egy párbeszédpanelen, ha teljesülnek a következő követelmények:

- A gomb egy űrlapcsoporthoz tartozik.
- A csoportnév az **CancelButtonGroup** kifejezéssel kezdődik.

## <a name="grid"></a>Rács

A stílusok automatikusan vannak alkalmazva. Nincs szükség specifikus konfigurációra.

## <a name="card-view"></a>Kártyanézet

A stílusokat csak akkor lehet alkalmazni kártyanézet-vezérlőkre, ha teljesülnek a következő követelmények:

- Minden kártyanézet egy űrlapcsoportba tartozik.
- A csoportnév a **CardGroup** elemmel kezdődik (például **CardGroupJobsView**).

A következő ábra egy olyan kártyanézetet mutat, amelyben nincsenek vezérlőelemek.

![Kártyanézet elemek nélkül.](media/pfe-styles-empty-card.png)

A következő ábrák kártyanézeteteket mutatnak be, amelyekben vannak vezérlőelemek.

![Kártya Hz értéket mutató elemekkel.](media/pfe-styles-elements.png)

![Kártya karbantartási kérések elemeivel.](media/pfe-styles-elements-maintenance.png)

## <a name="business-card"></a>Névjegykártya

A stílusokat csak akkor lehet alkalmazni névjegykártya-vezérlőkre, ha teljesülnek a következő követelmények:

- Minden névjegykártya egy űrlapcsoportba tartozik.
- A csoportnév a **BusinessCardGroup** elemmel kezdődik (például **BusinessCardGroupJobsList**).

A következő tulajdonságokat állítsa be a névjegykártyán:

- **Stílus**: **lista**
- **Kiterjesztett stílus**: **cardList**
- **Többszörös kijelölés**: **Nem**
- **Oszlopcímkék megjelenítése**: **Nem**

![Névjegykártya.](media/pfe-styles-business-card.png)

## <a name="radio-button"></a>Választógomb

A stílusokat csak akkor lehet alkalmazni választógombokra, ha teljesülnek a következő követelmények:

- Az összes választógomb egy űrlapcsoporthoz tartozik.
- A csoport neve a **RadioTextBelow** vagy a **RadioTextRight** előtaggal kezdődik attól függően, hogy hol szeretné a szöveget megjeleníteni.

A következő tulajdonságokat állítsa be a választógombon:

- **Váltógomb**: **Ellenőrzés**
- **Érték váltása**: **Be**, ha ki kell választani a választógombot, ellenkező esetben **Ki**

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

- **Gomb megjelenítése**: **TextWithImageLeft**.
- **Normál kép**: Ez a tulajdonság nem lehet üres. Például használja a **CoffeeScript** elemet.
- **Szöveg**: Ez a tulajdonság nem lehet üres. Például használja a **Törés kezdete** elemet.
- **Szélesség**: **Automatikus**.
- **Magasság**: **Automatikus**.

### <a name="primary-button"></a>Elsődleges gomb

A stílusokat csak akkor lehet alkalmazni elsődleges gombra, ha teljesülnek a következő követelmények:

- A gomb egy űrlapcsoporthoz tartozik.
- A csoport neve **DefaultButtonGroup** vagy **PrimaryButtonGroup** értékkel kezdődik (például **DefaultButtonGroup10**).

![Elsődleges gomb.](media/pfe-styles-first.png)

### <a name="secondary-button"></a>Másodlagos gomb

A stílusokat csak akkor lehet alkalmazni a másodlagos gombra, ha teljesülnek a következő követelmények:

- A gomb egy űrlapcsoporthoz tartozik.
- A csoport neve **Jobb panel**, vagy a csoport neve **SecondaryButtonGroup** kifejezéssel kezdődik.

![Másodlagos gomb.](media/pfe-styles-second.png)

### <a name="third-group-button"></a>Harmadlagos gomb

A stílusokat csak akkor lehet alkalmazni a harmadlagos gombra, ha teljesülnek a következő követelmények:

- A gomb egy űrlapcsoporthoz tartozik.
- A csoport neve **Bal panel**, vagy a csoport neve **ThirdButtonGroup** kifejezéssel kezdődik.

![Harmadlagos gomb.](media/pfe-styles-third.png)

### <a name="fourth-group-button"></a>Negyedik gombcsoport

A stílusokat csak akkor lehet alkalmazni a negyedleges gombra, ha teljesülnek a következő követelmények:

- A gomb egy űrlapcsoporthoz tartozik.
- A csoportnév a **FourthButtonGroup** kifejezéssel kezdődik.

A következő tulajdonságokat állítsa be a gombon:

- **Gomb megjelenítése**: **TextOnly**.
- **Normál kép**: Ez a tulajdonság üres kell legyen.
- **Szöveg**: Ez a tulajdonság nem lehet üres. Használhatja például a **Nézet** vagy a **Szerkesztés** gombot.
- **Szélesség**: **Automatikus**.
- **Magasság**: **Automatikus**.

![Negyedik gombcsoport.](media/pfe-styles-fourth.png)

### <a name="flat-button"></a>Lapos gomb

A stílusokat csak akkor lehet alkalmazni lapos gombra, ha teljesülnek a következő követelmények:

- A gomb egy űrlapcsoporthoz tartozik.
- A csoportnév a **FlatButtonGroup** kifejezéssel kezdődik.

A következő tulajdonságokat állítsa be a gombon:

- **Gomb megjelenítése**: **ImageOnly**.
- **Normál kép**: Ez a tulajdonság nem lehet üres. Például használja a **CoffeeScript** elemet.
- **Szöveg**: Ez a tulajdonság üres kell legyen.
- **Szélesség**: **Automatikus**.
- **Magasság**: **Automatikus**.

![Lapos gomb.](media/pfe-styles-flat-button.png)

## <a name="combo-box"></a>Kombinált lista

A kombinált lista három vezérlőelem együttesét jelenti: egy beviteli vezérlő, egy beviteli vezérlőt törlő a gomb, valamint egy, a keresést futtató gomb.

A stílusokat csak akkor lehet alkalmazni kombinált listákra, ha teljesülnek a következő követelmények:

- A kombinált lista egy űrlapcsoporthoz tartozik.
- A csoportnév a **Combobox** kifejezéssel kezdődik.
- A csoporton belül az első vezérlő egy **AxFormStringControl** vezérlő. Ez a vezérlő mutatja az aktuális értéket, és itt adja meg a felhasználó a szükséges értéket.
- A második vezérlő egy **CommonButton** vezérlő, a neve **ClearButton** értékkel kezdődik. Ennek a gombnak olyan kódot kell tartalmaznia, amely a gomb megjelenítéséhez vagy elrejtéséhez az **engedélyezés** tulajdonságot használja. Ha például, amikor a felhasználó a beviteli vezérlőbe beír egy adatokat, megjeleníti vagy elrejti a **Törlés** gombot, használhatja a következő kódot.

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

    A **Törlés** gomb **rákattintott** metódusa esetén a következő kódot használja.

    ```xpp
    public void clicked()
    {
        element.setSerialId('');
        InventSerialId.setFocus(); // set focus back to the input box
    }
    ```

    A beviteli vezérlő **AxFormStringControl** értékét állítsa be, ha az űrlap inicializálása az **init** módszerrel történik. Ha az érték nem üres, engedélyezze a **Törlés** gombot. Ha az érték nem üres letiltja a **Törlés** gombot.

- A harmadik vezérlő egy **CommonButton** vezérlő, a neve **SearchButton** értékkel kezdődik.

A következő ábra két kombinált lista vezérlőelemet mutat be. A bal oldali kombinált listában egy üres szövegmező található, és a **Törlés** gomb nincs engedélyezve. A jobb oldali kombinált listában egy szövegmezőben szöveg található, és a **Törlés** gomb engedélyezve van.

![Kombinált listák Törlés gombbal és anélkül.](media/pfe-styles-combo.png)

## <a name="quick-filter"></a>Gyorsszűrő

A gyorsszűrő-vezérlő keresési mezőt ad az oldalhoz. A stílusokat akkor alkalmazhatja gyorsszűrőkre, ha teljesülnek a következő követelmények:

- A gyorsszűrő egy űrlapcsoporthoz tartozik.
- A csoportnév a **SearchInputGroup** kifejezéssel kezdődik.
- A csoporton belül az első vezérlő egy **QuickFilter** vezérlő. (Itt adja meg a felhasználó a keresési karakterláncot.)
- A második vezérlő a **NumberOfResults** nevű **FormStaticTextControl** vezérlő. (Nem kötelező, és a megtalált cikkek számát megjeleníti, ha része.)
- A harmadik vezérlő egy **CommonButton** vezérlő, amelynek neve a **ClearButton** értékkel kezdődik.

A következő ábra két gyorsszűrő vezérlőelemet mutat be. A bal oldalon látható gyorsszűrő üres gyorsszűrővel rendelkezik, és az eredmények száma nem látható. A jobb oldalon található gyorsszűrő egy keresési sztringet tartalmaz, amely megjeleníti az eredmények számát.

![Példák gyorsszűrő vezérlőre keresési sztringgel és anélkül.](media/pfe-styles-quick-filter.png "Példák gyorsszűrő vezérlőre keresési sztringgel és anélkül")


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
