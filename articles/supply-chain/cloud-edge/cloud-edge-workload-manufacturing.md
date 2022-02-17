---
title: Gyártásvégrehajtási munkaterhelések felhőalapú és peremhálózati skálázási egységekhez
description: Ez a témakör ismerteti, hogyan működnek a gyártási végrehajtási számítási feladatok felhő- és peremhálózati skálázási egységekkel.
author: cabeln
ms.date: 10/06/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: SCM
ms.author: cabeln
ms.search.validFrom: 2020-10-06
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 633740ee1e26d2e4ed2ea7031ef298fb11c2ab58
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/31/2022
ms.locfileid: "8068844"
---
# <a name="manufacturing-execution-workloads-for-cloud-and-edge-scale-units"></a>Gyártási végrehajtás munkaterhelései felhőalapú és peremhálózat-lépték szerinti egységekhez

[!include [banner](../includes/banner.md)]

> [!IMPORTANT]
> A gyártási végrehajtási munkaterhelés jelenleg csak előnézetben érhető el.
>
> Néhány üzleti funkció nem teljes mértékben támogatott a nyilvános előzetes verzióban, ha számítási feladatokat skálázási egységeken használja.
>
> Az előnézeti gyártási végrehajtási munkaterhelés nem futtatható olyan léptékű egységen, ahol a raktári végrehajtási munkaterhelés is telepítve van.

A gyártásvégrehajtásban a skálázási egységek a következő lehetőségeket biztosítják:

- A gépkezelők és az üzemirányítók hozzáférhetnek az üzemeltetési termelési tervhez.
- A gépkezelők diszkrét és folyamatgyártási feladatok futtatásával naprakészen tarthatják a tervet.
- Az üzemvezető módosíthatja az üzemeltetési tervet.
- A dolgozók hozzáférhetnek a munkaidőhöz és a jelenléthez a peremhálózati érkezéskori és távozáskori blokkoláshoz a megfelelő dolgozói fizetésszámítás biztosítása érdekében.

Ez a témakör ismerteti, hogyan működnek a gyártási végrehajtási számítási feladatok felhő- és peremhálózati skálázási egységekkel.

## <a name="the-manufacturing-lifecycle"></a>A gyártási életciklus

Ahogy az alábbi ábra is mutatja, a gyártási életciklus három fázisra oszlik: *Tervezés*, *Végrehajtás* és *Véglegesítés*.

[![Gyártási végrehajtási fázisok egyetlen környezet használata során](media/mes-phases.png "Gyártási végrehajtási fázisok egyetlen környezet használata esetén.")](media/mes-phases-large.png)

A _Tervezés_ fázis tartalmazza a termékdefiníciót, a tervezést, a rendelés létrehozását és ütemezését, valamint a kiadást. A kiadási lépés a _Terv_ fázisról a _Végrehajtás_ fázisra való áttérést jelzi. A termelési rendelés kiadásakor a termelési rendelési feladatok láthatók lesznek a termelési szinten, és készen állnak a végrehajtásra.

Ha egy termelési feladat befejezettként van megjelölve, a _Végrehajtás_ fázisról a _Véglegesítés_ fázisra kerül. A _Véglegesítés_ fázisban a *Végrehajtás* fázis regisztrációi egy jóváhagyási munkafolyamaton mennek keresztül, ahol kiszámították, jóváhagyták és átvitték őket. Ezen a ponton a gyártási rendelés befejeződött. Ezért a munkavállalók fizetésének alapja létrejön.

## <a name="splitting-the-execute-phase-into-a-separate-workload"></a>A Végrehajtás fázis felosztása külön munkaterhelésre

Ahogy a következő ábra is mutatja, skálázási egységek használata esetén a _Végrehajtás_ fázis külön számítási feladatként van felosztva.

[![Gyártási végrehajtási fázisok skálázási egységek használata esetén](media/mes-phases-workloads.png "Gyártási végrehajtási fázisok méretarányos egységek használata esetén.")](media/mes-phases-workloads-large.png)

A modell most egy egypéldányos telepítésből egy olyan modellre kerül, amely a központon és a skálázási egységeken alapul. A _Tervezés_ és a _Véglegesítés_ fázisok háttérirodai műveletekként futnak a központban, és a gyártási végrehajtási számítási feladat a skálázási egységeken fut. Az adatok átvitele aszinkron módon történik a központ és a skálázási egységek között.

Amikor egy termelési rendelést kiadnak a központban, a termelési feladatok feldolgozásához szükséges összes adat átkerül a skálázási egységbe. Ezek az adatok tartalmazzák a termelési rendeléseket, a termelési útvonalakat, az anyagjegyzékeket és a termékeket. A termelési rendeléshez nem kapcsolódó adatok (például közvetett tevékenységek, távolléti kódok és termelési paraméterek) szintén átkerülnek a központból a skálázási egységre. Rendszerint a központból származó és a skálázási egységbe átvitt adatok csak a központon hozhatók létre vagy frissíthetők. Például egy új távolléti kód vagy közvetett tevékenység nem hozható létre a skálázási egységben, amely csak a regisztrációhoz használható. A skálázási egységen a végrehajtás során végzett regisztrációk ezután átkerülnek a központba, ahol a munkaidő- és jelenlét-jóváhagyás, a készlet és a pénzügyi frissítések feldolgozása történik.

## <a name="manufacturing-execution-tasks-that-can-be-run-on-workloads"></a>Számítási feladatokon futtatható gyártási végrehajtási feladatok

A következő gyártási végrehajtási feladatok jelenleg futtathatók a számítási feladatokon, ha skálázási egységeket használnak:

- Érkezéskori blokkolás, bejelentkezés, távozáskori blokkolás és távollét
- Feladat kezdete
- Csomagfeladatok
- Jelentés az előrehaladásról
- Selejt jelentése
- Közvetett tevékenység
- Szünet
- Készként jelentés és berakodása (a raktár végrehajtási terhelésének a skálázási egységen való futtatására is szükség van, lásd még a [Készként jelentés és betárolás skálázási egységen](#RAF))

## <a name="working-with-manufacturing-execution-workloads-on-the-hub"></a>Gyártási végrehajtási számítási feladatok használata a központban

Általában a gyártási végrehajtási számítási feladatok futtatásához szükséges folyamatok automatikusan futnak, hogy a központ és az összes skálázási egység szükség szerint szinkronban maradjon. Ha azonban problémája van, manuálisan aktiválhatja a számítási feladatokból kapott nyers regisztrációk feldolgozását, és/vagy ellenőrizheti a regisztrációs feldolgozási naplót.

### <a name="manually-process-raw-registrations"></a>Nyers regisztrációk manuális feldolgozása

A Supply Chain Management szolgáltatásban a kötegelt feladatok automatikusan futnak a számítási feladatokból beérkezett összes regisztráció feldolgozásához. Ez a feladat létrehozza a szükséges termelési naplókat és naplóbejegyzéseket, amikor a regisztrációfeldolgozás a számítási feladatokon végzett feladathoz történik.

Bár a feladat általában automatikusan fut, manuálisan bármikor futtathatja, ha bejelentkezik a központba, és a **Termelésvezérlés \> Időszakos feladatok  \> Háttérirodai munkaterhelés-kezelés \> Nyers regisztrációk feldolgozása** pontra lép.

### <a name="check-the-raw-registration-processing-log"></a>A nyers regisztrációs feldolgozási napló ellenőrzése

A regisztrációs feldolgozási napló áttekintéséhez jelentkezzen be a központba, és lépjen a **Termelésvezérlés \> Időszakos feladatok \> Háttérirodai munkaterhelés-kezelés \> Nyers regisztrációs feldolgozási napló** pontba. A **Nyers regisztrációs feldolgozási napló** lap a feldolgozott nyers regisztrációk listáját és az egyes regisztrációk állapotát jeleníti meg.

![A nyers regisztrációs feldolgozási napló oldala.](media/mes-processing-log.png "A nyers regisztrációs feldolgozási napló oldala")

A lista bármely regisztrációján úgy dolgozhat, hogy kijelöli, majd a műveletpanelen az alábbi gombok egyikét választja:

- **Feldolgozás** – A kijelölt regisztráció manuális feldolgozása. Ez a művelet akkor lehet hasznos, ha a _Nyers regisztrációk feldolgozása_ feladat nem fut, vagy ha nem sikerült.
- **Megszakítás** – A kijelölt regisztráció visszavonása.

## <a name="working-with-manufacturing-execution-workloads-on-a-scale-unit"></a>Gyártási végrehajtási számítási feladatok használata a skálázási egységen

Általában a gyártási végrehajtási számítási feladatok futtatásához szükséges folyamatok automatikusan futnak, hogy a központ és az összes skálázási egység szükség szerint szinkronban maradjon. Ha azonban problémája van, ellenőrizheti a skálázási egységen feldolgozott rendelések előzményeit, vagy manuálisan futtathatja a _Gyártási központból a skálázási egységbe irányuló üzenetfeldolgozó_ feladatot.

### <a name="view-the-history-of-manufacturing-jobs-that-have-been-processed-on-a-scale-unit"></a>A skálázási egységen feldolgozott gyártási feladatok előzményeinek megtekintése

A skálázási egységen feldolgozott gyártási feladatok előzményeinek áttekintéséhez jelentkezzen be a skálázási egység gépébe, és lépjen a **Termelésvezérlés \> Időszakos feladatok \> Háttérirodai számítási feladatok kezelése \> Gyártási feladatok feldolgozási előzményei** pontra. A **Gyártási feladatok feldolgozási előzményei** lap a skálázási egység termelési rendeléseinek feldolgozási előzményeit jeleníti meg. A lista bármely termelési rendelésén úgy dolgozhat, hogy kijelöli, majd a műveletpanelen az alábbi gombok egyikét választja:

- **Feldolgozás** – A kijelölt termelési rendelés manuális feldolgozása.
- **Megszakítás** – A kijelölt termelési rendelés visszavonása.

### <a name="manufacturing-hub-to-scale-unit-message-processor-job"></a>Gyártási központból a skálázási egységbe irányuló üzenetfeldolgozó

A _Gyártási központból a skálázási egységbe irányuló üzenetfeldolgozó_ feladat feldolgozza a központból a skálázási egységbe érkező adatokat. Ez a feladat automatikusan elindul, amikor a gyártási végrehajtási számítási feladat telepítve van. Azonban manuálisan is futtathatja, ha a **Termelésvezérlés \> Időszakos feladatok \> Háttérirodai munkaterhelés-kezelés \> Gyártási központból a skálázási egységbe irányuló üzenetfeldolgozó** pontba lép.

<a name="RAF"></a>

## <a name="report-as-finished-and-putaway-on-a-scale-unit"></a>Készként jelentés és berakodás egy skálaegységre

<!-- KFM: 
This section describes how to enable the abilities to report as finished and then putaway finished items when you are using to a scale unit.

### Enable and use report as finished and putaway on a scale unit -->

A jelenlegi kiadásban a készre jelentés és betárolási műveletek (késztermékekhez, társtermékekhez és melléktermékekhez) támogatva vannak a [raktári végrehajtási terheléshez](cloud-edge-workload-warehousing.md) (nem a gyártási végrehajtási terheléshez). Ennek megfelelően ahhoz, hogy egy skálaegységhez kapcsolódva használni tudja ezt a funkciót, a következőket kell tenni:

- A raktári végrehajtási számítási feladatot és a gyártási végrehajtási számítási feladatot is telepítse a skálaegységre.
- A Warehouse Management mobilalkalmazás használatával készként jelenthető, és feldolgozható a berakodási munka. A termelési üzem végrehajtási felülete jelenleg nem támogatja ezeket a folyamatokat.

<!-- KFM: API details needed

### Customize report as finished and putaway functionality

 -->

## <a name="enable-and-use-the-start-operation-on-a-scale-unit"></a>Engedélyezze és használja az indítási műveletet egy mérlegegységen

A jelenlegi kiadásban a gyártási és kötegelt rendelések indítási műveletét a [raktári végrehajtási terhelés](cloud-edge-workload-warehousing.md) (nem a gyártási végrehajtási munkaterhelés). Ezért ennek a funkciónak a használatához, amikor egy mérlegegységhez csatlakozik, el kell végeznie a következő feladatokat:

- A raktári végrehajtási számítási feladatot és a gyártási végrehajtási számítási feladatot is telepítse a skálaegységre.
- Engedélyezze a *Indítsa el a termelési rendelést a felhő- és peremléptékű egység raktárkezelési munkaterhelésén* jellemző be [Funkciókezelés](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).
- Használja a Warehouse Management mobilalkalmazást a gyártási vagy kötegelt rendelés elindításához.

## <a name="enable-and-use-material-consumption-on-a-scale-unit"></a>Az anyagfelhasználás engedélyezése és használata a mérlegegységen

A jelenlegi kiadásban a Warehouse Management mobilalkalmazásban az anyagfelhasználás regisztrálására szolgáló folyamatot támogatja a [raktári végrehajtási terhelés](cloud-edge-workload-warehousing.md) (nem a gyártási végrehajtási munkaterhelés). Ezért ennek a funkciónak a használatához, amikor egy mérlegegységhez csatlakozik, el kell végeznie a következő feladatokat:

- A raktári végrehajtási számítási feladatot és a gyártási végrehajtási számítási feladatot is telepítse a skálaegységre.
- Engedélyezze a *Regisztrálja az anyagfelhasználást a mobilalkalmazásban egy mérlegegységen* jellemző be [Funkciókezelés](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).
- Az anyagfelhasználás regisztrálásához használja a Warehouse Management mobilalkalmazást.

[!INCLUDE [cloud-edge-privacy-notice](../../includes/cloud-edge-privacy-notice.md)]

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
