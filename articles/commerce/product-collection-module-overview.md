---
title: Termékgyűjtési modulok
description: Ez a témakör áttekintést nyújt a Microsoft Dynamics 365 Commerce termékgyűjtési moduljairól.
author: v-chgri
manager: annbe
ms.date: 01/07/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: asharchw
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 31307035014f2fae6146f33bc23e3e06103f82eb
ms.sourcegitcommit: c237123ad94d9418994ac095fbd8634c05a927b1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/08/2020
ms.locfileid: "2943263"
---
# <a name="product-collection-modules"></a>Termékgyűjtési modulok

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Ez a témakör áttekintést nyújt a Microsoft Dynamics 365 Commerce termékgyűjtési moduljairól.

## <a name="overview"></a>Áttekintés

A termékfelfedezés elsődleges eszköz, amellyel a kiskereskedők az e-kereskedelmi weboldalakon keresztül együttműködhetnek vevőikkel. A termékgyűjtési modulok segítenek a kiskereskedőknek a vonzó vásárlási élmények létrehozásában, és intuitív vizuális kezelőfelületet létrehozásában, amely a termékgyűjtemények gyors összeállítására használható.

A termékgyűjtési modulok a webhely fizikai termékeit és szolgáltatásait jelenítik meg. A termékgyűjtési modul általában olyan egy részletek oldalhoz van csatolva, ahol a vevők megvásárolhatnak egy terméket vagy szolgáltatást, illetve többet tudhatnak meg arról. 

A termékgyűjtemények forrásai a következő négy típusba foglalhatók:

- A termékek szerkesztői listái, amelyek manuálisan vannak definiálva a Dynamics 365 Retail alkalmazásban egy termék vagy terméklista kapcsolódó termékeiként.
- Algoritmikus listák, mint például az új, legnépszerűbb vagy trendi termékek listái
- A gépi tanuláson alapuló ajánlati listák
- Az ügyfél számára testreszabott találatokat támogató testreszabási listák. Az ügyfeleknek a testreszabott eredmények megtekintéséhez be kell jelentkezniük az e-kereskedelmi webhelyre. A vendégfelhasználók nem látnak a személyre szabott találatokat. A felhasználók a [fiókkezelő oldalról](account-management.md) leiratkozhatnak a testreszabásáról.

A következő ábra bemutatja az e-kereskedelmi webhelyeken használt termékgyűjtemények különböző típusait.

![Példa egy e-kereskedelmi webhely különböző típusú termékgyűjteményére](./media/ProductCollectionsAcrossTheSiteUseProductPlacement.png)

> [!NOTE]
> Hasonló típusú termékek csoportjának megjelenítéséhez mindig a termékgyűjtési modulokat használja.

## <a name="product-collection-modules-and-types"></a>Termékgyűjtési modulok és típusok

A következő táblázat leírja a Dynamics 365 Commerce különböző típusú termékgyűjtési moduljait.

| Termékgyűjtési modul  | Típus | Leírás |
|----------------------------|------|-------------|
| Kategória                   | Kategória | Ez a modul egy kategóriában jeleníti meg a termékek listáját, a kiskereskedelmi csatornához létrehozott navigációs kategóriahierarchia által meghatározott módon. |
| Kapcsolódó termékek           | Szerkesztői | Ez a modul felsorolja azokat a termékeket, amelyekhez a termékmenedzser kapcsolódó terméket állított be a Retailben, ahhoz a kapcsolattípushoz, amit a szerkesztő kiválasztott. |
| Válogatott terméklisták      | Szerkesztői | Ez a modul megjelenít egy egyéni listát, amelyet a kereskedők és szerkesztők hoztak létre a Retail alkalmazásban. |
| Új                        | Algoritmikus | A modul a csatornákhoz és katalógusokhoz hozzárendelt legújabb termékek listáját jeleníti meg. Ez a lista akkor jeleníti meg az aláírt felhasználó testreszabott eredményeit, ha a webhely szerzője ezt a lehetőséget választja. |
| Legnépszerűbb               | Algoritmikus | Ez a modul a termék listáját jeleníti meg, amelyek az eladások száma alapján van rendezve. Ez a lista akkor jeleníti meg az aláírt felhasználó testreszabott eredményeit, ha a webhely szerzője ezt a lehetőséget választja. |
| Felkapott                   | Algoritmikus | Ez a modul az adott időszakra vonatkozóan a legjobban teljesítő termékek listáját jeleníti meg. Ez a lista akkor jeleníti meg az aláírt felhasználó testreszabott eredményeit, ha a webhely szerzője ezt a lehetőséget választja. |
| Gyakran együtt vásárolt | Mesterséges intelligencia/gép tanulás | Ez a modul gépi tanulást használ a fogyasztói vásárlási mintáinak elemzésére és olyan cikkeket ajánl fel, amelyeket gyakran megvásárolnak az adott termékkel együtt. Ez a lista akkor jeleníti meg az aláírt felhasználó testreszabott eredményeit, ha a webhely szerzője ezt a lehetőséget választja. |
| Szintén kedvelt           | Mesterséges intelligencia/gép tanulás | Ez a modul gépi tanulást használ a fogyasztói vásárlási mintáinak elemzésére és olyan cikkeket ajánl fel, amelyek egy adott termékhez kapcsolódnak. Ez a lista akkor jeleníti meg az aláírt felhasználó testreszabott eredményeit, ha a webhely szerzője ezt a lehetőséget választja. |
| Önnek ajánljuk              | Mesterséges intelligencia/gép tanulás | Ez a modul gépi tanulást használ a bejelentkezett felhasználók vásárlási mintáinak elemzésére, és olyan személyre szabott javaslatokat biztosít, amelyek ezeken a vásárlási mintákon alapulnak. A vendégfelhasználó számára ez a lista összecsukott állapotban lesz. |

## <a name="add-a-product-collection-module-to-a-category-page"></a>Termékgyűjtési modul hozzáadása egy kategórialaphoz

A következő lépésekkel lehet hozzáadni egy termékgyűjtési modult egy kategóriához.

1. A Dynamics 365 Commerce alkalmazásban nyissa meg webhelyét, és hozzon létre egy olyan lapot, amely ugyanazt a sablont használja, mint az alapértelmezett kategórialap.
1. Az oldalstruktúrában válassza ki az válassza ki az **Allábléc** helyet, jelölje ki a három pontot (**…**) majd válassza a **Modul hozzáadása** elemet.
1. A **Modul hozzáadása** párbeszédpanelen válassza a **Tároló** elemet, majd kattintson az **OK** gombra.
1. A tároló moduljában válassza ki a modulhoz tartozó három pont gombot (…), majd válassza a **Modul hozzáadása** elemet.
1. A **Modul hozzáadása** párbeszédpanelen válassza a **Termékgyűjtemény** elemet, majd kattintson az **OK** gombra.  
![Termékgyűjtő modul varázsló folyamatának példája](./media/productCollectionModule.png)
1. A beállításokat a megfelelő adatforrás és bemenetek kiválasztásával konfigurálhatja a termékgyűjteményhez.
1. A termékgyűjtési modultulajdonságok ablaktábláján válassza ki a **Terméklista hozzáadása** elemet.
1. A **Terméklista-konfiguráció kiválasztása** párbeszédpanelen válassza ki a lista típusát, adja meg a cikkek számát, és válassza ki a lista típusához rendelkezésre álló egyéb beállításokat. A lista típusokkal kapcsolatosan a következő táblázatban olvashat bővebben. 
1. Válassza ki az **OK** lehetőséget.
1. Mentse ez oldalt, majd küldje azt be.

A következő táblázat felsorolja azokat a lista-típusokat, amelyek a **Terméklista-konfiguráció kiválasztása** párbeszédpanelen választhatók ki.

| Típus                       | Leírás | Használat | Oldalkörnyezet | Specifikus környezet | Személyre szabás |
|----------------------------|-------------|-------|--------------|------------------|-----------------|
| Termékek kategóriák szerint       | Egy adott kategóriába tartozó termékek listája. Ez a kategória a lap környezetéből vagy a szerző által biztosított környezetből van meghatározva. | Ez a listatípus bármely oldalon használható (például kezdőoldal, kategóriaoldal, marketingoldal vagy termékrészletek oldal \[PDP\]) egy adott termékkategória reklámozásához. | Kategória az oldalkörnyezetből, ahol elérhető (például egy kategóriaoldal) | A szerző egy adott kategóriát adhat meg a lista kontextusaként. | Nem alkalmazható |
| Kapcsolódó termékek           | Azoknak a termékeknek a listája, amelyeket a termékmenedzser kapcsolódó termékekként állított be a Retail alkalmazásban az objektumkapcsolati típushoz. | Ez a listástípus elsődlegesen a PDP-k esetében használatos, de bármely oldalon használható, ha a szülő termék rendelkezésre áll. | Termék az oldalról, kapcsolat típusa (kötelező) | A termék kijelölhető a választóban, és a kapcsolattípus kerül felhasználásra. | Nem alkalmazható |
| Összeállította                    | Egy egyéni lista, amelyet a kereskedők és szerkesztők hoztak létre a Retail alkalmazásban. | Gazdagíthatja a kategória oldalát, a kezdőlapot, a pénztár és a kosár lapjait és a terméklapokat. | Nem alkalmazható | Nem alkalmazható | Nem alkalmazható |
| Algoritmikus                | <ul><li>**Új** – A csatornákhoz és katalógusokhoz hozzárendelt legújabb termékek listája.</li><li>**Legnépszerűbb** – Termék listája amelyek az eladások száma alapján van rendezve.</li><li>**Népszerű** – Az adott időszakra vonatkozóan a legjobban teljesítő termékek listája.</li></ul> | Kezdőlap, kategóriaoldal és pénztári és kosároldalak bővítése | Kategória az oldalkörnyezetből (például egy kategóriaoldal) | A webhely szerzője által meghatározott kategória | Támogatott |
| Gyakran együtt vásárolt | Ez a lista gépi tanulást használ a fogyasztói vásárlási mintáinak elemzésére és olyan cikkeket ajánl fel, amelyeket gyakran megvásárolnak az adott termékkel együtt. | Az ilyen típusú lista csak a kosárlapra vonatkozik. | Kosár | Nem alkalmazható | Támogatott |
| Szintén kedvelt           | Ez a lista gépi tanulást használ a fogyasztói vásárlási mintáinak elemzésére és olyan cikkeket ajánl fel, amelyek egy adott termékhez kapcsolódnak. | Az ilyen típusú listát a PDP-ken használják azon termékek megjelenítéséhez, amelyeket más ügyfelek vásároltak. | Termékkontextus az oldalról | A webhely szerzője által megadott termék | Támogatott |
| Önnek ajánljuk              | Az ügyfélpreferenciák meghatározásához a gépi tanulást alkalmazó lista. | Ez a listatípus bármely oldalon használható. | Nem alkalmazható| Nem alkalmazható | Támogatott | 

## <a name="additional-resources"></a>További erőforrások

[Kezdő csomag áttekintése](starter-kit-overview.md)

[Forgótármodul](add-carousel.md)

[Tartalomgazdag blokkmodul](add-content-rich-block.md)

[Tartalomelhelyezési modul](add-content-placement-modules.md)

[Tárolómodul](add-container-module.md)

[Vásárlásmező-modul](add-buy-box.md)

[Termékajánlatok áttekintése](product-recommendations.md)
