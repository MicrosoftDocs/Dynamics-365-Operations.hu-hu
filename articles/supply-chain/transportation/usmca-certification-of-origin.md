---
title: USMCA eredettanúsítvány
description: Ezzel a funkcióval kinyomtathatja az Egyesült Államok-Mexikó-Kanada megállapodás (USMCA) által megkövetelt eredettanúsítványokat.
author: Weijiesa
ms.date: 08/09/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSShipPlanningListPage, WHSShipmentDetails
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: weijiesa
ms.search.validFrom: 2020-10-23
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: c67fd12c31b475b323bc4c7feee4cc5267da7793
ms.sourcegitcommit: 229ea085cf35579a2631ea1e5fc2c602fa47e3f3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/24/2022
ms.locfileid: "9714699"
---
# <a name="usmca-certification-of-origin"></a>USMCA eredettanúsítvány

[!include [banner](../includes/banner.md)]

Ezzel a funkcióval kinyomtathatja az Egyesült Államok-Mexikó-Kanada megállapodás (USMCA) által megkövetelt eredettanúsítványokat.

Az *USMCA eredettanúsítvány* tartalmazza a bevalláshoz szükséges minimális adatelemeket. Egyes adatelemek nyomtatás előtt előre kitölthetők, míg másokat nyomtatás után manuálisan kell kitölteni. A preferenciális tarifakezelés érdekében a dokumentumot a nyilatkozat megtételének időpontjában ki kell tölteni, és az importőr birtokában kell lennie. A dokumentumot az importőr, az exportőr vagy a termelő is kitöltheti.

Egyetlen szállítmány bizonylatát a **Minden szállítmány** listaoldaláról vagy a **Szállítás részletei** oldalról nyomtathatja ki.

A dokumentum csak akkor érhető el, ha a jogi személy elsődleges címe az Egyesült Államokban található.

A dokumentum nyomtatási beállításától függően a dokumentum előre kitölthető a rendszerben lévő adatokkal. Módosítható és hozzáadható adat a nyomtatott dokumentumhoz úgy, hogy a nyomtatott dokumentumot szerkeszthető formátumba exportálja, például Microsoft Word. Az exportálás után a szükséges módosításokat a nyilatkozat előtt alkalmazhatja.

## <a name="turn-the-usmca-feature-on-or-off"></a>Az USMCA funkció be- és kikapcsolása

A funkció használatához be kell kapcsolva lennie a rendszeren. Az Ellátásilánc-kezelés 10.0.29-es verziója szerint a funkció alapértelmezés szerint be van kapcsolva. A rendszergazdák úgy kapcsolhatják *be és kapcsolják ki ezt a funkciót, hogy a funkciókezelés munkaterületén az USMCA-tanúsítvány* eredetdokumentumot [keresi](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

## <a name="document-content"></a>Dokumentum tartalma

Az USMCA eredettanúsítvány a következő adatelemeket tartalmazza:

- Címelemek
- A tanúsító fél szerepe
- Egyetlen szállítmány
- Számlák
- Keretidőszak
- Cikk részletes adatai
- Hitelesítő aláírása
- Oldalak száma

Az elemekről és azok értékeinek a megtalálásról a jelen cikk további szakaszaiban olvashat bővebben.

## <a name="print-a-usmca-certification-of-origin-document"></a>Az USMCA eredettanúsítvány kinyomtatása

Ha egy szállítmányhoz USMCA eredettanúsítványt szeretne nyomtatni, tegye a következőket:

1. Válasszon az alábbi lehetőségek közül:
    - Menjen a Szállításkezelés **tervezéséhez \> minden \> szállítmányhoz \>**, és válassza ki azt a szállítmányt, amelyről nyomtatni szeretné a dokumentumot.
    - Nyissa meg annak a szállítmánynak a **Szállítmány részletei** oldalát, amelyhez ki szeretné nyomtatni a bizonylatot (többféleképpen is beszerezheti, többek között a **Minden szállítmány** oldalról).
1. A Művelet panelen nyissa meg a **Szállítmányok** fület, és a **Nyomtatás** csoportban válassza az **USMCA eredettanúsítvány** lehetőséget.
1. Megnyílik az **Eredettanúsítvány** párbeszédpanel. A dokumentum létrehozásához adja meg a következő alszakaszokban leírt beállításokat, majd kattintson az **OK** gombra.
1. A dokumentum előnézeti képe jelenik meg. A Művelet panelen található parancsokkal szükség szerint kinyomtathatja vagy exportálhatja a dokumentumot.

### <a name="certifying-party"></a>Tanúsító fél

A **Tanúsító fél** legördülő lista használatával azonosíthatja a dokumentumot kinyomtató fél típusát. Adja meg, hogy a tanúsító fél *Exportőr*, *Exportőr és termelő*, *Termelő* vagy *Importőr*; vagy hagyja üresen, ha ezek közül egyik sem. A kiválasztott beállítás határozza meg, hogy mi kerül nyomtatásra a dokumentum címszakaszaiban.

A kiválasztott **Tanúsító fél** szerepelni fog a kinyomtatott dokumentumban.

A dokumentum kinyomtatható mind a bejövő, mind a kimenő szállítmányokhoz. Válassza az *Importőr* lehetőséget **Tanúsító fél** szerepként csak a bejövő szállítmányokra.

Az alábbi táblázat a dokumentumban a választott **Tanúsító fél** alapján szereplő információtípusokat ismerteti.

| Tanúsító&nbsp;fél | Leírás |
|---|---|
| *\[Üres\]* | A következő részleteket adja a dokumentumhoz:<ul><li>**A tanúsító adatai**: A szállítási raktár címadatait használja, ha rendelkezésre állnak; ellenkező esetben a szállítási hely címét használja, ha rendelkezésre áll; ellenkező esetben a Supply Chain Managementben kiválasztott jogi személy (vállalat) címét használja.</li><li>**Exportőr adatai**: Üres</li><li>**Termelő adatai**: Üres</li><li>**Importőr adatai**: Üres</li><ul>|
| *Exportőr* | A következő részleteket adja a dokumentumhoz:<ul><li>**A tanúsító adatai**: A szállítási raktár címadatait használja, ha rendelkezésre állnak; ellenkező esetben a szállítási hely címét használja, ha rendelkezésre áll; ellenkező esetben a Supply Chain Managementben kiválasztott jogi személy (vállalat) címét használja.</li><li>**Exportőr adatai**: A jogi személy címadatait használja.</li><li>**Termelő adatai**: Üres</li><li>**Importőr adatai**: A kapcsolódó értékesítési rendelés számlaszámát használja.</li><ul>|
| *Exportőr és gyártó* | A következő részleteket adja a dokumentumhoz:<ul><li>**A tanúsító adatai**: A szállítási raktár címadatait használja, ha rendelkezésre állnak; ellenkező esetben a szállítási hely címét használja, ha rendelkezésre áll; ellenkező esetben a Supply Chain Managementben kiválasztott jogi személy (vállalat) címét használja.</li><li>**Exportőr adatai**: A jogi személy címadatait használja.</li><li>**Termelő adatai**: A jogi személy címadatait használja.</li><li>**Importőr adatai**: A kapcsolódó értékesítési rendelés számlaszámát használja.</li><ul>|
| *Importőr* | A következő részleteket adja a dokumentumhoz:<ul><li>**A tanúsító adatai**: A szállítási raktár címadatait használja, ha rendelkezésre állnak; ellenkező esetben a szállítási hely címét használja, ha rendelkezésre áll; ellenkező esetben a Supply Chain Managementben kiválasztott jogi személy (vállalat) címét használja.</li><li>**Exportőr adatai**: Üres</li><li>**Termelő adatai**: Üres</li><li>**Importőr adatai**: A jogi személy címadatait használja.</li><ul>|
| *Gyártó* | A következő részleteket adja a dokumentumhoz:<ul><li>**A tanúsító adatai**: A szállítási raktár címadatait használja, ha rendelkezésre állnak; ellenkező esetben a szállítási hely címét használja, ha rendelkezésre áll; ellenkező esetben a Supply Chain Managementben kiválasztott jogi személy címét használja.</li><li>**Exportőr adatai**: Üres</li><li>**Termelő adatai**: A jogi személy címadatait használja.</li><li>**Importőr adatai**: Üres</li><ul>|

### <a name="has-various-producers"></a>Különböző gyártók

A **Tanúsító fél** legördülő lista a dokumentumban szereplő termelői adatokhoz használandó szöveget szabályozza. A következők közül választhat:

- *Különböző termelők* – A „Különböző” szöveget nyomtatja a termelő adataihoz.
- *Kérésre elérhető* – Az „Importáló hatóságok kérésére elérhető” szöveget nyomtatja a termelő adataihoz.

Ha a **Tanúsító fél** az *Exportőr és termelő* vagy a *Termelő* értékre van állítva, akkor a **Különböző termelők** beállítás felül lesz bírálva, és a termelő címadatai meg fognak egyezni a hitelesítőével.

### <a name="blanket-period"></a>Keretidőszak

Használja a **Keretidőszak kezdete** és a **Keretidőszak vége** beállításokat a keretidőszak megállapításához, miközben a dokumentum számos megegyező áru szállítmányát lefedi, attól függetlenül, hogy a dokumentum csak egy szállítmányhoz lett kinyomtatva. A keretidőszak dátumait korlátok nélkül állíthatja be, ami hozzáadódik a dokumentumhoz. Ezeket a beállításokat üresen is hagyhatja, vagy beállíthatja múltban lévő időpontra is.

### <a name="is-single-shipment"></a>Egyetlen szállítmány

Az **Eredettanúsítvány** párbeszédpanelen állítsa be az **Egyetlen szállítmány** lehetőséget az alábbi adatok valamelyikére:

- *Igen* – A számlaszám mellé hozzáadja az „Egyetlen szállítmány: Igen” értéket.
- *Nem* – Nem ad hozzá semmit.

## <a name="other-information-included-in-the-document"></a>A dokumentumban szereplő egyéb információk

Az **Eredettanúsítvány** párbeszédpanelen kiválasztott választható elemeken kívül az USMCA eredettanúsítványát, a következő alszakaszokban összefoglalt információkat és egyéni mezőket is tartalmazza. Ezen adatok egy részét a dokumentum létrehozása után manuálisan kell megadni.

### <a name="invoice-number"></a>Számla száma

A szállítólevelekhez kapcsolódó értékesítési számlák azonosítói a keretidőszaktól függetlenül rá vannak nyomtatva a bizonylatra. A számla számai az **Egyetlen szállítmány** kiválasztásának megfelelően lesznek kinyomtatva.

### <a name="item-details"></a>Cikk részletes adatai

A dokumentum több szakaszt tartalmaz, ezek konkrét elemek részleteit sorolják fel, amelyek a következők:

- **Termékváltozat száma**: A kiadott termék cikkszámának nyomtatása.

- **Leírás**: A kiadott termék leírását vagy nevét nyomtatja ki. Ha létezik leírás a felhasználó nyelvén, akkor a program az adott nyelven nyomtatja ki a leírást. Ha nem létezik ilyen leírás, akkor a program a nevet nyomtatja ki a program a felhasználó nyelvén. Ha ez a név nem létezik, akkor a cikk neve lesz kinyomtatva.

- **Harmonizált rendszer (HR) tarifaosztályzása**: A termékhez társított harmonizált tarifaütemezést nyomtatja ki. Ezeket az ütemezéseket a **Szállításkezelés \> Beállítás \> Szállítási szabvány \> Harmonizált tarifaütemezések** oldalon állíthatja be.

- **Eredetkritérium:** Ebben a szakaszban manuálisan kell megadnia az adatokat a dokumentum első kiadásakor.

- **Származási ország:** Kinyomtatja a származási országot, amelyet a **Termékinformáció-kezelés \> Beállítás \> Termékmegfelelőség \> Származási ország** (lásd [még: Származási ország)](../pim/country-of-origin.md) című témakörben talál. A származási ország ISO-kódja a szállítmány szállítási címében és a cikkben szereplő célország/-régió alapján történik. Ha nincs beállítva származási ország adat, akkor ez az érték visszaáll a **Kiadott termék \> Külkereskedelem \> Eredet** mezőben található beállításra. Ha még mindig nem talál származási országadatot, akkor a dokumentum létrehozása után manuálisan kell megadnia a származási országot.

### <a name="certifier-signature-and-date"></a>Tanúsító aláírása és dátum

Ezt a dokumentum létrehozása után manuálisan kell megadnia.

### <a name="consists-of-number-of-pages"></a>Több oldalból áll

A tanúsítványt aláíró felhasználónak a dokumentum létrehozása után manuálisan meg kell adnia az oldalak számát (ellenőrzés céljából).

### <a name="page-numbers"></a>Oldalszámok

Az aktuális oldal és a dokumentum aljára nyomtatott oldalak száma.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]