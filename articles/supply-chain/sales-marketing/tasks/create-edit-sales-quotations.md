---
title: Értékesítési ajánlatok létrehozása és szerkesztése
description: Ez az eljárás bemutatja, hogyan hozhat létre és frissíthet értékesítési árajánlatokat.
author: omulvad
manager: tfehr
ms.date: 06/26/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesQuotationListPage, SalesCreateQuotation, SalesQuotationTable, SalesQuotationTotals, SalesQuotationPriceSimulation, SalesQuotationEditLines, SrsReportViewerForm, smmSetNumSeqIfManual, CustTable, SalesTable, CustQuotationConfirmationJournal, CustQuotationJournal, CustSalesLines, SalesQuotationCopying, SalesQuotationDeleteQuotations, SalesQuotationListPagePreviewPane, SalesQuotationTypeGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 73c15b41a4b0979ec79c8dbd8d88627bffcf6ed3
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4429324"
---
# <a name="create-and-edit-sales-quotations"></a>Értékesítési ajánlatok létrehozása és szerkesztése

[!include [banner](../../includes/banner.md)]

Ez az eljárás bemutatja, hogyan hozhat létre és frissíthet értékesítési árajánlatokat. Ezt a folyamatot saját adatokkal, vagy az USMF bemutatócég adataival is futtathatja.


## <a name="create-a-sales-quotation"></a>Értékesítési ajánlat létrehozása
1. Ugorjon az **Navigációs lap > Modulok > Értékesítés és marketing > Értékesítési ajánlatok > Minden ajánlat** pontra.
2. Kattintson az **Új** elemre.
3. A **Fiók típusa** mezőben válassza ki a „Potenciális vevő” lehetőséget.
4. A **Potenciális vevő** mezőben adjon meg vagy válasszon ki egy értéket.
5. Bontsa ki az **Általános** szakaszt. Mivel azt választotta, hogy az Értékesítés és Marketing területről hoz létre árajánlatot, a típus automatikusan „Értékesítési árajánlat” lesz. Ha projekthez akar árajánlatot létrehozni, akkor a **Projektvezetés és könyvelés** modulból kell hozzáférnie.
6. Kattintson az **OK** gombra. A mezők és a műveletek az ajánlati sorok esetében nagyon hasonlítanak az értékesítésirendelés-sorokhoz tartozókhoz.   Az értékesítési rendelésekhez hasonlóan az árajánlatokat létre lehet hozni egy konkrét cikkhez, vagy ha a cikkszám nem ismert vagy nem létezik az árajánlat létrehozásásnak időpontjában, létre lehet hozni az értékesítési kategóriában.     
7. A **Cikk** mezőben adjon meg vagy válasszon ki egy értéket.
8. Adjon meg egy értéket a **Telephely** mezőben.
9. Adjon meg egy számot a **Mennyiség** mezőben. Ha a sorban a kiválasztott elemhez tartoznak érvényes kereskedelmi megállapodások, akkor az alkalmazandó ár és engedmények automatikusan átmásolódnak az árajánlati sorba. Győződjön meg arról, hogy az Egységár mező tartalmaz értéket, és megadhat engedmény értékeket is, ha szeretne 
10. Kattintson a **Mentés** gombra.
11. A **Művelet panelen** kattintson az **Értékesítési ajánlat** elemre.
12. Kattintson az **Összegre** lehetőségre.
13. Kattintson az **OK** gombra.
14. Jelölje ki az értékesítési ajánlat sorát.
15. A **Művelet panelen** kattintson az **Árajánlat** elemre.
16. Kattintson az **Árszimuláció** lehetőségre.
    - Az **Árszimuláció futtatása** lapon kísérletezhet az érajánlat várt bevételének vagy jövedelmezőségének beállításával a kívánt egységár, kedvezményösszeg, kedvezményszázalék, teljes összeg, árrés vagy hozzájárulási arány alapján. Ha elégedett a cél számokkal, alkalmazza a javaslatot az ajánlati sorra, és az árral kapcsolatos mezői ennek megfelelően frissülni fognak..  
    - Annyi árszimulációt végezhet, amennyit szeretne. Ha az **Új** gombra kattint az aktuálisár ajánlati sorból az árfeltételek átmásolódnak a lapra. Ezután módosíthatja, a célok árral kapcsolatos mezőinek értékeit. A mezők valamelyikén végzett változása elindítja az összes mező újraszámítását. Ahhoz, hogy a rendszer kiszámolja az értékesítési árrést és hozzájárulási arányt a termék egységköltségét ismerni kell. A Szimulált árak lapon részletesen megtekinthetők az eredeti árak, a javasolt módosítások és hatásaik az árajánlati összegekre. Általános szabályként elmondható, hogy amikor egy új összeget beállító szimulációt alkalmaznak az árajánlati sorra, a rendszer újraszámolja, és egy új értéket ír be az Egységár mezőbe. Ha szimuláció alapja egy új árrés vagy egy új hozzájárulási arány, csak a Nettó összeg mező frissül, és az Egységár üres marad. Mindkét esetben törlődnek az engedmények, amelyek az árajánlati soron voltak a szimuláció előtt.
17. A **Művelet panelen** kattintson az **Árajánlat** elemre.
18. Kattintson az **Árajánlat küldése** elemre.
19. Válassza az „Igen” lehetőséget az **Árajánlat nyomtatása** mezőben.
20. Kattintson az **OK** gombra. A jelentés létrehozása egy percig is eltarthat. Amíg ez meg nem történik ne zárja be a lapot.

## <a name="update-a-sales-quotation"></a>Értékesítési ajánlat frissítése
1. Ugorjon az **Navigációs lap > Modulok > Értékesítés és marketing > Értékesítési ajánlatok > Minden ajánlat** pontra.
2. A **Műveleti panelen** kattintson a **Követés** elemre.
3. Kattintson a **Konvertálás vevővé** elemre.
4. Írjon be egy értéket a **Vevői számla** mezőbe.
5. Kattintson az **Ellenőrzés** lehetőségre. Ellenőrizze, hogy megjelenik-e egy üzenet, amely szerint a megadott számlaszám szabadon használható.  
6. Kattintson az **OK** gombra. A rendszer most létrehozott egy új vevőszámlát, a potenciális vevőhöz az árajánlaton.  
7. Zárja be a lapot.
8. A **Műveleti panelen** kattintson a **Követés** elemre.
9. Kattintson a **Megerősítés** gombra.
10. Az **Ok** mezőben adjon meg vagy válasszon ki egy értéket.
11. Kattintson az **OK** gombra.
12. A **Művelet panelen** kattintson az **Általános** elemre.
13. Kattintson az **Értékesítési rendelések** gombra.
14. Zárja be a lapot.

