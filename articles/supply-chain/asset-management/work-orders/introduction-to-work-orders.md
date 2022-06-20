---
title: Bevezetés a munkarendelések használatába
description: Ez a cikk áttekintést nyújt az Eszközkezelésben található munkarendelésekről.
author: johanhoffmann
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetWorkOrderLineNote, EntAssetWorkOrderTable, EntAssetWorkOrderActive, EntAssetWorkOrderHoursInfoPart, EntAssetWorkOrderLineListPage, EntAssetWorkOrderAddObjectBOMItem, EntAssetWorkOrderTablePoolAdd, EntAssetWorkOrderPurchReqListPagePreviewPane, EntAssetWorkOrderPoolReferenceAdd, EntAssetWorkOrderWorkspace, EntAssetWorkOrderTableAdjust, EntAssetWorkOrderGantt, EntAssetWorkOrderNotes, EntAssetWorkOrderActivePart, EntAssetWorkOrderTableInfoPart, EntAssetWorkOrderLineListPagePreviewPane, EntAssetWorkOrderTool, EntAssetMobileWorkOrderLineDetails, EntAssetMobileWorkOrderLineList, EntAssetMobileWorkOrderDetails
audience: Application User
ms.reviewer: kamaybac
ms.custom: intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: dcee5fd729de6e96d57462879f7851756f287dc9
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8902831"
---
# <a name="introduction-to-work-orders"></a>Bevezetés a munkarendelések használatába

[!include [banner](../../includes/banner.md)]



A munkarendelések a karbantartási feladatokkal kezelésére a szükséges információk biztosítására és a fogyasztás regisztrálására használatosak Minden egyes munkarendelés egy vagy több munkarendelés-feladatot tartalmaz, és egy vagy több eszköz az egyes munkarendelésekhez kapcsolható. Minden munkarendelési feladat egy ütemezett karbantartási feladatot határoz meg az eszközön.

A munkarendeléseket a következő módokon lehet létrehozni:

- A [Karbantartási tervek ütemezése](../preventive-and-reactive-maintenance/schedule-maintenance-plans.md) képernyő használatával automatikusan, a naptár alapú karbantartási tervekhez beállíthatja az „Automatikus létrehozás” lehetőséget.

- A [Karbantartási körök ütemezése](../preventive-and-reactive-maintenance/maintenance-rounds.md) képernyő használatával automatikusan, a naptár alapú karbantartási körökhöz beállíthatja az „Automatikus létrehozás” lehetőséget.

- A létrehozáshoz a [Karbantartási ütemezésből](../preventive-and-reactive-maintenance/maintenance-schedule.md), amely lehet megelőző karbantartási feladat vagy karbantartási kérelem.

- Manuálisan

- Az **Összes karbantartási kérés**, az **Aktív karbantartási kérések** vagy a **Saját munkavégzési helyszínhez tartozó karbantartási kérések** oldalról.

>[!NOTE]
>Az ugyanahhoz az eszközhöz kapcsolódó munkarendelés-feladatok ugyanahhoz a projektazonosítóhoz kapcsolódnak.

## <a name="all-work-orders"></a>Összes munkarendelés

Válassza az **Eszközkezelés** > **Közös** > **Munkarendelések** > **Összes munkarendelés** lehetőséget az **Új munkarendelések** listaoldal megnyitásához. Ezen az oldalon a munkarendelések, és bizonyos rájuk vonatkozó információk láthatók.

Az alábbi ábra az **Összes munkarendelés** listaoldal egy példáját mutatja be.

![1. ábra](media/01-work-orders.png)

Kattintson az **Eszközkezelés** > **Közös** > **Munkarendelések** > **Aktív munkarendelések** lehetőségre a csak az aktív munkarendelések listájának megtekintéséhez. 

Kattintson az **Eszközkezelés** > **Közös** > **Munkarendelések** > **Saját munkavégzési helyszín munkarendelés karbantartási feladatai** lehetőségre a munkavégzési helyszínekre telepített eszközöket tartalmazó Munkarendelés-feladatok listájának megtekintéséhez, amelyekhez ön dolgozóként kapcsolódik (a Karbantartási dolgozók és dolgozócsoportok helyen beállítva). (A dolgozók és a funkcionális helyszínek közötti kapcsolatot a **Dolgozók** lapon lehet beállítani. További információ: [Karbantartási dolgozók és dolgozói csoportok](../setup-for-objects/workers-and-worker-groups.md).)

Az **Összes munkarendelés** lap a következő módokon használható:

- Az rácsnézetben válasszon egy hivatkozást a **Munkarendelés** oszlopból a kiválasztott rekord részleteinek megtekintéséhez. Ezt követően a **Szerkesztés** parancsot választva megnyithatja a rekordot szerkesztésre.

- A részletek nézetben a munkarendeléshez kapcsolódó részletes információkat tekintheti meg.  

- A részletek nézetben válassza ki a **Sorok** lap hivatkozását a munkarendelés részleteinek megtekintéséhez, vagy válassza a **Fejléc** hivatkozást a munkarendelés részleteinek megtekintéséhez.  

- A lap jobb oldalán található **Kapcsolódó információ** ablaktábla kibontásával megjelenítheti a kiválasztott munkarendeléssel kapcsolatos további információkat.

Az alábbi ábra az **Összes munkarendelés** részletek nézet egy példáját mutatja be.

![2. ábra](media/02-work-orders.png)


A műveleti ablak gombjai lapokon vannak rendezve. A következő táblázat röviden leírja azokat a gombokat, amelyek az Eszközkezeléshez kötődnek:



| Gomb neve                     | Leírás                                                                                                                                                                                                                                                             |
|---------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Szerkesztés                            | A kijelölt munkarendelés szerkesztése                                                                                                                                                                                                                                           |
| Új                             | Új munkarendelés létrehozása.                                                                                                                                                                                                                                                  |
| Delete                          | A kijelölt munkarendelés törlése                                                                                                                                                                                                                                         |
| Munkarendelés-gyűjtő                 | A kiválasztott munkarendelés hozzáadása egy munkarendelésgyűjtőhöz vagy a annak eltávolítása a munkarendelés gyűjtőből.                                                                                                                                                                                           |
| Beállítás                          | A kiválasztott munkarendeléseken a várt kezdési és befejezés, szolgáltatási szint, felelős karbantartó dolgozó vagy felelős karbantartó dolgozói csoport adatainak módosítása.                                                                                                                                     |
| Kapcsolódó munkarendelés              | Hozzon létre új munkarendelést a kiválasztott munkarendeléshez kapcsolódó feladathoz. Ez akkor lehet hasznos, ha elsődleges és másodlagos munkarendeléseket szeretne rögzíteni.                                                                                                                              |
| Munkarendelés másolása                 | Új munkarendelés létrehozása, amely egy meglévő munkarendelésen alapul.                                                                                                                                                                                                               |
| Eseményelőzmény                   | A munka rendelés regisztrációs előzményeinek megtekintése.                                                                                                                                                                                                                |
| Munkarendelésen kiadott karbantartási feladatra vonatkozó megjegyzések                           | Leírás létrehozása egy munkarendelésen, illetve jegyezetek vagy megjegyzések beszúrása azzal kapcsolatosan. A felhasználónév és időbélyegző hozzáadásához a megjegyzésbe először kattintson az **Időbélyegző hozzáadása** gombra. A megjegyzések a **Leírás** lapon, a **Sor részletei** gyorslapon a **Munkarendelés** oldalon láthatók.         |
| Eszközök                           | A szükséges eszközök listájának létrehozása egy munkarendelésen. Az eszközök erőforrásként vannak beállítva a **Szervezet felügyelete** > **Erőforrások** > **Erőforrások** helyen.                                                                                                      |
| Karbantartási ellenőrző lista           | A munkarendeléshez kapcsolódó eszköz ellenőrzőlistájának megtekintése.                                                                                                                                                                                                              |
| Eszközhiba                     | Meghibásodási adatok megtekintése vagy rögzítése az eszközön. Ezek az adatok a hibakezelésben használhatók.                                                                                                                                                                                      |
| Karbantartás miatti üzemkimaradás            | A munkarendeléshez tartozó karbantartás miatti üzemkimaradás megadása.                                                                                                                                                                                                                               |
| Állapotfelmérés            | Az munkarendelésen állapotfelmérési méréseket regisztrálhat.                                                                                                                                                                                                             |
| Eszközszámlálók                 | Az eszközön számlálóregisztrációinak létrehozása vagy megtekintése.                                                                                                                                                                                                                     |
| Előrejelzés                        | A munkarendelésen előrejelzéseinek megtekintése vagy létrehozása.                                                                                                                                                                                                                               |
| Naplók                        | Munkarendelési naplók megtekintése vagy létrehozása. A naplósorok az előrejelzésekből másolhatók.                                                                                                                                                                                         |
| Projekttranzakciók            | Az eszközhöz létrehozott munkarendelésekhez kapcsolódó összes feladott tranzakció megtekintése.                                                                                                                                                                                             |
| Munkarendelés állapotának frissítése           | A munkarendelés életciklus-állapotának frissítése.                                                                                                                                                                                                                                                |
| Életciklus-állapot naplója                      | Megtekinthet egy naplót, amely a kiválasztott munkarendelés életciklus-állapotait mutatja.                                                                                                                                                                                                                   |
| Eszközdokumentumok                | A munkarendeléshez kapcsolódó eszközökhöz csatolt dokumentumai listájának megtekintése. Ezek a dokumentumok az **Eszközkezelés** > **Beállítás** > **Eszközdokumentumok** pontban vannak beállítva.                                                                                                 |
| Ütemezés                        | A kijelölt munkarendelések ütemezése.                                                                                                                                                                                                                                      |
| Elküldés            | A kiválasztott munkarendelésének ütemezése egy dolgozóhoz.                                                                                                                                                                                                                        |
| Ütemezés törlése                 | Az ütemezése törlése egy kiválasztott munkarendeléshez.                                                                                                                                                                                                                          |
| Ütemezett munkarendelésen kiadott karbantartási feladatok             | Nyissa meg az **Ütemezett munkarendelés-karbantartási feladatok** listaoldalt.                                                                                                                                                                                                                             |
| Munkarendelés beszerzési igénylése | Nyissa meg a **Munkarendelés beszerzési igénylése** listaoldalt.                                                                                                                                                                                                                 |
| Munkarendelés beszerzése             | Nyissa meg a **Munkarendelés beszerzése** listaoldalt.                                                                                                                                                                                                                             |
| Költségkontroll                    | A munkarendelés költségvetési költségeinek és tényleges költségeinek összevetése.                                                                                                                                                                                                                |
| Órakontroll                    | Az munkarendelés előrejelzett óráinak és tényleges óráinak összehasonlítása.                                                                                                                                                                                                                |
| Munkarendelés jelentése               | Egy munkarendelés-jelentés nyomtatása.                                                                                                                                                                                                                                                |
| Munkarendelés felhasználása          | Egy felhasználási jelentés nyomtatása.                                                                                                                                                                                                                                               |


A Műveleti panel **Projekt** csoport **Munkarendelés** lapján a **Projektmenedzsment és könyvelés** modul funkcióihoz kapcsolódik az előrejelzések, naplók és számlázás tekintetében.

>[!NOTE]
>Az alapütemezés futtatásakor a munkarendelésen létrehozott előrejelzéseket az **Eszközkezelés paraméterei** képernyőn kiválasztott előrejelzési modell segítségével lehet befoglalni.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]