---
title: Képletszerkesztő elektronikus jelentésekhez (ER)
description: A témakör tájékoztatást nyújt a képletszerkesztő használatának módjáról az elektronikus jelentésekben (ER).
author: NickSelin
ms.date: 12/05/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: eec63fb1782c5afed0320eb841b6bfc92af31a691731ef6bac5d00ed442c0dcd
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6777404"
---
# <a name="formula-designer-in-electronic-reporting-er"></a>Képletszerkesztő elektronikus jelentésekhez (ER)

[!include [banner](../includes/banner.md)]

Ez a témakör ismerteti a képletszerkesztő használatát az Elektronikus jelentésben (ER). Ha egy formátumot az ER-ben meghatározott elektronikus dokumentumra vonatkozóan tervez meg, akkor használhat képleteket az adatok átalakításához a dokumentum teljesítésére és formázására vonatkozó követelményekhez történő megfeleltetés érdekében. Ezek a képletek a Microsoft Excel programban található képletekre hasonlítanak. A képletek funkciók különféle típusait támogatják - szöveg, dátum és időpont, matematikai logika, információ, adattípus-konvertálás funkciók, valamint egyéb üzletitartomány-specifikus funkciók.

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

## <a name="data-binding"></a><a name="Binding"></a>Adatok kötése

Az ER Képletszerkesztő segítségével meghatározhatja azokat a kifejezéseket, amelyek átalakítják az adatforrásból származó adatokat, hogy az adatokat az adattárolóban futásidőben adhassa meg a következő módokon:

- Az alkalmazás-adatforrásokból és futtatási paraméterekből egy ER adatmodellbe
- Az ER adatmodell ER formátumba
- Az alkalmazás-adatforrásokból és futtatási paraméterekből egy ER-formátumba

Az alábbi ábra bemutatja az ilyen típusú kifejezés tervezését. Ebben a példában a kifejezés két tizedesjegy pontosságra kerekíti az **Intrastat.AmountMST** mezőjének – Intrastat tábla – értékét, majd visszaadja a kerekített értéket.

[![Adatkötési kifejezés.](./media/picture-expression-binding.jpg)](./media/picture-expression-binding.jpg)

Az alábbi ábra bemutatja, hogyan használható az ilyen típusú kifejezés. Ebben a példában a tervezett kifejezés eredményének megadása a **Adóösszeg-jelentési** adatmodell **Transaction.InvoicedAmount** komponensének alapján történik.

[![Használatban lévő adatkötési kifejezés.](./media/picture-expression-binding2.jpg)](./media/picture-expression-binding2.jpg)

Futásidőben a tervezett `ROUND (Intrastat.AmountMST, 2)` képlet az **AmountMST** mező értékét két tizedesjegy pontossággal kerekíti az Intrastat tábla minden egyes rekordjánál. Ezután a kerekített értéket beviszi az **Adóbevallás** adatmodell **Transaction.InvoicedAmount** összetevőjébe.

## <a name="data-formatting"></a><a name="Transformation"></a>Adatformázás

Az ER Képletszerkesztő segítségével meghatározhatja azokat a formátumokat, amelyek átalakítják az adatforrásból származó adatokat, úgy hogy adatokat küldhet egy elektronikusan létrejövő dokumentum részeként. Előfordulhat, hogy olyan formátummal kell dolgoznia, amelyet amelyet olyan tipikus szabályként kell alkalmazni, amelyet egy formátumban újra kell használni. Ebben az esetben a formátumot bevezetheti egyszer a formátum konfigurációjában névvel ellátott, formázási kifejezést tartalmazó átalakításként. Ez az elnevezett átalakítás hozzákapcsolható számos formátum-összetevőhöz, amelynek kimenetét formázni kell a létrehozott formázási kifejezésnek megfelelően.

Az alábbi ábra bemutatja az ilyen típusú átalakítás tervezését. Ebben a példában a **TrimmedString** átalakítás a *karakterlánc* adattípus bejövő adatait csonkolja a kezdő és záró szóközök eltávolításával. Ezután a csonkolt karakterláncot adja vissza.

[![Átalakítás.](./media/picture-transformation-design.jpg)](./media/picture-transformation-design.jpg)

Az alábbi ábra bemutatja, hogyan használható az ilyen típusú átalakítás. Ebben a példában számos formátum-összetevő küld szöveget kimenetként futásidóben a létrehozó elektronikus dokumentum számára. Ezen formátum-összetevők mindegyike név szerint hivatkozik a **TrimmedString** átalakításra.

[![Használt átalakítás.](./media/picture-transformation-usage.jpg)](./media/picture-transformation-usage.jpg)

Amikor a formátum azon összetevőit, mint például az előző példában a **partyName** összetevőt, amelyek hivatkoznak a **TrimmedString** átalakításra, ez az átalakítás kimenetként küldi el a létrehozó elektronikus dokumentum számára. Ez a szöveg nem tartalmazza a kezdő és záró szóközöket.

Ha olyan formázással rendelkezik, amelyet egyénileg kell alkalmazni, akkor a formázás a megadott formátum-összetevő kötésének egyéni kifejezéseként jelenítheti meg. Az alábbi ábra bemutatja az ilyen típusú kifejezését. Ebben a példában a **partyType** formátum összetevő az adatforráshoz kötött azon kifejezésen keresztül, amely átalakítja a **Model.Company.RegistrationType** mezőjéből származó bejövő adatokat az adatforrásban a nagybetűs szöveghez. A kifejezés ezután ezt a szöveget az elektronikus dokumentum számára kimenetként küldi el.

[![Formázás alkalmazása egyes összetevőkre.](./media/picture-binding-with-formula.jpg)](./media/picture-binding-with-formula.jpg)

## <a name="process-flow-control"></a><a name="Validation"></a>Folyamatáramlat irányítás

A ER képlettervező segítségével meg lehet határozni azokat a kifejezéseket, amelyek irányítják az elektronikus dokumentumok létrehozásának folyamatábráját. A következő feladatokat végezheti el:

- Határozza meg azokat a kifejezéseket, amelyek meghatározzák, hogy mikor kell egy dokumentumkészítési folyamatot megszakítani.
- Határozza meg azokat a kifejezéseket, amelyek üzeneteket hoznak létre a felhasználónak a megállított folyamatról vagy végrehajtásnapló-üzeneteket adnak ki a jelentéskészítés zajló folyamatáról.
- Adja meg a generálási elektronikus dokumentumok fájlneveit és létrehozás szabályozó feltételeit.

A folyamatáramlat irányítás minden szabálya egyéni ellenőrzésként van tervezve. Az alábbi ábra bemutatja az ilyen típusú ellenőrzést. Íme a konfiguráció magyarázata ebben a példában:

- Az ellenőrzés akkor megy végbe, amikor a **INSTAT** csomópont létrejön az XML-fájl létrehozása során.
- Ha a tranzakció listája üres, az ellenőrzés megállítja a végrehajtási folyamatot és **HAMIS** értéket küld vissza.
- Az ellenőrzés egy hibaüzenetet küld vissza, amely tartalmazza a felhasználó által előnyben részesített nyelven a SYS70894 címke szövegét.

[![Ellenőrzés.](./media/picture-validation.jpg)](./media/picture-validation.jpg)

Az ER képletszerkesztő segítségével generálhat egy fájlnevet a létrejövő elektronikus dokumentum számára, és kezelheti a fájl létrejöttének folyamatát. Az alábbi ábra bemutatja az ilyen típus folyamatáramlat-irányítás tervezését. Íme a konfiguráció magyarázata ebben a példában:

- A **model.Intrastat** adatforrásból származó rekordok listája kötegekre oszlik. Minden egyes köteg legfeljebb 1000 rekordot tartalmaz.
- A kimenet létrehoz egy irányítószámot, amely tartalmaz egy fájlt minden létrehozott kötegre vonatkozóan egy XML-formátumú fájlban.
- Egy kifejezés a létrejövő elektronikus dokumentumokra vonatkozó fájlnevet ad vissza a fájlnév és a fájlnév-kiterjesztés összefűzésével. A második kötegre és minden további kötegre vonatkozóan a fájl neve tartalmazza a Kötegazonosítót utótagként.
- Egy kifejezés lehetővé teszi ( **IGAZ** visszaküldése esetén) a fájl létrehozási folyamatát azon kötegekre vonatkozóan, amelyek legalább egy rekordot tartalmaznak.

[![Folyamatáramlás irányítása.](./media/picture-file-control.jpg)](./media/picture-file-control.jpg)

## <a name="document-content-control"></a><a name="Enabled"></a>Dokumentumtartalmak vezérlése

Az elektronikus képlettervező segítségével olyan kifejezéseket állíthat be, amelyek vezérlik, hogy milyen adatokat kell elhelyezni az elektronikus dokumentumokban futásidőben. A kifejezések az adatok feldolgozásától és a konfigurált logikától függően engedélyezhetik vagy letilthatják a formátum egyes elemeinek kimenetét. Ezeket a kifejezéseket egyetlen formátumú elemként is megadhatja az **Engedélyezve** mezőben a **Műveleti tervező** oldal **Hozzárendelés** lapján. A kifejezéseket megadhatja logikai feltételként, amely egy *Logikai* értéket ad eredményül:

- Ha a feltétel **Igaz** értéket ad vissza, a jelenlegi formátumelem fut.
- Ha a feltétel **Hamis** értéket ad vissza, a jelenlegi formátumelem kihagyásra kerül.

Az alábbi ábra ilyen típusú kifejezéseket mutat be. (Az **ISO20022-jóváírás átutalás (NO)** formátumkonfigurációnak a Microsoft által biztosított 11.12.11 verziója kerül példaként felhasználásra.) Az **XMLHeader** formátumösszetevő úgy van konfigurálva, hogy leírja az átutalási üzenet szerkezetét az ISO 20022 XML-üzenetszabványoknak megfelelően. Az **XMLHeader/Document/CstmrCdtTrfInitn/PmtInf/CdtTrfTxInf/RmtInf/Ustrd** formátumösszetevő úgy van beállítva, hogy hozzáadja a létrejövő üzenethez az **Ustrd** XML-elemet, és az átutalási adatokat elhelyezze strukturálatlan formátumban a következő XML-elemek szövegeként:

- A **PaymentNotes** összetevő a fizetési megjegyzések szövegének előállítására szolgál.
- A **DelimitedSequence** összetevő az aktuális átutalás kiegyenlítéséhez használt vesszővel tagolt számlaszámokat állítja elő.

[![PaymentNotes és DelimitedSequence összetevők.](./media/GER-FormulaEditor-ControlContent-1.png)](./media/GER-FormulaEditor-ControlContent-1.png)

> [!NOTE]
> A **PaymentNotes** és **DelimitedSequence** összetevők kérdőjellel vannak megjelölve. A kérdőjel azt jelzi, hogy az összetevő használata feltételes. Ebben az esetben az összetevők használata a következő kritériumokon alapul:
>
> - A **PaymentNotes** összetevőhöz meghatározott `@.PaymentsNotes <> ""` kifejezés lehetővé teszi (**IGAZ** érték visszaküldésével) az **Ustrd** XML-elemnek a fizetési megjegyzések szövegével való feltöltését, ha az aktuális átutalás esetében ez a szöveg nem üres.
>
>    [![A PaymentNotes összetevő kifejezése.](./media/GER-FormulaEditor-ControlContent-2.png)](./media/GER-FormulaEditor-ControlContent-2.png)
>
> - A **DelimitedSequence** összetevőhöz meghatározott `@.PaymentsNotes = ""` kifejezés lehetővé teszi (**IGAZ** érték visszaküldésével) az **Ustrd** XML-elemnek a feltöltését olyan számlaszámok vesszővel elválasztott listájával, amelyeket az aktuális átutalás kiegyenlítéséhez használnak amikor az átutalás fizetési megjegyzése üres.
>
>    [![A DelimitedSequence összetevő kifejezése.](./media/GER-FormulaEditor-ControlContent-3.png)](./media/GER-FormulaEditor-ControlContent-3.png)
> 
> Ennek a beállításnak a alapján az összes adósi kifizetésre generált üzenet **Ustrd** XML-elem tartalmazni fogja a fizetési megjegyzések szövegét, vagy ha az ilyen szöveg üres, akkor a kifizetés kiegyenlítéséhez használt számlaszámok vesszővel tagolt listáját.

## <a name="validation-of-configured-formulas"></a><a name="TestFormula"></a>Konfigurált képletek érvényesítése

A **Képlettervező** lapon kattintson a **Teszt** elemre a konfigurált képlet működésének ellenőrzéséhez.

[![Teszt kiválasztása a képlet ellenőrzéséhez.](./media/ER-FormulaTest-Start.png)](./media/ER-FormulaTest-Start.png)

Ha a képletargumentumok értékei szükségesek, megnyithatja a **Tesztkifejezés** párbeszédpanelt a **Képlettervező** lapról. A legtöbb esetben ezeket az argumentumokat manuálisan kell definiálni, mert a konfigurált kötések nem futnak a tervezés során. A **Képlettervező** oldal **Teszteredmény** lapja megjeleníti a konfigurált képlet végrehajtásának eredményét.

A következő példa bemutatja, hogyan tesztelheti a külkereskedelmi tartományhoz konfigurált képletet annak biztosítására, hogy az Intrastat-vámtarifakód csak számjegyeket tartalmazzon.

A képlet tesztelésekor a **Tesztkifejezés** párbeszédpanel segítségével határozhatja meg az Intrastat-vámtarifakód teszteléshez használt értékét.

[![A teszteléshez használatos Intrastat-vámtarifakód megadása.](./media/ER-FormulaTest-Start-EnterArguments.png)](./media/ER-FormulaTest-Start-EnterArguments.png)

Az Intrastat-vámtarifakód megadása és az **OK** kiválasztása után a **Képlettervező** oldal **Teszteredmény** lapja a konfigurált képlet végrehajtásának eredményét jeleníti meg. Ezután kiértékelheti, hogy az eredmény elfogadható-e. Ha az eredmény nem elfogadható, akkor frissítheti a képletet, és újra tesztelheti.

[![Teszteredmény.](./media/ER-FormulaTest-Result.png)](./media/ER-FormulaTest-Result.png)

Néhány képletet nem lehet a tervezés alatt tesztelni. Előfordulhat például, hogy egy képlet olyan adattípus-eredményt adott vissza, amely nem jelenik meg a **Teszteredmény** lapon. Ebben az esetben egy hibaüzenet jelenik meg, amely szerint a képletet nem lehet tesztelni.

[![Hibaüzenet.](./media/ER-FormulaTest-Error.png)](./media/ER-FormulaTest-Error.png)

## <a name="additional-resources"></a>További erőforrások

- [Elektronikus jelentések áttekintése](general-electronic-reporting.md)
- [Elektronikus jelentéskészítés képletének nyelve](er-formula-language.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]