---
title: "Projekt tényleges adatainak szinkronizálása a Project Service Automation alkalmazásból közvetlenül a projektintegrációs naplóba a feladáshoz a Finance and Operations alkalmazásba"
description: "Ez a témakör azokat a sablonokat és kapcsolódó feladatokat mutatja be, melyek a projekt tényleges adatainak a Microsoft Dynamics 365 for Finance and Operations és a Microsoft Dynamics 365 for Project Service Automation közötti szinkronizálásra."
author: KimANelson
manager: AnnBe
ms.date: 05/21/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 87983
ms.assetid: b454ad57-2fd6-46c9-a77e-646de4153067
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-11-28
ms.dyn365.ops.version: AX 7.3.0
ms.translationtype: HT
ms.sourcegitcommit: bd8feff598cf80ca675c7d2b5dda636799b19e29
ms.openlocfilehash: 85ff049852e0b00623f47a12fb66e2c9bb9c4151
ms.contentlocale: hu-hu
ms.lasthandoff: 05/29/2018

---
# <a name="synchronize-project-actuals-from-project-service-automation-directly-to-the-project-integration-journal-for-posting-in-finance-and-operations"></a>Projekt tényleges adatainak szinkronizálása a Project Service Automation alkalmazásból közvetlenül a projektintegrációs naplóba a feladáshoz a Finance and Operations alkalmazásba

Ez a témakör azokat a sablonokat és kapcsolódó feladatokat mutatja be, melyek a projekt tényleges adatainak a Microsoft Dynamics 365 for Finance and Operations és a Microsoft Dynamics 365 for Project Service Automation közötti szinkronizálásra.

A sablon szinkronizálja a tranzakciókat a Project Service Automation alkalmazásból a Finance and Operations egy előkészítési táblájába. Szinkronizálás befejezése után, importálnia kell az előkészítő táblából a integrációs naplóba.

> [!NOTE]
> Projekt-tényleges adatainak integrációja a Dynamics 365 for Finance and Operations 8.01-es verziójában érhető el.

> [!NOTE]
> Ha időhöz kapcsolódó áfát vagy kiadási tranzakciókat visz be visz be a Project Service Automationbe , telepítenie kell a Project Service Automation Update 7 frissítést. Ha ez a frissítés nincs telepítve, a tényleges adó nem lesz csatolva a kapcsolódó tényleges időhöz vagy a költséghez, és nem lesz szinkronizálva a Finance and Operations alkalmazásba. További információért forduljon a támogatáshoz.


## <a name="data-flow-for-project-service-automation-to-finance-and-operations"></a>Adatáramlás a Project Service Automation és a Finance and Operations között

A Project Service Automation és Finance and Operations közötti integrációs megoldása az adatintegrációs funkciót használja a Project Service Automation and Finance és Operations példányok közötti szinkronizáláshoz. Az integrációs sablonok, amelyek elérhetőek az adatintegrációs funkcióval lehetővé teszik a projekt tényleges adatainak áramlását a Project Service Automation alkalmazásból a Finance and Operations alkalmazásba.

A következő ábra bemutatja a Project Service Automation és a Finance and Operations közötti adatszinkronizálást.

[![Adatáramlás a Project Service Automation és a Finance and Operations integrációjához](./media/ProjectActualsFlow.jpg)](./media/ProjectActualsFlow.jpg)


## <a name="templates-and-tasks"></a>Sablonok és feladatok

A rendelkezésre álló sablonok eléréséhez a Microsoft PowerApps Admin Centerben válassza a **Projektek** lehetőséget, majd ezután kattintson a jobb felső sarkában **Új projekt** lehetőségre a nyilvános sablonok kiválasztásához.

A következő sablon és alapul szolgáló feladatok használhatók az aktuális projektadatok szinkronizálásához a Project Service Automation és Finance and Operations között:

-  **Sablon neve az adatintegrációban:** Projekt tényleges adatai (PSA to Fin and Ops)

-  **A projekt tevékenységeinek nevei:** 
    - Tényadatok 
    - TransactionConnections

## <a name="entity-set"></a>Entitás beállítása

| Projekt szolgáltatásautomatizálása      | Finance and Operations                                      |
|---------------------------------|-------------------------------------------------------------|
| Tényadatok                         | Integrációs entitás a projekt tényleges adataihoz                      |
| Tranzakciók kapcsolatai         | Projekttranzakció-kapcsolatok integrációs entitása    |

## <a name="entity-flow"></a>Entitás folyamata

Projekt tényleges adatainak kezelése a Project Service Automation alkalmazásban történik, majd ezek szinkronizálva lesznek a Finance and Operations alkalmazásba a projektintegrációs naplóba. A könyvelési az alapértelmezett pénzügyi dimenziók és a feladási beállítások alapján lesz alkalmazva.

## <a name="preconditions"></a>Előfeltételek

Tényleges adatok szinkronizálása előtt, a Project Service Automation integrációs paramétereit be kell állítani, és szinkronizálni kell a projekteket, projektfeladatokat és projektköltség-tranzakció kategóriákat.

## <a name="power-query"></a>Power Query

A Microsoft Power Query-t a következőkre kell használnia a projekt aktuális adatainak sablonjában:
- A Project Service Automation **tranzakciótípus** átalakítására a megfelelő **tranzakciótípusra** a Finance and Operations alkalmazásban. A Projekt tényleges adatai (Fin és Ops PSA) sablon már definiálta ezt az átalakítást.
- A Project Service Automation **számlázási típus** átalakítására a megfelelő **számlázási típusra** a Finance and Operations alkalmazásban. A Projekt tényleges adatai (Fin és Ops PSA) sablon már definiálta ezt az átalakítást. A számlázási típus ezután hozzá lesz rendelve a **sortulajdonság** elemhez a Dynamics 365 for Project Service Automation integrációs paraméterek képernyő beállításai alapján.
- Szűrés specifikus **Erőforrás szervezeti egységekre**, amelyek e sablonnal szinkronizálhatók.
- Ha **a vállalatközi idő vagy tényleges költségek** szinkronizálva lesznek a Finance and Operations alkalmazásba, át kell alakítani a **szerződéses szervezeti egység** a megfelelő **jogi személy** elemre a Finance and Operations alkalmazásban. A Projekt tényleges adatai (Fin and Ops PSA) sablonjának van egy feltételes oszlopa a bemutató adatok alapján. Az utolsó beszúrt feltétel oszlopot frissítenie kell a megfelelő jogi személyekhez. Ellenkező esetben ez integrációs hibát vagy a helytelen tényleges tranzakciók importálását eredményezheti a Finance and Operations alkalmazásba.
- Ha **idő vagy a tényleges vállalatközi költségek** nem lesznek szinkronizálva a Finance and operations alkalmazásba, ki törölnie kell az utolsó beszúrt feltétel oszlopot a sablonból. Ellenkező esetben ez integrációs hibát vagy a helytelen tényleges tranzakciók importálását eredményezheti a Finance and Operations alkalmazásba.

### <a name="contract-organizational-unit"></a>Szerződéses szervezeti egység
A beszúrt feltételoszlop frissítéséhez sablonban kattintson a **Hozzárendelés** nyílra a hozzárendelés megnyitásához. Válassza ki a Speciális lekérdezés és szűrés megnyitásához.
- Ha az alapértelmezett Microsoft Projekt tényleges adatok (Fin és Ops PSA) sablont használ, jelölje be a **Beszúrt feltétel** elemet az **Alkalmazott lépések** szakaszban. Az **Funkció** bejegyzésben, cseréje az **USSI** elemet a **Jogi személy** nevére, melyet használni kell, hogy az integrációhoz. Szükség szerint adjon hozzá a további feltételeket a **Funkció** bejegyzéshez, és frissítése a **más** feltételt **USMF** helyett a megfelelő **Jogi személyre**.
- Új sablon létrehozásakor, hozzá kell adnia ezt az oszlopot a vállalatközi idő- és a költségek támogatásához. Válassza a **Feltételes oszlop hozzáadása** elemet, és adjon egy nevet az oszlopnak, például LegalEntity. Adja meg a feltételt az oszlop ha msdyn_contractorganizationalunitid.msdyn_name <organizational unit>, akkor <enter the Legal entity>; máskülönben nulla.

## <a name="template-mapping-in-data-integration"></a>Sablonleképezés az adatintegrátorban

Az alábbi ábrán egy példát mutat a sablonfeladat hozzárendelésére az Adatintegrációban A leképezés mutatja, hogy melyik mezőadatok szinkronizálódnak a Project Service Automation – Finance and Operations irányban.

[![Sablon-hozzárendelés](./media/ActualsMapping.jpg)](./media/ActualsMapping.jpg)

[![Sablon-hozzárendelés](./media/TransactionConnections.jpg)](./media/TransactionConnections.jpg)

## <a name="import-from-staging-table"></a>Importálás az előkészítési táblából

Az importálás előkészítési tábla periodikus folyamatját futtatni a tényleges adatok szinkronizálását követően a Project Service Automation és a Finance and Operations között. Ez a folyamat importálja a projekttranzakciókat az előkészítési táblából a Project Service Automation integrációs naplóba, ahol a könyvelés alkalmazva lesz, és fel lehet adni az importált tranzakciókat. Azt ajánljuk, hogy ez a folyamatot kötegelt módban futtassa, és tetszés szerint beállíthatja, hogy ismétlődő kötegként futtatandó.

## <a name="update-actuals"></a>Tényleges értékek frissítése

A következő sablon és alapul szolgáló feladatok használhatók a projekttranzakciókhoz feladott bizonylatszámok és áfa szinkronizálásához a Finance and Operations és a Project Service Automation között:

-  **Sablon neve az adatintegrációban:** Projekt tényleges adatainak frissítése (Fin Ops to PSA)
-  **A projekt tevékenységeinek nevei:** 
     - Tényadatok 
     - TransactionConnections

## <a name="entity-set"></a>Entitás beállítása

| Finance and Operations                                         | Projekt szolgáltatásautomatizálása        |
|----------------------------------------------------------------|-----------------------------------|
| Integrációs entitás a projekt tényleges adataihoz                         | Tényadatok                           |
| Projekttranzakció-kapcsolatok integrációs entitása       | Tranzakciók kapcsolatai           |

## <a name="entity-flow"></a>Entitás folyamata

Projekt tényleges adatainak kezelése a Project Service Automation alkalmazásban történik, majd ezek szinkronizálva lesznek a Finance and Operations alkalmazásba a projektintegrációs naplóba. Miután fel lett adva a Finance and Operations alkalmazásba a tényleges értékek frissülnek a Project Service Automation alkalmazásban a Finance and Operations bizonylatszámaival. Ha adók is hozzá lettek adva a Finance and Operations alkalmazásban, új tényleges adóértékek lesznek számítva a Project Service Automation alkalmazásban.

## <a name="power-query"></a>Power Query

A Microsoft Power Query-t a következőkre kell használnia a projekt aktuális adatainak frissítősablonjában:
- A Finance and Operations **tranzakciótípus** átalakítására a megfelelő **tranzakciótípusra** a Project Service Automation alkalmazásban. A Projekt tényleges adatainak frissítése (Fin Ops to PSA) sablon már definiálta ezt az átalakítást.
- A Finance and Operations **számlázási típus** átalakítására a megfelelő **számlázási típusra** a Project Service Automation alkalmazásban. A Projekt tényleges adatainak frissítése (Fin Ops to PSA) sablon már definiálta ezt az átalakítást.

## <a name="template-mapping-in-data-integration"></a>Sablonleképezés az adatintegrátorban

Az alábbi ábrán példákat láthat sablonfeladatok hozzárendelésére az Adatintegrációban A leképezés mutatja, hogy melyik mezőadatok szinkronizálódnak a Finance and Operations – Project Service Automation irányban.

[![Sablon-hozzárendelés](./media/ActualsUpdateMapping.jpg)](./media/ActualsUpdateMapping.jpg)

[![Sablon-hozzárendelés](./media/TransactionConnectionsUpdate.jpg)](./media/TransactionConnectionsUpdate.jpg)




