---
title: "Konszolidált pénzügyi kimutatások létrehozása"
description: "Ez a témakör a különböző helyzeteket mutatja be, ahol konszolidált pénzügyi kimutatásokat hozhat létre."
author: aprilolson
manager: AnnBe
ms.date: 07/09/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2018-5-31
ms.dyn365.ops.version: 8.0.1
ms.translationtype: HT
ms.sourcegitcommit: 2a9ceb774a8f205e39abe6a12a0deb69dd4cb69b
ms.openlocfilehash: 76e675373212195cbe3f6cf43d128b2104f92fc6
ms.contentlocale: hu-hu
ms.lasthandoff: 08/20/2018

---

# <a name="generate-consolidated-financial-statements"></a>Konszolidált pénzügyi kimutatások létrehozása

[!include [banner](../includes/banner.md)]

Ez a témakör a különböző helyzeteket mutatja be, ahol konszolidált pénzügyi kimutatásokat hozhat létre.

## <a name="single-level-and-multilevel-consolidations-across-legal-entities"></a>Egyszintű és többszintű konszolidáció jogi személyek között
Pénzügyi jelentések segítségével való konszolidálás legegyszerűbb módja a jelentési fák használatával az adatok aggregálása a vállalatok között, amelyek azonos számlatükörrel és pénzügyi időszakokkal rendelkeznek. Az alábbiakban találhatók a magas szintű lépések a konszolidáláshoz jelentési fa segítségével.

1. Hozzon létre sordefiníciót, és győződjön meg arról, hogy minden vállalatnál az összes megfelelő számla szerepel a sorokban.
2. Hozzon létre egy oszlop definíciót, amely a létrehozandó jelentéshez szükséges összes oszlopot tartalmazza.
3. Hozzon létre jelentési fát, amely a konszolidált jelentésben használt minden vállalathoz egy jelentési csomópontot tartalmaz.

> [!TIP]
> A jelentési fák, sordefiníciók és oszlopdefiníciók létrehozásával és kezelésével kapcsolatos további tudnivalókért tekintse meg a [pénzügyi jelentés-összetevőket](../../dev-itpro/analytics/financial-report-components.md).

A következő ábrán látható, hogyan kell használni egy jelentési fa definícióját a pénzügyi jelentéskészítésben arra, hogy azonosítsa az összes konszolidálandó vállalatot.

![Jelentési fa definíció](./media/reporting-tree-definition.png "Jelentési fa definíció")

Ahogy a konszolidált jelentés a következő ábrán mutatja, ha a jelentési fát egy jelentésdefinícióval használja, a vállalatokat külön-külön lehet megtekinteni. A konszolidált összegek az összegzési szinten jelennek meg.

![Összeg konszolidálása összegzés szint](./media/consolidate-amount-summary-level.png "Összeg konszolidálása összegzés szint")

Többszintű jelentési fastruktúrát szükség szerint akármennyi szinttel is létrehozhat. A következő ábrán egy többszintű jelentési fa definíció látható, amely világrégiónként görgetett összesítésekkel rendelkezik.

![Többszintű jelentési fa definíció görgetett összesítésekkel régiónként](./media/multilevel-reporting-tree-definition-roll-ups%20-worldwide-region.png "Többszintű jelentési fa definíció görgetett összesítésekkel régiónként")

A következő ábrán egy többszintű jelentési fa definíció látható, amely funkciónkénti görgetett összesítésekkel rendelkezik.

![Többszintű jelentési fa definíció görgetett összesítésekkel funkciónként](./media/multilevel-reporting-tree-definition-roll-ups%20-by-function.png "Többszintű jelentési fa definíció görgetett összesítésekkel funkciónként")

### <a name="viewing-companies-side-by-side"></a>Vállalatok megtekintése egymás mellett
Számos vevő olyan jelentéseket részesít előnyben, ahol a vállalatok egymás mellett jelennek meg, és egy oszlop mutatja a konszolidált teljes összeget. Ez a formátum könnyen elérhető a jelentési fa létrehozása után. Az alábbiakban az átfogó lépések láthatók a vállalatok egymás mellett való megtekintéséhez a konszolidált pénzügyi kimutatásokon.

1. Hozzon létre egy oszlopdefiníciót, amely tartalmazza a **pénzügyi dimenzió** oszlopot vállalatonként.
2. Használja a **jelentési egység** mezőt a fa és a jelentési egység kiválasztásához minden oszlophoz.
3. Választható: Fejlécek és összesen oszlop hozzáadása.

A következő ábrán egy oszlopdefiníció látható egymás melletti formátumban.

![Oszlopdefiníció egymás melletti formátumban](./media/column-definition-side-by-side-format.png "Oszlopdefiníció egymás melletti formátumban")

## <a name="consolidations-that-use-organization-structures-that-are-created-from-legal-entities"></a>Szervezeti struktúrákat használó konszolidációk, amelyek jogi személyekből lettek létrehozva
A szervezeti hierarchiák, amelyek dimenziókat vagy jogi személyeket tartalmaznak, dinamikusan hoznak létre jelentési fa definíciókat a pénzügyi jelentéskészítésben. Konszolidációk leegyszerűsítésének egy egyszerű módja a szervezeti hierarchia hozzáadása a jelentéshez a pénzügyi jelentéskészítésben. A pénzügyi jelentéskészítés a jelentés dátuma alapján kiválasztja a szervezeti hierarchiát az esedékesség napján vagy az előtt, ahogy az a következő ábrán látszik.

![Dinamikus jelentési fa definíció létrehozása](./media/dynamically-create-reporting-tree-definitions.png "Dinamikus jelentési fa definíció létrehozása")

## <a name="consolidations-that-involve-eliminations"></a>Eltávolításokkal járó konszolidációk
Az eltávolítási tranzakciók a konszolidációs folyamat megszokott részei. Ebben a példában öt számlát távolítunk el a konszolidáció során: 142600, 211400, 401420, 401180 és 510820. Előfordulhat, hogy az egyes vállalatok vállalatközi számláinakk beállítása eltérő. Például egyes vállalatoknál az utolsó számjegy 9, ha a számla a vállalatközi tranzakciók során használatos. A módszertől függetlenül, amennyiben ismeri a vállalatközi számlákat, megjelenítheti az eltávolításokat a konszolidált pénzügyi kimutatásain.

A következő ábrán egy konszolidált eredménykimutatás oszlopdefiníciója látható. Az egyes vállalatokra vonatkozóan meghatároztunk három vállalatközi nyereség- és veszteségszámlát a dimenziószűrő használatával. A D oszlop az eltávolítási számlákat tartalmazza, csak az USMF vállalatra vonatkozóan, és az E oszlop az eltávolításokat csak az DEMF vállalatra vonatkozóan. A D oszlop és az E oszlop úgy van beállítva, hogy **nem** kerülnek nyomtatásra a pénzügyi kimutatáson.

![Oszlopdefiníció konszolidált eredménykimutatás](./media/column-definition-consolidated-income-statement.png "Oszlopdefiníció konszolidált eredménykimutatás")

A jelentés létrehozásakor az eltávolítási összegek az F, G és H oszlopokban kerülnek kiszámításra, az összegük pedig az I oszlopban látható. A J oszlop a konszolidált összegeket mutatja meg. Ezek a konszolidációs összegek nem tartalmazzák az USMF, USRT és DEMF vállalatokra vonatkozó eltávolításokat.

> [!TIP]
> Hozzon létre egy második jelentéset, amely csak az eltávolítási bejegyzéseket tartalmazza, és használja egy olyan jelentési csoportban, amely a konszolidált jelentést is tartalmazza. Így rendelkezni fog minden olyan információval, amely bármely előírt naplóbejegyzés létrehozásához szükséges lehet.

A következő ábra a konszolidált jelentést ábrázolja.

![Konszolidált jelentés eredménykimutatás](./media/consolidated-report-income-statement.png "Konszolidált jelentés eredménykimutatás")

Akár számlákat, dimenziókat vagy mindkettőt használ, a Pénzügyi jelentéskészítés lehetővé teszi, hogy a dimenziószűrési képességek segítségével kiszűrje az eltávolítási bejegyzéseket.

## <a name="minority-interest"></a>Kisebbségi részesedés
Előfordulhat, hogy egy vállalat egy másik vállalatnak mindössze bizonyos százalékát tulajdonolja. Ebben a helyzetben egy konszolidált jelentés létrehozásakor fontos, hogy csak a vállalat által tulajdonolt százalékkal számoljon el. A Pénzügyi jelentéskészítés több lehetőséget biztosít a kisebbségi részesedés kimutatására, a felhasználói preferenciától függően. Az egyik módszer az görgetett összesítési százalék használata a jelentési fa definícióban. Egy másik módszer a kisebbségi tulajdon külön sorként való megjelenítése a jelentésben.

### <a name="using-the-reporting-tree-definition"></a>Jelentési fa definíció használata
A jelentési fa definícióban adja meg a tulajdon százalékát a **Görgetett összesítés %** oszlopban (H oszlop), ahogy a következő ábrán látható. Amikor a jelentést létrehozza, ezt a százalékot használja majd a rendszer a konszolidált összeg kiszámolásához. Ebben a példában a Contoso vállalat a Contoso Germany vállalatnak mindössze 80%-át birtokolja. Megadhat vagy **80**-at vagy **0,8**-at a **Görgetett összesítés %** oszlopban, és a konszolidált szintre csak 80% kerül továbbgörgetésre.

> [!NOTE]
> Ezt a tulajdonszázalékot bármely jelentési egység esetén alkalmazhatja, nem csak a vállalati szinten. 

![Jelentési fa definíciós százalék használata](./media/Using-reporting%20tree-definition-percentage.png "Jelentési fa definíciós százalék használata")

A jelentés létrehozásakor a Contoso Németország jelentésében az értékesítés összegének 100%-a jelenik majd meg, és az összeg 80%-át allokálják és görgetik tovább az értékesítés konszolidált szintjére.

Ha Ön a vállalat kevesebb mint 1%-t birtokolja, kijelölheti az **1%-nál kisebb görgetett összesítés engedélyezése** jelölőnégyzetet a **Jelentés beállításai** oldal **További beállítások** lapján, ahogy az a következő ábrán látható. Ebben az esetben a jelentési fa **Görgetett összesítés %** oszlopában levő értékeket úgy kezeli a rendszer, mintha kevesebb, mint 1%-ot jelentenének. Ha például **0.8**-at ad meg, a rendszer 0,8 százalékot görget a konszolidált szintre, nem 80%-ot. Alternatív lehetőségként elérheto ugyanezt az eredményt, ha nem jelöli be az **1%-nál kisebb görgetés engedélyezése** jelölőnégyzetet, és ehelyett **0,008**-at ad meg a **Görgetett összesítés %** oszlopba.

![Jelentéskészítés beállítási lehetőségei](./media/reporting-setting-options.png "Jelentéskészítés beállítási lehetőségei")

### <a name="showing-ownership-as-a-separate-row-on-the-consolidated-report"></a>A tulajdonjog külön sorként történő megjelentése a konszolidált jelentésen
A kisebbségi részesedésre vonatkozó másik lehetőség szerint minden sorban a leányvállalat 100%-át jeleníti meg a jelentésben, de kivonja a nem ellenőrző részesedést a nettó bevételből.

Ahogy a következő ábrán látható, a pénzügyi jelentésekben a kisebbségi részesedés kiszámítására a sordefinícióban egy **IF THEN ELSE** kijelentés és oszlopkorlátozás alkalmazható.

![Tulajdonrész külön sorként való megjelenítése a konszolidált jelentésen](./media/Showing-ownership-separate-row-consolidated-report.png "Tulajdonrész külön sorként való megjelenítése a konszolidált jelentésen")

## <a name="multiple-charts-of-accounts-across-legal-entities"></a>Több számlatükör jogi személyek között
Gyakran a különböző jogi személyek eltérő számlatükörrel rendelkeznek, de ettől függetlenül szeretnének konszolidált pénzügyi kimutatásokat létrehozni. Ez esetben a Pénzügyi jelentéskészítést lehet az adatok konszolidálására használni, így létrehozhatók konszolidált pénzügyi jelentések. Az alábbiakban találhatók a konszolidálás átfogó lépései, amikor eltérő számlatükör áll rendelkezésre a jogi személyek között.

1. Hozzon létre egy sordefiníciót, amely több pénzügyi dimenzióra mutató hivatkozást is tartalmaz. Minden számlatükörhöz kell tartoznia egy hivatkozásnak.
2. Az oszlopdefiníció jelentési egység korlátja segítségével rendelje hozzá a megfelelő oszlopot az egyes vállalatokhoz.


A sordefinícióban minden sor esetén több hivatkozás is adható a pénzügyi dimenziókhoz az egyes egyedi vállalati számlatükrök esetén. Az alábbi ábrán az USMF vállalat az első **Hivatkozás a pénzügyi dimenziókra** oszlopában (J oszlop) levő számlacsoportot használja, a DEMF vállalat pedig a második **Hivatkozás a pénzügyi dimenziókra** oszlopban levő számlákat (K oszlop).

> [!TIP]
> További információt a **Hivatkozás a pénzügyi dimenziókról** cellával kapcsolatban a Hivatkozás a pénzügyi dimenziókról hivatkozás meghatározása cellában talál.

![Beállított számlák első hivatkozása a pénzügyi dimenziókra](./media/set-accounts-first-Link-to-Financial-Dimensions.png "Beállított számlák első hivatkozása a pénzügyi dimenziókra")

A jelentési fa segítségével meghatározhatja, melyik pénzügyi dimenziókra mutató hivatkozást használják az egyes vállalatok a sordefinícióból. Válassza ki a sordefinícióz az E oszlopban, és majd válassza ki a megfelelő sorhivatkozást az F oszlopban, a következő ábrán látható módon.

![Alkalmazott pénzügyi dimenziók sordefiníció hivatkozása](./media/link-financial-dimensions-row-definition-used.png "Alkalmazott pénzügyi dimenziók sordefiníció hivatkozása")

> [!TIP]
> Pénzügyi dimenziókra mutató hivatkozások létrehozása esetén használja a leírást, hogy azonosítani tudja a vállalatokat, amelyekre a hivatkozások vonatkoznak. Így könnyebben kiválaszthatja a megfelelő vállalatot a jelentési fa létrehozásakor. Az oszlopdefinícióban a **Jelentési egység** mező lehetővé teszi, hogy mindegyik oszlopot a jelentési fa egy egységére korlátozza, így egymás mellett tekintheti meg az adatokat. Ha egy oszlophoz nem jelöl ki egy vállalatot sem, akkor az összes vállalatra vonatkozó konszolidált adatok jelennek meg.

## <a name="different-fiscal-calendars-across-multiple-legal-entities"></a>Különböző pénzügyi naptárak több jogi személy között
A különböző jogi személyek eltérő pénzügyi naptárral rendelkezhetnek, de ettől függetlenül kötelező számukra konszolidált pénzügyi kimutatásokat létrehozni. Kétféleképpen lehetséges a konszolidáció, ha a jogi személyek eltérő pénzügyi időszakokkal rendelkeznek:

- Hozzon létre egy oszlopdefiníciót, és az időszak és az év segítségével rendelje hozzá a megfelelő időszakokat az egyes vállalatokhoz.
- A **Beállítások** \> **Egyéb** \> **További lehetőségek** menüpontban adja meg, hogy az időszak záró dátuma vagy az időszak száma alapján szeretne konszolidálni.

Amikor oszlopdefiníciót hoz létre több, eltérő pénzügyi időszakkal rendelkező vállalat részére, fontos azt figyelembe vennie, hogy melyik vállalat szerepel majd a **Vállalat neve** mezőben a jelentésdefiníción belül. Ennek a vállalatnak a pénzügyi naptárja lesz az alap pénzügyi naptár a jelentésdefinícióban. Például az alábbi táblázat bemutatja a pénzügyi időszak beállítását az USMF és INMF vállalatok esetén. Konszolidált jelentések esetében a használandó pénzügyi naptár az USMF naptárja lesz. A „Hozzárendelés” oszlop mutatja vállalatonként a megfelelő időszakot és évet, ha jelentést 2018. június 30-án hozzák létre.

| Cég   | Pénzügyi év                                  | Hozzárendelés                     |
|-----------|----------------------------------------------|-----------------------------|
| USMF      | Pénzügyi év, július 1.–június 30.          | 12. időszak, 2018-as pénzügyi év | 
| INMF      | Naptári év, január 1.–december 31. | 6. időszak, 2018-as pénzügyi év  |

Az alábbi példában az USMF vállalat van megadva a jelentésdefiníció **Vállalat neve** mezőjében. Ezért ennek a vállalatnak a pénzügyi naptárja lesz az alap pénzügyi naptár. Ebben a példában a 2018. június 30-án létrehozott jelentésben az USMF vállalat az ALAP időszakot használja, amely a jelentésdefinícióban 12. időszakként van meghatározva. Az INMF vállalat az ALAP-6 időszakot fogja használni, ami a 6. időszak. Mindkét oszlopban a 2018. júniusi adatok szerepelnek.

![Jelentés alapidőszaka](./media/report-base-period.png "Jelentés alapidőszaka")

A következő ábra a jelentésdefinícióban található beállításokat mutatja, amelyek segítségével kiválaszthatja,, hogy a konszolidációhoz az időszak számát vagy az időszak záró dátumát használja.

![Beállítások jelentésdefiníció időszak száma](./media/options-report-definition-period-number.png "Beállítások jelentésdefiníció időszak száma")

## <a name="business-unit-consolidations"></a>Üzleti egység konszolidációi
Ez a témakör a jelentési fa defincíciók használatára és a hierarchiák Pénzügyi jelentéskészítésben való, konszolidációs célú szervezésére összpontosított. A jelentési fa segítségével üzleti egység konszolidációs jelentéseket is léterhozhat, például globális értékesítésről vagy üzemeltetésről szóló jelentéseket. Ezek a jelentések általában kötelezőek. Ezek létrehozásához minden konszolidálandó egységhez válasszon egy vállalatot és egy dimenziót. Például az alábbi példában az üzleti egység görgetett összesítése úgy volt elérhető, hogy minden egyes vállalatot megismételtek a **Vállalat** oszlopban (A oszlop) és azonosították a Részleg dimenzióértékeinek csoportját vállalatonként a **Dimenziók** oszlopban (D oszlop).

![Üzleti egység konszolidációs jelentések](./media/business-unit-consolidation-reports.png "Üzleti egység konszolidációs jelentések")

## <a name="consolidations-that-involve-multiple-reporting-currencies"></a>Több jelentési pénznemet tartalmazó konszolidációk
A pénzügyi jelentéskészítés megnövelt rugalmasságot nyújt, amikor aktuális, költségvetési, költségvetés-ellenőrzési és költségvetés-tervezési adatokat tekint meg több különböző pénznemben. A kulcsfontosságú beállítási adatok áthozásával nem kell a Pénzügyi jelentéskészítésben további beállításokat megtennie bármilyen riport, bármilyen pénznemben, bármely időpontban, bármely felhasználó általi megtekintése érdekében.

### <a name="prerequisites"></a>Előfeltételek
A lefordított egyenlegek helyes kiszámítása érdekében a Pénzügyi jelentéskészítés előírja, hogy a **Visszatartott kereseti számla** kategóriát a Visszatartott kereset számlához kell hozzárendelni a **Fő számla** listában. A pénzügyi jelentéskészítés nem támogatja a pénzügyi Visszatartott keresetek számlára való feladást. Ha a Visszatartott kereset számlára történik tranzakciók feladása, a lefordított egyenlegek nem helyesen lesznek kiszámítva. Javasoljuk, hogy a felhasználók hozzanak létre egy kiegészítő Visszatartott kereset számlát, hogy kiigazításokat adhassanak fel a Visszatartott kereset számlára.

A fő számlán a **Pénzügyi jelentéskészítés árfolyamtípusa** és **Pénznemátváltás típusa** mezőket a **Pénzügyi jelentéskészítés** gyorslapon minden egyes számlához be kell állítani, ahogy az a következő ábrán látszik. Ezt a feladatot számlánkénti alapon is végrehajthatja, vagy használhatja a számlasablonokat a legörgetendő módosításokhoz.

- A **Pénzügyi jelentéskészítés árfolyamtípusa** mezőben válassza ki azt az árfolyamtípust, amely a számlára vonatkozó pénznemeket és árfolyamokat is tartalmazza. Ezt a pénznemekről és árfolyamokról szóló táblát a Pénzügyi jelentéskészítés tényleges adataira alkalmazzák majd.
- A **Pénznemátváltás típusa** mezőben válassza ki a számlához tartozó árfolyamok kiszámításához használt módszert. Ezt a pénznemmódszert alkalmazzák a tényleges és költségvetési adatokra a Pénzügyi jelentéskészítésben.

![Pénzügyi jelentéskészítés fő számlák](./media/Financial-reporting-main-accounts.png "Pénzügyi jelentéskészítés fő számlák")

A költségvetési, a költségvetés-ellenőrzési és a költségvetés-tervezési adatok esetén az árfolyamtípust a **Főkönyv** oldalon határozzák meg. Ezt a táblát használják az árfolyamok lehívására, és azt pénznemátváltási típust használják, amely a számlához van rendelve.

### <a name="currency-translation-methods"></a>Pénznemátváltás módszere
A pénzügyi jelentéskészítésben az árfolyamok kiszámításához négy lehetőség közül választhat:

- **Súlyozott átlag** – Ezt a módszert használják leggyakrabban az eredményszámlák esetén. A következő képletet használja:

    (Árfolyam x Hatályos napok) ÷ napok száma az időszakban

- **Átlag** – Ez a módszer egy alternatív megoldás az eredményszámlák esetén. A következő képletet használja:

    Árfolyamok összesen ÷ árfolyamok száma összesen

- **Aktuális** – Ezt a módszert használják leggyakrabban mérlegszámlák esetében. Az az árfolyamtípus, amely a Pénzügyi jelentés jelentésében vagy oszlopában található adott napon vagy azt megelőző napon használatban volt.
- **Tranzakciós dátum** – Ezt a módszert használják a tárgyieszköz-számlákhoz. Az eszköz beszerzésének napján használt árfolyam. Ha adott dátumhoz nincs árfolyam megadva, akkor az eszköz beszerzési dátumához legközelebb megadott, korábbi árfolyam kerül alkalmazásra.

### <a name="report-designer-options-for-currency-translation"></a>Jelentéstervező lehetőségei devizaátváltásra
A Pénzügyi jelentéskészítésben bármelyik jelentést meg lehet jeleníteni tetszőleges számú jelentési pénznemben. A jelentésdefiníció következő mezői támogatják ezt a funkciót:

- A **Jelentésdefiníció** oldal **Pénznem-információ** szakasza Ebben a szakaszban az a pénznem látható, amelyben a jelentés létrehozásakor az értékek megjelennek.
- Egy új **Összes jelentési pénznem mutatása** jelölőnégyzet. Ha ez a jelölőnégyzet be van jelölve, akkor a vállalat funkcionális pénznemét használó jelentés létrehozása után minden egyes jelentési pénznemnek megfelelő jelentés is hozzáadásra kerül a jelentési sorhoz. Ha a jelölőnégyzet nincs bejelölve, a Webes megjelenítőben még kiválaszthat egy jelentési pénznemet. Ebben az esetben a jelentési pénznem csak akkor kerül feldolgozásra, ha kijelöli.

Jelentésdefiníció beállításai lehetővé teszik a jelentés egyszerűen átváltását az összes jelentési pénznemre. Így eltávolíthatja a duplikált jelentésdefiníciókat, amelyek csak a használt pénznemben térnek el. Ha olyan jelentésre van szüksége, amely több pénznemet egymás mellett jelenít meg, akkor továbbra is használhatja a **Pénznem megjelenítése** mezőt az **Oszlopdefiníció** oldalon, amivel csak a jelentés adott oszlopát alternatív jelentési pénznemekre válthatja át.

### <a name="currency-translation-adjustment"></a>Pénznemátváltás kiigazítása
A pénznemátváltási kiigazítás (CTA - currency translation adjustment) azt a különbséget jelenti, amely segítségével a mérlegszámlát és a használt árfolyamot lehet kiszámítani a bevételi kimutatási számlákhoz. Ez a különbség azt okozza, hogy a mérleg nem lesz egyensúlyban. A Pénzügyi jelentéskészítésben a CTA-t kétféleképpen lehet kiszámítani:

- Alkalmazza a **Kerekítési kiigazítás** oldalt a sordefinícióban, ahogy az a következő ábrán látható.

    ![Pénznemátváltási kiigazítás kerekítési kiigazítás](./media/Currency-translation-adjustment-rounding-adjustments.png "Pénznemátváltási kiigazítás kerekítési kiigazítás")

    Ha olyan sort határoz meg, amely megjeleníti a kerekítési kiigazítást (CTA), az összes eszköz sort, az összes kötelezettség és saját tőke sort és egy olyan küszöbértéket, amely Önnek megfelel, a Pénzügyi jelentéskészítés kiszámítja a különbséget és a kívánt sorba illeszti. Létrehoz egy **Kerekítési kiigazítás** sort, és a leásás esetén jeleníti meg, ahogy az a következő ábrán látható.

    ![Kerekítési kiigazítás leásás](./media/rounding-adjustment-drill-down.png "Kerekítési kiigazítás leásás")

- Az összes számla egy tartományba helyezése, eszközöktől költségekig. Ahogy a következő ábrán látható, a különbség értéke ugyanakkora összeg lesz, mint a kerekítési kiigazítás (CTA) értéke. Így ezt egy ellenőrző végösszegként is használhajta annak biztosítására, hogy a kerekítési kiigazítás oldal nem tartalmaz olyan számlaegyenlegeket, amelyeket kihagyott.

    ![Kerekítési kiigazítási űrlap ellenőrzése](./media/rounding-adjustment-form-check.png "Kerekítési kiigazítási űrlap ellenőrzése")

### <a name="balance-calculation-approach"></a>Egyenlegszámítási megközelítés
Annak érdekében, hogy a pénznemek használatakor helyesen átváltott összegeket kapjon, a Pénzügyi jelentéskészítés a következő számítási módszereket alkalmazza az egyenlegekhez:

- **Súlyozott átlag és átlag** – Minden egyes időszakot annak súlyozott átlagával számít, és negyedéves valamint év eleje óta oszlopokba kerül összesítésre.
- **Korábbi** – Minden olyan számla, amely a korábbi átváltási módszert használja, mindig a tranzakciós dátumig megy vissza. Ha a tranzakcióhoz beszerzési dátum van társítva, akkor az árfolyam meghatározásakor ezt a dátumot használja a rendszer. Ezután minden időszakot összesít a rendszer, és tárolja őket, hogy javítsa a kiszámítási időt.
- **Aktuális** – Kiszámított, és az összesen oszlopok (mint a negyedéves és év eleje óta számított összegek oszlopai) az azonnali árfolyamon kerülnek kiszámításra, amelyet az oszlopban vagy a jelentésen meghatároztak. Például az **1. negyedév** oszlop március 31-ei árfolyamot használ majd, ha naptári évet használ a rendszer.

## <a name="additional-resources"></a>További erőforrások

További információért a konszolidációról, és a pénznem átváltásokhoz tekintse meg jelen témakör szülő témakörét, [Pénzügyi konszolidáció és devizaátváltás](./financial-consolidations-currency-translation.md).

A konszolidáció részleteinek online úton történő megadásával kapcsolatos további információkért tekintse meg a következőt: [Online konszolidáció](./consolidate-online.md).

