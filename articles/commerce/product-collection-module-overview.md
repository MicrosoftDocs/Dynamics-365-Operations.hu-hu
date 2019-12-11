---
title: Termékgyűjtési modulok
description: Ez a témakör áttekintést nyújt a Microsoft Dynamics 365 Commerce termékgyűjtési moduljairól.
author: v-chgri
manager: annbe
ms.date: 10/01/2019
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
ms.openlocfilehash: 44f78b55b8e67b7358be75aa63c40a0147507e26
ms.sourcegitcommit: 3a4e137ef3a96ba0a58c5352f4a3b57467ace9ae
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/11/2019
ms.locfileid: "2785467"
---
# <a name="product-collection-modules"></a>Termékgyűjtési modulok  

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Ez a témakör áttekintést nyújt a Microsoft Dynamics 365 Commerce termékgyűjtési moduljairól.

## <a name="overview"></a>Áttekintés

A termékfelfedezés elsődleges eszköz, amellyel a kiskereskedők az e-kereskedelmi weboldalakon keresztül együttműködhetnek vevőikkel. A termékgyűjtési modulok segítenek a kiskereskedőknek a vonzó vásárlási élmények létrehozásában, és intuitív vizuális kezelőfelületet létrehozásában, amely a termékgyűjtemények gyors összeállítására használható.

A termékgyűjtési modulok a webhely fizikai termékeit és szolgáltatásait jelenítik meg. A termékgyűjtési modul általában olyan egy részletek oldalhoz van csatolva, ahol a vevők megvásárolhatnak egy terméket vagy szolgáltatást, illetve többet tudhatnak meg arról. 

A temékgyűjtemények forrásai három típusba foglalhatók:

- A termékek szerkesztői listái, amelyek manuálisan vannak definiálva a Dynamics 365 Retail alkalmazásban egy termék vagy terméklista kapcsolódó termékeiként.
- Algoritmikus listák, mint például az új, legnépszerűbb vagy trendi termékek listái
- A gépi tanuláson alapuló ajánlati listák

A következő ábra bemutatja az e-kereskedelmi webhelyeken használt termékgyűjtemények különböző típusait.

![Példa egy e-kereskedelmi webhely különböző típusú termékgyűjteményére](./media/ProductCollectionsAcrossTheSiteUseProductPlacement.png)

> [!NOTE]
> Hasonló típusú vagy témájú termékek csoportjának megjelenítéséhez mindig a temékgyűjtési modulokat használja.

## <a name="product-collection-modules-and-types"></a>Termékgyűjtési modulok és típusok

A következő táblázat leírja a Dynamics 365 Commerce különböző típusú termékgyűjtési moduljait.

| Termékgyűjtési modul  | Típus | Leírás |
|----------------------------|------|-------------|
| Kategóriatallózás            | Szerkesztői | Ez a termékgyűjtési modultípus a navigációs kategóriahierarchiát használja, amelyet a kiskereskedelmi csatornához készített kiskereskedő egy adott webhelykategóriában kínált termékek tallózási folyamatának megjelenítéséhez. |
| Keresési eredmények             | Keresési lekérdezés | Ez a termékgyűjtési modul olyan termékek listáját jeleníti meg, amelyek legjobban megfelelnek a vevő által megadott keresésnek. |
| Kapcsolódó termékek           | Szerkesztői | Ez a termékgyűjtési modul felsorolja azokat a termékeket, amelyekhez a termékmenedzser kapcsolódó terméket állított be a Retailben, ahhoz a kapcsolattípushoz, amit a szerkesztő kiválasztott. |
| Válogatott terméklisták      | Szerkesztői | Ez a termékgyűjtési modul egyéni listákat jelenít meg, amelyekkel a kereskedők és szerkesztők a létrehoztak a Retail alkalmazásban. |
| Új                        | Algoritmikus | Ez a termékgyűjtési modul felsorolja azokat a legújabb termékeket, amelyek a csatornákhoz és a katalógusokhoz lettek hozzárendelve. |
| Legnépszerűbb               | Algoritmikus | Ez a termékgyűjtemény modul felsorolja azokat a termékeket, amelyekből a legtöbbet adták el. |
| Felkapott                   | Algoritmikus | Ez a termékgyűjtési modul egy adott időszakra vonatkozóan megjeleníti a legjobban teljesítő termékek listáját. |
| Gyakran együtt vásárolt | Mesterséges intelligencia/gép tanulás | Ez a termékgyűjtési modul gépi tanulást használ a fogyasztói vásárlási mintáinak elemzésére és olyan cikkeket ajánl fel, amelyeket gyakran megvásárolnak az adott termékkel együtt. |
| Szintén kedvelt           | Mesterséges intelligencia/gép tanulás | Ez a termékgyűjtési modul gépi tanulást használ a fogyasztói vásárlási mintáinak elemzésére és olyan cikkeket ajánl fel, amelyek kapcsolódnak az adott termékhez. |

## <a name="add-a-product-collection-module-to-a-category-page"></a>Termékgyűjtési modul hozzáadása egy kategórialaphoz

A következő lépésekkel lehet hozzáadni egy termékgyűjtési modult egy kategóriához.

1. A Dynamics 365 Commerce alkalmazásban nyissa meg webhelyét, és hozzon létre egy olyan lapot, amely ugyanazt a sablont használja, mint az alapértelmezett kategórialap.
1. Az oldalstruktúrában válassza ki az válassza ki az **Allábléc** helyet, jelölje ki a három pontot (**…**) majd válassza a **Modul hozzáadása** elemet.
1. A **Modul hozzáadása** párbeszédpanelen válassza a **Tároló** elemet, majd kattintson az **OK** gombra.
1. A tároló moduljában válassza ki a modulhoz tartozó három pont gombot (…), majd válassza a **Modul hozzáadása** elemet.
1. A **Modul hozzáadása** párbeszédpanelen válassza a **Termékgyűjtemény** elemet, majd kattintson az **OK** gombra.
1. A beállításokat a megfelelő adatforrás és bemenetek kiválasztásával konfigurálhatja a termékgyűjteményhez.
1. A termékgyűjtési modultulajdonságok ablaktábláján válassza ki a **Terméklista hozzáadása** elemet.
1. A **Terméklista-konfiguráció kiválasztása** párbeszédpanelen válassza ki a lista típusát, adja meg a cikkek számát, és válassza ki a lista típusához rendelkezésre álló egyéb beállításokat. A lista típusokkal kapcsolatosan a következő táblázatban olvashat bővebben. 
1. Válassza ki az **OK** lehetőséget.
1. Mentse ez oldalt, majd küldje azt be.

A következő táblázat felsorolja azokat a lista-típusokat, amelyek a **Terméklista-konfiguráció kiválasztása** párbeszédpanelen választhatók ki.
   
| Típus                       | Leírás | Általános gyakorlat | A lapkörnyezetből származtatható környezet | Az a környezet, amellyel a szerző felülbírálhatja a lap környezetét. |
|----------------------------|-------------|------------------|-------------------------------------|-----------------------------------------------|
| Termékek kategóriák szerint       | Egy adott kategóriába tartozó termékek listája. Ez a kategória a lap környezetéből vagy a szerző által biztosított környezetből van meghatározva. | Gazdagíthatja a kategória oldalát, a kezdőlapot, a pénztár és a kosár lapjait és a terméklapokat. | Kategória | Szerző által meghatározott kategória |
| Kapcsolódó termékek           | Azoknak a termékeknek a listája, amelyeket a termékmenedzser kapcsolódó termékekként állított be a Retail alkalmazásban az objektumkapcsolati típushoz. | Termékoldalak, pénztári és kosároldalak, kívánságlista oldalak és ügyfélfiók oldala | Termék, objektumkapcsolati típus (kötelező)  | Termék, objektumkapcsolat típusa |
| Összeállította                    | Egy egyéni lista, amelyet a kereskedők és szerkesztők hoztak létre a Retail alkalmazásban. | Gazdagíthatja a kategória oldalát, a kezdőlapot, a pénztár és a kosár lapjait és a terméklapokat. | Nem alkalmazható | Listaválasztó |
| Algoritmikus                | <ul><li>**Új** – A csatornákhoz és katalógusokhoz hozzárendelt legújabb termékek listája.</li><li>**Legnépszerűbb** – Termék listája amelyek az eladások száma alapján van rendezve.</li><li>**Népszerű** – Az adott időszakra vonatkozóan a legjobban teljesítő termékek listája.</li></ul> | Kezdőlap, kategóriaoldal és pénztári és kosároldalak bővítése | Kategória | Szerző által meghatározott kategória |
| Gyakran együtt vásárolt | Ez a lista gépi tanulást használ a fogyasztói vásárlási mintáinak elemzésére és olyan cikkeket ajánl fel, amelyeket gyakran megvásárolnak az adott termékkel együtt. | Termékoldalak és pénztári és kosároldalak | Termék, kosár | Kosárral együtt |
| Szintén kedvelt           | Ez a lista gépi tanulást használ a fogyasztói vásárlási mintáinak elemzésére és olyan cikkeket ajánl fel, amelyek egy adott termékhez kapcsolódnak. | Termékoldalak és pénztári és kosároldalak | Termék, kosár | Nem alkalmazható |

## <a name="additional-resources"></a>További erőforrások

[Kezdő csomag áttekintése](starter-kit-overview.md)

[Forgótármodul](add-carousel.md)

[Tartalomgazdag blokkmodul](add-content-rich-block.md)

[Tartalomelhelyezési modul](add-content-placement-modules.md)

[Tárolómodul](add-container-module.md)

[Vásárlásmező modul](add-buy-box.md)
