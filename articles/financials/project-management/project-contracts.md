---
title: Projektszerződések
description: Ez a témakör a különféle projektekhez és finanszírozási forrásokhoz készíthető projektszerződéseket mutatja be példákkal, továbbá ismerteti a szerződéskezelés és a projektek megrendelői felé történő számlakiállítás módszereit a Microsoft Dynamics 365 for Finance and Operations rendszerben.
author: KimANelson
manager: AnnBe
ms.date: 11/03/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjProjectContractsListPage, ProjProjectsListPage
audience: Application User, IT Pro
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 23561
ms.assetid: bfd18d9b-d9a6-4e21-bc95-bf4af45f617f
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c0f0fcec64ce03c6e1d877fb1c8d004bb416bd95
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2019
ms.locfileid: "310369"
---
# <a name="project-contracts"></a>Projektszerződések

[!include [banner](../includes/banner.md)]

Ez a cikk a különféle projektekhez és finanszírozási forrásokhoz készíthető projektszerződéseket mutatja be példákkal, továbbá ismerteti a szerződéskezelés és a projektek megrendelői felé történő számlakiállítás módszereit a Microsoft Dynamics 365 for Finance and Operations rendszerben.

A projektszerződés teljesítésére létrehozott projekt típusa határozza meg a megrendelő felé történő számlakiállítás módszerét. A projektszerződés és a hozzá kapcsolódó projekt módosítható, de a projekt típusa nem. 

Projektszerződés használatával egy vagy több projektet számlázhat ki egyszerre. A projektszerződés elősegíti annak biztosítását is, hogy a projektstruktúrában szereplő összes részprojektnél konzisztens legyen a számlázási eljárás. 

Minden számlázandó projektet projektszerződéshez kell társítani. A projektszerződés beállításai az ahhoz társított összes projektre és alprojektre vonatkoznak. 

A projektszerződés egy vagy több finanszírozási forrást határozhat meg. Ennek köszönhetően a számlázás felosztható több finanszírozó között, finanszírozási korlátot lehet beállítani ahhoz, hogy egy-egy finanszírozási forrásnak ne számlázzanak ki a megszabottnál nagyobb összeget, illetve finanszírozási szabályokat lehet beállítani a kiadások terheléséhez.

## <a name="funding-for-project-contracts"></a>Finanszírozás projektszerződésekre
Egyes projektszerződések megadják, hogy a projektköltségek finanszírozásának felelőssége megoszlik több fél között.. Íme néhány példa:

-   Egy több osztállyal rendelkező nagy vevő azt kéri, hogy egy projekt finanszírozása osztály szerint legyen felosztva.
-   Az Ön vállalata egy külső szervezettel osztja meg egy nagy projekt költségeit.
-   Egy úttal kapcsolatos projektet két közigazgatási terület közösen finanszíroz.
-   Egy híddal kapcsolatos projektet valamilyen állami támogatás és egy magánvállalkozás finanszíroz.

A Finance and Operations rendszerben feloszthatja egyetlen tranzakció vagy egy teljes projekt számlázását több vevő, támogatás vagy szervezet között. 

A több finanszírozóval rendelkező projektek esetén finanszírozási forrásnak neveznek minden olyan felet, amely hozzájárul egy speciális finanszírozási projekt finanszírozásához. Miután egy vevő, szervezet vagy támogatás finanszírozási forrásként kerül meghatározásra, hozzárendelhető egy vagy több finanszírozási szabályhoz. A finanszírozási szabályok tartalmazzák azon feltételeket, amelyek meghatározzák, hogy hogyan oszlanak fel a költségek egy projekt különböző finanszírozási forrásai között. 

Mivel a raktározott cikkeket, például azokat, amelyek megjelennek beszerzési igényléseken és beszerzési rendeléseken, nem lehet megosztani, a költség összeget sem lehet megosztani több finanszírozási forrás között az elosztás idejében. Emiatt a finanszírozási forrás érték marad 0 (nulla) amíg a készletkiadás feladásra kerül. Amikor a készletkiadás feladásra kerül, a költségösszeg felosztása a projekt számlafelosztási szabályai alapján történik.

Íme néhány lépés, melyet megtehet annak érdekében, hogy megkönnyítse a számlázás felosztását több finanszírozási forrás között:

-   Adja meg, hogy minden tranzakció, melyet egy projektre megadnak, ugyanazon értékesítési pénznemet használja, mint a projektszerződés.
-   Állítson fel finanszírozási korlátokat úgy, hogy egy finanszírozási forrás ne legyen egy megadott összegnél többre számlázva egy projekt felé.
-   Állítson be finanszírozási szabályokat és finanszírozási korlátokat minden dolgozóra, cikkre, kategóriára, kategóriacsoportra és tranzakciótípusra (vagy az összes tranzakciótípusra).
-   Jelöljön ki választható kezdő és záró dátumokat, hogy meghatározza az időszakot, amikor az egyes finanszírozási szabályok érvényesek.
-   Adja meg azt a százalékos értéket, amelyért minden finanszírozási forrást felelős.
-   Adja meg, hogy melyik finanszírozási forrás felelős kerekítési különbségekért, amelyeket finanszírozás felosztási számítások okoznak.
-   Állítson fel szabályokat, amelyek meghatározzák, hogyan kerülnek a projektköltségek számlázásra külső vevőknek és felszámolásra belső szervezetek részére.
-   Rögzítse a tranzakciókat egy várakozó finanszírozási számlán, amíg további finanszírozást tud szerezni, vagy amíg úgy dönt, hogy belsőleg viseli a költségeket.

Annak megállapításához, hogy melyik adócsoportot kell társítani egy tranzakcióhoz, a projektben egy adócsoport-hozzárendelést keresnek. Ha adócsoport-hozzárendelés nem került létrehozásra projektszinten, a projektszerződésben kell keresni.

### <a name="example-multiple-funding-sources-simple"></a>Példa: Több finanszírozási forrás (egyszerű)

A következő táblázat esteket ad meg a finanszírozási felosztás kezelésére több finanszírozási forrás között. Ezek az esetek a következő feltevéseken alapulnak:

-   A prioritási beállítások hatással vannak a finanszírozás felosztására, egyéb finanszírozási szabályok feltételeinek alkalmazása előtt.
-   Dátumtartomány nem lett megadva annak meghatározására, hogy mikor érvényes a finanszírozási szabály.

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<tbody>
<tr class="odd">
<td><strong>Eset</strong></td>
<td><strong>Finanszírozási forrás</strong></td>
<td><strong>Felosztási százalék</strong></td>
<td><strong>Finanszírozás-felosztási prioritás</strong></td>
</tr>
<tr class="even">
<td>Célszerű a költségeket egy finanszírozási forráshoz kiosztani amíg az alapjai kimerülnek, majd egy második finanszírozási forráshoz kiosztani a költségeket amíg annak alapjai kimerülnek, végül a fennmaradó költségeket egy harmadik finanszírozási forráshoz kiosztani.</td>
<td><ul>
<li>Finanszírozási　forrás　1</li>
<li>Finanszírozási　forrás　2</li>
<li>Finanszírozási　forrás　3</li>
</ul></td>
<td><ul>
<li>100%</li>
<li>100%</li>
<li>100%</li>
</ul></td>
<td><ul>
<li>1</li>
<li>2</li>
<li>3</li>
</ul></td>
</tr>
<tr class="odd">
<td>Célszerű egy finanszírozási forráshoz kiosztani a költségek 75 százalékát és 25 százalékot egy második finanszírozási forráshoz. Amikor ezen finanszírozási források közül bármelyik ki van merítve, célszerű a fennmaradó költségösszeget egy harmadik finanszírozási forrásból fizetni.</td>
<td><ul>
<li>Finanszírozási　forrás　1</li>
<li>Finanszírozási　forrás　2</li>
<li>Finanszírozási　forrás　3</li>
</ul></td>
<td><ul>
<li>75%</li>
<li>25%</li>
<li>100%</li>
</ul></td>
<td><ul>
<li>1</li>
<li>1</li>
<li>2</li>
</ul></td>
</tr>
<tr class="even">
<td>Célszerű egy finanszírozási forráshoz kiosztani a költségek 75 százalékát és 25 százalékot egy második finanszírozási forráshoz. Amikor ezen finanszírozási források közül bármelyik ki van merítve, célszerű a fennmaradó költségösszeget egy harmadik finanszírozási forrás és egy negyedik finanszírozási forrás között felosztani.</td>
<td><ul>
<li>Finanszírozási　forrás　1</li>
<li>Finanszírozási　forrás　2</li>
<li>Finanszírozási　forrás　3</li>
<li>Finanszírozási　forrás　4</li>
</ul></td>
<td><ul>
<li>75%</li>
<li>25%</li>
<li>50%</li>
<li>50%</li>
</ul></td>
<td><ul>
<li>1</li>
<li>1</li>
<li>2</li>
<li>2</li>
</ul></td>
</tr>
<tr class="odd">
<td>Célszerű egy finanszírozási forráshoz kiosztani a költségek első 25 százalékát és a maradékot egy második finanszírozási forráshoz.</td>
<td><ul>
<li>Finanszírozási　forrás　1</li>
<li>Finanszírozási　forrás　2</li>
</ul></td>
<td><ul>
<li>25%</li>
<li>100%</li>
</ul></td>
<td><ul>
<li>1</li>
<li>2</li>
</ul></td>
</tr>
</tbody>
</table>

### <a name="example-multiple-funding-sources-complex"></a>Példa: Több finanszírozási forrás (összetett)

Három finanszírozási forrása van, amelyeket a következő sorrendben kíván használni:

1.  Használja a 2-es számú finanszírozási forrást és a 3-as számú finanszírozási forrást egyenlően amíg a 2-es számú finanszírozási forrás kimerül.
2.  Használja tovább a 3-as számú finanszírozási forrást amíg az kimerül.
3.  Használja az 1-es számú finanszírozási forrást miután a 3-as számú finanszírozási forrás kimerül.

Ezen cél eléréséhez a következőket kell tennie:

-   Állítson be finanszírozási korlátokat a 2-es számú finanszírozási forrásra és a 3-as számú finanszírozási forrásra a megfelelő összegekkel.
-   Hozza létre a következő finanszírozási szabályokat:
    -   Szabály 1 (1-es prioritás): Ossza ki a tranzakciók 50 százalékát a 2-es finanszírozási forráshoz és 50 százalékát a 3-as finanszírozási forráshoz.
    -   Szabály 2 (2-es prioritás): Ossza ki a tranzakciók 100 százalékát a 3-as finanszírozási forráshoz.
    -   Szabály 3 (3-es prioritás): Ossza ki a tranzakciók 100 százalékát az 1-es finanszírozási forráshoz.

Ez a beállítás azért működik, mert a tranzakciók összevetésre kerülnek a szabályokkal és korlátozásokkal, hogy meghatározzák, hogy bármelyikük vonatkozik-e a tranzakcióra. Ha semmilyen korlát vagy szabály sem vonatkozik kifejezetten a tranzakcióra, az Összes tranzakció szabály lép érvénybe. Az Összes tranzakció szabály megfeleltet minden tranzakciót. 

Ha található olyan szabály, amely megfeleltethető a tranzakcióval, a szabályban kiosztott százalék kerül alkalmazásra, de csak azután, hogy a megfeleltetések összevetésre kerülnek bármilyen beállított korlátokkal. Ha korlátba ütközés történik, és egy finanszírozási forrás alapjai kimerültek, a finanszírozási korláthoz társított finanszírozási szabály figyelmen kívül hagyható, és a program a következő érvényes szabályt keresi meg. 

Bizonyos esetekben csak a tranzakció egy részét lehet egy szabály alapján felosztani. Ez előfordulhat azért, mert korlátba ütközés történik, amikor a tranzakció felosztásra kerül. Ebben az esetben csak egy bizonyos pénzösszeg kerül felosztásra az adott szabály szerint, például 50 százalék minden finanszírozási forráshoz. Ez a helyzet az ebben a szakaszban korábban ismertetett 1-es szabályban. A maradék a sorban következő szabály szerint kerül felosztásra. 

Az alábbi táblázat ezt az esetet részletesebben megvizsgálja.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><strong>Fókusz</strong></td>
<td><strong>Részletek</strong></td>
</tr>
<tr class="even">
<td>Finanszírozási szabályok</td>
<td><ul>
<li>Szabály 1 (1-es prioritás): Összes tranzakció. Rendelje hozzá a 2 számú finanszírozási forrást 50 %-kal, és a 3 számú finanszírozási forrást 50 %-kal.</li>
<li>Szabály 2 (2-es prioritás): Összes tranzakció. Rendelje hozzá a 3 számú finanszírozási forrást 100%-kal.</li>
<li>Szabály 3 (2-es prioritás): Összes tranzakció. Rendelje hozzá a 1 számú finanszírozási forrást 100%-kal.</li>
</ul></td>
</tr>
<tr class="odd">
<td>Finanszírozási korlátozások</td>
<td><ul>
<li>Finanszírozási forrás 1 korlát = 10000.00</li>
<li>Finanszírozási forrás 2 korlát = 500.00</li>
<li>Finanszírozási forrás 3 korlát = 750.00</li>
</ul></td>
</tr>
<tr class="even">
<td>Tranzakció 1</td>
<td><strong>A tranzakció összege:</strong> 100,00<strong>Finanszírozás:</strong> A tranzakció fizetése csak az 1-es szabálynak megfelelően történik, mert a tranzakció csak az 1-es szabály alkalmazása után kerül teljes kifizetésre. A tranzakció egyenlően kerül finanszírozásra a 2-es finanszírozási forrás és a 3-as finanszírozási forrás között.
<ul>
<li>2-es finanszírozási forrás: 50.00</li>
<li>3-as finanszírozási forrás: 50.00</li>
</ul></td>
</tr>
<tr class="odd">
<td>Tranzakció 2</td>
<td><strong>A tranzakció összege:</strong> 5000,00 <strong>Finanszírozás:</strong> A tranzakció kifizetése mindhárom szabály alapján történik.1-es szabály <strong>1-es szabály</strong>
<ul>
<li>2-es finanszírozási forrás: 450.00</li>
<li>3-as finanszírozási forrás: 450.00</li>
</ul>
<strong>2-es szabály</strong>
<ul>
<li>3-as finanszírozási forrás: 250.00 (= 750.00 – 50.00 – 450.00)</li>
</ul>
<strong>3-as szabály</strong>
<ul>
<li>1-es finanszírozási forrás: 3,850.00 (= 5,000.00 – 450.00 – 450.00 – 250.00)</li>
</ul></td>
</tr>
<tr class="even">
<td>Az egyes finanszírozási források részére kiosztott összes alap</td>
<td><ul>
<li>1-as finanszírozási forrás: 3,850.00</li>
<li>2-as finanszírozási forrás: 500.00</li>
<li>3-as finanszírozási forrás: 750.00</li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="billing-rules"></a>Számlázási szabályok
Olyan projektszerződést választott tárgyaljanak egy vevő, ha definiálni, mikor és hogyan lehet számlát a vevő, a munka a projekt. Miután beállította a projektszerződést és a projektet, beállíthat számlázási szabályokat a projekthez. Számlázási szabályok vannak megadva a projektszerződés projekt feltételei alapján. A létrehozható számlázási szabály a projektszerződés feltételeitől és annak a projektnek a típusától – például vagy Mérföldkő – függ, amelyhez hozzárendeli a számlázási szabályt. Egy projektszerződéshez több számlázási szabályt is létrehozhat. A számlázási szabály hozzárendelése az azonos projektszerződéshez társított több projekt is, és hasonló számlázási feltételeket kell. 

A következő típusú ármegállapodások hozhatók létre:

-   **Szállítási egység** – Vevői számla kiállítása a szállítási egység befejezésekor. A szerződés szállítási egységei határozhatja meg.
-   **Haladás** – Vevői számla kiállítása a projekt adott százalékának befejezésekor. Állíthat be a számlázási szabály szeretné automatikusan kiszámítani az elvégzett munka százalékos, vagy manuálisan ki lehet számítani az elvégzett munka és az összeg a vevőnek való számlázáshoz százaléka.
-   **Mérföldkő** – Vevői számla kiállítása a projekt mérföldkő teljes összegéről egy mérföldkő elérésekor.
-   **Díj**– Vevői számla kiállítása a szolgáltatásokra, valamint kezelési díj, amely jellemzően a szolgáltatások költségének bizonyos százaléka.
-   **Idő és anyag** – Vevői számla kiállítása a projekteken használt idő és anyagok értékére.

Bármilyen típusú számlázási szabályokra megadhat egy visszatartási százalékot, amely a vevői számlákból kerül levonásra, amíg a projekt el nem éri az egyezményes fokozatot. A kifizetési visszatartás százaléka megadva a projektszerződés. Az összeg kiszámítása a vevői számla sorainak teljes értékén alapul, és abból kerül levonásra. 

Az **Idő és anyag** és **Haladás** számlázási szabályokkal hozzárendelhet számlázható kategóriákat. A számlázható kategóriák a vevői számlákba belefoglalandó tranzakciók. 

Ha készen áll a vevői számlát, az összeg a projekt számlázásához kiszámítja a számlázási szabályokkal, és a projektszámla-javaslat jön létre. 

A következő részek példákat mutatnak arra, hogyan lehet beállítani és kezelni számlázási szabályokat egy projektre.

### <a name="example-create-a-billing-rule-that-is-based-on-the-number-of-units-delivered"></a>Példa: Számlázási szabály létrehozása a szállított cikkek száma alapján

A szervezete egy megállapodást köt összesen öt képzési foglalkozás biztosítására egy vevő alkalmazottainak, képzési foglalkozásonként 10 000 költséggel. Minden képzési foglalkozás után számláz a vevőnek. 

Amikor beállítja a számlázási szabályokat a szerződésre, a következő értékeket használja:

-   A szállítási mértékegysége egy képzési munkamenet.
-   Az Egységár képzési munkamenet egy 10 000.
-   Egységek száma összesen öt képzéseken.

Egy képzési foglalkozás befejezése után létrehozhat számlát 10000 összeggel az első szállított egységre, és elküldheti a számlát a vevőnek.

### <a name="example-create-a-billing-rule-that-is-based-on-a-specified-percentage-of-project-completion-manual-calculation"></a>Példa: Számlázási szabály létrehozása a projekt feldolgozottságának megadott százaléka alapján (manuális számítás)

A termék, amelyet a vevő fejleszt részének hozzanak a vevővel kötött megállapodás belép a szervezethez, a szoftver tanácsadó cég. Szervezete vállalja, hogy hat hónapos időszak alatt leszállítja a programkódot a termékhez. A vevő pedig elfogadja, a munka a szervezet összesen 100 000 kifizetésére. Létrehoz egy számlázási szabályt a vevő számlázásra, mely a szerződésben meghatározott, a projekten elvégzett munka százalékos értéken alapul.

-   Az első hónap végén meg fognak felelni az elvégzett munka százalékos meghatározásához a vevővel. Miután Ön és a vevő áttekinti a projektet, Ön úgy dönt, hogy a projekt 15 százalékban befejezett.
-   Létrehoz egy számlát 15 000 összeggel (100 000-nek a 15 százaléka), és elküldi a vevőnek.

### <a name="example-create-a-billing-rule-that-is-based-on-a-specified-percentage-of-project-completion-automatic-calculation"></a>Példa: Számlázási szabály létrehozása a projekt feldolgozottságának megadott százaléka alapján (automatikus számítás)

Az Ön szervezete, egy szoftver fejlesztési vállalkozás megegyezik, hogy egy bérlista könyvelési csomagot fejleszt a vevőnek 30 000-ért. A vevő pedig elfogadja, a munkáért a szervezetnek a teljesített munka százaléka alapján fizet. Úgy becsli, hogy a projektköltségek 20 000-et tesznek majd ki. A projektszerződés megadja azon munka kategóriákat, amelyeket a számlázási folyamatban használ. Be lehet állítani olyan számlázási szabályokat, amelyek alapján az egyes kategóriákban elvégzett munka százaléka után járó számlaösszegek kiszámítása automatikusan történik. Az egyes levelezési kategóriák alkategóriáinak beállítása:

-   **Fejlesztés** – 15 000 költség és 20 000 bevétel.
-   **Telepítés** – 5 000 költség és 10 000 bevétel

Vevői számla létrehozásakor először a számlaösszeg automatikusan kiszámítja a következő adatokat:

-   A dolgozó a projekt havonta után elküldi a projekt munkaidő-kimutatás. A dolgozó munkaóráinak költsége pedig 5000 fejlesztési 1000 telepítésre. A fejlesztési munka 33 százalékosan befejezett (5000 tényleges költség/15 000 tervezett költség), és a telepítési munka 20 százalékosan teljes befejezett (1000 tényleges költség/5000 tervezett költség).
-   A számla összege 8 667, melyet a program automatikusan számít ki (20 000-nek a 33 százaléka + 10 000-nek a 20 százaléka).
-   Létrehoz egy számlát 8 667 összeggel, és elküldi a vevőnek.

### <a name="example-create-a-billing-rule-that-is-based-on-agreed-upon-milestones"></a>Példa: Számlázási szabály létrehozása egyezményes mérföldkövek alapján

Az Ön szervezete, egy vezetési tanácsadó cég megegyezik, hogy piackutatást végez egy vevői termékre, amelyet a vevő értékesíteni tervez. Az ügyfél elfogadja az ajánlatot, és márciustól kezdődően három hónapon át igénybe veszi a szolgáltatást, amiért 50 000-et fizet a szervezetnek. A projekt három mérföldkőből áll:

-   1. mérföldkő: Fogyasztói adatok gyűjtése - március 31.
-   2. mérföldkő: A fogyasztói adatok elemzése - április 30.
-   3. mérföldkő: A termék piacképességi vizsgálatának bemutatása - május 31.

A vevő megegyezik, hogy 10 000-et fizet a szervezetének az első mérföldkőre, 20 000-et a másodikra és 20 000-et a harmadik mérföldkőre. 

Amikor létrehozza a projektszerződést, megegyezik, hogy a vevőt a befejezett mérföldkő alapján számlázza. Az időszakok beállítása az alábbi két lépésből áll:

-   A projekt mérföldköveit meghatározása.
-   Adja meg az egyes mérföldkövek elérésekor a vevőnek számlázandó összegeket.

Amikor az első mérföldkő március 31-én befejeződik, a mérföldkövet befejezettnek jelöli, majd létrehoz egy számlát 10 000 összeggel és elküldi a vevőnek. Mérföldkőre számla nem hozható létre mindaddig, amíg a mérföldkövet befejezettként meg nem jelöli.

### <a name="example-create-a-billing-rule-that-is-based-on-services-plus-a-management-fee"></a>Példa: Számlázási szabály létrehozása szolgáltatások, valamint egy kezelési díj alapján

Az Ön szervezete, egy vezetési tanácsadó cég megegyezik, hogy piackutatást végez egy vevői termék piacképességének vizsgálatára, amelyet a vevő, egy kiskereskedelmi vállalat fejleszt. A szerződés feltételei rögzítik, hogy Ön a három legjobb vezetői tanácsadóinak szolgáltatásait biztosítja, akik a kutatást lebonyolítják adott idő- és anyagköltség mellett. A vevő vállalja, hogy óránként 100-at fizet, továbbá 10 százalékos kezelési költséget a tanácsadási órákért, melyek a projekthez kerülnek számlázásra.. 

A projektszerződés létrehozásakor hozzon létre egy számlázási szabályt 10 százalék kezelési díj hozzáadásához a projekthez felszámított tanácsadási órákra. 

A vevő számára számlát hoz létre, amikor a vevőnek számlázott kezelési díj 10 százalék és tanácsadási órák költségét. Például ha három tanácsadó összesen 200 órát dolgozott a projekten, egy számla kerül létrehozásra 22 000 összeggel, az alábbi számítás alapján:

-   200 órát óránkénti 100 = 20 000
-   10 százalékos kezelési díja = 2 000
-   Teljes számlaösszeg = 22 000

Ha díjak adóköteles egy vevőnek, és a projektszerződés áfacsoport lehetőséget választja, az áfacsoport automatikusan bekerül a számlázási szabály díjak.

### <a name="example-create-a-billing-rule-for-the-value-of-time-and-materials"></a>Példa: Számlázási szabály létrehozása idő és anyagok értékére

Az Ön szervezete, egy szoftver tanácsadó cég megegyezik, hogy öt technikai tanácsadót biztosít egy szoftverfejlesztési projekthez egy vevő számára a következő hat hónapra. A vevő vállalja, hogy 150-et fizet minden konzultációs óráért, továbbá az irodai kellékek költségét. A szervezet számla küldése a vevőnek minden hónap végén. 

Amikor létrehozza a projektszerződést, megegyezik, hogy a vevőt minden egyes hónapban számlázza a projektre használt időre és anyagokra. Hoz létre a számlázási szabály, amely a következő információkat tartalmazza:

-   A szerződési időszak hat hónap.
-   A tanácsadási idő óránkénti 150 díjjal kerül számításra.
-   Az irodai kellékek önköltségi áron kerülnek számlázásra, és a projekt teljes költsége nem lehet nagyobb, mint 10 000.
-   Vevői számla létrehozása a projekt során minden naptári hónap végén.

Az első hónapban 800 órák összesen rögzítésre kerülnek a tanácsadók a projekt szerint. A projekthez számlázott irodai kellékek költsége 2 000. Tehát a hónap végén 122 000-re hoz létre számlát, amely úgy kerül kiszámításra, hogy 800 óra, óránkénti 150-el, továbbá 2000 az irodai kellékért.



