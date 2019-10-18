---
title: Projekt-előrejelzések és -költségvetések
description: A Microsoft Dynamics 365 Finance a projektek intézésére és irányítására a projekt-előrejelzések és a projektköltségvetések szolgál.
author: KimANelson
manager: AnnBe
ms.date: 10/25/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ForecastModel, ProjYearEndProcess
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 23501
ms.assetid: 4e6d1384-19a2-4232-b3f3-d2590c218bd7
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 85a5577968024bf42449c50d72a11414f9207eec
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/27/2019
ms.locfileid: "2185589"
---
# <a name="project-forecasts-and-budgets"></a>Projekt-előrejelzések és -költségvetések

[!include [banner](../includes/banner.md)]

Két lehetőség van a projektek intézésére és irányítására: a projekt-előrejelzések és a projektköltségvetések. 

Használja a projekt-előrejelzést, amennyiben a szervezetnek van működési terve, és ha az a meghatározott tranzakciókból származtatott bevételekre és költségekre fókuszál. Használja a projekt költségvetés-tervezéshez, ha a szervezet inkább a pénzügyi összegekre összpontosít. 

A projekt-előrejelzések és a projekt-költségvetések egyaránt használható előrejelzési modellek ahhoz, hogy a tervezett tranzakció összegeit tartsák. 

Minden metódus előnyökkel jár. A következőket vegye figyelembe mielőtt kiválasztja a metódust a szervezet számára.

|                           |                                          |                                                    |
|---------------------------|------------------------------------------|----------------------------------------------------|
|                           | **Projekt-előrejelzés**                  | **Projekt-költségvetés**                              |
| **Időszaki felosztás**     | A pénzügyi időszakban tranzakciókat kifejezetten nem lehet végezni. Ehelyett az előrejelzés, és az előrejelzés vezérlő a projekt tartamán alapul. Mivel az előrejelzések egy adott dátumon alapulnak, az időszakot a dátum alapján kell kikövetkeztetni. | A teljes projekt vagy a pénzügyi időszak során lehet tranzakciókat végezni. Ha utalást végez rendel egy időszak alatt, a nem használt összegeket a következő pénzügyi időszakra viheti át. |
| **Tranzakciók megfigyelése**  | Az előrejelzési képernyőkön megtekinthetőek a tranzakciók, ahol látható a teljes vállalatra, és az összes projektre vonatkozó előrejelzés a hierarchiától függetlenül. Ha csak egy adott projektre összpontosít, szűrni kell az adatokat.                                       | Az egyetlen projekt hierarchiájához tartozó költségvetési tranzakciókat meg lehet tekinteni. Ezért a szülőprojektek vagy annak alprojektjének tranzakció adatait meg lehet tekinteni.                 |
| **Tranzakció változók** | Az előrejelzési tranzakciók megadása után, minden létező attribútumot felhasználhat az aktuális tranzakcióhoz. Ez lehetővé teszi a részletgazdagabb előrejelzést. Például megadhatja a létszám, a dolgozók, a cikkek vagy a sortulajdonságok adatait.         | A költségvetés részleteinek megadásakor csak az összegeket, a kategóriákat és a tevékenységeket használhatja.                    |
| **Biztonság**              | Az előrejelzés az előrejelzés képernyőn megadott tranzakciókon alapul, és magába foglalja a folyamaton kívüli vezérlő mechanizmust. Bármelyik dolgozó, aki az előrejelzés képernyőjéhez hozzáféréssel rendelkezik jóváhagyás nélkül módosíthatja az adatokat.                                        | A költségvetés munkafolyamat rendszert használ, amely lehetővé teszi a változáskezelést, és a felülvizsgálat előzményeinek megtartását.         |
| **Bejegyzéstípus**           | Az előrejelzési tranzakció bejegyzések az egységek számain, és az önköltségi- és eladási egységárakon alapulnak.  | A költségvetés részletei azokon az összegeken alapulnak, amelyek a költségek és bevételek között vannak megosztva.                                          |
| **Előrejelzési modellek**       | Mivel minden előrejelzést egy modellel kell társítani, több előrejelzési modellt is létrehozhat, és részmodelleket is megadhat.           | A projekt-költségvetés korlátozza a költségvetés-tervezéshez használt előrejelzési modelleket. A kevesebb előrejelzési modell segíthet növelni az előrejelzések összefüggéseit.                           |
| **Költségtúllépés**         | Csak engedélyezheti vagy letilthatja a tranzakciók engedélyezését, amelyek költségtúllépés okoznak.   | A projekt költségvetés további beállítások választását tartalmazza a felhasználók számára. Engedélyezheti a figyelmeztetéseket és a kerettúllépéseket.                    |
| **Vezérlő**               | Az előrejelzés vezérlő az előrejelzés csökkentés használatával történik. A tényleges összegek az előrejelzési tranzakció egyenlegéből vonhatóak ki bármilyen könyvvizsgálati ellenőrzés nélkül. Ez megnehezítheti azt, hogy nyomon kövessék, hogy hol történt a tényleges tranzakciók.                   | A projekt költségvetés-ellenőrzésben a tényleges összegek a fennmaradó költségvetési összegekből vonhatóak ki. Ez lehetővé teszi a világosabb könyvvizsgálati ellenőrzést.                                   |

## <a name="project-forecasts"></a>Projekt előrejelzései
Projekt-előrejelzések használata esetén minden tranzakciótípushoz előrejelzési tranzakciókat rögzíthetnek előrejelzési formában. Az aktuális tranzakciói során minden rendelkezésre álló attribútum felhasználható az előrejelzési tranzakcióhoz—például a sor nyereségessége, a sor attribútumok, a dolgozók vagy a leírások. Megtervezheti, hogy mennyi idő után készít számlát a vevőnek, miután hozzájárult az összeggel. 

Projekt-előrejelzési tranzakciókról egységek és az összegek alapulnak. 

Minden projekt előrejelzéshez előrejelzés modellt kell társítani. Az előrejelzés tranzakció megadása után, automatikusan egy előrejelzési modellt javasol. Az előrejelzési modell az előrejelzési tranzakcióit tárolójaként működik. 

Az előrejelzési modelleket kijelölheti egy modell részmodelljének. Ez lehetővé teszi, hogy régió, időszak vagy osztály alapján készítsen előrejelzést. Kimásolhatja egy modell előrejelzési tranzakcióit egy új modell létrehozásához, és átviheti a tranzakciókat a főkönyvbe. Mivel egy az egyhez kapcsolatot előrejelzés és a modell között, minden előrejelzési modellből egy külön költségvetés a projekthez készül. 

Előrejelzési modellek az ellenőrzési mechanizmusok projektekhez előrejelzés-csökkentés is használhatók. Az előrejelzés-csökkentés során, az tényleges tranzakciók csökkentik az előrejelzési tranzakció egyenlegét. Azonban a hierarchiában a legmagasabb projekt előrejelzés-csökkentés vonatkozik, mivel nyújt az előrejelzés változásai korlátozott megjeleníti. Például ha egy dolgozó alprojekt tartozik, a dolgozó tényleges tranzakciókat feladja a szülőprojekt projekttípusát. Emiatt nehéz lehet nyomon követni a változásokat, mert nem lehet könnyen meghatározni, hogy melyik tranzakció melyik alprojektben okozta az előrejelzés összegében a csökkenést. Ezért célszerű készíteni az előrejelzés-csökkentéshez használandó előrejelzés modellről egy másolatot. Majd a jelentések segítségével megtekintheti, hogy mi volt eredetileg előre jelezve. 

A projekt előrejelzések felülvizsgálhatóak, másolhatóak, törölhetőek vagy átvihetőek a költségvetés főkönyvébe. Azonban nincs folyamatvezérlés. Bármely olyan dolgozó , amely az előrejelzési laphoz engedéllyel rendelkezik ellenőrzés nélkül felülvizsgálatot végezhet.

-   **Vizsgálja felül** – Felülvizsgálhatja az előrejelzési tranzakciót azokon a lapokon, ahol az eredeti tételek történtek.
-   **Másolás vagy törlés** – Miután másolta az előrejelzési tranzakciókat, másolja az egyik előrejelzési modell tranzakciójának sorait egy másik előrejelzési modellbe. A költségvetések törlésekor egy előrejelzési modell előrejelzési tranzakcióit törli. A másolni vagy törölni kívánt előrejelzési tranzakcióik korlátozása érdekében, jelöljön be konkrét tranzakciótípusokat és dátumokat. Ez lehetővé teszi, hogy csak az előrejelzés meghatározott részeit másolja vagy törölje.
-   **Átvitel** – Miután átvitte a projekt előrejelzést a költségvetés főkönyvbe, átviszi előrejelzési modell előrejelzési tranzakcióit a költségvetési főkönyvbe. Bármely olyan tranzakciót felülírhat, amelyet korábban átvitt a költségvetési főkönyvbe, amelybe a projekt előrejelzést átvitte.

## <a name="project-budgets"></a>Projektköltségvetések
A projekt-költségvetés egyszerűbb módszer, mint a előrejelzés, bár előrejelzési modellekkel működik együtt. Egyetlen bejegyzés űrlapot használ az eredeti költségvetés adataihoz és felülvizsgálataihoz, és a verziók, és olyan előrejelzéseket tesz lehetővé, amelyek csak az összegen, a kategórián vagy a tevékenységen alapul. 

A projekt-költségvetés során, az összes eredeti költségvetést és felülvizsgálatot be kell küldeni a projekt munkafolyamatba jóváhagyásra. A munkafolyamatok a folyamatok feletti fokozott ellenőrzést és az előzmények rekordjainak létrehozását biztosítja. 

A projekt-költségvetés hasonlít a főkönyvi költségvetéshez, de gyorsabb és könnyebben lehet beállítani. A főkönyvi költségvetésben valamennyi beállítást, mint például a számsorozatok vagy a pénznem, nem szabad külön a projekthez létrehozni.

A projektköltségvetéseket automatikusan két előrejelzési modellel társítja, az eredeti költségvetés, és a fennmaradó költségvetés egyikét. Ezért az előrejelzési modelleken alapuló kimutatások költségvetési adatokat használhatnak. A projektköltségvetés vállalása esetén, a rendszer létrehozza társított modelleken alapuló előrejelzési tranzakciókat, amelyeket szabályozási és jelentési célokra használják.

## <a name="forecast-models"></a>Előrejelzési modellek
Az előrejelzési modellek egyrétegű hierarchiával rendelkeznek. Ez azt jelenti, hogy egy projekt előrejelzést egy előrejelzési modellel kell társítani.

A projekt-előrejelzések használatakor a modellek mint részmodellek azonosíthatók. Régió, időszak vagy osztály alapján készíthet előrejelzést. Például, létrehozhat előrejelzési modellt egy évre vonatkozóan, és ezután részmodelleket készíthet az északkeleti, délkeleti, északnyugati és délnyugati régiók előrejelzéseiről, amelyet az adott területi vezető nyújt be. A rendelkezésre álló jelentésekben található különböző beállítások segítségével megtekintheti az összesített előrejelzés vagy a részmodell szerinti információkat.



