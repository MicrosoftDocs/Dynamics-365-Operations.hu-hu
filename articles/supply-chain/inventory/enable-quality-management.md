---
title: "Minőségkezelés áttekintése"
description: "Ez a témakör leírja, hogyan alkalmazza a minőségkezelés funkciót a Microsoft Dynamics 365 for Finance and Operations rendszerben, hogy ezzel segítse a termékminőség fejlesztését az ellátási láncán belül."
author: perlynne
manager: AnnBe
ms.date: 11/02/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventTestAssociationTable, InventTestGroup, InventTestItemQualityGroup, InventTestTable, InventTestVariable, InventTestVariableOutcome
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 91cc547becfbd0c0d675d87921aed92eb2ab570d
ms.contentlocale: hu-hu
ms.lasthandoff: 04/13/2018

---

# <a name="quality-management-overview"></a>Minőségkezelés áttekintése

[!INCLUDE [banner](../includes/banner.md)]

Ez a témakör leírja, hogyan alkalmazza a minőségkezelés funkciót a Microsoft Dynamics 365 for Finance and Operations rendszerben, hogy ezzel segítse a termékminőség fejlesztését az ellátási láncán belül.

A minőségkezelés segítséget nyújt a szabálytalan termékek javítási folyamatának kezelésében, azok eredetétől függetlenül. Mivel a diagnosztikai típusok javítási jelentésekhez kapcsolódnak, a Microsoft Dynamics 365 for Finance and Operations rendszer képes beütemezni a problémák megoldásához és azok visszatérésének megelőzéséhez szükséges feladatokat.

A szabálytalanság kezelésére szolgáló funkció mellett a minőségkezelés egyéb funkciói lehetővé teszik a problémakövetést problématípus (akár belső problémák) szerint, valamint a rövid- és hosszútávú megoldások azonosítását. A fő teljesítménymutatókról (KPI-kről) vezetett statisztikák betekintést nyújtanak a múltban megtörtént szabálytalansági problémákba és az azok javítására használt megoldásokba. Az előzményadatok segítségével felülvizsgálhatja a korábbi minőségi mérések hatékonyságát, és kidolgozhatja a jövőben alkalmazni kívánt megfelelő méréseket.

Mikor beállít egy minőségi társítást, a Finance and Operations képes létrehozni különféle üzleti folyamatok, események és feltételek minőségi rendeléseit. A minőségi társítás vonatkozhat egyetlen cikkre, cikkek egy csoportjára vagy minden cikkre.

## <a name="examples-of-the-use-of-quality-management"></a>Példák a minőségkezelés használatára
A minőségkezelés rugalmas és sokféle módon megvalósítható, így meg tud felelni az ellátási lánc műveleteinek adott szintjeire vonatkozó követelményeknek. Az alábbi példák ezeknek a funkcióknak a felhasználási lehetőségeit mutatják be.

-   Indítson automatikusan minőségellenőrzési folyamatot előre meghatározott feltételek teljesülésekor (adott szállítótól történő beszerzési rendelés raktári regisztrációja alapján).
-   Vizsgálat alatt zárolja a készletet a jóvá nem hagyott készlet használatának megakadályozása érdekében (a beszerzési rendelési mennyiségek teljes zárolása).
-   Az aktuális tényleges készlet vizsgálandó mennyiségének meghatározásához használja a minőségi társítás részét képező cikkmintavételt. A mintavétel történhet adott mennyiség vagy százalékos érték alapján.
-   A részleges bevételezésekhez minőségi rendeléseket kell létrehozni. Ha olyan minőségi rendelést szeretne létrehozni, amely egy rendelésen fizikailag bevételezett mennyiségen alapul, akkor be kell jelölnie a **Frissített mennyiségenként** jelölőnégyzetet a **Cikkmintavétel** űrlapon.
-   Hozzon létre minimum, maximum és cél tesztértékeket magukban foglaló teszttípusokat, és végezzen előre definiált ellenőrzési eredményeket adó minőségi-mennyiségi teszteket.
-   Adja meg az elfogadható minőségi szint értékét a minőségi mérések tűréshatárainak szabályozása érdekében.
-   Határozza meg a vizsgálati művelethez szükséges erőforrásokat (például tesztterület és tesztműszerek).

## <a name="working-with-quality-associations"></a>Minőségi társítások használata
Egy minőségi társítást használó üzleti folyamat különféle forrásbizonylatokkal lehet kapcsolatban (például beszerzési rendelésekkel, értékesítési rendelésekkel, vagy termelési rendelésekkel).

Minden egyes minőségi társítási rekord meghatározza a létrehozott minőségi rendelésekre vonatkozó teszteket, elfogadható minőségi szintet és mintavételi eljárást. Az üzleti folyamat minden egyes változatára definiálnia kell egy minőségi társítási rekordot. Például beállíthat egy olyan minőségi társítást, amely egy beszerzési rendelés termékbevételezésének frissítésekor létrehoz egy minőségi rendelést. A végrehajtási terv beállításától függően letiltható maga az indító folyamat, ha van egy nyitott minőségi rendelés, vagy letilthatóak az ezután következő folyamatok, például a beszerzési rendelés számlázása.

**Megjegyzés:** Amíg vannak nyitott minőségi rendelések, a készletmennyiségek kiadása automatikusan le van tiltva. A **Cikkmintavételek** lap **Teljes zárolás** beállításától függően a mennyiség a minőségi rendelésen vagy a forrásbizonylat sorában szereplő mennyiség lehet.

Egy adott üzleti folyamatra a minőségi társítási rekord azonosítja azokat az eseményeket és feltételeket, amelyek fennállása esetén a minőségi rendelés létrejön. A feltételek helyre vagy jogi személyre vonatkozhatnak. Romboló teszteket igénylő minőségi rendelés csak akkor generálható, ha az eseményhez létezik aktuális készlet.

A következő példák bemutatják egy minőségi társítási rekord meghatározását az egyes üzleti folyamatok változásainak megfelelően. Egy minőségi társítási rekord által az egyes példák esetén meghatározott eseményeket és feltételeket az alábbi táblázat összegzi.

<table>
<tbody>
<tr>
<th>Hivatkozás típusa</th>
<th>Eseménytípus</th>
<th>Végrehajtás</th>
<th>Eseményzárolás</th>
<th>Dokumentumhivatkozás</th>
</tr>
<tr>
<td>Készlet</td>
<td>Nem alkalmazható</td>
<td>Nem alkalmazható</td>
<td>Egyik sem</td>
<td>Mind</td>
</tr>
<tr>
<td rowspan="7">Értékesítés</td>
<td rowspan="4">Kitárolási folyamat ütemezve</td>
<td rowspan="4">Előtte</td>
<td>Egyik sem</td>
<td rowspan="22">Csak Egyedi azonosító, Csoport vagy Mind</td>
</tr>
<tr>
<td>Kitárolási folyamat</td>
</tr>
<tr>
<td>Szállítólevél</td>
</tr>
<tr>
<td>Számla</td>
</tr>
<tr>
<td rowspan="3">Szállítólevél</td>
<td rowspan="3">Előtte</td>
<td>Egyik sem</td>
</tr>
<tr>
<td>Szállítólevél</td>
</tr>
<tr>
<td>Számla</td>
</tr>
<tr>
<td rowspan="15">Beszerzés</td>
<td rowspan="7">Bevételezési lista</td>
<td rowspan="4">Előtte</td>
<td>Egyik sem</td>
</tr>
<tr>
<td>Bevételezési lista</td>
</tr>
<tr>
<td>Termékbevételezés</td>
</tr>
<tr>
<td>Számla</td>
</tr>
<tr>
<td rowspan="3">Utána</td>
<td>Egyik sem</td>
</tr>
<tr>
<td>Termékbevételezés</td>
</tr>
<tr>
<td>Számla</td>
</tr>
<tr>
<td rowspan="3">Nyilvántartás</td>
<td rowspan="3">Nem alkalmazható</td>
<td>Egyik sem</td>
</tr>
<tr>
<td>Termékbevételezés</td>
</tr>
<tr>
<td>Számla</td>
</tr>
<tr>
<td rowspan="5">Termékbevételezés</td>
<td rowspan="3">Előtte</td>
<td>Egyik sem</td>
</tr>
<tr>
<td>Termékbevételezés</td>
</tr>
<tr>
<td>Számla</td>
</tr>
<tr>
<td rowspan="2">Utána</td>
<td>Egyik sem</td>
</tr>
<tr>
<td>Számla</td>
</tr>
<tr>
<td rowspan="8">Termelés</td>
<td rowspan="3">Nyilvántartás</td>
<td rowspan="3">Nem alkalmazható</td>
<td>Egyik sem</td>
<td rowspan="12">Mind</td>
</tr>
<tr>
<td>Készként jelentés</td>
</tr>
<tr>
<td>Záró</td>
</tr>
<tr>
<td rowspan="5">Készként jelentés</td>
<td rowspan="3">Előtte</td>
<td>Egyik sem</td>
</tr>
<tr>
<td>Készként jelentés</td>
</tr>
<tr>
<td>Záró</td>
</tr>
<tr>
<td rowspan="2">Utána</td>
<td>Egyik sem</td>
</tr>
<tr>
<td>Záró</td>
</tr>
<tr>
<td rowspan="4">Karantén</td>
<td rowspan="3">Készként jelentés</td>
<td rowspan="2">Előtte</td>
<td>Készként jelentés</td>
</tr>
<tr>
<td>Záró</td>
</tr>
<tr>
<td>Utána</td>
<td>Záró</td>
</tr>
<tr>
<td>Záró</td>
<td>Előtte</td>
<td>Záró</td>
</tr>
<tr>
<td rowspan="3">Útvonalművelet</td>
<td rowspan="3">Készként jelentés</td>
<td rowspan="2">Előtte</td>
<td>Egyik sem</td>
<td rowspan="3">Egyedi azonosító, Csoport vagy Mind, valamint Erőforrás-specifikus, Csoport vagy Mind</td>
</tr>
<tr>
<td>Készként jelentés</td>
</tr>
<tr>
<td>Utána</td>
<td>Egyik sem</td>
</tr>
<tr>
<td rowspan="3">Társtermék gyártása</td>
<td>Nyilvántartás</td>
<td>Nem alkalmazható</td>
<td rowspan="3">Egyik sem</td>
<td rowspan="3">Mind</td>
</tr>
<tr>
<td rowspan="2">Készként jelentés</td>
<td>Előtte</td>
</tr>
<tr>
<td>Utána</td>
</tr>
</tbody>
</table>

A következő táblázatban bővebben tájékozódhat arról, hogy hogyan hozhatóak létre minőségi rendelések adott típusú folyamatokhoz.
<div class="tableSection">

<table>
<tbody>
<tr>
<th>Folyamat típusa</th>
<th>Mikor hozhatóak létre automatikusan minőségi rendelések?</th>
<th>Mikor hozhatóak létre minőségi rendelések, amennyiben romboló tesztekre van szükség?</th>
<th>Feltételekre vonatkozó információ</th>
<th>Manuális létrehozásra vonatkozó információ</th>
</tr>
<tr>
<td>Beszerzési rendelés</td>
<td>A bevételezett anyagra vonatkozó bevételezési lista vagy termékbevételezés feladása előtt vagy után</td>
<td>A bevételezett anyagra vonatkozó termékbevételezés feladása után, mivel az anyagnak rendelkezésre kell állnia a romboló teszt elvégzéséhez</td>
<td>A minőségi rendelés követelménye vonatkozhat egy adott telephelyre, cikkre vagy szállítóra, illetve ezek bármilyen kombinációjára.</td>
<td>A beszerzési rendelésekhez manuálisan generált minőségi rendelésekben felhasználhatók a minőségi társítási rekordban szereplő adatok, például a mintavételezési eljárás.</td>
</tr>
<tr>
<td>Karanténutasítás</td>
<td>Mielőtt vagy miután a karanténutasítás készként lett jelentve vagy befejeződött</td>
<td>Romboló teszteket igénylő minőségi rendelések nem hozhatóak létre. A rendszer feltételezi, hogy a karanténutasítás funkció kezeli a roncsolt anyag elhelyezését.</td>
<td>A minőségi rendelés követelménye vonatkozhat egy adott telephelyre, cikkre vagy szállítóra, illetve ezek bármilyen kombinációjára.</td>
<td>A karanténutasításokhoz manuálisan generált minőségi rendelésekben felhasználhatók a minőségi társítási rekordban szereplő adatok, például a mintavételezési eljárás.</td>
</tr>
<tr>
<td>Értékesítési rendelés</td>
<td>A szállított cikkekre vonatkozó ütemezett kitárolási folyamat vagy szállítólevél frissítése előtt</td>
<td>Bármelyik lépésnél</td>
<td>A minőségi rendelés követelménye vonatkozhat egy adott telephelyre, cikkre vagy vevőre, illetve ezek bármilyen kombinációjára.</td>
<td>Az értékesítési rendelésekhez manuálisan generált minőségi rendelésekben felhasználhatók a minőségi társítási rekordban szereplő adatok, például a mintavételezési eljárás.</td>
</tr>
<tr>
<td>Termelési rendelés</td>
<td>A termelési rendelés befejezett mennyiségének jelentése előtt vagy után</td>
<td>A termelési rendelés befejezett mennyiségének jelentése után</td>
<td>A minőségi rendelés követelménye vonatkozhat egy adott telephelyre vagy vevőre, illetve ezek kombinációjára.</td>
<td>A termelési rendelésekhez manuálisan generált minőségi rendelésekben felhasználhatók a minőségi társítási rekordban szereplő adatok, például a mintavételezési eljárás.</td>
</tr>
<tr>
<td>Útvonalművelettel rendelkező termelési utasítás</td>
<td>A műveletre vonatkozó jelentés befejezése előtt vagy után</td>
<td>Miután az utolsó művelet készként való jelentése megtörtént</td>
<td>A minőségi rendelés követelménye vonatkozhat egy adott telephelyre, cikkre, vevőre vagy üzemi erőforrásra, illetve ezek bármilyen kombinációjára.</td>
<td>Az útvonalművelethez manuálisan generált minőségi rendelésekben felhasználhatók a minőségi társítási rekordban szereplő adatok, például a mintavételezési eljárás.</td>
</tr>
<tr>
<td>Készlet</td>
<td>A készletnaplón belüli tranzakciókhoz és az átmozgatási rendelési tranzakciókhoz nem generálhatók automatikusan minőségi rendelések.</td>
<td></td>
<td></td>
<td>Cikk készletmennyiségére vonatkozó minőségi rendelést manuálisan kell létrehozni. Tényleges aktuális készlet szükséges.</td>
</tr>
</tbody>
</table>

## <a name="quality-management-pages"></a>A Minőségkezelés oldalai
<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Oldal</th>
<th>Leírás</th>
<th>Példa</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Minőségi társítások</td>
<td>Lásd a cikk előző szakaszait.</td>
<td>A minőségi társítás meghatározza a létrehozott minőségi rendelésre vonatkozó alábbi adatok mindegyikét:
<ul>
<li>Tranzakcióesemény</li>
<li>A cikkeken elvégzendő tesztek</li>
<li>Elfogadható minőségi szint</li>
<li>Mintavételi terv</li>
</ul>
Definiálnia kell egy minőségi társítást az üzleti folyamat minden olyan változatához, ahol minőségi rendelés automatikus létrehozása szükséges. Minőségi rendelés létrehozható például az üzleti folyamatokban beszerzési rendelésekhez, karanténutasításokhoz, értékesítési rendelésekhez és termelési rendelésekhez.</td>
</tr>
<tr class="even">
<td>Tesztek</td>
<td>Ezen az oldalon lehet meghatározni és megtekinteni azokat a teszteket, amelyekkel megállapítható, hogy a termékek megfelelnek-e a minőségi specifikációknak. Hozzárendelhet egy vagy több különálló tesztet egy tesztcsoporthoz. Ebben az esetben tesztspecifikus adatokat is megadhat, például az elfogadható mérési értékeket. Mennyiségi tesztekhez mérési értékek, minőségi tesztekhez pedig tesztváltozók használhatók.
<ul>
<li>Egy mennyiségi teszt teszttípusa <strong>Egész</strong> vagy <strong>Tört</strong> lehet, és egy kijelölt mértékegység is tartozik hozzá. A minőségi specifikációk és a teszteredmények számokként fejeződnek ki.</li>
<li>A minőségi tesztek teszttípusa: <strong>Lehetőség</strong>. A minőségi tesztekhez további, a mérendő tesztváltozóra és annak sorszámozott lehetőségeire vonatkozó adatok szükségesek. A minőségi specifikációk és a teszteredmények egy eredménynek megfelelően fejeződnek ki.</li>
</ul></td>
<td>Egy gyártóvállalat a beszerzett anyagon két tesztet végez el: ezek egyike az anyagminőséggel kapcsolatos mennyiségi teszt, a másik pedig a csomagolási sérüléseket felmérő minőségi teszt. A vállalat további adatokat ad meg a kvalitatív tesztre vonatkozóan, hogy meghatározza a tesztváltozót (sérült csomagolás) és annak kimeneteleit. A vállalat a <strong>Tesztcsoportok</strong> oldalon hozzárendeli a két tesztet egy tesztcsoporthoz és megadja a tesztspecifikus adatokat. A tesztcsoportot hozzárendeli egy minőségi rendeléshez, hogy a két teszt eredményét jelenteni tudja.</td>
</tr>
<tr class="odd">
<td>Tesztcsoportok</td>
<td>Ezen az oldalon lehet beállítani, módosítani és megtekinteni a tesztcsoportokat és a tesztcsoportokhoz rendelt különálló teszteket. A felső ablak jeleníti meg a tesztcsoportokat, míg az alsó ablakban láthatók a kiválasztott tesztcsoporthoz tartozó tesztek. Egy tesztcsoporthoz több szabályt is hozzá lehet rendelni, például mintavételi tervet, elfogadható minőségi szintet, valamint a romboló teszt követelményét. Amikor hozzárendel egy különálló tesztet egy tesztcsoporthoz, további adatokat definiálhat, például sorrendet, dokumentumokat és érvényességi dátumokat. Mennyiségi teszt esetén a megadott adatok az elfogadható mérési értékeket is tartalmazzák. Minőségi teszt esetén az adatok a tesztváltozót és az alapértelmezett eredményt tartalmazzák. A minőségi rendelésekhez rendelt tesztcsoport meghatározza azokat az alapértelmezett teszteket, amelyeket az adott cikken végre kell hajtani. Azonban hozzáadhat, törölhet, vagy módosíthat adott minőségi rendelésre vonatkozó teszteket. A minőségi rendelés keretében végzett mindegyik tesztnél megtörténik a teszteredmények jelentése.</td>
<td>Egy gyártóvállalat minőségi irányelveinek minden variációjához meghatároz egy-egy tesztcsoportot. A különböző tesztcsoportok tükrözik a mintavételi tervek, az együttesen végrehajtandó tesztsorok, az elfogadható mérési értékek, az elfogadható minőségi szint és egyéb tényezők eltéréseit. Mennyiségi teszt esetén az elfogadható mérési értékekben is van különbség. A minőségi irányelveinek érvényesítése érdekében a vállalat minden egyes, minőségi rendeléseket automatikusan generáló szabályhoz a <strong>Minőségi társítások</strong> oldalon hozzárendel egy tesztcsoportot, valamint a manuálisan létrehozott minőségi rendelésekhez is hozzárendel egy tesztcsoportot.</td>
</tr>
<tr class="even">
<td>Cikkminőségi csoportok</td>
<td>Ezen az oldalon a minőségi csoporthoz rendelt cikkeket, illetve a cikkhez rendelt minőségi csoportokat lehet beállítani, módosítani és megtekinteni. A minőségi csoport a cikkekre vonatkozó közös tesztkövetelményeket képvisel. Miután a <strong>Tesztcsoportok</strong> oldalon definiálta a tesztkövetelményeket, meghatározhatja a minőségi rendelések automatikus létrehozásának szabályait. A folyamat egyszerűsítése érdekében az egyes cikkekhez tartozó szabályokat nem definiáljuk. Ehelyett egy minőségi csoportra vonatkozó szabályokat definiálhatunk a <strong>Minőségi társítások</strong> oldalon. Emellett egy kiválasztott minőségi csoporthoz tartozó <strong>Cikkminőségi csoportok</strong> oldal is használható arra, hogy megfelelő cikkeket az adott csoporthoz rendeljünk. Emellett egy kiválasztott cikkhez tartozó <strong>Cikkminőségi csoportok</strong> oldal is használható arra, hogy megfelelő minőségi csoportokat az adott cikkhez rendeljünk.</td>
<td>Egy gyártóvállalat több nyersanyagot is vásárol, amelyeknél a beérkezéskor szükséges vizsgálatokra ugyanazok a tesztkövetelmények vonatkoznak. A vállalat definiál egy minőségi csoportot, majd hozzárendeli a nyersanyagokhoz társított cikkszámokat a csoporthoz. Később a vállalat egy új típusú nyersanyagot vásárol, amelyre az előzőekkel azonos tesztkövetelmények vonatkoznak. Ahelyett, hogy az új anyagra új tesztkövetelményeket állítana be, a vállalat hozzáadja az új anyag cikkszámát a meglévő minőségi csoporthoz. Ugyanez a gyártóvállalat olyan cikkeket is gyárt, amelyek gyártási tesztjeire ugyanazok a követelmények érvényesek, és olyan cikkeket is szállít, amelyek szállítás előtti tesztjeire ugyanolyan követelmények vonatkoznak. A vállalat két további minőségi csoportot határoz meg, majd a megfelelő cikkszámokat hozzárendeli az egyes minőségi csoportokhoz.</td>
</tr>
<tr class="odd">
<td>Tesztváltozók</td>
<td>Ezen az oldalon meghatározhatja és megtekintheti a minőségi tesztekhez társított változókat. Minden változóhoz definiálhat sorszámozott eredményeket, amelyek a szóba jöhető lehetőségeket jelölik. Teszteket a <strong>Tesztek</strong> oldalon adhat meg. Minőségi tesztek esetén a teszt típusát <strong>Lehetőség</strong>-re kell állítania. A <strong>Tesztcsoportok</strong> oldal használatával lehet tesztváltozót adott teszthez hozzárendelni.</td>
<td>Egy süteménygyártó a készterméken vizsgálatot végez. A vizsgálat tesztnek többféle változója van. Az egyik változó az íz, ennek lehetséges eredményei: jó és rossz. Egy másik változó a szín, ennek lehetséges eredményei: túl sötét, túl világos és megfelelő.</td>
</tr>
<tr class="even">
<td>Tesztváltozó eredményei</td>
<td>Ezen az oldalon lehet beállítani, módosítani vagy megtekinteni a minőségi teszthez kapcsolódó tesztváltozó lehetséges teszteredményeit. Mindegyik eredményhez egy <strong>megfelelt</strong> vagy egy <strong>nem felelt meg</strong> állapotot kell hozzárendelni. Minden egyes, a <strong>Tesztek</strong> oldalon megadott minőségi teszthez definiálnia kell egy változót és annak eredményeit. (Minőségi tesztek esetén a <strong>Tesztek</strong> oldalon beállított teszttípus <strong>Lehetőség</strong>.) A <strong>Tesztcsoportok</strong> oldal használatával lehet tesztváltozót és az alapértelmezett eredményt adott minőségi teszthez hozzárendelni.</td>
<td>Egy süteménygyártó a készterméken vizsgálatot végez. Ennek a vizsgálati tesztnek többféle változója van. Az egyik változó az íz, ennek lehetséges eredményei: jó és rossz. Egy másik változó a szín, ennek lehetséges eredményei: túl sötét, túl világos és megfelelő. Mindegyik eredményhez hozzá van rendelve egy <strong>megfelelt</strong> vagy <strong>nem felelt meg</strong> állapot. Az egyes változók vizsgálatakor az ellenőr a teszt eredményét az egyik eredmény kiválasztásával jelenti.</td>
</tr>
</tbody>
</table>



<a name="see-also"></a>Lásd még
--------

[Minőségkezelési folyamatok](quality-management-processes.md)

[Szabálytalanság kezelésének aktiválása](enable-nonconformance-management.md)

