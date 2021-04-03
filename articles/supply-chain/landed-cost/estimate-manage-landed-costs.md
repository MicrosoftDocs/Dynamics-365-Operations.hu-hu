---
title: Partraszállítási költségek becslése és kezelése
description: A rendszer az automatikus költségbeállítás alapján határozza meg a partraszállítási költséget. Ez a témakör bemutatja, hogy hogyan lehet pontosabb becslést adni különböző helyzetek megadásával.
author: sherry-zheng
manager: tfehr
ms.date: 01/26/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ITMCostTemplateTable, ITM CostEstimateDialog, ITMCostEstimateTable, SysOperationTemplateForm
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-01-26
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: cbd652f2b29f7a78ad9e4e1d3dda4a3ef8a9f3f3
ms.sourcegitcommit: 2b4809e60974e72df9476ffd62706b1bfc8da4a7
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/04/2021
ms.locfileid: "5501270"
---
# <a name="estimate-and-manage-landed-costs"></a>Partraszállítási költségek becslése és kezelése

[!include [banner](../../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

A rendszer az [automatikus költségbeállítás](auto-cost-setup.md) alapján határozza meg a partraszállítási költséget. Emellett pontosabb becslést adhat különböző helyzetek megadásával. Ezeket az eseteket tárolja a alkalmazás. Ezeket később áttekintheti, és összevetheti a jelentés tényadataival. A cikk árát is frissítheti.

## <a name="set-up-cost-estimates"></a>Költségbecslések beállítása

### <a name="set-up-cost-templates"></a>Költségsablonok beállítása

A költségsablonok olyan alapértelmezett beállításokat hoznak létre, amelyekről a becslést kapó felhasználók nem feltétlenül tudnak. A sablonok segítségével csökkenthető a becslési folyamat összetettsége, azáltal, hogy minimálisra csökkentik azokat a kiválasztásokat, amelyek alapján a felhasználóknak pontos becslést kell kapniuk. Ha az elszámolóáras modellt használja, a költségsablonokat az áruk költségének beállítása közben használhatja.

A költségsablonok beállításához kattintson a **Partraszállítási költségek \> Költségszámítás beállítása \> Költségsablonok** gombra. A **Költségsablonok** oldalon a bal oldali listaablak az összes aktuális költségsablont mutatja. A Művelet panel gombjaival sablonokat hozhat létre, törölhet és szerkeszthet.

Az alábbi táblázat bemutatja az egyes sablonokhoz rendelkezésre álló mezőket.

| Mező | Leírás |
|---|---|
| Költségsablon | Adjon egy egyedi nevet a költségsablonhoz. A név általában a sablon tényezőjét vagy költségszorzóját írja le. |
| Leírás | A költségsablon leírásának megadása. |
| Szállítmányozási vállalat | Válassza ki azt a szállítmányozó vállalatot, amely a sablon használata esetén alkalmazandó. |
| Szállítás módja | Válassza ki a szállítási módot (például tengeri vagy légi szállítás), amelyet alkalmazni kell a sablon használata esetén. Ez a mező segít meghatározni a költségbecslésben az árukhoz kapcsolódó automatikus költségeket. |
| Szállítási konténer típusa | Válassza ki azt a szállítókonténer típusát, amely a sablon használata esetén alkalmazandó. Ez a mező segít meghatározni a költségbecslésben az árukhoz kapcsolódó automatikus költségeket. |
| Vámügynök | A vámügynök (szállító), amely a sablon használata esetén alkalmazandó. Ez a mező segít meghatározni a költségbecsléshez kapcsolódó automatikus költségeket. |
| Szorzó | Adja meg azt a szorzót (százalék), amely automatikusan alkalmazandó a költségbecslésre a sablon használata esetén. Ha például 10 százalékot szeretne hozzáadni a számított költségbecsléshez, *1,10*-et adjon meg. |

### <a name="create-a-cost-estimate"></a>Költségbecslés létrehozása

A **Költségbecslés** párbeszédpanelen új költségbecslést generálhat, amely a kiválasztott költségsablonon, kiválasztott cikkhalmazon és az utazás egyéb adatain alapul. Ezek a beállítások ezután meghatározzák az áruk becsült partraszállítási költségét. Ezek a költségbecslések elsősorban az elszámolóáras cikkekhez használatosak. Ha a becsült partraszállítási költséget hozzáadja a készletben meglévő áruk elszámolóáraihoz, akkor kisebb különbözeti tranzakciók merülnek fel, amikor az árukat hozzáadják egy hajóúthoz, mivel az elszámolóár tükrözi ezeknek a partraszállítási költségeknek a becslését.

A **Költségbecslés** párbeszédpanel megnyitásához lépjen a **Partraszállítási költség \> Időszakos feladatok \> Költségbecslés** lehetőségre. Ezután állítsa be a következő alszakaszokban leírt mezőket. A becslés létrehozásához végül válassza az **OK** elemet. Ezt követpen megjelenik a **Költségbecslés** oldal (**Partraszállítási költség \> Lekérdezések \> Költségbecslések**), és megjeleníti az új becslést, amint azt a témakör későbbi része ismerteti.

### <a name="settings-on-the-parameters-tab"></a>Beállítások a Paraméterek lapon

A következő táblázat felsorolja azokat a mezőket, amelyek elérhetők a **Költségbecslés** párbeszédpanel **Paraméterek** lapján.


| Mező | Leírás |
|---|---|
| Költségsablon | Válasszon ki egy költségsablont. A rendszer a kiválasztott sablonhoz társított beállításokat használja az alkalmazott automatikus költségek meghatározásához. |
| Becsült dátum | Alapértelmezés szerint a mező a mai dátumra van beállítva, de az érték megváltoztatható. A megadott dátum lesz használva a megfelelő eladási árak, beszerzési árak, automatikus költségek és az átváltási árfolyam kiválasztására, amennyiben egy szállítási árfolyam van használatban. |
| Mértékegység | A költségek a mértéktől függhetenek. Például légi fuvar használata esetén előfordulhat, hogy a volumtrikus árazás érvényes. Ha a költség egy mértéktől függ, adja meg annak értékét. Ellenkező esetben javasoljuk, hogy ezt a mezőt *1* értékre állítsa, hacsak nem biztos abban, hogy nem történik arányosítás a mérték segítségével. Adjon meg egy tizedes értéket. Az egység az az egység, amely a vonatkozó automatikus költségrekordban meg van határozva. |
| Utazássablon | Válasszon ki egy [hajóútsablont](multi-leg-journey-setup.md). Ez a mező az alkalmazandó automatikus költségek helyes meghatározására használható. |
| Kiindulási kikötő | Az a kikötő, amelyből a cikkeket szállítani fogják. Ez a mező a kiválasztott hajóútsablon alapján van beállítva. |
| Célkikötő | Az a kikötő, amelybe a cikkeket szállítani fogják. Ez a mező a kiválasztott hajóútsablon alapján van beállítva. |
| Pénznem | Válassza ki a cikkek vásárlásának pénznemét. |
| Tárolók | Ha jellemzően több konténert használnak, adja meg a konténerek számát. A rendszer ezt követően a költségek becslésekor több konténer költségét használja. |
| Ívlapok | Ha jellemzően több levele van, adja meg a mennyiséget. (A mennyiség általában *1*.) |
| Hely | Adja meg azt a helyet, ahová az árut szállítani fogják. |

### <a name="settings-on-the-items-tab"></a>Beállítások a Cikkek lapon

A **Cikkek** lapon annyi cikket adhat hozzá a becsléshez, amennyit csak szeretne. Az eszköztár segítségével cikkeket adhat hozzá a rácshoz, illetve eltávolíthat cikkeket. Válassza az eszköztár **Készlet \> Dimenziók megjelenítése** elemét egy párbeszédpanel megnyitásához, ahol dimenzióoszlopokat adhat hozzá a rácshoz, vagy eltávolíthatja az oszlopokat.

Az alábbi táblázat bemutatja az egyes cikkekhez rendelkezésre álló mezőket.

| Mező | Leírás |
|---|---|
| Cikkszám | Válassza ki azt a cikket, amelyhez meghatározza az árat. (Ha a cikk még nem létezik a rendszerben, hozzon létre egy üres cikket, igény szerint csatolja egy hajóút cikk-költségcsoporjához, majd hagyja üresen az árat, vagy hozza létre vagy módosítsa az árat.) |
| Szállítói számla | A cikk becsléséhez használt szállító kiválasztása. Ha a cikkhez alapértelmezett szállító van hozzárendelve, ez a mező automatikusan be van állítva. |
| Mennyiség | Válassza ki a beszerezni kívánt mennyiséget. |
| Önköltségi ár | A rendszer az árképzési szabályok alapján keres kiindulási árat, de ez az ár szükség esetén felülbírálható. |
| Eladási ár | Adja meg az áruk várt eladási árát. |
| Mértékegység | Adja meg az áruk mértékének tizedesértékét. Az egység az az egység, amely be van állítva a vonatkozó kiadott termékhez. |
| Cikk súlyának/térfogatának frissítése | Jelölje be ezt a jelölőnégyzetet, ha frissíteni kell a kiadott termék súlyát vagy térfogatát úgy, hogy megfeleljen az ebben a sorban megadott **Mérték** értékének. |
| (Egyéb dimenziók) | A kiválasztott dimenzióktól függően az egyes cikkekre vonatkozó további információoszlopok is láthatók. |

Egy cikk térfogatának és/vagy súlyának megtekintéséhez vagy módosításához jelölje ki a cikket a rácsban, majd használja az oldal alján található mezőket.

## <a name="manage-estimated-costs"></a>Becsült költségek kezelése

A létrehozott költségbecslések megtekintéséhez és szerkesztéséhez kattintson a **Partraszállítási költség \> Lekérdezések \> Költségbecslések** elemre. A **Költségbecslések** oldalon a bal oldali listaablak az összes aktuális költségbecslést mutatja. A Művelet panel gombjaival kezelhet egy kiválasztott becslést. Ne feledje, hogy a **Költségbecslések** oldalon nem hozhat létre új költségbecslést. Ehelyett használja a **Költségbecslés** párbeszédpanelt (**Partraszállítási költség \> Időszakos feladatok \> Költségbecslés**) a témakörben korábban ismertetett módon.

A **Költségbecslés** oldal bemutatja, hogyan származtatták az egyes becsült költségeket. Az egyes cikkek becsült partraszállítási költségét is megjeleníti. A költségbecslések a különféle árukhoz társított önköltségi ár és/vagy pénznem módosításával módosíthatók. A kapcsolódó hajóútköltségek a hajóút és a konténer szintjén is módosíthatók. Ha ezen a lapon módosítja a költségeket, akkor a program felkéri a költségbecslésben található cikkek becsült költségeinek újraszámítására. Ha készen áll, a becslések segítségével frissítheti a költségsablonban található cikkek önköltségi árát.

### <a name="information-on-the-header"></a>Információk a fejlécben

A **Költségbecslés** oldal felső része azokat a beállításokat jeleníti meg, amelyek a kiválasztott költségbecslés létrehozásához voltak használva, az előző szakaszban leírtak szerint. 

### <a name="settings-and-buttons-on-the-lines-fasttab"></a>A Sorok gyorslap beállításai és gombjai

A **Sorok** gyorslap felsorolja az aktuális becslésben szereplő összes cikket. Az alábbi táblázat bemutatja az egyes sorokhoz rendelkezésre álló mezőt.

| Mező | Leírás |
|---|---|
| Szállítói számla | A cikkhez társított szállítókód. |
| Cikkszám | A cikkszám. |
| Mennyiség | A költség meghatározásához használt cikkek száma. |
| Önköltségi ár | A kereskedelmi megállapodásnak megfelelő önköltségi ár. Az érték a helyi pénznemben van megadva. |
| Mértékegység | Az egyéni mérték. Az egység az az egység, amely meg van adva a vonatkozó kiadott termékhez. |
| Becsült kirakodási költség | A teljes mennyiség becsült partraszállítási költsége. |
| Egységenként | A becsült partraszállítási költség a mennyiséggel osztva. |
| (Egyéb dimenziók) | A kiválasztott dimenzióktól függően az egyes cikkekre vonatkozó további információoszlopok is láthatók. |

A következő táblázat a **Sorok** gyorslap eszköztárán elérhető gombok leírását tartalmazza.

| Gomb | Leírás |
|---|---|
| Hozzáadás | Cikkek hozzáadása a költségbecsléshez. A cikkek hozzáadása után ki kell választania az **Újraszámítás** lehetőséget a Művelet panelen. |
| Eltávolítás | Cikkek eltávolítása a költségbecslésből. A cikkek eltávolítása után ki kell választania az **Újraszámítás** lehetőséget a Művelet panelen. |
| Út költségei | Egy lap megnyitása, ahol megtekinthetők és szerkeszthetők a cikk különféle hajóútköltségei. |
| Készlet \> Dimenziók megjelenítése | Egy párbeszédpanel megnyitása, ahol dimenzióoszlopokat adhat hozzá a rácshoz, illetve eltávolíthat oszlopokat. |

### <a name="settings-on-the-general-fasttab"></a>Az Általános gyorslap beállításai

Az **Általános** gyorslap a **Sorok** gyorslapon aktuálisan kiválasztott cikk adatait jeleníti meg. Az információk nagy része ismétlődik a **Sorok** gyorslapról, és bármelyik helyen szerkeszthető. Itt azonban további részletek is elérhetők. Az extra mezők értékei a vonatkozó kiadott termék beállításain alapulnak.

### <a name="settings-on-the-dimension-fasttab"></a>A Dimenzió gyorslap beállításai

A **Dimenzió** gyorslap a **Sorok** gyorslapon kiválasztott cikk összes elérhető készletdimenziójának értékeit jeleníti meg, függetlenül attól, hogy milyen dimenziókat választott a megjelenítéshez. Az itt megjelenő értékek a megfelelő költségbecslési sablonból származnak. A költségbecslési sablonban nem kötelezőek.

### <a name="buttons-on-the-action-pane"></a>A Művelet panel gombjai

A **Költségbecslés** oldal Művelet paneljén található gombokkal lehet kezelni a kiválasztott költségbecslést. A következő táblázat az elérhető gombokat írja le:

| Művelet | Leírás |
|---|---|
| Költséglekérdezés | Az hajóút összes költségének megtekintése. A költségeket szükség szerint az egyes cikkek szintjén lehet megtekinteni. |
| Elszámolóár frissítése | <p>Frissítse az elszámolóárat a **Partraszállítási költség paraméterei** oldalon megadott alapértelmezett költségszámítási verzió segítségével. Ez a verzió felülbírálható.</p><p>**Megjegyzés:** Ha egy cikknek több cikkdimenziója van (például különböző méretek, színek és konfigurációk), de ezek a dimenziók még nincsenek kiválasztva a becsléshez, a rendszer az egyes kombinációkhoz létrehoz egy függőben lévő árat.</p><p>**Fontos:** Az árlebontás létrejön, és a segítségével meghatározható a partraszállítási költségenkénti elszámolóár-különbözet.</p> |
| Út költségei | A szállítmány minden árujára vonatkozó hajóútköltségek megtekintése és szerkesztése. |
| Újraszámítás | A becsült partraszállítási költségek frissítése az hajóútköltségek frissítése, hozzáadása vagy eltávolítása után. |
| Zárolás | A költségbecslési rekord zárolása, hogy ne legyen további módosítás. |

## <a name="item-cost-price-update"></a>Cikk önköltségi árának frissítése

A **Cikk önköltségi árának frissítése** ismétlődő feladat minden olyan költségbecslést frissít, amely megfelel a feladat futtatásakor beállított szűrőknek. Ez a hatás hasonló ahhoz a hatáshoz, mint a Művelet panelen az **Elszámolóár frissítése** kiválasztása egyetlen becslés esetében. Ebben az esetben azonban a frissítés az összes egyező becslésre vonatkozik.

Az ismétlődő feladat futtatásához kövesse az alábbi lépéseket.

1. Lépjen a **Partraszállítási költség \> Időszakos feladatok \> Cikk önköltségi árának frissítése** elemre.
1. Az **Önköltségi ár frissítése becslésből** párbeszédpanelen állítsa be a következő mezőket a frissítés hatókörének korlátozása érdekében:

    - **Verzió** – Csak a megadott költségszámítási verziót használó becslések frissítése.
    - **Hely** – Csak a megadott helyet használó becslések frissítése.
    - **Költségsablon** – Csak a megadott sablont használó becslések frissítése.
    - **Célkikötő** – Csak a megadott „cél” kikötőt használó becslések frissítése.
    - **Becsült dátum** – Csak a megadott dátummal rendelkező becslések frissítése.

1. Adja meg a kívánt beállításokat a **Tartalmazandó rekordok** elemet és a **Futtatás a háttérben** gyorslapon az időszakos feladatoknak megfelelő szokásos módon.
1. A feladat futtatásához válassza az **OK** lehetőséget.

> [!NOTE]
> Az időszakos feladat csak akkor hajtható végre sikeresen, ha rendelkezésre állnak a következő információk:
>
> - Minden érintett terméknek rendelkeznie kell megadott **Bruttó mélység**, **Bruttó szélesség** és **Bruttó magasság** értékekkel.
> - Minden érintett szállítónak rendelkeznie kell egy megadott **Indulási kikötő** értékkel.
