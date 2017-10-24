--- 
title: "Költségellenőrzési munkaterület paramétereinek konfigurációja"
description: "Ezzel az eljárással konfigurálhatja a Költségellenőrzési munkaterületet úgy, hogy a szervezeten belüli különböző szinteken lévő vezetők betekintést nyerhetnek a költségobjektumokba, például a költséghelyekbe és a termékcsoportokba."
author: YuyuScheller
manager: AnnBe
ms.date: 06/27/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 8ede40951d08e159358b713fc3dde46576a1b4e3
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="configure-cost-control-workspace-parameters"></a>Költségellenőrzési munkaterület paramétereinek konfigurációja

[!include[task guide banner](../../includes/task-guide-banner.md)]

Ezzel az eljárással konfigurálhatja a Költségellenőrzési munkaterületet úgy, hogy a szervezeten belüli különböző szinteken lévő vezetők betekintést nyerhetnek a költségobjektumokba, például a költséghelyekbe és a termékcsoportokba. A rendszer az USP2 bemutatócéget használta a rögzítés létrehozására.

1. Lépjen a Költségkönyvelés > Beállítás > Költségellenőrzési munkaterület konfigurációja lehetőségre.
2. Kattintson az Új lehetőségre.
3. Írjon be egy értéket a Név mezőbe.
4. A Leírás mezőben adjon meg egy értéket.
5. Válassza az Igen lehetőséget a Közzétéve mezőben.
    * Ha Igen értékre állítja ezt a beállítást, a következő szerepkörök valamelyikéhez hozzárendelt felhasználó láthatja a Költség-ellenőrzési munkaterület jelentését: költségkönyvelés-kezelő, költségkönyvelő, költségkönyvelő adminisztrátor vagy költségobjektum-ellenőr. Ha Nem értékre állítja ezt a beállítást, kizárólag a következő szerepkörök valamelyikéhez hozzárendelt felhasználó láthatja a Költség-ellenőrzési munkaterület jelentését: költségkönyvelés-kezelő, költségkönyvelő vagy költségkönyvelő adminisztrátor.  
6. Bontsa ki az Adatszűrés szakaszt.
7. A Költség-ellenőrzőegység mezőben adjon meg vagy válasszon ki egy értéket.
8. A Költségvetés eredeti verziója mezőben adjon meg vagy válasszon ki egy értéket.
9. A Költségösszetevő-dimenzió mezőben adjon meg vagy válasszon ki egy értéket.
10. A Költségobjektum dimenzióhierarchia mezőben adjon meg vagy válasszon ki egy értéket.
11. Bontsa ki a Számítási rekordok hozzárendelése szakaszt.
12. Kattintson az Új lehetőségre.
13. A listában jelölje meg a kiválasztott sort.
14. A Pénzügyi naptári időszak mezőben adjon meg vagy válasszon ki egy értéket.
15. A Tényleges verzió mezőben adjon meg vagy válasszon ki egy értéket.
16. Bontsa ki a Pénzügyi időszakok oszloponként szakaszt.
17. Válassza az Igen lehetőséget az Aktuális időszak mezőben.
18. Bontsa ki a Megjelenítendő oszlopok költségekhez szakaszt.
19. Válassza az Igen lehetőséget a Rögzített költség mezőben.
20. Válassza az Igen lehetőséget a Változó költség mezőben.
21. Válassza az Igen lehetőséget a Teljes költség mezőben.
22. Kattintson a Mentés gombra.
23. Zárja be a lapot.
24. Lépjen a Költségkönyvelés > Munkaterületek > Költségellenőrzés pontra.
25. Válasszon egy kimutatást rögzített, változó, összesített és nem besorolt költségek megtekintéséhez a kijelölt pénzügyi időszakokra vonatkozóan.
26. A Pénzügyi naptári időszak mezőben adjon meg vagy válasszon ki egy értéket.
27. A Költségobjektum dimenzióhierarchia-csomópont mezőben adjon meg vagy válasszon ki egy értéket.
    * A Költségobjektum dimenzióhierarchia kijelölése után bontsa ki a Költségösszetevő dimenzióhierarchiát a kívánt költségértékek megtekintése érdekében. Kibonthatja például a hierarchiát a Gyártási többletköltségre az érték megtekintése érdekében.  


