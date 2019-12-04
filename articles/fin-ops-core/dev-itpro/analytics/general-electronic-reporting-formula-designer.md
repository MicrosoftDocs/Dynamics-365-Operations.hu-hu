---
title: Képletszerkesztő elektronikus jelentésekhez (ER)
description: Ez a témakör ismerteti a képletszerkesztő használatát az Elektronikus jelentésben (ER).
author: NickSelin
manager: kfend
ms.date: 07/30/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e55ab83302cc75b1a9d9d3e4f06d2258697b31fc
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/06/2019
ms.locfileid: "2771214"
---
# <a name="formula-designer-in-electronic-reporting-er"></a>Képletszerkesztő elektronikus jelentésekhez (ER)

[!include [banner](../includes/banner.md)]

Ez a témakör ismerteti a képletszerkesztő használatát az Elektronikus jelentésben (ER). Ha egy formátumot az ER-ben meghatározott elektronikus dokumentumra vonatkozóan tervez meg, akkor használhat képleteket az adatok átalakításához a dokumentum teljesítésére és formázására vonatkozó követelményekhez történő megfeleltetés érdekében. Ezek a képletek a Microsoft Excel programban található képletekre hasonlítanak. A képletek funkciók különféle típusait támogatják - szöveg, dátum és időpont, matematikai logika, információ, adattípus-konvertálás és egyéb (üzletitartomány-specifikus funkciók).

## <a name="formula-designer-overview"></a>Képletszerkesztő áttekintése

Az ER támogatja a képletszerkesztőt. Ezért tervezéskor konfigurálhatja a futtatás közben a következő feladatokhoz használható kifejezéseket:

- Átalakításra vonatkozó adatok, amelyek az alkalmazás adatbázisából származnak, és egy ER adatmodellben kell megadni őket, amelyet az ER formátumok adatforrási feladataira terveztek. (Például ezek az átalakítások magukban foglalhatják a szűrést, csoportosítást és az adattípus-konverziót.)
- Olyan formátumadatok, amelyeket egy generáló elektronikus dokumentumba kell küldeni, egy adott ER-formátum elrendezésének és feltételeinek megfelelően. (Például a formázás a kért nyelv vagy kultúra,illetve a kódolás alapján történhet).
- Elektronikus dokumentumok létrehozási folyamatának szabályozása. (Például a kifejezések az adatok feldolgozásától függően engedélyezhetik vagy letilthatják a formátum egyes elemeinek kimenetét. Meg is szakíthatják a dokumentum létrehozásának folyamatát, vagy üzeneteket küldhetnek a felhasználóknak.)

A **Képlettervező** lapot a következő műveletek bármelyikének végrehajtásakor meg lehet megnyitni:

- Az adatmodellek komponenseihez tartozó adatforrás cikkek kötése.
- A formátum komponenseihez tartozó adatforráscikkek kötése.
- Az adatforrások részeként számított mezők karbantartásának elvégzése.
- Felhasználó által megadott paraméterek láthatósági feltételeinek meghatározása.
- A formátum átalakításainak tervezése.
- A formátum összetevőkre vonatkozó engedélyező feltételek meghatározása.
- A formátum fájl összetevőkre vonatkozó fájlneveinek definíciója.
- A vezérlő-ellenőrzések feldolgozására vonatkozó feltételek meghatározása.
- A vezérlő-ellenőrzések feldolgozására vonatkozó üzenetszöveg meghatározása.

## <a name="designing-er-formulas"></a>ER-képletek tervezése

### <a name="data-binding"></a>Adatok kötése

Az ER Képletszerkesztő segítségével meghatározhatja azokat a kifejezéseket, amelyek átalakítják az adatforrásból származó adatokat, úgy hogy az adatokat az adattárolóban futtásidőben meg lehet adni:

- Az alkalmazás-adatforrásokból és futtatási paraméterekből egy ER adatmodellbe
- Az ER adatmodell ER formátumba
- Az alkalmazás-adatforrásokból és futtatási paraméterekből egy ER-formátumba

Az alábbi ábra bemutatja az ilyen típusú kifejezés tervezését. Ebben a példában a kifejezés két tizedesjegy pontosságra kerekíti az **Intrastat.AmountMST** mezőjének – Intrastat tábla – értékét, majd visszaadja a kerekített értéket.

[![Adatok kötése](./media/picture-expression-binding.jpg)](./media/picture-expression-binding.jpg)

Az alábbi ábra bemutatja, hogyan használható az ilyen típusú kifejezés. Ebben a példában a tervezett kifejezés eredményének megadása a **Adóösszeg-jelentési** adatmodell **Transaction.InvoicedAmount** komponensének alapján történik.

[![Használatban lévő adatkötés](./media/picture-expression-binding2.jpg)](./media/picture-expression-binding2.jpg)

Futásidőben a tervezett **(Intrastat.AmountMST 2) a KEREKÍTÉSI** képlet az **AmountMST** mező értékét két tizedesjegy pontossággal kerekíti az Intrastat tábla minden egyes rekordjánál. Ezután a kerekített értéket beviszi az **Adóbevallás** adatmodell **Transaction.InvoicedAmount** összetevőjébe.

### <a name="data-formatting"></a>Adatformázás

Az ER Képletszerkesztő segítségével meghatározhatja azokat a formátumokat, amelyek átalakítják az adatforrásból származó adatokat, úgy hogy adatokat küldhet egy elektronikusan létrejövő dokumentum részeként. Előfordulhat, hogy olyan formátummal kell dolgoznia, amelyet amelyet olyan tipikus szabályként kell alkalmazni, amelyet egy formátumban újra kell használni. Ebben az esetben a formátumot bevezetheti egyszer a formátum konfigurációjában névvel ellátott, formázási kifejezést tartalmazó átalakításként. Ez az elnevezett átalakítás hozzákapcsolható számos formátum-összetevőhöz, amelynek kimenetét formázni kell a létrehozott formázási kifejezésnek megfelelően.

Az alábbi ábra bemutatja az ilyen típusú átalakítás tervezését. Ebben a példában a **TrimmedString** átalakítás a **karakterlánc** adattípus bejövő adatait csonkolja a kezdő és záró szóközök eltávolításával. Ezután a csonkolt karakterláncot adja vissza.

[![Átalakítás](./media/picture-transformation-design.jpg)](./media/picture-transformation-design.jpg)

Az alábbi ábra bemutatja, hogyan használható az ilyen típusú átalakítás. Ebben a példában számos formátum-összetevő küld szöveget kimenetként futásidóben a létrehozó elektronikus dokumentum számára. Ezen formátum-összetevők mindegyike név szerint hivatkozik a **TrimmedString** átalakításra.

[![Használt átalakítás](./media/picture-transformation-usage.jpg)](./media/picture-transformation-usage.jpg)

Amikor a formátum azon összetevőit, mint például az előző példában a **partyName** összetevőt, amelyek hivatkoznak a **TrimmedString** átalakításra, ez az átalakítás kimenetként küldi el a létrehozó elektronikus dokumentum számára. Ez a szöveg nem tartalmazza a kezdő és záró szóközöket.

Ha olyan formázással rendelkezik, amelyet egyénileg kell alkalmazni, akkor a formázás a megadott formátum-összetevő kötésének egyéni kifejezéseként jelenítheti meg. Az alábbi ábra bemutatja az ilyen típusú kifejezését. Ebben a példában a **partyType** formátum összetevő az adatforráshoz kötött azon kifejezésen keresztül, amely átalakítja a **Model.Company.RegistrationType** mezőjéből származó bejövő adatokat az adatforrásban a nagybetűs szöveghez. A kifejezés ezután ezt a szöveget az elektronikus dokumentum számára kimenetként küldi el.

[![Formázás alkalmazása egyes összetevőkre](./media/picture-binding-with-formula.jpg)](./media/picture-binding-with-formula.jpg)

### <a name="process-flow-control"></a>Folyamatáramlat irányítás

A ER képlettervező segítségével meg lehet határozni azokat a kifejezéseket, amelyek irányítják az elektronikus dokumentumok létrehozásának folyamatábráját. A következő feladatokat végezheti el:

- Határozza meg azokat a kifejezéseket, amelyek meghatározzák, hogy mikor kell egy dokumentumkészítési folyamatot megszakítani.
- Határozza meg azokat a kifejezéseket, amelyek üzeneteket hoznak létre a felhasználónak a megállított folyamatról vagy végrehajtásnapló-üzeneteket adnak ki a jelentéskészítés zajló folyamatáról.
- Adja meg a generálási elektronikus dokumentumok fájlneveit és létrehozás szabályozó feltételeit.

A folyamatáramlat irányítás minden szabálya egyéni ellenőrzésként van tervezve. Az alábbi ábra bemutatja az ilyen típusú ellenőrzést. Íme a konfiguráció magyarázata ebben a példában:

- Az ellenőrzés akkor megy végbe, amikor a **INSTAT** csomópont létrejön az XML-fájl létrehozása során.
- Ha a tranzakció listája üres, az ellenőrzés megállítja a végrehajtási folyamatot és **HAMIS** értéket küld vissza.
- Az ellenőrzés egy hibaüzenetet küld vissza, amely tartalmazza a felhasználó által előnyben részesített nyelven a SYS70894 címke szövegét.

[![Ellenőrzés](./media/picture-validation.jpg)](./media/picture-validation.jpg)

Az ER képletszerkesztő segítségével generálhat egy fájlnevet a létrejövő elektronikus dokumentum számára, és kezelheti a fájl létrejöttének folyamatát. Az alábbi ábra bemutatja az ilyen típus folyamatáramlat-irányítás tervezését. Íme a konfiguráció magyarázata ebben a példában:

- A **model.Intrastat** adatforrásból származó rekordok listája kötegekre oszlik. Minden egyes köteg legfeljebb 1000 rekordot tartalmaz.
- A kimenet létrehoz egy irányítószámot, amely tartalmaz egy fájlt minden létrehozott kötegre vonatkozóan egy XML-formátumú fájlban.
- Egy kifejezés a létrejövő elektronikus dokumentumokra vonatkozó fájlnevet ad vissza a fájlnév és a fájlnév-kiterjesztés összefűzésével. A második kötegre és minden további kötegre vonatkozóan a fájl neve tartalmazza a Kötegazonosítót utótagként.
- Egy kifejezés lehetővé teszi ( **IGAZ** visszaküldése esetén) a fájl létrehozási folyamatát azon kötegekre vonatkozóan, amelyek legalább egy rekordot tartalmaznak.

[![Fájlvezérlés](./media/picture-file-control.jpg)](./media/picture-file-control.jpg)

### <a name="documents-content-control"></a>Dokumentumtartalmak szabályzása

Az elektronikus képlettervező segítségével olyan kifejezéseket állíthat be, amelyek vezérlik, hogy milyen adatokat kell elhelyezni az elektronikus dokumentumokban futásidőben. A kifejezések az adatok feldolgozásától és a konfigurált logikától függően engedélyezhetik vagy letilthatják a formátum egyes elemeinek kimenetét. Ezeket a kifejezéseket egyetlen formátumú elemként is megadhatja az **Engedélyezve** mezőben **Műveleti tervező lap** **Hozzárendelés lapján**, **Logikai értéket** visszaadó logikai feltételként:

-   Ha **igaz** értéket ad vissza, a program végrehajtja az aktuális formátumelemet.
-   Ha **Hamis** értéket ad vissza, a program kihagyja az aktuális formátumelemet.

A következő ábra az ilyen típusú kifejezéseket mutatja meg (a **11.12.11** verzió a **ISO20022 Credit transfer (NO)** formátum konfiguráció a Microsoft részéről egy példa). Az **XMLHeader** -formátum összetevő úgy van beállítva, hogy leírja a átutalási üzenet szerkezetét az ISO 20022 XML-szabványoknak megfelelően. Az **XMLHeader/Document/CstmrCdtTrfInitn/PmtInf/CdtTrfTxInf/RmtInf/Ustrd** formátumösszetevő úgy van beállítva, hogy hozzáadja a létrejövő üzenethez az **Ustrd** XML-elemet, és az átutalási adatokat elhelyezze strukturálatlan formátumban a következő XML-elemek szövegeként:

-   A **PaymentNotes** összetevő a fizetési megjegyzések szövegének kimeneteként szolgál.
-   A **DelimitedSequence** összetevő kimenete az aktuális átutalás kiegyenlítéséhez használt vesszővel tagolt számlaszámok.

[![Művelettervező](./media/GER-FormulaEditor-ControlContent-1.png)](./media/GER-FormulaEditor-ControlContent-1.png)

> [!NOTE]
> A **PaymentNotes** és **DelimitedSequence** összetevők kérdőjellel vannak megjelölve. Ez azt jelenti, hogy mindkét összetevő használata feltételes következő kritériumok alapján:

-   A **PaymentNote** összetevőjéhez a **@.PaymentsNotes<>""** kifejezés lehetővé teszi (**IGAZ** érték visszaküldésével) az **Ustrd** XML-elembe generálását, a fizetési megjegyzések szövegét, ha az aktuális átutalás szövege nem üres.

[![Művelettervező](./media/GER-FormulaEditor-ControlContent-2.png)](./media/GER-FormulaEditor-ControlContent-2.png)

-   A **DelimitedSequence** összetevőhöz definiált **@.PaymentsNotes=""** kifejezés engedélyezi (**IGAZ** érték visszaküldésével) az **Ustrd** XML elem kitöltését, vesszővel elválasztott számlaszámokkal, amelyeket az aktuális átutalás kiegyenlítéséhez használnak amikor az átutalás fizetési megjegyzése üres.

[![Művelettervező](./media/GER-FormulaEditor-ControlContent-3.png)](./media/GER-FormulaEditor-ControlContent-3.png)

Ennek a beállításnak a alapján az összes adósi kifizetésre generált üzenet **Ustrd** XML-elem tartalmazni fogja a fizetési megjegyzések szövegét, vagy ha az ilyen szöveg üres, akkor a kifizetés kiegyenlítéséhez használt számlákat vesszővel elválasztva.

### <a name="basic-syntax"></a>Alap szintaxis

ER kifejezések bármennyi vagy az összes elemet tartalmazhatja a következő elemek közül:

- Állandók
- Operátorok
- Hivatkozások
- Útvonalak
- Funkciók

#### <a name="constants"></a>Állandók

Amikor a kifejezéseket tervezi, használhat szöveges és a numerikus állandókat (nem számított értékeket). Például az **ÉRTÉK ("100") + 20** kifejezés a **20** numerikus konstanst és a **100** szövegkonstanst használja és a **120** numerikus értéket adja vissza. Az ER képletszerkesztő támogatja a feloldó szakaszokat. Így meghatározhat olyan kifejezés-karakterláncot, amelyet eltérően kell kezelni. Például a **„Lev Tolstoy” „Háború és béke „1. kötet”** kifejezés megjeleníti a **„Lev Tolstoy” „Háború és béke „1. kötet”** szöveges karakterláncot.

#### <a name="operators"></a>Operátorok

Az alábbi táblázat bemutatja az aritmetikai operátorokat, amelyek segítségével elvégezheti a matematikai alapműveleteket, mint például összeadás, kivonás, szorzás és osztás.

| Kezelő | Jelentés               | Példa |
|----------|-----------------------|---------|
| +        | Hozzáadás              | 1+2     |
| -        | Kivonás, tagadás | 5-2, -1 |
| \*       | szorzás        | 7\*8    |
| /        | Osztály              | 9/3     |

A következő táblázat a támogatott összehasonlító operátorokat mutatja. Ezen operátorok segítségével összehasonlíthat két értéket.

| Kezelő | Jelentés                  | Példa    |
|----------|--------------------------|------------|
| =        | Egyenlő                    | X=Y        |
| &gt;     | Nagyobb, mint             | X&gt;Y     |
| &lt;     | Kisebb, mint                | X&lt;Y     |
| &gt;=    | Nagyobb vagy egyenlő | X&gt;=Y    |
| &lt;=    | Kisebb vagy egyenlő    | X&lt;=Y    |
| &lt;&gt; | Nem egyenlő             | X&lt;&gt;Y |

Ezenkívül használhat és-jelet (&) szövegösszefűző operátorként. Így egy vagy több szövegláncot összekapcsolhat vagy összefűzhet egyetlen szöveggé.

| Kezelő | Jelentés     | Példa                                             |
|----------|-------------|-----------------------------------------------------|
| &        | Összefűzés | „Nincs nyomtatnivaló” & ":&nbsp;" & „nem található rekord” |

##### <a name="operator-precedence"></a>Operátor elsőbbségi sorrend

Fontos a sorrend, amelyben az összetett kifejezés egy része kiértékelésre került. Például az **1 + 4 / 2** kifejezés eredménye attól függően változik, hogy az összeadás vagy az osztás művelet hajtódik-e végre először. A zárójelek segítségével megadhatja egy kifejezés kiértékelésének módját. Például, ha jelezni szeretné, hogy először a hozzáadás műveletet kell végrehajtani, így módosíthatja az előző kifejezést: **(1 + 4) / 2**. Ha a kifejezésben elvégzendő műveletek sorrendje nincs megadva explicit módon, akkor a a sorrend támogatott operátorokhoz rendelt alapértelmezett elsőbbségi sorrenden alapul. A következő táblázatok az egyes operátorokhoz rendelt elsőbbségi sorrendet jeleníti meg. A magasabb elsőbbségi sorrenddel (például 7) rendelkező operátorok az alacsonyabb elsőbbségi sorrenddel rendelkező operátorok előtt (például 1) kerülnek kiértékelésre.

| Elsőbbségi sorrend | Operátorok      | Szintaxis                                                                  |
|------------|----------------|-------------------------------------------------------------------------|
| 7          | Csoportosítás       | ( … )                                                                   |
| 6          | Tag hozzáférés  | … gombra. …                                                                   |
| 5          | Függvényhívás  | … ( … )                                                                 |
| 4          | Szorzás | … \* …<br>… / …                                                         |
| 3          | Additív       | … + …<br>… - …                                                          |
| 2          | Összehasonlítás     | … &lt; …<br>… &lt;= …<br>… =&gt; …<br>… &gt; …<br>… = …<br>… &lt;&gt; … |
| 1          | Kiválasztás     | … , …                                                                   |

Ha egy kifejezés olyan több egymást követő operátort tartalmaz, amelyek ugyanolyan elsőbbséget élveznek, akkor ezen műveletek kiértékelése balról jobbra történik. Például az **1 + 6 / 2 \* 3 &gt; 5** kifejezés az **igaz** értéket adja vissza. Ajánlatos a zárójelek használata a kifejezésekben található műveletek kívánt sorrendjének explicit módon történő jelzéséhez, illetve a kifejezések könnyebb olvasása és kezelése érdekében.

#### <a name="references"></a>Hivatkozások

Egy kifejezés tervezése során elérhető jelenlegi ER komponens összes adatforrását elnevezett hivatkozásként lehet használni. (Az aktuális ER-összetevő modell vagy formátum lehet.) Például az aktuális ER-adatmodell tartalmazza a **ReportingDate** adatforrást, és ez az adatforrás visszaad egy értéket a **DATETIME** adattípushoz. Annak érdekében, hogy a létrejövő dokumentumban megfelelően formázott értéket kapjon, a következőképpen hivatkozhat a kifejezésben szereplő adatforrásokra: : **DATETIMEFORMAT (ReportingDate, "nn-hh-éééé")**

Az adatforrásra hivatkozó minden név minden olyan karaktere előtt, amely nem az ábécé egy betűjét jelöli, egyszeres idézőjelet (') kell használni. A hivatkozási adatforrás minden nevének, amely tartalmaz legalább egy szimbólumot, amely nem az ábécé egy betűjét jelenti, egyszeres idézőjelekben kell megjelennie. (Ezek a nem alfabetikus szimbólumok lehetnek például írásjelek vagy más írott szimbólumok.) Íme néhány példa:

- A **Mai dátum és idő** adatforrást a következőképpen kell hivatkozni egy ER kifejezésben: **Mai dátum és idő”**.
- A **Vevők** adatforrás **név()** metódusát a következőképp kell hivatkozni az ER kifejezésben: **Vevők.'név()'**

Ha az alkalmazás-adatforrásainak metódusai paraméterekkel rendelkeznek, a következő szintaxist kell használni ezen metódusok meghívásához:

- Ha a **Rendszer** adatforrás **isLanguageRTL** metódusa rendelkezik egy **karakterlánc** adattípusú **EN-US** paraméterrel, erre a metódusra a következő módon kell hivatkozni az ER-kifejezésekben: **System.'isLanguageRTL'("EN-US")**.
- Az idézőjelek nem kötelezőek, ha egy metódus neve csak alfanumerikus szimbólumokat tartalmaz. Az olyan táblametódusok esetén viszont kötelezőek, amikor a név zárójeleket tartalmaz.

Amikor a **Rendszer** adatforrás hozzá van adva egy ER-hozzárendeléshez, amelyik a **globális** alkalmazásosztályra hivatkozik, a kifejezés a **HAMIS** logikai értéket adja vissza. A módosított **System.' isLanguageRTL'("AR")** kifejezés az **IGAZ** logikai értéket adja vissza.

Az ilyen típusú metódusok paramétereinek átadott értékek átadásának módja korlátozható:

- Csak állandók adhatók át ilyen típusú metódusoknak. Az állandók értékeit a tervezés során kell meghatározni.
- Az ilyen típusú paraméterekhez csak egyszerű (alap) adattípusok támogatottak. (Az egyszerű adattípusok: egész, valós, logikai, karakterlánc stb.)

#### <a name="paths"></a>Útvonalak

Amikor a kifejezés egy adatforrásra hivatkozik, az útvonal meghatározása segítségével kiválaszthatja az adatforrás egy megadott egyszerű elemének kiválasztásához. A pont karaktert (.) a strukturált adatforrás egyes elemeinek elkülönítésére használják. Például az aktuális ER adatmodell tartalmazza a **InvoiceTransactions** adatforrást, és ez az adatforrás rekordok listáját adja vissza. Az **InvoiceTransactions** rekordszerkezete tartalmazza az **AmountDebit** és **AmountCredit** mezőket, amelyek mindegyike numerikus értékeket ad vissza. Ezért a számlázott összeg kiszámítása érdekében a következő kifejezést tervezheti meg: **InvoiceTransactions.AmountDebit - InvoiceTransactions.AmountCredit**.

#### <a name="functions"></a>Funkciók

A következő témakör az ER kifejezésekben használható funkciókat mutatja be. A kifejezéskörnyezet (aktuális ER adatmodell vagy ER formátum) minden adatforrása használható függvénymeghívási paraméterként a függvénymeghívási argumentumok listájával összhangban. Az állandók szintén használhatók függvények meghívásának paraméterként. Például az aktuális ER adatmodell tartalmazza a **InvoiceTransactions** adatforrást, és ez az adatforrás rekordok listáját adja vissza. Az **InvoiceTransactions** rekordszerkezete tartalmazza az **AmountDebit** és **AmountCredit** mezőket, amelyek mindegyike numerikus értékeket ad vissza. Ezért a számlázott összeg kiszámításához, megtervezheti azokat a következő kifejezéseket, amelyek az ER kerekítési funkciót használják: **ROUND (InvoiceTransactions.AmountDebit - InvoiceTransactions.AmountCredit, 2)**.

## <a name="supported-functions"></a>Támogatott függvények

Az alábbi táblázatok bemutatják azokat az adatkezelő függvényeket, amelyeket az ER adat modellek és ER jelentések tervezéséhez használhat. A funkciók listája nem kötött. A fejlesztők bővíthetik. A használható funkciók listájának megtekintéséhez nyissa meg a funkciók ablakot az ER képletszerkesztőben.

### <a name="date-and-time-functions"></a>Dátum és idő függvények

| Funkció | Leírás | Példa |
|----------|-------------|---------|
| NAPOKHOZZÁADÁSA (dátum és idő, napok) | Adja hozzá a napok meghatározott számát a meghatározott dátum/idő értékhez. | **(MOST() 7) NAPOKHOZZÁADÁSA** megjeleníti a dátum és idő hét napot a jövőben. |
| DATETODATETIME (dátum) | A megadott dátumérték átalakítása egy dátum/idő értékre. | **DATETODATETIME (CompInfo. 'getCurrentDate()')** az aktuális Finance and Operations munkamenet dátumát, 2015. december 24-et, a következő módon adja vissza: **12/24/2015 12:00:00 AM**. Ebben a példában a **CompInfo** a **Finance and Operations/Tábla** típus ER-adatforrása, és a CompanyInfo táblára hivatkozik. |
| MOST () | A jelenlegi alkalmazáskiszolgáló dátumát és időpontját dátum/idő értékként jeleníti meg. | |
| Ma () | A jelenlegi alkalmazáskiszolgáló dátumát dátum értékként jeleníti meg. | |
| NULLDATE () | **Nulla** dátumértéket jelenik meg. | |
| NULLDATETIME () | **Null** dátum/idő értéket ad vissza. | |
| DATETIMEFORMAT (dátum és idő, a formátum) | A megadott dátum/idő értéket a megadott formátumban karakterlánccá alakítja. (A támogatott formátumokkal kapcsolatos további tudnivalókat lásd: [szokásos](https://msdn.microsoft.com/library/az4se3k1(v=vs.110).aspx) és [egyéni](https://msdn.microsoft.com/library/8kb3ddd4(v=vs.110).aspx).) | **DATETIMEFORMAT (NOW(), „nn-hh-éééé”)** a jelenlegi alkalmazáskiszolgáló dátumát, 2015. december 24-et adja vissza, **24-12-2015** formában, a megadott egyéni formátum szerint. |
| DATETIMEFORMAT (dátum és idő, formátum, kultúra) | A megadott dátum/idő értéket a megadott formátumban szereplő karakterlánccá és [kultúra](https://msdn.microsoft.com/goglobal/bb896001.aspx) lehetőséggé alakítja. (A támogatott formátumokkal kapcsolatos további tudnivalókat lásd: [szokásos](https://msdn.microsoft.com/library/az4se3k1(v=vs.110).aspx) és [egyéni](https://msdn.microsoft.com/library/8kb3ddd4(v=vs.110).aspx).) | A **DATETIMEFORMAT (NOW(), "d", "de")** a jelenlegi alkalmazáskiszolgáló dátumát (2015. december 24.) a kiválasztott német területi beállítások szerint (**"24.12.2015"**) adja vissza. |
| SESSIONTODAY () | A jelenlegi alkalmazás-munkamenet dátumát dátum értékként jeleníti meg. | |
| SESSIONNOW () | A jelenlegi alkalmazás-munkamenet dátumát és időpontját dátum/idő értékként jeleníti meg. | |
| DATEFORMAT (dátum, formátum) | A megadott dátumot karakterlánc formájában adja vissza a megadott formátumban. | **DATEFORMAT (SESSIONTODAY (), "nn-hh-éééé")** a jelenlegi alkalmazás-munkamenet dátumát, 2015. december 24-et adja vissza, **24-12-2015** formában, a megadott egyéni formátum szerint. |
| DATEFORMAT (dátum, formátum, területi beállítások) | Alakítsa a megadott dátumértéket a megadott formátumban és [területi beállításoknak](https://msdn.microsoft.com/goglobal/bb896001.aspx) megfelelő karakterlánccá. (A támogatott formátumokkal kapcsolatos további tudnivalókat lásd: [szokásos](https://msdn.microsoft.com/library/az4se3k1(v=vs.110).aspx) és [egyéni](https://msdn.microsoft.com/library/8kb3ddd4(v=vs.110).aspx).) | A **DATETIMEFORMAT (SESSIONNOW(), "d", "de")** a jelenlegi alkalmazás-munkamenet dátumát (2015. december 24.) a kiválasztott német területi beállítások szerint (**"24.12.2015"**) adja vissza. |
| DAYOFYEAR (dátum) | Január 1. és a megadott dátum közötti napok számát adja vissza egész szám formátumban. | **DAYOFYEAR (DATEVALUE ("01-03-2016", "dd-MM-yyyy"))** a **61** értéket adja vissza. **DAYOFYEAR (DATEVALUE ("01-01-2016", "dd-MM-yyyy"))** a **1** értéket adja vissza. |
| DAYS (1. dátum, 2. dátum) | Az első megadott dátum és a második megadott dátum közötti napok számát adja vissza. Pozitív értéket ad vissza, ha az első dátum későbbi, mint a második dátum, **0**-t (nullát) ad vissza, ha az első dátum megegyezik a második dátummal, vagy pedig negatív értéket ad vissza, ha az első dátum korábbi a második dátumnál. | A **DAYS (TODAY (), DATEVALUE( DATETIMEFORMAT( ADDDAYS(NOW(), 1), "ééééHHnn"), "ééééHHnn"))** **-1**-et ad vissza. |

### <a name="data-conversion-functions"></a>Adatkonvertálási függvények

| Funkció | Leírás | Példa |
|----------|-------------|---------|
| DATETODATETIME (dátum) | A megadott dátumérték átalakítása egy dátum/idő értékre. | **DATETODATETIME (CompInfo. 'getCurrentDate()')** az aktuális Finance and Operations munkamenet dátumát, 2015. december 24-et, a következő módon adja vissza: **12/24/2015 12:00:00 AM**. Ebben a példában a **CompInfo** a **Finance and Operations/Tábla** típus ER-adatforrása, és a CompanyInfo táblára hivatkozik. |
| DATEVALUE (karakterlánc, formátum) | A megadott karakterláncot dátum formájában adja vissza a megadott formátumban. | **DATEVALUE ("21-Dec-2016", "dd-MMM-yyyy")** a 2016. december 21. dátumot adja vissza a megadott egyéni formátum szerint, az alapértelmezett alkalmazás **EN-US** területi beállításai szerint. |
| DATEVALUE (karakterlánc, formátum, területi beállítások) | A megadott karakterláncot dátum formájában adja vissza a megadott formátum és területi beállítások alapján. | A **DATEVALUE ("21-Gen-2016", "dd-MMM-yyyy", "IT")** a 2016. január 21. dátumot a megadott egyéni formátum és területi beállítások alapján adja vissza. A **DATEVALUE ("21-Gen-2016", "dd-MMM-yyyy", "EN-US")** viszont kivételt eredményez, és a felhasználó értesül, hogy a megadott karakterlánc nem ismerhető fel érvényes dátumként. |
| DATETIMEVALUE (karakterlánc, formátum) | A megadott karakterláncot dátum/idő formájában adja vissza a megadott formátumban. | A **DATETIMEVALUE ("21-Dec-2016 02:55:00", "nn-HHH-éééé óó:pp:ss")** 2016. december 21. 02:55:00-t ad vissza a megadott egyéni formátum alapján, az alapértelmezett alkalmazás **EN-US** területi beállításai szerint. |
| DATETIMEVALUE (karakterlánc, formátum, területi beállítások) | A megadott karakterláncot dátum/idő formájában adja vissza a megadott formátum és területi beállítások alapján. | A **DATETIMEVALUE ("21-Gen-2016 02:55:00", "nn-HHH-éééé óó:pp:ss", "IT")** 2016. december 21. 02:55:00-t ad vissza a megadott egyéni formátum alapján, az alapértelmezett egyéni formátum és területi beállítások szerint. A **DATETIMEVALUE ("21-Gen-2016 02:55:00", "dd-MMM-yyyy óó:pp:ss", "EN-US")** viszont kivételt eredményez, és a felhasználó értesül, hogy a megadott karakterlánc nem ismerhető fel érvényes dátumként. |

### <a name="list-functions"></a>Lista függvények

<table>
<thead>
<tr>
<th>Funkció</th>
<th>Leírás</th>
<th>Példa</th>
</tr>
</thead>
<tbody>
<tr>
<td>MEGOSZTÁS (bejövő, hossza)</td>
<td>A megadott bemeneti karakterlánc felosztása a részkarakterláncokban, amelyek mindegyike megadott időtartammal rendelkezik. Új listaként jeleníti meg az eredményt.</td>
<td>A <strong>SPLIT (&quot;abcd&quot;, 3)</strong> két rekordot tartalmazó új listát jelenít meg, amelyek <strong>KARAKTERLÁNC</strong> mezővel rendelkeznek.. Az első rekordban szereplő mező <strong>&quot;abc&quot;</strong> szöveget tartalmaz és a második rekordban szereplő mező <strong>&quot;d&quot;</strong> betűt tartalmaz.</td>
</tr>
<tr>
<td>SPLIT (bejövő, elválasztó)</td>
<td>A megadott bemeneti karakterlánc felosztása a részkarakterláncokban, megadott elválasztó alapján.</td>
<td><strong>A SPLIT (&quot;XAb aBy&quot;, &quot;aB&quot;)</strong> három rekordot tartalmazó új listát jelenít meg, amelyek <strong>STRING</strong> mezővel rendelkeznek.. Az első rekordra a mező a szöveg <strong>&quot;X&quot;</strong>, a második bejegyzést a mezőben a szöveg &quot;&nbsp;&quot;, míg a harmadik bejegyzés a mező a szöveg <strong>&quot;y&quot;</strong>. Ha üres az elválasztó, egy új listát ad vissza, amely egy rekordból áll, amelynek van egy <strong>STRING</strong> mezője, amely tartalmazza a beviteli mezőt. Ha a bevitel üres, akkor egy új, üres listát ad vissza.
Ha a bejövő vagy az elválasztó nincs megadva (null), alkalmazáskivétel történik.</td>
</tr>
<tr>
<td>FELOSZTÁSLISTA (lista, szám)</td>
<td>A megadott listát kötegekké osztja fel, amelynek mindegyike megadott számú rekordot tartalmaz. A kötegek új listájaként jeleníti meg az eredményt, amely a következő elemeket tartalmazza:
<ul>
<li>Kötegek, mint normál listák (<strong>Érték </strong>összetevő)</li>
<li>Az aktuális köteg száma (<strong>BatchNumber</strong> összetevő)</li>
</ul>
</td>
<td>Az alábbi példában egy <strong>Sorok</strong> adatforrás jön létre három rekord rekordlistájaként. Ez a kötegekre tételekre oszlik, amelyek mindegyike legfeljebb két rekordot tartalmaz.
<p><a href="./media/picture-splitlist-datasource.jpg"><img src="./media/picture-splitlist-datasource.jpg" alt="Data source that is divided into batches" class="alignnone wp-image-290681 size-full" width="397" height="136" /></a></p>
<p>Az alábbi ábrán a tervezett formátumelrendezés látható. Ebben a formátumelrendezésben a <strong>Sorok</strong> adatforráshoz kötések jönnek létre a kimenet XML-formátumú előállításához. Ez a kimenet minden egyes kötethez és a hozzá tartozó rekordokhoz egyedi csomópontokat tartalmaz.</p>
<p><a href="./media/picture-splitlist-format.jpg"><img src="./media/picture-splitlist-format.jpg" alt="Format layout that has bindings to a data source" class="alignnone wp-image-290691 size-full" width="374" height="161" /></a></p>
<p>Az alábbi ábrán a tervezett formátum futtatásának eredménye látható.</p>
<a href="./media/picture-splitlist-result.jpg"><img src="./media/picture-splitlist-result.jpg" alt="Result of running the format" class="alignnone wp-image-290701 size-full" width="358" height="191" /></a>
</td>
</tr>
<tr>
<td>LIST (1. rekord [, 2. rekord...])</td>
<td>A megadott argumentumokból létrehozott új listát jelenítik meg.</td>
<td><strong>LISTA (modell. MainData, modell. OtherData)</strong> egy üres sort jelenít meg, ahol a mezők listája a <strong>MainData</strong> és <strong>OtherData</strong> rekord lista összes mezőjét tartalmazza.</td>
</tr>
<tr>
<td>LISTJOIN (1. lista, 2. lista, ...)</td>
<td>A megadott argumentumok listájából létrehozott csatolt listát jelenítik meg.</td>
<td>A <strong>LISTJOIN (SPLIT (&quot;abc&quot;, 1), SPLIT (&quot;def&quot;, 1))</strong> hat rekord listáját adja vissza, ahol a <strong>KARAKTERLÁNC</strong> adattípusú egy mezője egyedüli betűket tartalmaz.</td>
</tr>
<tr>
<td>ISEMPTY (lista)</td>
<td><strong>IGAZ</strong> értéket ad vissza, ha a megadott lista nem tartalmaz elemeket. Ellenkező esetben <strong>HAMIS</strong> választ jelenít meg.</td>
<td></td>
</tr>
<tr>
<td>EMPTYLIST (lista)</td>
<td>A megadott lista segítségével egy üres listát jelenít meg a lista szerkezetére vonatkozó forrásként.</td>
<td>Az <strong>EMPTYLIST (SPLIT (&quot;abc&quot;, 1))</strong> egy új üres listát ad vissza, amelynek ugyanolyan szerkezete van, mint a <strong>SPLIT</strong> funkció által megjelenített listának.</td>
</tr>
<tr>
<td>ELSŐ (lista)</td>
<td>A megadott lista első rekordját akkor jeleníti meg, ha a rekord nem üres. Ellenkező esetben egy kivételt jelenít meg.</td>
<td></td>
</tr>
<tr>
<td>FIRSTORNULL (lista)</td>
<td>A megadott lista első rekordját akkor jeleníti meg, ha a rekord nem üres. Ellenkező esetben egy <strong>null</strong> rekordot jelenít meg.</td>
<td></td>
</tr>
<tr>
<td>LISTOFFIRSTITEM (lista)</td>
<td>Olyan listát jelenít meg, amely csak a megadott lista első elemét tartalmazza.</td>
<td></td>
</tr>
<tr>
<td>ALLITEMS (útvonal)</td>
<td>Ez a funkció a memóriában lévő kiválasztásként fut. Új, összevont listát jelenít meg, amely a meghatározott elérési útnak megfelelő összes elemet tartalmazza. Az elérési utat egy érvényes adatforrás útvonalaként kell megadni a rekordlista adattípus adatforrásához. Adatelemek (például elérési út karakterlánc, dátum) hibaüzenetet jelenítenek meg az ER kifejezésszerkesztőben tervezéskor.</td>
<td>Ha adatforrásként <strong>SPLIT(&quot;abcdef&quot; , 2)</strong> értéket ad meg (DS), a <strong>COUNT( ALLITEMS (DS.Value))</strong> által visszaadott érték <strong>3</strong>.</td>
</tr>
<tr>
<td>ALLITEMSQUERY (útvonal)</td>
<td>Ez a funkció illesztett SQL-lekérdezésként fut. Új, összevont listát jelenít meg, amely a meghatározott elérési útnak megfelelő összes elemet tartalmazza. A megadott elérési utat egy érvényes adatforrás útvonalaként kell megadni a rekordlista adattípus adatforrásához, és tartalmaznia kell legalább egy objektumkapcsolatot. Adatelemek (például elérési út karakterlánc, dátum) hibaüzenetet jelenítenek meg az ER kifejezésszerkesztőben tervezéskor.</td>
<td>A következő adatforrás megadása a modell-hozzárendelésben:
<ul>
<li><strong>CustInv</strong> (<strong>Táblarekordok</strong> típus), amelyre vonatkozik a CustInvoiceTable táblára</li> 
<li><strong>FilteredInv</strong> (<strong>Számított mező</strong> típus), amely ezt a kifejezést tartalmazza: <strong>FILTER (CustInv, CustInv.InvoiceAccount = &quot;USA-001-&quot;)</strong></li>
<li><strong>JourLines</strong> (<strong>Számított mező</strong> típus), amely ezt a kifejezést tartalmazza: <strong>ALLITEMSQUERY (FilteredInv.'&lt;Relations'.CustInvoiceJour.'&lt;Relations'.CustInvoiceTrans)</strong></li>
</ul>
<p>A modell leképezés futtatásakor meghívni a <strong>JourLines</strong> adatforrást, a következő SQL-utasítás futtassa történik:</p>
SELECT ... FROM CUSTINVOICETABLE T1 CROSS JOIN CUSTINVOICEJOUR T2 CROSS JOIN CUSTINVOICETRANS T3 WHERE...
</td>
</tr>
<tr>
<td>RENDEZÉS (lista [1 kifejezés, 2 kifejezés, ...])</td>
<td>Visszaadja meg a megadott listát, miután rendezte a megadott argumentumok szerint. Ezek az argumentumok kifejezésként adhatók meg.</td>
<td>Ha a <strong>Szállító </strong> a VendTable táblára hivatkozó ER adatforrásként van konfigurálva, akkor az <strong>ORDERBY (Vendors, Vendors.'name()')</strong> név szerinti növekvő sorrendben rendezve adja vissza a szállítók listáját.</td>
</tr>
<tr>
<td>SZTORNÍROZÁS (lista)</td>
<td>A megadott listát a sztornírozott rendezési sorrendben jeleníti meg.</td>
<td>Ha a <strong>Szállító</strong> a VendTable táblára hivatkozó ER adatforrásként van konfigurálva, akkor a <strong>REVERSE (ORDERBY (Szállítók, Szállítók.'name()')) )</strong> név szerinti növekvő sorrendben rendezve adja vissza a szállítók listáját.</td>
</tr>
<tr>
<td>HOL (lista, feltétel)</td>
<td>Visszaadja meg a megadott listát, miután szűrte a megadott feltételek szerint. A megadott feltétel a memóriában lévő listára kerül. Így a <strong>WHERE</strong> függvény más, mint a <strong>FILTER</strong> függvény.</td>
<td>Ha a <strong>Szállító</strong> a VendTable táblára hivatkozó ER adatforrásként van konfigurálva, akkor a <strong>WHERE(Szállítók, Szállítók.VendGroup = &quot;40&quot;)</strong> csak a 40-es szállítócsoporthoz tartozó szállítók listáját adja vissza.</td>
</tr>
<tr>
<td>ENUMERÁLÁS (lista)</td>
<td>A megadott lista enumerált rekordjait tartalmazó és a következő elemeket megjelenítő új listáját jeleníti meg:
<ul>
<li>A megadott lista rekordjai rendszeres listákként (<strong>Érték </strong>összetevő)</li>
<li>Az aktuális rekord index (<strong>Szám </strong>összetevő)</li>
</ul>
</td>
<td>A következő ábrán az <strong>Sorszámozott</strong> adatforrás a szállítói rekordok sorszámozott listájaként jött létre a <strong>Szállítók</strong> adatforrásból, amely a VendTable táblára hivatkozik.
<p><a href="./media/picture-enumerate-datasource.jpg"><img src="./media/picture-enumerate-datasource.jpg" alt="Enumerated data source" class="alignnone wp-image-290711 size-full" width="387" height="136" /></a></p>
<p>Az alábbi ábra bemutatja a formátumot. Ebben a formátumelrendezésben adatkötések jönnek létre a kimenet XML-formátumú előállításához. A kimenet az egyes szállítókat sorszámozott csomópontként jeleníti meg.</p>
<p><a href="./media/picture-enumerate-format.jpg"><img src="./media/picture-enumerate-format.jpg" alt="Format that has data bindings" class="alignnone wp-image-290721 size-full" width="414" height="138" /></a></p>
<p>Az alábbi ábrán a tervezett formátum futtatásának eredménye látható.</p>
<a href="./media/picture-enumerate-result.jpg"><img src="./media/picture-enumerate-result.jpg" alt="Result of running the format" class="alignnone wp-image-290731 size-full" width="567" height="176" /></a>
</td>
</tr>
<tr>
<td>SZÁMLÁLÓ (lista)</td>
<td>A megadott listában szereplő rekordok számát jeleníti meg, ha a rekord nem üres. Ellenkező esetben <strong>0</strong> (zero) választ jelenít meg.</td>
<td>A <strong>COUNT (SPLIT(&quot;abcd&quot; , 3))</strong> <strong>2</strong> értéket jelenít meg, mert a <strong>SPLIT</strong> funkció két rekordot tartalmazó listát hoz létre.</td>
</tr>
<tr>
<td>LISTOFFIELDS (útvonal)</td>
<td>A következő argumentumok valamelyikéből létrehozott rekordlistát ad vissza:
<ul>
<li>Modellfelsorolás</li>
<li>Formátumok felsorolása</li>
<li>Konténer</li>
</ul>
<p>A létrehozott lista olyan rekordokból áll, amelyek a következő mezőket tartalmazzák:</p>
<ul>
<li>Név</li>
<li>Címke</li>
<li>Leírás</li>
</ul>
A <strong>Név</strong> és a <strong>Címke</strong> mezőben futásidejű értékek jelennek meg a formátum nyelvi beállításaitól függően.
</td>
<td>A következő ábra az adatmodellbe bevezetett sorszámozást mutatja be.
<p><a href="./media/ger-listoffields-function-model-enumeration.png"><img src="./media/ger-listoffields-function-model-enumeration-e1474545790761.png" alt="Enumeration in a model" class="alignnone wp-image-1203943 size-full" width="514" height="155" /></a></p>
<p>A következő ábrán ezek a részletek láthatók:</p>
<ul>
<li>A modell felsorolása adatforrásként kerül be egy jelentésbe.</li>
<li>Az ER kifejezés a modellfelsorolást a <strong>LISTOFFIELDS</strong> függvény paramétereként használja.</li>
<li>A rekordlistatípus adatforrása beillesztésre kerülegy jelentésbe a létrehozott ER kifejezés használatával.</li>
</ul>
<p><a href="./media/ger-listoffields-function-in-format-expression.png"><img src="./media/ger-listoffields-function-in-format-expression-e1474546110395.png" alt="Format" class="alignnone wp-image-1204033 size-full" width="549" height="318" /></a></p>
<p>A következő példa azokat az ER formázási elemeket mutat be, amelyek ahhoz a rekordlistatípus-adatforráshoz vannak kötve, amelyet a <strong>LISTOFFIELDS</strong> függvénnyel hoztak létre.</p>
<p><a href="./media/ger-listoffields-function-format-design.png"><img src="./media/ger-listoffields-function-format-design.png" alt="Format design" class="alignnone size-full wp-image-1204043" width="466" height="221" /></a></p>
<p>Az alábbi ábrán a tervezett formátum futtatásának eredménye látható.</p>
<p><a href="./media/ger-listoffields-function-format-output.png"><img src="./media/ger-listoffields-function-format-output.png" alt="Format output" class="alignnone size-full wp-image-1204053" width="585" height="158" /></a></p>
<blockquote>[!NOTE] A címkék és leírások fordított szövege az ER formátumú kimenetbe kerül bevitelre, a szülő FILE és FOLDER formátumelemekhez konfigurált nyelvi beállításainak megfelelően.</blockquote>
</td>
</tr>
<tr>
<td>LISTOFFIELDS (elérési út, nyelv)</td>
<td>Egy argumentumból, például modellfelsorolásból, egy formátumfelsorolásból vagy tárolóból létrehozott rekordlistát ad vissza. A létrehozott lista olyan rekordokból áll, amelyek a következő mezőket tartalmazzák:
<ul>
<li>Név</li>
<li>Címke</li>
<li>Leírás</li>
<li>Lefordítva</li>
</ul>
A <strong>Név</strong> és a <strong>Címke</strong> mezőben futásidejű értékek jelennek meg a formátum nyelvi beállításaitól és a megadott nyelvtől függően. A <strong>Lefordítva</strong> mező azt jelzi, hogy a <strong>Címke</strong> mezőt lefordították a megadott nyelvre.
</td>
<td>Használhatja például a <strong>Számított mező</strong> adatforrástípust az <strong>enumType_de</strong> és <strong>enumType_deCH</strong> adatforrások az <strong>enumType</strong> adatokmodell-felsoroláshoz való konfigurálására.
<ul>
<li>enumType_de = <strong>LISTOFFIELDS</strong> (enumType, &quot;de&quot;)</li>
<li>enumType_deCH = <strong>LISTOFFIELDS</strong> (enumType, &quot;de-CH&quot;)</li>
</ul>
<p>Ebben az esetben a következő kifejezést használhatja a felsorolási érték címkéjének svájci német nyelven történő lekéréséhez, ha ez a fordítás elérhető. Ha a svájci német fordítás nem érhető el, a címke németül szerepel.</p>
IF (NOT (enumType_deCH.IsTranslated), enumType_de.Label, enumType_deCH.Label)
</td>
</tr>
<tr>
<td>STRINGJOIN (lista, mezőnév, elválasztó)</td>
<td>Visszaad egy olyan karakterláncot, amely a megadott lista megadott mezőjének összefűzött értékeiből áll. Az értékeket a megadott elválasztó választja el egymástól.</td>
<td>Ha ezt adja meg: <strong>SPLIT(&quot;abc&quot; , 1)</strong> adatforrásként (DS), a  <strong>STRINGJOIN (DS, DS.Value, &quot;-&quot;)</strong> ezt adja vissza: <strong>&quot;a-b-c&quot;</strong>.</td>
</tr>
<tr>
<td>SPLITLISTBYLIMIT (lista, határérték, korlát forrása)</td>
<td>A megadott listát új, részleges listákból álló listává osztja fel, és a rekordlista tartalmának eredményét adja vissza. A <strong>korlátérték</strong> paramétere az eredeti lista felosztása korlátjának értékét határozza meg. A <strong>korlát forrásának</strong> paramétere a teljes összeg növelésének lépését határozza meg. A rendszer nem használja a korlátot az eredeti lista egyetlen eleménél, amikor a korlát forrása meghaladja a meghatározott határértéket.</td>
<td>Az alábbi ábra bemutatja a formátumot. 
<p><a href="./media/ger-splitlistbylimit-format.png"><img src="./media/ger-splitlistbylimit-format.png" alt="Format" class="alignnone size-full wp-image-1204063" width="396" height="195" /></a></p>
<p>Az alábbi ábrákon láthatók az adatforrások, amelyek használatosak a formátumhoz.</p>
<p><a href="./media/ger-splitlistbylimit-datasources.png"><img src="./media/ger-splitlistbylimit-datasources.png" alt="Data sources" class="alignnone size-full wp-image-1204073" width="320" height="208" /></a></p>
<p>Az alábbi ábrán a formátum futtatásának eredménye látható. Ebben az esetben a kimenet egy egyszerű lista árucikkekről.</p>
<p><a href="./media/ger-splitlistbylimit-output.png"><img src="./media/ger-splitlistbylimit-output.png" alt="Output" class="alignnone size-full wp-image-1204083" width="462" height="204" /></a></p>
<p>A következő ábrákon ugyanezt a formázást módosítottuk, hogy az árucikkcsoportok listáját kötegekben mutassa be, amikor egy-egy kötegnek árucikkeket kell tartalmaznia, és a teljes súly nem haladhatja meg a 9-es határértéket.</p>
<p><a href="./media/ger-splitlistbylimit-format-1.png"><img src="./media/ger-splitlistbylimit-format-1.png" alt="Adjusted format" class="alignnone size-full wp-image-1204103" width="466" height="438" /></a></p>
<p><a href="./media/ger-splitlistbylimit-datasources-1.png"><img src="./media/ger-splitlistbylimit-datasources-1.png" alt="Data sources for the adjusted format" class="alignnone size-full wp-image-1204093" width="645" height="507" /></a></p>
<p>Az alábbi ábrán a módosított formátum futtatásának eredménye látható.</p>
<p><a href="./media/ger-splitlistbylimit-output-1.png"><img src="./media/ger-splitlistbylimit-output-1.png" alt="Output of the adjusted format" class="alignnone size-full wp-image-1204113" width="676" height="611" /></a></p>
<blockquote>[!NOTE] A korlát nem vonatkozik az eredeti lista utolsó elemére, mivel a korlát forrásának (súly) értéke (11) meghaladja a meghatározott határértéket (9). Használja a megfelelő formátumelem <strong>WHERE</strong> függvényét vagy az <strong>Enabled</strong> kifejezést a részleges listák figyelmen kívül hagyásához (átugrásához) a jelentés előállítása során, ha szükséges.</blockquote>
</td>
</tr>
<tr>
<td>FILTER (lista, feltétel)</td>
<td>Visszaadja meg a megadott listát, miután a lekérdezést módosította és szűrte a megadott feltételek szerint. Ez a függvény eltér a <strong>WHERE</strong> függvénytől, mivel a megadott feltétel az adatbázis szintjén kerül alkalmazásra a <strong>Táblarekordok</strong> típus bármely ER adatforrására. A lista és a feltétel táblák és kapcsolatok segítségével határozhatók meg.</td>
<td>Ha a <strong>Szállító</strong> a VendTable táblára hivatkozó ER adatforrásként van konfigurálva, akkor a <strong>FILTER(Szállítók, Szállítók.VendGroup = &quot;40&quot;)</strong> csak a 40-es szállítócsoporthoz tartozó szállítók listáját adja vissza. Ha a <strong>Szállító</strong> ER-adatforrásként van konfigurálva, amely a VendTable táblára és ha a <strong>parmVendorBankGroup</strong>-ra hivatkozik, amely ER-adatforrásként konfigurálva az értéket <strong>karakterlánc</strong> adattípusként adja vissza, a <strong>FILTER (Vendor.'&lt;Relations'.VendBankAccount, Vendor.'&lt;Relations'.VendBankAccount.BankGroupID = parmVendorBankGroup)</strong> csak az adott bankcsoporthoz tartozó szállítói számlák listáját adja vissza.</td>
</tr>
<tr>
<td>INDEX (lista, index)</td>
<td>Ez a funkció egy megadott numerikus index által kiválasztott rekordot ad vissza a listában. Kivétel történik, ha az index kívül esik a listán szereplő rekordok tartományán.</td>
<td>Ha megadja a <strong>DS</strong> adatforrást a <strong>Számított mező</strong> típushoz és az tartalmazza a <strong>SPLIT ("A|B|C", “|”), 2</strong> kifejezést, a <strong>DS.Value</strong> kifejezés a „B” szöveges értéket adja vissza. Az <strong>INDEX (SPLIT ("A|B|C", “|”), 2).Value</strong> kifejezés szintén a „B” szövegértéket adja vissza.</td>
</tr>
</tbody>
</table>

### <a name="logical-functions"></a>Logikai függvények

| Funkció | Leírás | Példa |
|----------|-------------|---------|
| CASE (kifejezés, 1. beállítás, 1. \[2. beállítás, 2. eredmény\] ... \[, alapértelmezett eredmény\]) | A megadott kifejezés értékének kiértékelése a megadott alternatív beállításokkal szemben. Megjeleníti a lehetőség eredményét, amely egyenlő a kifejezés eredményével. Ellenkező az opcionális alapértelmezett eredményt adja vissza, ha alapértelmezett eredmény meg van adva. (Az alapértelmezett eredmény az utolsó paraméter, amelyet nem előz meg egy lehetőség.) | **ESET (DATETIMEFORMAT (NOW(), „MM”), a „10”, „TÉLI”, „11”, „TÉLI”, „12”, „TÉLI”, „”)** **„TÉLI”** karakterláncot jelenít meg, amikor a jelenlegi alkalmazás-munkamenet dátuma október és december közötti. Ellenkező esetben üres karakterláncot jelenít meg. |
| HA (feltétel, 1 érték, 2 érték) | Az 1. megadott értéket adja vissza a megadott feltétel teljesülése esetén. Ellenkező esetben a második megadott értéket adja vissza. Ha az 1. érték és a 2. érték rekordok vagy rekordlistáják, az eredmény csak olyan mezőkkel rendelkezik, amelyek mindkét listában szerepelnek. | **HA (1 = 2, „feltétel teljesülése esetén”, „feltétel nem teljesül”)** **„feltétel nem teljesül”** karakterláncot jelenít meg. |
| NEM (feltétel) | Megjeleníti a megadott feltételek sztornírozott logikai értékét. | **NEM (IGAZ)** **HAMIS** értéket jelenít meg. |
| AND (1. feltétel\[, 2. feltétel, …\]) | **IGAZ** értéket jelenít meg, ha *minden* megadott feltétel igaz. Ellenkező esetben **HAMIS** választ jelenít meg. | **ÉS a (1 = 1, „a” = „a”)** **IGAZ** értéket jelenít meg. **ÉS a (1 = 2, „a” = „a”)** **HAMIS** értéket jelenít meg. |
| OR (1. feltétel\[, 2. feltétel, …\]) | **HAMIS** értéket jelenít meg, ha *minden* megadott feltétel hamis. **IGAZ** értéket jelenít meg, ha *bármely* megadott feltétel igaz. | **VAGY a (1 = 2, „a” = „a”)** **IGAZ** értéket jelenít meg. |
| VALUEIN (bejövő, lista, listaelem kifejezés) | Azt határozza meg, hogy a megadott bemenet megegyezik-e bármilyen értékkel a megadott lista valamelyik elemére. Az **IGAZ** értéket adja vissza, ha a megadott bemenet megfelel a megadott kifejezés legalább egy rekordhoz tartozó futtatásának az eredményének. Ellenkező esetben **HAMIS** választ jelenít meg. A **bemenet** paraméter az adatforrás elem elérési útját jelöli. Az elem értékét a rendszer megfelelteti. A **lista** paraméter egy rekord listatípusú adatforrás elem elérési útját határozza meg a kifejezést tartalmazó rekordok listájaként. Az elem értékét a program összehasonlítja a megadott bemenettel. A **listaelem kifejezés** argumentum egy kifejezést jelöl, amely a megadott lista egyetlen mezőjére mutat vagy azt tartalmazza, amely a megfeleltetéshez használandó. | Példákért lásd a [Példák: VALUEIN (bejövő, lista, listaelem kifejezés)](#examples-valuein-input-list-list-item-expression) következő szakaszt. |

#### <a name="examples-valuein-input-list-list-item-expression"></a>Példák: VALUEIN (bejövő, lista, listaelem kifejezés)
Általában a **VALUEIN** függvény **VAGY** feltételek egy csoportjára fordul le:

(input = list.item1.value) OR (input = list.item2.value) OR …

##### <a name="example-1"></a>1. példa
A modell-hozzárendelésben határozza meg a következő adatforrást: **Lista** (**számított mező** típus). Az adatforrás tartalmaz a kifejezést: **SPLIT ("a, b, c", ",")**.

Amikor egy adatforrás van meghívva, amely **VALUEIN ("B", List, List.Value)** kifejezéskén van konfigurálva, a rendszer az **IGAZ** értéket adja vissza. Ebben az esetben a **VALUEIN** függvény a következő feltételek csoportjára fordul le:

**(("B" = "a") vagy ("B" = "b") or ("B" = "c"))**, ahol **("B" = "b")** egyenlő **TRUE**

Amikor egy adatforrás van meghívva, amely **VALUEIN ("B", List, LEFT(List.Value, 0))** kifejezéskén van konfigurálva, a rendszer a **HAMIS** értéket adja vissza. Ebben az esetben a **VALUEIN** függvény a következő feltételre fordul le:

**("B" = "")**, amely nem azonos azzal, hogy **IGAZ**

Ne feledje, hogy az ilyen feltétel szövegében a karakterszám felső határa 32 768 karakter. Ezért ne hozzon létre olyan adatforrásokat, amelyek túlléphetik ezt a korlátot futásidőben. Ha túllépte a korlátot, az alkalmazás leáll, és kivételt küld. Például ez a helyzet akkor fordulhat elő, ha így van beállítva az adatforrás: **WHERE (List1, VALUEIN (List1.ID, List2, List2.ID)**, és a **List1** és **List2** listák nagy mennyiségű rekordot tartalmaznak.

Bizonyos esetekben a **VALUEIN** funkció egy adatbázis-kimutatásra fordul le az **EXISTS JOIN** operátor használatával. Ez a viselkedés akkor fordul elő, amikor a **FILTER** függvény használatos, és a következő feltételek teljesülnek:

- Az **ASK FOR QUERY** beállítás ki van kapcsolva az adatforrás **VALUEIN** függvényéhez, amely rekordok listájára hivatkozik. (További feltételek nem vonatkoznak erre az adatforrásra futásidőben.)
- Nincsenek konfigurálva beágyazott kifejezések az adatforrás **VALUEIN** függvényéhez, amely rekordok listájára hivatkozik.
- A **VALUEIN** függvény listaeleme a megadott adatforrás mezőjére (nem egy kifejezésre vagy metódusra) hivatkozik.

Fontolja meg ennek használatát a **WHERE** függvény helyett, ahogy ebben a példában korábban ismertettük.

##### <a name="example-2"></a>2. példa

A következő adatforrás megadása a modell-hozzárendelésben:

- **In** (**Táblarekordok** típus), amely az Intrastat táblára hivatkozik
- **Port** (**Táblarekordok** típus), amely az Intrastat táblára hivatkozik

Amikor adatforrás van meghívva, amely a **FILTER (In, VALUEIN(In.Port, Port, Port.PortId)** kifejezésben van beállítva, a következő SQL-utasítás generálódik, hogy az Intrastat tábla szűrt rekordjait adja vissza:

```
select … from Intrastat
exists join TableId from IntrastatPort
where IntrastatPort.PortId = Intrastat.Port
```

A **dataAreaId** mezőkhöz, a végső SQL-utasítás az **IN** operátor használatával van előállítva.

##### <a name="example-3"></a>3. példa

A következő adatforrás megadása a modell-hozzárendelésben:

- **Le** (**Számított mező** típus), amely a következő kifejezést tartalmazza: **SPLIT ("DEMF,GBSI,USMF", ",")**
- **In** (**Táblarekordok** típus), amely az Intrastat táblára hivatkozik, amelyhez a **Több vállalatot érintő** beállítás engedélyezve van

Amikor adatforrás van meghívva, amely a **FILTER (In, VALUEIN (In.dataAreaId, Le, Le.Value)** kifejezésben van beállítva, a végső SQL-utasítás tartalmazza a következő feltételt:

```
Intrastat.dataAreaId IN ('DEMF', 'GBSI', 'USMF')
```

### <a name="mathematical-functions"></a>Matematikai funkciók

| Funkció | Leírás | Példa |
|----------|-------------|---------|
| ABS (szám) | A megadott szám abszolút értékét adja vissza. (Más szóval, a számot előjel nélkül adja vissza.) | **ABS (-1)** **1** értéket jelenít meg. |
| TELJESÍTMÉNY (szám, teljesítmény) | A megadott pozitív szám megadott teljesítményre történő javításának eredményét jeleníti meg. | **TELJESÍTMÉNY (10, 2)** **100** értéket jelenít meg. |
| NUMBERVALUE (karakterlánc, tizedesjegy-elválasztó, számjegy csoportosítási elválasztó) | A megadott karakterlánc konvertálása egy számhoz. A megadott tizedeselválasztó a decimális szám egészszám- és a tizedestört-részei között használatos. A megadott számjegy csoportosítási elválasztó használatos az ezresek elválasztására. | **NUMBERVALUE ("1 234,56", ",","")** **1234,56** értéket jelenít meg. |
| ÉRTÉK (karakterlánc) | A megadott karakterlánc konvertálása egy számhoz. A vesszőket és a pont karaktereket (.) decimális elválasztóknak tekintik és a vezető kötőjelet (-) negatív jelként használjál. Kivételt ad, ha más nem numerikus karakterek találhatók a megadott karakterláncban. | **ÉRTÉK („1 234,56”)** megad egy kivételt. |
| KEREKÍTÉS (szám, tizedesjegyek) | A megadott számot adja vissza adott számú tizedesjegyre kerekítve:<ul><li>Ha a megadott **tizedesjegy**-paraméter értéke nagyobb, mint 0 (nulla) akkor a megadott szám a tizedesjegyek ezen megadott számára van kerekítve.</li><li>Ha a **tizedesjegy**-paraméter értéke **0** (nulla) értéket, a megadott szám a legközelebbi egészre van kerekítve.</li><li>Ha a **tizedesjegy**-paraméter értéke kisebb, mint 0 (nulla) akkor a megadott szám a tizedesjegyek bal oldalára van kerekítve.</li></ul> | **KEREKÍTÉS (1200,767, 2)** két tizedesjegyre kerekít és **1200,77** értéket jelenít meg. **KEREKÍTÉS (1200,767, -3)** az 1000 legközelebbi többszörösére kerekít és **1000** értéket jelenít meg. |
| LEKEREKÍTÉS (szám, tizedesjegyek) | A megadott számot adja vissza adott számú tizedesjegyre lefelé kerekítve.<blockquote>[!NOTE] Ez a függvény úgy viselkedik, mint a **ROUND**, de mindig lefelé (nulla felé) kerekíti a megadott számot.</blockquote> | **LEKEREKÍTÉS (1200,767, 2)** két tizedesjegyre kerekít le és **1200,76** értéket jelenít meg. **LEKEREKÍTÉS (1700,767, -3)** az 1000 legközelebbi többszörösére kerekít le és **1000** értéket jelenít meg. |
| FELKEREKÍTÉS (szám, tizedesjegyek) | A megadott számot adja vissza adott számú tizedesjegyre felfelé kerekítve.<blockquote>[!NOTE] Ez a függvény úgy viselkedik, mint a **ROUND**, de mindig felfelé (nullával ellenkező irányba) kerekíti a megadott számot.</blockquote> | **FELKEREKÍTÉS (1200,763, 2)** két tizedesjegyre kerekít fel és **1200,77** értéket jelenít meg. **FELKEREKÍTÉS (1200,767, -3)** az 1000 legközelebbi többszörösére kerekít fel és **2000** értéket jelenít meg. |

### <a name="data-conversion-functions"></a>Adatkonvertálási függvények

| Funkció | Leírás | Példa |
|----------|-------------|---------|
| ÉRTÉK (karakterlánc) | A megadott karakterlánc konvertálása egy számhoz. A vesszőket és a pont karaktereket (.) decimális elválasztóknak tekintik és a vezető kötőjelet (-) negatív jelként használjál. Kivételt ad, ha más nem numerikus karakterek találhatók a megadott karakterláncban. | **ÉRTÉK („1 234,56”)** megad egy kivételt. |
| NUMBERVALUE (karakterlánc, tizedesjegy-elválasztó, számjegy csoportosítási elválasztó) | A megadott karakterlánc konvertálása egy számhoz. A megadott tizedeselválasztó a decimális szám egészszám- és a tizedestört-részei között használatos. A megadott számjegy csoportosítási elválasztó használatos az ezresek elválasztására. | A **NUMBERVALUE("1 234,56", ",", " ")** **1234,56**-ot ad vissza. |
| INTVALUE (karakterlánc) | A megadott karakterláncot egész szám formájában adja vissza. Minden tizedesjegy csonkolásra kerül. | Az **INTVALUE ("100.77")** a **100** értéket adja vissza. |
| INTVALUE (szám) | A megadott számot egész szám formájában adja vissza. Minden tizedesjegy csonkolásra kerül. | **INTVALUE (-100.77)** a **-100** értéket adja vissza. |
| INT64VALUE (karakterlánc) | A megadott karakterláncot int64 formájában adja vissza. Minden tizedesjegy csonkolásra kerül. | Az **INT64VALUE ("22565422744")** **22565422744** értéket ad vissza. |
| INT64VALUE (szám) | A megadott számot int64 formájában adja vissza. Minden tizedesjegy csonkolásra kerül. | **INT64VALUE (22565422744.00)** a **22565422744** értéket jelenít meg. |

### <a name="record-functions"></a>Rekord függvények

| Funkció | Leírás | Példa |
|----------|-------------|---------|
| NULLCONTAINER (lista) | **Nulla** rekordot jelenít meg, amely ugyanolyan szerkezetű, mint a megadott rekord listája vagy a rekord.<blockquote>[!NOTE] Ez a funkció már elavult. Használja az **EMPTYRECORD** helyette.</blockquote> | **NULLCONTAINER (FELOSZTÁS („abc”, 1))** megjelenít egy új üres rekordot, amelynek ugyanolyan szerkezete van, mint a **FELOSZTÁS** funkció által megjelenített listának. |
| EMPTYRECORD (rekord) | **Nulla** rekordot jelenít meg, amely ugyanolyan szerkezetű, mint a megadott rekord listája vagy a rekord.<blockquote>[!NOTE] A **null** rekord olyan rekord, amelyben minden mezőhöz üres érték tartozik. Az üres érték **0** (nulla) a számok esetén, üres karakterlánc a karakterláncoknál stb.</blockquote> | **ÜRESREKORD (FELOSZTÁS („abc”, 1))** megjelenít egy új üres rekordot, amelynek ugyanolyan szerkezete van, mint a **FELOSZTÁS** funkció által megjelenített listának. |

### <a name="text-functions"></a>Szöveg függvények

<table>
<thead>
<tr>
<th>Funkció</th>
<th>Leírás</th>
<th>Példa</th>
</tr>
</thead>
<tbody>
<tr>
<td>FELSŐ (karakterlánc)</td>
<td>Visszaadja a megadott karakterláncot, amelyet előtte nagybetűssé alakít.</td>
<td><strong>FELSŐ(&quot;Minta&quot;)</strong> a következőt adja vissza: <strong>&quot;MINTA&quot;</strong>.</td>
</tr>
<tr>
<td>ALSÓ (karakterlánc)</td>
<td>Visszaadja a megadott karakterláncot, amelyet előtte kisbetűssé alakít.</td>
<td><strong>ALSÓ (&quot;Minta&quot;)</strong> a következőt adja vissza: <strong>&quot;minta&quot;</strong>.</td>
</tr>
<tr>
<td>BALRA (karakterlánc, karakterek száma)</td>
<td>Megjeleníti a megadott karakterlánc elejéről származó karakterek megadott számát.</td>
<td><strong>BALRA (&quot;Minta&quot;, 3)</strong> a következőt adja vissza: <strong>&quot;Min&quot;</strong>.</td>
</tr>
<tr>
<td>JOBBRA (karakterlánc, karakterek száma)</td>
<td>Megjeleníti a megadott karakterlánc végéről származó karakterek megadott számát.</td>
<td><strong>JOBBRA (&quot;Minta&quot;, 3)</strong> a következőt adja vissza: <strong>&quot;nta&quot;</strong>.</td>
</tr>
<tr>
<td>KÖZEPES (szöveg, kezdő beosztás, karakterek száma)</td>
<td>Megjeleníti a megadott karakterláncból származó karakterek megadott számát a megadott pozíciótól kezdve.</td>
<td><strong>KÖZEPES (&quot;Minta&quot;, 2, 3)</strong> a következőt adja vissza: <strong>&quot;amp&quot;</strong>.</td>
</tr>
<tr>
<td>LEN (karakterlánc)</td>
<td>A megadott karakterláncban szereplő karakterek számát jeleníti meg.</td>
<td><strong>LEN (&quot;Minta&quot;)</strong> a következőt adja vissza: <strong>6</strong>.</td>
</tr>
<tr>
<td>CHAR (szám)</td>
<td>Megjelenítik a megadott Unicode szám által hivatkozott karakterek karakterláncát.</td>
<td><strong>CHAR (255)</strong> a következőt adja vissza: <strong>&quot;ÿ&quot;</strong>.
<blockquote>[!NOTE] A funkció által visszaadott karakterlánc a szülő FILE formátumelemben kiválasztott kódolástól függ. A támogatott kódolások listájához lásd: <a href="https://msdn.microsoft.com/en-us/library/system.text.encoding(v=vs.110).aspx">Kódolási osztály</a>.</blockquote>
</td>
</tr>
<tr>
<td>ÖSSZEFŰZÉS (1-es karakterlánc [, 2-es karakterlánc...])</td>
<td>Az összes megadott szöveges karakterláncot adja vissza egy karakterláncba egyesítve.</td>
<td><strong>ÖSSZEFŰZÉS (&quot;abc&quot;, &quot;def&quot;)</strong> a következőt adja vissza: <strong>&quot;abcdef&quot;</strong>.
<blockquote>[!NOTE] Az <strong>&quot;abc&quot; &amp; &quot;def&quot;</strong> kifejezés szintén az <strong>&quot;abcdef&quot;</strong> értéket adja vissza.</blockquote>
</td>
</tr>
<tr>
<td>FORDÍTÁS (karakterlánc, minta, csere)</td>
<td>Úgy adja vissza a megadott karakterláncot, hogy a megadott mintakarakterlánc karaktereinek összes előfordulását a megadott helyettesítő karakterlánc megfelelő helyén található karakterekkel helyettesíti.</td>
<td>A <strong>FORDÍTÁS (&quot;abcdef&quot;, &quot;cd&quot;, &quot;GH&quot;)</strong> lecseréli a <strong>&quot;cd&quot;</strong> mintát a <strong>&quot;GH&quot;</strong> karakterlánccal, és a következőt adja vissza: <strong>&quot;abGHef&quot;</strong>.</td>
</tr>
<tr>
<td>CSERE (karakterlánc, minta, helyettesítő, reguláris kifejezés jelző)</td>
<td>Ha a megadott <strong>reguláris kifejezés jelzője</strong> paraméter <strong>igaz</strong>, akkor úgy adja vissza a megadott karakterláncot, hogy előtte a függvény <strong>mintaargumentumaként</strong> megadott reguláris kifejezés alkalmazásával módosította azt. A kifejezés segítségével meg lehet találni azokat a karaktereket, amelyeket ki kell cserélni. A megadott helyettesítési argumentum karakterei segítségével <strong>ki lehet cserélni</strong> a megtalált karaktereket. Ha a megadott <strong>reguláris kifejezés jelző</strong> paraméter <strong>hamis</strong>, ez a funkció úgy viselkedik, mint a <strong>TRANSLATE</strong> funkció.</td>
<td><strong>CSERE (&quot;+1 923 456 4971&quot;, &quot;[^0-9]&quot;, &quot;&quot;, igaz)</strong> reguláris kifejezést alkalmazásával eltávolítja az összes nem numerikus szimbólumot, és <strong>&quot;19234564971&quot;</strong> értéket jelenít meg. <strong>CSERE (&quot;abcdef&quot;, &quot;cd&quot;, &quot;GH&quot;, false)</strong> a <strong>&quot;cd&quot;</strong> mintát lecseréli a <strong>&quot;GH&quot;</strong> karakterlánccal, és a következőt adja vissza: <strong>&quot;abGHef&quot;</strong>.</td>
</tr>
<tr>
<td>SZÖVEG (bevitel)</td>
<td>A megadott bemenetet úgy adja vissza, hogy előtte az aktuális alkalmazás példányának kiszolgálója területi beállításainak megfelelően formázott szöveges karakterlánccá alakítja. A <strong>valós</strong> típus értékeihez a karakterlánc-konverzió két tizedesjegyre korlátozódik.</td>
<td>Ha a Finance and Operations-példány kiszolgáló területi beállítása <strong>EN-US</strong>, a <strong>TEXT (NOW ())</strong> a jelenlegi alkalmazás-munkamenet dátumát (2015. december 17.) <strong>&quot;12/17/2015 07:59:23 AM&quot;</strong> szöveges karakterláncként adja vissza. <strong>TEXT (1/3)</strong>a következőt adja vissza: <strong>&quot;0,33&quot;</strong>.</td>
</tr>
<tr>
<td>FORMAT (1. karakterlánc, 2. karakterlánc[, 3. karakterlánc, …])</td>
<td>A megadott karakterláncot úgy adja vissza, hogy előtte az <strong>%N</strong> minden előfordulását az <em>n.</em> argumentummal helyettesítve formázza. Az argumentumok karakterláncok. Ha egy argumentum nem érhető el a paraméter számára, a paraméter a karakterláncban <strong>&quot;%N&quot;</strong> elemként jelenik meg. A <strong>valós</strong> típus értékeihez a karakterlánc-konverzió két tizedesjegyre korlátozódik.</td>
<td>A következő példában a <strong>PaymentModel</strong> adatforrás megjeleníti a vevőrekordok listáját a <strong>Vevő</strong> összetevőn keresztül és az adatérték feldolgozását a <strong>ProcessingDate</strong> mezőn keresztül.
<p><a href="./media/picture-format-datasource.jpg"><img src="./media/picture-format-datasource.jpg" alt="PaymentModel data source" class="alignnone wp-image-290751 size-full" width="293" height="143" /></a></p>
<p>A kijelölt vevőkre vonatkozó elektronikus fájlok létrehozására tervezett ER formátumban a <strong>PaymentModel</strong> adatforrásként van kijelölve, és ellenőrzi a munkafolyamatot. A felhasználó tájékoztatásul kivételt kap, amikor a kiválasztott vevő le van állítva a jelentés feldolgozásának dátumára. Az ellenőrzés feldolgozásának ezen típusára vonatkozóan tervezett formula a következő forrásokat használhatja:</p>
<ul>
<li>A SYS70894 címke, amely a következő szöveggel rendelkezik:
<ul>
<li><strong>Az EN-US nyelvhez</strong>: &quot;Nothing to print&quot;</li>
<li><strong>A DE nyelvhez:</strong> &quot;Nichts zu drucken&quot;</li>
</ul></li>
<li>A SYS18389 címke, amely a következő szöveggel rendelkezik:
<ul>
<li><strong>Az EN-US nyelvhez:</strong> &quot;Customer %1 is stopped for %2.&quot;</li>
<li><strong>DE nyelvhez:</strong> &quot;Debitor '%1' wird für %2 gesperrt.&quot;</li>
</ul></li>
</ul>
<p>Íme a tervezhető képlet:</p>
<p>FORMAT (CONCATENATE (@&quot;SYS70894&quot;, &quot;. &quot;, @&quot;SYS18389&quot;), model.Customer.Name, DATETIMEFORMAT (model.ProcessingDate, &quot;d&quot;))</p>
<p>Ha a jelentés feldolgozása a <strong>Litware Retail</strong> vevőre vonatkozóan 2015. december 17-én folyik, az <strong>EN-US</strong> területi beállításban és az <strong>EN-US</strong> nyelvben ez a képlet a következő szöveget jeleníti meg, amely a felhasználó számára egy kivételre vonatkozó üzenetként jeleníthető meg:</p>
<p>&quot;Nothing to print. Customer Litware Retail is stopped for 12/17/2015.&quot;</p>
<p>Ha ugyanazt a jelentést 2015. december 17-én a <strong>Litware Retail</strong> vevőre vonatkozóan a <strong>DE</strong> területi beállítással és a <strong>DE</strong> nyelven dolgozzák fel, ez a képlet a következő, eltérő dátumformátumot használó szöveget jeleníti meg:</p>
<p>&quot;Nichts zu drucken. Debitor 'Litware Kiskereskedelmi' wird für 17.12.2015 gesperrt.&quot;</p>
<blockquote>[!NOTE] A címkék ER-képleteinél a következő szintaxis kerül alkalmazásra:
<ul>
<li><strong>Finance and Operations alkalmazások erőforrásokból származó címkékhez:</strong> <strong>@&quot;X&quot;</strong>, ahol <strong>X</strong> az alkalmazásobjektum-fában (AOT) szereplő címkeazonosító</li>
<li><strong>Az ER-konfigurációkban található címkékhez:</strong> <strong>@&quot;GER_LABEL:X&quot;</strong>, ahol <strong>X</strong> az ER-konfigurációban található címkeazonosító</li>
</ul>
</blockquote>
</td>
</tr>
<tr>
<td>SZÁMFORMÁTUM (szám, formátum)</td>
<td>A megadott szám karakterlánc formáját adja vissza a megadott formátumban. (A támogatott formátumokkal kapcsolatos információkért lásd: <a href="https://msdn.microsoft.com/library/dwhawy9k(v=vs.110).aspx">normál</a> és <a href="https://msdn.microsoft.com/library/0c899ak8(v=vs.110).aspx">egyéni</a>.) A környezet, amelyben a függvény fut, a számok formázásához használt kultúra függvénye.</td>
<td>Az EN-US kultúrában a <strong>SZÁMFORMÁTUM (0.45, &quot;p&quot;)</strong> a következőt adja vissza: <strong>&quot;45.00 %&quot;</strong>. <strong>SZÁMFORMÁTUM (10.45, &quot;#&quot;)</strong> a következőt adja vissza: <strong>&quot;10&quot;</strong>.</td>
</tr>
<tr>
<td>NUMBERFORMAT (szám, formátum, kulturális környezet)</td>
<td>A megadott számot parancsfájl formájában adja vissza a megadott formátum és területi beállítások alapján. (A támogatott formátumokkal kapcsolatos további tudnivalókat lásd: <a href="https://docs.microsoft.com/dotnet/standard/base-types/standard-numeric-format-strings">szokásos</a> és <a href="https://docs.microsoft.com/dotnet/standard/base-types/custom-numeric-format-strings">egyéni</a>.).</td>
<td><strong>NUMBERFORMAT (10/3, “F2”, "de")</strong> visszaadja a <strong>3,33</strong> értéket, míg <strong>NUMBERFORMAT (10/3, “F2”, "en-us")</strong> visszaadja a <strong>3.33</strong> értéket.</td>
</tr>
<tr>
<td>NUMERALSTOTEXT (szám, nyelv, pénznem, pénznem névjelzőjének nyomtatása, tizedes)</td>
<td>A megadott számot adja vissza, miután megtörtént az átírása (konvertálása szöveglánc formátumra) a megadott nyelven. A nyelvkód megadása nem kötelező. Ha üres karakterláncként van megadva, akkor a futó környezet nyelvkódját használja a rendszer. (A futó környezet nyelvkódja létrehozó mappához vagy fájlhoz van megadva.) A pénznemkód szintén nem kötelező. Ha üres karakterláncként van meghatározva, a rendszer a vállalati pénznemet használja.
<blockquote>[!NOTE] A <strong>pénznem névjelzőjének nyomtatása</strong> paraméter és a <strong>tizedes</strong> paraméterek elemzését csak a következő nyelvkódokra vonatkozóan végzi el a rendszer: <strong>CS</strong>, <strong>ET</strong>, <strong>HU</strong>, <strong>LT</strong>, <strong>LV</strong>, <strong>PL</strong> és <strong>RU</strong>. Emellett a <strong>pénznem névjelzőjének nyomtatása</strong> paraméter elemzését csak azon, a rendszert használó vállalatok esetében végzi el a rendszer, amelyek ország- vagy régiókörnyezete támogatja a valuták nevének ragozását.</blockquote>
</td>
<td>A <strong>NUMERALSTOTEXT (1234.56, &quot;EN&quot;, &quot;&quot;, false, 2)</strong> a következő eredményt adja vissza: <strong>&quot;One Thousand Two Hundred Thirty Four and 56&quot;</strong>. A <strong>NUMERALSTOTEXT (120, &quot;PL&quot;, &quot;&quot;, false, 0)</strong> a következő eredményt adja vissza: <strong>&quot;Sto dwadzieścia&quot;</strong>. A <strong>NUMERALSTOTEXT (120.21, &quot;RU&quot;, &quot;EUR&quot;, true, 2)</strong> a következő eredményt adja vissza: <strong>&quot;Сто двадцать евро 21 евроцент&quot;</strong>.</td>
</tr>
<tr>
<td>PADLEFT (karakterlánc, hossz, kitöltő karakterek)</td>
<td>Megadott hosszúságú karakterláncot ad vissza, amelyben az aktuális karakterlánc eleje megadott karakterekkel van kitöltve.</td>
<td>A <strong>PADLEFT (&quot;1234&quot;, 10, &quot;&nbsp;&quot;)</strong> a következő szöveges karakterláncot adja vissza: <strong>&quot;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;1234&quot;</strong>.</td>
</tr>
<tr>
<td>TRIM (karakterlánc)</td>
<td>A megadott szöveget adja vissza, miután a kezdő és záró szóközöket levágta, és a szavak közötti több szóközt eltávolította.</td>
<td>A <strong>TRIM (&quot;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Minta&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;szöveg&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&quot;)</strong> a következő eredményt adja vissza: <strong>&quot;Minta szöveg&quot;</strong>.</td>
</tr>
<tr>
<td>GETENUMVALUEBYNAME (felsorolási adatforrás elérési útja, felsorolási érték címkeszövege)</td>
<td>Egy megadott felsorolási adatforrás értékét adja vissza a felsorolási címke megadott szövege alapján.</td>
<td>A következő ábra az adatmodellbe bevezetett <strong>ReportDirection</strong> sorszámozást mutatja be. Vegye figyelembe, hogy a címkék az enumerációs értékekhez vannak megadva.
<p><a href="./media/ER-data-model-enumeration-values.PNG"><img src="./media/ER-data-model-enumeration-values.PNG" alt="Available values for data model enumeration" class="alignnone wp-image-290681 size-full" width="397" height="136" /></a></p>
<p>A következő ábrán ezek a részletek láthatók:</p>
<ul>
<li>A <strong>ReportDirection</strong> modellfelsorolás jelentésbe <strong>$Direction</strong> adatforrásként kerül beillesztésre.</li>
<li>Az <strong>$IsArrivals</strong> ER-kifejezés a modellfelsorolást e függvény paramétereként használja. A kifejezés értéke <strong>IGAZ</strong>.</li>
</ul>
<a href="./media/ER-data-model-enumeration-usage.PNG"><img src="./media/ER-data-model-enumeration-usage.PNG" alt="Example of data model enumeration" class="alignnone wp-image-290681 size-full" width="397" height="136" /></a>
</td>
</tr>
<tr>
<td>GUIDVALUE (bevitel)</td>
<td>Konvertálja a megadott bemenetét a <strong>karakterlánc</strong> adattípusnak a <strong>GUID</strong> adattípus adatelemévé.<blockquote>[!NOTE] Ehhez az ellenkező irányban konverzió (például konvertálható bevitele megadott a <strong>GUID</strong> egy adatelem az adattípust a <strong>karakterlánc</strong> adattípus), használhatja a <strong>TEXT()</strong> funkció.</blockquote></td>
<td>A következő adatforrás megadása a modell-hozzárendelésben:
<ul>
<li><strong>myID</strong> (<strong>Számított mező</strong> típus), amely ezt a kifejezést tartalmazza: <strong>GUIDVALUE (&quot;AF5CCDAC-F728-4609-8C8B-A4B30B0C0AA0&quot;)</strong></li>
<li><strong>Felhasználók</strong> (<strong>Táblarekordok</strong> típus), amelyre vonatkozik a UserInfo táblára</li>
</ul>
Ezen adatforrások megadásakor használható kifejezés például a <strong>FILTER (Users, Users.objectId = myID)</strong> a UserInfo tábla szűréséhez az <strong>objectId</strong> területén a <strong>GUID</strong> adattípusnak.
</td>
</tr>
<tr>
<td>JSONVALUE (azonosító, elérési út)</td>
<td>Adatok elemzése a megadott elérési út által használt JavaScript Object Notation (JSON) formátumban, a megadott azonosítón alapuló skaláris érték kibontásához.</td>
<td>Az adatforrás <strong>$JsonField</strong> JSON-formátumban a következő adatokat tartalmazza:<strong>{&quot;BuildNumber&quot;:&quot;7.3.1234.1&quot;, &quot;KeyThumbprint&quot;:&quot;7366E&quot;}</strong>. Az adatforrásra: </strong>JSONVALUE ( &quot;BuildNumber&quot;, $JsonField)</strong> ezt az értéket adja eredményül: <strong>7.3.1234.1</strong>, a <strong>karakterlánc</strong> adattípussal.</td>
</tr>
</tbody>
</table>

### <a name="data-conversion-functions"></a>Adatkonvertálási függvények

| Funkció | Leírás | Példa |
|----------|-------------|---------|
| SZÖVEG (bevitel) | A megadott bemenetet úgy adja vissza, hogy előtte az aktuális alkalmazás példányának kiszolgálója területi beállításainak megfelelően formázott szöveges karakterlánccá alakítja. A **valós** típus értékeihez a karakterlánc-konverzió két tizedesjegyre korlátozódik. | Ha a Finance and Operations-példány kiszolgáló területi beállítása **EN-US**, a **TEXT (NOW ())** a jelenlegi Finance and Operations munkamenet dátumát (2015. december 17.) **12/17/2015 07:59:23 AM** szöveges karakterláncként adja vissza. **SZÖVEG (1/3)** **„0,33”** értéket jelenít meg. |
| QRCODE (karakterlánc) | QR-kód-képet ad vissza base64 bináris formátumban az adott karakterlánchoz. | A **QRCODE (“Sample text”)** a **U2FtcGxlIHRleHQ=** értéket adja vissza. |

### <a name="data-collection-functions"></a>Adatgyűjtési függvények

| Funkció | Leírás | Példa |
|----------|-------------|---------|
| FORMATELEMENTNAME () | Az aktuális formátum összetevőjének nevét adja vissza. Üres karakterláncot ad vissza, ha az aktuális fájlok **Kimeneti részletek gyűjtése** jelzője ki van kapcsolva. | Ha többet szeretne megtudni e függvény használatáról, tekintse meg az **ER kimeneti adatformátum használata számlálás és összegzés céljából** című feladat-útmutatót (ez az **Informatikai szolgáltatások/megoldások összetevőinek beszerzése/kifejlesztése** üzleti folyamat része). |
| SUMIFS (kulcskarakterlánc az összegzéshez, feltételtartomány1 karakterlánca, kiválasztási feltétel1 karakterlánca \[, feltételtartomány2 karakterlánca, kiválasztási feltétel2 karakterlánca, ...\]]) | XML-csomópontok értékeinek összegét adja vissza (kulcsként meghatározott névvel), amelyet a rendszer a formátum végrehajtásakor gyűjt, és amely megfelel a megadott feltételeknek (tartomány- és értékpárok). **0** (nulla) értéket ad vissza, ha az aktuális fájlok **Kimeneti részletek gyűjtése** jelzője ki van kapcsolva. | |
| SUMIF (kulcskarakterlánc az összegzéshez, feltételtartomány karakterlánca, kiválasztási feltétel karakterlánca) | XML-csomópontok értékeinek összegét adja vissza (kulcsként meghatározott névvel), amelyet a rendszer a formátum végrehajtásakor gyűjt, és amely megfelel a megadott feltételnek (tartomány és érték). **0** (nulla) értéket ad vissza, ha az aktuális fájlok **Kimeneti részletek gyűjtése** jelzője ki van kapcsolva. | |
| COUNTIFS (feltételtartomány1 karakterlánca, kiválasztási feltétel1 karakterlánca \[, feltételtartomány2 karakterlánca, kiválasztási feltétel2 karakterlánca, ...\]) | Az XML-csomópontok számát adja vissza, amelyeket a rendszer a formátum végrehajtásakor gyűjtött, és amely megfelel a megadott feltételeknek (tartomány- és értékpárok). **0** (nulla) értéket ad vissza, ha az aktuális fájlok **Kimeneti részletek gyűjtése** jelzője ki van kapcsolva. | |
| COUNTIF (feltételtartomány karakterlánca, kiválasztási feltételek karakterlánca) | Az XML-csomópontok számát adja vissza, amelyeket a rendszer a formátum végrehajtásakor gyűjtött, és amely megfelel a megadott feltételnek (tartomány és érték). **0** (nulla) jelzőértéket ad vissza, ha az aktuális fájlok **Kimeneti részletek gyűjtése** jelzője ki van kapcsolva. | |
| COLLECTEDLIST (feltételtartomány1 karakterlánca, kiválasztási feltétel1 karakterlánca \[, feltételtartomány2 karakterlánca, kiválasztási feltétel2 karakterlánca, ...\]) | Az XML-csomópontokra nézve gyűjtött értékek listáját adja vissza, amelyeket a rendszer a formátum végrehajtásakor gyűjtött, és amely megfelel a megadott feltételeknek (tartomány és érték). Üres listát ad vissza, ha az aktuális fájlok **Kimeneti részletek gyűjtése** jelzője ki van kapcsolva. | |

### <a name="other-business-domainspecific-functions"></a>Egyéb (üzleti területre jellemző) függvények

| Funkció | Leírás | Példa |
|----------|-------------|---------|
| PÉNZNEMVÁLTÁS (összeg, eredeti pénznem, cél pénznem, dátum, vállalat) | A megadott pénzösszeg konvertálása a megadott eredeti pénznemről a megadott cél pénznemre a megadott vállalat beállításainak használata segítségével a megadott időpontban. | **PÉNZNEMVÁLTÁS (1, „EUR”, „USD”, MA(), „DEMF”)** egy euró egyenértékét USA-dollárban jelenít meg az aktuális munkameneti napon a DEMF vállalat beállításai alapján. |
| ÖSSZEGKEREKÍTÉS (szám, tizedes, kerekítési szabály) | A megadott összeget a megadott tizedesjegyek száma és a megadott kerekítési szabály szerint kerekíti.<blockquote>[!NOTE] A kerekítési szabályt a **RoundOffType** felsorolásának értékeként kell meghatározni.</blockquote> | Ha a **model.RoundOff** paraméter **Downward** értékre van állítva, a **ROUNDAMOUNT (1000.787, 2, model.RoundOff)** a következő értéket adja vissza: **1000,78**. Ha a **modell.Roundoff** paraméter értéke vagy **Normál** vagy **Felkerekítés** lehetőségre van beállítva, akkor az **ÖSSZEGKEREKÍTÉS (1000,787, 2. modell.Roundoff)** **1000,79** értéket jeleníti meg. |
| CURCredRef (számjegy) | Egy hitelező hivatkozást jelenít meg a megadott számlaszám számjegyei alapján. | **CURCredRef („VEND-200002”)** **„2200002”** értéket jelenít meg. |
| MOD\_97 (számjegy) | Egy hitelező hivatkozást MOD97 kifejezésként jelenít meg a megadott számlaszám számjegyei alapján. | **MOD\_97 ("VEND-200002")** a következőt adja vissza: **"20000285"**. |
| ISOCredRef (számjegy) | Egy ISO (International Organization for Standardization ) hitelezői hivatkozást jelenít meg a megadott számlaszám betűi és számjegyei alapján.<blockquote>[!NOTE] A nem ISO szabványos betűkből származó szimbólumok eltávolításához a bemeneti paramétereket le kell fordítani a függvénynek történő megfeleltetés előtt.</blockquote> | **ISOCredRef („VEND-200002”)** **„RF23VEND-200002”** értéket jelenít meg. |
| CN\_GBT\_AdditionalDimensionID (karakterlánc, szám) | A megadott további pénzügyi dimenzió azonosítójának beolvasása. A **karakterlánc** paraméterben a dimenziókat a rendszer vesszővel elválasztott azonosítókként jeleníti meg. A **szám** paraméter a kért dimenzió számsorozatkódját határozza meg a karakterláncban. | A **CN\_GBT\_AdditionalDimensionID ("AA,BB,CC,DD,EE,FF,GG,HH",3)** a következőt adja vissza: **"CC"**. |
| GetCurrentCompany () | Egy olyan jogi személyhez (vállalathoz) tartozó kód szöveges változatát adja vissza, amelybe egy felhasználó jelenleg be van jelentkezve. | A **GETCURRENTCOMPANY()** az **USMF** értéket adja vissza a programban a **Contoso Entertainment System USA** vállalatba bejelentkezett felhasználók számára. |
| CH\_BANK\_MOD\_10 (számjegyek) | Egy hitelező hivatkozást MOD10 kifejezésként jelenít meg a megadott számlaszám számjegyei alapján. | A **CH\_BANK\_MOD\_10 ("VEND-200002")** a következőt adja vissza: **3**. |
| FA\_SUM (tárgyi eszköz kódja, értékmodell kódja, kezdő dátum, záró dátum) | A tárgyi eszköz adott időszakra vonatkozó összegeinek előkészített adattárolóját adja vissza. | A **FA\_SUM ("COMP-000001", "Aktuális", Dátum1, Dátum2)**  a **„COMP-000001”** tárgyi eszköz előkészített adattárolóját adja vissza **„Aktuális”** értékmodellel a **Dátum1** és **Dátum2** közötti időtartamra. |
| FA\_BALANCE (tárgyi eszköz kódja, értékmodell kódja, jelentési év, jelentés dátuma) | A tárgyieszköz-egyenleg előkészített adattárolóját adja vissza. A jelentési évet az **AssetYear** felsorolás értékeként kell meghatározni. | A **FA\_SUM ("COMP-000001", "Aktuális", AxEnumAssetYear.ThisYear, SESSIONTODAY ())** a **„COMP-000001”** tárgyieszköz-egyenlegek előkészített adattárolóját adja vissza **„Aktuális”** értékmodellként az aktuális alkalmazás-munkamenet dátumán. |
| TABLENAME2ID (karakterlánc) | Egy adott táblanévhez tartozó táblaazonosítót ad vissza egész számokkal kifejezett formában. | A **TABLENAME2ID ("Intrastat")** az **1510** értéket adja vissza. |
| ISVALIDCHARACTERISO7064 (karakterlánc) | A logikai **IGAZ** értéket adja vissza, ha a megadott karakterlánc érvényes nemzetközi bankszámlaszámnak (IBAN) felel meg. Ellenkező esetben a visszaadott logikai érték **HAMIS**. | **ISVALIDCHARACTERISO7064 ("AT61 1904 3002 3457 3201")** az **IGAZ** értéket adja vissza. **ISVALIDCHARACTERISO7064 ("AT61")** a **HAMIS** értéket adja vissza. |
| NUMSEQVALUE (számsorozat kódját, hatókör, hatókör-azonosító) | Egy számsorozat új generált értékét adja vissza a megadott számsorozat kódja, a hatókör és a hatókör-azonosító alapján. A hatókör értéket a **ERExpressionNumberSequenceScopeType** felsorolás alapján kell megadni (**megosztott**, **jogi személy** vagy **vállalat**). A **megosztott** hatókörnél egy üres karakterláncot adjon meg a hatókör-azonosítóként. A **vállalat** és a **jogi személy** hatóköröknél a vállalat azonosítóját adja meg a hatókör-azonosítóként. A **vállalat** és a **jogi személy** hatóköröknél, ha egy üres karakterláncot ad meg a hatókör-azonosítóként, az aktuális vállalati azonosít lesz használatos. | A következő adatforrás megadása a modell-hozzárendelésben:<ul><li>**enumScope** (**Dynamics 365 for Operations felsorolás** típusa), amely az **ERExpressionNumberSequenceScopeType** felsorolásra hivatkozik</li><li>**NumSeq** (**Számított mező** típus), amely ezt a kifejezést tartalmazza: **NUMSEQVALUE ("Gene\_1", enumScope.Company, "")**</li></ul>Ha a **NumSeq** adatforrást hívják meg, az új létrehozott értékét ad vissza a **Gene\_1** számsorozatnak, amely a vállalathoz van beállítva, amely a kontextust adja, amely alatt az ER-formátumot futtatják. |
| NUMSEQVALUE (számsorozatkód) | Egy számsorozat új generált értékét adja vissza, a megadott számsorozat alapján, a **vállalat** hatókörben, és (mint hatókör-azonosító) a vállalat kódját, amely a kontextust adja, amely alatt az ER-formátumot futtatják. | A modell-hozzárendelésben határozza meg a következő adatforrást: **NumSeq** (**számított mező** típus). Az adatforrás tartalmazza a kifejezést: **NUMSEQVALUE ("Gene\_1")**. Ha a **NumSeq** adatforrást hívják meg, az új létrehozott értékét ad vissza a **Gene\_1** számsorozatnak, amely a vállalathoz van beállítva, amely a kontextust adja, amely alatt az ER-formátumot futtatják. |
| NUMSEQVALUE (számsorozat-rekordazonosító) | Egy számsorozat új generált értékét adja vissza a megadott számsorozat rekordazonosítója alapján. | A következő adatforrás megadása a modell-hozzárendelésben:<ul><li>**LedgerParms** (**Tábla** típus), amely a LedgerParameters táblára hivatkozik</li><li>**NumSeq** (**Számított mező** típus), amely ezt a kifejezést tartalmazza: **NUMSEQVALUE (LedgerParameters.'numRefJournalNum()'.NumberSequenceId)**</li></ul>Ha a **NumSeq** adatforrást hívják meg, az új létrehozott értékét ad vissza a számsorozatnak, amely a vállalathoz van beállítva a főkönyvi paraméterekben, amely a kontextust adja, amely alatt az ER-formátumot futtatják. Ez a számsorozat egyértelműen azonosítja naplókat, és kötegszámként viselkedik, amely összekapcsolja a tranzakciókat. |

### <a name="functions-list-extension"></a>A funkciók lista kiterjesztése

Az ER segítségével bővítheti az ER kifejezésekben használt függvények listáját. Ez bizonyos műszaki erőfeszítést igényel. Részletes tudnivalókat lásd: [Elektronikus jelentéskészítési (ER) funkciók listájának kibővítése](general-electronic-reporting-formulas-list-extension.md).

## <a name="additional-resources"></a>További erőforrások

- [Elektronikus jelentéskészítés (ER) áttekintése](general-electronic-reporting.md)
- [Elektronikus jelentéskészítési (ER) funkciók listájának kibővítése](general-electronic-reporting-formulas-list-extension.md)
