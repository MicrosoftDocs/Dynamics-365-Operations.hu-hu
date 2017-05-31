---
title: "Értékesítési visszáruk"
description: "Ez a témakör a visszárurendelések folyamatáról nyújt tájékoztatást. Magában foglalja a vevői visszárura vonatkozó információkat, valamint azok hatását a költségszámításra és a készletek mennyiségére."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 269384
ms.assetid: 98a4b517-e606-4036-b55f-1ab248898bdf
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: bdec28ba1fe3650f59520cb42a71497c54a7d93e
ms.contentlocale: hu-hu
ms.lasthandoff: 05/25/2017


---

# <a name="sales-returns"></a>Értékesítési visszáruk

[!include[banner](../includes/banner.md)]


Ez a témakör a visszárurendelések folyamatáról nyújt tájékoztatást. Magában foglalja a vevői visszárura vonatkozó információkat, valamint azok hatását a költségszámításra és a készletek mennyiségére.

A vevők számos különböző ok miatt küldhetnek visszárut. Például lehet, hogy egy cikk hibás, vagy nem felel meg a vevő elvárásainak. A visszárufolyamat olyankor indul el, amikor a vevő egy cikk visszaküldését kéri. Miután megérezik egy vevői kérés, a Microsoft Dynamics 365 for Operations programban visszárurendelés jön létre.

## <a name="return-order-process"></a>Visszárurendelés folyamata
A következő ábrán áttekinthető a visszárufolyamat.  

[![salesreturns01](./media/salesreturns01.jpg)](./media/salesreturns01.jpg)  

Kétféle visszárufeldolgozás létezik: a fizikai visszáru és a csak jóváírás.

-   **Fizikai visszáru** – A visszárurendelés engedélyezi a termékek fizikai visszaszállítását.
-   **Csak jóváírás** – A visszárurendelés engedélyezi vevőnél a jóváírást, de nem kell, hogy a vevő ténylegesen visszajuttassa a termékeket.

### <a name="physical-return-order-process"></a>Fizikai visszárurendelés folyamata

1.  **Visszárurendelés létrehozása.** Formálisan dokumentálja az ügyfélnek a hibás vagy nem kívánt termékek visszaküldésére vonatkozó engedélyét. A visszárurendelésnél nem kell, hogy a vállalat elfogadja a visszaküldött termékeket, illetve hogy jóváírást adjon a vevőnek. A visszaküldés elfogadása esetén engedélyezheti egy cserecikk elküldését a hibás cikk visszaküldését megelőzően.
2.  **Érkezzen meg a raktárba ellenőrzés.** Végezze el a kezdeti vizsgálati és ellenőrzési folyamatot a visszárurendelési bizonylat alapján. A visszárurendelés a visszaküldött cikkek karanténba helyezését is támogatja, ha további vizsgálatra és minőség-ellenőrzésre van szükség.
3.  **Intézkedés meghatározása.** Véglegesítse az ellenőrzési eljárást, és döntse el, hogy mi történjen a visszaküldött termékekkel. E lépés részeként döntse el, hogy jóváírja-e az összeget az ügyfélnél, visszautasítja-e a termék visszaküldését, vagy elfogadja-e a termék visszaszolgáltatását, törli-e a terméket, majd elküldi a csereterméket az ügyfélnek.
4.  **Hozzon létre szállítólevelet.** A csomagjegyzék készítése, és hajtsa végre az intézkedési döntést, amelyet a 3 lépésben is megtett. A logisztikai folyamat lezárása.
5.  **Számla előállítása.** A visszárurendelés szerkesztése.

### <a name="credit-only-process"></a>Csak jóváírás folyamat

1.  **Visszárurendelés létrehozása.** Hivatalosan a dokumentum hibás vagy nem kívánt termék vissza a vevőnek az engedélyt. A **Csak követelés** intézkedéskód engedélyezi a határozat nélkül fizikai visszaszállításánál a vevői jóváírást.
2.  **Számla előállítása.** A jóváírás létrehozása, és zárja be a visszáru rendelést.

## <a name="return-material-authorization"></a>Visszáru-jóváhagyás
Anyagok engedély (RMA) visszáruk feldolgozása épül értékesítési rendelésekkel kapcsolatos funkcióihoz. Az RMA visszáru rendelést, a program létrehoz egy eladási rendelést, és lehetnek társítva, úgynevezett helyettesítő rendelés más értékesítési rendelés van regisztrálva. Mindkét értékesítési rendelések csatolása az eredeti RMA-szám.

-   **Visszárurendelés** regisztrálni az RMA-hoz létre egy visszáru rendelést, amely egy eladási rendelést, a hozzárendelt típusa, **vissza a rendelés.** Az RMA-információk végzett módosításokat az eladási rendelés automatikusan frissül. Amíg a visszáru rendelés állapota a **nyitott**, nem jelenik meg az értékesítési rendelések listája. RMA használni, kezelni az érkezés és a visszaküldött cikkek átvételét, valamint a hitel csak intézkedési művelet engedélyezése (ld. **intézkedési kódok és intézkedési műveletek**). Az eladási rendelésen szereplő összes követési folyamat kell kezelni.
-   **Csererendelés** – egy cserecikkrendelést kell szállítani a vevőnek, ha az RMA második kapcsolódó eladási rendelés szerepelhet. Létrehozhat kézzel a csererendelés a közvetlen szállítás támogatására az RMA. Azt is megteheti csererendelés a program automatikusan készíti el az érkezés, a vizsgálati és a bevételezési töltik az RMA sor elemet, amely egy intézkedési kód, amely jelzi a csere után. A csererendelés kapcsolódó eladási rendelés ugyanazokat a funkciókat tartalmaz. Például használhatja azt a helyettesítő cikként egyéni termék konfigurálása, javítása a visszárut, küldeni a helyettesítő szállító közvetlen kiszállítás beszerzési rendelés létrehozása vagy egyéb célból támogatja a termelési rendelés létrehozása.

## <a name="create-a-return-order"></a>Visszárurendelés létrehozása
A visszáru-rendelési folyamat elindul, amikor egy ügyfél a szervezet vissza a hibás vagy nem kívánt terméket és/vagy jóváírandó. Miután a szervezet elfogadta a return, a return visszáru rendelés ismertetését. A visszárurendelés tájékoztatási központjának, a visszaküldött termék belső feldolgozás válik. Az alábbi ábrán látható a visszáru rendelés létrehozása.  

[![Visszárurendelés létrehozása](./media/salesreturn02.png)](./media/salesreturn02.png)

### <a name="create-a-return-order-header"></a>Új visszárurendelés létrehozása

Visszáru rendelés létrehozásakor szerepelnie kell a következő táblázatban szereplő adatokkal.

| Mező              | Leírás                                              | Megjegyzések                                                                                                                                                                                                                                                                                                                                        |
|--------------------|----------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Vevőkód   | Hivatkozás a számítási tábla rekordjára.                       | Meg kell adnia egy létező vevőszámla.                                                                                                                                                                                                                                                                                                  |
| Szállítási cím   | A cikk visszaküldéséhez használt cím                 | Alapértelmezés szerint a szervezet címet használja. Ha egy adott raktár van kiválasztva a fej, a szállítási címet a szállítási címet a raktár változik. Módosíthatja ezt a címet a **visszárurendelés részletei** oldalon.                                                                                                  |
| Raktár/hely     | A hely vagy raktár, amely fogadja a visszaküldött termék | A visszáru rendelés szállítási címét a webhely vagy a raktár a szállítási cím alapján határozza meg.                                                                                                                                                                                                                                 |
| RMA-szám         | A tevékenységhez rendelt kategória.              | Másodlagos kulcs a visszáru-rendelési folyamat során az RMA-szám lesz. Az automatikusan hozzárendelt RMA-szám, amely a **Kinnlevőségek paraméterei** lapon beállított RMA-számsorozaton alapszik.                                                                                                                              |
| Határidő           | Az utolsó dátum, amikor visszaadható egy cikk               | Az alapértelmezett érték számítása az aktuális dátum plusz érvényességi idő alapján történik. Például ha csak 90 napig érvényes a visszaküldés a visszáru-rendelés dátumától, és a visszáru rendelés május 1-jén jött létre, a mező értéke **július 30**. Az érvényességi időtartam beállítása a **Kinnlevőségek paraméterei** oldalon. |
| Visszaadási okkód | Az ok, ami miatt a vevő visszaadta a terméket          | Az Okkód választható ki a felhasználó által definiált okkódjainak listáját. A mező a későbbiekben bármikor szerkeszthető.                                                                                                                                                                                                                                    |

### <a name="create-return-order-lines"></a>Visszárurendelés sorainak létrehozása

Miután befejezte a visszáru fejlécét, az alábbi módszerek egyikével visszárusorokat hozhat létre:

-   Manuálisan adja meg a cikk részleteit, a mennyiséget és az egyéb adatokat minden visszárusornál.
-   Hozzon létre egy visszárusort az **Értékesítési rendelés megkeresése** funkcióval. Javasoljuk, hogy ezt a funkciót használja visszáru-rendelés létrehozásakor. Az **Értékesítési rendelés keresése** funkció a számlázott értékesítésirendelés-sort a visszáru rendelés sornak a hivatkozást hoz létre, és olvassa be a részletek, például cikkszám, mennyiség, ár, engedmény és az eladás sorból költségértékek sor. A hivatkozás segít garantálni, hogy amikor a terméket visszaküldik a vállalatnak, az ugyanazon egységköltséggel kerüljön felértékelésre, mint az eladás során. A hivatkozás azt is igazolja, hogy a visszáru-rendeléseket nem olyan mennyiségben hozták létre, amely meghaladja a számlán eladott mennyiséget.

**Megjegyzés:** Az értékesítési rendelésre hivatkozó visszárusorokat az értékesítés korrekciójaként vagy visszavonásaként kezelik. További tudnivalókért lásd a "Feladás a főkönyvbe" című részt, a témakör későbbi részében.

### <a name="charges"></a>Költségek

A visszáru-rendelés díjait a következő módszerek egyikével vagy többel egészítheti ki:

-   Manuálisan felveheti a díjat a visszáru-rendelés fejlécére, a visszárusorra vagy mindkettőre.
-   Az átutalási megbízás fejlécére a visszaküldési okok függvényében automatikusan feltölthetők a díjak.
-   Az átutalási megbízás fejlécére a sor intézkedéskódja alapján automatikusan feltölthetők a díjak.

A díjak automatikusan hozzáadódnak, miután a visszaküldés okának kódja vagy elosztási kód lett hozzárendelve a sorhoz. Ha később megváltoztatjuk az okkódot, a meglévő díjbevétel nem lesz eltávolítva, de az új ok kód alapján új díjbevitelt lehet hozzáadni. Amikor visszatérítési sorrendet ad meg, akkor a sor vagy sorrend százalékában kifejezett díjak negatívvá válnak, ha a vonal vagy a sorrend negatív, hacsak a százalék nem negatív szám. A negatív értékű díj az ügyfél számára nyújtott hitelt jelenti.

### <a name="return-reason-codes"></a>Visszaadási okkódok

Okkódok vissza alkalmazásával segíthet könnyebben visszatérési minták elemzése. Okkódok ismerteti, miért egy ügyfél szeretne cikkeket vissza. Egyes szervezeteknél sok okkód szerepel. E szervezet csoportosítja az okkódok okkódok csoportjai számára jobban áttekintheti és halmozott jelentéséért.

### <a name="disposition-codes-and-disposition-actions"></a>Intézkedési kódok és szabályozó intézkedések

A visszáru-rendelési folyamat fontos lépés a hozzárendelés egy intézkedéskódot a visszáru-rendelési sorhoz az érkezés regisztráció részeként. Az intézkedéskód határozza meg a következő adatokat:

-   **A pénzügyi következmények** – a vevőnek kell jóváírni a visszaküldött cikkeket, és minden díjat, ki kell egészíteni a visszáru-rendelési sor?
-   **A visszaküldött cikk intézkedése** – a cikk lehet hozzáadott készlet, kell azt kell selejtezni, vagy azt vissza kell küldeni a vevőnek?
-   **A visszaküldött cikk logisztikája** – egy cserecikk kiállítani a vevőnek?

Annak meghatározása, hogy milyen a térti áruk értékesítik, mellett intézkedéskódok okozhat a visszárusor alkalmazandó díjakat. Akkor is használható statisztikai elemzések eredménye csoportba. Visszárurendelések beállításainak részeként intézkedési kódok határozzák meg. Azonban minden egyes intézkedéskód hivatkoznia kell a beépített intézkedési műveletek egyikét. Az alábbi táblázatban a beépített intézkedési kódok és műveleteik szerepelnek. **Fontos:** He egy elem nem lesz visszaadva, de még mindig kell jóváírni a vevő, ha a **csak követel** a visszáru rendelés sornak a intézkedéskód.

<table>
<thead>
<tr class="header">
<th>Intézkedési kód</th>
<th>Pénzügyi következmények</th>
<th>A logisztikai vonatkozásai</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Csak követelés</td>
<td><ul>
<li>A vevő számláján az eladási ár minden díj vagy díjak levonásával.</li>
<li>A cikk selejtezési veszteség van feladva a főkönyvbe.</li>
</ul></td>
<td>A cikk nem küldhető vissza. A Törlés művelet a következő esetekben használható:
<ul>
<li>Nincs elegendő bizalmi kapcsolat a felek között.</li>
<li>A hibás cikk költségét nem engedheti.</li>
<li>A cikkek készletbe vissza sem lehet engedélyezni. Egyéb feltételek esetén nem szükséges fizikai visszaszállítása.</li>
</ul></td>
</tr>
<tr class="even">
<td>Követel</td>
<td><ul>
<li>A vevő számláján az eladási ár minden díj vagy díjak levonásával.</li>
<li>A készletérték növekszik a visszaküldött cikk költségét.</li>
</ul></td>
<td>Az elem vissza és kerül vissza a készletbe.</td>
</tr>
<tr class="odd">
<td>Csere és jóváírás</td>
<td><ul>
<li>A vevő számláján az eladási ár minden díj vagy díjak levonásával.</li>
<li>A készletérték növekszik a visszaküldött cikk költségét.</li>
<li>Egy külön értékesítési rendelés létrejön, és a program külön kezeli.</li>
</ul></td>
<td>Az elem vissza és kerül vissza a készletbe.</td>
</tr>
<tr class="even">
<td>Csere és selejtezés</td>
<td><ul>
<li>A vevő számláján az eladási ár minden díj vagy díjak levonásával.</li>
<li>A cikk selejtezési veszteség van feladva a főkönyvbe.</li>
<li>Egy külön értékesítési rendelés létrejön, és a program külön kezeli.</li>
</ul></td>
<td>Az elem vissza, és a hulladék.</td>
</tr>
<tr class="odd">
<td>Vissza a vevőnek</td>
<td>Nincs, kivéve minden díj vagy díjak.</td>
<td>A cikk érkezik, de a vizsgálat után küld vissza az vevő. A Törlés művelet használható, ha a cikk szándékosan sérült, vagy ha a jótállás érvénytelenítve lett.</td>
</tr>
<tr class="even">
<td>Selejt</td>
<td><ul>
<li>A vevő számláján az eladási ár minden díj vagy díjak levonásával.</li>
<li>A cikk selejtezési veszteség van feladva a főkönyvbe.</li>
</ul></td>
<td>Az elem vissza, és a hulladék.</td>
</tr>
</tbody>
</table>

## <a name="arrival-at-the-warehouse-for-inspection"></a>Érkezzen meg a raktárba ellenőrzésre
Visszaküldött cikkeket készletre könyvelésével egy szállítólevélen fizikailag kap, mielőtt a cikkek beérkezésének regisztrációja és nem kötelező ellenőrzést kell lépnie. A következő ábrán áttekinthető az érkeztetési folyamat. Az alábbi részek minden lépés, amely az ábrán látható.  

[![Érkeztetési folyamat](./media/salesreturn03.png)](./media/salesreturn03.png)  

A folyamat számos egyéb változattal rendelkezik, melyek nem szerepelnek ebben a témakörben. Az alábbiakban látható néhány ilyen változat:

-   Ne használja az **Érkeztetési áttekintés** listát Érkeztetési napló létrehozásához. Ehelyett manuális létrehozása a cikkérkezési napló. Visszáru rendeléseket kell **Értékesítési rendelés** referenciaként.
-   Raktárkezelés használata, a raklapos szállítások készítése. A Visszárusor állapota lesz **beérkezett** raklapos szállítás közben.
-   Segítségével közvetlenül a visszáru-rendelési sorból visszaküldött cikk érkezése regisztrálni a **regisztrációs** függvény.

A beérkezési folyamat során az általános folyamat a raktári beérkezés integrált értéket ad vissza. A beérkezési folyamat elhozatalára külön ellenőrző vizsgálatnak kell alávetni a karanténutasítások létrehozását is támogatja.

### <a name="identify-products-in-the-arrival-overview-list"></a>Érkezés áttekintés listájában termékek azonosítása

A **Érkeztetési áttekintés** lap felsorolja az összes tervezett bejövő érkezők. **Megjegyzés:** érkezése tranzakció típusú külön-külön kell feldolgozni az érkezések visszárurendelésekből. Után már azonosítani egy bejövő csomag a **Beérkezés áttekintése** (például úgy, hogy az RMA kísérőokmány segítségével), a műveletek ablaktábla a lap **Érkeztetés indítása** hozzon létre, és az cikkérkezési napló, amely megfelel az érkezési inicializálása.

### <a name="edit-the-arrival-journal"></a>Szerkessze az Érkeztetési napló tartalmát.

Beállításával a **Karantén kezelése** **Igen**, a visszáru rendelés sornak a karanténutasítást is létrehozhat. Egy sor el lett küldve a karantén vizsgálatra, a az intézkedéskód nem adható meg. **Megjegyzés:** Ha a **karantén kezelése** be **Igen** a cikk készletmodell-csoport, a a **karantén kezelése** a beállítás a **naplósorok** lap az érkeztetési napló sorában megjelöli, és nem módosítható. Karantén a sort küld, ha meg kell adnia a megfelelő karanténraktár. Ha az érkezési sort nem küldi el ellenőrzésre, a raktár érkeztetési képviselőjének meg kell adnia az intézkedési kódot közvetlenül az Érkeztetési napló sorban, majd fel kell adnia az Érkeztetési naplót. Ha az azonos intézkedéskód nem a teljes mennyiség visszárusor kell rendelni, vagy ha a teljes mennyiséget a sor még nem érkezett meg, fel kell osztania a sor. Az érkeztetési naplósor felosztásakor is felosztja a visszárusor (**SalesLine**), és hozzon létre egy új tétel. A sor szétválaszthatja az érkeztetési napló sorában mennyiségének csökkentésével. A napló könyvelésekor a program visszatérési új sor jön létre, amelyek állapota **várt** a fennmaradó mennyiség. Megoszthatja a sort, ha a **Funkciók**&gt;**Megosztást** pontra kattint.

### <a name="process-the-quarantine-order"></a>Karanténutasítás feldolgozása

Ha a visszaküldött termékek a karanténraktárban vizsgálatra küldi, minden további feldolgozásra a karanténutasítás kitölteni. Minden beérkezési sor karantén küldött egy karanténutasítás készül. Az intézkedéskód azt jelzi, hogy az ellenőrzési folyamat eredménye. A karanténutasítás szétválaszthatja, ugyanúgy, mint a cikkérkezési napló fel. A visszáru rendelés sornak megfelelő megoszlása okozhat, ha a karanténutasítás szétválasztásához. Az intézkedéskód beírásakor, töltse ki a karanténutasítás használatával a **vége** függvény vagy a **jelentés készként** függvény. Ha a **Jelentés készként** elemet választja, egy új beérkezés jön létre a kijelölt raktárban. Majd feldolgozhatja az érkezési segítségével a **Beérkezés áttekintése** oldalon. Ha az érkezés a karanténutasítás származik, az ellenőrzés során hozzárendelt intézkedéskód nem módosítható. Ha befejezte a karanténutasítás segítségével a **Vége** a rendszer automatikusan regisztrálja a függvényt, a tétel. Néha egy cikk lehet küldeni vissza a karanténból a szállítási és a fogadó osztály. Például a karantén ellenőr nem ismeri a készlet a cikk tárolási helyét. Ebben az esetben a megfelelő szállítólevél frissíteni kell, hogy megfelelően rögzíteni, és a az intézkedéskód miatt a karantén megadott jár el. Átvételi elismervényt lehet küldeni a vevőnek a visszárusor regisztrálásakor. A **Visszáru-elismervény** jelentés hasonlít az visszárurendelési bizonylatra. A **Visszáru-elismervény** jelentés nem naplózott vagy más módon a rendszerben regisztrált, és nem egy szükséges lépés a visszáru-rendelési folyamat.

## <a name="replace-a-product"></a>Termék cseréje
Helyettesítő termék kezelésének két módszere van:

-   **Előzetes csere** – cserélje ki a termék a vevő visszaküldött termék megérkezése előtt.
-   **Intézkedési kód váltja** – automatikusan helyettesítő új rendeléssor létrehozásához.

### <a name="up-front-replacement"></a>Előzetes csere

Az elülső csere során a csereeszköz a termék visszaküldése előtt szállítható az ügyfélnek. Ez a módszer akkor hasznos, ha például az elem egy olyan géprész, amelyet nem lehet eltávolítani, kivéve, ha pótalkatrész áll rendelkezésre a helyére, vagy csak azt szeretné, hogy az ügyfél a lehető leghamarabb megtalálja a cserealkatrészeket. Az előzetescsere-rendelés független értékesítési rendelés. A fejlécinformáció az ügyféltől inicializálódik, a sorinformáció pedig a visszáru-rendelésből inicializálódik. A csererendelést a visszárurendeléstől függetlenül szerkesztheti, feldolgozhatja és törölheti. Ha töröl egy csererendelést, kap egy üzenetet, hogy a rendelés helyettesítő rendelésként lett létrehozva. A következő ábrán az előzetes csere folyamata látható.  

[![Előzetes csere folyamata](https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn04.png)](https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn04.png)  

A visszárurendelés hivatkozást tartalmaz a csererendelésre. Ha a hibás tétel visszaszolgáltatása előtt egy visszaállítási sorrendet hoz létre a visszatérési megrendeléshez, a hibás tétel visszaadását követően nem választhatja ki a helyreállítási kódokat.

### <a name="replacement-by-disposition-code"></a>Intézkedéskód helyettesítése

Ha az ügyfélnek szállított egy cserecikket, és használja a **csere és selejtezés** vagy **csere és jóváírás** a visszárurendelés intézkedési művelet használata a folyamat, amely az alábbi ábrán látható.  

[![Helyettesítő folyamatot egy intézkedéskód használatakor](https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn05.png)](https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn05.png)  

A csereeszköz önálló értékesítési megrendeléssel, a helyettesítő értékesítési rendeléssel történik. Ez az értékesítési rendelés a visszáru-rendelés szállítólevelének létrehozásakor jön létre. A rendelés fejlécében a visszáru rendelés fejen a hivatkozott vevőtől származó adatokat használja. A sor adatgyűjtés megadott adatok alapján a **Helyettesítő cikk** oldalon. A **Helyettesítő cikk** lapot ki kell tölteni intézkedési műveleteket a word "csere." kezdetű sorok Azonban a mennyiség és a helyettesítő cikk azonosításával járó nem érvényesített vagy korlátozott. Ez a viselkedés lehetővé teszi, hogy olyan esetekben, ahol a vevő szeretné ugyanazt a cikket, de egy másik konfigurációt vagy méretét, valamint esetekben azt szeretné, ahol a vevők egy teljesen másik elemet. Alapértelmezés szerint egy azonos elemet meg a **Helyettesítő cikk** oldalon. Választhatja azonban egy másik elemet, feltéve, hogy a funkció be van állítva. **Megjegyzés:** szerkesztheti és törölheti a cserecikk-eladási rendelést létrehozását követően.

## <a name="generate-a-packing-slip"></a>Hozzon létre szállítólevelet
Ahhoz, hogy a visszaküldött cikkeket bevételezni lehessen a készletbe, frissíteni kell annak a rendelésnek a csomagjegyzékét, amelyhez a cikkek tartoznak. Ahogyan a számlafrissítés folyamata a pénzügyi tranzakció frissítése, úgy a csomagjegyzék-frissítés folyamata a készletrekord fizikai frissítése, amely véglegesíti a készlet változásait. Más szóval ez a folyamat véglegesíti a készlet módosításait. Visszaküldés esetén a csomagjegyzék frissítésekor az intézkedési művelethez tartozó lépéseket is végrehajtják. A csomagjegyzék létrehozásakor a következők történnek:

-   A raktárban a tényleges bevételezés végrehajtásához a szokásos eljárást kell alkalmazni. Főkönyvi feladások jönnek létre, ha a készletkönyvelési csoport minta (**tényleges készlet feladása**) és a Kinnlevőségek paraméterei (**Szállítólevél főkönyvi feladása**) megfelelően vannak beállítva.
-   A "hulladék" szót tartalmazó intézkedési művelet megjelölt selejtnek, és a készletveszteség a főkönyvbe.
-   A jelölt elemek a **vissza a vevőnek** besorolási műveletet kapott, és az ügyfél. Ezek az elemek nem befolyásolják a készletben.
-   Az új csererendelés létrehozása megtörténik. Ez az értékesítési rendelés adatain alapul a **Helyettesítő cikk** oldalon.

Csak azokat a sorokat, amelyek állapota visszáru szállítólevél hozhat létre **Bejegyzett**, és csak a visszáru rendelés sornak a teljes mennyiségét. Ha több sort a visszáru rendelés a **Bejegyzett** állapotát, a szállítólevél sorok részhalmazát elő a többi sor törlése a **szállítólevél könyvelése** oldalon. A részleges szállítások visszárurendelés-sorok, nem pedig visszárurendelés-szállítmányok formájában vannak meghatározva. Ez annyit jelent, hogy ha a visszárurendelés egyik sorában szereplő teljes mennyiséget visszaküldik, de a többi sor mennyiségéből semmit, akkor a szállítás nem részleges szállítás. Ha viszont egy visszárurendelés-sorban az adott cikkből tíz visszaküldendő egység szerepel, és ebből csak négyet kap meg, akkor ez egy részleges szállítás. Ha nem várható visszáru elemeinek érkeztek, félretéve a szállítólevelet, és várja meg a többi érkezzen a visszatérő mennyiség. Azt is megteheti regisztrálása és feladása a részleges mennyiséget. A szállítólevelek könyvelési folyamat részeként a csomagjegyzék hivatkozási száma a vevő szállítási dokumentumokból is társíthat a rendelési sorokban. Ez a társítás nem kötelező, és csak referenciaként szolgál. Ez nem hoz létre tranzakciós frissítéseket. Általában ki lehet hagyni a szállítólevél folyamatát, és folytatható a számlázás. Ebben az esetben a, ha szállítólevél-bizonylat létrehozása során végzett volna lépéseket számlázás során.

## <a name="generate-an-invoice"></a>Számla előállítása
Bár a **Visszárurendelés** lapon található információk és tevékenységek, amelyek szükségesek ahhoz, hogy kezelni a különleges logisztikai szempontok a visszárurendelés kell használnia az **Értékesítési rendelés** oldalon a számlázási folyamat befejezéséhez. A szervezet majd számlázhatja visszáru rendelések vagy eladási rendelések egy időben, és ugyanaz a személy, szükség szerint a számlázási folyamat végrehajtásához. A visszáru rendelés megtekintéséhez az **Értékesítési rendelés** lap, kattintson a hivatkozásra kattintva nyissa meg a megfelelő eladási rendelést az értékesítési rendelés számát. A visszárurendelés is megtalálható a **Minden értékesítési rendelések** lapon. Visszáru rendelések, amelyek a rendelés típusát az értékesítési rendelések **Visszaküldött rendelés**.

### <a name="credit-correction"></a>Jóváírás korrekciója

A számlázási folyamat részeként a vegyes költségek helyességének ellenőrzése. Ahhoz, hogy a főkönyvi feladások javításokat (sztornó) válik, fontolja meg a **jóváírás-korrekció** a beállítás a **más** lapján a **számla** oldal a számla/jóváírás könyvelésekor. **Megjegyzés:** alapértelmezés szerint a **hitel javítás** beállítás aktiválva van, ha a **Jóváírás helyesbítésként** a beállítás a **Kinnlevőségek paraméterei** lap engedélyezve van. Azonban azt javasoljuk, hogy Ön nem post visszaad sztornó.

## <a name="create-intercompany-return-orders"></a>A vállalatközi visszárurendelések létrehozása
Visszárurendelések hajtható végre a szervezeten belül a két vállalat között. A varázsló a következő forgatókönyveket támogatja:

-   Egy vállalatközi kapcsolatban részt vevő két vállalat közötti egyszerű vállalatközi beolvasása
-   Vállalatközi láncon keresztül, amely az eladó vállalat vevői visszáru rendelés létrehozásakor jön létre
-   Vállalatközi láncon keresztül, amely a vevő vállalat szállítói visszáru rendelésének létrehozásakor jön létre
-   Közvetlen kiszállítás, szállítási egy külső vevő és egy vállalatközi kapcsolatban részt vevő két vállalat közötti adja vissza

### <a name="setup"></a>Beállítás

Az alábbi ábra a minimális telepítés, szükség a két részt egy vállalatközi kapcsolatot, és kihasználják a vállalatközi kereskedelmi vállalat.  

[![Minimális beállítás](https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn06.png)](https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn06.png)  

A következő forgatókönyvben a CompBuy a vevő vállalat és a CompSell az eladó vállalat. Általában az eladó vállalat hajók áru a vásárló vállalatnak vagy, közvetlen kiszállítás szállítólevél esetekben közvetlenül a végső vevő számára. A CompBuy, a Vállalatközi szállító\_CompSell a meghatározás szerint egy vállalatközi végponthoz társított a vállalat CompSell. Ugyanakkor a CompBuy, a Vállalatközi szállító\_CompSell a meghatározás szerint egy vállalatközi végponthoz társított a vállalat CompBuy. A megfelelő intézkedéseket a házirend részletei és értékmegfeleltetések mindkét vállalat meg kell határozni. Egy vállalatközi, egyben a vállalatközi értékesítési rendelés, visszáru rendelés közvetlen kiszállítás szállítás esetén az eladó vállalat létrejön. A vállalatközi visszáru rendelés RMA-szám RMA számsorozat CompSell kell kivételezni, vagy az RMA-szám CompBuy az eredeti visszárurendelés rendelt átmásolható. Az RMA szám beállításait a **PurchaseRequisition** CompBuy a műveleti irányelv határozza meg ezeket a műveleteket. Ha az RMA-szám szinkronizálása, meg kell terveznie szám ütközés kockázatának csökkentése, ha a két vállalat használja ugyanazt a számsorozatot.

### <a name="simple-intercompany-returns"></a>Egyszerű vállalatközi visszáruk

Ebben az esetben a két vállalat a szervezethez, az alábbi ábrán látható módon.  

[![Egyszerű vállalatközi visszáruk](https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn07.png)](https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn07.png)  

A rendelési lánc akkor jöhet létre, ha a vevő vállalatnál létrehoznak egy szállítói visszárurendelést, illetve amikor az eladó cégnél létrehoznak egy vevői visszárurendelést. A Dynamics 365 for Operations műveleteket hoz létre a megfelelő sorrendben a másik társaság, és meggyőződik arról, hogy a fej és sor-információt a szállítói visszáru rendelés tükrözi a beállításokat a vevő a visszáru rendelés. A létrehozott visszáru rendelést vagy kihagyhatjuk vagy beszámíthatjuk a hivatkozás (**Értékesítési rendelés keresése**) egy meglévő vevő számlát. A csomagjegyzékek és számlák két rendelések dolgozhatók fel külön-külön. Például nem kell létrehozni a szállítói visszáru rendelés csomagjegyzékét a Vevői visszáru rendelés csomagjegyzékének elkészítése előtt.

### <a name="direct-delivery-shipment-returns-among-three-parties"></a>Közvetlen kiszállítás visszárui három fél között

Ebben az esetben állapítható meg, ha egy korábbi értékesítése a **a közvetlen szállítást** típus van-e töltve, és ha számlával szemben a vevő szerepel a vállalat kommunikáló az ügyféllel. Az alábbi ábrán a CompBuy vállalat korábban termékeket adott el és számlázott ki az Extern ügyfélnek. A termékek a vállalat CompSell közvetlenül a leszállították a vevőnek egy vállalatközi láncon keresztül.  

[![Közvetlen kiszállítás visszárui három fél között](https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn08.png)](https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn08.png)  

Ha Extern vevő vissza szeretné küldeni a termékeket, akkor visszárurendelés (RMA02) jön létre a vevő számára a CompBuy vállalatnál. A vállalatközi lánc létrehozásához a visszáru-rendelést közvetlen kiszállításra kell jelölni. Használata esetén a **található értékesítési rendelés** a vevői számla visszaállításához válasszon függvény létrejön egy vállalatközi lánc, amely a következő dokumentumokat:

-   **Eredeti visszárurendelés:** RMA02 (CompBuy cég)
-   **Beszerzési rendelés:** PO02 (CompBuy cég)
-   **Vállalatközi visszáru rendelés:** RMA\_00032 (CompSell cég)

Vállalatközi közvetlen szállítási láncban létrehozása után az összes fizikai kezelés és a visszáruk feldolgozása kell előfordulnia összefüggésben a vállalatközi visszáru rendelés RMA\_00032 a vállalat CompSell. A termékek nem fogadható el a vállalat CompBuy. A vállalatközi visszáru rendelés hozzá van rendelve egy intézkedéskódot, ha azt az eredeti visszáru rendelés az eredeti rendelés megfelelő számlázás lehetővé szinkronizálva.

## <a name="post-to-the-ledger"></a>Feladás a főkönyvbe
A visszáru rendelés számlázásakor létrehozott főkönyvi feladások néhány fontos beállítások és paraméterek befolyásolják:

-   **Visszáru-önköltségi ár** – a készlet eltérő modellek **általános költség**, a **visszáru-önköltségi ár** paraméter határozza meg a cikk költségét vissza a készletbe elfogadott vagy hulladék. Kiszámításához a megfelelő Készletértékelés, fontos beállítani a **visszáru-önköltségi ár** paraméter megfelelően. Ha a **található értékesítési rendelés** függvény egy hivatkozást a vevői számla, visszáru-rendelési sor létrehozása a **visszáru-önköltségi ár** értéke egyenlő az önköltségi ár a cikk eladása. Egyébként önköltségi ár értékét a cikk beállítása származik, vagy manuálisan is megadhatók.
-   **Javítási/sztornírozott jóváírás** – a **korrekciós követel** paraméter a **számla** lap határozza meg, hogy a feladások legyen rögzített (Tartozás/Követelés) pozitív tételeket, vagy javítása, a negatív tételeket.

Az alábbi példákban a visszáru-önköltségi ára ábrázolva **számlaengedmény önköltségi ár**.

### <a name="example-1-the-return-order-doesnt-reference-a-customer-invoice"></a>1. példa: A visszárurendelés nem hivatkozhat a vevői számla

A visszárurendelés nem hivatkozhat a vevői számla A visszárucikk létrejön. A **Jóváírás korrekciója** paraméter nincs kijelölve, ha létrejön a visszáru-rendelés számlája vagy jóváírása.  

[![Visszárurendelés nem hivatkozik a vevő számlára](https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn09.png)](https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn09.png)  

**Megjegyzés:** a Cikkár fő része lesz az alapértelmezett érték a **visszáru-önköltségi ár** paraméter. Az alapértelmezett ár készletkiadás alkalmával az önköltségi ár eltér. A tényezők ezért 3 veszteség keletkezett. Ezenkívül a visszáru rendelést az eladási rendelésen a vevőnek adott engedmény nem tartalmaz. Ezért a túlzott követel következik be.

### <a name="example-2-credit-correction-is-selected-for-the-return-order"></a>2. példa: A jóváírás-korrekció kijelöltük a visszárurendelés

2. példa megegyezik 1,. példa, de a **hitel javítás** paraméter meg van jelölve, ha a visszáru-rendelési számla jön létre.  

[![A jóváírás-korrekció kijelöltük a visszárurendelés ](https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn10.png)](https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn10.png)  

**Megjegyzés:** negatív helyesbítés főkönyvi feladások kerülnek.

### <a name="example-3-the-return-order-line-is-created-by-using-the-find-sales-order-function"></a>3. példa: A visszáru-rendelési sor létrejön az eladási rendelés keresés funkció használatával

A visszáru-rendelési sor létrejön az **Értékesítési rendelés keresése** funkció használatával A **Hitel javítás** paraméter nincs bejelölve, a számla létrehozásakor.  

[![A visszáru-rendelési sor létrejön az eladási rendelés keresés funkció használatával ](https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn11.png)](https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn11.png)  

**Megjegyzés:** Az **Engedmény** és a **Visszáru-önköltségi ár** mezők helyesen vannak beállítva. Ezért a vevői számla pontos sztornírozása következik be.




