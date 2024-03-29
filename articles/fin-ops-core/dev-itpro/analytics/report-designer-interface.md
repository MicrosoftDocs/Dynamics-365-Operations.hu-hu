---
title: Jelentéstervező felület
description: Ez a cikk bemutatja a jelentéstervezőben való navigálást, és bemutatja, hogy hogyan lehet a különféle beállításokat az adott követelményeknek megfelelően használni.
author: aprilolson
ms.date: 11/22/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.custom: 59041
ms.assetid: 054de5b0-8618-4195-be12-f031b4bb4d74
ms.search.form: FinancialReports
ms.openlocfilehash: 25d913e6f5d4c95dceda1291a2c33abe37348574
ms.sourcegitcommit: d27fef61593c6d1e9e26d5c9fad21411bc52fabc
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/23/2022
ms.locfileid: "9802742"
---
# <a name="report-designer-interface"></a>Jelentéstervező felület

[!include [banner](../includes/banner.md)]

Ez a cikk bemutatja a jelentéstervezőben való navigálást, és bemutatja, hogy hogyan lehet a különféle beállításokat az adott követelményeknek megfelelően használni.

## <a name="report-designer-menu-commands"></a>Jelentéstervező menüparancsai

Az alábbi táblázatok bemutatják, hogy milyen parancsok és beállítások állnak a rendelkezésére, a pénzügyi jelentések tervezésekor. Egyes menüparancsok és beállítások csak bizonyos körülmények között érhetők el. A jelentések előre- és hátrasorolására vonatkozó parancsok például csak jelentési-fa definíció esetén érhetők el.

### <a name="file-menu"></a>Fájl menü

A **Fájl** menü az összes felhasználó által elérhető, és a következő parancsokat tartalmazza.

| Parancs                           | Leírás |
|-----------------------------------|-------------|
| Új                               | Új jelentésdefiníció, sordefiníció, oszlopdefiníció, jelentési-fa definíció, jelentéscsoport-definíció, illetve mappa létrehozása. A szerepkörének függvényében elérhetőek további beállítások is. |
| Nyitva                              | Nyisson meg egy korábbi sordefiníciót, oszlopdefiníciót, jelentési-fa definíciót vagy jelentésdefiníciót. |
| Bezár                             | Zárja be az aktuális építőelemet. |
| Összes bezárása                         | Zárjon be minden építőelemet. |
| Mentés                              | Mentse az aktuális sordefiníciót, oszlopdefiníciót, jelentési-fa definíciót vagy jelentésdefiníciót. |
| Mentés másként                           | Mentse el más néven az aktuális sordefiníciót, oszlopdefiníciót, jelentési-fa definíciót vagy jelentésdefiníciót. |
| Tulajdonságok                        | Nyissa meg a **Tulajdonságok** párbeszédpanelt, ahol módosítani tudja a jelentés nevét és leírását. |
| Létrehozás                          | Hozza létre az aktuális jelentést. Ez a parancs egy jelentésdefinícióban érhető el. |
| Jelentés megtekintése                       | Nyissa meg a létrehozott jelentés legfrissebb verzióját. Ez a parancs egy jelentésdefinícióban érhető el, ha már legalább egy jelentést létrehozott. |
| Legutóbbi jelentésdefiníciók         | A nemrég létrehozott vagy módosított jelentések listáját jeleníti meg. Ezután ki tud választani egy jelentést a listából. |
| Legutóbbi sordefiníciók            | A nemrég létrehozott vagy módosított sordefiníciók listáját jeleníti meg. Ezután ki tud választani egy sordefiníciót a listából. |
| Legutóbbi oszlopdefiníciók         | A nemrég létrehozott vagy módosított oszlopdefiníciók listáját jeleníti meg. Ezután ki tud választani egy oszlopdefiníciót a listából. |
| A legutóbbi jelentési fa definíciói | A nemrég létrehozott vagy módosított jelentési-fa definíciók listáját jeleníti meg. Ezután ki tud választani egy jelentési-fa definíciót a listából. |
| Kilépés                              | Lépjen ki a Jelentéstervezőből. |

### <a name="edit-menu"></a>Szerkesztés menü

A **Szerkesztés** menü a **Tervező** vagy **Rendszergazda** szerepkörrel rendelkező felhasználók részére érhető el. Ez a menü következő parancsokból áll:

| Parancs                                | Leírás |
|----------------------------------------|-------------|
| Visszavonás                                   | Utolsó művelet visszavonása. |
| Ismétlés                                   | Utolsó művelet sztornírozása. |
| Kivágás                                    | A kijelölt szöveg törlése és másolása a vágólapra. |
| Másolás                                   | A kijelölt szöveg másolása a vágólapra. |
| Beillesztés                                  | Az utoljára kivágott vagy másolt szöveg beszúrása a vágólapról. |
| Kijelölések törlése                                  | A kijelölt építőelem-cella tartalmának törlése. |
| Keresés                                   | Nyissa meg a **Keresés és csere** párbeszédpanelt, amelynek segítségével szövegre tud rákeresni a nézet ablaktáblában. |
| Csere                                | Nyissa meg a **Keresés és csere** párbeszédpanel, amelynek segítségével szövegre tud rákeresni, illetve azt cserélni tudja a nézet ablaktáblában. |
| Sorok beszúrása dimenziókból            | Nyissa meg a **Sorok beszúrása dimenziókból** párbeszédpanel, ahol ki tudja választani, hogy a sordefinícióban milyen dimenzióértékek szerepeljenek. Ez a parancs egy sordefinícióban érhető el. |
| Sorok újraszámozása                          | Az összes sor numerikus sorkód újraszámozása. Ez a parancs egy sordefinícióban érhető el. |
| Sorhivatkozások                              | Nyissa meg a **Sorhivatkozások** párbeszédpanelt, ahol be tudja állítani a sordefiníciókban és jelentési-fa definíciókban szereplő adathivatkozások forrásait. Ez a parancs egy sordefinícióban érhető el. |
| Kerekítési helyesbítés                    | Nyissa meg a **Kerekítési helyesbítés** párbeszédpanelt, ahol be tudja állítani a kerekítési paramétereket. Ez a parancs egy sordefinícióban érhető el. |
| Dimenziókészletek kezelése                  | Nyissa meg a **Dimenziókészletek** párbeszédpanelt, ahol dimenziókészleteket tud létrehozni, illetve módosíthatja azokat. Ez a parancs egy sordefinícióban vagy jelentési-fa definícióban érhető el. |
| Sor beszúrása                             | Üres sor beszúrása a sordefinícióba vagy egy üres fejlécsor beszúrása az oszlopdefinícióba. Ez a parancs egy sordefinícióban vagy oszlopdefinícióban érhető el. |
| Sor törlése                             | A kijelölt sor törlése a sordefinícióból, illetve a kiválasztott fejlécsor törlése az oszlopdefinícióból. Ez a parancs egy sordefinícióban vagy oszlopdefinícióban érhető el. |
| Oszlop beszúrása                          | Üres oszlop beszúrása az oszlopdefinícióba. Ez a parancs egy oszlopdefinícióban érhető el. |
| Oszlop törlése                          | A kijelölt oszlop törlése az oszlopdefinícióból Ez a parancs egy oszlopdefinícióban érhető el. |
| Jelentési egységek beszúrása dimenziókból | Nyissa meg a **Jelentési egységek beszúrása dimenziókból** párbeszédpanelt, ahol ki tudja választani, hogy a jelentési-fa definícióban milyen dimenzióértékek szerepeljenek. Ez a parancs valamelyik jelentési-fa definícióban érhető el. |
| Dimenziókészlet hierarchiájának importálása         | Nyissa meg a **Dimenziókészlet hierarchiája** párbeszédpanelt, ahol dimenziókészlet-hierarchiát tud importálni a pénzügyi adatokból. Ez a parancs egy jelentési-fa definícióban érhető el ..\\financial-dimensions\\dimension alapú rendszer esetén. |
| Jelentési egység beszúrása                  | Üres sor beszúrása a jelentési fa-definícióba. Ez a parancs valamelyik jelentési-fa definícióban érhető el. |
| Jelentési egység törlése                  | A kijelölt jelentési-egység sor törlése a jelentési-fa definícióból. Ez a parancs a jelentésfa-definíciókból érhető el. |

### <a name="view-menu"></a>Nézet menü

A **Nézet** menü az összes felhasználó által elérhető, és a következő parancsokat tartalmazza.

| Parancs         | Leírás                                                            |
|-----------------|------------------------------------------------------------------------|
| Navigációs ablak | Megjeleníti vagy elrejti a navigációs ablaktáblát.                                      |
| Eszköztárak        | A látható eszköztár kiválasztása.                                  |
| Állapotsor      | Az állapotinformációk megjelenítése vagy elrejtése a Jelentéstervező **ablakban** . |
| Kezdőlap    | A **Kezdőlap** megnyitása.                                             |

### <a name="format-menu"></a>Formázás menü

A **Formázás** menü a **Tervező** vagy **Rendszergazda** szerepkörrel rendelkező felhasználók részére érhető el. Ez a menü következő parancsokból áll:

| Command               | Leírás |
|-----------------------|-------------|
| Stílusok és formázás | A Stílusok **és formázás** párbeszédpanel megnyitása, ahol létrehozhatja és módosíthatja a sordefiníciókban és oszlopdefiníciókban megjelenő szöveg stílusát. Ez a parancs egy sordefinícióban vagy egy oszlopdefinícióban érhető el. |
| Oszlopszélesség          | Az Oszlop szélessége **párbeszédpanel** megnyitása, ahol beállíthatja a kiválasztott oszlop szélességét. Ez a parancs egy sordefinícióban, egy oszlopdefinícióban vagy egy jelentési-fa definícióban érhető el. |
| Elrejtés                  | A kiválasztott oszlop elrejtése Ez a parancs egy sordefinícióban, egy oszlopdefinícióban vagy egy jelentési-fa definícióban érhető el. |
| Megjelenítés                | A kijelölt oszlopok között elrejtett oszlopok megjelenítése. Ez a parancs egy sordefinícióban, oszlopdefinícióban vagy jelentési-fa definícióban érhető el. |

### <a name="company-menu"></a>Vállalat menü

A **Vállalat** menü a **Tervező** vagy **Rendszergazda** szerepkörrel rendelkező felhasználók részére érhető el. Ez a menü következő parancsokból áll:

| Parancs               | Leírás                                                                                                            |
|-----------------------|------------------------------------------------------------------------------------------------------------------------|
| Vállalatok             | Nyissa meg a **Vállalatok** párbeszédpanelt, ahol vállalatokat tud létrehozni, illetve módosíthatja azokat.                                          |
| Építőelem-csoportok | A Blokkcsoportok **létrehozása** párbeszédpanel megnyitása, ahol létrehozhat, módosíthat, importálhat és exportálhat blokkcsoportokat. |

### <a name="go-menu"></a>Ugrás menü

Az **Ugrás** menü minden felhasználó számára elérhető, és az alábbi parancsokat tartalmazza.

> [!NOTE]
> A parancsok hatása csak akkor látható, ha meg van nyitva a navigációs ablaktábla.

| Parancsok                   | Leírás                                                                        |
|----------------------------|------------------------------------------------------------------------------------|
| Jelentésdefiníciók         | Jelentésdefiníciók megjelenítése a navigációs ablaktáblában.                                    |
| Sordefiníciók            | Sordefiníciók megjelenítése a navigációs ablaktáblában.                                       |
| Oszlopdefiníciók         | Oszlopdefiníciók megjelenítése a navigációs ablaktáblában.                                    |
| Jelentési-fa definíciók | Jelentési-fa definíciók megjelenítése a navigációs ablaktáblában.                            |
| Biztonság                   | Felhasználókra, csoportokra és vállalatokra vonatkozó biztonsági információk megjelenítése a navigációs ablaktáblában. |

### <a name="tools-menu"></a>Eszközök menü

Az **Eszközök** menü minden felhasználó számára elérhető, de néhány parancs elérhetősége korlátozott. Ez a menü következő parancsokból áll:

| Parancs                       | Leírás |
|-------------------------------|-------------|
| Védelem                       | Jelszó alkalmazása az aktuális építőelemre. Ez a parancs **Tervező** vagy **Rendszergazda** szerepkörrel rendelkező felhasználók részére érhető el. |
| Jelentés-várólista állapota           | Nyissa meg a **Jelentés-várólista állapota** párbeszédpanelt, ahol megtekintheti a legutoljára létrehozott jelentéseket, illetve az egyes jelentések részleteit. |
| Forrásrendszer adatai     | A beállítások megjelenítése a Microsoft Dynamics ERP rendszerhez. Ez a parancs **Tervező** vagy **Rendszergazda** szerepkörrel rendelkező felhasználók részére érhető el. |
| Felelősnél tételek             | A jelenleg nyitva lévő sordefiníciók, oszlopdefiníciók, jelentési-fa definíciók, és jelentésdefiníciók megjelenítése. Ez a parancs **Tervező** vagy **Rendszergazda** szerepkörrel rendelkező felhasználók részére érhető el. |
| Gyorsítótárazott pénzügyi adatok frissítése | Adatok frissítése a pénzügyi dimenziók oszlopban. |
| Beállítások                       | Nyissa meg a **Beállítások** párbeszédpanel, ahol módosítani tudja Jelentéstervezőre vonatkozó felhasználói preferenciákat. |

### <a name="window-menu"></a>Ablak menü

Az **Ablak** menü az összes felhasználó által elérhető, és a következő parancsokat tartalmazza.

| Parancs              | Leírás |
|----------------------|-------------|
| Vízszintes elrendezés    | Az összes megnyitott ablakot egymás mellett jeleníti meg. |
| Függőleges elrendezés      | Az összes megnyitott ablakot egymás alatt jeleníti meg. |
| Lépcsőzetes elrendezés              | Az összes megnyitott ablakot egymás fölé helyezve jeleníti meg, úgy hogy mindegyik ablak címsorára látható marad. |
| Vízszintes rögzítés    | A kijelölt sor rögzítése oly módon, hogy az görgetéskor továbbra is látható marad az ablakban. Ez a parancs **Tervező** vagy **Rendszergazda** szerepkörrel rendelkező felhasználók részére érhető el. |
| Függőleges rögzítés      | A kijelölt oszlop rögzítése oly módon, hogy az görgetésekor továbbra is látható marad az ablakban. Ez a parancs **Tervező** vagy **Rendszergazda** szerepkörrel rendelkező felhasználók részére érhető el. |
| Megnyitott ablakok listája | A megnyitott ablakok listáját jeleníti meg. Válassza ki az előrehozni kívánt ablakot. |

### <a name="help-menu"></a>Súgó menü

A **Súgó** menü az összes felhasználó által elérhető, és a következő parancsokat tartalmazza.

| Command | Leírás                                                              |
|---------|--------------------------------------------------------------------------|
| Súgó    | A pénzügyi jelentés súgócikkének megnyitása. |
|         |                                                                          |

## <a name="report-designer-toolbar-buttons"></a>Jelentéstervező eszköztárgombjai
Az alábbi táblázatok a jelentések tervezéséhez rendelkezésre álló eszköztár gombjait mutatják be. Egyes eszköztár gombok csak bizonyos körülmények között érhetők el. A jelentések előre- és hátrasorolására vonatkozó gombok például csak jelentési-fa definíció esetén érhetők el.

### <a name="standard-toolbar"></a>Szokásos eszköztár

A szokásos eszköztár gyors hozzáférést biztosít a fájl és szerkesztési parancsokhoz. Ez az eszköztár az alábbi gombokat tartalmazza.

| Gomb                                                                                       | Leírás |
|----------------------------------------------------------------------------------------------|-------------|
| [![Új gomb.](./media/rowc130389.png)](./media/rowc130389.png)                              | Új (üres) sordefiníció, oszlopdefiníció, jelentési-fa definíció vagy jelentésdefiníció létrehozása. |
| [![Megnyitás gomb.](./media/openfolderc130389.png)](./media/openfolderc130389.png)               | Nyisson meg egy korábbi sordefiníciót, oszlopdefiníciót, jelentési-fa definíciót vagy jelentésdefiníciót. |
| [![Mentés gomb.](./media/savec130389.png)](./media/savec130389.png)                           | Mentse az aktuális sordefiníciót, oszlopdefiníciót, jelentési-fa definíciót vagy jelentésdefiníciót. |
| [![Másolás gomb.](./media/copyc130389.png)](./media/copyc130389.png)                           | A kijelölt szöveg másolása a vágólapra. |
| [![Kivágás gomb.](./media/cutc130389.png)](./media/cutc130389.png)                              | A kijelölt szöveg törlése és másolása a vágólapra. |
| [![Beillesztés gomb.](./media/pastec130389.png)](./media/pastec130389.png)                        | Szöveg beszúrása a vágólapról. |
| [![Visszavonás gomb.](./media/undoc130389.png)](./media/undoc130389.png)                           | Utolsó művelet visszavonása. |
| [![Újra gomb.](./media/redoc130389.png)](./media/redoc130389.png)                           | Utolsó művelet sztornírozása. |
| [![Keresés gomb.](./media/findc130389.png)](./media/findc130389.png)                           | Nyissa meg a **Keresés és csere** párbeszédpanelt, amelynek segítségével szövegre tud rákeresni, illetve azt cserélni tudja az aktív ablakban. |
| [![Sor beszúrása gomb.](./media/insertrowc130389.png)](./media/insertrowc130389.png)           | Üres sor beszúrása a sordefinícióba vagy egy üres fejlécsor beszúrása az oszlopdefinícióba. Ez a gomb egy sordefinícióban vagy oszlopdefinícióban érhető el. |
| [![Oszlop beszúrása gomb.](./media/insertcolumnc130389.png)](./media/insertcolumnc130389.png)  | Üres oszlop beszúrása az oszlopdefinícióba. Ez a gomb egy oszlopdefinícióban érhető el. |
| [![Zárolás gomb.](./media/lockc130389.png)](./media/lockc130389.png)                           | Jelszó alkalmazása az aktuális építőelemre. Ez a gomb **Tervező** vagy **Rendszergazda** szerepkörrel rendelkező felhasználók részére érhető el. |
| [![Sorhivatkozás gomb.](./media/rowlinkc130389.png)](./media/rowlinkc130389.png)                 | Nyissa meg a **Sorhivatkozások** párbeszédpanelt, ahol be tudja állítani a sordefiníciókban és jelentési-fa definíciókban szereplő adathivatkozások forrásait. Ez a gomb egy sordefinícióban érhető el. |
| [![Előresorolás gomb.](./media/promotec130389.png)](./media/promotec130389.png)                  | A jelentési-fa definíció egy egységének előresorolása. Ha gyermekegységet jelöl ki, majd az **Előresorolás** lehetőségre kattint, a gyermekegység ugyanarra a szintre, mint szülőegység kerül átmozgatásra. |
| [![Hátrasorolás gomb.](./media/demotec130389.png)](./media/demotec130389.png)                     | A jelentési-fa definíció egy egységének hátrasorolása. Ha egy egységet kijelöl, majd a **Hátrasorolás** lehetőségre kattint, úgy az egység az azt megelőző szülő gyermeke lesz. |
| [![Kibontás gomb.](./media/expandtreebuttonc130389.png)](./media/expandtreebuttonc130389.png) | A jelentési-fa definíció összes egységének, a kijelölt egység szintjén történő kibontása. |
| [![Összecsukás gomb.](./media/collapsec130389.png)](./media/collapsec130389.png)               | A jelentési fa összecsukása. |
| [![Súgó gomb.](./media/helpc130389.png)](./media/helpc130389.png)                           | Nyissa meg a Súgót. |

### <a name="formatting-toolbar"></a>Formázás eszköztár

A formázás eszköztár egyszerű hozzáférést biztosít a stílus parancsokhoz. Ez az eszköztár az alábbi gombokat tartalmazza.

| Gomb                                                                                                       | Leírás                                           |
|--------------------------------------------------------------------------------------------------------------|--------------------------------------------------|
| [![Betűstílus gomb.](./media/formattingc130389.png)](./media/formattingc130389.png)                         | A kijelölt betűstílus alkalmazása az aktuális szövegre.   |
| [![Betűtípus gomb.](./media/fonttype.png)](./media/fonttype.png)                                                 | A kijelölt betűtípus alkalmazása az aktuális szövegre.           |
| [![Betűméret gomb.](./media/fontsize.png)](./media/fontsize.png)                                            | Az aktuális szöveg beállítása a kiválasztott betűméretre (pontokban). |
| [![Félkövér gomb.](./media/boldc130389.png)](./media/boldc130389.png)                                           | Az aktuális szöveg félkövérre állítása.                          |
| [![Dőlt gomb.](./media/italicsc130389.png)](./media/italicsc130389.png)                                   | Az aktuális szöveg dőltre állítása.                        |
| [![Aláhúzás gomb.](./media/underlinec130389.png)](./media/underlinec130389.png)                            | Az aktuális szöveg aláhúzása.                          |
| [![Behúzás csökkentése gomb.](./media/outdentlsc130389.png)](./media/outdentlsc130389.png)                      | Az aktuális szöveg behúzásának csökkentése.             |
| [![Behúzás növelése gomb.](./media/indentlsc130389.png)](./media/indentlsc130389.png)                        | Az aktuális szöveg behúzásának növelése.             |
| [![Háttérszín gomb.](./media/fillbackgroundcolorc130389.png)](./media/fillbackgroundcolorc130389.png) | Az aktuális cella háttérszínének módosítása.     |
| [![Betűszín gomb.](./media/fontcolorc130389.png)](./media/fontcolorc130389.png)                           | Az aktuális szöveg színének módosítása.                |

### <a name="report-designer-toolbar"></a>Jelentéstervező eszköztár

A Jelentéstervező eszköztár gyors hozzáférést biztosít a Jelentéstervezőn belüli navigálást lehetővé tevő parancsokhoz. Ez az eszköztár az alábbi gombokat tartalmazza.

| Gomb                                                                                              | Leírás |
|-----------------------------------------------------------------------------------------------------|-------------|
| [![Jelentésdefiníció gomb.](./media/reportc130389.png)](./media/reportc130389.png)            | Az **Ablak** menüben felsorolt jelentésdefiníció megjelenítése. |
| [![Sordefiníció gomb.](./media/rowc130389.png)](./media/rowc130389.png)             | Az aktív jelentésdefinícióhoz rendelt sordefiníció megjelenítése. |
| [![Oszlopdefiníció gomb.](./media/columnc130389.png)](./media/columnc130389.png)  | Az aktív jelentésdefinícióhoz rendelt oszlopdefiníció megjelenítése. |
| [![Jelentési fa definíció gomb.](./media/treec130389.png)](./media/treec130389.png)             | Az aktív jelentésdefinícióhoz rendelt jelentési-fa definíció megjelenítése. |
| [![Jelentésmegjelenítő gomb.](./media/reportviewerc130389.png)](./media/reportviewerc130389.png)         | A Jelentésmegjelenítő megnyitása, és a létrehozott jelentés legfrissebb verziójának megjelenítése. Ez a gomb egy jelentésdefinícióban érhető el, ha már legalább egy jelentést létrehozott. |
| [![Jelentés létrehozása gomb.](./media/generate-to-ddvc130389.png)](./media/generate-to-ddvc130389.png) | Jelentés készítése az aktív jelentésdefiníció alapján. Ez a gomb a jelentésdefiníciókból érhető el. |

## <a name="additional-resources"></a>További erőforrások

[Pénzügyi jelentéskészítés](financial-reporting-intro.md)

[Pénzügyi jelentések létrehozása](generate-financial-report.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
