---
title: Intrastat – áttekintés
description: Ez a témakör információt biztosít az Intrastat árukereskedelemről és esetenként az Európai Unió (EU) országainak/régióinak szolgáltatásairól szóló jelentésekről. Áttekintést biztosít továbbá a jelentési folyamatot illetően és leírja a szükséges beállításokat és előfeltételeket.
author: EvgenyPopovMBS
ms.date: 01/13/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: Intrastat
audience: Application User
ms.reviewer: kfend
ms.custom:
- "28581"
- intro-internal
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: epopov
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: a5e74b43bbeae011b2cde5c29d5a05aab28ec07e
ms.sourcegitcommit: 92ff867a06ed977268ffaa6cc5e58b9dc95306bd
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/03/2021
ms.locfileid: "6340063"
---
# <a name="intrastat-overview"></a>Intrastat – áttekintés

[!include [banner](../includes/banner.md)]

Ez a témakör információt biztosít az Intrastat árukereskedelemről és esetenként az Európai Unió (EU) országainak/régióinak szolgáltatásairól szóló jelentésekről. Áttekintést biztosít továbbá a jelentési folyamatot illetően és leírja a szükséges beállításokat és előfeltételeket.

Az Intrastat az Európai Unió (EU) országai/régiói közötti kereskedelemről adatokat gyűjtő és statisztikákat készítő rendszer. Intrastat-jelentés szükséges minden olyan esetben, amikor egy termék egy másik EU ország/régió határát átlépi. Az Intrastat-jelentés több országban/régióban szolgáltatásokra is vonatkozik. Az Intrastat-jelentésben kötelező és választható elemek gyűjthetők. A következő elemek kötelezőek: az információszolgáltatásért felelős fél adószáma, a referencia-időszak, a forgalom iránya (beérkezés vagy feladás), a nyolc számjegyű vámtarifakód, a partner tagállam (a partner tagállam a bizományosi ország érkezéskor és a partner tagállam a rendeltetési tagállam a feladáskor), a termékek értéke, a termékek mennyisége (nettó súly és kiegészítő egység) és az ügylet jellege. Országok/régiók opcionális elemeket is gyűjthetnek különböző feltételek mellett. Néhány választható elem: származási ország/régió, a szállítási feltételek, szállítási mód, CN8-nál részletesebb vámtarifaszám, a származási régió kiszállításkor és a rendeltetési régió beérkezéskor, a statisztikai eljárás, a statisztikai érték, az áruk leírása, valamint a be vagy kirakodó kikötő/reptér.

## <a name="overview-of-the-intrastat-reporting-process"></a>Az Intrastat jelentési folyamat áttekintése
Az alábbi szakaszok leírják az Intrastat-jelentéshez használt teljes információáramlást.

### <a name="1-enter-a-transaction-that-crosses-the-border-of-another-eu-countryregion"></a>1. Egy másik EU ország/régió határát átlépő tranzakció megindítása

Vevői számla, szabadszöveges számla, beszerzési számla, projekt számla, vevői szállítólevél, szállítói termékbevételezés vagy átmozgatási rendelés csak akkor kerül át az Intrastat-naplóba, ha a célország/régió típusa (elküldéskor) vagy a bizományosi ország típusa (érkezéskor) **EU**. Ez a funkció a Microsoft Dynamics 365 for Operations 1611-es verziójában kiterjesztésre került, és lehetővé teszi egy közösségen belüli tranzakciónál berakodási címek megadását. Ha egy berakodási cím eltér a szállító céges címétől (vagy visszárurendelés esetén vevő üzleti címétől), az Intrastat-jelentések figyelembe veszik ezt az információt. Értékesítési rendelés, szabadszöveges számla, beszerzési rendelés, szállítói számla, projekt számla vagy átmozgatási rendelés létrehozásakor bizonyos külkereskedelemhez kapcsolódó mezők alapértelmezett értékkel rendelkeznek a dokumentum fejlécében vagy a sorban. Az alapértelmezett tranzakciókód a **Külkereskedelmi paraméterek** oldal megfelelő mezőjéből származik. Az alapértelmezett vámtarifaszám, a származási ország/régió és a származási állam/tartomány a cikkről származik. Az alapértelmezett értékeket módosíthatja, és más külföldi kereskedelemmel kapcsolatos adatokat is megadhat: a statisztikai eljárást, a szállítási módot és a kikötőt.

### <a name="2-use-the-intrastat-journal-to-generate-information-about-trade-among-eu-countriesregions"></a>2. Az Intrastat-jelentés az EU országok/régiók közötti, kereskedelemmel kapcsolatos információ létrehozására szolgál

Statisztikai okokból az EU országok/régiók közötti, kereskedelemmel kapcsolatos információkat minden hónapban létre kell hozni. Tranzakciók átvihetők a szabadszöveges számlából, a vevői számlából, vevői szállítólevélből, szállítói számlából, szállítói szállítólevélből, projektszámlából vagy átmozgatási rendelésből, a **Külkereskedelmi paraméterek** oldalon felállított átviteli feltételek szerint. Másik lehetőségként a tranzakciók manuálisan is bevihetők. Ha frissítés szükséges, az átvitt tranzakciók manuálisan frissíthetők az Intrastat-naplóban. Bizonyos feltételek fennállása esetén, amelyek a **Az Intrastat tömörítése** lapon találhatóak, az Intrastat-naplóban található tranzakciók tömöríthetők. Egyes országokban/régiókban kis tranzakciós küszöb alkalmazható. Ezután a meghatározott árukód alatti küszöbérték alatt lévő tranzakciók jelentése lehetővé válik. Az árukódok a megfelelő Intrastat-napló soraiban frissíthetők a **Minimális limit** beállítás alapján, amely a **Külkereskedelmi paraméterek** lapon található. Ezek a tranzakciók tömöríthetőek is, **Az Intrastat tömörítése** beállítás alapján. A tranzakció befejezettsége ellenőrizhető az Intrastat-naplóban, a **Beállításának ellenőrzése** beállításnál a **Külkereskedelmi paraméterek** lapon. A megfelelő mezők adatai a teljesség érdekében ellenőrizhetők: ország/régió, állam vagy tartomány, súly, vámtarifaszám, tranzakciókód, kiegészítő egység, port, eredet, szállítási feltételek, szállítási mód és adómentességi szám. A befejezetlen tranzakciók érvénytelenként lesznek megjelölve.

### <a name="3-use-the-intrastat-journal-to-report-information-about-trade-among-eu-countriesregions"></a>3. Az EU országok/régiók közötti kereskedelemmel kapcsolatos információ jelentésére az Intrastat-jelentés használatos.

Statisztikai okokból az EU országok/régiók közötti kereskedelemmel kapcsolatos információk jelentése minden hónapban szükséges. Az Intrastat-jelentés kinyomtatható a **Jelentésformátum-hozzárendelés** beállítások alapján, amelyek a **Külkereskedelmi paraméterek** lapon találhatóak. Elektronikus fájl is létrehozható a **Fájlformátum-hozzárendelés** beállítások alapján, amelyek a **Külkereskedelmi paraméterek** lapon találhatóak. Az Intrastat-jelentésekkel kapcsolatos további információért lásd az Intrastat-jelentésekkel kapcsolatos feladatrögzítéseket, ahol a szükséges előfeltételek is megtalálhatók:

-   Uniós Intrastat-nyilatkozat létrehozása,
-   Tranzakciók átvitele az Intrastatba,
-   Berakodási cím megadása egy Közösségen belüli tranzakcióhoz.

## <a name="prerequisites"></a>Előfeltételek
Az alábbi táblázatlista mutatja az Intrastat-jelentés előfeltételeit.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Előfeltételek</th>
<th>Leírás</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Címbeállítás</td>
<td>Állítsa be a Nemzetközi Szabványügyi Szervezet (ISO) kódjait az országokhoz/régiókhoz.</td>
</tr>
<tr class="even">
<td>Jogi személy</td>
<td>Állítsa be az adószámokat az importhoz/exporthoz, az ágazatiszám-kiterjesztést importhoz/exporthoz, és a jogi személyhez hozzárendelt Intrastat kódot.</td>
</tr>
<tr class="odd">
<td>Termékkategória hierarchiája (értékesítési hierarchia, beszerzési hierarchia)</td>
<td>Rendelje hozzá az Intrastat vámtarifakódokat a kategória-csomópontokhoz a <strong>Vámtarifakódok</strong> lapon, amely <strong>Kategóriahierarchia</strong> oldalon található. Ha vámtarifakódot rendel egy szülőkategória-csomóponthoz, a kód a gyermekkategória-csomópontokra is vonatkozni fog. A kiválasztott vámtarifakódok elérhetőek lesznek <strong>Kijelölt</strong> nézetben, amennyiben kiválaszt egy vámtarifakódot a kiadott termék részleteiben, és az értékesítési rendelés, a beszerzési rendelés, és átmozgatási rendelés sorban.</td>
</tr>
<tr class="even">
<td>Megjelent termék részletei</td>
<td>Állítsa be a kiadott termékekre vonatkozó alábbi külkereskedelmi adatokat:
<ul>
<li><strong>Vámtarifakód</strong> – Válassza ki a hozzárendelt termékkategóriából származó kiválasztott vámtarifakódok listájából vagy az Intrastat vámtarifakódok teljes listájából.</li>
<li><strong>Az statisztikai költségek százalékos értéke</strong></li>
<li><strong>Származási ország/régió</strong> – Válassza ki az alapértelmezett országot/régiót, ahol az árukat beszerezték vagy előállították.</li>
<li><strong>Származási/rendeltetési állam/tartomány</strong> – Válassza ki az alapértelmezett célállamot/céltartományt az érkezéshez és a származási államot/tartományt az elküldéshez.</li>
<li><strong>Nettó súly (kg)</strong></li>
<li><strong>Kihagyás</strong> - annak engedélyezése, hogy ez a paraméter ne továbbítsa az ezzel a termékkel kapcsolatos tranzakciókat az Intrastat számára</li>
</ul></td>
</tr>
<tr class="odd">
<td>Vevők</td>
<td>Állítsa be a vevő EU országbeli/régióbeli szállítási címét.</td>
</tr>
<tr class="even">
<td>Szállítók</td>
<td>Állítsa be a szállító EU országbeli/régióbeli címét.</td>
</tr>
<tr class="odd">
<td>Vegyes költségek</td>
<td>Állítsa be a vegyes költségek kódját, hogy a számlaösszeg, a statisztikai összeg vagy mindkettő tartalmazza azt. A <strong>Költségkódok</strong> oldalon, a <strong>Külkereskedelem</strong> lapon, engedélyezze az <strong>Intrastat számlaérték</strong> -et, hogy a költségek összegét is tartalmazza a számlaérték, és engedélyezze <strong>Intrastat statisztikai érték</strong> -et, hogy a költségek összegét is tartalmazza a statisztikai érték.</td>
</tr>
<tr class="even">
<td>Elektronikus jelentés</td>
<td>Állítsa be az elektronikus jelentéskészítési konfigurációkat az Intrastat adatok egy olyan elektronikus fájlba történő exportálásához, amelynek formátuma megegyezik a hatóságok által kérttel, és az Intrastat fájlok felhasználóbarát, olvasható megtekintéséhez (például Microsoft Excel programban).</td>
</tr>
<tr class="even">
<td>Raktárkészlet-nyilvántartás</td>
<td>Társítsa a szállítói számlákat a raktárkódokkal adómentességi szám kitöltésére az átmozgatási rendelés átvitelekor.</td>
</tr>
</tbody>
</table>

## <a name="setup"></a>Beállítás
Az alábbi szakaszok leírják az Intrastat-jelentéshez szükséges beállításokat.

### <a name="set-up-all-required-intrastat-related-lists"></a>Állítsa be az összes szükséges Intrastattal kapcsolatos listát

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Lista</th>
<th>További információk</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Árucikk-kódok</td>
<td>Állítson be <strong>Vámtarifakód</strong> típusú kategóriahierarchiát és adja meg az összes vámtarifakódot a kombinált nomenklatúra-lista alapján. Minden árucikknél a következő adatokat adja meg:
<ul>
<li>Árucikk megnevezése és vámtarifaszám</li>
<li>Könnyen megjegyezhető név és/vagy a lefordított név</li>
<li>A további (kiegészítő) egységek jelentésének beállításai a <strong>Külkereskedelem</strong> lapon. A kiegészítő egységet az egységlistában választhatja ki. Megadhatja az is, hogy a kiválasztott kiegészítő egység mellett az áruk súlyát is jelenteni kell-e.</li>
</ul></td>
</tr>
<tr class="even">
<td>Tranzakciókódok</td>
<td>Állítsa be a tranzakció jellegét a saját országa/régiója követelményei szerint. Minden egyes beállított tranzakciókódhoz be kell állítania az átmozgatási rendelés és eladási/beszerzési rendelés számlaösszegének és statisztikai összegének kiszámítására vonatkozó szabályokat.
<ul>
<li>Átmozgatási rendeléseknél a számlaösszeg és statisztikai összeg kiszámítására a következő szabályokat állítsa be:
<ul>
<li><strong>Üres</strong> – Az összeg 0 (nulla) lesz.</li>
<li><strong>Pénzügyi önköltség</strong> – Az összeg meg fog egyezni a pénzügyi költséggel.</li>
<li><strong>Teljes költség</strong> – Az összeg meg fog egyezni a tranzakció teljes költségével.</li>
<li><strong>Manuális</strong> – Az összeg meg fog egyezni az átmozgatási rendelés sorában manuálisan megadott az összeggel.</li>
</ul></li>
<li>Értékesítési rendeléseknél és beszerzési rendeléseknél a számlaösszeg és statisztikai összeg kiszámítására a következő szabályokat állítsa be:
<ul>
<li><strong>Üres</strong> – Az összeg 0 (nulla) lesz.</li>
<li><strong>Számlaösszeg</strong> – Az összeg meg fog egyezni az árucikkért számlázott összeggel.</li>
<li><strong>Alapösszeg</strong> – Az összeg meg fog egyezni a számlázandó összeggel, bármilyen engedmény alkalmazása előtt.</li>
</ul></li>
</ul></td>
</tr>
<tr class="odd">
<td>Szállítási módok</td>
<td>Állítsa be a szállítási módot a saját országa/régiója követelményei szerint. Minden szállítási módhoz állíthat be egy alapértelmezett szállítási módot a <strong>Külkereskedelmi</strong> lapon.</td>
</tr>
<tr class="even">
<td>Kikötők</td>
<td>Állítsa be a berakodás/kirakodás kikötőjét/repülőterét, ha az országa/régiója gyűjti ezeket az adatokat.</td>
</tr>
<tr class="odd">
<td>Statisztikai eljárások</td>
<td>Állítsa be a statisztikai eljárást, ha országa/régiója gyűjti ezeket az adatokat.</td>
</tr>
</tbody>
</table>

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



[!INCLUDE[footer-include](../../includes/footer-banner.md)]
