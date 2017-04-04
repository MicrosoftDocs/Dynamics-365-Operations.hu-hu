---
title: "A Költségkönyvelés elemzés kiemelt BI-tartalom"
description: "Ez a témakör azt ismerteti, mit tartalmaz a Költségkönyvelés elemzés kiemelt BI-tartalom. Ismerteti, hogyan lehet elérni a kiemelt BI jelentéseket, és tájékoztatást nyújt az adatmodell és a tartalom létrehozásához használt entitások."
author: YuyuScheller
manager: AnnBe
ms.date: 2017-04-04
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: Operations
ms.custom: 270274
ms.assetid: b74549df-35d5-4f2f-b3c7-405b0d38ea78
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 388b6398488e6f316c1ec07a00182e81c1dc8d08
ms.openlocfilehash: 50e7bd92ee693f59fd013226aee22bd1a54c81e2
ms.lasthandoff: 03/31/2017


---

# <a name="cost-accounting-analysis-power-bi-content"></a>A Költségkönyvelés elemzés kiemelt BI-tartalom

Ez a témakör azt ismerteti, mit tartalmaz a Költségkönyvelés elemzés kiemelt BI-tartalom. Ismerteti, hogyan lehet elérni a kiemelt BI jelentéseket, és tájékoztatást nyújt az adatmodell és a tartalom létrehozásához használt entitások.

<a name="overview"></a>Áttekintés
--------

A **a Költségkönyvelés elemzés** a Microsoft kiemelt BI tartalom költség vezérlők vagy olyan személy, aki felelős a szervezet Költségkontroll szánt. Ez magában foglalja a kulcs metrika, például a költség nagysága és tényleges költség, tervezett költség és költség rugalmas költségvetési költségszorzó. Költségkönyvelési tranzakciók adatait használja a Microsoft Dynamics 365 műveletekhez és a költségek egy összesítő nézetet biztosít a teljes szervezet számára kimutatási pénznemben. Vezetők szűrheti az adatokat a szervezeti egységek Költségkontroll végrehajtásához költség objektumok akkor is, ha a szervezet több jogi személyek lehetnek. Mert a **a Költségkönyvelés elemzés** Power BI tartalom kiemeli a tényleges és tervezett költségek közötti eltéréseket a működési egységek vezetői is értesítést kapni a pozitív és negatív tendenciák. Vezetők bepillantást részletes költségeltéréseket hogyan történt, és majd tesznek eredményes intézkedéseket a költség elem hierarchiák vagy egyes költségtényezők leáshat. A **a Költségkönyvelés elemzés** Power BI tartalom most költség könyvelők elemzése, hogyan folyik az költség a teljes szervezet költség objektumait. A Költségkönyvelés kapcsolatos további tudnivalókért lásd: [honlap Költségkönyvelés](/dynamics365/operations/financials/cost-accounting/cost-accounting-home-page.md). A Költségkönyvelés biztonsági hozzáférési szintjét meghatározó és kiemelt két sor szintű biztonsági és együttes azt, akkor minden költség objektum tulajdonos hozzáférést biztosíthat a **költségkönyvelési elemzés** Power BI-tartalom. A képi megjelenítések tartoznak az összes adat lesz majd szűrhető alapján milyen hozzáférési szinttel a Költségkönyvelés vezérelt. Ha többet szeretne megtudni a biztonsági hozzáférési szint és a sor szintű biztonság, lásd: [Power BI költségkönyvelési tartalom biztonsági beállítása](setup-security-cost-accounting-content-pack.md).

## <a name="accessing-the-power-bi-content"></a>A kiemelt BI-tartalom elérése
Megtalálhatja a **a Költségkönyvelés elemzés** kiemelt BI-tartalmat a megosztott eszközök könyvtárban a Microsoft Dynamics életciklus szolgáltatások (LCS). További információt a hogyan lehet letölteni a tartalmat, és csatlakoztassa a Dynamics 365 műveleti adatok, lásd: [a Microsoft és a partnerek LCS kiemelt BI-tartalom](power-bi-content-microsoft-partners.md). **Megjegyzés:** KB4011327 ** ** előfeltétele a **költségkönyvelési elemzés** Power BI-tartalom.  Életciklus szolgáltatásokhoz való bejelentkezést követően hozzáférhet a KB itt: <https://fix.lcs.dynamics.com/issue/results/?q=kb4011327>.

## <a name="metrics-that-are-included-in-the-power-bi-content"></a>A kiemelt BI tartalom található metrikák
A tartalom jelentés oldalak készletét tartalmazza. Minden oldal metrikák láthatóvá tehetők, mozaikok, táblázatok és diagramok, amelyek összessége alkotja. A következő táblázat áttekintést nyújt az a képi megjelenítések a a **költségkönyvelési elemzés** Power BI-tartalom.

| Jelentés lap                      | Diagram                                                                                                                         | Csempe                                          |
|----------------------------------|-------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------|
| Költségkontroll pénzügyi időszak szerint    | Tényleges költség és költség elem hierarchia által előirányzott költség                                                                   | Tényleges költség vs előirányzott költség                    |
|                                  | Költségvetés eltérése költség elem hierarchia szerint                                                                               | Tényleges költség sebesség vs költségvetési Díjtábla          |
|                                  | TOP 10 költségvetés eltérése a költségtényező százalékos aránya                                                                          | Tényleges nagysága vs költségvetés nagysága          |
| Költségkontroll év záró dátum szerint     | Tényleges és tervezett költség időszak a naptári év szerint                                                                           | Tényleges költség vs előirányzott költség                    |
|                                  | Költségvetés eltérése időszak a naptári év szerint                                                                                       | Tényleges költség sebesség vs költségvetési Díjtábla          |
|                                  | TOP 10 költségvetés eltérése a költségtényező százalékos aránya                                                                          | Tényleges nagysága vs költségvetés nagysága          |
| Költségszorzó pénzügyi év szerint         | Tényleges költségszorzó költség működése                                                                                             | Tényleges költség sebesség vs költségvetési Díjtábla          |
|                                  | Tényleges költségszorzó, költségvetési bekerülési árfolyam-különbözet, költségvetési költségek százalékos arányt és költségvetési költségszorzó költség elem hierarchia szerint | Tényleges nagysága vs költségvetés nagysága          |
|                                  | Költségvetés eltérése költség elem hierarchia szerint                                                                               |                                               |
|                                  | TOP 10 költségvetés eltérése a költségtényező százalékos aránya                                                                          |                                               |
| Rugalmas költségvetés pénzügyi időszak szerint | Tényleges költség, tervezett költség és költség elem hierarchia költségének rugalmas költségvetés                                             | Tényleges nagysága vs költségvetés nagysága          |
|                                  | Költségvetés eltérése és költség elem hierarchia szerint rugalmas költségvetés eltérése                                                  | Tényleges költség vs rugalmas költségvetés költség           |
|                                  | Tényleges költség, tervezett költség és rugalmas költség szerint viselkedés költség és költség elem hierarchia                                  | Tényleges költség sebesség vs rugalmas költségvetési költségszorzó |
| Költségkimutatás pénzügyi időszak szerint  | Tényleges költség elem hierarchia költség és költség objektum dimenzió tag neve                                             |                                               |
|                                  | Tényleges költség költség objektum dimenzió tag neve és a költség elem dimenzió tag neve                                       |                                               |

## <a name="understanding-the-data-model-and-entities"></a>Adatmodell, illetve entitások ismertetése
365 Dynamics műveleti adatok segítségével töltse ki a jelentés oldalt a **költségkönyvelési elemzés** Power BI-tartalom. Összesített mérések előkészítettek ki ezeket az adatokat az entitás üzlet Ez az analytics optimalizált Microsoft SQL adatbázis. További tudnivalókért lásd: [tároló entitás integráció kiemelt BI áttekintése](power-bi-integration-entity-store.md). A következő kulcs összesített mérések a tartalom alapjául szolgálnak.

| Entitás                  | Kulcs összesített támogatottsági mutató | Adatforrás Dynamics 365 műveletek | Mező     | Leírás                                   |
|-------------------------|---------------------------|---------------------------------------------|-----------|-----------------------------------------------|
| A Költségkönyvelés tételek | Sum(Amount)               | CAMDATAAggregatedCostEntry                  | Összeg    | A költségkönyvelés könyvelési pénznemben kifejezett összeg |
| Statisztikai bejegyzések     | Sum(magnitude)            | CAMDATAAggregatedStatisctialEntry           | Nagyság |                                               |

A következő táblázat a kulcs összesített mérések használata a tartalom dataset több számított mértékek létrehozására.

| Méret                                       | Az intézkedés kiszámításának módjáról                                                                                          |
|-----------------------------------------------|------------------------------------------------------------------------------------------------------------------------|
| Tényleges költség                                   | SZÁMÍTÁS ("a Költségkönyvelés bejegyzések"\[intézkedés\], "Tranzakció verziók"\[ISSOURCEVERSIONBUDGET\_értéke\] = 0)            |
| Előirányzott költség                                   | SZÁMÍTÁS ("a Költségkönyvelés bejegyzések"\[intézkedés\], "Tranzakció verziók"\[ISSOURCEVERSIONBUDGET\_értéke\] = 1)            |
| Előirányzott költség-különbözet                          | \[Előirányzott költség\] - \[tényleges költség\]                                                                                      |
| Költségvetési eltérés százaléka                    | IF (\[tervezett költség\] = 0, blank(), \[költségvetés eltérése\] / \[tervezett költség\])                                                |
| Tényleges nagysága                              | SZÁMÍTÁS ("Statisztikai bejegyzések"\[FullMagnitude\], "Tranzakció verziók"\[ISSOURCEVERSIONBUDGET\_értéke\] = 0)          |
| Költségvetés nagysága                              | SZÁMÍTÁS (\[FullMagnitude\], "Tranzakció verziók"\[ISSOURCEVERSIONBUDGET\_értéke\] = 1)                               |
| Statisztikai költségvetés eltérése                   | \[Költségvetés nagyságát\] - \[tényleges nagysága\]                                                                            |
| Költségvetési statisztikai eltérés százaléka        | IF (\[költségvetés nagyságát\] = 0, blank(), \[statisztikai költségvetés eltérése\] / \[költségvetés nagyságát\])                          |
| Tényleges költségszorzó                              | IF (\[tényleges nagyságának\] = 0, BLANK(), \[tényleges költsége\] / \[tényleges nagyságának\])                                          |
| Költségvetési költségszorzó                              | IF (\[költségvetés nagyságát\] = 0, BLANK(), \[tervezett költség\] / \[költségvetés nagyságát\])                                          |
| Előirányzott költség árfolyam-különbözet                     | \[Költségvetési költségszorzó\] - \[tényleges költségszorzó\]                                                                            |
| Előirányzott költség százalékos eltérés          | IF (\[tervezett költség\] = 0, blank(), \[sebesség költségeltérés költségvetési\] / \[költségvetési költségszorzó\])                                 |
| Költségvetésben rögzített költség                             | SZÁMÍTÁS (\[tervezett költség\], a "Költség könyvelési tételek"\[COSTBEHAVIOR\] = 1)                                              |
| Változó előirányzott költség                          | SZÁMÍTÁS (\[tervezett költség\], a "Költség könyvelési tételek"\[COSTBEHAVIOR\] = 2)                                              |
| Rugalmas költségvetésben rögzített költség                    | \[Költségvetésben rögzített költség\]                                                                                                  |
| Rugalmas költségvetés változó költség                 | IF (\[költségvetés nagyságát\] = 0, BLANK(), (\[változó tervezett költség\] / \[költségvetés nagyságát\]) \*\[tényleges nagyságának\])       |
| Rugalmas költségvetés költség                          | \[Fix költség rugalmas költségvetés\] + \[rugalmas költségvetés változó költség\]                                                     |
| Rugalmas költségvetés eltérése                      | \[Rugalmas költségvetés költség\] - \[tényleges költség\]                                                                             |
| Rugalmas költségvetés eltérés százaléka           | IF (\[rugalmas költségvetés költség\] = 0, BLANK(), \[rugalmas költségvetés eltérése\] / \[rugalmas költségvetés költség\])                     |
| Rugalmas költségvetés költség arány                     | IF (\[tényleges nagyságának\] = 0, BLANK(), \[rugalmas költségvetés költség\] / \[tényleges nagyságának\])                                 |
| Rugalmas költségvetés költség arány eltérése            | \[Rugalmas költségvetési költségszorzó\] - \[tényleges költségszorzó\]                                                                   |
| Rugalmas költségvetés sebesség költségeltérési százaléka | IF (\[rugalmas költségvetési költségszorzó\] = 0, BLANK(), \[sebesség költségeltérés rugalmas költségvetés\] / \[rugalmas költségvetési költségszorzó\]) |

A következő főbb dimenziókra használják szűrőként nagyobb részletesség elérése és mélyebb analitikai elképzelések összesített mérések szeletelhetők.

| Entitás                             | Példák az attribútumok                                                                                               |
|------------------------------------|----------------------------------------------------------------------------------------------------------------------|
| Költségkönyvelési főkönyvek            | Költségkönyvelési főkönyv                                                                                               |
| Költség-ellenőrzőegységek                 | Költség-ellenőrzőegység neve                                                                                               |
| Költségösszetevő-dimenziók            | Költség elemek dimenzióérték nevét, a költség elem dimenzió tag neve, a költség elem dimenzió tag leírása          |
| Költségobjektum-dimenziók             | Költség objektum dimenzió neve, a költség objektum dimenzió tag nevét, a költség objektum dimenzió tag leírás              |
| Statisztikai dimenziók             | Statisztikai dimenzió neve, a statisztikai dimenzió tag neve, a statisztikai dimenzió tag leírása              |
| A dimenzióhierarchiák költség objektum  | Dimenzió-hierarchia neve objektum költség, a költség objektum dimenzió-hierarchia szintje, költség objektum dimenzió Alkalmazáshierarchia-fa    |
| A dimenzióhierarchiák elem költség | Dimenzió-hierarchia neve elem költség, a költség elem dimenzió-hierarchia szintje, költség elem dimenzió Alkalmazáshierarchia-fa |
| Statisztikai dimenzió-hierarchiák  | Statisztikai dimenzió-hierarchia neve, statisztikai dimenzió hierarchia, statisztikai dimenzió Alkalmazáshierarchia-fa    |
| Tranzakcióverziók               | Verzió neve                                                                                                         |
| Pénzügyi naptárak                   | Naptár naptár leírása                                                                                       |
| Pénzügyi év                       | Naptári év                                                                                                        |
| Pénzügyi időszakok                     | Naptári éven                                                                                                 |

## <a name="additional-resources"></a>További erőforrások
Az alábbiakban néhány hasznos, entitásokkal és kiemelt Üzletiintelligencia-tartalommal kapcsolatos hivatkozást találhat:

-   [Adatentitások](..\data-entities\data-entities.md)
-   [Szervezeti tartalmi csomagok létrehozása](https://powerbi.microsoft.com/en-us/documentation/powerbi-service-organizational-content-packs-introduction/)
-   [Adatmodellezés az üzleti Intelligencia használatával](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-2-1-intro-modeling-data)
-   [Kiemelt Üzletiintelligencia-lapok hozzáadása munkaterületekhez](configure-power-bi-integration.md)
-   [Kiemelt BI költségkönyvelési tartalom biztonsági beállítása](setup-security-cost-accounting-content-pack.md)


