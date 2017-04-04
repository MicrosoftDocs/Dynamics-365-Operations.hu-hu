---
title: "Képletszerkesztő elektronikus jelentésekhez"
description: "Ez a témakör ismerteti a képletszerkesztő használatát az Elektronikus jelentésben (ER). Ha egy formátumot az ER-ben meghatározott elektronikus dokumentumra vonatkozóan tervez meg, akkor használhatja a Microsoft Excelt– úgy mint az adat átalakítás képleteire vonatkozó formulákat a dokumentum teljesítésére és formázására vonatkozó követelményekhez történő megfeleltetés érdekében. Különféle funkciók támogatottak - dátum és idő, logikai, matematikai információt adattípus konvertálása és egyéb (üzleti domain-specifikus függvények)."
author: kfend
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 388b6398488e6f316c1ec07a00182e81c1dc8d08
ms.openlocfilehash: ac8d6c064ca826cc1c2fed07578ca9ce0c66ef66
ms.lasthandoff: 03/31/2017


---

# <a name="formula-designer-in-electronic-reporting"></a>Képletszerkesztő elektronikus jelentésekhez

Ez a témakör ismerteti a képletszerkesztő használatát az Elektronikus jelentésben (ER). Ha egy formátumot az ER-ben meghatározott elektronikus dokumentumra vonatkozóan tervez meg, akkor használhatja a Microsoft Excelt– úgy mint az adat átalakítás képleteire vonatkozó formulákat a dokumentum teljesítésére és formázására vonatkozó követelményekhez történő megfeleltetés érdekében. Különféle funkciók támogatottak - dátum és idő, logikai, matematikai információt adattípus konvertálása és egyéb (üzleti domain-specifikus függvények).

<a name="formula-designer-overview"></a>Képletszerkesztő áttekintése
-------------------------

Az elektronikus jelentés (ER) támogatja a képletszerkesztőt. Ezért tervezéskor konfigurálhatja futtatás közben a következő feladatokhoz használható kifejezéseket:

-   A Microsoft Dynamics 365 for Operations adatbázisból érkeznek az átalakítási adatok és áttöltésre kerülnek az ER formátumokra vonatkozó adatforrásnak tervezett ER adatmodellbe (szűrés, csoportosítás, adattípus-átalakítás stb.)
-   Olyan adatok formázása, amelyeket ki kell küldeni egy elektronikusan létrejövő dokumentumba az adott ER formátum elrendezésével és állapotával összhangban (a kért nyelvnek vagy kultúrának, kódolásnak stb. megfelelően).
-   Az elektronikus dokumentumkészítés folyamatának irányítása (bizonyos formátumelemek kivitelének engedélyezése/tiltása a feldolgozóadattól függően, a dokumentumlétrehozás megszakítása, üzenetek küldése a végfelhasználóknak stb.)

Emiatt a képlettervező lapot a következő módok valamelyikén lehet megnyitni:

-   Az adatmodellek komponenseihez tartozó adatforrás cikkek kötése.
-   A formátum komponenseihez tartozó adatforráscikkek kötése.
-   Az adatforrások részeként számított mezők karbantartásának elvégzése.
-   Felhasználó által megadott paraméterek láthatósági feltételeinek meghatározása.
-   A formátum átalakításainak tervezése.
-   A formátum összetevőkre vonatkozó engedélyező feltételek meghatározása.
-   A formátum fájl összetevőkre vonatkozó fájlneveinek definíciója.
-   A vezérlő-ellenőrzések feldolgozására vonatkozó feltételek meghatározása.
-   A vezérlő-ellenőrzések feldolgozására vonatkozó üzenetszöveg meghatározása.

## <a name="designing-er-formulas"></a>ER-képletek tervezése
### <a name="data-binding"></a>Adatok kötése

Az ER Képletszerkesztő segítségével meghatározhatja azokat a kifejezéseket, amelyek átalakítják az adatforrásból származó adatokat, úgy hogy az adatokat az adattárolóban futtatási időben ki lehet tölteni:

-   A Microsoft Dynamics 365 for Operations adatforrásokból és futtatási paraméterekből egy ER adatmodellbe.
-   Az ER adatmodell ER formátumba.
-   A Microsoft Dynamics 365 for Operations adatforrásokból és futtatási paraméterekből egy ER formátumba.

Az alábbi ábra bemutatja az ilyen típusú kifejezés tervezését. Ebben a példában a kifejezés megjeleníti a Dynamics 365 for Operations **Intrastat** tábla **Intrastat.AmountMST** mezőjének értékét, miután ez az érték két tizedesjegy pontossággal kerekítve lett. [![kép kifejezés kötelező érvényű](./media/picture-expression-binding.jpg)](./media/picture-expression-binding.jpg) az alábbi ábra szemlélteti, hogyan lehet használni az ilyen típusú kifejezés. Ebben a példában a tervezett kifejezés eredménye nem üres a **Transaction.InvoicedAmount** -összetevője a **adó adatszolgáltatási modell** modellt. [![kép-kifejezés-binding2](./media/picture-expression-binding2.jpg)](./media/picture-expression-binding2.jpg) futás közben a tervezett képlet **kerek (Intrastat.AmountMST 2)**, értékét kerekíti a **AmountMST** mező minden egyes rekord, a **Intrastat** tábla két tizedes pontossággal, és feltölti a kerekített értéket a **Transaction.InvoicedAmount** összetevője a **adóbevallás** adatmodell.

### <a name="data-formatting"></a>Adatformázás

Az ER Képletszerkesztő segítségével meghatározhatja azokat a formátumokat, amelyek átalakítják az adatforrásból származó adatokat, úgy hogy adatokat küldhet egy elektronikusan létrejövő dokumentum részeként. Ha formázást kell alkalmazni általános szabályként, egy formátumra vonatkozóan újra fel kell használni, bemutatja, hogy a formázás egyszerre szerepel a formátum konfigurációban, amely egy formázási kifejezés nevű átalakításként jelenik meg. Ez az elnevezett átalakítás hozzákapcsolható számos formátum-összetevőhöz, amelynek kimenetét formázni kell a létrehozott kifejezésnek megfelelően. Az alábbi ábra bemutatja az ilyen típusú átalakítás tervezését. Ebben a példában a **TrimmedString** átalakítása a **karakterlánc** adattípus bejövő adatait veszi és csonkolja a kezdő és záró szóközöket, amikor karakterlánc-értéket ad vissza. [![kép-átalakítás-Tervező](./media/picture-transformation-design.jpg)](./media/picture-transformation-design.jpg) az alábbi ábra szemlélteti, hogyan lehet használni az ilyen típusú átalakítás. Ebben a példában több olyan szöveg komponens vonatkozik a név szerinti **TrimmedString** átalakításra, amely kimentként küldi el a szöveget az elektronikusan létrejövő dokumentum számára a futtatási időben. [![Kép átalakítása-használati](./media/picture-transformation-usage.jpg)](./media/picture-transformation-usage.jpg) amikor komponens formázása hivatkozik a ** TrimmedString ** átalakítása (például a **partyName** az előző ábrán az alkatrész) Ez küld szöveges kimenetként létrehozása a dokumentum. A szöveg nem tartalmazza a kezdő és záró szóközöket. Ha olyan formázással rendelkezik, amelyet egyénileg kell alkalmazni, akkor a formázás a megadott formátum-összetevő kötésének egyéni kifejezéseként jelenítheti meg. Az alábbi ábra bemutatja az ilyen típusú kifejezését. Ebben a példában a **partyType** formátum összetevő az adatforráshoz kötött azon kifejezésen keresztül, amely átalakítja a **Model.Company.RegistrationType** mezőjéből származó bejövő adatokat az adatforrásban a nagybetűs szöveghez és az elektronikus dokumentum számára kimeneti szövegként küldi el. [![kép-kötés-a-képlet](./media/picture-binding-with-formula.jpg)](./media/picture-binding-with-formula.jpg)

### <a name="process-flow-control"></a>Folyamatáramlat irányítás

A ER képlettervező segítségével meg lehet határozni azokat a kifejezéseket, amelyek irányítják a dokumentumok létrehozásának folyamatábráját. A lehetőségek:

-   Határozza meg azokat a kifejezéseket, amelyek meghatározzák, hogy mikor kell egy dokumentumkészítési folyamatot megszakítani.
-   Határozza meg azokat a kifejezéseket, amelyek üzeneteket hoznak létre a végfelhasználónak a megállított folyamatról vagy végrehajtásnapló-üzeneteket adnak ki a jelentéskészítés zajló folyamatáról.
-   Adja meg a generálási dokumentumok fájlneveit és létrehozás szabályozó feltételeit.

A folyamatáramlat irányítás minden szabálya egyéni ellenőrzésként van tervezve. Az alábbi ábra bemutatja az ilyen típusú ellenőrzést. Íme a konfiguráció magyarázata ebben a példában:

-   Az ellenőrzés akkor megy végbe, amikor a **INSTAT** csomópont létrejön az XML-fájl létrehozásában.
-   Ha a tranzakció listája üres, az ellenőrzés megállítja a végrehajtási folyamatot és **HAMIS** értéket küld vissza.
-   Az ellenőrzés egy hibaüzenetet küld vissza, amely tartalmazza a felhasználó által előnyben részesített nyelven a SYS70894 címke szövegét.

[![kép-ellenőrzés](./media/picture-validation.jpg)](./media/picture-validation.jpg) az ER Képletszerkesztő is használható létrehozása elektronikus dokumentum fájlnevét meghatározására és ellenőrzésére a fájl létrehozásának folyamatát. Az alábbi ábra bemutatja az ilyen típus folyamatáramlat-irányítás tervezését. Íme a konfiguráció magyarázata ebben a példában:

-   A rekordok listája a **model. Intrastat** adatforrásból olyan kötegekre osztódik fel, amelyek legfeljebb 1000 rekordot tartalmaznak
-   A kimenet létrehoz egy irányítószámot, amely tartalmaz egy fájlt minden létrehozott kötegre vonatkozóan egy XML-formátumú fájlban.
-   Egy kifejezés a létrejövő elektronikus dokumentumokra vonatkozó fájlnevet ad vissza a fájlnév és a fájlkiterjesztés összefűzésével. A második kötegre és minden további kötegre vonatkozóan a fájl neve tartalmazza a Kötegazonosítót utótagként.
-   Egy kifejezés lehetővé tesz ( **IGAZ**visszaküldése esetén)a fájl létrehozását azon kötegekre vonatkozóan, amelyek legalább egy rekordot tartalmaznak.

[![Képvezérlő-fájl](./media/picture-file-control.jpg)](./media/picture-file-control.jpg)

### <a name="basic-syntax"></a>Alap szintaxis

ER kifejezések bármennyi vagy az összes elemet tartalmazhatja a következő elemek közül:

-   Állandók
-   Operátorok
-   Hivatkozások
-   Útvonalak
-   Függvények

#### <a name="constants"></a>Állandók

A szöveges és a numerikus állandók (nem számított értékek) segítségével, amikor a kifejezéseket tervezi. Ha például a kifejezés ** érték ("100") + 20 ** használja a numerikus állandó 20 és állandó "100" karakterláncot, és a numerikus értéket ad vissza, **120**. Az ER képletszerkesztő támogatja a feloldó szakaszokat, így meghatározhatja a kifejezés karakterláncának azon részét, amelyet eltérően kell kezelni. Például a **„Lev Tolstoy” „Háború és béke „1. kötet”** kifejezés megjeleníti a **„Lev Tolstoy” „Háború és béke „1. kötet”** szöveges karakterláncot.

#### <a name="operators"></a>Operátorok

Az alábbi táblázat bemutatja az aritmetikai operátorokat, amelyek segítségével elvégezheti a matematikai alapműveleteket, mint például összeadás, kivonás, osztás és szorzás.

| Kezelő | Jelentés              | Példa |
|----------|----------------------|---------|
| +        | Hozzáadás             | 1+2     |
| -        | Kivonandó tagadás | 5-2 -1  |
| \*       | szorzás       | 7\*8    |
| /        | Osztály             | 9/3     |

Az alábbi táblázat bemutatja az összehasonlító operátorokat, amelyek támogatva vannak, és amelyek segítségével összehasonlíthat két értéket.

| Kezelő | Jelentés                  | Példa    |
|----------|--------------------------|------------|
| =        | Egyenlő                    | X=Y        |
| &gt;     | Nagyobb, mint             | X&gt;Y     |
| &lt;     | Kisebb, mint                | X&lt;Y     |
| &gt;=    | Nagyobb vagy egyenlő | X&gt;=Y    |
| &lt;=    | Kisebb vagy egyenlő    | X&lt;=Y    |
| &lt;&gt; | Nem egyenlő             | X&lt;&gt;Y |

Ezenkívül használhat (&) jelet egy szöveg összefűző operátoraként, hogy egy vagy több szövegláncot összekapcsoljon vagy összefűzzön a szöveg egy részével.

| Kezelő | Jelentés     | Példa                                        |
|----------|-------------|------------------------------------------------|
| &        | Összefűzés | Nincs nyomtatni-való” és „ ” és „nem található rekord” |

#### <a name="operator-precedence"></a>Operátor elsőbbségi sorrend

Fontos a sorrend, amelyben az összetett kifejezés egy része kiértékelésre került. Például az eredménye a kifejezés ** 1 + 4 / 2 **, attól függően változik, hogy az összeadási művelet vagy a körzet műveletet végzi el először. A zárójelek segítségével megadhatja egy kifejezés kiértékelésének módját. Például, ha jelezni szeretné, hogy először a kiegészítő műveletet kell végrehajtani, módosíthatja az előző kifejezés **(1 + 4) / 2** lehetőségre. Ha a kifejezésben elvégzendő műveletek sorrendje nincs megadva explicit módon, akkor a támogatott operátorokhoz rendelt alapértelmezett elsőbbségi sorrenden alapul. A következő táblázatok az egymáshoz rendelt műveleteket és az elsőbbségi sorrendet jeleníti meg. A magasabb elsőbbségi sorrenddel (például 7) rendelkező operátorok az alacsonyabb elsőbbségi sorrenddel rendelkező operátorok előtt (például 1) kerülnek kiértékelésre.

| Elsőbbségi sorrend | Operátorok      | Szintaxis                                                   |
|------------|----------------|----------------------------------------------------------|
| 7          | Csoportosítás       | ( … )                                                    |
| 6          | Tag hozzáférés  | … gombra. …                                                    |
| 5          | Függvényhívás  | … ( … )                                                  |
| 4          | Szorzás | … \* … … / …                                             |
| 3          | Additív       | … + … … - …                                              |
| 2          | Összehasonlítás     | … &lt; … … &lt;= … … =&gt; … … &gt; … … = … … &lt;&gt; … |
| 1          | Kiválasztás     | … , …                                                    |

Ugyanabban a sorban azonos elsőbbségi sorrenddel rendelkeznek az operátorok. Ha a kifejezés ezen operátorok közül egynél többet tartalmaz, akkor a kifejezést balról jobbra értékelte ki a program. Ha például a kifejezés **1 + 6 / 2 \*3 &gt;5** adja vissza **igaz**. Ajánlatos a zárójelek használata a kifejezések kívánt sorrendjének explicit módon történő jelzéséhez, illetve a kifejezések könnyebb olvasása és kezelése érdekében.

#### <a name="references"></a>Hivatkozások

Egy kifejezés tervezése során elérhető jelenlegi ER komponens összes adatforrását (modell vagy egy formátum) elnevezett hivatkozásként lehet használni. Például az aktuális ER adatmodell tartalmazza a **ReportingDate** adatforrást, amely megjeleníti a **DATETIME** adattípus értékét. Ez az érték az áramfejlesztő dokumentum megfelelően formázásához hivatkozhatunk az adatforrás a kifejezésben az alábbiak szerint: **DATETIMEFORMAT (ReportingDate, "nn-hh-éééé")** az ábécé egy betűjét jelképező nem hivatkozási adatforrás nevét az összes karakter aposztrófot (') kell megelőznie. Ha hivatkozási adatforrás neve tartalmaz legalább egy szimbólum nem képviselő az ábécé (például írásjeleket vagy egyéb írásos szimbólumok) levél, neve szimpla idézőjelek közé kell tenni. Íme néhány példa:

-   A **Mai dátum és idő** adatforrást a következőképpen kell hivatkozni egy ER kifejezésben: **Mai dátum és idő”**
-   A **Vevők** adatforrás **Név()** metódusát a következőképp kell hivatkozni az ER kifejezésben: **Vevők.„név()”**

#### <a name="path"></a>Elérési út

Amikor a kifejezés egy adatforrásra hivatkozik, az útvonal meghatározása segítségével kiválaszthatja az adatforrás egy megadott egyszerű elemének kiválasztásához. A pont karaktert (.) a strukturált adatforrás egyes elemeinek elkülönítésére használják. Például az aktuális ER adatmodell tartalmazza a **InvoiceTransactions** adatforrást, amely a rekordok listáját jeleníti meg. Az** InvoiceTransactions** rekordok szerkezete tartalmazhat **AmountDebit** és **AmountCredit** mezőket, amelyek numerikus értékeket jelenítenek meg. Ezért a számlázott összeg kiszámítása érdekében a következő kifejezést tervezheti meg: **InvoiceTransactions.AmountDebit - InvoiceTransactions.AmountCredit**

#### <a name="functions"></a>Függvények

A következő témakör az ER kifejezésekben használható funkciókat mutatja be. A kifejezés környezet (aktuális ER adatmodell vagy ER formátum) minden adatforrása és az állandók is használhatóak függvénymeghívási paraméterként a függvénymeghívási argumentumok listájával összhangban. Például az aktuális ER adatmodell tartalmazza a **InvoiceTransactions** adatforrást, amely a rekordok listáját jeleníti meg. Az** InvoiceTransactions** rekordok szerkezete tartalmazhat **AmountDebit** és **AmountCredit** mezőket, amelyek numerikus értékeket jelenítenek meg. Ezért a számlázott összeg kiszámításához, megtervezheti azokat a következő kifejezéseket, amelyek az ER kerekítési funkciót használják: **ROUND (InvoiceTransactions.AmountDebit - InvoiceTransactions.AmountCredit, 2)**

## <a name="supported-functions"></a>Támogatott függvények
Az alábbi táblázatok bemutatják azokat az adatkezelő függvényeket, amelyeket az ER adat modellek és ER jelentések tervezéséhez használhat. A függvények listája nem rögzített, és a fejlesztők által bővíthető. A használható funkciók listájának megtekintéséhez nyissa meg a funkciók ablakot az ER képletszerkesztőben.

### <a name="date-and-time-functions"></a>Dátum és idő függvények

| Funkció                                   | Leírás                                                                                                                                                                                                                                                                                                                                                      | Példa                                                                                                                                                                                                                                                                                               |
|--------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| NAPOKHOZZÁADÁSA (dátum és idő, napok)                   | Adja hozzá a napok meghatározott számát a meghatározott dátum és idő értékhez.                                                                                                                                                                                                                                                                                                | **(MOST() 7) NAPOKHOZZÁADÁSA** megjeleníti a dátum és idő hét napot a jövőben.                                                                                                                                                                                                                            |
| DATETODATETIME (dátum)                      | A megadott dátumérték átalakítása egy dátum-idő értékre.                                                                                                                                                                                                                                                                                                            | **DATETODATETIME (CompInfo. "getCurrentDate()')** számítja ki a jelenlegi Dynamics 365 műveletek munkamenet dátuma, a 12/24/2015, **12/24/2015 12:00:00 AM**. Ebben a példában **CompInfo** a **Dynamics 365 for Operations/Tábla** típus ER-adatforrása, amely a CompanyInfo táblára hivatkozik. |
| MOST ()                                     | A jelenlegi Dynamics 365 for Operations alkalmazáskiszolgáló dátumát és időpontját dátum-idő értékként jeleníti meg.                                                                                                                                                                                                                                                             |                                                                                                                                                                                                                                                                                                       |
| Ma ()                                   | A jelenlegi Dynamics 365 for Operations alkalmazáskiszolgáló dátumát dátumértékként jeleníti meg.                                                                                                                                                                                                                                                                          |                                                                                                                                                                                                                                                                                                       |
| NULLDATE ()                                | **Nulla** dátumértéket jelenik meg.                                                                                                                                                                                                                                                                                                                                    |                                                                                                                                                                                                                                                                                                       |
| NULLDATETIME ()                            | **Nulla** dátum-idő érték jelenik meg.                                                                                                                                                                                                                                                                                                                                |                                                                                                                                                                                                                                                                                                       |
| DATETIMEFORMAT (dátum és idő, a formátum)          | A megadott dátum-idő értéket a megadott formátumban karakterlánccá alakítja. (A támogatott formátumokkal kapcsolatos további tudnivalókat lásd: [szokásos](https://msdn.microsoft.com/en-us/library/az4se3k1(v=vs.110).aspx) és [egyéni](https://msdn.microsoft.com/en-us/library/8kb3ddd4(v=vs.110).aspx).)                                                                        | A **DATETIMEFORMAT (NOW(), "nn-hh-éééé")** a jelenlegi Dynamics 365 for Operations alkalmazáskiszolgáló dátumát (12/24/2015) a megadott egyéni formátum szerint **"24-12-2015"** jeleníti meg.                                                                                                          |
| DATETIMEFORMAT (dátum és idő, formátum, kultúra) | A megadott dátum-idő értéket a megadott formátumban szereplő karakterlánccá és [kultúra](https://msdn.microsoft.com/en-us/goglobal/bb896001.aspx) lehetőséggé alakítja. (A támogatott formátumokkal kapcsolatos további tudnivalókat lásd: [szokásos](https://msdn.microsoft.com/en-us/library/az4se3k1(v=vs.110).aspx) és [egyéni](https://msdn.microsoft.com/en-us/library/8kb3ddd4(v=vs.110).aspx)). | A **DATETIMEFORMAT (NOW(), "d", "de")** a jelenlegi Dynamics 365 for Operations alkalmazáskiszolgáló dátumát (12/24/2015) a kiválasztott német területi beállítások szerint (**"24.12.2015"**) jeleníti meg.                                                                                                             |
| SESSIONTODAY ()                            | Az aktuális Dynamics 365 for Operations munkamenet dátumát dátumértékként jeleníti meg.                                                                                                                                                                                                                                                                                      |                                                                                                                                                                                                                                                                                                       |
| SESSIONNOW ()                              | Az aktuális Dynamics 365 for Operations munkamenet dátumát és időpontját dátumértékként jeleníti meg.                                                                                                                                                                                                                                                                         |                                                                                                                                                                                                                                                                                                       |
| DATEFORMAT (dátum, formátum)                  | Karakterlánc formájában adja vissza a dátumot a megadott formátum használatával.                                                                                                                                                                                                                                                                                                    | A **DATEFORMAT (SESSIONTODAY (), "dd-MM-yyyy")** az aktuális Dynamics 365 for Operations munkamenet dátumát (12/24/2015) a megadott egyéni formátum szerint (**24-12-2015**) jeleníti meg.                                                                                                                      |
| DATEFORMAT (dátum, formátum, területi beállítások)         | Alakítsa a megadott dátumértéket a megadott formátumban és [területi beállításoknak](https://msdn.microsoft.com/en-us/goglobal/bb896001.aspx) megfelelő karakterlánccá. (A támogatott formátumokkal kapcsolatos további tudnivalókat lásd: [szokásos](https://msdn.microsoft.com/en-us/library/az4se3k1(v=vs.110).aspx) és [egyéni](https://msdn.microsoft.com/en-us/library/8kb3ddd4(v=vs.110).aspx)).     | A **DATETIMEFORMAT (SESSIONNOW (), "d", "de")** az aktuális Dynamics 365 for Operations munkamenet dátumát (12/24/2015) a kiválasztott német területi beállítások szerint (**"24.12.2015"**) jeleníti meg.                                                                                                                       |

### <a name="list-functions"></a>Lista függvények

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Funkció</th>
<th>Leírás</th>
<th>Példa</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>MEGOSZTÁS (bejövő, hossza)</td>
<td>A megadott bemeneti karakterlánc felosztása a részkarakterláncokban, amelyek mindegyike megadott időtartammal rendelkezik. Új listaként jeleníti meg az eredményt.</td>
<td><strong>Felosztás (&quot;abcd&quot;, 3)</strong> áll, amelyek két bejegyzés új listáját adja vissza a <strong>karakterlánc</strong> mezőben. Az első bejegyzés mezőben a szöveg <strong>&quot;abc&quot;</strong>, míg a második bejegyzés a mező a szöveg <strong>&quot;d&quot;</strong>.</td>
</tr>
<tr class="even">
<td>FELOSZTÁSLISTA (lista, szám)</td>
<td>A megadott listát kötegekké osztja fel, amelynek mindegyike megadott számú rekordot tartalmaz. A kötegek új listájaként jeleníti meg az eredményt, amely a következő elemeket tartalmazza:
<ul>
<li>Kötegek, mint normál listák (<strong>Érték </strong>összetevő)</li>
<li>Az aktuális köteg száma (<strong>BatchNumber </strong>összetevő)</li>
</ul></td>
<td>Az alábbi példában a <strong>Sorok</strong> adatforrás három rekord rekordlistájaként jön létre, amely kötegekre oszlik, és mindegyike legalább két rekordot tartalmaz. <a href="./media/picture-splitlist-datasource.jpg"><img src="./media/picture-splitlist-datasource.jpg" alt="Data source that is divided into batches" class="alignnone wp-image-290681 size-full" width="397" height="136" /></a>Ez jelzi a tervezett formátum elrendezését, ahol kötéseket a <strong>vonalak</strong> adatforrás lehet létrehozni a kimeneti XML-formátum, amely azt közli minden egyes tétel és a rekordok egyes csomópontok jönnek létre. <a href="./media/picture-splitlist-format.jpg"><img src="./media/picture-splitlist-format.jpg" alt="Format layout that has bindings to a data source" class="alignnone wp-image-290691 size-full" width="374" height="161" /></a>A tervezett formátum futtatásának az eredménye a következő: <a href="./media/picture-splitlist-result.jpg"><img src="./media/picture-splitlist-result.jpg" alt="Result of running the format" class="alignnone wp-image-290701 size-full" width="358" height="191" /></a></td>
</tr>
<tr class="odd">
<td>LISTA (rekord 1 [, 2. rekord...])</td>
<td>A megadott argumentumokból létrehozott új listát jelenítik meg.</td>
<td><strong>LISTA (modell. MainData, modell. OtherData)</strong> egy üres sort jelenít meg, ahol a mezők listája a <strong>MainData</strong> és <strong>OtherData</strong> rekord lista összes mezőjét tartalmazza.</td>
</tr>
<tr class="even">
<td>LISTJOIN (1 lista, 2 lista, ...)</td>
<td>A megadott argumentumok listájából létrehozott csatolt listát jelenítik meg.</td>
<td><strong>LISTJOIN (felosztása (&quot;abc&quot;, 1), osztott (&quot;def&quot;, 1))</strong> hat rekordok listáját adja vissza, ha az egyik területe a <strong>karakterlánc</strong> adattípust tartalmaz egyetlen betűt.</td>
</tr>
<tr class="odd">
<td>ISEMPTY (lista)</td>
<td><strong>IGAZ</strong> választ jelenít meg, ha a megadott lista nem tartalmaz elemeket. Ellenkező esetben <strong>HAMIS</strong> választ jelenít meg.</td>
<td></td>
</tr>
<tr class="even">
<td>EMPTYLIST (lista)</td>
<td>A megadott lista segítségével egy üres listát jelenít meg a lista szerkezetére vonatkozó forrásként.</td>
<td><strong>EMPTYLIST (felosztása (&quot;abc&quot;, 1))</strong> ad vissza egy új üres lista, amely a listát ad vissza, mint az ugyanolyan szerkezetű <strong>SPLIT</strong> függvény.</td>
</tr>
<tr class="odd">
<td>ELSŐ (lista)</td>
<td>A megadott lista első rekordját akkor jeleníti meg, ha a rekord nem üres. Ellenkező esetben egy kivételt jelenít meg.</td>
<td></td>
</tr>
<tr class="even">
<td>FIRSTORNULL (lista)</td>
<td>A megadott lista első rekordját akkor jeleníti meg, ha a rekord nem üres. Ellenkező esetben egy <strong>null</strong> rekordot jelenít meg.</td>
<td></td>
</tr>
<tr class="odd">
<td>LISTOFFIRSTITEM (lista)</td>
<td>Olyan listát jelenít meg, amely csak a megadott lista első elemét tartalmazza.</td>
<td></td>
</tr>
<tr class="even">
<td>ALLITEMS (útvonal)</td>
<td>Új, összevont listát jelenít meg, amely a meghatározott elérési útnak megfelelő összes elemet tartalmazza. Az elérési utat egy érvényes adatforrás útvonalaként kell megadni a rekordlista adattípus adatforrásához. A karakterlánc, a dátum stb. adatelemek elérési útvonalának hibaüzenetet kell megjeleníteniük az ER kifejezésszerkesztő tervezéskor.</td>
<td>Ha <strong>felosztása (&quot;abcdef&quot;, 2)</strong> adatforrásként (DS), <strong>száma (ALLITEMS (DS. Érték))</strong> adja vissza <strong>3</strong>.</td>
</tr>
<tr class="odd">
<td>RENDEZÉS (lista [1 kifejezés, 2 kifejezés, ...])</td>
<td>Megadott listát jelenít meg, amely a megadott, kifejezésként definiált argumentumok kifejezése szerint van sorba rendezve.</td>
<td>Ha <strong>Szállító </strong>a VendTable táblára hivatkozó ER adatforrásként van konfigurálva, akkor<strong> RENDEZÉS (Szállítók, Szállítók.„neve()”)</strong> megjeleníti a név szerinti növekvő sorrendben rendezett szállítók listáját.</td>
</tr>
<tr class="even">
<td>SZTORNÍROZÁS (lista)</td>
<td>A megadott listát a sztornírozott rendezési sorrendben jeleníti meg.</td>
<td>Ha <strong>Szállító </strong>a VendTable táblára hivatkozó ER adatforrásként van konfigurálva, akkor a <strong>SZTORNÍROZÁS (RENDEZÉS (Szállítók, Szállítók.„neve()”)) )</strong> megjeleníti a név szerinti növekvő sorrendben rendezett szállítók listáját.</td>
</tr>
<tr class="odd">
<td>HOL (lista, feltétel)</td>
<td>Azt megadott listát jeleníti meg, amely a megadott feltételek szerint szűrve lett. Eltérően a <strong>SZŰRŐ</strong> funkciótól, a megadott feltétel hozzá van rendelve a memóriában levő listához.</td>
<td>Ha <strong>szállító</strong> van beállítva, az ER-adatforrásként, amely utal a VendTable táblához <strong>ahol (szállítók, Vendors.VendGroup = &quot;40&quot;)</strong> a szállítói csoport 40 tartozó szállítók listáját adja vissza.</td>
</tr>
<tr class="even">
<td>ENUMERÁLÁS (lista)</td>
<td>A megadott lista enumerált rekordjait tartalmazó és a következő elemeket megjelenítő új listáját jeleníti meg:
<ul>
<li>A megadott lista rekordjai rendszeres listákként (<strong>Érték </strong>összetevő)</li>
<li>Az aktuális rekord index (<strong>Szám </strong>összetevő)</li>
</ul></td>
<td>A következő példában az <strong>Enumerált</strong> adatforrás a szállítói rekordok sorszámozott listájaként jött létre a <strong>Szállítók</strong> adatforrásból, amely a <strong>VendTable</strong> táblájára hivatkozik. <a href="./media/picture-enumerate-datasource.jpg"><img src="./media/picture-enumerate-datasource.jpg" alt="Enumerated data source" class="alignnone wp-image-290711 size-full" width="387" height="136" /></a>Itt van a formátum adatkötések lehet létrehozni a kimeneti XML-formátum, amely bemutatja az egyes szállítók sorszámozott csomópontok létrehozásának helyét. <a href="./media/picture-enumerate-format.jpg"><img src="./media/picture-enumerate-format.jpg" alt="Format that has data bindings" class="alignnone wp-image-290721 size-full" width="414" height="138" /></a>Ez az a tervezett formátum futtatásának az eredménye. <a href="./media/picture-enumerate-result.jpg"><img src="./media/picture-enumerate-result.jpg" alt="Result of running the format" class="alignnone wp-image-290731 size-full" width="567" height="176" /></a></td>
</tr>
<tr class="odd">
<td>SZÁMLÁLÓ (lista)</td>
<td>A megadott listában szereplő rekordok számát jeleníti meg, ha a rekord nem üres. Ellenkező esetben <strong>0</strong> (zero) választ jelenít meg.</td>
<td><strong>COUNT (felosztása (&quot;abcd&quot;, 3))</strong> adja vissza <strong>2</strong>, mert a <strong>SPLIT</strong> függvény létrehoz egy listát, amely áll a két bejegyzés.</td>
</tr>
<tr class="even">
<td>LISTOFFIELDS (útvonal)</td>
<td>A következő argumentumok valamelyikéből létrehozott rekordlistát ad ki:
<ul>
<li>Modellfelsorolás</li>
<li>Formátumok felsorolása</li>
<li>Konténer</li>
</ul>
A létrehozott lista a következő mezőket tartalmazó rekordokból áll:
<ul>
<li>Név</li>
<li>Címke</li>
<li>Leírás</li>
</ul>
A Név és a Címke mezőben futásidejű értékek jelennek meg a formátum nyelvi beállításaitól függően.</td>
<td>A következő példa bemutatja az adatmodellbe bevezetett sorszámozást. <a href="./media/ger-listoffields-function-model-enumeration.png"><img src="./media/ger-listoffields-function-model-enumeration-e1474545790761.png" alt="GER LISTOFFIELDS function - model enumeration" class="alignnone wp-image-1203943 size-full" width="514" height="155" /></a>Az alábbi példa mutatja:
<ul>
<li>Jelentésbe adatforrásként beillesztett modellfelsorolás.</li>
<li>A modellfelsorolás e funkció paramétereként használatos ER kifejezés.</li>
<li>A rekordlistatípus jelentésbe illesztett adatforrása a létrehozott ER kifejezést használatával.</li>
</ul><ph id="t1">
< a href="./media/ger-listoffields-function-in-format-expression.png" ></ph><img src="./media/ger-listoffields-function-in-format-expression-e1474546110395.png" alt="GER LISTOFFIELDS function - in format expression" class="alignnone wp-image-1204033 size-full" width="549" height="318" /></a> a következő példa az LISTOFFIELDS funkció segítségével létrehozott rekord lista típusú adatforráshoz kötött ER formátum elemeit mutatja. <a href="./media/ger-listoffields-function-format-design.png"><img src="./media/ger-listoffields-function-format-design.png" alt="GER LISTOFFIELDS function - format design" class="alignnone size-full wp-image-1204043" width="466" height="221" /></a>Ez a tervezett formátum végrehajtásának eredménye. <a href="./media/ger-listoffields-function-format-output.png"><img src="./media/ger-listoffields-function-format-output.png" alt="GER LISTOFFIELDS function - format output" class="alignnone size-full wp-image-1204053" width="585" height="158" /></a><strong>Megjegyzés:</strong> címfordításos szöveges címkék és leírások ER formátumú kimenetre a nyelvi beállítások konfigurálva a szülő fájl és mappa elemek formázásának megfelelően van kitöltve.</td>
</tr>
<tr class="odd">
<td>STRINGJOIN (lista, mezőnév, elválasztó)</td>
<td>A mező értékének összefűzött karakterláncát a kijelölt elválasztóval elválasztott listából adja vissza.</td>
<td>Ha DS adatforrásként a SPLIT ("abc", 1) van megadva, a STRINGJOIN (DS, DS.Value ":") kifejezés "a: b:c" formában jelenik meg</td>
</tr>
<tr class="even">
<td>SPLITLISTBYLIMIT (lista, határérték, korlát forrása)</td>
<td>A megadott listát új, részleges listákból álló listává osztja fel, és a rekordlista tartalmának eredményét adja vissza. A korlátérték paramétere a származási lista korlátjának értékét határozza meg. A korlát forrásának paramétere a teljes összeg növelésének lépését határozza meg. A rendszer nem használja a korlátot az adott lista egyetlen cikkénél, amikor a korlát forrása meghaladja a meghatározott határértéket.</td>
<td>A következő példa bemutatja az adatforrásokat használó mintaformátumot. <a href="./media/ger-splitlistbylimit-format.png"><img src="./media/ger-splitlistbylimit-format.png" alt="GER SPLITLISTBYLIMIT - format" class="alignnone size-full wp-image-1204063" width="396" height="195" /></a><a href="./media/ger-splitlistbylimit-datasources.png"><img src="./media/ger-splitlistbylimit-datasources.png" alt="GER SPLITLISTBYLIMIT - datasources" class="alignnone size-full wp-image-1204073" width="320" height="208" /></a>Ez az eredmény formátum végrehajtása, amely bemutatja a lapos áru cikkek listája. <a href="./media/ger-splitlistbylimit-output.png"><img src="./media/ger-splitlistbylimit-output.png" alt="GER SPLITLISTBYLIMIT - output" class="alignnone size-full wp-image-1204083" width="462" height="204" /></a>Az alábbi példa bemutatja a helyesbített kötegekben árucikk elemek listájának bemutatni, ha egy tételt tartalmaznia kell az áruk 9 határa nem haladhatja meg a teljes súllyal ugyanazt a formátumot. <a href="./media/ger-splitlistbylimit-format-1.png"><img src="./media/ger-splitlistbylimit-format-1.png" alt="GER SPLITLISTBYLIMIT - format 1" class="alignnone size-full wp-image-1204103" width="466" height="438" /></a><a href="./media/ger-splitlistbylimit-datasources-1.png"><img src="./media/ger-splitlistbylimit-datasources-1.png" alt="GER SPLITLISTBYLIMIT - datasources 1" class="alignnone size-full wp-image-1204093" width="645" height="507" /></a>Ez a helyesbített formátum végrehajtásának eredménye. <a href="./media/ger-splitlistbylimit-output-1.png"><img src="./media/ger-splitlistbylimit-output-1.png" alt="GER SPLITLISTBYLIMIT - output 1" class="alignnone size-full wp-image-1204113" width="676" height="611" /></a><strong>Megjegyzés:</strong> a korlát nem vonatkozik a származási lista utolsó eleme, a korlátot forrás (tömeg) (11) értéke meghaladja a meghatározott korlátot (9). Használja a megfelelő formátumelem <strong>WHERE</strong> funkcióját vagy az <strong>Enabled</strong> kifejezést a részleges listák figyelmen kívül hagyásához (átugrásához) a jelentés előállítása során (ha szükséges).</td>
</tr>
<tr class="odd">
<td>FILTER (lista, feltétel)</td>
<td>Visszaállítja az adott listát úgy, hogy a lekérdezést a megadott feltételek szerint szűrve módosítja. Ellentétben a <strong>WHERE</strong> funkcióval, a megadott feltétel az adatbázis szintjén hozzá van rendelve a Táblarekordok típus bármely ER adatforrásához.</td>
<td>SZŰRŐ (szállítók, Vendors.VendGroup = &quot;40&quot;) csak a "40" a szállítók csoportba tartozó szállítók listáját adja vissza Ha <strong>szállító</strong> ER-adatforrásként történő hivatkozás úgy van beállítva a <strong>VendTable</strong> táblázat</td>
</tr>
</tbody>
</table>

### <a name="logical-functions"></a>Logikai függvények

| Funkció                                                                                | Leírás                                                                                                                                                                                                                                                                     | Példa                                                                                                                                                                                                                                                      |
|-----------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ESET (kifejezés, a beállítás 1, eredménye 1 \[, 2 beállítás, eredménye 2\] ... \[, eredmény alapértelmezett\]) | A megadott kifejezés értékének kiértékelése a megadott alternatív beállításokkal szemben. Megjeleníti a lehetőség eredményeit, amely egyenlő a kifejezés eredményével. Ellenkező esetben választható módon megadott alapértelmezett eredményt (utolsó paramétert, amelyet nem előz meg egy lehetőség) jelenít meg. | A **CASE( DATETIMEFORMAT( NOW(), "MM"), "10", "WINTER", "11", "WINTER", "12", "WINTER", "")** a **„WINTER”** karakterláncot jeleníti meg, amikor a jelenlegi Dynamics 365 for Operations munkamenet dátuma október és december közötti. Ellenkező esetben üres karakterláncot jelenít meg. |
| HA (feltétel, 1 érték, 2 érték)                                                        | 1 megadott értéket jelenít meg a megadott feltétel teljesülése esetén. Ellenkező esetben a visszatérési érték 2. Ha értéke 1 és 2 érték rekordok vagy rekordok listáját, az eredmény lesz csak azokat a mezőket, amely mindkét listában szerepel.                                                                     | **HA (1 = 2, „feltétel teljesülése esetén”, „feltétel nem teljesül”)** **„feltétel nem teljesül”** karakterláncot jelenít meg.                                                                                                                                                      |
| NEM (feltétel)                                                                         | Megjeleníti a megadott feltételek sztornírozott logikai értékét.                                                                                                                                                                                                                   | **NEM (IGAZ)** **HAMIS** értéket jelenít meg.                                                                                                                                                                                                                            |
| ÉS (azzal a feltétellel 1\[, azzal a feltétellel 2,... \])                                                 | **IGAZ** értéket jelenít meg, ha *minden *megadott feltétel igaz. Ellenkező esetben **HAMIS** választ jelenít meg.                                                                                                                                                                                            | **ÉS a (1 = 1, „a” = „a”)** **IGAZ** értéket jelenít meg. **ÉS a (1 = 2, „a” = „a”)** **HAMIS** értéket jelenít meg.                                                                                                                                                                           |
| VAGY (azzal a feltétellel 1\[, azzal a feltétellel 2,... \])                                                  | **HAMIS** értéket jelenít meg, ha *minden *megadott feltétel hamis. **IGAZ** értéket jelenít meg, ha *bármely *megadott feltétel igaz.                                                                                                                                                                 | **VAGY a (1 = 2, „a” = „a”)** **IGAZ** értéket jelenít meg.                                                                                                                                                                                                                      |

### <a name="mathematical-functions"></a>Matematikai funkciók

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Funkció</th>
<th>Leírás</th>
<th>Példa</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>ABS (szám)</td>
<td>A megadott szám abszolút értékét jeleníti meg (előjel nélküli számot).</td>
<td><strong>ABS (-1)</strong> <strong>1</strong> értéket jelenít meg.</td>
</tr>
<tr class="even">
<td>TELJESÍTMÉNY (szám, teljesítmény)</td>
<td>A megadott pozitív szám megadott teljesítményre történő javításának eredményét jeleníti meg.</td>
<td><strong>TELJESÍTMÉNY (10, 2)</strong> <strong>100</strong> értéket jelenít meg.</td>
</tr>
<tr class="odd">
<td>NUMBERVALUE (karakterlánc, tizedesjegy-elválasztó, számjegy csoportosítási elválasztó)</td>
<td>A megadott karakterlánc konvertálása egy számhoz. A megadott szimbólumot és a megadott ezres elválasztót is a decimális szám egész és tört részének elválasztására használják.</td>
<td><strong>NUMBERVALUE (&quot;1 234,56&quot;, &quot;,&quot;, &quot;&quot;)</strong> értékét adja vissza <strong>1234,56</strong>.</td>
</tr>
<tr class="even">
<td>ÉRTÉK (karakterlánc)</td>
<td>A megadott karakterlánc konvertálása egy számhoz. A vesszőket és a pont karaktereket (.) decimális elválasztóknak tekintik és a vezető kötőjelet (-) negatív jelként használjál. Adjon meg egy kivételt, ha más nem numerikus karakterek tapasztalhatóak a megadott karakterláncban.</td>
<td><strong>ÉRTÉK (&quot;1 234,56&quot;)</strong> kivételt okoz.</td>
</tr>
<tr class="odd">
<td>KEREKÍTÉS (szám, tizedesjegyek)</td>
<td>Azt a megadott számot jeleníti meg, amelyik a tizedesjegyek megadott számára van kerekítve:
<ul>
<li>Ha a megadott tizedesjegyek értéke nagyobb, mint 0 (nulla) akkor a megadott szám a tizedesjegyek megadott számára van kerekítve.</li>
<li>Ha a megadott tizedesjegyek értéke 0 (nulla) értéket, a megadott szám a legközelebbi egészre van kerekítve.</li>
<li>Ha a megadott tizedesjegyek értéke kisebb, mint 0 (nulla) akkor a megadott szám a tizedesjegyek bal oldalára van kerekítve.</li>
</ul></td>
<td><strong>KEREKÍTÉS (1200,767, 2)</strong> két tizedesjegyre kerekít és <strong>1200,77</strong> értéket jelenít meg. <strong>KEREKÍTÉS (1200,767, -3)</strong> az 1000 legközelebbi többszörösére kerekít és <strong>1000</strong> értéket jelenít meg.</td>
</tr>
<tr class="even">
<td>LEKEREKÍTÉS (szám, tizedesjegyek)</td>
<td>Azt a megadott számot jeleníti meg, amelyik a tizedesjegyek megadott számára van lekerekítve (nullára): <strong>Megjegyzés:</strong> Ez a funkció úgy viselkedik, mint a <strong>KEREKÍTÉS</strong>, de mindig lekerekíti a megadott számot.</td>
<td><strong>LEKEREKÍTÉS (1200,767, 2)</strong> két tizedesjegyre kerekít le és <strong>1200,76</strong> értéket jelenít meg. <strong>LEKEREKÍTÉS (1700,767, -3)</strong> az 1000 legközelebbi többszörösére kerekít le és <strong>1000</strong> értéket jelenít meg.</td>
</tr>
<tr class="odd">
<td>FELKEREKÍTÉS (szám, tizedesjegyek)</td>
<td>Azt a megadott számot jeleníti meg, amelyik a tizedesjegyek megadott számára van felkerekítve (nulla fölött): <strong>Megjegyzés:</strong> Ez a funkció úgy viselkedik, mint a <strong>KEREKÍTÉS</strong>, de mindig felkerekíti a megadott számot.</td>
<td><strong>FELKEREKÍTÉS (1200,763, 2)</strong> két tizedesjegyre kerekít fel és <strong>1200,77</strong> értéket jelenít meg. <strong>FELKEREKÍTÉS (1200,767, -3)</strong> az 1000 legközelebbi többszörösére kerekít fel és <strong>2000</strong> értéket jelenít meg.</td>
</tr>
</tbody>
</table>

### <a name="record-functions"></a>Rekord függvények

| Funkció             | Leírás                                                                                                                                                                                                                                     | Példa                                                                                                                                             |
|----------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------|
| NULLCONTAINER (lista) | **Nulla** rekordot jelenít meg, amely ugyanolyan szerkezetű, mint a megadott rekord listája vagy a rekord. **Megjegyzés: **Ez a funkció már elavult. Használja az **EMPTYRECORD** helyette.                                                                                  | **NULLCONTAINER (FELOSZTÁS („abc”, 1))** megjelenít egy új üres rekordot, amelynek ugyanolyan szerkezete van, mint a **FELOSZTÁS** funkció által megjelenített listának. |
| EMPTYRECORD (rekord) | **Nulla** rekordot jelenít meg, amely ugyanolyan szerkezetű, mint a megadott rekord listája vagy a rekord. **Megjegyzés:** A **null** rekord olyan bejegyzések, ahol az összes mező rendelkezik egy üres értéket (**0**\[nulla\] a számok, üres karakterláncok és így tovább). | **ÜRESREKORD (FELOSZTÁS („abc”, 1))** megjelenít egy új üres rekordot, amelynek ugyanolyan szerkezete van, mint a **FELOSZTÁS** funkció által megjelenített listának.   |

### <a name="text-functions"></a>Szöveg függvények

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Funkció</th>
<th>Leírás</th>
<th>Példa</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>FELSŐ (karakterlánc)</td>
<td>Megjeleníti a megadott karakterláncot, amelyet nagybetűssé alakítanak.</td>
<td><strong>FELSŐ (&quot;minta&quot;)</strong> adja vissza <strong>&quot;minta&quot;</strong>.</td>
</tr>
<tr class="even">
<td>ALSÓ (karakterlánc)</td>
<td>Megjeleníti a megadott karakterláncot, amelyet kisbetűssé alakítanak.</td>
<td><strong>ALSÓ (&quot;minta&quot;)</strong> adja vissza <strong>&quot;minta&quot;</strong>.</td>
</tr>
<tr class="odd">
<td>BALRA (karakterlánc, karakterek száma)</td>
<td>Megjeleníti a megadott karakterlánc elejéről származó karakterek megadott számát.</td>
<td><strong>BALRA (&quot;minta&quot;, 3)</strong> adja vissza <strong>&quot;Sam&quot;</strong>.</td>
</tr>
<tr class="even">
<td>JOBBRA (karakterlánc, karakterek száma)</td>
<td>Megjeleníti a megadott karakterlánc végéről származó karakterek megadott számát.</td>
<td><strong>JOBBRA (&quot;minta&quot;, 3)</strong> adja vissza <strong>&quot;minta&quot;</strong>.</td>
</tr>
<tr class="odd">
<td>KÖZEPES (szöveg, kezdő beosztás, karakterek száma)</td>
<td>Megjeleníti a megadott karakterláncból származó karakterek megadott számát a megadott pozíciótól kezdve.</td>
<td><strong>MID (&quot;minta&quot;, 2, 3)</strong> adja vissza <strong>&quot;amp&quot;</strong>.</td>
</tr>
<tr class="even">
<td>LEN (karakterlánc)</td>
<td>A megadott karakterláncban szereplő karakterek számát jeleníti meg.</td>
<td><strong>HOSSZ (&quot;minta&quot;)</strong> adja vissza <strong>6</strong>.</td>
</tr>
<tr class="odd">
<td>CHAR (szám)</td>
<td>Megjelenítik a megadott Unicode szám által hivatkozott karakterek karakterláncát.</td>
<td><strong>CHAR (255)</strong> adja vissza <strong>&quot;y&quot;</strong>. <strong>Megjegyzés:</strong> A visszaadott karakterlánc a szülő FILE formátumelemben kiválasztott kódolástól függ. A támogatott kódolások listája a <a href="https://msdn.microsoft.com/en-us/library/system.text.encoding(v=vs.110).aspx">Kódolási osztály</a> témakörben található meg.</td>
</tr>
<tr class="even">
<td>ÖSSZEFŰZÉS (1-es karakterlánc [, 2-es karakterlánc...])</td>
<td>Megjeleníti az összes megadott szöveg karakterláncot, amely egy karakterlánchoz van kapcsolva.</td>
<td><strong>ÖSSZEFŰZÉSE (&quot;abc&quot;, &quot;def&quot;)</strong> adja vissza <strong>&quot;abcdef&quot;</strong>. <strong>Megjegyzés:</strong> a kifejezés <strong>&quot;abc&quot;&amp;&quot;def&quot;</strong> is vissza <strong>&quot;abcdef&quot;</strong>.</td>
</tr>
<tr class="odd">
<td>FORDÍTÁS (karakterlánc, minta, csere)</td>
<td>Megjeleníti a megadott karakterláncot, amelyben a megadott minta karakterlánc karaktereinek összes előfordulása a karakterekkel van helyettesítve a megadott helyettesítő karakterlánc megfelelő helyén.</td>
<td><strong>FORDÍTÁS (&quot;abcdef&quot;, &quot;cd&quot;, &quot;GH&quot;)</strong> váltja fel a mintát <strong>&quot;cd&quot;</strong> a karakterláncot tartalmazó <strong>&quot;GH&quot;</strong> és <strong>&quot;abGHef&quot;</strong>.</td>
</tr>
<tr class="even">
<td>CSERE (karakterlánc, minta, helyettesítő, reguláris kifejezés jelző)</td>
<td>Ha a megadott reguláris kifejezés jelző <strong>igaz</strong>, akkor megjeleníti a megadott karakterláncot, amely a funkcióra vonatkozó minta argumentumaként meghatározott reguláris kifejezés alkalmazása által módosult. A kifejezés segítségével meg lehet találni azokat a karaktereket, amelyeket ki kell cserélni. A megadott helyettesítési argumentum karakterei segítségével ki lehet cserélni a megtalált karaktereket. Ha a megadott reguláris kifejezés jelző <strong>hamis</strong>, ez a funkció úgy viselkedik, mint a <strong>FORDÍTÁS</strong> funkció.</td>
<td>  <strong>Csere (&quot;+1 923 456 4971&quot;, &quot;[^ 0-9]&quot;, &quot;&quot;, igaz)</strong> vonatkozik egy reguláris kifejezés, amely eltávolítja az összes nem numerikus szimbólumokat, és adja vissza <strong>&quot;19234564971&quot;</strong>. <strong>Csere (&quot;abcdef&quot;, &quot;cd&quot;, &quot;GH&quot;, hamis)</strong> váltja fel a mintát <strong>&quot;cd&quot;</strong> a karakterláncban <strong>&quot;GH&quot;</strong> és <strong>&quot;abGHef&quot;</strong>.</td>
</tr>
<tr class="odd">
<td>SZÖVEG (bevitel)</td>
<td>A megadott bemenetet jeleníti meg, amelyet az aktuális Dynamics 365 for Operations példányának kiszolgálója területi beállításainak megfelelően formázott szöveges karakterlánccá alakítanak. A <strong>valós</strong> típus értékeihez a karakterlánc-konverzió két tizedesjegyre korlátozódik.</td>
<td>Ha van meghatározva a Dynamics 365 műveletek példány kiszolgáló területi beállításhoz tartozó <strong>EN-US</strong>, <strong>szöveg (most ())</strong> vissza a jelenlegi Dynamics 365 műveletek munkamenet dátuma, a 12/17/2015, mint a szöveges karakterlánc <strong>&quot;12/17/2015 07:59:23 AM&quot;</strong>. <strong>SZÖVEG (1/3)</strong> adja vissza <strong>&quot;0.33&quot;</strong>.</td>
</tr>
<tr class="even">
<td>FORMÁTUM (1-es karakterlánc, 2-es karakterlánc [, 3-as karakterlánc...])</td>
<td>Azt a megadott karakterláncot jeleníti meg, amely az <strong>%N</strong> elem bármely előfordulásának <em>n</em>argumentumával történő helyettesítése által formázva lett. Az argumentumok karakterláncok. Amennyiben egy argumentum nem egy paraméter, a paraméterrel visszaadott <strong>&quot;%N&quot;</strong> a karakterláncban. A <strong>valós</strong> típus értékeihez a karakterlánc-konverzió két tizedesjegyre korlátozódik.</td>
<td>Ebben a példában a <strong>PaymentModel</strong> adatforrás megjeleníti a vevőrekordok listáját a <strong>Vevő</strong> összetevőn keresztül és az adatérték feldolgozását a <strong>ProcessingDate</strong> mezőn keresztül. <a href="./media/picture-format-datasource.jpg"><img src="./media/picture-format-datasource.jpg" alt="PaymentModel data source" class="alignnone wp-image-290751 size-full" width="293" height="143" /></a>Célja, hogy az elektronikus dokumentum létrehozása a kiválasztott ügyfelek ER formátumban <strong>PaymentModel</strong> adatforrásként ki van jelölve, és szabályozza a folyamatot. A végfelhasználó kivételt kap, amikor a kiválasztott vevő le van tiltva a jelentés feldolgozása során. Az ellenőrzés feldolgozásának ezen típusára vonatkozóan tervezett formula a következő forrásokat használhatja:
<ul>
<li>A SYS70894 címkével ellátott Dynamics 365 for Operations a következő szöveggel rendelkezik:
<ul>
<li><strong>Az EN-US nyelven:</strong>&quot;Nincs nyomtatnivaló&quot;</li>
<li><strong>DE nyelv:</strong>&quot;Nichts zu drucken&quot;</li>
</ul></li>
<li>A SYS18389 címkével ellátott Dynamics 365 for Operations a következő szöveggel rendelkezik:
<ul>
<li><strong>Az EN-US nyelven:</strong>&quot;a(z) %1 vevő leállítva a következőhöz: %2.&quot;</li>
<li><strong>DE nyelv:</strong>&quot;'%1' adós wird für a(z) %2 gesperrt.&quot;</li>
</ul></li>
</ul>
Íme, úgy kell megtervezni, hogy a képlet: formátum (ÖSSZEFŰZ (@&quot;SYS70894&quot;,&quot;. &quot;@&quot;SYS18389&quot;), model.Customer.Name, DATETIMEFORMAT (modell. ProcessingDate, &quot;d&quot;)) a jelentés feldolgozása a <strong>Litware Kiskereskedelmi vevő</strong> a 2015. December 17., a a <strong>EN-US</strong> kultúra és a <strong>EN-US</strong> nyelv, a képlet eredménye az alábbi szöveget, és a végfelhasználó számára a kivételhez tartozó üzenet lehet előterjeszteni: &quot;Nincs nyomtatnivaló. Vevő Litware Kiskereskedelmi le van állítva, a 12/17/2015.&quot; Ha ugyanazt a jelentést feldolgozása a<strong> Litware Kiskereskedelmi vevő</strong> a 2015. December 17., a a <strong>DE</strong> kultúra és a <strong>DE</strong> nyelv, a képlet eredménye a következő szöveget egy másik dátum formátuma: &quot;Nichts zu drucken. Adós "Litware Kiskereskedelmi" wird für 17.12.2015 gesperrt.&quot; <strong>Megjegyzés: </strong>A címkék ER-képleteiben kerül alkalmazásra a következő szintaxis:
<ul>
<li><strong>Dynamics 365 a tevékenységek, erőforrások címkék:</strong> <strong>@&quot;X&quot;</strong>, ahol X a Címkeazonosítót, az alkalmazásobjektum-fában (AOT)</li>
<li><strong>ER-konfigurációk lévő címkék:</strong> <strong>@&quot;ER_LABEL:X&quot;</strong>, ahol X a Címkeazonosítót, az ER-konfiguráció</li>
</ul></td>
</tr>
<tr class="odd">
<td>SZÁMFORMÁTUM (szám, formátum)</td>
<td>Megjeleníti a megadott formátumban szereplő megadott szám karakterlánc formáját. (A támogatott formátumok kapcsolatos információkért lásd: <a href="https://msdn.microsoft.com/en-us/library/dwhawy9k(v=vs.110).aspx">standard</a> és <a href="https://msdn.microsoft.com/en-us/library/0c899ak8(v=vs.110).aspx">egyéni</a>.) A környezet, amelyet a függvény futtatásához használt számok formázása a kultúra határozza meg.</td>
<td>Az EN-US kulturális környezet <strong>NUMBERFORMAT (0,45, &quot;p&quot;)</strong> adja vissza <strong>&quot;45.00 %&quot;</strong>. <strong>NUMBERFORMAT (10.45, &quot;#&quot;)</strong> adja vissza <strong>&quot;10&quot;</strong>.</td>
</tr>
<tr class="even">
<td>NUMERALSTOTEXT (szám, nyelv, pénznem, pénznem névjelzőjének nyomtatása, tizedes)</td>
<td>A szöveges karakterlánccá alakított (konvertált) számot adja vissza betűvel kifejezve a megadott nyelven. A nyelvkód megadása nem kötelező: ha üres karakterláncként van meghatározva, a futó környezet (mappa vagy fájl generálására meghatározott) nyelvi kódját használja helyette a rendszer. A pénznemkód megadása nem kötelező. Ha üres karakterláncként van meghatározva, a rendszer a vállalati pénznemet használja. Megjegyzés: a <strong>Pénznem nevének nyomtatása</strong> paraméter és a <strong>Tizedes</strong> paraméter elemzését csak a következő nyelvkódokra vonatkozóan végzi el a rendszer: <strong>CS</strong>, <strong>ET</strong>, <strong>HU</strong>, <strong>LT</strong>, <strong>LV</strong>, <strong>PL</strong>, <strong>RU</strong>. Megjegyzés: a <strong>Pénznem nevének nyomtatása</strong> paraméter elemzését csak azon, a Dynamics 365 for Operations rendszert használó vállalatok esetében végzi el a rendszer, amelyek országkontextusa támogatja a valutaragozást.</td>
<td>NUMERALSTOTEXT (1234,56, &quot;EN&quot;, &quot;&quot;, hamis, 2) adja vissza "Egy ezred két száz harminc négy és 56" NUMERALSTOTEXT (120, &quot;PL&quot;, &quot;&quot;, hamis, 0) adja vissza a "Dwadzieścia SA" NUMERALSTOTEXT (120.21, &quot;RU&quot;, &quot;EUR&quot;, igaz, 2) "Сто двадцать евро 21 евроцент" adja vissza</td>
</tr>
<tr class="odd">
<td>PADLEFT (karakterlánc, hossz, kitöltő karakterek)</td>
<td>Megadott hosszúságú karakterláncot ad vissza, amelyben az aktuális karakterlánc eleje megadott karakterekkel van kitöltve.</td>
<td>A PADLEFT (“1234”, 10, “ “) a következő szöveges karakterláncot adja vissza: „      1234”</td>
</tr>
</tbody>
</table>

### <a name="data-collection-functions"></a>Adatgyűjtési függvények

Funkció

Leírás

Példa

FORMATELEMENTNAME ()

Az aktuális formátum összetevőjének nevét adja vissza. Üres karakterláncot ad vissza, ha az aktuális fájlok **Kimeneti részletek gyűjtése** jelzője ki van kapcsolva.

Tekintse meg az **ER kimeneti adatformátum használata számlálás és összegzés céljából** című Feladat-útmutatót (az **Informatikai szolgáltatások/megoldások összetevőinek beszerzése/kifejlesztése** üzleti folyamat), ha többet szeretni megtudni ezen funkciók használatáról.

SUMIFS (karakterlánc kulcs megengedő, range1 karakterlánc kritériumok, feltételek érték1 karakterlánc \[, range2 karakterlánc kritériumok, feltételek érték2 string,... \])

XML-csomópontok értékeinek összegét adja vissza (kulcsként meghatározott névvel), amelyet a rendszer a formátum végrehajtásakor gyűjt, és amely megfelel a megadott feltételeknek (tartomány és érték). Nulla érték jelenik meg, ha az aktuális fájlok **Kimeneti részletek gyűjtése **jelzője ki van kapcsolva.

SUMIF (kulcskarakterlánc az összegzéshez, feltételtartomány karakterlánca, kiválasztási feltétel karakterlánca)

XML-csomópontok értékeinek összegét adja vissza (kulcsként meghatározott névvel), amelyet a rendszer a formátum végrehajtásakor gyűjt, és amely megfelel a megadott feltételnek (tartomány és érték). Nulla érték jelenik meg, ha az aktuális fájlok **Kimeneti részletek gyűjtése** jelzője ki van kapcsolva.

COUNTIFS (range1 karakterlánc kritériumok, feltételek érték1 string \[, range2 karakterlánc kritériumok, feltételek érték2 string,... \])

XML-csomópontok számát adja vissza (kulcsként meghatározott névvel), amelyet a rendszer a formátum végrehajtásakor gyűjt, és amely megfelel a megadott feltételeknek (tartomány és érték). Nulla érték jelenik meg, ha az aktuális fájlok **Kimeneti részletek gyűjtése** jelzője ki van kapcsolva.

COUNTIF (feltételtartomány karakterlánca, kiválasztási feltételek karakterlánca)

XML-csomópontok számát adja vissza (kulcsként meghatározott névvel), amelyet a rendszer a formátum végrehajtásakor gyűjt, és amely megfelel a megadott feltételnek (tartomány és érték). Nulla érték jelenik meg, ha az aktuális fájlok **Kimeneti részletek gyűjtése** jelzője ki van kapcsolva.

COLLECTEDLIST (range1 karakterlánc kritériumok, feltételek érték1 string \[, range2 karakterlánc kritériumok, feltételek érték2 string,... \])

XML-csomópontok értékeinek listáját adja vissza (kulcsként meghatározott névvel), amelyet a rendszer a formátum végrehajtásakor gyűjt, és amely megfelel a megadott feltételeknek (tartomány és érték). Üres listát ad vissza, ha az aktuális fájlok **Kimeneti részletek gyűjtése **jelzője ki van kapcsolva.

### <a name="other-business-domainspecific-functions"></a>Egyéb (üzleti területre jellemző) függvények

| Funkció                                                                         | Leírás                                                                                                                                                                                                                                                        | Példa                                                                                                                                                                                                                                                                                                       |
|----------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| PÉNZNEMVÁLTÁS (összeg, eredeti pénznem, cél pénznem, dátum, vállalat)        | A megadott pénzösszeg konvertálása az eredeti pénznemről a cél pénznemre a megadott Dynamics 365 for Operations vállalat beállításainak használata segítségével a megadott időpontban.                                                                            | **PÉNZNEMVÁLTÁS (1, „EUR”, „USD”, MA(), „DEMF”)** egy euró egyenértékét USA-dollárban jelenít meg az aktuális munkameneti napon a DEMF vállalat beállításai alapján.                                                                                                                                  |
| ÖSSZEGKEREKÍTÉS (szám, tizedes, kerekítési szabály)                                       | A megadott összeget a megadott kerekítési szabály és a megadott tizedesjegyek száma szerint kerekítenek. **Megjegyzés:** A kerekítési szabályt a **RoundOffType** felsorolás Dynamics 365 for Operations értékeként kell meghatározni.                          | Ha a **modell. Űrlapokon** paraméter értéke *** Downward *** **ROUNDAMOUNT (1000.787, 2, minta. Űrlapokon)** értékét adja vissza **1000.78**. Ha a **modell.Roundoff** paraméter értéke vagy **Normál** vagy **Felkerekítés**lehetőségre van beállítva, akkor az **ÖSSZEGKEREKÍTÉS (1000,787, 2. modell.Roundoff)** **1000,79** értéket jeleníti meg. |
| CURCredRef (számjegy)                                                              | Egy hitelező hivatkozást jelenít meg a megadott számlaszám számjegyei alapján.                                                                                                                                                                                  | **CURCredRef („VEND-200002”)** **„2200002”** értéket jelenít meg.                                                                                                                                                                                                                                                         |
| MOD\_97 (jegy)                                                                 | Egy hitelező hivatkozást MOD97 kifejezésként jelenít meg a megadott számlaszám számjegyei alapján.                                                                                                                                                            | **MOD\_97 ("VEND-200002")** adja vissza **"20000285"**.                                                                                                                                                                                                                                                           |
| ISOCredRef (számjegy)                                                              | Egy ISO hitelezői hivatkozást jelenít meg a megadott számlaszám betűi és számjegyei alapján. **Megjegyzés: **A nem ISO szabványos betűkből származó szimbólumok eltávolításához, a bemeneti paramétereket le kell fordítani a függvénynek történő megfeleltetés előtt. | **ISOCredRef („VEND-200002”)** **„RF23VEND-200002”** értéket jelenít meg.                                                                                                                                                                                                                                                 |
| CN\_GBT\_AdditionalDimensionID (karakterlánc, szám)                                  | A további pénzügyi dimenzió azonosítójának beolvasása. Ebben a karakterláncban a dimenziókat a rendszer vesszővel elválasztott azonosítókként jeleníti meg. Ebben a karakterláncban a kért dimenzió számsorozatkódját számok határozzák meg.                                                                            | CN\_GBT\_AdditionalDimensionID ("AA, BB, CC, nn, EE, FF, GG, HH", 3) vissza a "Másolat"                                                                                                                                                                                                                                      |
| GetCurrentCompany ()                                                             | Az aktuálisan bejelentkezett vállalat kódját jeleníti meg.                                                                                                                                                                                                                    |                                                                                                                                                                                                                                                                                                               |
| CH\_BANK\_MOD\_10 (jegy)                                                       | Egy hitelező hivatkozást MOD10 kifejezésként jelenít meg a megadott számlaszám számjegyei alapján.                                                                                                                                                                      | CH\_BANK\_MOD\_("VEND-200002") 10 3 adja vissza                                                                                                                                                                                                                                                                   |
| FA\_SUM (befektetett eszköz kód, a modell kódja, a kezdési dátum, záró dátuma)               | A tárgyi eszköz időszakra vonatkozó összegeinek előkészített adattárolóját adja vissza.                                                                                                                                                                                         | FA\_("COMP-000001", "Aktuális", dátum1, dátum2) összege adja meg az előkészített adatok tároló a tárgyi eszköz "COMP-000001" "Aktuális" értékmodell időtartamra dátum1 és dátum2.                                                                                                                        |
| FA\_egyenlege (befektetett eszköz kód, a modell kódja, jelentési év, jelentés dátuma) | A tárgyieszköz-egyenlegek előkészített adattárolóját adja vissza. A jelentési évet az **AssetYear** felsorolás Dynamics 365 for Operations értékeként kell meghatározni.                                                                                           | FA\_SUM ("COMP-000001", "Aktuális", AxEnumAssetYear.ThisYear, SESSIONTODAY ()) dátumot adja vissza a előkészített adatok tároló egyenlegek a befektetett eszköz "COMP-000001" értékmodell "Aktuális" az aktuális 365 a műveletek munkamenet.                                                                |

### <a name="functions-list-extension"></a>A funkciók lista kiterjesztése

Az ER segítségével bővítheti az ER kifejezésekben használt függvények listáját. Ez bizonyos műszaki erőfeszítéseket igényel. Részletes tudnivalókat lásd: [Elektronikus jelentéskészítési funkciók listájának kibővítése](general-electronic-reporting-formulas-list-extension.md).

<a name="see-also"></a>Lásd még
--------

[Elektronikus jelentések áttekintése](general-electronic-reporting.md)

[Elektronikus jelentéskészítési (ER) funkciók listájának kibővítése](general-electronic-reporting-formulas-list-extension.md)


