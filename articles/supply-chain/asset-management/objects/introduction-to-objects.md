---
title: Bevezetés az eszközökbe
description: Ez a témakör áttekintést ad az Eszközkezelésben használt eszközökről.
author: johanhoffmann
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetTimeline, EntAssetObjectTableLookup, EntAssetObjectTableParent, EntAssetObjectOverview, EntAssetObjectImage, EntAssetObjectTable, EntAssetLifecycleStateLog, EntAssetObjectWorkOrderActive, EntAssetObjectAttribute
audience: Application User
ms.reviewer: kamaybac
ms.custom:
- "2214"
- intro-internal
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 43a5646bc4a1301922781d8b083dfa709befe3dca0fad1074b5433c6e02f5c66
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6767508"
---
# <a name="introduction-to-assets"></a>Bevezetés az eszközökbe

[!include [banner](../../includes/banner.md)]

 

Ez a témakör áttekintést ad az Eszközkezelésben használt eszközökről. Az *Eszköz* bármilyen típusú berendezés, például gép vagy gépalkatrész, amely karbantartást, szervizt vagy javítást igényel.

Egy eszköz automatikusan frissül a kapcsolódó információkkal. Ilyen információ lehet például az új vagy frissített munkakrendelésekkel kapcsolatban. Az eszközök az **Összes eszköz** menüpont vagy a **Függőben lévő eszközök** menüpont segítségével hozhatók létre. Ez a témakör bemutatja, hogyan lehet eszközöket létrehozni az **Összes eszköz** menüpont használatával. A **Függőben lévő eszközök** menüelem segítésével való eszközlétrehozás módjával kapcsolatos további információkért lásd: [Eszközök létrehozása munkarendelések alapján](../objects/create-objects-based-on-purchase-orders.md).

## <a name="all-assets"></a>Minden eszköz

Válassza ki az **Eszközkezelés** \> **Általános** \> **Eszközök** \> **Összes eszköz** lehetőséget. Az **Összes eszköz** listaoldalon az összes eszköz és a hozzájuk kapcsolódó információk egy része látható. Ha csak az aktív eszközöket szeretné megtekinteni , válasszaaz **Aktív eszközök** pontot. Ha csak azokat az eszközöket szeretné megtekinteni, amelyeket olyan munkavégzési helyszíneken telepítettek, amelyhez karbantartási dolgozóként Ön kapcsolódik, válassza a **Saját aktív eszközök** lehetőséget. (Ez a kapcsolat a **Dolgozók** oldalon állítható be. További információ: [Karbantartási dolgozók és dolgozói csoportok](../setup-for-objects/workers-and-worker-groups.md).)

Az **Összes eszköz** rácsnézetben válasszon egy hivatkozást az **Eszköz** oszlopból a kiválasztott rekord részleteinek megtekintéséhez. A rekord szerkesztéséhez válassza a **Szerkesztés** képernyőgombot. A Részletek nézetben az eszközhöz kapcsolódó részletes információk láthatók. A jobb oldalon található **Kapcsolódó információk** ablaktáblán további, eszközzel kapcsolatos információk szerepelnek. Bontsa ki az ablaktáblát a kijelölt eszköz kapcsolódó információinak megjelenítéséhez.

A műveleti ablak gombjai lapokon vannak rendezve. A következő táblázat röviden leírja azokat a gombokat, amelyek az Eszközkezeléshez kötődnek.

| Gomb neve          | Leírás                                                                                                                                                       |
|----------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Szerkesztés                 | Szerkessze a kijelölt eszközt.                                                                                                                                         |
| Új                  | Hozzon létre egy új eszközt.                                                                                                                                                |
| Eltávolítás               | Törölje a kijelölt eszközt.                                                                                                                                       |
| Eszköz áthelyezése           | Egy másik eszközszerkezetbe vagy ugyanazon eszközstruktúra más helyére helyezheti át az eszközt.                                                                                         |
| Eszköz cseréje        | Egyetlen alárendelt eszközt lecserélhet az eszközhierarchiában egy másik eszközzel.                                                                                                  |
| Eszköz telepítése        | Telepítsen egy eszközt egy munkavégzési helyszínre.                                                                                                                          |
| Eszköz másolása           | Eszközhierarchia másolása másik eszközre.                                                                                                                          |
| Kérelmek             | Nyissa meg az **Aktív kérések** listaoldalt, ahol megtekintheti a kiválasztott eszközhöz létrehozott karbantartási kéréseket.                                                                         |
| Eseményelőzmények        | Az eszközön végrehajtott különböző regisztrációk áttekintését tekintheti meg.                                                                                                         |
| Eszköz DBJ            | Az eszközön használt összes cikk (pótalkatrész és más cikkek) listája.                                                                                  |
| Munkarendelések          | Nyissa meg az **Aktív munkrendelések** listaoldalát, ahol megtekintheti az eszköz munkarendeléseit.                                                                                        |
| Ellenőrzőlista            | Az eszközre regisztrált karbantartási ellenőrzőlisták és mértékek áttekintésének megtekintése.                                                                                                 |
| Karbantartás miatti üzemkimaradás | Az eszközön regisztrált karbantartás miatti üzemkimaradások létrehozása vagy megtekintése.                                                                                                       |
| Projekttranzakciók | Az eszközhöz létrehozott, munkarendelésekkel kapcsolatos összes feladott tranzakció megtekintése.                                                                                       |
| Eszköz mértékei       | Eszközmérések létrehozása vagy megtekintése az eszközre.                                                                                                               |
| Karbantartási ütemezés | Nyissa meg a **Nyitott karbantartási ütemezés** listaoldalt, ahol megtekintheti a karbantartási terveket, karbantartási kéréseket és karbantartási köröket, amelyeket az adott eszközhöz társítottak, és **Létrehozott** állapottal rendelkeznek. |
| Eszköz állapotának frissítése   | Az eszköz életciklus-állapotának frissítése. Több eszközt is kiválaszthat az **Összes eszköz** listaoldalon, majd egyszerre frissítheti az eszköz-életciklusállapotot mindegyikükhöz.              |
| Életciklus-állapot naplója  | Nyisson meg egy naplót, amely a kiválasztott eszköz életciklus-állapotait mutatja.                                                                                                                 |
| Eszközdokumentumok      | Az eszközhöz csatolt dokumentumok listájának megtekintése. Ezek a dokumentumok az **Eszközkezelés** \> **Beállítás** \> **Eszközdokumentumok** pontban vannak beállítva.                 |
| Attribútumok           | Létrehozhat vagy megtekinthet eszközattribútumokat.                                                                                                                             |
| Kép                | Kép kijelölése az eszközhöz.                                                                                                                                   |
| Fölérendelt eszközök        | A kijelölt eszköz fölérendelteszköz-előzményeinek megtekintése.                                                                                                                |
| Munkavégzési helyszínek | A kijelölt eszköz munkavégzésihelyszín-előzményeinek megtekintése.                                                                                                          |
| Állapotfelmérés | Az eszközön állapotfelmérési méréseket regisztrálhat.                                                                                                         |
| Hibák               | Nyissa meg az **Eszközhibák** listaoldalt, ahol megtekintheti az eszközre regisztrált hibákat.                                                                                             |
| Költségkontroll         | Az eszköz költségvetési költségeinek és tényleges költségeinek összevetése.                                                                                                              |
| Órakontroll         | Az eszköz előrejelzésett óráinak és tényleges óráinak összehasonlítása.                                                                                                              |
| Eszköz KPI-k           | Az eszköz fő teljesítménymutatóinak (KPI-k) számítása és megtekintése.                                                                                              |
| Feladattípusok            | Az eszköz aktuális alapértelmezett feladattípusai áttekintésének megtekintése.                                                                                                            |
| Kritikussági típusok    | Megtekintheti vagy frissítheti az eszköz kritikussági típusait.                                                                                                                              |
| Pótalkatrészek          | Az eszközhöz használható jóváhagyott és alternatív pótalkatrészeket tartalmazó lista megtekintése.                                                                               |
| Eszközfelhasználás    | Az eszközfelhasználási regisztrációkat tartalmazó jelentést kinyomtathatja.                                                                                                |
| Eszközhiba          | Az eszköz hibaregisztrációit tartalmazó jelentést kinyomtathatja.                                                                                                      |


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]