---
title: Készlet előrejelzések
description: Ez a témakör leírja azokat a készlet- és igény-előrejelzési funkciókat, amelyek készlet.előrejelzések készítéséhez használhatók a Microsoft Dynamics 365 Supply Chain Management alkalmazásban.
author: crytt
ms.date: 06/08/2021
ms.topic: article
ms.search.form: EcoResProductDetailsExtended, ForecastSales, ForecastPurch, ForecastInvent
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-06-08
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0a7ed310ebdef130b0fb09c5db19397398dc5042
ms.sourcegitcommit: 60afcd85b3b5b9e5e8981ebbb57c0161cf05e54b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/09/2021
ms.locfileid: "6216842"
---
# <a name="inventory-forecasts"></a>Készlet előrejelzések

[!include [banner](../includes/banner.md)]

Ez a témakör azt ismerteti, hogyan lehet készlet-előrejelzéseket megtekinteni és létrehozni. A cikkekhez, cikkcsoportokhoz, cikkfelosztási kulcsokhoz, vevőszámlákhoz, vevőcsoportokhoz, szállítói számlákhoz és szállítócsoportokhoz készlet- és igény-előrejelzési sorokat lehet létrehozni és megtekinteni.

Mindegyik előrejelzési sorhoz ki lehet választani a használt előrejelzési modellt. Ezt követően megadható a cikk vagy cikkcsoport, valamint a mennyiség vagy a tranzakció összege. Az előrejelzési mennyiség felosztásához lehetőség van ütemezés beállítására is.

Az ellátás- és igény-előrejelzési sorok készlet-előrejelzést hoznak létre egy cikk és egy modell ugyanazon kombinációjához. Ez a készlet-előrejelzés egy egyenleget képvisel az ugyanahhoz a cikkhez megadott készlet és igény között. Ezt nem lehet szerkeszteni. A készlet-előrejelzés segít a készletkezelési csoportnak abban, hogy áttekintse egy cikk aktuális készletének várható változásait a következő időszakban, amely már előre lett jelezve.

Miután megadta az igényt és/vagy ellátást előrejelzés-tervezést futtathat a bruttó anyag- és kapacitásigény kiszámítása és a tervezett megrendelések létrehozása érdekében.

## <a name="view-and-manually-enter-forecast-lines"></a><a name="manual-entry"></a>Előrejelzési sorok megtekintése és manuális megadása

Használja ezt a folyamatot a termékek új előrejelzési sorainak manuális létrehozásához.

Az előrejelzési sorok létrehozására vannak más lehetőségek is:

- [Statisztikai kiinduló előrejelzés létrehozása](generate-statistical-baseline-forecast.md).
- [Előzményadatok importálása az igény-előrejelzésekhez](import-historical-data.md).
- [Az előrejelzés létrehozásához a Microsoft Azure Machine Learning webszolgáltatást](demand-forecasting-setup.md) használja.
- [Igény- vagy ellátás-előrejelzési sorok importálása az adatkezelési keretrendszer használatával (ForecastDemandForecastEntryStaging és ForecastSupplyForecastEntryStaging adatentitások)](../../dev-itpro/data-entities/data-entities-data-packages.md).

Ahogy az 1. lépésben található táblázat mutatja, különböző lehetőségek állnak rendelkezésre a használt oldalak elérésére.

1. Attól függően, hogy milyen entitáshoz szeretne előrejelzést létrehozni, és attól függően, hogy milyen típusú előrejelzést szeretne létrehozni, nyissa meg az ellátás, igény vagy készlet-előrejelzési lapot a következő táblázatban leírtak szerint.

    | Entitás | Utasítások |
    |---|---|
    | Kiadott termékek | <ol><li>Kattintson a **Termékinformációk kezelése \> Termékek \> Kiadott termékek** lehetőségre.</li><li>Válassza ki azt a terméket, amelyről előrejelzést kell létrehozni.</li><li>A műveleti panel **Tervezés** lapján, az **Előrejelzés** csoportban válassza az **Igény-előrejelzés**, az **Ellátási előrejelzés** vagy a **Készlet-előrejelzés** lehetőséget a munkához használt előrejelzés típusától függően.</li></ol> |
    | Kiadott termékváltozatok | <ol><li>Kattintson a **Termékinformációk kezelése \> Termékek \> Kiadott termékváltozatok** lehetőségre.</li><li>Válassza ki azt a változatot, amelyről előrejelzést kell létrehozni.</li><li>A műveleti panel **Tervezés** lapján, az **Előrejelzés** csoportban válassza az **Igény-előrejelzés**, az **Ellátási előrejelzés** vagy a **Készlet-előrejelzés** lehetőséget a munkához használt előrejelzés típusától függően.</li></ol> |
    | Cikkcsoportok | <ol><li>Lépjen a **Készletgazdálkodás \> Beállítás \> Készlet \> Cikkcsoportok** pontra.</li><li>Válassza ki azt a cikkcsoportot, amelyről előrejelzést kell létrehozni.</li><li>A műveleti panelen válassz az **Előrejelzés \> Igény**, **Előrejelzés \> Ellátás** vagy az **Előrejelzés \> Készlet-előrejelzés** lehetőséget a munkához használt előrejelzés típusától függően.</li></ol> |
    | Cikkfelosztási kulcsok | <ol><li>Ugrás a következő lehetőségre: **Készletgazdálkodás \> Beállítás \> Előrejelzés**.</li><li>Válassza ki azt a cikkhozzárendelési kulcsot, amelyről előrejelzést kell létrehozni.</li><li>A Művelet ablaktáblán válassza ki az **Igény-előrejelzés** elemet.</li></ol> |
    | Vevők | <ol><li>Ugorjon az **Alaptervezés \> Előrejelzés \> Manuális előrejelzési bejegyzés \> Vásárlók** lehetőségre.</li><li>Válassza ki azt a vásárlót, amelyhez előrejelzést kell létrehozni.</li><li>A Művelet ablaktáblán válassza ki az **Igény-előrejelzés definiálása** elemet.</li></ol> |
    | Vevőcsoportok | <ol><li>Ugorjon az **Alaptervezés \> Előrejelzés \> Manuális előrejelzési bejegyzés \> Ügyfélcsoportok** lehetőségre.</li><li>Válassza ki azt a vásárlót, amelyhez előrejelzést kell létrehozni.</li><li>A Művelet ablaktáblán válassza ki az **Igény-előrejelzés definiálása** elemet.</li></ol> |
    | Szállítók | <ol><li>Ugorjon az **Alaptervezés \> Előrejelzés \> Manuális előrejelzési bejegyzés \> Szállítók** lehetőségre.</li><li>Válassza ki azt a szállítót, amelyhez előrejelzést kell létrehozni.</li><li>A műveleti ablaktáblán válassza ki a **Bevitel** lehetőséget az **Ellátási előrejelzés** oldal megnyitásához.</li></ol> |
    | Szállítói csoportok | <ol><li>Ugorjon az **Alaptervezés \> Előrejelzés \> Manuális előrejelzési bejegyzés \> Szállítócsoportok** lehetőségre.</li><li>Válassza ki azt a szállítócsoportot, amelyhez előrejelzést kell létrehozni.</li><li>A műveleti ablaktáblán válassza ki a **Bevitel** lehetőséget az **Ellátási előrejelzés** oldal megnyitásához.</li></ol> | 
    | Minden sor | <ul><li>A munkához használt előrejelzés típusától függően menjen az **Alaptervezés \> Előrejelzési \> Igényelőrejelzési-sorok** vagy az **Alaptervezés \> Előrejelzés \> Ellátási előrejelzési sorok** menübe.</li></ul> |

    A választástól függően megjelenik az **Ellátási előrejelzés** vagy az **Igény-előrejelzés** lap. A lap megnyitása előtt a kiválasztott rekordhoz már meglévő előrejelzési sorokat jeleníti meg.

1. A műveleti ablaktáblán válassza az **Új** elemet előrejelzési sor rácshoz adásához az oldal felső részén.
1. Az új sor **Modell** mezőjében válassza ki a használni kívánt előrejelzési modellt. Ezután szükség szerint adja meg a további adatokat, például a cikket, a cikkcsoportot, a vevői vagy szállítói számlát vagy csoportot, a cikk mennyiségét vagy a tranzakció teljes összegét. Az **Ellátási előrejelzés** és az **Igény-előrejelzési** lapokon elérhető mezőkkel kapcsolatos részletes információk a témakör későbbi szakaszaiban találhatók.
1. Az előrejelzés adott időszakra való elosztásához válassza az eszköztár **Áttekintés** lapján az **Előrejelzés felosztása** lehetőséget.
1. A **Felosztás** rácson tekintse át időhatárt és az időintervallumokat, amelyek az előre jelzett mennyiségek elosztásához használatosak.

## <a name="supply-forecast-lines"></a>Ellátási előrejelzés sorai

Az ellátási előrejelzéssel tervet lehet létrehozni a megvásárolni szükséges cikkekhez. Közli a beszerzési és forrás adminisztrátorokkal, hogy mit kell rendelniük.

Az ellátási előrejelzést cikk, cikkcsoport, cikkfelosztási kulcs, szállító és szállítócsoport szerint is megadhatja. A különböző entitások és rekordok **Ellátási előrejelzés** oldalának megnyitásával kapcsolatos tudnivalókat lásd a témakör korábbi [Előrejelzési sorok megtekintése és manuális megadása](#manual-entry) szakaszában.

Az **Ellátási előrejelzés** lap felső része az ellátási előrejelzési sorok rácsát és egy lapkészletet biztosít, amely a kiválasztott előrejelzési sor további információinak megtekintésére és beállítására használható. A lap alsó részén a **Felosztás** rács található.

Az alábbi alszakaszok leírják az egyes lapokon elérhető mezőket, valamint a lap munkaablakában és az **Áttekintés** lap eszköztárán elérhető összes parancsot.

### <a name="action-pane-commands-on-the-supply-forecast-page"></a>A Műveleti panel parancsai az Ellátási előrejelzés lapon

A következő táblázat a Művelet panel **Ellátási előrejelzés** oldalán elérhető parancsok leírását tartalmazza.

| Parancs | Leírás |
|---|---|
| Mentés | Mentse az aktuális beállításokat. |
| Szerkesztés | A beállítások engedélyezése a szerkesztendő lapon. |
| Új | Adjon egy előrejelzési sort a felső rácshoz. |
| Eltávolítás | A kijelölt előrejelzési sort távolítsa el a felső rácsból. |
| Előrejelzési egyenlegek | A kiválasztott sor aktuális pénzügyi évre vonatkozó modellazonosítójára számított előrejelzési egyenlegek megtekintése. Az egyenlegek időszak (hónap) szerint vannak felosztva. |
| Pénzforgalmi előrejelzések | A főkönyvbe felosztott előrejelzési tranzakciók megtekintése. További információkért lásd: [Pénzforgalmi előrejelzés](../../finance/cash-bank-management/cash-flow-forecasting.md). |
| Készlet \> Dimenziók megjelenítése | Az **Áttekintés** lapon a rácsban megjelenő készletdimenziók kiválasztása. |

### <a name="toolbar-commands-on-the-overview-tab-of-the-supply-forecast-page"></a>A Ellátási előrejelzés lap Áttekintés lapján található eszköztárparancsok

A következő táblázat az **Ellátási előrejelzés** oldal **Áttekintés** lapjának eszközsorán elérhető parancsok leírását tartalmazza.

| Parancs | Leírás |
|---|---|
| Előrejelzés felosztása | Ha felosztási módszert használ, hozza létre az előrejelzési tranzakció egyéni ütemezési sorait. A program ezután dátum szerint (a kiválasztott időintervallumok szerint), mennyiség és összeg szerint osztja el a sor mennyiségét a teljes időhatáron belül. |
| Tömeges frissítés | Nyissa meg az **Előrejelzési tranzakciók szerkesztése** lapot. (Lásd: [Az előrejelzési tranzakciók tömeges frissítése](#bulk-update) szakaszt a témakör későbbi részében.) |
| Készlet előrejelzése | A **Készlet-előrejelzés** lapnak a kiválasztott cikk-/modellkombinációra szűrt nézetének megnyitása. (Lásd: [Készlet-előrejelzések](#inventory-forecast) szakaszt a témakör későbbi részében.) |
| Cikkszükséglet létrehozása | Egy párbeszédpanel megnyitása, ahol cikkeket, illetve értékesítési rendeléseket vagy cikknaplósorokat hozhat létre a projekthez kapcsolódó előrejelzési tranzakciókhoz. Bár ez a parancs az ellátási előrejelzési sorokhoz és az igény előrejelzési sorokhoz is elérhető, nem használható az **Ellátási előrejelzés** lapon. |

### <a name="the-overview-tab-on-the-supply-forecast-page"></a>A Ellátási előrejelzés lap Áttekintés lapja

Az alábbi táblázat leírja az **Ellátási előrejelzés** oldal **Áttekintés** lapján található mezőket.

| Mező | Leírás |
|---|---|
| **Típus** | A tranzakcióval kapcsolatos előrejelzési modell. |
| **Dátum** | A tranzakció kezdeti dátuma. |
| **Szállítói számla** | A tranzakcióhoz kapcsolódó szállítókód. |
| **Szállítócsoport** | A tranzakcióhoz kapcsolódó szállítói csoport. |
| **Cikkszám** | A cikk azonosítója. |
| **Cikkcsoport** | A tranzakcióhoz társított cikkcsoport. |
| **Cikkfelosztási kulcs** | Az előrejelzéshez rendelt cikkfoglalási kulcs. |
| **Tényleges súly szerinti mennyiség** | Az előrejelzési mennyiség a megadott tényleges súly egységében megadva. |
| **Tényleges súly egysége** | Válassza ki azt az ténylegessúly-egységet, amelyben a cikk beszerzése történt. A program automatikusan a cikkbeállításból olvassa be az értéket. |
| **Mennyiség** | Az előrejelzési mennyiség a megadott beszerzési egységben. |
| **Egység** | Az egységet, amelyben a cikk beszerzése történik. A program automatikusan a cikkbeállításból olvassa be az értéket. Az egységátváltások beállítása esetén azonban módosítható. |
| **Összeg** | A bruttó összeg mínusz az engedmények, amellyel az előrejelzési tranzakció az előrejelzéshez hozzájárul. |
| **Pénznem** | Az előrejelzési tranzakcióhoz használt pénznem. Az alapértelmezett pénznemet a program automatikusan kitölti, de választhat másik pénznemet. |
| (Egyéb dimenziók) | A további dimenziók a rács oszlopaiként jeleníthetők meg. Válassza a **Dimenziók megjelenítése** lehetőséget a Művelet panelen a megjelenítendő dimenziók kiválasztásához. |

### <a name="the-general-tab-on-the-supply-forecast-page"></a>A Ellátási előrejelzés lap Általános lapja

Az **Általános** lap további adatokat is megjeleníti az **Áttekintés** lapon aktuálisan kiválasztott sorról. Az információk egy része az **Áttekintés** lapról lesz megismételve. Az alábbi táblázat az **Általános** lap egyedi mezőit írja le.

| Mező | Leírás |
|---|---|
| Jelentés | Állítsa ezt a lehetőséget *Igen* értékre , hogy a tranzakció szerepeljen a jelentésben. |
| Megjegyzések | Megjegyzést írhat be az előrejelzési tranzakcióról. |
| Aktív | Jelölje be ezt a jelölőnégyzetet, ha azt szeretné, hogy a tranzakció szerepeljen a költségvetési jelentésben. |
| Szerepeltetése pénzforgalmi előrejelzésekben | Jelölje be ezt a jelölőnégyzetet, ha az előrejelzési tranzakciót a főkönyvhöz kívánja lefoglalni. A jelölőnégyzet beállítása nem módosítható jelentési tranzakciók esetében. |
| Áfacsoport | Az előrejelzési tranzakció adójának megadására szolgáló adócsoport. |
| Cikkáfacsoport | Az előrejelzési tranzakció adójának megadására szolgáló cikkadócsoport. |
| Metódus | <p>Az előrejelzési tranzakció felosztához használt módszer kiválasztása:</p><ul><li>**Nincs** – Nem kerül sor felosztásra.</li><li>**Időszak** – az egyes időszakokhoz azonos mennyiség előrejelzése. Ha ezt az értéket választja, adjon meg egy mennyiséget a **/** mezőben, és egy időegységet az **Egység** mezőben.</li><li>**Kulcs** – Az előrejelzett mennyiség felosztása az **Időszakkulcs** mezőben megadott Időszakfelosztási kulcs szerint történik. Ezt a módszert a szezonális eltérések figyelembe vétele esetén célszerű használni.</li></ol>|
| / | <p>Adja meg, hogy hány időszakra előre terjed ki a jövőbe az előrejelzés. Ez a mező csak akkor érhető el, ha az *Időszak* lehetőséget választotta a **Metódus** mezőben.</p><p>Például válassza az *Időszakos* lehetőséget a **Metódus** mezőben, írjon be *1*-et a **Per** mezőbe, és válassza a *Hónapok* lehetőséget az **Egység** mezőben. A **Befejezés** mezőben adja meg a záró dátumot, amely az elkövetkező egy évre terjedhet ki. Ebben az esetben az elkövetkező egy éves időtartam minden hónapjához létrehoz egy előrejelzési sort a fejlécsorban megadott cikk és mennyiség alapján.</p> |
| Egység | Az időintervallum egysége: *Nap*, *Hónap* vagy *Év*. A felosztás ekkor a **Per** mezőben megadott napok, hónapok vagy évek számának felel meg.|
| Időszaki kulcs | Az időszaki felosztási kulcs meghatározása. |
| Vége | A befejezési dátumot adja meg, ha a **Per** és **Egység** mezőket használja. |

### <a name="the-item-tab-on-the-supply-forecast-page"></a>A Ellátási előrejelzés lap Cikk lapja

A **Cikk** lap kiválasztásával megtekintheti az **Áttekintés** lapon aktuálisan kiválasztott sorra vonatkozó további cikkinformációkat.

A **Cikk** lap tetején lévő rács az **Áttekintés** lapon is megjelenő cikkadatokat ismétli. Ezenkívül tartalmazza az **Egységár** mezőt is, amely az **Egység** mezőben megadott számú egység beszerzési árát mutatja. A rendszer az egységárat automatikusan átveszi a cikkbeállításból, de ez módosítható.

A rács alatti mezők további cikkadatokat tartalmaznak. Eze információk egy része az **Áttekintés** lapról lesz megismételve. Az alábbi táblázat a **Cikk** lap egyedi mezőit írja le.

| Mező | Leírás |
|---|---|
| Áregység | Az egységek száma, amelyekre a mennyiség vonatkozik. A rendszer automatikusan átveszi ezt az értéket a Cikkek táblából, de módosítható. |
| Beszerzések költségei | A beszerzési árral kapcsolatos állandó költségek. A költségek függetlenek a mennyiségtől. |
| Engedmény százaléka | Az engedmény százalékos kulcsa. |
| Engedmény összege | Értékesítési egységenkénti összegben kifejezett engedmény. |
| Bruttó összeg | Az az összeg, amikor nem alkalmaznak engedményeket. |
| Mennyiség | Tranzakció mennyisége a cikk készletegységében. |
| Részanyagjegyzék | Egy meghatározott részanyagjegyzék anyagjegyzékszáma. |
| Részútvonal | A megadott részútvonal útvonalszáma. |

### <a name="the-financial-dimensions-tab-on-the-supply-forecast-page"></a>A Ellátási előrejelzés lap Pénzügyi dimenziók lapja

A **Pénzügyi dimenziók** lapon látható az **Áttekintés** lapon jelenleg kiválasztott sor összes pénzügyidimenzió-értéke.

### <a name="the-inventory-dimensions-tab-on-the-supply-forecast-page"></a>A Ellátási előrejelzés lap Készletdimenziók lapja

A **Készletdimenziók** lapon látható az **Áttekintés** lapon jelenleg kiválasztott sor összes készletdimenzió-értéke.

### <a name="the-allocation-grid-on-the-supply-forecast-page"></a>A Ellátási előrejelzés lap Felosztás rácsa

Ha cikkfelosztási kulcsot használ, vagy egy vagy több jövőbeli időszakra vonatkozóan adott meg cikk-előrejelzést, az **Előrejelzés felosztása** lehetőség kiválasztásával az **Áttekintés** lap eszközsorán feloszthatja az előrejelzést. A program ezután úgy osztja el a mennyiséget, ahogy a **Felosztási** rács sorai jelzik.

## <a name="demand-forecast-lines"></a>Igény-előrejelzés sorai

Az igény-előrejelzés segítségével lehet megadni vagy generálni egy vevőre vonatkozó igényt. Segít az értékesítési és marketing adminisztrátorok számára, hogy tájékoztassák az alaptervezési adminisztrátorokat a következő előrejelzési időszakban várható igényről.

Az igényelőrejelzést cikk, cikkcsoport, cikkfelosztási kulcs, vásárló és vásárlócsoport szerint is megadhatja. A különböző entitások és rekordok **Igényelőrejelzés** oldalának megnyitásával kapcsolatos tudnivalókat lásd a témakör korábbi [Előrejelzési sorok megtekintése és manuális megadása](#manual-entry) szakaszában.

Az **Igényelőrejelzés** lap felső része az igényelőrejelzési sorok rácsát és egy lapkészletet biztosít, amely a kiválasztott előrejelzési sor további információinak megtekintésére és beállítására használható. A lap alsó részén a **Felosztás** rács található.

Az alábbi alszakaszok leírják az egyes lapokon elérhető mezőket, valamint a lap munkaablakában és az **Áttekintés** lap eszköztárán elérhető összes parancsot.

### <a name="action-pane-commands-on-the-demand-forecast-page"></a>A Műveleti panel parancsai az Igényelőrejelzés lapon

A következő táblázat a Művelet panel **Igényelőrejelzés** oldalán elérhető parancsok leírását tartalmazza.

| Parancs | Leírás |
|---|---|
| Mentés | Mentse az aktuális beállításokat. |
| Szerkesztés | A beállítások engedélyezése a szerkesztendő lapon. |
| Új | Adjon egy előrejelzési sort a felső rácshoz. |
| Eltávolítás | A kijelölt előrejelzési sort távolítsa el a felső rácsból. |
| Előrejelzési egyenlegek | A kiválasztott sor aktuális pénzügyi évre vonatkozó modellazonosítójára számított előrejelzési egyenlegek megtekintése. Az egyenlegek időszak (hónap) szerint vannak felosztva. |
| Pénzforgalmi előrejelzés | A főkönyvbe kötelezően felosztott előrejelzési tranzakciók megtekintése. További információkért lásd: [Pénzforgalmi előrejelzés](../../finance/cash-bank-management/cash-flow-forecasting.md). |
| Dimenziók megjelenítése | Az **Áttekintés** lapon a rácsban megjelenő termék-, tárolás- és készletdimenziók kiválasztása. |
| Főkönyv előnézete | A kijelölt tranzakció főkönyvi bejegyzéseinek megtekintése. |
| Árajánlati sorok átvitele | Az ajánlati sorok áthelyezése a kiválasztott projektbe. |

### <a name="toolbar-commands-on-the-overview-tab-of-the-demand-forecast-page"></a>Az Igényelőrejelzés lap Áttekintés lapján található eszköztárparancsok

A következő táblázat az **Igényelőrejelzés** oldal **Áttekintés** lapjának eszközsorán elérhető parancsok leírását tartalmazza.

| Parancs | Leírás |
|---|---|
| Előrejelzés felosztása | Ha felosztási módszert használ, hozza létre az előrejelzési tranzakció egyéni ütemezési sorait. A program ezután dátum szerint (a kiválasztott időintervallumok szerint), mennyiség és összeg szerint osztja el a sor mennyiségét a teljes időhatáron belül. |
| Tömeges frissítés | Nyissa meg az **Előrejelzési tranzakciók szerkesztése** lapot. (Lásd: [Az előrejelzési tranzakciók tömeges frissítése](#bulk-update) szakaszt a témakör későbbi részében.) |
| Készlet előrejelzése | A **Készlet-előrejelzés** lapnak a kiválasztott cikk-/modellkombinációra szűrt nézetének megnyitása. (Lásd: [Készlet-előrejelzések](#inventory-forecast) szakaszt a témakör későbbi részében.) |
| Cikkszükséglet létrehozása | Egy párbeszédpanel megnyitása, ahol cikkeket, illetve értékesítési rendeléseket vagy cikknaplósorokat hozhat létre a projekthez kapcsolódó előrejelzési tranzakciókhoz. |

### <a name="the-overview-tab-on-the-demand-forecast-page"></a>A Igényelőrejelzés oldal Áttekintés lapja

Az alábbi táblázat leírja az **Igényelőrejelzés** oldal **Áttekintés** lapján található mezőket.

| Mező | Leírás |
|---|---|
| **Feladat neve** | A kötegfeladat neve, amelyet az előrejelzési sor létrehozásához használtak. |
| **Típus** | A tranzakcióval kapcsolatos előrejelzési modell. |
| **Dátum** | A tranzakció kezdeti dátuma. |
| **Vevőkód** | A tranzakcióhoz kapcsolódó vásárlói fiók. |
| **Vevőcsoport** | A tranzakcióhoz kapcsolódó vásárlócsoport. |
| **Cikkszám** | A cikk azonosítója. |
| **Terméknév** | A cikk leírása. |
| **Cikkfelosztási kulcs** | A készlet-előrejelzési felosztás során használt cikkfelosztási kulcs. |
| **Értékesítési mennyiség** | A tranzakciós mennyiség a megadott értékesítési egységben. |
| **Egység** | A cikk eladásakor használt egység. |
| **Összeg** | A bruttó összeg az engedmények nélkül, amellyel az előrejelzési tranzakció az előrejelzéshez hozzájárul. |
| **Eladási ár** | Az **Áregység** mezőben megadott számú egység eladási ára. A rendszer az információt átveszi a cikkbeállításból, de módosítható. |
| **Értékesítés pénzneme** | Az előrejelzési tranzakcióhoz használt pénznem. Az alapértelmezett pénznemet a program automatikusan kitölti, de választhat másik pénznemet. |
| **Tényleges súly szerinti mennyiség** | Az előrejelzési mennyiség a megadott tényleges súly egységében megadva. |
| **Tényleges súly egysége** | Válassza ki azt az ténylegessúly-egységet, amelyben a cikk értékesítése történik. A program automatikusan a cikkbeállításból olvassa be az értéket. |
| (Egyéb dimenziók) | A további termék, tárolási és követést dimenziók a rács oszlopaiként jeleníthetők meg. Válassza a **Dimenziók megjelenítése** lehetőséget a Művelet panelen a megjelenítendő dimenziók kiválasztásához. |

### <a name="the-general-tab-on-the-demand-forecast-page"></a>Az Igényelőrejelzés lap Általános lapja

Az **Általános** lap további adatokat is megjeleníti az **Áttekintés** lapon aktuálisan kiválasztott sorról. Az információk egy része az **Áttekintés** lapról lesz megismételve. Az alábbi táblázat az **Általános** lap egyedi mezőit írja le.

| Mező | Leírás |
|---|---|
| Igény-előrejelzés sorszáma | Az igényelőrejelzési sor egyedi száma. Ez a szám az igény-előrejelzésekhez az **Alaptervezés paraméterei** oldalon kiválasztott számsorozat alapján jön létre. |
| Cikkcsoport | A tranzakcióhoz társított cikkcsoport. |
| Jelentés | Állítsa ezt a lehetőséget *Igen* értékre , hogy a tranzakció szerepeljen a jelentésben. |
| Megjegyzések | Megjegyzést írhat be az előrejelzési tranzakcióról. |
| Aktív | Jelölje be ezt a jelölőnégyzetet, ha azt szeretné, hogy a tranzakció szerepeljen a költségvetési jelentésben. A jelölőnégyzet beállítása nem módosítható jelentési tranzakciók esetében. |
| Szerepeltetése pénzforgalmi előrejelzésekben | Jelölje be ezt a jelölőnégyzetet, ha az előrejelzési tranzakciót a főkönyvhöz kívánja lefoglalni. A jelölőnégyzet beállítása nem módosítható jelentési tranzakciók esetében. További információkért lásd: [Pénzforgalmi előrejelzés](../../finance/cash-bank-management/cash-flow-forecasting.md). |
| Áfacsoport | Az előrejelzési tranzakció adójának megadására szolgáló adócsoport. |
| Cikkáfacsoport | Az előrejelzési tranzakció adójának megadására szolgáló cikkadócsoport. |
| Metódus | <p>Az előrejelzési tranzakció felosztához használt módszer kiválasztása:</p><ul><li>**Nincs** – Nem kerül sor felosztásra.</li><li>**Időszak** – az egyes időszakokhoz azonos mennyiség előrejelzése. Ha ezt az értéket választja, adjon meg egy mennyiséget a **/** mezőben, és egy időegységet az **Egység** mezőben.</li><li>**Kulcs** – Az előrejelzett mennyiség felosztása az **Időszakkulcs** mezőben megadott Időszakfelosztási kulcs szerint történik. Ezt a módszert a szezonális eltérések figyelembe vétele esetén célszerű használni.</li><ul>|
| / | <p>Adja meg, hogy hány időszakra előre terjed ki a jövőbe az előrejelzés. Ez a mező csak akkor érhető el, ha az *Időszak* lehetőséget választotta a **Metódus** mezőben.</p><p>Például válassza az *Időszakos* lehetőséget a **Metódus** mezőben, írjon be *1*-et a **Per** mezőbe, és válassza a *Hónapok* lehetőséget az **Egység** mezőben. A **Befejezés** mezőben adja meg a záró dátumot, amely az elkövetkező egy évre terjedhet ki. Ebben az esetben az elkövetkező egy éves időtartam minden hónapjához létrehoz egy előrejelzési sort a fejlécsorban megadott cikk és mennyiség alapján. |
| Egység | Az időintervallum egysége: *Nap*, *Hónap* vagy *Év*. A felosztás ekkor a **Per** mezőben megadott napok, hónapok vagy évek számának felel meg.|
| Időszaki kulcs | Adja meg az előrejelzés felosztása során használt időszaki felosztási kulcsot. További információ: [Költségvetés-tervezés – adatok megadása](../../finance/budgeting/budget-planning-data-allocation.md). |
| Vége | A befejezési dátumot adja meg, ha a **Per** és **Egység** mezőket használja. |

### <a name="the-item-tab-on-the-demand-forecast-page"></a>A Igényelőrejelzés lap Cikk lapja

A **Cikk** lap további adatokat is megjeleníti az **Áttekintés** lapon aktuálisan kiválasztott sorról. Az információk egy része az **Áttekintés** lapról lesz megismételve. Az alábbi táblázat a **Cikk** lap egyedi mezőit írja le.

| Mező | Leírás |
|---|---|
| Áregység | Az értékesítési egységek száma, amelyekre az eladási ár vonatkozik. A rendszer automatikusan átveszi ezt az értéket a Cikkek táblából, de módosítható. |
| Értékesítési költségek | Az eladási árral kapcsolatos állandó költségek. A költségek függetlenek a mennyiségtől. |
| Önköltségi ár | Az aktuális előrejelzési tranzakció egy készletegységre jutó költsége. A rendszer átveszi az értéket a Cikkek táblából, de módosítható. |
| Engedmény százaléka | Az engedmény százalékos kulcsa. |
| Engedmény összege | Értékesítési egységenkénti összegben kifejezett engedmény. |
| Bruttó összeg | Az az összeg, amikor nem alkalmaznak engedményeket. |
| Készletmennyiség | Tranzakció mennyisége a cikk készletegységében. |
| Konkrét anyagjegyzék használata | A megadott anyagjegyzék anyagjegyzékszáma. |
| Konkrét útvonal használata | A megadott részútvonal útvonalszáma. |

### <a name="the-project-tab-on-the-demand-forecast-page"></a>Az Igényelőrejelzés lap Projekt lapja

A **Projekt** lap további projektinformációkat is megjeleníti az **Áttekintés** lapon aktuálisan kiválasztott sorról. Az információk egy része az **Áttekintés**, **Általános** vagy **Cikk** lapról lesz megismételve. Az alábbi táblázat a **Projekt** lap egyedi mezőit írja le.

| Mező | Leírás |
|---|---|
| Projekt dátuma | Az igényelőrejelzési tranzakció feladási dátuma. |
| Projektazonosító | Annak a projektnek az azonosítója, amelyre az aktuális tranzakció hivatkozik. |
| Finanszírozási forrás | Az igényelőrejelzéshez kapcsolódó finanszírozási forrás. |
| Tevékenységszám | Az igényelőrejelzés-tranzakcióhoz társított tevékenység. |
| Kategória | Az aktuális tranzakció költségkategóriája. |
| Sortulajdonság | Az az állapot, amelyhez a tranzakció csatolva van. |
| Tranzakció azonosítója | Az igény-előrejelzési tranzakció rendszerazonosítója. |
| Költség összege | Az igényelőrejelzési tranzakció mennyisége. |
| Egységár | Az egységár. |
| Módosította | A kijelölt tranzakciót legutóbb módosító dolgozó azonosítója. |
| Számla dátuma | A várható számladátum megadása. |
| Eltávolítás dátuma | Tekintse meg, vagy módosítsa az eltávolítási dátumot. Az előrejelzés létrehozásakor a program a projekt záró dátumára állítja be az eltávolítási dátumot. Ha a projektnek nincs záró dátuma, akkor a program a projektdátumot alkalmazza. Ez a mező csak a kötött árú projektekre és a beruházási projektekre vonatkozik. |
| Költség kifizetési dátuma | A költség várható kifizetési dátumának megadása. |
| Értékesítési kifizetés dátuma | Az értékesítési kifizetésének várható dátumát adja meg itt. |

### <a name="the-financial-dimensions-tab-on-the-demand-forecast-page"></a>Az Igényelőrejelzés lap Pénzügyi dimenziók lapja

A **Pénzügyi dimenziók** lapon látható az **Áttekintés** lapon jelenleg kiválasztott sor összes pénzügyidimenzió-értéke.

### <a name="the-inventory-dimensions-tab-on-the-demand-forecast-page"></a>Az Igényelőrejelzés lap Készletdimenziók lapja

A **Készletdimenziók** lapon látható az **Áttekintés** lapon jelenleg kiválasztott sor összes készletdimenzió-értéke.

### <a name="the-allocation-grid-on-the-demand-forecast-page"></a>Az Igényelőrejelzés lap Felosztás rácsa

Ha cikkfelosztási kulcsot használ, vagy egy vagy több jövőbeli időszakra vonatkozóan adott meg cikk-előrejelzést, az **Előrejelzés felosztása** lehetőség kiválasztásával az **Áttekintés** lap eszközsorán feloszthatja az előrejelzést. A program ezután úgy osztja el a mennyiséget, ahogy a **Felosztási** rács sorai jelzik.

## <a name="inventory-forecast"></a><a name="inventory-forecast"></a>Készlet előrejelzése

A készletek és igények előrejelzési soraihoz tartozik **Készletelőrejelzés** gomb, amely egy nézetet nyit meg a **Készlet-előrejelzés** lapról, amely szűrést tartalmaz ugyanannak a cikk-/modellkombinációnak a számára. A készlet-előrejelzés egyensúlyt képvisel az ugyanahhoz a cikkhez megadott készlet és igény között. Ezt nem lehet szerkeszteni. A készlet-előrejelzés segít a készletkezelési csoportnak abban, hogy áttekintse egy cikk aktuális készletének várható változásait a következő időszakban, amely már előre lett jelezve.

### <a name="the-action-pane-on-the-inventory-forecast-page"></a>A Műveleti panel parancsai a Készletelőrejelzés lapon

A következő táblázat a Művelet panel **Igényelőrejelzés** oldalán elérhető parancsok leírását tartalmazza.

| Művelet | Leírás |
|---|---|
| Ellátási előrejelzés | Az **Ellátási előrejelzés** lapnak ugyanazon cikk-/modell/dátumkombinációra szűrt nézetének megnyitása. |
| Igény-előrejelzés | Az **Igény-előrejelzés** lapnak ugyanazon cikk-/modell/dátumkombinációra szűrt nézetének megnyitása. |
| Készlet \> Dimenziók megjelenítése | Az **Áttekintés** rácsban megjelenő termék-, tárolás- és készletdimenziók kiválasztása. |

### <a name="the-grid-on-the-inventory-forecast-page"></a>A rács a Készletelőrejelzés lapon

A következő táblázat a **Készlet-előrejelzés** oldal rácsának mezőit írja le.

| Mező | Leírás |
|---|---|
| **Típus** | A tranzakcióval kapcsolatos előrejelzési modell. |
| **Cikkszám** | A cikk azonosítója. |
| **Költségvetés dátuma** | Az előrejelzési tranzakció feladási dátuma. |
| **Előrejelzés típusa** | A tranzakció forrása (*Igény-előrejelzés* vagy *Ellátási előrejelzés*). |
| **Tényleges súly szerinti mennyiség** | Az előrejelzési mennyiség a tényleges súly egységében megadva. |
| **Mennyiség** | Az előrejelzett mennyiség készletegységben. |
| **Halmozott tényleges súly** | A halmozott előrejelzési mennyiség a tényleges súly egységében, amikor ugyanannak a cikknek több előrejelzési sora a gyűlt össze. |
| **Részanyagjegyzék** | A megadott részanyagjegyzék anyagjegyzékszáma. |
| **Részútvonal** | A megadott részútvonal útvonalszáma. |
| (Egyéb dimenziók) | A további dimenziók a rács oszlopaiként jeleníthetők meg. Válassza a **Készlet \> Dimenziók megjelenítése** lehetőséget a Művelet panelen a megjelenítendő dimenziók kiválasztásához. |

## <a name="bulk-update-forecast-transactions"></a><a name="bulk-update"></a>Előrejelzési tranzakciók tömeges frissítése

Használja ezt az eljárást a meglévő előrejelzési tranzakciósorok feldolgozásához. Az előrejelzési tranzakciósorok másolhatók, szerkeszthetők és törölhetők.

1. A készlet- vagy igény-előrejelzési sorok lapon válassza a **Tömeges frissítés** lehetőséget.
1. Kattintson az párbeszédpanelen a **Szűrés** gombra.
1. A **Tartomány** lapon adja meg azokat a feltételeket, amelyek azonosítják a másolni, szerkeszteni vagy törölni kívánt előrejelzési forrásadatokat. Az adatok között lehet például az előrejelzési modell, a cikkszám és a vevőfiók.
1. A kiválasztás jóváhagyásához kattintson az **OK** gombra.

    Az adatok kiválasztása után az **Előrejelzési tranzakciók szerkesztése** párbeszédpanelen megadhatja, hogy hogyan szeretné másolni, szerkeszteni vagy törölni az adatokat.

    > [!NOTE]
    > A szűrési lépés előfeltétele a **Tömeges szerkesztés** funkció használatának. Ha kihagyja, a program az **összes** előrejelzési sort kijelöli és frissíti. Emiatt előfordulhat, hogy a tranzakciók véletlenül ismétlődéseket vagy eltávolításokat okoznak.

1. A **Kezelés** szakaszban adja meg, hogy másolni, frissíteni vagy törölni szeretné-e a kiválasztott előrejelzési tranzakciókat.
1. A **Módosítások a mezőben** szakasz segítségével módosíthatja az előrejelzés paramétereit. Jelölje be a megfelelő paraméter jelölőnégyzetét, majd válasszon a rendelkezésre álló lehetőségek közül. Például jelölje be a **Modell** jelölőnégyzetet, majd válassza ki az előrejelzési modell számát. A kijelölt előrejelzési modellhez a meglévő előrejelzési sorok másolódnak.
1. Az **Időszakváltás** szakasz használatával az előrejelzés kezdő és záró dátumát előre és hátra mozgathatja. Jelölje be a jelölőnégyzetet, majd a mennyiség és időszak mezők segítségével határozza meg hogyan legyenek áthelyezve az előrejelzési dátumok. Negatív mennyiséget is be lehet írni, ha a kezdő dátumot előre kell hozni (tehát korábbra).

    Ha például hat hónappal késleltetni kell az előrejelzési tranzakció kezdő dátumát, jelölje be a jelölőnégyzetet, írja be a *6*-ot mennyiségként, és válassza az *Hónapok* lehetőséget időszaknak.

1. A **Mező helyesbítése** szakaszban frissítheti az aktuális előrejelzési adatokat. A **Mező** mezőben válassza ki azt a feltételt, amelyet módosítani szeretne. A **Tényező** mezőben adja meg azt a szorzótényezőt, amellyel a kiválasztott feltételre alkalmazni szeretne, vagy adjon meg egy hozzáadandó vagy kivonandó konstanst. Például válassza feltételként a *Mennyiség* feltételt, és adjon meg egy *1,5*-ös szorzótényezőt a cikk mennyiségének 1,5-tel történő szorzásához. Másik lehetőségként cikkmennyiség 25 egységgel történő csökkentéséhez adjon meg egy *-25*-ös konstanst.
1. Az előrejelzési sorok pénzügyi dimenzióinak frissítésére használja a **Pénzügyi dimenziók** szakaszt. Válassza ki a módosítani kívánt pénzügyi dimenziókat, majd adja meg a kiválasztott dimenziókra alkalmazandó értéket.
1. A módosítások alkalmazásához kattintson az **OK** gombra.

## <a name="run-forecast-planning"></a>Előrejelzési tervezés futtatása

Miután megadta az igény-előrejelzést és/vagy ellátási előrejelzés-tervezést futtathat a bruttó anyag- és kapacitásigény kiszámítása és a tervezett megrendelések létrehozása érdekében.

1. Ugrás az **Alaptervezés \> Előrejelzési tervezés \> helyre**.
1. Az **Előrejelzési terv** mezőben válasszon egy előrejelzési tervet.
1. A **Feldolgozási idő nyomon követése** engedélyezésével az egyes tervezési feladatok feldolgozási időtartamát rögzítheti.
1. Adjon meg egy értéket a **Szálak száma** mezőben. (További tájékoztatás: [Alaptervezés teljesítményének javítása](master-planning-performance.md).)
1. A **Megjegyzés** mezőben adja meg a szöveget a szükséges további adatok rögzítéséhez.
1. A **Szerepeltetni kívánt rekordok** gyorslapján válassza a **Szűrő** parancsot, hogy korlátozza az elemek kiválasztását.
1. A **Futtatás a háttérben** gyorslapon adja meg a köteg paramétereit.
1. Válassza ki az **OK** lehetőséget.

A kiszámított követelmények megtekintéséhez nyissa meg a **Bruttó szükséglet** lapot. Például a **Kiadott termékek** oldalon, a **Terv** lapon, a **Követelmények** szakaszban válassza a **Bruttó követelmény** lehetőséget.

A létrehozott tervezett rendelések megtekintéséhez menjen az **Alaptervezés \> Közös \> Tervezett rendelések** menübe és válassza ki a megfelelő előrejelzési tervet.

## <a name="additional-resources"></a>További erőforrások

- [Igény-előrejelzés áttekintése](introduction-demand-forecasting.md)
- [Igény-előrejelzés beállítása](demand-forecasting-setup.md)
- [Statisztikai kiinduló előrejelzés létrehozása](generate-statistical-baseline-forecast.md)
- [A kiinduló előrejelzés manuális kiigazítása](manual-adjustments-baseline-forecast.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
