---
title: Árszimuláció
description: Ez a cikk az árajánlatokra vonatkozó árszimulációval kapcsolatban tartalmaz információt. Az árszimuláció segít felbecsülni a jövőbeni árajánlati folyamat alatti eladási árok csökkenését, még mielőtt meghatározni egy konkrét árat.
author: omulvad
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesQuotationPriceSimulation, SalesQuotationsTableLookup
audience: Application User
ms.reviewer: kamaybac
ms.custom: 12254
ms.assetid: 92be7c85-73cf-4f77-833c-d37ce779a031
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7ef40fb01352bce3c4f9848e0268ac548771120c
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4975035"
---
# <a name="price-simulation"></a>Árszimuláció

[!include [banner](../includes/banner.md)]

Ez a cikk az árajánlatokra vonatkozó árszimulációval kapcsolatban tartalmaz információt. Az árszimuláció segít felbecsülni a jövőbeni árajánlati folyamat alatti eladási árok csökkenését, még mielőtt meghatározni egy konkrét árat.

Az ajánlatok árszimulációja új végösszeget vagy sor szintű összeget jelenít meg vagy specifikus sorösszeget hoz létre egy külső ajánlathoz egy meglévő ajánlathoz egy javasolt új ár alapján. Az árszimuláció megmutathatja az új mennyiséget egy adott sorban, amelyet egy létező árajánlatban hoztak létre. Megadhatja az árszimulációt és később alkalmazhatja. Vagy csak később alkalmazza, vagy pedig választhatja az eredeti ajánlat használatát árszimuláció nélkül, és további változtatásokat hajthat végre, miközben a vevővel végighalad az értékesítési folyamaton.  

Az árszimuláció nem változtatja meg az árajánlatban szereplő árat. Ha az árszimulációt az egész árajánlatra alkalmazza, akkor azt egy speciális engedményként kell kezelni az árajánlat fejlécében. Ha az árszimulációt adott cikkekre alkalmazza, akkor azt egy speciális engedményként kell kezelni az árajánlat soraiban. A létrehozott ajánlati soron az egységenkénti eladási ár nem változik az árszimuláció futtatásakor. Ehelyett a program az ajánlati sor árengedményének megfelelő engedményszázalékot alkalmaz. Amikor alkalmazza az árszimulációt, az egységenkénti eladási ár és az engedményszázalék átkerül az ajánlati sorra vagy az ajánlat fejlécére.  

>[Megjegyzés:] Árszimuláció futtatásakor a program csak az aktuális értékesítési pénznemet használja a szimuláció létrehozásához. Amikor azonban megnézi az ajánlat végösszegeit, együtt látja a vállalati pénznemet és az értékesítési pénznemet.  

A kiegészítő cikkek, amelyeket hozzáad az árajánlat soraihoz sorkedvezményeket vagy többsoros kedvezményeket válthatnak ki. Továbbá kiválthatnak összengedményeket, amelyek megváltoztathatják pénzügyi árréseket és az árajánlat sorok árrés arányait és az egész engedményt.  

Az árszimuláció futtatásával nyomon követheti, hogy az ajánlat céljain milyen hatással vannak az árkorrekciók. A szimulációk futtatása lehetővé teszi az ajánlat teljes árának, illetve az ajánlaton belül egy vagy több konkrét sor árának korrekcióját, majd annak az árszimulációnak a futtatását, amely a legnagyobb valószínűséggel eredményezi az eladás sikeres létrejöttét.  

Ha létrehoz egy ajánlatot beállíthat figyelmeztetést. Íme néhány mód a figyelmeztetések használatára:

-   Naprakész maradhat a szervezet árajánlataival kapcsolatban.
-   Konkrét ajánlat felülvizsgálatát indíthatják el, vagy tájékoztathatják az engedménykorlátok eléréséről.

## <a name="price-simulation-and-discounts"></a>Árszimuláció és engedmények
Hogy az engedmények és árak kiszámítása mindig pontosan menjen végbe, az engedményekkel készülő ajánlatok árszimulációjának futtatásakor nagy figyelemmel kell eljárni. Mivel minden árszimulációt az aktív ajánlati sorra vagy a teljes ajánlatra vonatkozó különleges engedményként kezel a rendszer figyelemmel követni, hogy milyen különbségek állnak fenn az engedmények között.

### <a name="types-of-discounts-in-trade-agreements"></a>Kedvezmények típusai a kereskedelmi megállapodásokban

Kereskedelmi megállapodások a Supply Chain Management rendszerben négy árengedménytípust kínálnak. Ezek az engedmények különböző cikkekre, vevőkre vagy árcsoportokra lehetnek beállítva, és időben korlátozhatók. Téves számítások elkerülése végett figyelembe kell venni a kereskedelmi egyezményeket árszimulációk futtatásakor. A kereskedelmi megállapodások négy engedménytípusa:

-   **Értékesítési ár** – Cikkenkénti eladási árakat lehet meghatározni. Ajánlatkérési sorok létrehozásakor a program megkeresi a megfelelő eladási árat a cikkhez és továbbítja azt az árajánlat sorokhoz. Ebből következően egy ilyen típusú kereskedelmi megállapodás nincs hatással az árszimulációra. Az ajánlati sorban létrejövő ár a kereskedelmi megállapodáson alapul.
-   **Sorengedmény** – A cikkhez különleges engedmények adhatók meg, a rendelt mennyiségtől függően. A sorösszegek általában a sorkedvezményekkel csökkennek az árszimuláció futtatása előtt. Ebből következően egy ilyen típusú kereskedelmi megállapodás hatással van az árszimulációra.
-   **Többsoros engedmény** – Ha a kombinált mennyiségek túllépik az előre meghatározott határértéket, a megrendelt cikkek előre meghatározott kombinációi kiváltják egy engedmény alkalmazását a teljes rendelésre. A sorösszegek általában a sorkedvezményekkel csökkennek az árszimuláció futtatása előtt. Ebből következően egy ilyen típusú kereskedelmi megállapodás hatással van az árszimulációra.
-   **Összengedmény** – Ha a kombinált mennyiségek túllépik a meghatározott határértéket, az előre meghatározott rendelt cikkek kiváltják egy engedmény alkalmazását a teljes rendelésre. Az összengedményt az árajánlat sorok hozzák létre. Ugyanakkor az összengedmény a teljes árajánlatban engedményként történő alkalmazása miatt csökken az árajánlat teljes összege. Ebből következően egy ilyen típusú kereskedelmi megállapodás hatással van az árszimulációra.

### <a name="quotation-lines-and-trade-agreements"></a>Ajánlati sorok és kereskedelmi megállapodások

Amikor elkészít vagy módosít egy árajánlati sort, akkor a sorkedvezmények automatikusan kiszámításra kerülnek. Az adott cikk értékesítési ára meghatározva, a kereskedelmi megállapodás alapján.

## <a name="price-simulation-examples"></a>Árszimuláció – példák
Az alábbi példák bemutatják az árszimuláció használatot az ajánlati fejlécnél és egyetlen cikksornál.

### <a name="price-simulation-for-quotation-headers"></a>Árszimuláció árajánlatok fejlécéhez

Létrehoz egy árajánlatot, amely a következő sorokat tartalmazza:

-   10 egység a BR-12 cikkből (egységenkénti önköltségi ár: 9,52 USD, egységenkénti eladási ár: 15,32 USD)
-   12 egység a BR-14 cikkből (egységenkénti önköltségi ár: 7,48 USD, egységenkénti eladási ár: 13,75 USD)

A következő táblázat mutatja az árajánlat sorait.

|    &nbsp;                  | Számítás                          | Eredmény   |
|----------------------------|--------------------------------------|----------|
| Értékesítési mennyiség             | 10 egység + 12 egység                  | 22 egység |
| Eladási érték forintban         | (10 × 15,32) + (12 × 13,75)          | 31820   |
| Önköltség forintban          | (10 × 9,52) + (12 × 7,48)            | 18496   |
| Árrés forintban | 31820 – 18496                      | 13324   |
| Hozzájárulás aránya         | (\[318,20-184,96\] ÷ 318,20) × 100 | 41,87%   |

Futtat egy árszimulációt, és 15 százalékos teljes engedményt ad a teljes árajánlatra vagy az árajánlat fejlécére. A következő táblázat mutatja az árajánlat új összegeit az árszimuláció futtatása után.

|     &nbsp;                                           | Számítás                               | Eredmény   |
|------------------------------------------------------|-------------------------------------------|----------|
| Értékesítési mennyiség                                       | 10 egység + 12 egység                       | 22 egység |
| Korábbi eladási érték forintban                               | (10 × 15,32) + (12 × 13,75)               | 31820   |
| Korábbi önköltség forintban                                | (10 × 9,52) + (12 × 7,48)                 | 18496   |
| Korábbi árrés forintban                       | 31820 – 18496                           | 13324   |
| Korábbi árrésarány                               | (\[318,20-(10 × 9,52)\] ÷ 318,20) × 100 | 41,87%   |
| Árszimuláció – 15 százalékos teljes engedmény forintban | (15 × 318,2) ÷ 100                        | 4773    |
| Új eladási érték forintban                               | 31820 – 4773                            | 27047   |
| Új árrés forintban                       | 27047 – 18496                           | 8551    |
| Új hozzájárulási arány                               | \[(270,47-184,96) ÷ 270,47\] × 100      | 31,61%   |

### <a name="price-simulation-for-single-line-items"></a>Árszimuláció egyes cikksorokhoz

Létrehoz egy árajánlatot, amely a következő sorokat tartalmazza:

-   10 egység a BR-12 cikkből (egységenkénti önköltségi ár: 9,52 USD, egységenkénti eladási ár: 15,32 USD)
-   12 egység a BR-14 cikkből (egységenkénti önköltségi ár: 7,48 USD, egységenkénti eladási ár: 13,75 USD)

A következő táblázat mutatja az árajánlat sorait.

|      &nbsp;                          | Számítás                          | Eredmény   |
|--------------------------------------|--------------------------------------|----------|
| Értékesítési mennyiség                       | 10 egység + 12 egység                  | 22 egység |
| A BR-12 eladási értéke forintban         | 10 × 15,32                           | 15320   |
| A BR-14 eladási értéke forintban         | 12 × 13.75                           | 16500   |
| A BR-12 költsége forintban          | 10 × 9,52                            | 9520    |
| A BR-14 költsége forintban          | 12 × 7,48                            | 8976    |
| A BR-12 árrése forintban | 15320 – 9520                       | 5800    |
| A BR-14 árrése forintban | 16500 – 8976                       | 7524    |
| A BR-12 árrésaránya forintban  | \[(153,20-95,20) ÷ 153,20\] × 100  | 3786    |
| A BR-14 árrésaránya forintban  | \[(165,00-89,76) ÷ 165,00\] × 100  | 4560    |
| Teljes eladási érték forintban             | (10 × 15,32) + (12 × 13,75)          | 31820   |
| Összes önköltség forintban              | (10 × 9,52) + (12 × 7,48)            | 18496   |
| Teljes árrés forintban     | 31820 – 18496                      | 13324   |
| Teljes árrésarány             | \[(318,20-184,96) ÷ 318,20\] × 100 | 41,87%   |

Futtat egy árszimulációt, és 10 százalékos teljes engedményt ad a BR-12 cikkekre. A következő táblázat mutatja az árajánlat új összegeit az egy cikksorra vonatkozó árszimuláció futtatása után.

|    &nbsp;                                         | Számítás                             | Eredmény   |
|---------------------------------------------------|-----------------------------------------|----------|
| Értékesítési mennyiség                                    | 10 egység + 12 egység                     | 22 egység |
| A BR-12 korábbi eladási értéke forintban                  | 10 × 15,32                              | 15320   |
| Árszimuláció – 10 százalékos engedmény a BR-12 cikkre | (10 × 153,2) ÷ 100                      | 1532    |
| A BR-12 új eladási értéke forintban                  | (10 × 15,32) – 15,32                    | 13788   |
| A BR-14 eladási értéke forintban                      | 12 × 13.75                              | 16500   |
| A BR-12 költsége forintban                       | 10 × 9,52                               | 9520    |
| A BR-14 költsége forintban                       | 12 × 7,48                               | 8976    |
| A BR-12 új árrése forintban          | 13788 – 9520                          | 4268    |
| A BR-14 árrése forintban              | 16500 – 8976                          | 7524    |
| A BR-12 új árrésaránya forintban           | \[(137,88-95,20) ÷ 137,88\] × 100     | 3095    |
| A BR-14 árrésaránya forintban               | \[(165,00-89,76) ÷ 165,00\] × 100     | 4560    |
| Új teljes eladási érték forintban                      | \[(10 × 15,32) – 15,32\] + (12 × 13,75) | 30288   |
| Összes önköltség forintban                           | (10 × 9,52) + (12 × 7,48)               | 18496   |
| Új teljes árrés forintban              | 30288 – 18496                         | 11792   |
| Új teljes árrésarány                      | \[(302,88-184,96) ÷ 302,88\] × 100    | 38.93%   |

Az árszimuláció csak azt a sort érinti, amelyre alkalmazták, csökkentve a sor összegét.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]