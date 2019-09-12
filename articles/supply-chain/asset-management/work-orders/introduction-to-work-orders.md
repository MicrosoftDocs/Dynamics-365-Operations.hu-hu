---
title: Bevezetés a munkarendelések használatába
description: Ez a témakör áttekintést ad az Eszközkezelésben használt munkarendelésekről.
author: josaw1
manager: AnnBe
ms.date: 08/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-15
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 9483c50a15fca566b1f5e089297795bbbe09c042
ms.sourcegitcommit: f5bfa3212bc3ef7d944a358ef08fe8863fd93b91
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/16/2019
ms.locfileid: "1875701"
---
# <a name="introduction-to-work-orders"></a>Bevezetés a munkarendelések használatába

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

A munkarendelések a karbantartási feladatokkal kezelésére a szükséges információk biztosítáásra és a fogyasztás regisztrálására használatosak Egy munkarendelés egy vagy több munkarendelés-feladatot tartalmaz, és egy vagy több eszköz a munkarendeléshez kapcsolható. Minden munkarendelési sor egy ütemezett karbantartási feladatot határoz meg az eszközön.

A munkarendeléseket létre lehet hozni manuálisan vagy automatikusan.

- A **Karbantartási tervek ütemezése** képernyő használatával automatikusan, a naptár alapú karbantartási tervekhez állítsa be az „Automatikus létrehozás” lehetőséget.  

- A **Karbantartási körök ütemezése** képernyő használatával automatikusan, a naptár alapú karbantartási körökhöz állítsa be az „Automatikus létrehozás” lehetőséget.  

- Létrehozás a karbantartási ütemezésből, amely lehet megelőző karbantartási feladat vagy karbantartási kérelem.  

- Munkarendelések létrehozása manuálisan.  

- Hozza létre a munkarendelést az **Összes karbantartási kérés**, az **Aktív karbantartási kérések** vagy a **Saját munkavégzési helyszínhez tartozó karbantartási kérések** helyről.

>[!NOTE]
>Az ugyanahhoz az eszközhöz kapcsolódó munkarendelés-feladatok ugyanahhoz a projektazonosítóhoz kapcsolódnak.

## <a name="all-work-orders"></a>Összes munkarendelés

Kattintson az **Eszközkezelés** > **Közös** > **Munkarendelések** > **Összes munkarendelés** elemre a lista megnyitásához. Az **Összes munkarendelés** tartalmazza az összes munkarendelés listáját, és megjeleníti egy munkarendeléssel vagy a munkarendelési munkával kapcsolatos adatokat.

![1. ábra](media/01-work-orders.png)

- Kattintson az **Eszközkezelés** > **Közös** > **Munkarendelések** > **Aktív munkarendelések** lehetőségre az aktív munkarendelések listájának megtekintéséhez.

- Kattintson az **Eszközkezelés** > **Közös** > **Munkarendelések** > **Saját munkavégzési helyszín munkarendelés karbantartási feladatai** lehetőségre a munkavégzési helyszínekre telepített eszközöket tartalmazó Munkarendelés-feladatok listájának megtekintéséhez, ön dolgozóként kapcsolódik ehhez (a [Karbantartási dolgozók és dolgozócsoportok](../setup-for-objects/workers-and-worker-groups.md) helyen beállítva).

- A kiválasztott rekord részletek nézetének megtekintéséhez az **Összes munkarendelés** listában (rácsnézet) kattintson egy hivatkozásra a **Munkarendelés** oszlopban. Szerkesztéshez kattintson a **Szerkesztés** gombra.  

- A Részletek nézetben a munkarendeléshez kapcsolódó részletes információk láthatók.  

- A Részletek nézetben válassza ki a **Sorok** hivatkozását a munkarendelés részleteinek megtekintéséhez, vagy válassza a **Fejléc** hivatkozást a munkarendelés részleteinek megtekintéséhez.  

- A képernyő jobb oldalán található függőleges **Kapcsolódó információk** panel további munkarendeléssel kapcsolatos információkat tartalmaz. Bontsa ki az ablaktáblát a kijelölt munkarendelés kapcsolódó információinak megjelenítéséhez.  


![2. ábra](media/02-work-orders.png)


A műveleti ablak gombjai lapokon vannak rendezve a műveleti ablakban. Az alábbiakban a vállalati eszközök kezelésével kapcsolatos gombok rövid leírása található.



| Gomb neve                     | Leírás                                                                                                                                                                                                                                                             |
|---------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Szerkesztés                            | A kijelölt munkarendelés szerkesztése                                                                                                                                                                                                                                           |
| Új                             | Új munkarendelés létrehozása.                                                                                                                                                                                                                                                  |
| Eltávolítás                          | A kijelölt munkarendelés törlése                                                                                                                                                                                                                                         |
| Munkarendelés-gyűjtő                 | A kiválasztott munkarendelés hozzáadása egy munkarendelésgyűjtőhöz vagy a eltávolítás a munkarendelésgyűjtőből.                                                                                                                                                                                           |
| Beállítás                          | A kiválasztott munkarendeléseken a várt kezdési és befejezés, szolgáltatási szint, felelős karbantartó dolgozó vagy felelős karbantartó dolgozói csoport adatainak módosítása.                                                                                                                                     |
| Kapcsolódó munkarendelés              | Hozzon létre új munkarendelést a kiválasztott munkarendeléshez kapcsolódó feladathoz. Ez akkor lehet hasznos, ha elsődleges és másodlagos munkarendeléseket szeretne rögzíteni.                                                                                                                              |
| Munkarendelés másolása                 | Új munkarendelés létrehozása egy meglévő munkarendelés alapján.                                                                                                                                                                                                                |
| Eseményelőzmény                   | A munkarendelésen szereplő regisztrációs előzmények megtekintése.                                                                                                                                                                                                                |
| Munkarendelésen kiadott karbantartási feladatra vonatkozó megjegyzések                           | A munkarendelések leírásának létrehozása, illetve jegyezetek vagy megjegyzések beszúrása. A felhasználónév és időbélyegző hozzáadásához a megjegyzésbe kattintson az **Időbélyegző hozzáadása** gombra. A megjegyzések a **Munkarendelés** képernyőjén > **Sor részletei** gyorslap > **Leírás** lapján jelennek meg. |
| Eszközök                           | A szükséges eszközök listájának létrehozása egy munkarendelésen. Az eszközök erőforrásként vannak beállítva a **Szervezet felügyelete** > **Közös** > **Erőforrások** > **Erőforrások**helyen.                                                                                                      |
| Karbantartási ellenőrző lista           | A munkarendeléshez kapcsolódó eszköz ellenőrzőlistájának megtekintése.                                                                                                                                                                                                              |
| Eszközhiba                     | A hibakezeléshez eszközre vonatkozó hibaadatok megtekintése vagy rögzítése.                                                                                                                                                                                        |
| Karbantartás miatti üzemkimaradás            | A munkarendeléshez tartozó karbantartás miatti üzemkimaradás megadása.                                                                                                                                                                                                                               |
| Állapotfelmérés            | Az munkarendelésen állapotfelmérési méréseket regisztrálhat.                                                                                                                                                                                                             |
| Eszközszámlálók                 | Az eszközön számlálóregisztrációinak létrehozása vagy megtekintése.                                                                                                                                                                                                                     |
| Előrejelzés                        | A munkarendelésen előrejelzéseinek megtekintése vagy létrehozása.                                                                                                                                                                                                                               |
| Naplók                        | Munkarendelési naplók megtekintése vagy létrehozása. A naplósorok az előrejelzésekből másolhatók.                                                                                                                                                                                         |
| Projekttranzakciók            | Az eszközhöz létrehozott munkarendelésekhez kapcsolódó összes feladott tranzakció megtekintése.                                                                                                                                                                                             |
| Munkarendelés állapotának frissítése                | Munkarendelés életciklus-állapotának frissítése.                                                                                                                                                                                                                                                |
| Életciklus-állapot naplója                       | A kiválasztott munkarendelés életciklus-állapotait megjelenítő napló.                                                                                                                                                                                                                   |
| Eszközdokumentumok                | A munkarendeléshez kapcsolódó eszközökhöz csatolt dokumentumai listájának megtekintése. Ezek a dokumentumok az **Eszközkezelés** > **Beállítás** > **Eszközdokumentumok** pontban vannak beállítva.                                                                                                 |
| Ütemezés                        | A kijelölt munkarendelések ütemezése.                                                                                                                                                                                                                                      |
| Elküldés            | A kiválasztott munkarendelésének ütemezése egy dolgozóhoz.                                                                                                                                                                                                                        |
| Ütemezés törlése                 | Az ütemezése törlése egy kiválasztott munkarendeléshez.                                                                                                                                                                                                                          |
| Ütemezett munkarendelésen kiadott karbantartási feladatok             | Nyissa meg az **Ütemezett munkarendelés-karbantartási feladatok** listaoldalt.                                                                                                                                                                                                                             |
| Munkarendelés beszerzési igénylése | Nyissa meg a **Munkarendelés beszerzési igénylése** listaoldalt.                                                                                                                                                                                                                 |
| Munkarendelés beszerzése             | Nyissa meg a **Munkarendelés beszerzése** listaoldalt.                                                                                                                                                                                                                             |
| Költségkontroll                    | A munkarendelés költségvetési költségeinek és tényleges költségeinek összevetése.                                                                                                                                                                                                                |
| Órakontroll                    | Az munkarendelés előrejelzett óráinak és tényleges óráinak összehasonlítása.                                                                                                                                                                                                                |
| Munkarendelés jelentése               | Munkarendelés jelentésének nyomtatása.                                                                                                                                                                                                                                                |
| Munkarendelés felhasználása          | Felhasználási jelentés nyomtatása.                                                                                                                                                                                                                                               |


A **Munkarendelés** lap > **Projekt** csoport a **Projektmenedzsment és könyvelés** modul funkcióihoz kapcsolódik az előrejelzések, naplók és számlázás tekintetében.

>[!NOTE]
>A munkarendelésen létrehozott előrejelzéseket az alapütemezés futtatásakor lehet szerepeltetni az **Eszközkezelés paraméterei** képernyőn kiválasztott előrejelzési modell segítségével.

