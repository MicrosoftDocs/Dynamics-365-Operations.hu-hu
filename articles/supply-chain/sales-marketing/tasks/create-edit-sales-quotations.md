--- 
title: "Értékesítési ajánlatok létrehozása és szerkesztése"
description: "Ez az eljárás bemutatja, hogyan hozhat létre és frissíthet értékesítési árajánlatokat."
author: omulvad
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SalesQuotationListPage, SalesCreateQuotation, SalesQuotationTable, SalesQuotationTotals, SalesQuotationPriceSimulation, SalesQuotationEditLines, SrsReportViewerForm, smmSetNumSeqIfManual, CustTable, SalesTable
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: f56b495131836689395a2124d5a834579e1646b7
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="create-and-edit-sales-quotations"></a>Értékesítési ajánlatok létrehozása és szerkesztése

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ez az eljárás bemutatja, hogyan hozhat létre és frissíthet értékesítési árajánlatokat. Ezt a folyamatot saját adatokkal, vagy az USMF bemutatócég adataival is futtathatja.


## <a name="create-a-sales-quotation"></a>Értékesítési ajánlat létrehozása
1. Lépjen az Értékesítés és marketing > Értékesítési árajánlatok > Minden árajánlat menüpontba.
2. Kattintson az Új lehetőségre.
3. A Fiók típusa mezőben válassza ki a „Potenciális vevő” lehetőséget.
4. A Potenciális vevő mezőben adjon meg vagy válasszon ki egy értéket.
5. Bontsa ki az Általános szakaszt.
    * Mivel azt választotta, hogy az Értékesítés és Marketing területről hoz létre árajánlatot, a típus automatikusan Értékesítési árajánlat lesz. Ha projekthez akar árajánlatot létrehozni, akkor a Projektvezetés és könyvelés modulból kell hozzáférnie.   
6. Kattintson az OK gombra.
    * A mezők és a műveletek az ajánlati sorok esetében nagyon hasonlítanak az értékesítésirendelés-sorokhoz tartozókhoz.   Az értékesítési rendelésekhez hasonlóan az árajánlatokat létre lehet hozni egy konkrét cikkhez, vagy ha a cikkszám nem ismert vagy nem létezik az árajánlat létrehozásásnak időpontjában, létre lehet hozni az értékesítési kategóriában.  
7. A Cikk mezőben adjon meg vagy válasszon ki egy értéket.
8. Írjon be egy értéket a Cikk mezőbe.
9. Zárja be a lapot.
10. Adjon meg egy számot a Mennyiség mezőben.
    * Ha a sorban a kiválasztott elemhez tartoznak érvényes kereskedelmi megállapodások, akkor az alkalmazandó ár és engedmények automatikusan átmásolódnak az árajánlati sorba. Győződjön meg arról, hogy az Egységár mező tartalmaz értéket, és megadhat engedmény értékeket is, ha szeretne  
11. Kattintson a Mentés gombra.
12. A Művelet panelen kattintson az Értékesítési ajánlat elemre.
13. Kattintson az Összegek lehetőségre.
14. Kattintson az OK gombra.
15. Kattintson az Értékesítésiajánlat-sor lehetőségre.
16. Kattintson az Árak lehetőségre.
    * Az Árszimuláció futtatása lapon kísérletezhet az érajánlat várt bevételének vagy jövedelmezőségének beállításával a kívánt egységár, kedvezményösszeg, kedvezményszázalék, teljes összeg, árrés vagy hozzájárulási arány alapján.   Ha elégedett a cél számokkal, alkalmazza a javaslatot az ajánlati sorra, és az árral kapcsolatos mezői ennek megfelelően frissülni fognak..  
    * Annyi árszimulációt végezhet amennyit akar. Ha az Új gombra kattint az aktuálisár ajánlati sorból az árfeltételek átmásolódnak a lapra. Ezután módosíthatja, a célok árral kapcsolatos mezőinek értékeit. A mezők valamelyikén végzett változása elindítja az összes mező újraszámítását. Ahhoz, hogy a rendszer kiszámolja az értékesítési árrést és hozzájárulási arányt a termék egységköltségét ismerni kell. A Szimulált árak lapon részletesen megtekinthetők az eredeti árak, a javasolt módosítások és hatásaik az árajánlati összegekre.   Általános szabályként elmondható, hogy amikor egy új összeget beállító szimulációt alkalmaznak az árajánlati sorra, a rendszer újraszámolja, és egy új értéket ír be az Egységár mezőbe. Ha szimuláció alapja egy új árrés vagy egy új hozzájárulási arány, csak a Nettó összeg mező frissül, és az Egységár üres marad. Mindkét esetben törlődnek az engedmények, amelyek az árajánlati soron voltak a szimuláció előtt.  
17. Zárja be a lapot.
18. A Művelet panelen kattintson az Árajánlat elemre.
19. Kattintson az Árajánlat küldése elemre.
20. Válassza az Igen lehetőséget az Árajánlat nyomtatása mezőben.
21. Kattintson az OK gombra.
    * A jelentés létrehozása egy percig is eltarthat. Amíg ez meg nem történik ne zárja be a lapot.  
22. Zárja be a lapot.

## <a name="update-a-sales-quotation"></a>Értékesítési ajánlat frissítése
1. A műveleti panelen kattintson a Követés elemre.
2. Kattintson a Konvertálás vevővé elemre.
3. Írjon be egy értéket a Vevői számla mezőbe.
4. Kattintson az ellenőrzés lehetőségre.
    * Ellenőrizze, hogy megjelenik-e egy üzenet, amely szerint a megadott számlaszám szabadon használható.  
5. Kattintson az OK gombra.
    * A rendszer most létrehozott egy új vevőszámlát, a potenciális vevőhöz az árajánlaton.  
6. Zárja be a lapot.
7. A műveleti panelen kattintson a Követés elemre.
8. Kattintson a Megerősítés gombra.
9. A Ok mezőben adjon meg vagy válasszon ki egy értéket.
10. Kattintson az OK gombra.
11. A Művelet panelen kattintson az Általános elemre.
12. Kattintson az Értékesítési rendelések elemre.
13. Zárja be a lapot.


