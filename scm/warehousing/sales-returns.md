---
title: "Értékesítési visszáruk"
description: "Ez a témakör a visszárurendelések folyamatáról. Vevői visszáru és ezek hatása a költségszámítási és az aktuális készlet mennyiségét kapcsolatos információkat tartalmaz."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 269384
ms.assetid: 98a4b517-e606-4036-b55f-1ab248898bdf
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 3d02a15387231160f5b8a237aa11008b91ef1223
ms.openlocfilehash: b265a20a271230de5dba6df93900a24aad642885
ms.lasthandoff: 03/31/2017


---

# <a name="sales-returns"></a>Értékesítési visszáruk

Ez a témakör a visszárurendelések folyamatáról. Vevői visszáru és ezek hatása a költségszámítási és az aktuális készlet mennyiségét kapcsolatos információkat tartalmaz.

Vevők visszatérés elemek különböző okok miatt. Például lehet, hogy egy cikk hibás, vagy azt nem felel meg a vevő elvárásainak. A visszáru folyamat elindul, amikor a vevő visszaküldje a kérelem. Után a vevő kérés érkezik, a Microsoft Dynamics 365 műveletek visszárurendelés jön létre.

## <a name="return-order-process"></a>Visszáru-rendelési folyamat
A következő ábra áttekintést nyújt a visszáru-rendelési folyamat.  

[![salesreturns01](./media/salesreturns01.jpg)](./media/salesreturns01.jpg)  

Visszáru-rendelési folyamat két típusa van: fizikai vissza, és csak követel.

-   **Fizikai visszaszállítása** – a visszáru rendelést engedélyezi a termékek fizikai visszaszállítása.
-   **Csak követel** – a visszáru rendelést engedélyezi egy vevői jóváírás, de nem kell, hogy a vevő ténylegesen visszajuttatnia a termékeket.

### <a name="physical-return-order-process"></a>Fizikai visszárurendelési folyamat

1.  **Visszárurendelés létrehozása.** Hivatalosan a dokumentum hibás vagy nem kívánt termék vissza a vevőnek az engedélyt. A visszárurendelés nem kell, hogy a társaság fogadja a visszaküldött termékek, vagy adja meg a vevő követel. A visszaküldés elfogadása esetén engedélyezheti egy cserecikk elküldését megelőzően a hibás cikket ő visszaküldené.
2.  **Raktári ellenőrzés céljából érkeznek.** Töltse ki egy kezdeti vizsgálati és ellenőrzési ellen a visszárurendelési bizonylatra. A visszárurendelés is támogatja a visszaadott elemek karantén további vizsgálatra és minőség-ellenőrzés.
3.  **Intézkedési határozza meg.** Az ellenőrzési eljárás véglegesítése, és döntse el, hogy mi történjen a visszaküldött termékek. Ez a lépés részeként döntse el, hogy meg a vevő jóváírás, elutasítja a termék vissza vagy fogadja el a termék vissza, hulladékot a termék, és küldje el az ügyfélnek a helyettesítő termék.
4.  **A csomagjegyzék készítése.** A csomagjegyzék készítése, és hajtsa végre az intézkedési döntést, amelyet a 3. A logisztikai folyamat lezárása.
5.  **Számla készítése.** Zárja be a visszáru rendelést.

### <a name="credit-only-process"></a>A hitel csak feldolgozása

1.  **Visszárurendelés létrehozása.** A dokumentum hivatalosan az engedélyt a vevő hitelt nem tér vissza a hibás vagy nem kívánt termékek számára. A **csak követel** intézkedéskód engedélyezi a határozat nélkül fizikai visszaszállítása a vevő jóváírás.
2.  **Számla készítése.** A jóváírás létrehozása, és zárja be a visszáru rendelést.

## <a name="return-material-authorization"></a>Visszáru anyag engedélyezési
Anyagok engedély (RMA) visszáruk feldolgozása épül értékesítési rendelésekkel kapcsolatos funkcióihoz. Az RMA visszáru rendelést, a program létrehoz egy eladási rendelést, és lehetnek társítva, úgynevezett helyettesítő rendelés más értékesítési rendelés van regisztrálva. Mindkét értékesítési rendelések csatolása az eredeti RMA-szám.

-   **Visszárurendelés** regisztrálni az RMA-hoz létre egy visszáru rendelést, amely egy eladási rendelést, a hozzárendelt típusa, **vissza a rendelés.** Az RMA-információk végzett módosításokat az eladási rendelés automatikusan frissül. Amíg a visszáru rendelés állapota a **nyitott**, nem jelenik meg az értékesítési rendelések listája. RMA használni, kezelni az érkezés és a visszaküldött cikkek átvételét, valamint a hitel csak intézkedési művelet engedélyezése (ld. **intézkedési kódok és intézkedési műveletek**). Az eladási rendelésen szereplő összes követési folyamat kell kezelni.
-   **Csererendelés** – egy cserecikkrendelést kell szállítani a vevőnek, ha az RMA második kapcsolódó eladási rendelés szerepelhet. Létrehozhat kézzel a csererendelés a közvetlen szállítás támogatására az RMA. Azt is megteheti csererendelés a program automatikusan készíti el az érkezés, a vizsgálati és a bevételezési töltik az RMA sor elemet, amely egy intézkedési kód, amely jelzi a csere után. A csererendelés kapcsolódó eladási rendelés ugyanazokat a funkciókat tartalmaz. Például használhatja azt a helyettesítő cikként egyéni termék konfigurálása, javítása a visszárut, küldeni a helyettesítő szállító közvetlen kiszállítás beszerzési rendelés létrehozása vagy egyéb célból támogatja a termelési rendelés létrehozása.

## <a name="create-a-return-order"></a>Visszárurendelés létrehozása
A visszáru-rendelési folyamat elindul, amikor egy ügyfél a szervezet vissza a hibás vagy nem kívánt terméket és/vagy jóváírandó. Miután a szervezet elfogadta a return, a return visszáru rendelés ismertetését. A visszárurendelés tájékoztatási központjának, a visszaküldött termék belső feldolgozás válik. Az alábbi ábrán látható a visszáru rendelés létrehozása.  

[![Visszárurendelés létrehozása](./media/salesreturn02.png)](./media/salesreturn02.png)

### <a name="create-a-return-order-header"></a>Visszáru-rendelési fejléc létrehozása

Visszáru rendelés létrehozásakor szerepelnie kell a következő táblázatban szereplő adatokkal.

| Mező              | Leírás                                              | Megjegyzések                                                                                                                                                                                                                                                                                                                                        |
|--------------------|----------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Vevőkód   | A Vevők tábla hivatkozás                       | Meg kell adnia egy létező vevőszámla.                                                                                                                                                                                                                                                                                                  |
| Szállítási cím   | A cím, a cikk visszakerül                 | Alapértelmezés szerint a szervezet címet használja. Ha egy adott raktár van kiválasztva a fej, a szállítási címet a szállítási címet a raktár változik. Módosíthatja ezt a címet a **visszárurendelés részletei** oldalon.                                                                                                  |
| Hely/raktár     | A hely vagy raktár, amely fogadja a visszaküldött termék | A visszáru rendelés szállítási címét a webhely vagy a raktár a szállítási cím alapján határozza meg.                                                                                                                                                                                                                                 |
| RMA-szám         | A rendelt a visszáru rendelés azonosítója              | Másodlagos kulcs a visszáru-rendelési folyamat során az RMA-szám lesz. Az RMA-szám hozzárendelt alapul RMA számsorozat, amely be van állítva a **Kinnlevőségek paraméterei** oldalon.                                                                                                                              |
| Határidő           | Az utolsó dátum visszaadható elem               | Az alapértelmezett érték számítása az aktuális dátum plusz érvényességi ideje. Például ha csak 90 napig a napot, amikor a visszáru rendelés létrejön, és a visszáru rendelés május 1-jén jött létre egy vissza érvényes, a mező értéke **30-július**. Az érvényességi időtartam beállítása a **Kinnlevőségek paraméterei** oldalon. |
| Visszaadási okkód | A termék a vevő oka          | Az Okkód választható ki a felhasználó által definiált okkódjainak listáját. Ezt a mezőt bármikor frissítheti.                                                                                                                                                                                                                                    |

### <a name="create-return-order-lines"></a>Visszáru-rendelési sorok létrehozása

Miután befejezte a visszáru fej, az alábbi módszerek egyikével visszárusorokat hozhat létre:

-   Manuálisan adja meg a részleteit, a mennyiség és az egyéb adatokat minden visszárusor.
-   Hozzon létre egy visszáru sort segítségével a **található értékesítési rendelés** függvény. Javasoljuk, hogy ezt a funkciót használja, amikor visszáru rendelést hoz létre. A **található értékesítési rendelés** függvény a számlázott értékesítésirendelés-sort a visszáru rendelés sornak a hivatkozást hoz létre, és olvassa be a részletek, például cikkszám, mennyiség, ár, engedmény és az eladás sorból költségértékek sor. A hivatkozás segítségével garantálja, hogy a termék a vállalat kapja, amikor azt van értékelni az azonos egységköltséggel, hogy eladtak. A hivatkozás is ellenőrzi, hogy a visszáru rendelések adták el a számlán szereplő mennyiséget meghaladó mennyiségre nem jön létre.

**Megjegyzés:** javításokat, vagy az értékesítés az értékesítési rendelésre vonatkozó hivatkozás visszáru sorokat kezeli. További információért lásd a "Főkönyvi könyvelése" szakasz a témakör későbbi részében található.

### <a name="charges"></a>Költségek

Díjak és illetékek adhatók hozzá a visszárurendelés keresztül az alábbi módszerek egyikét:

-   Költségek manuális felvétele a visszáru-rendelési fej vagy a visszáru-rendelési sor.
-   Vegyes költségek automatikusan hozzáadhatók a visszáru rendelés fejen a visszaküldési okkód függvényében.
-   Vegyes költségek automatikusan hozzáadhatók a visszáru-rendelési sor, a az intézkedéskód sor alapján.

Vegyes költségek automatikusan hozzáadódnak a visszaküldési okkód után vagy intézkedéskód hozzá van rendelve a sor. Ha az Okkód később módosul, a meglévő tétel nem távolítja el, de lehet hozzáadni egy új tétel, az új okkód alapján. Költségek a visszáru-rendelési sorok hozzáadásakor a sor vagy a rendelés értékének százalékaként számított költségek válnak negatív a sort vagy a rendelés sor értéke negatív, kivéve, ha az értéke negatív szám. Negatív értékű díjat a vevőnek követel jelöli.

### <a name="return-reason-codes"></a>Visszaadási okkódok

Okkódok vissza alkalmazásával segíthet könnyebben visszatérési minták elemzése. Okkódok ismerteti, miért egy ügyfél szeretne cikkeket vissza. Egyes szervezeteknél sok okkódokat. E szervezet csoportosítja az okkódok okkódok csoportjai számára jobban áttekintheti és halmozott jelentéséért.

### <a name="disposition-codes-and-disposition-actions"></a>Intézkedési kódok és szabályozó intézkedések

A visszáru-rendelési folyamat fontos lépés a hozzárendelés egy intézkedéskódot a visszáru-rendelési sorhoz az érkezés regisztráció részeként. Az intézkedéskód határozza meg a következő adatokat:

-   **A pénzügyi következményekre** – a vevőnek kell jóváírni a visszaküldött cikkeket, és minden díjat, ki kell egészíteni a visszáru-rendelési sor?
-   **A visszaküldött cikk intézkedési** – a cikk lehet hozzáadott készlet, kell azt kell selejtezni, vagy azt vissza kell küldeni a vevőnek?
-   **A logisztikai visszaküldött cikk** – egy cserecikk kiállítani a vevőnek?

Annak meghatározása, hogy milyen a térti áruk értékesítik, mellett intézkedéskódok okozhat a visszárusor alkalmazandó díjakat. Akkor is használható statisztikai elemzések eredménye csoportba. Visszárurendelések beállításainak részeként intézkedési kódok határozzák meg. Azonban minden egyes intézkedéskód hivatkoznia kell a beépített intézkedési műveletek egyikét. A következő táblázat a beépített intézkedési kódok és tevékenységeiket. **Fontos:** elem nem lesznek visszaadva, de még mindig kell jóváírni a vevő, ha a **csak követel** a visszáru rendelés sornak a intézkedéskód.

<table>
<thead>
<tr class="header">
<th>Intézkedési kód</th>
<th>Pénzügyi vonatkozásai</th>
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
<td>A cikk nem vissza kell adni. A Törlés művelet a következő esetekben használható:
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
<li>Készletérték a visszaküldött cikk költségét növekszik.</li>
<li>Egy külön értékesítési rendelés létrejön, és a program külön kezeli.</li>
</ul></td>
<td>Az elem vissza és kerül vissza a készletbe.</td>
</tr>
<tr class="even">
<td>Csere és selejtezés</td>
<td><ul>
<li>Vevő követel tételként az eladási ár, csökkentve bármely illetékek és díjak.</li>
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
<td>Az elem vissza vagy hulladék.</td>
</tr>
</tbody>
</table>

## <a name="arrival-at-the-warehouse-for-inspection"></a>Érkezés ellenőrzés céljából a raktárban
Visszaküldött cikkeket készletre könyvelésével egy szállítólevélen fizikailag kap, mielőtt a cikkek beérkezésének regisztrációja és nem kötelező ellenőrzést kell lépnie. A következő ábra áttekintést nyújt a beérkezési folyamat. Az alábbi részek minden lépés, amely az ábrán látható.  

[![Érkezés folyamat](./media/salesreturn03.png)](./media/salesreturn03.png)  

A folyamat még egyéb változatok Ez a témakör nem vonatkozik. Íme néhány ezek a változatok:

-   Ne használja a **Érkeztetési áttekintés** lista létrehozása a cikkérkezési napló. Ehelyett manuális létrehozása a cikkérkezési napló. Visszáru rendeléseket kell **eladási rendelés** referenciaként.
-   Raktárkezelés használata, a raklapos szállítások készítése. A Visszárusor állapota lesz **beérkezett** raklapos szállítás közben.
-   Segítségével közvetlenül a visszáru-rendelési sorból visszaküldött cikk érkezése regisztrálni a **regisztrációs** függvény.

A beérkezési folyamat során az általános folyamat a raktári beérkezés integrált értéket ad vissza. A beérkezési folyamat elhozatalára külön ellenőrző vizsgálatnak kell alávetni a karanténutasítások létrehozását is támogatja.

### <a name="identify-products-in-the-arrival-overview-list"></a>Érkezés áttekintés listájában termékek azonosítása

A **Érkeztetési áttekintés** lap felsorolja az összes tervezett bejövő érkezők. **Megjegyzés:** érkezése tranzakció típusú külön-külön kell feldolgozni az érkezések visszárurendelésekből. Után már azonosítani egy bejövő csomag a **Beérkezés áttekintése** (például úgy, hogy az RMA kísérőokmány segítségével), a műveletek ablaktábla a lap **Érkeztetés indítása** hozzon létre, és az cikkérkezési napló, amely megfelel az érkezési inicializálása.

### <a name="edit-the-arrival-journal"></a>A cikkbeérkezési napló szerkesztése

Beállításával a **karantén kezelése** be **Igen**, a visszáru rendelés sornak a karanténutasítást is létrehozhat. Egy sor el lett küldve a karantén vizsgálatra, a az intézkedéskód nem adható meg. **Megjegyzés:** Ha a **karantén kezelése** be **Igen** a cikk készletmodell-csoport, a a **karantén kezelése** a beállítás a **naplósorok** lap az érkeztetési napló sorában megjelöli, és nem módosítható. Karantén a sort küld, ha meg kell adnia a megfelelő karanténraktár. Ha a beérkezés sor vizsgálatra nem küldött, a raktári beérkezési adminisztrátor kell közvetlenül a érkezési naplósorban adja meg a az intézkedéskód és a érkeztetési napló feladása. Ha az azonos intézkedéskód nem a teljes mennyiség visszárusor kell rendelni, vagy ha a teljes mennyiséget a sor még nem érkezett meg, fel kell osztania a sor. Az érkeztetési naplósor felosztásakor is felosztja a visszárusor (**SalesLine**), és hozzon létre egy új tétel. A sor szétválaszthatja az érkeztetési napló sorában mennyiségének csökkentésével. A napló könyvelésekor a program visszatérési új sor jön létre, amelyek állapota **várt** a fennmaradó mennyiség. A sor gombra kattintva is feloszthat **funkciók**&gt;**osztott**.

### <a name="process-the-quarantine-order"></a>A karanténutasítás folyamat

Ha a visszaküldött termékek a karanténraktárban vizsgálatra küldi, minden további feldolgozásra a karanténutasítás kitölteni. Minden beérkezési sor karantén küldött egy karanténutasítás készül. Az intézkedéskód azt jelzi, hogy az ellenőrzési folyamat eredménye. A karanténutasítás szétválaszthatja, ugyanúgy, mint a cikkérkezési napló fel. A visszáru rendelés sornak megfelelő megoszlása okozhat, ha a karanténutasítás szétválasztásához. Az intézkedéskód beírásakor, töltse ki a karanténutasítás használatával a **vége** függvény vagy a **jelentés készként** függvény. Ha **készként jelenteni**, egy új beérkezés a kijelölt raktárban jön létre. Majd feldolgozhatja az érkezési segítségével a **Beérkezés áttekintése** oldalon. Ha az érkezés a karanténutasítás származik, az ellenőrzés során hozzárendelt intézkedéskód nem módosítható. Ha befejezte a karanténutasítás segítségével a **vége** a rendszer automatikusan regisztrálja a függvényt, a tétel. Néha egy cikk lehet küldeni vissza a karanténból a szállítási és a fogadó osztály. Például a karantén ellenőr nem ismeri a készlet a cikk tárolási helyét. Ebben az esetben a megfelelő szállítólevél frissíteni kell, hogy megfelelően rögzíteni, és a az intézkedéskód miatt a karantén megadott jár el. Átvételi elismervényt lehet küldeni a vevőnek a visszárusor regisztrálásakor. A **visszáru-elismervény** jelentés hasonlít az visszárurendelési bizonylatra. A **visszáru-elismervény** jelentés nem naplózott vagy más módon a rendszerben regisztrált, és nem egy szükséges lépés a visszáru-rendelési folyamat.

## <a name="replace-a-product"></a>A termék cseréje
Helyettesítő termék kezelésének két módszere van:

-   **Előzetes csere** – cserélje ki a termék a vevő visszaküldött termék megérkezése előtt.
-   **Intézkedési kód váltja** – automatikusan helyettesítő új rendeléssor létrehozásához.

### <a name="up-front-replacement"></a>Előzetes csere

Előzetes csere a a helyettesítő cikk szállítható a vevőnek a cikk visszaérkezett előtt. Ez a módszer akkor hasznos, ha például az elem valamely gép részét, amely nem lehet eltávolítani, kivéve, ha a tartalék alkatrész rendelkezésére veszi át a helyét, vagy csak szeretné, hogy a helyettesítő termék, a lehető legrövidebb időn belül a vevő. Az előzetes csere sorrend a független értékesítési rendelést. A fejléc-információt az ügyfél inicializálva van, és a sor-információt a visszáru rendelésből inicializálva van. Szerkesztés, feldolgozni, és a csererendelés függetlenül a visszárurendelés törlése. Ha töröl egy cserecikkrendelést, kap egy üzenetet, hogy a rendelés helyettesítő rendelés létrehozása. A következő ábrán az előzetes csere folyamata.  

[![Előzetes csere folyamata](https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn04.png)](https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn04.png)  

A visszárurendelés tartalmaz egy hivatkozást a csererendelés. Ha a hibás cikkek visszaküldése előtt előzetes csere rendelés visszáru rendelés készül, nem intézkedéskódok cserére választhat után a hibás cikket ő visszaküldené.

### <a name="replacement-by-disposition-code"></a>Intézkedéskód helyettesítése

Ha az ügyfélnek szállított egy cserecikket, és használja a **csere és selejtezés** vagy **csere és jóváírás** a visszárurendelés intézkedési művelet használata a folyamat, amely az alábbi ábrán látható.  

[![Helyettesítő folyamatot egy intézkedéskódot használatakor](https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn05.png)](https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn05.png)  

A helyettesítő elem segítségével független eladási rendelés, eladási cserecikkrendelést érkeznek meg. Ez az értékesítési rendelés szállítólevél a visszáru rendelés létrehozásakor jön létre. A rendelés fejlécében a visszáru rendelés fejen a hivatkozott vevőtől származó adatokat használja. A sor adatgyűjtés megadott adatok alapján a **helyettesítő cikk** oldalon. A **helyettesítő cikk** lapot ki kell tölteni intézkedési műveleteket a word "csere." kezdetű sorok Azonban a mennyiség és a helyettesítő cikk azonosításával járó nem érvényesített vagy korlátozott. Ez a viselkedés lehetővé teszi, hogy olyan esetekben, ahol a vevő szeretné ugyanazt a cikket, de egy másik konfigurációt vagy méretét, valamint esetekben azt szeretné, ahol a vevők egy teljesen másik elemet. Alapértelmezés szerint egy azonos elemet meg a **helyettesítő cikk** oldalon. Választhatja azonban egy másik elemet, feltéve, hogy a funkció be van állítva. **Megjegyzés:** szerkesztheti és törölheti a cserecikk-eladási rendelést létrehozását követően.

## <a name="generate-a-packing-slip"></a>A csomagjegyzék készítése
Visszaküldött cikkek bevételezése készletre, frissítenie kell a csomagjegyzéket a rendeléshez tartozó cikkek. A számla frissítése folyamatban a frissítés a pénzügyi tranzakció, mint a csomagjegyzék frissítése folyamatban a készletrekord tényleges frissítése. Más szóval ez a folyamat véglegesíti a készlet módosításait. Esetében adja vissza, a lépések az intézkedési művelet rendelt hajtják végre, a csomagolás során frissítésével. A csomagjegyzék létrehozásakor a következők történnek:

-   A raktárban a tényleges bevételezés végrehajtásához a szokásos eljárást kell alkalmazni. Főkönyvi feladások jönnek létre, ha a készletkönyvelési csoport minta (**tényleges készlet feladása**) és a Kinnlevőségek paraméterei (**Szállítólevél főkönyvi feladása**) megfelelően vannak beállítva.
-   A "hulladék" szót tartalmazó intézkedési művelet megjelölt selejtnek, és a készletveszteség a főkönyvbe.
-   A jelölt elemek a **vissza a vevőnek** besorolási műveletet kapott, és az ügyfél. Ezek az elemek nem befolyásolják a készletben.
-   Jön létre egy cserecikk-eladási rendelést. Ez az értékesítési rendelés adatain alapul a a **helyettesítő cikk** oldalon.

Csak azokat a sorokat, amelyek állapota visszáru szállítólevél hozhat létre **bejegyzett**, és csak a visszáru rendelés sornak a teljes mennyiségét. Ha több sort a visszáru rendelés a **bejegyzett** állapotát, a szállítólevél sorok részhalmazát elő a többi sor törlése a **szállítólevél könyvelése** oldalon. Részleges bevallások visszáru-rendelési sorok visszáru rendelés szállítmányok tekintetében nem megfelelő kifejezésekkel vannak definiálva. Ezért ezt az egy rendelésen szereplő teljes mennyiséget kap, de a többi sort a visszáru rendelést kap semmi, ha a szállítás nem részleges szállítás. Azonban ha a visszáru-rendelési sor van szükség, hogy 10 egység az elem vissza, de csak négy egység kap, a szállítási részleges szállítás nem. Ha nem várható visszáru elemeinek érkeztek, félretéve a szállítólevelet, és várja meg a többi érkezzen a visszatérő mennyiség. Azt is megteheti regisztrálása és feladása a részleges mennyiséget. A szállítólevelek könyvelési folyamat részeként a csomagjegyzék hivatkozási száma a vevő szállítási dokumentumokból is társíthat a rendelési sorokban. Ez a társítás nem kötelező, és csak referenciaként szolgál. A tranzakciós frissítéseket nem hoz létre. Általában ki lehet hagyni a csomagolási folyamat elismervény, és folytassa a számlázás. Ebben az esetben a, ha szállítólevél-bizonylat létrehozása során végzett volna lépéseket számlázás során.

## <a name="generate-an-invoice"></a>Számla előállítása
Bár a **visszárurendelés** lapon található információk és tevékenységek, amelyek szükségesek ahhoz, hogy kezelni a különleges logisztikai szempontok a visszárurendelés kell használnia a **az eladási rendelés** oldalon a számlázási folyamat befejezéséhez. A szervezet majd számlázhatja visszáru rendelések vagy eladási rendelések egy időben, és ugyanaz a személy, szükség szerint a számlázási folyamat végrehajtásához. A visszáru rendelés megtekintéséhez a **az eladási rendelés** lap, kattintson a hivatkozásra kattintva nyissa meg a megfelelő eladási rendelést az értékesítési rendelés számát. A visszárurendelés is megtalálja a **minden értékesítési rendelések** lap. Visszáru rendelések, amelyek a rendelés típusát az értékesítési rendelések **vissza a rendelés**.

### <a name="credit-correction"></a>Jóváírás korrekciója

A számlázási folyamat részeként a vegyes költségek helyességének ellenőrzése. Ahhoz, hogy a főkönyvi feladások javításokat (sztornó) válik, fontolja meg a **jóváírás-korrekció** a beállítás a **más** lapján a **számla** oldal a számla/jóváírás könyvelésekor. **Megjegyzés:** alapértelmezés szerint a **hitel javítás** beállítás aktiválva van, ha a **Jóváírás helyesbítésként** a beállítás a **Kinnlevőségek paraméterei** lap engedélyezve van. Azonban azt javasoljuk, hogy Ön nem post visszaad sztornó.

## <a name="create-intercompany-return-orders"></a>Vállalatközi visszáru rendelések létrehozása
Visszárurendelések hajtható végre a szervezeten belül a két vállalat között. A következő esetekben használható:

-   Egy vállalatközi kapcsolatban részt vevő két vállalat közötti egyszerű vállalatközi beolvasása
-   Vállalatközi láncon keresztül, amely az eladó vállalat vevői visszáru rendelés létrehozásakor jön létre
-   Vállalatközi láncon keresztül, amely a vevő vállalat szállítói visszáru rendelés létrehozásakor jön létre
-   Közvetlen kiszállítás, szállítási egy külső vevő és egy vállalatközi kapcsolatban részt vevő két vállalat közötti adja vissza

### <a name="setup"></a>Beállítás

Az alábbi ábra a minimális telepítés, szükség a két részt egy vállalatközi kapcsolatot, és kihasználják a vállalatközi kereskedelmi vállalat.  

[![Minimum setup](https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn06.png)](https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn06.png)  

Az alábbi esetben CompBuy a vásárló vállalatnak, és CompSell az eladó vállalat. Általában az eladó vállalat hajók áru a vásárló vállalatnak vagy, közvetlen kiszállítás szállítólevél esetekben közvetlenül a végső vevő számára. A CompBuy, a Vállalatközi szállító\_CompSell a meghatározás szerint egy vállalatközi végponthoz társított a vállalat CompSell. Egy időben, a CompSell, a Vevő VK\_CompBuy a meghatározás szerint egy vállalatközi végponthoz társított a vállalat CompBuy. A megfelelő intézkedéseket a házirend részletei és értékmegfeleltetések mindkét vállalat meg kell határozni. Egy vállalatközi, egyben a vállalatközi értékesítési rendelés, visszáru rendelés közvetlen kiszállítás szállítás esetén az eladó vállalat létrejön. A vállalatközi visszáru rendelés RMA-szám RMA számsorozat CompSell kell kivételezni, vagy az RMA-szám CompBuy az eredeti visszárurendelés rendelt átmásolható. Az RMA szám beállításait a **PurchaseRequisition** CompBuy a műveleti irányelv határozza meg ezeket a műveleteket. Ha az RMA-szám szinkronizálása, meg kell terveznie szám ütközés kockázatának csökkentése, ha a két vállalat használja ugyanazt a számsorozatot.

### <a name="simple-intercompany-returns"></a>Egyszerű vállalatközi beolvasása

Ebben az esetben a két vállalat a szervezethez, az alábbi ábrán látható módon.  

[![Egyszerű vállalatközi visszáru](https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn07.png)](https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn07.png)  

A lánc a szállítói visszáru rendelést a vásárló vállalat létrehozásakor, illetve a Vevői visszáru rendelés létrejön az eladó vállalat hozható létre. 365 Dynamics műveletek hoz létre a megfelelő sorrendben a másik társaság, és meggyőződik arról, hogy a fej és sor-információt a szállítói visszáru rendelés tükrözi a beállításokat a vevő a visszáru rendelés. A létrehozott visszáru rendelést vagy kihagyhatjuk vagy beszámíthatjuk a hivatkozás (**található értékesítési rendelés**) egy meglévő vevő számlát. A csomagjegyzékek és számlák két rendelések dolgozhatók fel külön-külön. Például nem kell létrehozni a szállítói visszáru rendelés csomagjegyzékét a Vevői visszáru rendelés csomagjegyzékének elkészítése előtt.

### <a name="direct-delivery-shipment-returns-among-three-parties"></a>Közvetlen kiszállítás, szállítási adja vissza a három fél közötti

Ebben az esetben állapítható meg, ha egy korábbi értékesítése a **a közvetlen szállítást** típus van-e töltve, és ha számlával szemben a vevő szerepel a vállalat kommunikáló az ügyféllel. Az alábbi ábrán látható a vállalat CompBuy már korábban Eladva és Számlázva, a vevő Extern termékek. A termékek a vállalat CompSell közvetlenül a leszállították a vevőnek egy vállalatközi láncon keresztül.  

[![Közvetlen kiszállítás, szállítási adja vissza a három fél közötti](https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn08.png)](https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn08.png)  

Ha a vevő Extern vissza a termékek, a visszáru rendelést (RMA02) a vevő a vállalat CompBuy jön létre. A vállalatközi lánc létrehozására a visszáru rendelés közvetlen kiszállításra kell megjelölni. Használata esetén a **található értékesítési rendelés** a vevői számla visszaállításához válasszon függvény létrejön egy vállalatközi lánc, amely a következő dokumentumokat:

-   **Eredeti visszárurendelés:** RMA02 (CompBuy cég)
-   **Beszerzési rendelés:** PO02 (CompBuy cég)
-   **Vállalatközi visszáru rendelés:** RMA\_00032 (CompSell cég)

Vállalatközi közvetlen szállítási láncban létrehozása után az összes fizikai kezelés és a visszáruk feldolgozása kell előfordulnia összefüggésben a vállalatközi visszáru rendelés RMA\_00032 a vállalat CompSell. A termékek nem fogadható el a vállalat CompBuy. A vállalatközi visszáru rendelés hozzá van rendelve egy intézkedéskódot, ha azt az eredeti visszáru rendelés az eredeti rendelés megfelelő számlázás lehetővé szinkronizálva.

## <a name="post-to-the-ledger"></a>A főkönyvi könyvelés
A visszáru rendelés számlázásakor létrehozott főkönyvi feladások néhány fontos beállítások és paraméterek befolyásolják:

-   **Visszáru-önköltségi ár** – a készlet eltérő modellek **általános költség**, a **visszáru-önköltségi ár** paraméter határozza meg a cikk költségét vissza a készletbe elfogadott vagy hulladék. Kiszámításához a megfelelő Készletértékelés, fontos beállítani a **visszáru-önköltségi ár** paraméter megfelelően. Ha a **található értékesítési rendelés** függvény egy hivatkozást a vevői számla, visszáru-rendelési sor létrehozása a **visszáru-önköltségi ár** értéke egyenlő az önköltségi ár a cikk eladása. Egyébként önköltségi ár értékét a cikk beállítása származik, vagy manuálisan is megadhatók.
-   **Javítási/sztornírozott jóváírás** – a **korrekciós követel** paraméter a **számla** lap határozza meg, hogy a feladások legyen rögzített (Tartozás/Követelés) pozitív tételeket, vagy javítása, a negatív tételeket.

Az alábbi példákban a visszáru-önköltségi ára ábrázolva **számlaengedmény önköltségi ár**.

### <a name="example-1-the-return-order-doesnt-reference-a-customer-invoice"></a>1. példa: A visszárurendelés nem hivatkozhat a vevői számla

A visszárurendelés nem hivatkozhat a vevői számla. A visszárucikk kell jóváírni. A **hitel javítás** paraméter nincs bejelölve, ha a visszáru rendelés, számla vagy jóváírás esetén jön létre.  

[![Visszárurendelés nem hivatkozik a vevő invoic](https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn09.png)](https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn09.png)  

**Megjegyzés:** a Cikkár fő része lesz az alapértelmezett érték a **visszáru-önköltségi ár** paraméter. Az alapértelmezett ár készletkiadás alkalmával az önköltségi ár eltér. A tényezők ezért 3 veszteség keletkezett. Ezenkívül a visszáru rendelést az eladási rendelésen a vevőnek adott engedmény nem tartalmaz. Ezért a túlzott követel következik be.

### <a name="example-2-credit-correction-is-selected-for-the-return-order"></a>2. példa: A jóváírás-korrekció kijelöltük a visszárurendelés

2. példa megegyezik 1,. példa, de a **hitel javítás** paraméter meg van jelölve, ha a visszáru-rendelési számla jön létre.  

[![Visszáru rendelés, ahol van kiválasztva a jóváírás-korrekció](https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn10.png)](https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn10.png)  

**Megjegyzés:** negatív helyesbítés főkönyvi feladások kerülnek.

### <a name="example-3-the-return-order-line-is-created-by-using-the-find-sales-order-function"></a>3. példa: A visszáru-rendelési sor létrejön az eladási rendelés keresés funkció használatával

Ebben a példában a visszáru-rendelési sor létrejön, segítségével a **található értékesítési rendelés** függvény. A **hitel javítás** paraméter nincs bejelölve, a számla létrehozásakor.  

[![Visszáru rendelési sorában létrehozott eladási rendelés keresés használatával](https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn11.png)](https://msdynamics.blob.core.windows.net/media/2017/02/SalesReturn11.png)  

**Megjegyzés:****engedmény** és **visszáru-önköltségi ár** helyesen van beállítva. Ezért a vevői számla pontos sztornírozásai következik be.


