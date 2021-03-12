---
title: Hardverméretezési követelmények helyszíni környezetekben
description: Ez a témakör a hardverméretezési követelményekkel foglalkozik helyszíni környezetekben.
author: sericks007
manager: AnnBe
ms.date: 11/27/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.custom: 55651
ms.assetid: ''
ms.search.region: Global
ms.author: chwolf
ms.search.validFrom: 2016-08-30
ms.dyn365.ops.version: Platform update 8
ms.openlocfilehash: 9d4f2e59d4dd78d15d561ff0da47e4b9b1a2fce3
ms.sourcegitcommit: b112925c389a460a98c3401cc2c67df7091b066f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/19/2020
ms.locfileid: "4798304"
---
# <a name="hardware-sizing-requirements-for-on-premises-environments"></a>Hardverméretezési követelmények helyszíni környezetekben

[!include [banner](../includes/banner.md)]

Mielőtt elkezdi a hardver és infrastruktúra helyszíni környezetekben való méretezésének folyamatát, ismerkedjen meg ezzel: [Rendszerkövetelmények felhőbeli telepítések esetén](system-requirements.md) és ezzel: [Beállítási és telepítési útmutató](../../dev-itpro/deployment/setup-deploy-on-premises-environments.md), hogy kellőképpen ismerje a mögöttes infrastruktúrát.

> [!NOTE]
> Alaposan figyeljen oda a rendszerbeállítás ajánlott eljárásaira az optimális teljesítmény érdekében.

A dokumentáció áttekintése után megkezdheti a tranzakciós és egyidejű felhasználói terjedelem becslését, illetve a környezet méretezését az átlagos processzormagonkénti teljesítmény alapján.

## <a name="factors-that-affect-sizing"></a>A méretezést befolyásoló tényezők

A következő ábrán látható összes tényező befolyásolja a méretezést. Minél részletesebb a begyűjtött információ, ön annál pontosabban tudja megállapítani a méretezést. A támogató adatok nélküli hardverméretezés valószínűleg pontatlan. Az abszolút minimális szükséges adat a tranzakció óránkénti sorsebesség-terhelés csúcspontja.

[![Hardverméretezés helyszíni környezetekhez](./media/lbd-sizing-01.png)](./media/lbd-sizing-01.png)

Balról jobbra haladva az első és az egyik legfontosabb tényező, ami a méretezés pontos becsléséhez szükséges, a tranzakció profil vagy a tranzakció jellemzés. Fontos, hogy mindig megtalálja a tranzakciós terjedelem óránkénti csúcspontját. Ha több csúcspont időszak van, akkor ezeket az időszakokat pontosan meg kell határozni.

Az infrastruktúrára hatással lévő terhelés megértése mellett ezeket a tényezőket is részletesen tanulmányoznia kell:

- **Tranzakciók** – általában a tranzakciók egy adott csúcsponttal rendelkeznek, ami nem változik a nap/hét során. Ez elsősorban a tranzakció típusától függ. Az idő- és kiadási tételek általában hetente egyszer érik el a csúcspontot, míg az értékesítési rendelési tételek gyakran tömegesen, integráció vagy szivárgás által érkeznek be a nap folyamán.
- **Egyidejű felhasználók száma** – Az egyidejű felhasználók száma a második legfontosabb méretezési tényező. Az egyidejű felhasználók száma alapján nem juthat megbízható méretezési becslésekhez, így ha ez az egyetlen rendelkezésre álló adata, akkor becsüljön meg egy hozzávetőleges számot, és térjen vissza, ha további adatok is rendelkezésére állnak. Egy pontos egyidejű felhasználó definíció azt jelenti, hogy:

    - A névvel rendelkező felhasználók nem egyidejű felhasználók.
    - Az egyidejű felhasználók mindig részhalmazai a névvel rendelkező felhasználóknak. 
    - A terhelés csúcspontja határozza meg a méretezésre vonatkozó maximális egyidejűséget.

    Egy felhasználó akkor egyidejű felhasználó, ha megfelel a következő feltételeknek:

    - Bejelentkezett.
    - Működő tranzakciók/lekérdezések a leltározás idején.
    - Nem tétlen állapotú munkamenet.

- **Adatok összetétele** – Ez elsősorban a rendszere beállításának és konfigurációjának módját jelenti. Például azt, hogy hány jogi személlyel, cikkel , és anyajegyzék-szinttel rendelkezik, illetve milyen összetettek a biztonsági beállítások. Ezen tényezők közül valamennyi kis hatással lehet a teljesítményre, így ezek kiegyenlítésére intelligens választási lehetőségek használata ajánlott az infrastruktúra esetén.
- **Bővítmények** – A testreszabások egyszerűek vagy összetettek lehetnek. A testreszabások száma, összetettsége és használati jellege különféle hatással vannak a szükséges infrastruktúra méretére. Összetett testreszabások esetén teljesítményértékeléseket ajánlott végezni annak biztosítása érdekében, hogy azok nem csak hatékonyak, de az infrastruktúra szükségeinek megértésében is segítenek. Ez még inkább elengedhetetlen akkor, ha a bővítmények nem a teljesítményre és skálázhatóságra vonatkozó ajánlott eljárások alapján vannak kódolva.
- **Jelentés és analitika** – Ezekhez a tényezőkhöz rendszerint a nehéz lekérdezések futtatása tartozik az adatbázis rendszereken található adatbázisok számára. A gyakoriság megértése és csökkentése erőforrás-igényes jelentések futtatásakor segíthet önnek a hatásuk megértésében.
- **Harmadik felektől származó megoldások** – Ezek a megoldások, mint például az ISV-k, ugyanazokkal a következményekkel és ajánlásokkal rendelkeznek, mint a bővítmények.

## <a name="sizing-your-environment"></a>A környezet méretezése

A méretezési követelmények megértése érdekében ismernie kell az ön által feldolgozandó tranzakciók terjedelmi csúcspontját. A legtöbb kiegészítő rendszer, mint például a felügyeleti jelentéskészítő vagy az SSRS, kisebb létfontosságú. Emiatt ez a dokumentum elsősorban az AOS-szel és az SQL Server-rel foglalkozik.

> [!NOTE]
> A számítási szintek általában felskálázódnak, és N+1 módon kell őket beállítani, ami azt jelenti, hogy ha három AOS-t becsült , akkor adjon hozzá egy negyedik AOS-t. Az adatbázis-szintet Always-On módban, magas rendelkezésre állással kell beállítani.

## <a name="sql-server-oltp"></a>SQL Server (OLTP)

### <a name="sizing"></a>Méretezés

- 3000-15000 óránkénti tranzakciós sorsebesség processzormagonként az adatbázis-kiszolgálón.
- A tipikus AOS-SQL processzormag arány az elsődleges SQL Server számára 3:1. Szükség lehet további processzormagokra a választott magas rendelkezésre állású konfiguráció alapján.

    - Az adatbázisokra támaszkodó műveletek ezt 2:1 arányra csökkenthetik.

- A változatokat a következő tényezők befolyásolják:

    - A használt paraméter-beállítások.
    - Bővítmény szintek.
    - További funkciók használata, mint például az adatbázisnapló és a figyelmeztetések. Az extrém adatbázis-naplózás tovább csökkenti a teljesítményt, óránként és processzormagonként 3000 alatti sorsebességre.
    - Adatösszetétel összetettsége – Egy egyszerű számlatükör és egy részletes számlatükör különböző módon befolyásolják a teljesítményt (egy példaként).
    - Tranzakció jellemzése.
    - 2 GB-tól 16 GB-ig terjedő memória minden egyes processzormag számára.
    - Kiegészítő adatbázisok az adatbázis-kiszolgálón, mint például a felügyeleti jelentéskészítő és az SSRS-adatbázisok.
    - Ideiglenes adatbázis = az adatbázis méretének 15%-a, annyi fájllal, amennyi tényleges processzor van.
    - SAN mérete és teljesítménye a teljes egyidejű tranzakciós terjedelem/felhasználás alapján.

### <a name="high-availability"></a>Magas rendelkezésre állás

Mindig ajánlott az SQL Server használata egy fürtben vagy egy tükrözött beállításban. A második SQL-csomópontnak ugyanannyi processzormaggal kell rendelkeznie, mint az elsődleges csomópont.

### <a name="active-directory-federation-services-ad-fs"></a>Active Directory Federation Services (AD FS)

Az AD FS méretezéséhez lásd: [AD FS kiszolgálói kapacitás dokumentáció](/windows-server/identity/ad-fs/design/planning-for-ad-fs-server-capacity).

Elérhető egy [méretezési táblázat](https://adfsdocs.blob.core.windows.net/adfs/ADFSCapacity2016.xlsx) a telepítésében található példányok számának tervezéséhez.

## <a name="aos-online-and-batch"></a>AOS (Online és kötegelt)

### <a name="sizing"></a>Méretezés

- Tranzakciós terjedelem/használat szerinti méretezés

    - 2000-6000 sorsebesség processzormagonként
    - 16 GB példányonként
    - Szokásos mező – 4-24 processzormag
    - 10-15 vállalati felhasználó processzormagonként
    - 15-25 Activity felhasználó processzormagonként
    - 25-50 csapattag processzormagonként

- Köteg

    - 1–4 Kötegszál processzormagonként
    - A kötegfeldolgozási ablak jellemzésétől függő méret

- Ne feledje, hogy az AOS, az adatkezelő és a köteg ugyanahhoz a Service Fabric szerepkörhöz tartoznak. Ezen három terhelést kombináltan méretezze, és ne válassza szét őket úgy, mint a Microsoft Dynamics AX 2012-ben.
- Ugyanazok az SQL Server változtathatósági tényezők érvényesek itt is.

### <a name="high-availability"></a>Magas rendelkezésre állás

- Győződjön meg róla, hogy legalább 1-2-vel több AOS érhető el, mint az ön becslése.
- Győződjön meg róla, hogy van legalább 3–4 elérhető virtuális állomása.

## <a name="management-reporter"></a>Felügyeleti Jelentéskészítő

A legtöbb esetben a két csomópontot használó ajánlott minimális követelmények betartása elég a működéshez,kivéve ha a használat kiterjedt. Csak abban az esetben kell kettőnél több csomópont, ha a használat jelentős fokú. Kérjük, skálázzon szükség szerint.

## <a name="sql-server-reporting-services"></a>SQL Server Reporting Services szolgáltatás

Az általános elérhetőségű verzió esetén csak egy SSRS-csomópontot lehet telepíteni. Figyelje az SSRS-csomópontját tesztelés közben, és szükség szerint emelje az SSRS számára elérhető processzormagok számát. Győződjön meg arról, hogy rendelkezik a virtuális állomáson olyan előre konfigurált másodlagos csomóponttal, amely eltér az SSRS virtuális géptől. Ez akkor fontos, ha probléma van az SSRS-t tároló virtuális géppel vagy a virtuális állomással. Ez esetben ki kellene őket cserélni.

## <a name="environment-orchestrator"></a>Környezeti szervező

A szervező szolgáltatás kezeli az ön telepítését és az ehhez kapcsolódó LCS-szel való kommunikációt. Ez a szolgáltatás az elsődleges Service Fabric szolgáltatásként van telepítve, és legalább három virtuális gépet igényel. Ez a szolgáltatás egy helyen található a Service Fabric szervezési szolgáltatásokkal. Ezt a fürt terhelési csúcspontja alapján kell méretezni. További információkért lásd: [Önálló Service Fabric fürttelepítés tervezése és előkészítése](https://docs.microsoft.com/azure/service-fabric/service-fabric-cluster-standalone-deployment-preparation).

## <a name="virtualization-and-oversubscription"></a>Virtualizáció és túljegyzés

Az olyan létfontosságú szolgáltatásokat, mint az AOS, dedikált erőforrásokkal rendelkező virtuális gépeken kell tárolni. Ilyen erőforrások a processzormagok, a memória, és a lemez.
