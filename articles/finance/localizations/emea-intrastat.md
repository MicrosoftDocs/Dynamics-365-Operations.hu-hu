---
title: Intrastat – áttekintés
description: Ez a cikk információt biztosít az Intrastat árukereskedelemről és esetenként az Európai Unió (EU) országainak/régióinak szolgáltatásairól szóló jelentésekről.
author: mrolecki
ms.date: 11/30/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: Intrastat
audience: Application User
ms.reviewer: kfend
ms.custom:
- "28581"
- intro-internal
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: mrolecki
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 762de8a098c61bc0d717c038d6ca0ff6d649bff3
ms.sourcegitcommit: 2804b05214c87f76457608b5db072582ff339852
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/01/2022
ms.locfileid: "9815711"
---
# <a name="intrastat-overview"></a>Intrastat – áttekintés

[!include [banner](../includes/banner.md)]

Ez a cikk információt biztosít az Intrastat árukereskedelemről és esetenként az Európai Unió (EU) országainak/régióinak szolgáltatásairól szóló jelentésekről. Ez a cikk áttekintést nyújt a jelentéskészítési folyamatról, valamint ismerteti a szükséges beállításokat és előfeltételeket.

Az Intrastat az Európai Unió (EU) országai/régiói közötti kereskedelemről adatokat gyűjtő és statisztikákat készítő rendszer. Intrastat-jelentés szükséges minden olyan esetben, amikor egy termék egy másik EU ország/régió határát átlépi. Az Intrastat-jelentés több országban/régióban szolgáltatásokra is vonatkozik. Az Intrastat-jelentésben kötelező és választható elemek gyűjthetők. A következő elemek kötelezőek: az információszolgáltatásért felelős fél adószáma, a referencia-időszak, a forgalom iránya (beérkezés vagy feladás), a nyolc számjegyű vámtarifakód, a partner tagállam (a partner tagállam a bizományosi ország érkezéskor és a partner tagállam a rendeltetési tagállam a feladáskor), a termékek értéke, a termékek mennyisége (nettó súly és kiegészítő egység) és az ügylet jellege. Országok/régiók opcionális elemeket is gyűjthetnek különböző feltételek mellett. Néhány választható elem: származási ország/régió, a szállítási feltételek, szállítási mód, CN8-nál részletesebb vámtarifaszám, a származási régió kiszállításkor és a rendeltetési régió beérkezéskor, a statisztikai eljárás, a statisztikai érték, az áruk leírása, valamint a be vagy kirakodó kikötő/reptér.

## <a name="overview-of-the-intrastat-reporting-process"></a>Az Intrastat jelentési folyamat áttekintése
Az alábbi szakaszok leírják az Intrastat-jelentéshez használt teljes információáramlást.

### <a name="enter-a-transaction-that-crosses-the-border-of-another-eu-countryregion"></a>Egy másik EU ország/régió határát átlépő tranzakció megindítása.

Vevői számla, szabadszöveges számla, beszerzési számla, projekt számla, vevői szállítólevél, szállítói termékbevételezés vagy átmozgatási rendelés csak akkor kerül át az Intrastat-naplóba, ha a célország/régió típusa (elküldéskor) vagy a bizományosi ország típusa (érkezéskor) **EU**. Ez a funkció a Microsoft Dynamics 365 for Operations 1611-es verziójában kiterjesztésre került, és lehetővé teszi egy közösségen belüli tranzakciónál berakodási címek megadását. Ha egy berakodási cím eltér a szállító céges címétől (vagy visszárurendelés esetén vevő üzleti címétől), az Intrastat-jelentések figyelembe veszik ezt az információt. Értékesítési rendelés, szabadszöveges számla, beszerzési rendelés, szállítói számla, projekt számla vagy átmozgatási rendelés létrehozásakor bizonyos külkereskedelemhez kapcsolódó mezők alapértelmezett értékkel rendelkeznek a dokumentum fejlécében vagy a sorban. Az alapértelmezett tranzakciókód a **Külkereskedelmi paraméterek** oldal megfelelő mezőjéből származik. Az alapértelmezett vámtarifaszám, a származási ország/régió és a származási állam/tartomány a cikkről származik. Az alapértelmezett értékeket módosíthatja, és más külföldi kereskedelemmel kapcsolatos adatokat is megadhat: a statisztikai eljárást, a szállítási módot és a kikötőt.

### <a name="use-the-intrastat-journal-to-generate-information-about-trade-among-eu-countriesregions"></a>Az Intrastat-jelentés az EU országok/régiók közötti, kereskedelemmel kapcsolatos információ létrehozására szolgál

Statisztikai okokból az EU országok/régiók közötti, kereskedelemmel kapcsolatos információkat minden hónapban létre kell hozni. Tranzakciók átvihetők a szabadszöveges számlából, a vevői számlából, vevői szállítólevélből, szállítói számlából, szállítói szállítólevélből, projektszámlából vagy átmozgatási rendelésből, a **Külkereskedelmi paraméterek** oldalon felállított átviteli feltételek szerint. Másik lehetőségként a tranzakciók manuálisan is bevihetők. Ha frissítés szükséges, az átvitt tranzakciók manuálisan frissíthetők az Intrastat-naplóban. Bizonyos feltételek fennállása esetén, amelyek a **Az Intrastat tömörítése** lapon találhatóak, az Intrastat-naplóban található tranzakciók tömöríthetők. Egyes országokban/régiókban kis tranzakciós küszöb alkalmazható. Ezután a meghatározott árukód alatti küszöbérték alatt lévő tranzakciók jelentése lehetővé válik. Az árukódok a megfelelő Intrastat-napló soraiban frissíthetők a **Minimális limit** beállítás alapján, amely a **Külkereskedelmi paraméterek** lapon található. Ezek a tranzakciók tömöríthetőek is, **Az Intrastat tömörítése** beállítás alapján. A tranzakció befejezettsége ellenőrizhető az Intrastat-naplóban, a **Beállításának ellenőrzése** beállításnál a **Külkereskedelmi paraméterek** lapon. A megfelelő mezők adatai a teljesség érdekében ellenőrizhetők: ország/régió, állam vagy tartomány, súly, vámtarifaszám, tranzakciókód, kiegészítő egység, port, eredet, szállítási feltételek, szállítási mód és adómentességi szám. A befejezetlen tranzakciók érvénytelenként lesznek megjelölve.

### <a name="use-the-intrastat-journal-to-report-information-about-trade-among-eu-countriesregions"></a>Az EU országok/régiók közötti kereskedelemmel kapcsolatos információ jelentésére az Intrastat-jelentés használatos.

Statisztikai okokból az EU országok/régiók közötti kereskedelemmel kapcsolatos információk jelentése minden hónapban szükséges. Az Intrastat-jelentés kinyomtatható a **Jelentésformátum-hozzárendelés** beállítások alapján, amelyek a **Külkereskedelmi paraméterek** lapon találhatóak. Elektronikus fájl is létrehozható a **Fájlformátum-hozzárendelés** beállítások alapján, amelyek a **Külkereskedelmi paraméterek** lapon találhatóak. Az Intrastat-jelentésekkel kapcsolatos további információért lásd az Intrastat-jelentésekkel kapcsolatos feladatrögzítéseket, ahol a szükséges előfeltételek is megtalálhatók:

  - Uniós Intrastat-nyilatkozat létrehozása,
  - Tranzakciók átvitele az Intrastatba,
  - Berakodási cím megadása egy Közösségen belüli tranzakcióhoz.

## <a name="prerequisites"></a>Előfeltételek
Az alábbi táblázatlista mutatja az Intrastat-jelentés előfeltételeit.

|  Előfeltételek  |  Leírás  |
|-------------------------|-------------------------|
| Címbeállítás | Állítsa be a Nemzetközi Szabványügyi Szervezet (ISO) kódjait az országokhoz/régiókhoz. |
| Jogi személy | Állítsa be az adószámokat az importhoz/exporthoz, az ágazatiszám-kiterjesztést importhoz/exporthoz, és a jogi személyhez hozzárendelt Intrastat kódot. |
| Termékkategória hierarchiája (értékesítési hierarchia, beszerzési hierarchia) | Rendelje hozzá az Intrastat vámtarifakódokat a kategória-csomópontokhoz a **Vámtarifakódok** lapon, amely **Kategóriahierarchia** oldalon található. Ha vámtarifakódot rendel egy szülőkategória-csomóponthoz, a kód a gyermekkategória-csomópontokra is vonatkozni fog. A kiválasztott vámtarifakódok elérhetőek lesznek **Kijelölt** nézetben, amennyiben kiválaszt egy vámtarifakódot a kiadott termék részleteiben, és az értékesítési rendelés, a beszerzési rendelés, és átmozgatási rendelés sorban. |
| Megjelent termék részletei | Állítsa be a kiadott termékekre vonatkozó alábbi külkereskedelmi adatokat:<ul><li>**Vámtarifakód** – Válassza ki a hozzárendelt termékkategóriából származó kiválasztott vámtarifakódok listájából vagy az Intrastat vámtarifakódok teljes listájából.</li><li>**Az statisztikai költségek százalékos értéke**</li><li>**Származási ország/régió** – Válassza ki az alapértelmezett országot/régiót, ahol az árukat beszerezték vagy előállították.</li><li>**Származási/rendeltetési állam/tartomány** – Válassza ki az alapértelmezett célállamot/céltartományt az érkezéshez és a származási államot/tartományt az elküldéshez.</li><li>**Nettó súly (kg)**</li><li>**Kihagyás – akkor**  engedélyezze ezt a paramétert, ha nem szeretné áthelyezésre az ezzel a termékkel kapcsolatos tranzakciókat az Intrastat számára.</li></ul> |
| Vevők | Állítsa be a vevő EU országbeli/régióbeli szállítási címét. |
| Szállítók | Állítsa be a szállító EU országbeli/régióbeli címét. |
| Vegyes költségek | Állítsa be a vegyes költségek kódját, hogy a számlaösszeg, a statisztikai összeg vagy mindkettő tartalmazza azt. A **Költségkódok** oldalon, a **Külkereskedelem** lapon, engedélyezze az **Intrastat számlaérték** -et, hogy a költségek összegét is tartalmazza a számlaérték, és engedélyezze **Intrastat statisztikai érték** -et, hogy a költségek összegét is tartalmazza a statisztikai érték.</br>A további tudnivalókat tekintse át a [Tranzakciókódok](#transaction-codes-and-miscellaneous-charges) és a Vegyes költségek példa szerint. |
| Elektronikus jelentés | Állítsa be az elektronikus jelentéskészítési konfigurációkat az Intrastat adatok egy olyan elektronikus fájlba történő exportálásához, amelynek formátuma megegyezik a hatóságok által kérttel, és az Intrastat fájlok felhasználóbarát, olvasható megtekintéséhez (például Microsoft Excel programban). |
| Raktárkészlet-nyilvántartás | Társítsa a szállítói számlákat a raktárkódokkal adómentességi szám kitöltésére az átmozgatási rendelés átvitelekor.</br>További tájékoztatás: Átviteli [rendelés](#transfer-order) – példa.|

## <a name="setup"></a>Beállítás
Az alábbi szakaszok leírják az Intrastat-jelentéshez szükséges beállításokat.

### <a name="set-up-all-required-intrastat-related-lists"></a>Állítsa be az összes szükséges Intrastattal kapcsolatos listát

|   Lista   |   További információk   |
|-------------------------|-------------------------|
| Árucikk-kódok | Állítson be **Vámtarifakód** típusú kategóriahierarchiát és adja meg az összes vámtarifakódot a kombinált nomenklatúra-lista alapján. Minden árucikknél a következő adatokat adja meg:<ul><li>Árucikk megnevezése és vámtarifaszám</li><li>Könnyen megjegyezhető név és/vagy a lefordított név</li><li>A további (kiegészítő) egységek jelentésének beállításai a **Külkereskedelem** lapon. A kiegészítő egységet az egységlistában választhatja ki. Megadhatja az is, hogy a kiválasztott kiegészítő egység mellett az áruk súlyát is jelenteni kell-e.</li></ul>További tájékoztatás a További egységek [között található](#additional-units) .|
| Tranzakciókódok | Állítsa be a tranzakció jellegét a saját országa/régiója követelményei szerint. Minden egyes beállított tranzakciókódhoz be kell állítania az átmozgatási rendelés és eladási/beszerzési rendelés számlaösszegének és statisztikai összegének kiszámítására vonatkozó szabályokat.<ul><li>Átmozgatási rendeléseknél a számlaösszeg és statisztikai összeg kiszámítására a következő szabályokat állítsa be:<ul><li>**Üres** – Az összeg 0 (nulla) lesz.</li><li>**Pénzügyi önköltség** – Az összeg meg fog egyezni a pénzügyi költséggel.</li><li>**Teljes költség** – Az összeg meg fog egyezni a tranzakció teljes költségével.</li><li>**Manuális** – Az összeg meg fog egyezni az átmozgatási rendelés sorában manuálisan megadott az összeggel.</li></ul></li><li>Értékesítési rendeléseknél és beszerzési rendeléseknél a számlaösszeg és statisztikai összeg kiszámítására a következő szabályokat állítsa be:<ul><li>**Üres** – Az összeg 0 (nulla) lesz.</li><li>**Számlaösszeg** – Az összeg meg fog egyezni az árucikkért számlázott összeggel.</li><li>**Alapösszeg** – Az összeg meg fog egyezni a számlázandó összeggel, bármilyen engedmény alkalmazása előtt.</li></ul></ul>A további tudnivalókat tekintse át a [Tranzakciókódok](#transaction-codes-and-miscellaneous-charges) és a Vegyes költségek példa szerint. |
| Szállítási módok | Állítsa be a szállítási módot a saját országa/régiója követelményei szerint. Minden szállítási módhoz állíthat be egy alapértelmezett szállítási módot a **Külkereskedelmi** lapon. |
| Kikötők | Állítsa be a berakodás/kirakodás kikötőjét/repülőterét, ha az országa/régiója gyűjti ezeket az adatokat. |
| Statisztikai eljárások | Állítsa be a statisztikai eljárást, ha országa/régiója gyűjti ezeket az adatokat. |



### <a name="set-up-rules-for-compressing-intrastat-transactions"></a>Állítsa be az Intrastat tranzakciók tömörítésére vonatkozó szabályokat

Az **Az Intrastat tömörítése** lapon kiválaszthatja a tömörítéshez használni kívánt mezőket. Minden tranzakció amely ugyanazokat az értékkombinációkat tartalmazza az Intrastat-napló kiválasztott mezőihez, egy tranzakcióba lesz tömörítve az Intrastat-napló Tömörítés funkciójának futtatásakor.

### <a name="set-up-foreign-trade-parameters"></a>Külkereskedelmi paraméterek beállítása

Használja a **Külkereskedelmi paraméterek** lapot az alábbi táblázatban található adatok beállításához.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Lap</th>
<th>Paraméterek</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Általános</td>
<td><ul>
<li><strong>Általános</strong> – Adja meg a következő információkat:
<ul>
<li>Az értékesítési rendelésekre, beszerzési rendelésekre, jóváírásokra és átmozgatási rendelésre vonatkozó alapértelmezett tranzakciós kódok. A jóváírásokhoz beállított tranzakciós kódok a tényleges áruk visszatérítési kódjaiként is használatosak és használatosak az eltérő tényleges visszatérítések és jóváírási helyesbítés összevetésére. A tényleges áruk visszáruzásának jelentése az Intrastat-átvitelben eltérő irányban történik. A rendszer az érkezés visszáruzását átvitelét kiszállításként jelenti, a kiszállítás visszáruzását pedig érkezésként.</li>
<li>Az Intrastat-jelentés készítésért felelős alkalmazott.</li>
</ul></li>
<li><strong>Minimumhatár</strong> – Adja meg a küszöbérték alatt lévő tranzakciók frissítési beállításait:
<ul>
<li>A küszöbösszeg és küszöbsúly</li>
<li>A küszöbérték alatt lévő tranzakcióra alkalmazandó vámtarifakód</li>
</ul></li>
<li><strong>Átvitel</strong> – Adja meg a tranzakciók Intrastat-naplóba való átvitelének feltételeit. Megadhatja, hogy a tranzakciók csak akkor kerüljenek átvitelre, amikor a cikkek megfelelnek egy, vagy az összes alábbi feltételnek.
<ul>
<li>A cikk nem szolgáltatási tétel.</li>
<li>A cikk rendelkezik vámtarifakóddal.</li>
<li>A cikk rendelkezik súllyal.</li>
<li>Cikkek rendelkezik kiegészítő egységekkel.</li>
</ul></li>
<li><strong>Beállítások ellenőrzése</strong> – Adja meg Intrastat-adatok befejezettségének ellenőrzésére vonatkozó szabályokat. Kiválaszthatja, hogy mely adatok ellenőrzöttek.</li>
<li><strong>Kerekítési szabályok</strong> – Adja meg az Intrastat-jelentésben szereplő összegek és súlyok kerekítésére vonatkozó következő beállításokat:
<ul>
<li>A kerekítési szabály (pontosság)</li>
<li>A kerekítés módja: felfelé, lefelé vagy normál</li>
<li>Az értékekre és súlyokra vonatkozó a tizedesjegyek száma</li>
<li>Útmutató az 1 kilogrammnál (kg) kisebb súlyokra vonatkozó kerekítéshez: legfeljebb 1 kg, normál vagy nincs kerekítés</li>
</ul></li>
<li><strong>Elektronikus jelentés</strong> – Adja meg a hivatkozásokat az elektronikus jelentéskészítés konfigurációihoz, így létrehozhat elektronikus fájlokat és jelentést.</li>
<li><strong>Vámtarifakódok hierarchiája</strong> – Adja meg a kategóriahierarchiáját annak a <strong>Vámtarifakód</strong> típusnak amely az Intrastat CN8 vámtarifakódot jelöli.</li>
  <li> <strong>Árfolyamtípus</strong> – Opcionális, adja meg az Intrastat értékesítési és beszerzési tranzakcióinak jelentéseihez használandó árfolyamot külföldi pénznemekben. Ez akkor használatos, ha az árfolyam eltér a tranzakció feladásakor alkalmazott árfolyamtól.</li>  
</ul></td>
</tr>
<tr class="even">
<td>Az ügynök kapcsolattartási adatai</td>
<td>Adja meg az ügynök nevét, címét, adószámát, telefonszámát és faxszámát.</td>
</tr>
<tr class="odd">
<td>Ország vagy régió tulajdonságai</td>
<td>Állítsa az aktuális jogi személy országát/régióját a következőre: <strong>Belföldi</strong>. Állítsa az EU kereskedelemben aktuális jogi személlyel résztvevő EU országok/régiók országok/régióját a következőre: <strong>EU</strong>. Az egyes országokhoz/régiókhoz, külkereskedelmi célból, adja meg az országkódot/régiókódot.</td>
</tr>
<tr class="even">
<td>Számsorozat</td>
<td>Adja meg a számsorozatot az Intrastat-naplóhoz.</td>
</tr>
</tbody>
</table>

## <a name="example"></a>Példa

### <a name="transaction-codes-and-miscellaneous-charges"></a><a name= "transaction-codes-and-miscellaneous-charges"></a> Tranzakciókódok és vegyes költségek

Ez a cikk egy olyan helyzetről ad le, amikor egy németországi vállalatnak árut kell vásárolnia egy olaszországi vállalattól. Ehhez a beszerzéshez a német vállalatnak új tranzakciókódokat kell beállítania, valamint be kell állítania a számlaösszegre és a statisztikai összegre vonatkozó számítási szabályokat. Ezenkívül amikor a vállalat számlát készít, meg kell adnia a vegyes költségeket és azok százalékos arányát. Ezeket az értékeket a rendszer figyelembe fogja venni a statisztikai érték számítása során.

Ez az eset a **DEMF jogi** személyt használja.

#### <a name="preliminary-setup"></a>Előzetes beállítás

1. Menjen a **Szervezetfelügyeleti** > **Szervezet** > **jogi személyekhez**, és válassza a **DEMF lehetőséget**.
2. Ellenőrizze a **Címek** gyors területen, **hogy az Ország/terület**  **mező beállítása DEU(Németország)**.
3. Ugrás a Kötelezettségek **szállítói** > **minden** > **szállítójához**.
4. A rácsban válassza a **DE-001 et**.
5. Válassza a **Szerkesztés** gombra a Cím **gyorsában**.
6. A **Cím szerkesztése** párbeszédpanelen az **Ország/régió** mezőben válassza ki a **ITA** lehetőséget.
7. Az **OK** gombbal zárja be a párbeszédpanelt.

#### <a name="set-up-transaction-codes"></a>Tranzakciókódok beállítása

1. Ugorjon a következőre: **Adó** > **Beállítás** > **Külkereskedelem** > **Tranzakciókódok**.
2. Válassza ki a **11** értéket a rácsban. Ezután a munkaablakban válassza a Törlés **lehetőséget**.
3. A Műveleti ablaktáblán kattintson az **Új** elemre.
4. Írja be **a 11-et**  **·** **·**  **a Tranzakciókódok gyorsgombra.**
5. A Név **mezőben** adja meg **az outright beszerzést/értékesítést**.
6. Az Értékesítés **és beszerzések** szakasz **Számlaösszeg mezőjében** válassza ki a Számla **összege lehetőséget**.
7. A Statisztikai **összeg mezőben** válassza ki a Számla **összegét**.
8. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.

#### <a name="set-up-miscellaneous-charges"></a>Vegyes költségek beállítása

1. Ugrás a Kötelezettségek **– Költségek** > **beállítása –** > **Költségek kódra**
2. A rácsban válassza a Fuvar **lehetőséget**.
3. A műveleti ablaktáblán válassza a **Szerkesztés** lehetőséget.
4. Állítsa Az **Intrastat számla értékét és az Intrastat**  **statisztikai érték beállítását a** Külkereskedelmi **gyorsnyelven** "Igen" értékre **.**

#### <a name="set-up-foreign-trade-parameters"></a>Külkereskedelmi paraméterek beállítása

1. Ugorjon a következőre: **Adó** > **Beállítások** > **Külkereskedelem** > **Külkereskedelmi paraméterek**.
2. Az **Intrastat** lapon az **Általános** gyorslapon a **Tranzakció** **kód** mezőben válassza a **11**-et.
3. Az Árucikk-kódok **hierarchiája** gyorssablonban ellenőrizze, **hogy a Kategóriahierarchia** mező beállítása **Intrastat**.

#### <a name="create-a-purchase-order"></a>Beszerzési rendelés létrehozása

1. Menjen a **Fizetendő számlák** > **Beszerzési megbízások** > **Minden beszerzési megbízás** menüpontba.
2. A Műveleti ablaktáblán kattintson az **Új** elemre.
3. A **Megrendelés létrehozása** párbeszédpanelen a **Szállítói számla** mezőben válassza a **DE-001-et**.
4. Válassza ki az **OK** lehetőséget.
5. A **Fejléc** lap **Kül** **kereskedelmi** gyorslapon ellenőrizze, hogy a **Tranzakciókód** mezőben **11** van-e beállítva.
6. A **Sorok** lapon, a **Beszerzési rendelés sorai** gyorslapon a **Tételszám** mezőben válassza a **D0003-et**. Ezután a **Mennyiség** mezőbe írjon be **10**-et.
7. Ellenőrizze **a**  **·**  **Tranzakciókód mező automatikus beállítását a Külkereskedelem lap Sor részletei gyorslapJán,**  **a Külkereskedelem** szakaszban.
8. Válassza **a**  **·**  **Költségek** szakasz Pénzügyi menüjének Beszerzési rendelés sorai gyorsjelentési csoportban a Költségek **karbantartása lehetőséget.**
9. A Költségkód **mezőben** válassza a FUVAR **lehetőséget**.
10. A Költségek értékmezőben **adja** meg **a 30-as értéket**.
11. A műveleti ablaktáblán válassza a **Mentés** lehetőséget. Ezután zárja be az oldalt.
12. A Műveletpanelen, a **Vásárlás** lapon, a **Műveletek** csoportban válassza a **Megerősítés** lehetőséget.
13. A Műveleti ablaktábla **Számla** lapján a **Létrehozás** csoportban válassza a **Számla** lehetőséget.
14. A Műveletpanelen válassza az **Alapértelmezettet**. A **Sorok alapértelmezett mennyisége** mezőben válassza a **Megrendelt mennyiséget**. Majd kattintson az **OK** lehetőségre.
15. A **Szállítói számla fejléc** gyorslap, a **Számla azonosítása** szakaszában a **Szám** mezőbe írja be a **00100-es** számot.
16. Válassza a **Számladátum**  **szakasz Számladátum mezőjében**  **a 2021.02.11. dátumot (2021** . november 24. ).
17. A Művelet ablaktáblán válassza a **Feladás** lehetőséget a számla könyveléséhez.

### <a name="transfer-the-vendor-invoice-to-the-intrastat-journal"></a>A szállítói számla átvitele az Intrastat naplóba

1. Ugorjon a következőre: **Adó** > **Nyilatkozatok** > **Külkereskedelem** > **Intrastat**.
2. A Műveletpanelen válassza az **Átvitel** lehetőséget.
3. Az **Intrastat (Átvitel)** párbeszédpanelen állítsa a **Szállítói számla** opciót **Igenre**.
4. Válassza az **OK** lehetőséget a tranzakciók átviteléhez, és tekintse át az Intrastat naplót.

   ![Az Intrastat lapon a beszerzési rendelést vegyes költségeket képviselő sor](media/intrastat_overview_1.png)

5. Tekintse át a beszerzési rendelés **Általános** lapját. Ne **feledje**  **·**  **·**, hogy a Számla értéke mezőben a Számlaösszeg és a Számla költségei összegmezőinek összege, **·**  **·**  **a Statisztikai érték mezőben pedig a Statisztikai összeg és a Statisztikai költségek összege mezők összege** látható.

   ![Beszerzési rendelés adatai vegyes költségeket tartalmazó költségeket az Intrastat lap Általános lapján](media/intrastat_overview_2.png)

### <a name="transfer-order"></a>Átmozgatási rendelés

Ebben a példában egy németországi vállalatnak két termékegységet kell áthelyeznie egy németországi raktárból egy olaszországi raktárba. A statisztikai érték mezőben 20 **százalékos költségeket is meg kell adni ehhez a termékhez a könyveléshez** . Ez a példa a **DEMF jogi** személyt használja.

#### <a name="preliminary-setup"></a>Előzetes beállítás

1. Menjen a **Szervezetfelügyeleti** > **Szervezet** > **jogi személyekhez**, és válassza a **DEMF lehetőséget**.
2. Ellenőrizze a **Címek** gyors területen, **hogy az Ország/terület**  **mező beállítása DEU(Németország)**.
3. Ugorjon a következőre: **Adó** > **Beállítások** > **Külkereskedelem** > **Külkereskedelmi paraméterek**.
4. Az Árucikk-kódok **hierarchiája** gyorssablonban ellenőrizze, **hogy a Kategóriahierarchia** mező beállítása **Intrastat**.
5. Ugrás a Kötelezettségek **szállítói** > **minden** > **szállítójához**.
6. A rácsban válassza a **DE-001 et**.
7. Válassza a **Szerkesztés** gombra a Cím **gyorsában**.
8. A **Cím szerkesztése** párbeszédpanelen az **Ország/régió** mezőben válassza ki a **ITA** lehetőséget.
9. Az **OK** gombbal zárja be a párbeszédpanelt.

#### <a name="set-up-transaction-codes"></a>Tranzakciókódok beállítása

1. Ugorjon a következőre: **Adó** > **Beállítás** > **Külkereskedelem** > **Tranzakciókódok**.
2. Válassza ki a **11** értéket a rácsban. Ezután a munkaablakban válassza a Törlés **lehetőséget**.
3. A Műveleti ablaktáblán kattintson az **Új** elemre.
4. Írja be **a 11-et**  **·** **·**  **a Tranzakciókódok gyorsgombra.**
5. A Név **mezőben** adja meg **az outright beszerzést/értékesítést**.
6. Az Áthozott **rendelés** szakaszban, a Számla **összege mezőben** válassza a Teljes **költség lehetőséget**.
7. A Statisztikai **összeg mezőben** válassza az Összköltség **lehetőséget**.
8. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.
9. Ugorjon a következőre: **Adó** > **Beállítások** > **Külkereskedelem** > **Külkereskedelmi paraméterek**.
10. Válassza a **11-et az Intrastat**  **lap** Általános gyorslap Áthozási **rendelés**  **mezőjében.**

#### <a name="set-up-charges-for-an-item"></a>Cikkek költségeinek beállítása

1. Ugorjon a következőre: **Termékinformáció-kezelés** > **Termékek** > **Felszabadított termékek**.
2. Válassza ki a rácson a **D0001**-et.
3. Adja meg **a**  **20-ast a Külkereskedelmi gyorsjelentési csoport Intrastat szakasz**  **Költségszázalék**  **mezőjében**.

#### <a name="change-the-site-address"></a>A webhely címének módosítása

1. Menjen a **Raktárkezelés** > **Beállítás** > **Raktár** > **Oldalak** pontra.
2. Válassza ki a **1** értéket a rácsban.
3. A **Címek** gyorslapon válassza a **Szerkesztés** lehetőséget.
4. A **Cím szerkesztése** párbeszédpanelen az **Ország/régió** mezőben válassza ki a **DEU** lehetőséget.
5. Válassza ki az **OK** lehetőséget.
6. Válassza ki a **2** értéket a rácsban.
7. A **Címek** gyorslapon válassza a **Szerkesztés** lehetőséget.
8. A **Cím szerkesztése** párbeszédpanelen az **Ország/régió** mezőben válassza ki a **ITA** lehetőséget.
9. Válassza ki az **OK** lehetőséget.
10. Ugorjon a **Raktárkezelés** > **Beállítás** > **Raktár** > **Raktárak** pontra.
11. Válassza ki a **21** értéket a rácsban.
12. Válassza **a**  **DE**-001 et az Általános gyorstinta csoport **Hivatkozás**  **szakaszában a Szállítói számla mezőben.**

#### <a name="create-a-transfer-order"></a>Átmozgatási rendelés létrehozása

1. Ugrás a Készletkezelés **kimenő** > **rendeléseit –** > **Átvezetési rendelés**
2. A Műveleti ablaktáblán kattintson az **Új** elemre.
3. Válassza **a**  **11**-et a Sorok lap Átátviteli rendelés fejlécének **gyorslap** Áttekintés szakaszában a **11**-es **kódot.** A Raktárba **mezőben** válassza a **21-et**.
4. Válassza a **Hozzáadás gombra** a Sorok lap Átátviteli **rendelés sorai** gyorslapon a Hozzáadás **lehetőséget**.
5. A **Cikkszám** mezőben válassza ki a **D0001** cikkszámot. Ezt követően az Áthozott **mennyiség mezőbe** írja be a **2-es mennyiséget**.
6. Ellenőrizze **a**  **·**  **Tranzakciókód mező automatikus beállítását a Külkereskedelem lap Sor részletei gyorslapJán,**  **a Külkereskedelem** szakaszban.
7. A Műveleti ablak Szállítás **lapján**, **·**  **a Műveletek csoportban válassza az Átátviteli rendelés szállítása lehetőséget.**
8. A Szállítás **párbeszédpanel** Áttekintés **lapján** **·**, a Frissítés mezőben válassza a Mind **lehetőséget**.
9. A **rendelés szállításhoz kattintson az OK** gombra.
10. A Műveleti ablakTábla **Fogadás** lapján, **a Műveletek** csoportban válassza a Fogadás **lehetőséget**.
11. A Fogadás **párbeszédpanel Áttekintés**  **lapján**  **, a Frissítés mezőben válassza a Mind** lehetőséget **.**
12. A **rendelés szállításhoz kattintson az OK** gombra.

#### <a name="transfer-the-transfer-order-to-the-intrastat-journal"></a>Át kell utalni az átrendelést az Intrastat naplóba

1. Ugorjon a következőre: **Adó** > **Nyilatkozatok** > **Külkereskedelem** > **Intrastat**.
2. A Műveletpanelen válassza az **Átvitel** lehetőséget.
3.  **Az Intrastat (Átátvitel)**  párbeszédpanelen **állítsa**  **Az** Átrendelés lehetőséget Igen, az összes többi beállítást Pedig Állítsa Nem beállításra. **·**
4. Válassza az **OK** lehetőséget a tranzakciók átviteléhez, és tekintse át az Intrastat naplót.

   ![Az intrastat oldalon található átátviteli rendelést képviselő sor](media/intrastat_overview_3.png)

5.  Tekintse át az **áthozott** rendelés Általános lapját.

    Ne figyelje meg, hogy a számlaérték és **a**  **statisztikai értékszakaszok mezői** automatikusan be vannak állítva. A Számlaösszeg **és**  **a Statisztikai** összeg mezők értékei a Tranzakciókódok lapon megadott **beállításokon alapulnak** . A Költségszázalék mezőben a 20 **érték a Kiadott termék oldalon beállított** érték. **·**  **·**  A Statisztikai költségek **összege** mező értéke a költségek mennyiségi kifejezése (mivel a 107,24-es érték 536,18 százalék 20 százalék). A Statisztikai érték **mező** értéke **a**  **Statisztikai összeg és a Statisztikai költségek összegmezőiben található értékek** összege.

  ![Átátviteli rendelés részletei az Intrastat lap Általános lapján](media/intrastat_overview_4.png)

### <a name="additional-units"></a>Kiegészítő egységek

Ebben a példában egy németországi vállalatnak 10 áruegységet kell vásárolnia egy olaszországi vállalattól. Az árucikk-kódokon kívül további egységeket is meg kell adni az ilyen cikkekhez. A példa bemutatja, hogyan lehet új mértékegységeket létrehozni, további egységeket rendelni az Intrastat vámtarifókódhoz, feladhatja a további egységeket tartalmazó tranzakciókat, és áttekintheti azt az Intrastat-naplót, amelyben a kiegészítő egységek mezője be van állítva.

#### <a name="preliminary-setup"></a>Előzetes beállítás

1. Menjen a **Szervezetfelügyeleti** > **Szervezet** > **jogi személyekhez**, és válassza a **DEMF lehetőséget**.
2. Ellenőrizze a **Címek** gyors területen, **hogy az Ország/terület**  **mező beállítása DEU(Németország)**.
3. Ugorjon a következőre: **Adó** > **Beállítások** > **Külkereskedelem** > **Külkereskedelmi paraméterek**.
4. Az **Intrastat** lapon az **Általános** gyorslapon a **Tranzakció** **kód** mezőben válassza a **11**-et.
5. Az Árucikk-kódok **hierarchiája** gyorssablonban ellenőrizze, **hogy a Kategóriahierarchia** mező beállítása **Intrastat**.
6. Ugrás a Kötelezettségek **szállítói** > **minden** > **szállítójához**.
7. A rácsban válassza a **DE-001 et**.
8. Válassza a **Szerkesztés** gombra a Cím **gyorsában**.
9. A **Cím szerkesztése** párbeszédpanelen az **Ország/régió** mezőben válassza ki a **ITA** lehetőséget.
10. Az **OK** gombbal zárja be a párbeszédpanelt.

#### <a name="create-a-unit-of-measure"></a>Mértékegység létrehozása

1. Ugrás a Szervezet felügyelete **– Beállítási** > **egységek** > **gombra** > **·**.
2. A Műveleti ablaktáblán kattintson az **Új** elemre.
3. A Mértékegység **mezőbe** írja be a mértékegység nevét. Ebben a példában adja meg a **GRM-et**.
4. Az Általános **gyorslap** **Osztályozás** szakaszában, **az** Egységosztály mezőben válassza ki az egység mértékegységét. Ebben a példában válassza a Tömeges **lehetőséget**.
5. Az Egységek **rendszere mezőben** válassza ki azt a mértékegységrendszert, amelyhez az egység tartozik. Például válassza ki a metrikus **mértékegységeket**.

#### <a name="set-up-unit-conversions"></a>Egységátváltások beállítása

1. Ugrás a Szervezetfelügyelet **–** > **Beállítási egységek** > **egységátváltásai** > **beállításához**.
2. Az Osztályközi átalakítások lapon **válassza az Új lehetőséget**  **.**
3. Az Egységátváltás **párbeszédpanel** Termék **mezőjében** válassza az **F00007 lehetőséget**.
4. A From **Unit mezőben** válassza ki az ea **lehetőséget**.
5. A To egység **mezőben** válassza a **GRM-et**.
6. Győződjön meg róla, hogy az átváltási árfolyam **1 = 1**.
7. Válassza ki az **OK** lehetőséget.
8. Ugorjon a következőre: **Termékinformáció-kezelés** > **Termékek** > **Felszabadított termékek**.
9. Válassza ki a rácson a **F00007**-et.
10. Válassza a **GRM** gombra a Készlet **gyorsétét**  **gombra** a Készlet szakaszban, az **Egység mezőben**.
11. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.

#### <a name="set-up-product-information"></a>Termékinformációk beállítása

1. Ugorjon a következőre: **Termékinformáció-kezelés** > **Termékek** > **Felszabadított termékek**.
2. Válassza ki a rácson a **F00007**-et.
3. A **Külkereskedelem** gyorslapon az **Intrastat** szakaszban, az **Árucikk** mezőben válassza a **920 20 34** kódot.
4. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.

#### <a name="assign-the-additional-unit-to-an-intrastate-commodity-code"></a>A kiegészítő egység hozzárendelése intrastate árucikk-kódhoz

1. Menjen a **Termékinformációk kezelése** > **Beállítás** > **Kategóriák és attribútumok** > **Kategóriahierarchiák** pontra.
2. Válassza ki a listából az **Intrastatt**.
3. A rácsban válassza a Kijelölés **lehetőséget**.
4. Válassza a **GRM gombra a** Külkereskedelem gyorsmező **További** egységek **mezőjében**.
5. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.

   További tájékoztatás: Mértékegységek [kezelése](../../supply-chain/pim/tasks/manage-unit-measure.md).

#### <a name="create-a-purchase-order"></a>Beszerzési rendelés létrehozása

1. Menjen a **Fizetendő számlák** > **Beszerzési megbízások** > **Minden beszerzési megbízás** menüpontba.
2. A Műveleti ablaktáblán kattintson az **Új** elemre.
3. A **Megrendelés létrehozása** párbeszédpanelen a **Szállítói számla** mezőben válassza a **DE-001-et**.
4. Válassza ki az **OK** lehetőséget.
5. A **Fejléc** lap **Kül** **kereskedelmi** gyorslapon ellenőrizze, hogy a **Tranzakciókód** mezőben **11** van-e beállítva.
6. A **Sorok** lapon, a **Beszerzési rendelés sorai** gyorslapon a **Tételszám** mezőben válassza a **F00007-et**. Ezután a **Mennyiség** mezőbe írjon be **10**-et.
7. A Sor **részletei gyorslap** Külkereskedelem **lapján**, a Külkereskedelmi **szakaszon ellenőrizze,**  **·**  **hogy be van-e állítva automatikusan a Tranzakciókód és a Vámtariat mező.** 
8. A Műveletpanelen, a **Vásárlás** lapon, a **Műveletek** csoportban válassza a **Megerősítés** lehetőséget.
9. A Műveleti ablaktábla **Számla** lapján a **Létrehozás** csoportban válassza a **Számla** lehetőséget.
10. A Műveletpanelen válassza az **Alapértelmezettet**. A **Sorok alapértelmezett mennyisége** mezőben válassza a **Megrendelt mennyiséget**. Majd kattintson az **OK** lehetőségre.
11. Adja meg **a**  **·**  **·**  **VE-0010 számot a Szállítói számla fejlécének gyorskódja területen a Számlaazonosító szakasz Szám mezőjében.**
12. Válassza a **Számladátum**  **szakasz Számladátum mezőjében**  **a 2021. február 10.-ét (2021** . október 5.).
13. A Művelet ablaktáblán válassza a **Feladás** lehetőséget a számla könyveléséhez.

#### <a name="transfer-the-vendor-invoice-to-the-intrastat-journal"></a>A szállítói számla átvitele az Intrastat naplóba

1. Ugorjon a következőre: **Adó** > **Nyilatkozatok** > **Külkereskedelem** > **Intrastat**.
2. A Műveletpanelen válassza az **Átvitel** lehetőséget.
3. Az **Intrastat (Átvitel)** párbeszédpanelen állítsa a **Szállítói számla** opciót **Igenre**.
4. Válassza az **OK** lehetőséget a tranzakciók átviteléhez, és tekintse át az Intrastat naplót.

   ![A beszerzési rendelést képviselő sor az Intrastat oldalon](media/intrastat_overview_5.png)

5. Tekintse át a beszerzési rendelés **Általános** lapját. Ne feledje **, hogy az**  **·**  **Egység szakasz további egységeinek és Kiegészítő egység mezőinek** mennyisége automatikusan be van állítva.

   ![Beszerzési rendelés részletei az Intrastat lap Általános lapján](media/intrastat_overview_6.png)
   
## <a name="list-of-countryregion-specific-articles"></a>Ország-/régióspecifikus cikkek listája
Az alábbi táblázat felsorolja a rendelkezésre álló ország-/régióspecifikus Intrastat cikkeket.

| Ország          | Hivatkozás      |
|------------------|-----------|
| Ausztria          |[Osztrák Intrastat](emea-aut-intrastat.md)| 
| Belgium          |[Belgium – Intrastat](emea-bel-intrastat.md)|
| Cseh Köztársaság   |[Cseh Intrastat](emea-cze-intrastat.md)|
| Dánia          |[Dán Intrastat](emea-dnk-intrastat.md)|
| Észtország          |[Észt Intrastat](emea-est-intrastat.md)|
| Finnország          |[Finn Intrastat](emea-fin-intrastat.md)|
| Franciaország           |[Francia Intrastat](emea-fra-intrastat.md)|
| Németország          |[Német Intrastat](emea-deu-intrastat.md)|
| Magyarország          |[Magyar Intrastat](emea-hun-intrastat.md)|
| Olaszország            |[Olasz Intrastat](emea-ita-intrastat.md)|
| Lettország           |[Lett Intrastat](emea-lva-intrastat.md)|
| Litvánia        |[Litván Intrastat](emea-ltu-intrastat.md)|
| Hollandia      |[Hollandia – Intrastat](emea-nl-intrastat.md)|
| Lengyelország           |[Lengyelország – Intrastat](emea-pol-intrastat.md)|
| Spanyolország            |[Spanyolország – Intrastat](emea-esp-intrastat.md)|
| Svédország           |[Svéd Intrastat](emea-swe-intrastat.md)|


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
