---
title: "EU értékesítési lista jelentése"
description: "Ez a cikk az Európai Uniós (EU) értékesítési listáiról nyújt tájékoztatást."
author: EvgenyPopovMBS
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: EUSalesList
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 12811
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: epopov
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: e1eff86902170401e593019ea555d9c2a4c11c04
ms.contentlocale: hu-hu
ms.lasthandoff: 04/13/2018

---

# <a name="eu-sales-list-reporting"></a>EU értékesítési lista jelentés

[!INCLUDE [banner](../includes/banner.md)]

Ez a cikk az Európai Uniós (EU) értékesítési listáiról nyújt tájékoztatást.

<a name="eu-sales-list-reporting"></a>EU értékesítési lista jelentése
-----------------------

A szállítónak, aki Közösségen belül biztosít terméket vagy szolgáltatásokat olyan cégeknek, amiket az Európai Unióban (EU) hoztak létre, kötelessége benyújtani egy Közösségen belüli termék kiszállításáról szóló nyilatkozatot (EU értékesítési lista vagy ESL). Általában az ESL-t ben kell nyújtani az adóhatóságoknak, legkésőbb az ESL-t lefedő naptári időszakot követő hónap utolsó napjáig. A szállítónak fel kell tüntetnie az ESL-ben az általános forgalmi adó (áfa) azonosító számát és ügyfelenként külön az alábbi információkat:

-   Az EU-s vevő áfa azonosító száma
-   A Közösségen belüli áruk és szolgáltatások összértéke az EU-s vevő felé, abban az időszakban. A szállítónak el kell különítenie az általános termékértékesítést a háromszög-kereskedelemtől. A háromszög-kereskedelemben a tranzakció magában foglalja az áruk közvetlen szállítását a vevőnek, a beszerző beszerzőjétől, ha mindkét fél regisztrálva van egy másik EU-tagállamban.

AZ ESL használatával minden EU-tagállam adóhatósága ellenőrizheti, hogy mennyi áfa került fizetésre minden Közösségen belüli tranzakció során. A listaelemek kombinációja és az áfa bevallások lehetővé teszik az EU-tagállamoknak, hogy információt cseréljenek a termékek EU-n belüli áramlásáról.

## <a name="overview-of-the-eu-sales-list-reporting-process"></a>AZ EU értékesítési lista jelentési folyamatának áttekintése.
EU értékesítési listához tartozó jelentéshez a következő feladatokat hajthatja végre:

-   Közösségen belüli kereskedelmi tranzakciók adatainak összegyűjtése. Egy Közösségen belüli kereskedelmi tranzakció lehet egy értékesítési számla, szabadszöveges számla, projekt-számla vagy szállítói számla. A tranzakciót az ügyfél országa/régiója alapján azonosítják. A különböző Közösségen belüli kereskedelmi tranzakciókat az EU értékesítési listába gyűjtik, ahol ezeket a megszokott formában ábrázolják. Az ESL tábla minden bejegyzése egy tranzakciót jelöl, és az ügyfél áfa azonosítóját, valamint a szállított áruk és szolgáltatások teljes értékét foglalja magában.
-   (Opcionális) **EU értékesítési lista** jelentés előnézete. Megtekintheti és ellenőrizheti az **EU értékesítési lista** jelentést egy megadott időszakra, Microsoft Excel-munkafüzet formában.
-   Az **EU értékesítési lista** jelentés létrehozása. Az **EU értékesítési lista** jelentés elektronikus fájlként jön létre, minden EU-tagállamnak egyedi formátumban. Általában egy **EU értékesítési lista** jelentés alap információkat tartalmaz a jelentő félről, valamint az áruk és szolgáltatások értékéről. Az adatok ország, és az ügyfél áfa azonosítója alapján vannak csoportosítva.
-   Az EU értékesítési lista jelentési időszakának lezárása. Miután az **EU értékesítési lista** jelentés létrejött és benyújtották a hatóságoknak, az ESL tábla bejegyzéseinek új állapota **Lezárt**lesz. Ezek a tranzakciók nem fognak szerepelni további jelentésekben.

## <a name="prerequisites"></a>Előfeltételek
Az alábbi táblázat bemutatja a munka megkezdése előtt biztosítandó előfeltételeket.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Kategória</th>
<th>Előfeltételek</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Jogi személy<strong>beállítása</strong> .</td>
<td>A jogi személy elsődleges címének egy EU tagállamban kell lennie. A <strong>Jogi személyek</strong> lapon (az eléréshez kattintson a <strong>Szervezet felügyelete</strong> &gt; <strong>Szervezetek</strong> &gt; <strong>Jogi személyek</strong> elemre) válassza ki a jogi személyt. A <strong>Címek</strong> gyorslapon hozzon létre egy címet, válassza ki az országot/régiót, valamint a cím további részeit és jelölje meg, mint <strong>Elsődleges</strong>cím. Az <strong>Adó regisztráció</strong> gyorslapon, az <strong>Adószám</strong> mezőben adja meg a vállalat adószámát.</td>
</tr>
<tr class="even">
<td><strong>Beállítás:</strong> Adómentesség azonosítási paraméterei</td>
<td>Állítsa be az adómentesség azonosítási paramétereit az <strong>Országos/területi paraméterek</strong> lapon (kattintson az <strong>Adó</strong> &gt; <strong>Beállítások</strong> &gt; <strong>Áfa</strong> &gt; <strong>Országos/területi paraméterek</strong> elemre). Minden külön országban/régióban tartózkodó ügyfélhez hozzon létre egy rekordot az oldalon, és adja meg a következő információkkal:
<ul>
<li><strong>Ország/régió</strong> – Válasszon ki egy országot/területet egy adómentességi azonosítóval.</li>
<li><strong>Forgalmi adó</strong> – Adja meg a kiválasztott ország/régió adómentességi azonosító számát (az adómentességi szám előtagja).</li>
<li><strong>Adómentességi szám ellenőrzése</strong> –Jelölje be ezt a jelölőnégyzetet a kiválasztott ország/régió adómentességi azonosítójának ellenőrzéséhez.</li>
</ul></td>
</tr>
<tr class="odd">
<td><strong>Beállítás: </strong>Adómentességi számok</td>
<td>Hozzon létre adómentességi számokat az ügyfeleinek az <strong>Adómentességi számok</strong> lapon (kattintson az <strong>Adó</strong> &gt; <strong>Beállítás</strong> &gt; <strong>Áfa</strong> &gt; <strong>Adómentességi számok</strong> elemre). Minden egyes adómentességi számhoz hozzon létre egy rekordot az oldalon, és adja meg a következő adatokat:
<ul>
<li><strong>Ország/régió </strong>– Válassza ki az ügyfél adónyilvántartásának országát/régióját.</li>
<li><strong>Adómentességi szám</strong> – Adja meg az ügyfél adómentességi számát.</li>
<li>(Opcionális) Az <strong>Ügyfél neve</strong> mezőbe írja be az ügyfele nevét.</li>
</ul></td>
</tr>
<tr class="even">
<td><strong>Beállítás: </strong>Az ügyfelek adónyilvántartása</td>
<td>Az ügyfelek adónyilvántartási adatainak beállításához nyissa meg az <strong>Összes vevő</strong> oldalt (kattintson az <strong>Értékesítés és marketing</strong> &gt; <strong>Vevők</strong> &gt; <strong>Összes vevő</strong> elemre, majd válasszon ki egy vevőrekordot, és kattintson a <strong>Beállítások</strong> &gt; <strong>Nézetváltás</strong> &gt; <strong>Részletek nézet</strong> elemre), vagy nyissa meg a <strong>Szállítók</strong> oldalt (kattintson a <strong>Beszerzések és források</strong> &gt; <strong>Szállítók</strong> &gt; <strong>Szállítók</strong> fülre, majd válasszon ki egy szállítói rekordot, és kattintson a <strong>Beállítások</strong> &gt; <strong>Nézetváltás</strong> &gt; <strong>Részletek nézet</strong> fülre). A <strong>Számlázás és szállítás</strong> gyorslapon, az <strong>Adómentességi szám</strong> mezőben válassza ki az adószámot.</td>
</tr>
<tr class="odd">
<td><strong>Beállítás: </strong>Forgalmi adó beállítása</td>
<td>Áfakódok beállítása, hogy megjelenjenek az <strong>EU értékesítési lista</strong> jelentésben, az <strong>Áfakódok</strong> lapon lehetséges (kattintson az <strong>Adó</strong> &gt; <strong>Közvetett adók</strong> &gt; <strong>Áfa</strong> &gt; <strong>Áfa-kódok</strong> fülre). A <strong>Jelentés beállítása</strong> gyorslapon, minden áfa kódnál, aminek szerepelnie kell a jelentésben, törölje a jelet a <strong>Kizárt </strong>jelölőnégyzetből. Állítsa be a cikkek forgalmiadó-paramétereit a <strong>Cikkáfacsoportok</strong> lapon (kattintson az <strong>Adó</strong> &gt; <strong>Közvetett adók</strong> &gt; <strong>Áfa</strong> &gt; <strong>Cikkáfacsoportok</strong> fülre). Minden cikkáfacsoporthoz adjon meg egy értéket a <strong>Jelentéstípus</strong> mezőben. A megadott érték határozza meg az ESL összeg oszlopot, amiben szerepel a sor összege.
<ul>
<li><strong>Üres</strong> – A sor, aminek értékét a <strong>Nem hozzárendelt érték</strong> oszlop tartalmazza.</li>
<li><strong>Cikk</strong> – A sor, aminek értékét a <strong>Cikkek értéke</strong> oszlop tartalmazza.</li>
<li><strong>Szolgáltatás</strong> – A sor, aminek értékét a <strong>Szolgáltatások értéke</strong> oszlop tartalmazza.</li>
<li><strong>Befektetés</strong> – A sor, aminek értékét a <strong>Befektetés értéke</strong> oszlop tartalmazza. Ez az oszlop csak Belgiumra értendő.</li>
</ul></td>
</tr>
<tr class="even">
<td><strong>Beállítás:</strong> ESL jelentéskészítés beállítása</td>
<td>Importáljon, vagy hozzon létre elektronikus jelentéskészítés konfigurációt az ESL számára. További tájékoztatás az elektronikus jelentés konfigurációinak létrehozásáról és karbantartásáról az elektronikus jelentési dokumentációban olvasható.</td>
</tr>
<tr class="odd">
<td><strong>Beállítás: </strong>Általános paraméterek beállítása</td>
<td>Az ESL jelentés paramétereinek beállításához nyissa meg a <strong>Külkereskedelmi paraméterek</strong> lapot (kattintson az <strong>Adó</strong> &gt; <strong>Beállítás</strong> &gt; <strong>Külkereskedelem</strong> &gt; <strong>Külkereskedelmi paraméterek</strong> fülre). Adja meg az alábbi paramétereket:
<ul>
<li><strong>EU értékesítési lista</strong> lap:
<ul>
<li><strong>Készpénzfizetési engedmény jelentése</strong> – Jelölje be ezt a jelölőnégyzetet, hogy a készpénzfizetési engedmény megjelenjen az értékben, amikor a tranzakció szerepel az ESL-ben.</li>
<li><strong>Beszerzések átvitele</strong> – Jelölje be ezt a jelölőnégyzetet, hogy a beszerzések megjelenjenek az ESL-ben.</li>
<li><strong>Fájlformátum-hozzárendelés</strong> – Válassza ki az elektronikus jelentési formátumot, mikor egy elektronikus fájl jön létre az ESL-hez.</li>
<li><strong>Jelentésformátum-hozzárendelés</strong> – Válassza ki az elektronikus jelentési formátumot, mikor egy jelentés előnézete létrejön az ESL-hez.</li>
<li><strong>Kerekítési szabály</strong> – Adjon meg egy, a kerekítéshez használandó valós számot. Az ESL összegek e szám többszörösére lesznek kerekítve.</li>
<li><strong>Kerekítési mód</strong> – Válassza ki a kerekítési módszert az ESL összegek kerekítéséhez. (<strong>Normál</strong>, <strong>Lefelé kerekítés</strong>, vagy <strong>Felfelé kerekítés</strong>).</li>
<li><strong>Minimális érték használata</strong> – Jelölje be ezt a jelölőnégyzetet, ha szeretné, hogy azok az érétkek, melyek kisebbek, mint a <strong>Kerekítési szabály</strong> értéke, felfelé legyenek kerekítve, a <strong>Kerekítési szabály</strong> értékéhez.</li>
<li><strong>Tizedesjegyek száma</strong> – Adja meg az ESL összegeiben megjelenítendő tizedesjegyek számát. (elektronikus fájlokban és <strong>ESL előnézet</strong> jelentésben egyaránt).</li>
</ul></li>
<li><strong>Országos/területi paraméterek</strong> lap: Azonosítsa az EU-tagállamokat. Minden egyes EU-tagállamhoz hozzon létre egy rekordot az oldalon, és adja meg a következő adatokat:
<ul>
<li><strong>Ország/régió</strong> – Válasszon ki egy országot/régiót.</li>
<li><strong>Ország/régió típusa</strong> – Ha az <strong>Ország/régió</strong> értéke ugyan az, mint az ország/régió, ahol a vállalat regisztrálva van, jelölje be-e <strong>Belföldi</strong> lehetőséget. Ha az <strong>Ország/régió</strong> értéke egy másik EU-tagállam, mint ahol a vállalata regisztrálva van, válassza ki az <strong>EU</strong> értéket. Ha az <strong>Ország/régió</strong> értéke nem egy EU-tagállam, válassza ki a <strong>Harmadik ország/régió</strong>értéket.</li>
</ul></li>
<li><strong>Számsorozatok</strong> lap: A sorban, ahol a <strong>Hivatkozás</strong> értéke <strong>EU értékesítési lista</strong>, válasszon ki egy számsorozat kódot.</li>
</ul></td>
</tr>
<tr class="even">
<td><strong>Kapcsolódó tranzakciók</strong></td>
<td><ul>
<li>Értékesítés regisztrálása egy másik EU-tagállambeli vevőnek.</li>
<li>Ingyenes szabadszöveges számla regisztrálása egy másik EU-tagállambeli vevőnek.</li>
<li>Projekt számla regisztrálása egy másik EU-tagállambeli vevőnek.</li>
<li>Szállítói számla regisztrálása egy másik EU-tagállambeli vevőnek.</li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="working-with-the-esl"></a>Az ESL modul használata
### <a name="collecting-information-about-intra-community-trade-transactions"></a>Közösségen belüli kereskedelmi tranzakciók adatainak összegyűjtése.

A következő típusú tranzakciók Közösségen belüli kereskedelmi tranzakcióknak minősülnek:

-   Értékesítési számlák
-   Szabadszöveges számlák
-   Projektszámlák
-   Szállítói számlák

Egy tranzakció Közösségen belüli kereskedelmi tranzakciónak minősül, ha a tranzakció szállítási címe egy EU-tagállamon belül van. Létre kell hozni egy rekordot az ilyen országokhoz és régiókhoz az **Országok/régiók paraméterei** lapján a **Külkereskedelmi paraméterek** oldalnak, és az **Ország/régió típusa** értékhez az **EU**értéket kell megadni. A Közösségen belüli kereskedelmi tranzakciók meg vannak jelölve a **Listakód** mezőben. Ezzel a mezővel elkülöníthetőek az általános Közösségen belüli kereskedelmi tranzakciók a Háromszögügylet tranzakcióktól. Közösségen belüli kereskedelmi tranzakciókkal kapcsolatos információkat gyűjthet az **EU értékesítési lista** lapon (kattintson az **Adó** &gt; **Nyilatkozatok** &gt; **Külkereskedelem** &gt; **EU értékesítési lista** fülre) az **Áthelyezés** funkció segítségével. Ennek a funkciónak segítségével olyan tranzakciókról is kaphat információkat, amelyek különböző jelentéstípusokkal bírnak (pl. cikkek vagy szolgáltatások) a tranzakció sorban megadott cikkáfacsoportokat illetően. Egyéb szűrőket is alkalmazhat, hogy megadja, mely tranzakciók szerepeljenek benne. Az **Áthelyezés** funkció létrehoz egy rekordot az **EU értékesítési lista** oldalon minden Közösségen belüli kereskedelmi tranzakcióhoz, ami szerepel benne, valamint megadja egy ügyfél számlaszámát, országát/régióját, adómentességi számát, egy számlaszámot és dátumot, illetve a sorok teljes összegét jelentésenként. Át is másolja a **Listakód** értékét a tranzakcióból. Egy tranzakció listakódját manuálisan is megváltoztathatja az **EU értékesítési lista** oldalon. Az **Áthelyezés** funkció rekordokat hoz létre, ha a **Jelentéskészítési állapot** értéke **Beleszámít**. Ellenőrizheti az összegyűjtött adatokat az **EU értékesítési lista**lapon, az **Érvényesítés** funkció használatával.

### <a name="generating-the-eu-sales-list-report"></a>EU értékesítési lista jelentés létrehozása.

Létrehozhat egy **EU értékesítési lista** jelentés, a **Jelentés**funkció használatával az **EU értékesítési lista**oldalon. Ez a funkció lehetővé teszi a jelentési időszak kiválasztását, valamint szűrőket adhat meg, hogy melyik ESL rekord szerepeljen benne. Beállíthat további, országokhoz/régiókhoz tartozó paramétereket is. Lehetősége van létrehozni jelentés-előnézetet, elektronikus fájlt, vagy mindkettőt. A **Jelentés**funkció a **Külkereskedelmi paraméterek**oldalon megadott jelentés és fájlformátumokat használja. Általában egy **EU értékesítési lista** külön sorokat tartalmaz, amik listázzák az ügyfelenkénti cikkek teljes összegét, országot/régiót, adómentességi számot és a jelentéstípust (háromszögügylet tranzakciókat is beleértve). Miután létrehozott egy **EU értékesítési lista** jelentést egy adott időszakra, megjelölheti azokat az ESL rekordokat, amelyek szerepeljenek a jelentésben, ha a **Jelentéskészítési állapot** értékét **Jelentett**értékre állítja. Ezen állapot beállításához használja a **Megjelölés jelentettként**funkciót az **EU értékesítési lista**oldalon.

### <a name="closing-the-eu-sales-list-reporting-period"></a>Az EU értékesítési lista jelentési időszakának lezárása.

Amikor befejezte az adott időszakra kiterjedő jelentési folyamatot (például amikor az adóhatóságok elfogadták az **EU értékesítési lista** jelentést), az ESL rekordokat, amelyek szerepelnek a jelentésben, megjelölheti, ha a **Jelentéskészítési állapot** értékét **Lezárt**értékre módosítja. Ezen állapot beállításához használja a **Megjelölés lezártként**funkciót az **EU értékesítési lista**oldalon. Az időszak zárásának visszaállításával megjelölheti az ESL rekordokat,ha a **Jelentéskészítési állapot** értékét **Beleszámít**értékre módosítja. Ezeket a rekordokat aztán felveheti egy **EU értékesítési lista** jelentésben újra. Ezen állapot beállításához használja a **Megjelölés** **beleszámítottként**funkciót az **EU értékesítési lista** oldalon.




