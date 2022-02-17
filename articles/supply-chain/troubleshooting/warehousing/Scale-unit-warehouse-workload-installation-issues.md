---
title: Feldolgozási problémák lépnek fel egy méretarányos raktári munkaterhelés telepítése után
description: Ez a témakör azokat a problémákat írja le, amelyek röviddel a mérlegegység raktári munkaterhelésének telepítése után fordulhatnak elő, és tanácsokat ad ezek kijavítására.
author: perlynne
ms.date: 1/13/2022
ms.topic: troubleshooting
ms.search.form: WHSLoadPlanningWorkbench, WHSOutboundLoadPlanningWorkbench
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2022-01-13
ms.dyn365.ops.version: 10.0.25
ms.openlocfilehash: f589ffed61b695f471989ab1dd693f30cd5d5262
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/31/2022
ms.locfileid: "8071779"
---
# <a name="processing-issues-occur-after-a-scale-unit-warehouse-workload-is-installed"></a>Feldolgozási problémák lépnek fel egy méretarányos raktári munkaterhelés telepítése után

Ez a témakör azokat a problémákat írja le, amelyek röviddel a mérlegegység raktári munkaterhelésének telepítése után fordulhatnak elő, és tanácsokat ad ezek kijavítására.

## <a name="issue-1-error-after-a-load-is-released-from-a-load-planning-workbench"></a>1. probléma: Hiba, miután egy terhelést felszabadított a terheléstervezési munkaasztalról

### <a name="symptoms-of-issue-1"></a>A probléma tünetei 1

Amikor elenged egy terhelést a **Terhelés tervező munkapad** vagy **Kimenő terhelés tervező munkaasztal** oldalon a következő hibaüzenet jelenik meg:

> A rendszer kivételt észlelt a(z) %1 rakomány feladásakor; a rakomány nem adható ki.
> 
> SZÁLLÍTÁSTÁBLÁZAT FRISSÍTÉSE...
> 
> A Szállítmányok (WHSShipmentTable) rekord nem szerkeszthető. Szállítási azonosító:...

Íme egy tényleges példa, amely mintaadatokat tartalmaz:

> Kivétel történt az USMF-000033 rakomány feladásakor, a terhelést nem sikerült felszabadítani.
Munkamenet 5133 (adminisztrátor)
>
> SZÁLLÍTÁSI TÁBLÁZAT FRISSÍTÉSE ORDERNUM=?,RECVERSION=?,MODIFIEDDATETIME=?,MODIFIEDBY=? HOL ((RECID=?) ÉS (RECVERSION=?))  
> A [Microsoft][ODBC 17-es SQL Server-illesztőprogram][SQL Server]@@ méretezési egység megpróbálta frissíteni a @A méretegység tulajdonában lévő rekordokat.  
> Object Server Azure:
>
> A Szállítmányok (WHSShipmentTable) rekord nem szerkeszthető. Szállítási azonosító: USMF-000031, USMF-000033. Az SQL adatbázis a következő hibát jelzi:

### <a name="cause-of-issue-1"></a>A probléma oka 1

Ez a probléma akkor fordulhat elő, ha a feltételek alábbi kombinációja áll fenn a méretezési egység raktári munkaterhelésének telepítésekor:

- A rendszer tartalmaz egy fel nem adott rakományt, ahol több sor van társítva különböző rendelésekhez, és egyes rakománysorok nincsenek társítva egy szállítmányhoz.
- A rendszer a szállítmányösszevonás használatára van beállítva.

Az elosztott hibrid topológia telepítésében minden terhelési és szállítási rekord egy adott léptékű egység vagy hub tulajdonaként van megjelölve. Amikor elenged egy terhelést a **Terhelés tervező munkapad** oldalon a rendszer megváltoztatja a hozzárendelt tulajdonjogot. Előfordulhat azonban, hogy a korábban felsorolt feltételek miatt a rendszer nem tudja feloldani az adatok tulajdonjogát. Ezért nem tudja kiadni a rakományt a raktárba.

### <a name="resolution-of-issue-1"></a>Az 1. kérdés megoldása

Ossza fel a rakományt két kisebb rakományra, mielőtt kiadná a raktárba.

## <a name="issue-2-error-while-a-wave-is-processed-on-a-scale-unit"></a>2. probléma: Hiba a hullám skálaegységen történő feldolgozása közben

### <a name="symptoms-of-issue-2"></a>A 2. probléma tünetei

Amikor hullámot dolgoz fel egy skálaegységen, a következő hibaüzenet jelenik meg:

> Nem módosíthatja a betöltési sort a RecId = értékkel%1, load id=%2 mivel továbbra is a vállalati központ tulajdonában van. Kérjük, győződjön meg arról, hogy a megfelelő kimenő rakományt kiadta egy méretarányos egységnek, és ezáltal létrejöttek a raktári rendelési sorok.

Íme egy tényleges példa, amely mintaadatokat tartalmaz:

> Infónapló az állás végrehajtásához Hullám végrehajtása USMF-000000012 (9223377668365210)  
> Infónapló a feladat végrehajtásához: USMF-000000012 (9223377668370462)  
> Nem módosíthatja a betöltési sort a következővel: RecId = 68719478242, load id= USMF-000034, mivel továbbra is a vállalati hub tulajdona. Kérjük, győződjön meg arról, hogy a megfelelő kimenő rakományt kiadta egy méretarányos egységnek, és ezáltal létrejöttek a raktári rendelési sorok.

### <a name="cause-of-issue-2"></a>A probléma oka 2

Az elosztott hibrid topológia telepítésében a terhelési és szállítási adatok tulajdonjoga egy adott léptékű egységhez vagy hubhoz van hozzárendelve. A hullámzási feldolgozás részeként az adatok tulajdonjogát egy skálaegységhez kell hozzárendelni.

Méretezési egység raktári munkaterhelés telepítésekor, ha egy nyitott szállítmány rakományhoz és hullámhoz van társítva, a rendszer nem tudja ellenőrizni az adatok tulajdonjogát. Ezért a hullámfeldolgozás meghiúsul a skálaegységen.

### <a name="resolution-of-issue-2"></a>A 2. kérdés megoldása

Engedje el a rakományt a raktárba az agyról.

## <a name="troubleshoot-issues-by-viewing-a-records-ownership-and-destination"></a>A problémák elhárítása a rekord tulajdonjogának és céljának megtekintésével

Az elosztott hibrid topológia központi telepítésében sok rekordtípus egy adott léptékű egység vagy hub tulajdonaként van megjelölve. Miután átvált egy elosztott hibrid topológiára és/vagy beállított egy új léptékű egység raktári munkaterhelést, a rendszer tulajdonjogot rendel az egyes releváns rekordokhoz. Ez a folyamat néha hibákat vagy váratlan eredményeket okozhat. Ezért a rekord tulajdonjogával és átruházási céljával kapcsolatos információk segíthetnek az ilyen típusú módosítások végrehajtása után felmerülő problémák hibaelhárításában.

Kövesse ezeket a lépéseket egy rekord tulajdonjogának és átruházási céljának megtekintéséhez.

1. Nyissa meg a megfelelő rekordot.
1. A Műveletpanelen a **Opciók** lapon, a **Adatok rögzítése** csoport, válassza ki **Az összes mező megjelenítése**.
1. A megjelenő oldalon a kiválasztott rekordhoz elérhető összes mező értékei láthatók. Tekintse át a következő mezőket:

    - **SYSSCALEUNITID** – Ez a mező a rekord jelenlegi tulajdonosát mutatja.
    - **SYSTARGETSCALEUNITID** – Ez a mező annak a hubnak vagy léptékegységnek az azonosítóját mutatja, amelyre a rekord átkerül, amikor a jelenlegi tulajdonos befejezte a munkát. A mező értékét az ilyen típusú folyamatokat kezelő kötegelt feladatok használják. Bár ez a mező nem kapcsolódik közvetlenül a tulajdonjoghoz, a tulajdonjog megváltozhat a rekord átruházásakor. Egyes esetekben ez a mező üres lesz.
