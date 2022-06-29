---
title: Karbantartás miatti üzemkimaradási tevékenységek
description: Ez a témakör bemutatja, hogy a karbantartási leállások hogyan használhatók fel annak a kapacitásnak az áttekintésére, amely egy adott eszköz karbantartási feladatának egy adott időszakban való elvégzéséhez szükséges.
author: johanhoffmann
ms.date: 08/27/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetMaintenanceStopCopy, EntAssetMaintenanceStopObject, EntAssetObjectProductionStop, EntAssetProductionStopType, EntAssetMaintenanceStop
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 42e8ba4e19333cb25464203a2583175ef082ad98
ms.sourcegitcommit: cfe8fbc202c3eb05d894076fdf99e46704f17365
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/15/2022
ms.locfileid: "9016478"
---
# <a name="maintenance-downtime-activities"></a>Karbantartás miatti üzemkimaradási tevékenységek

[!include [banner](../../includes/banner.md)]

A karbantartás miatti üzemkimaradás révén áttekintést kaphat az adott eszközökre vonatkozó, adott időszak során esedékes karbantartási feladatok végrehajtásához szükséges kapacitásról. Létrehozhat például a karbantartás miatti üzemkimaradás regisztrálására szolgáló megoldást a 29-A termelési csarnok 02 termelési helyének 10-es gyártósorához. A karbantartás miatti üzemkimaradás regisztrálásának kezdő és záró időpontja jelzi azt az időszakot, amikor a karbantartáshoz kapcsolódó eszközök nem állnak rendelkezésre a termeléshez.

A **Karbantartás miatti üzemkimaradási tevékenységek** egy adott időszakra vonatkozóan áttekintést nyújt a karbantartási ütemezés sorairól és a munkarendelés kapcsolódó eszközökre vonatkozó karbantartási feladatairól. A munkarendelés karbantartási feladataihoz kapcsolódó sorok várható kezdő dátuma a karbantartás leállási időszakán belül van. Hasznos adatokat szerezhet, és kiigazíthatja a tervezett karbantartási feladatokat:

- Áttekintést kaphat a termelési berendezések (eszközök) szükséges leállási időszakáról.  
- Áttekintést kaphat a tervezett karbantartásról (óra), hatáskörök szerint csoportosítva (karbantartási dolgozók felelős csoportja vagy karbantartási dolgozók); például a villanyszerelők, a kovácsok vagy más karbantartó munkacsoportok kapacitásterhelése, amely szükséges a tervezett karbantartási feladatokhoz.  
- Kiigazíthatja az eszközökkel kapcsolatos karbantartási ütemezési sorokat vagy a munkarendelés karbantartási feladatait, például módosíthatja egy sorban a várt kezdési és befejezési időpontot, vagy másik karbantartási dolgozókat választhat a munkafolyamat karbantartási dolgozókhoz és karbantartási dolgozói csoportokhoz való optimalizálásához.

Ha a karbantartás miatti üzemkimaradás regisztrációjához eszközöket választott, akkor az aktív munkarendelésekhez kapcsolódó összes nyitott karbantartási ütemezési sor és munkarendelési karbantartási feladat szerepel a karbantartás miatti üzemkimaradás regisztrációjában.

## <a name="maintenance-downtime-activities"></a>Karbantartás miatti üzemkimaradási tevékenységek

Kattintson **az Eszközkezelés** > **·** > **- karbantartás - leállási tevékenységek lehetőségre Az** összes karbantartási leállási tevékenység gombra kattintva listát nyit az összes karbantartási leállási tevékenységről, és láthatja a tevékenységekkel kapcsolatos bizonyos adatokat. A részletes nézet megnyitásához kattintson a **Karbantartás miatti üzemkimaradási tevékenységek** oszlopban lévő hivatkozásra. A lenti ábra a **Karbantartás miatti üzemkimaradási tevékenységek** listaoldalt szemlélteti.

![1. ábra](media/19-preventive-maintenance.png)


## <a name="create-a-maintenance-downtime-activity"></a>Karbantartás miatti üzemkimaradás tevékenység létrehozása

1. Kattintson az Eszközkezelés **-** > **karbantartási leállási** > **tevékenységek lehetőségre: minden karbantartási** leállási tevékenység vagy aktív **karbantartási leállási tevékenység**.

2. Kattintson az **Új** elemre.

3. Szúrjon be egy azonosítót a **Karbantartás miatti üzemkimaradási tevékenységek** mezőbe és írjon be egy nevet a **Név** mezőbe.

4. A karbantartási leállás időszakát szúrja be a **Kezdő dátum/idő** és a **Záró dátum/idő** mezőbe.

5. A **Karbantartás miatti üzemkimaradási tevékenységek eszközei** gyorslapon kattintson a **Sor hozzáadása** elemre, ha a tárgyi eszközt szeretne hozzáadni (egyesével) a karbantartás miatti üzemkimaradási tevékenységhez.

6. Ha minden eszközt felvett, kattintson a **Mentés** gombra. A lenti ábra a kapcsolódó eszközökkel és karbantartási feladatokkal kapcsolatos karbantartási állásidőt mutatja be.

7. A kiválasztott eszközökhöz kapcsolódó munkarendelési karbantartási feladatok és a nyitott karbantartási ütemezési sorok a **Munkarendelés eredményként kapott karbantartási feladatai** és a **Karbantartási ütemezés sorai** gyorslapon láthatók. Az **Általános** gyorslap > **Munkarendelések** csoport > **Karbantartás előrejelzett időpontjai** mezőben és az **Általános** gyorslap > **Karbantartási ütemezés** csoport > **Karbantartás előrejelzett időpontjai** mezőben látható a munkarendelés karbantartási feladataihoz és a karbantartási ütemezés soraihoz előrejelzett órák száma.

A lenti ábra a **Karbantartás miatti üzemkimaradási tevékenységek** részletes nézetet szemlélteti.

![2. ábra](media/20-preventive-maintenance.png)

>[!NOTE]
>A kiválasztott eszközökkel kapcsolatos munkarendelési karbantartási feladatok és karbantartási ütemezési sorok automatikusan frissülnek, ha új munkarendeléseket vagy karbantartási ütemezési sorokat hoz létre a karbantartás miatti üzemkimaradási tevékenység létrehozása után. Ha például két nappal a karbantartás miatti üzemkimaradási tevékenység létrehozása után ütemez karbantartási terveket és karbantartási köröket a kapcsolódó eszközökhöz, akkor az új karbantartási ütemezési sorok automatikusan hozzáadódnak a karbantartás miatti üzemkimaradási tevékenységhez.

8. **Minden karbantartás miatti üzemkimaradási tevékenység** > **Karbantartás miatti üzemkimaradási tevékenységek** > válasszon ki egy karbantartás miatti üzemkimaradási tevékenységet a listában, és kattintson a **Kapacitásterhelés** elemre a **Kapacitásterhelés kiszámítása** párbeszédpanel megnyitásához. Ezen a párbeszédpanelen áttekintheti a kapacitásterhelést például a dátumok, az eszközök, az eszköztípusok vagy a karbantartási feladatok típusai esetében. Ne feledje, hogy a párbeszédpanelen megjelenő dátumok a **Karbantartás miatti üzemkimaradási tevékenységek** részen kiválasztott kezdő és záró dátumok. Ez a számítás figyelembe veszi a karbantartás miatti üzemkimaradási tevékenységhez kapcsolódó eszközöket.

9. A **Kapacitásterhelés kiszámítása** párbeszédpanelen szükség esetén módosítsa a kezdő és a záró időpontot, és adja meg, hogy szeretné-e szerepeltetni a számításban a munkarendeléseket és a karbantartási ütemezéseket. A **Szint** mezőben adhatja meg, hogy a kapacitásterhelési számítás milyen részletesen jelenítse meg a munkavégzési helyszíneket. Ha például az „1” értéket adja meg a mezőben, és többszintű struktúrát használ a munkavégzési helyszínekhez, akkor a munkavégzési helyszín karbantartás miatti üzemkimaradási tevékenységénél megadott összes eszköze a legfelső szinten jelenik meg, így a sorban szereplő óraszámok hozzáadhatók az alacsonyabb szinten található munkavégzési helyszínekből. Ha a „0” értéket adja meg a **Szint** mezőben, akkor részletes eredmény jelenik meg, amely a kapacitásterhelés minden sorát megjeleníti az összes olyan munkavégzési helyszínnél, amelyhez a sor kapcsolódik.

10. Kattintson az **OK** gombra az számítás indításához. A **Kapacitásterhelés** áttekintésében a teljes óraszám jelenik meg. A **Kapacitásterhelés** lap > **Csoportosítás alapja...** Műveleti panel csoportokban kattintson a megfelelő gombra, ha részletesebb áttekintést szeretne kapni az előrejelzett órák felosztásáról. A lenti ábra a **Kapacitásterhelés** számításának eredményeit mutatja.

![3. ábra](media/21-preventive-maintenance.png)

11. Ha a kapacitásterhelés áttekintése után kiigazítást kíván végezni a munkarendelés karbantartási feladatokon vagy a karbantartási ütemezés sorain, lépjen vissza a **Karbantartás miatti üzemkimaradási tevékenységek** részletes nézethez, és válassza ki a módosítani kívánt sorokat a **Munkarendelés eredményként kapott karbantartási feladatai** és a **Karbantartási ütemezés sorai** gyorslapon.

12. Kattintson a **Beállítás** gombra, és frissítse a munkarendelés karbantartási feladatainak vagy a karbantartási ütemezési soroknak a várható kezdési/záró időpontját, a szolgáltatási szintjét vagy a felelős karbantartó dolgozókat.

13. Ha elvégezte a szükséges kiigazításokat, kattintson az **OK** gombra. 

>[!NOTE]
>A munkarendelés olyan karbantartási feladatait és az olyan karbantartási ütemezési sorokat, amelyek a kiigazítás után nem szerepelnek a karbantartás miatti üzemkimaradás időszakában, a rendszer automatikusan eltávolítja a **Karbantartás miatti üzemkimaradási tevékenységek** közül.

14. **Minden karbantartás miatti üzemkimaradási tevékenység** > **Karbantartás miatti üzemkimaradási tevékenységek** > válasszon ki egy karbantartás miatti üzemkimaradási tevékenységet a listában, és kattintson a **Cikkelőrejelzés** elemre a **Cikkelőrejelzés kiszámítása** párbeszédpanel megnyitásához. Ezen a párbeszédpanelen kiszámíthatja a cikkekhez (pótalkatrészekhez és más szükséges cikkekhez) tartozó előrejelzéseket, és úgy csoportosíthatja a cikkeket, hogy például dátum, eszköz, eszköztípus vagy a karbantartási feladatok típusa szerinti áttekintést kapjon. Ne feledje, hogy a párbeszédpanelen megjelenő dátumok a **Karbantartás miatti üzemkimaradási tevékenységek** részen kiválasztott kezdő és záró dátumok. Ez a számítás a karbantartás miatti üzemkimaradási tevékenységnél kiválasztott eszközökhöz kapcsolódó pótalkatrészeket és cikkeket tartalmaz.

15. A **Cikkelőrejelzés kiszámítása** párbeszédpanelen szükség esetén módosítsa a kezdő és a záró időpontot, és adja meg, hogy szeretné-e szerepeltetni a számításban a munkarendeléseket és a karbantartási ütemezéseket. A **Szint** mezőben adhatja meg, hogy a kapacitásterhelési számítás milyen részletesen jelenítse meg a munkavégzési helyszíneket. Ha például az „1” értéket adja meg a mezőben, és többszintű struktúrát használ a munkavégzési helyszínekhez, akkor a munkavégzési helyszín karbantartás miatti üzemkimaradási tevékenységénél megadott összes eszköze a legfelső szinten jelenik meg, így a sorban szereplő óraszámok hozzáadhatók az alacsonyabb szinten található munkavégzési helyszínekből. Ha a „0” értéket adja meg a **Szint** mezőben, akkor részletes eredmény jelenik meg, amely a kapacitásterhelés minden sorát megjeleníti az összes olyan munkavégzési helyszínnél, amelyhez a sor kapcsolódik.

16. Kattintson az **OK** gombra az számítás indításához. A cikkelőrejelzések teljes száma a **Cikkelőrejelzés** áttekintésében jelenik meg. A **Cikkelőrejelzés** lap > **Csoportosítás alapja...** Műveleti panel csoportokban kattintson a megfelelő gombra, ha részletesebb áttekintést szeretne kapni az előrejelzett cikkek felosztásáról.A lenti ábra a karbantartás **ütemezés költség** számításának eredményeit mutatja.

![4. ábra](media/22-preventive-maintenance.png)

- A karbantartás miatti üzemkimaradási tevékenységek között átmásolhatja az eszközöket. A **Minden karbantartás miatti üzemkimaradási tevékenység** részen kattintson a **Karbantartás miatti üzemkimaradási tevékenységek másolása** gombra, majd válassza ki a megfelelő értékeket a **Karbantartás miatti üzemkimaradási tevékenységből** és a **Karbantartás miatti üzemkimaradási tevékenységbe** mezőben, és kattintson az **OK** gombra.
- A **Minden karbantartás miatti üzemkimaradási tevékenység** részen kattintson a **Karbantartási ütemezés sorai** vagy az **Aktív munkarendelések** gombra a kapcsolódó listák megnyitásához, illetve a kiválasztott karbantartás miatti üzemkimaradási tevékenységhez kapcsolódó sorok megtekintéséhez.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]