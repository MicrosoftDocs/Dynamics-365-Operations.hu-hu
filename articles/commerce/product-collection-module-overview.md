---
title: Termékgyűjtemény-modulok
description: Ez a cikk áttekintést nyújt a termékgyűjtemények moduljairól a következőben:Microsoft Dynamics 365 Commerce
author: v-chgri
ms.date: 05/18/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: asharchw
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.assetid: ''
ms.openlocfilehash: 2ad50011e2f4c037a75c8c4b195c728bb58c3b47
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9269862"
---
# <a name="product-collection-modules"></a>Termékgyűjtemény-modulok

[!include [banner](includes/banner.md)]

Ez a cikk áttekintést nyújt a termékgyűjtemények moduljairól a következőben:Microsoft Dynamics 365 Commerce

A termékfelfedezés elsődleges eszköz, amellyel a kiskereskedők az e-kereskedelmi weboldalakon keresztül együttműködhetnek vevőikkel. A termékgyűjtési modulok segítenek a kiskereskedőknek a vonzó vásárlási élmények létrehozásában, és intuitív vizuális kezelőfelületet létrehozásában, amely a termékgyűjtemények gyors összeállítására használható.

A termékgyűjtési modulok a webhely fizikai termékeit és szolgáltatásait jelenítik meg. A termékgyűjtési modul általában olyan egy részletek oldalhoz van csatolva, ahol a vevők megvásárolhatnak egy terméket vagy szolgáltatást, illetve többet tudhatnak meg arról. 

A termékgyűjtemények forrásai a következő négy típusba foglalhatók:

- A termékek szerkesztői listái, amelyek manuálisan vannak definiálva a Dynamics 365 Commerce alkalmazásban egy termék vagy terméklista kapcsolódó termékeiként.
- Algoritmikus listák, mint például az új, legnépszerűbb vagy trendi termékek listái
- A gépi tanuláson alapuló ajánlati listák
- Az ügyfél számára testreszabott találatokat támogató testreszabási listák. Az ügyfeleknek a testreszabott eredmények megtekintéséhez be kell jelentkezniük az e-kereskedelmi webhelyre. A vendégfelhasználók nem látnak a személyre szabott találatokat. A felhasználók a [fiókkezelő oldalról](account-management.md) leiratkozhatnak a testreszabásáról.

A következő ábra bemutatja az e-kereskedelmi webhelyeken használt termékgyűjtemények különböző típusait.

![Példa egy e-kereskedelmi webhely különböző típusú termékgyűjteményére.](./media/ProductCollectionsAcrossTheSiteUseProductPlacement.png)

> [!NOTE]
> Hasonló típusú termékek csoportjának megjelenítéséhez mindig a termékgyűjtési modulokat használja.

## <a name="product-collection-modules-and-types"></a>Termékgyűjtési modulok és típusok

A következő táblázat leírja a Dynamics 365 Commerce különböző típusú termékgyűjtési moduljait.

| Termékgyűjtési modul  | Típus | Leírás |
|----------------------------|------|-------------|
| Kategória                   | Kategória | Ez a modul egy kategóriában jeleníti meg a termékek listáját, a csatornához létrehozott navigációs kategóriahierarchia által meghatározott módon. |
| Kapcsolódó termékek           | Szerkesztői | Ez a modul felsorolja azokat a termékeket, amelyekhez a termékmenedzser kapcsolódó terméket állított be a Commerce alkalmazásban, ahhoz a kapcsolattípushoz, amit a szerkesztő kiválasztott. |
| Keresési eredmények             | Keresési lekérdezés | Ez a termékgyűjtési modul olyan termékek listáját jeleníti meg, amelyek legjobban megfelelnek a vevő által megadott keresésnek. |
| Válogatott terméklisták      | Szerkesztői | Ez a modul megjelenít egy egyéni listát, amelyet a kereskedők és szerkesztők hoztak létre a Commerce alkalmazásban. |
| Új                        | Algoritmikus | A modul a csatornákhoz és katalógusokhoz hozzárendelt legújabb termékek listáját jeleníti meg. Ez a lista akkor jeleníti meg az aláírt felhasználó testreszabott eredményeit, ha a webhely szerzője ezt a lehetőséget választja. |
| Legnépszerűbb               | Algoritmikus | Ez a modul a termék listáját jeleníti meg, amelyek az eladások száma alapján van rendezve. Ez a lista akkor jeleníti meg az aláírt felhasználó testreszabott eredményeit, ha a webhely szerzője ezt a lehetőséget választja. |
| Felkapott                   | Algoritmikus | Ez a modul az adott időszakra vonatkozóan a legjobban teljesítő termékek listáját jeleníti meg. Ez a lista akkor jeleníti meg az aláírt felhasználó testreszabott eredményeit, ha a webhely szerzője ezt a lehetőséget választja. |
| Gyakran együtt vásárolt | Mesterséges intelligencia/gép tanulás | Ez a modul gépi tanulást használ a fogyasztói vásárlási mintáinak elemzésére és olyan cikkeket ajánl fel, amelyeket gyakran megvásárolnak az adott termékkel együtt. Ez a lista akkor jeleníti meg az aláírt felhasználó testreszabott eredményeit, ha a webhely szerzője ezt a lehetőséget választja. |
| Szintén kedvelt           | Mesterséges intelligencia/gép tanulás | Ez a modul gépi tanulást használ a fogyasztói vásárlási mintáinak elemzésére és olyan cikkeket ajánl fel, amelyek egy adott termékhez kapcsolódnak. Ez a lista akkor jeleníti meg az aláírt felhasználó testreszabott eredményeit, ha a webhely szerzője ezt a lehetőséget választja. |
| Önnek ajánljuk              | Mesterséges intelligencia/gép tanulás | Ez a modul gépi tanulást használ a bejelentkezett felhasználók vásárlási mintáinak elemzésére, és olyan személyre szabott javaslatokat biztosít, amelyek ezeken a vásárlási mintákon alapulnak. A vendégfelhasználó számára ez a lista összecsukott állapotban lesz. |

## <a name="supported-modules"></a>Támogatott modulok 

A termékgyűjtési modul támogatja a [gyorsnézet modult](quick-view-module.md), amellyel a felhasználók megtekinthetik a termékadatokat, és cikkeket adhatnak hozzá a kosárhoz egy termékgyűjtési oldalról.

## <a name="add-a-product-collection-module-to-a-category-page"></a>Termékgyűjtési modul hozzáadása egy kategórialaphoz

A következő lépésekkel lehet hozzáadni egy termékgyűjtési modult egy kategóriához.

1. Lépjen az **Oldalak** pontra, majd válassza az **Új** lehetőséget új oldal létrehozásához.
1. Az Új lap **létrehozása párbeszédpanel** Lap neve **csoportban** írja be a megfelelő oldal nevét, majd válassza **a Tovább gombra**.
1. A **Sablon kiválasztása csoportban** válassza ki az alapértelmezett kategóriaoldal által használt sablont, **majd válassza a Tovább gombra**.
1. Az **Elrendezés kiválasztása oldalon válasszon** egy lapelrendezést (például **rugalmas** elrendezés), majd válassza **a Tovább lehetőséget**.
1. Az Ellenőrzés **és befejezés lapon** ellenőrizze a lap konfigurációját. Ha szerkesztenie kell a lap adatait, válassza a Vissza **lehetőséget**. Ha a lap adatai helyesek, válassza a Létrehozás **lapot**. 
1. Válassza ki a **három pontból (...**), **majd válassza a Modul hozzáadása lehetőséget a Sub footer** **slotban**.
1. A Modulok **kiválasztása párbeszédpanelen** válassza ki **a** Tároló modult, majd válassza az **OK gombra.**
1. A tárolóhelyen **válassza** ki a három pontból (**...**), majd válassza a **Modul hozzáadása lehetőséget**.
1. A Modulok **kiválasztása párbeszédpanelen** válassza ki **a Termékgyűjtemény** modult, majd válassza az **OK gombra.**  
1. A termékgyűjtési modultulajdonságok ablaktábláján válassza ki a **Terméklista hozzáadása** elemet.
1. A **Terméklista-konfiguráció kiválasztása** párbeszédpanelen válassza ki a lista típusát, a lista forrását, és adja meg a cikkek számát. Adja meg a többi beállítást, amely elérhető ehhez a listatípushoz. A lista típusokkal kapcsolatosan a következő táblázatban olvashat bővebben. 
1. Válassza ki az **OK** lehetőséget.
1. Válassza a **Mentés** lehetőséget, majd az oldal előnézetének megtekintéséhez az **Előnézet** elemet.
1. Válassza a **Szerkesztés befejezése** parancsot az oldal ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.

A következő táblázat felsorolja azokat a lista-típusokat, amelyek a **Terméklista-konfiguráció kiválasztása** párbeszédpanelen választhatók ki.

| Típus                       | Leírás | Használat | Oldalkörnyezet | Specifikus környezet | Személyre szabás |
|----------------------------|-------------|-------|--------------|------------------|-----------------|
| Termékek kategóriák szerint       | Egy adott kategóriába tartozó termékek listája. Ez a kategória a lap környezetéből vagy a szerző által biztosított környezetből van meghatározva. | Ez a listatípus bármely oldalon használható (például kezdőoldal, kategóriaoldal, marketingoldal vagy termékrészletek oldal \[PDP\]) egy adott termékkategória reklámozásához. | Kategória az oldalkörnyezetből, ahol elérhető (például egy kategóriaoldal) | A szerző egy adott kategóriát adhat meg a lista kontextusaként. | Nem alkalmazható |
| Kapcsolódó termékek           | Azoknak a termékeknek a listája, amelyeket a termékmenedzser kapcsolódó termékekként állított be a Commerce alkalmazásban az objektumkapcsolati típushoz. | Ez a listástípus elsődlegesen a PDP-k esetében használatos, de bármely oldalon használható, ha a szülő termék rendelkezésre áll. | Termék az oldalról, kapcsolat típusa (kötelező) | A termék kijelölhető a választóban, és a kapcsolattípus kerül felhasználásra. | Nem alkalmazható |
| Összeállította                    | Egy egyéni lista, amelyet a kereskedők és szerkesztők hoztak létre a Commerce alkalmazásban. | Gazdagíthatja a kategória oldalát, a kezdőlapot, a pénztár és a kosár lapjait és a terméklapokat. | Nem alkalmazható | Nem alkalmazható | Nem alkalmazható |
| Algoritmikus                | <ul><li>**Új** – A csatornákhoz és katalógusokhoz hozzárendelt legújabb termékek listája.</li><li>**Legnépszerűbb** – Termék listája amelyek az eladások száma alapján van rendezve.</li><li>**Népszerű** – Az adott időszakra vonatkozóan a legjobban teljesítő termékek listája.</li></ul> | Kezdőlap, kategóriaoldal és pénztári és kosároldalak bővítése | Kategória az oldalkörnyezetből (például egy kategóriaoldal) | A webhely szerzője által meghatározott kategória | Támogatott |
| Gyakran együtt vásárolt | Ez a lista gépi tanulást használ a fogyasztói vásárlási mintáinak elemzésére és olyan cikkeket ajánl fel, amelyeket gyakran megvásárolnak az adott termékkel együtt. | Az ilyen típusú lista csak a kosárlapra vonatkozik. | Kosár | Nem alkalmazható | Támogatott |
| Szintén kedvelt           | Ez a lista gépi tanulást használ a fogyasztói vásárlási mintáinak elemzésére és olyan cikkeket ajánl fel, amelyek egy adott termékhez kapcsolódnak. | Az ilyen típusú listát a PDP-ken használják azon termékek megjelenítéséhez, amelyeket más ügyfelek vásároltak. | Termékkontextus az oldalról | A webhely szerzője által megadott termék | Támogatott |
| Önnek ajánljuk              | Az ügyfélpreferenciák meghatározásához a gépi tanulást alkalmazó lista. | Ez a listatípus bármely oldalon használható. | Nem alkalmazható| Nem alkalmazható | Támogatott | 

## <a name="additional-resources"></a>További erőforrások

[Modulkönyvtár – áttekintés](starter-kit-overview.md)

[Forgótármodul](add-carousel.md)

[Tartalomgazdag blokkmodul](add-content-rich-block.md)

[Tárolómodul](add-container-module.md)

[Vásárlásmező-modul](add-buy-box.md)

[Termékajánlatok áttekintése](product-recommendations.md)

[Gyorsnézeti modul](quick-view-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
