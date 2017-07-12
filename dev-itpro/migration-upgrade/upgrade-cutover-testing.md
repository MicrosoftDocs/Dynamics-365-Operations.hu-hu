---
title: "Frissítés – Átállás teszt"
description: "Ez a témakör bemutatja, hogy tesztelheti az AX 2012 kikapcsolása utáni, de a Dynamics 365 for Finance and Operations Enterprise edition bekapcsolása előtti esedékes tevékenységeket."
author: tariqbell
manager: AnnBe
ms.date: 05/29/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Developer, IT Pro
ms.reviewer: margoc
ms.search.scope: Operations, UnifiedOperations, Platform
ms.search.region: Global
ms.author: tabell
ms.search.validFrom: 2017-06-16
ms.dyn365.ops.version: Platform update 8
ms.translationtype: Human Translation
ms.sourcegitcommit: 6816e3820ab77c71bbf9bde4a068375448331671
ms.openlocfilehash: 711ad5cc3aafacf209704349effb4e08019205ac
ms.contentlocale: hu-hu
ms.lasthandoff: 06/15/2017

---

# <a name="upgrade-cutover-testing"></a>Frissítés – Átállás teszt

[!include[banner](../includes/banner.md)]

[!include[upgrade banner](../includes/upgrade-banner.md)]

Az *átállás* az a kifejezés, amelyet az új rendszer élesítésének végleges folyamatára használunk. Az átállási folyamat azon feladatokból áll, amelyek a Microsoft Dynamics AX 2012 kikapcsolása után, de a Microsoft Dynamics 365 for Finance and Operations Enterprise edition bekapcsolása előtt következnek be. A frissítési átállási tesztelés célja az átállási folyamat gyakorlása, hogy zökkenőmentes élményt nyújtjon mindazoknak, akik a tényleges átállás élesítése során érintettek.

Egy átállás során két fő munkafolyamat van:

- **Technikai munkafolyamat** – Ez a munkafolyamat tartalmazza az adatfrissítési végrehajtási folyamatot. A vállalkozása korlátozza az engedélyezett leállási idő küszöbértékét. A leállás során sem az AX 2012, sem a Finance and Operations nem lesz elérhető. Megtörténhet, hogy a munkafolyamatnak módosítania kell az adatfrissítési eljárást a vállalat leállási ideje küszöbértékének megfelelően.
- **Funkcionális munkafolyamat** – Ez a munkafolyamat az adatfrissítés befejezése után végrehajtott konfigurációs feladatokat tartalmazza. Mindezeket a feladatokat dokumentálni kell és számszerűsíteni kell, és egy erőforrást kell hozzárendelni, mivel mind a funkcionális munkafolyamatnak, mind a technikai munkafolyamatnak be kell illeszkednie a vállalkozás leállási idejébe.

A következő ábra bemutatja az átállás teljes folyamata, ahogyan az élesben a termelési környezetben végbe fog menni.

![Átállási folyamat](./media/cutover_1.png)

Ez az átállási folyamat a következőkben tér el a védőfalkörnyezetben végrehajtótt alapvető adatfrissítéstől:

- Az AX 2012 adatbázist a rendszer nem másolja, csak biztonsági másolatot készít, majd módosítja az eredeti adatbázist. Ez a megközelítés gyorsabb, és a biztonsági másolatot biztosítja a visszaállítást, ha erre szükség van.
- Mivel a Finance and Operations termelési környezete korlátozta a hozzáférést, azok a feladatok, amelyeket korábban az Application Object Server (AOS) védőfalkörnyezetben hajtottak végre, most a Microsoft DSE csoportja végzi el. Ezen feladatok közé tartozik a bacpac fájl letöltése és importálása, valamint a MajorversionDataUpgrade.zip csomag futtatása.
- A következő feladatokat adtuk hozzá:

    - Füstellenőrzés végzése.
    - Alkalmazás-beállítási feladatok elvégzése. Ez a lépés nagy lehet a használt funkcióktól függően. Ebben a lépésben a funkcionális csoport konfigurálja az új alkalmazásfunkciókat úgy, hogy készen álljanak a frissített rendszerben történő használatra.
    - Felhasználók újbóli engedélyezése. Értesítse a felhasználói bázist, hogy a frissítés befejeződött, és újra használhatják a rendszert.

## <a name="technical-workstream"></a>Technikai munkafolyamat

A technikai munkafolyamat különböző technikai csapattagokat foglal magába: az adatbázis rendszergazdáját (DBA), AX 2012 rendszergazdját, a kiszolgálói rendszergazdákat, és azokat a fejlesztőket, akik ismerik az AX 2012 és a Finance and Operations rendszereket. Ez a témakör elmagyarázza, hogy mely feladatokhoz milyen szerepek tartoznak.

Az átállási tesztelés során a technikai csoport elsősorban az adatfrissítési folyamat teljesítményét és megbízhatóságát ellenőrzi, hogy az megfelel-e a vállalat leállási ideje küszöbértékének. Ez a folyamat hardvereszközök és szoftverek számos elemét tartalmazza. Ezek közül egyes elemek a helyszínen vannak, mások a Microsoft-felhőben. Ezenkívül számos egyedi alkalmazáskódot és szabványkódot is tartalmaz. A tesztelés eredményének bizalmat kell ébresztenie a környezetében végzendő átállási folyamatban.

### <a name="turn-off-the-ax-2012-aos-instances"></a>Az AX 2012 AOS-példányok kikapcsolása

Ehhez a feladathoz be kell vonnia az AX 2012 rendszergazdáját és a kiszolgáló rendszergazdáit.

Az alábbi területeket ajánlott ellenőrizni:

- **Az átállás időpontjában futó kötegelt feladatok** – A már elindított hosszú távú kötegelt munka megakadályozza a rendszer leállítását. Tervezzen előre hogy megállíthassa AOS-példányait a kívánt pillanatban. Előfordulhat, hogy ütemeznie kell a kötegeket, hogy valamivel az AX 2012 kikapcsolása előtt elkészüljenek.
- **Integrált rendszerek** – Lehet hogy más rendszerek is integrálódnak az AX 2012 környezethez. Ezeket a tényezőket kell figyelembe vennie az AX 2012 kikapcsolása esetén. Előfordulhat például, korábban ki kell kapcsolnia az integrált rendszereket az AX 2012 kikapcsolása előtt, hogy az összes többi folyamatban lévő tranzakciót el lehessen végezni. Az integrált rendszerek követelményei vállalkozásonként rendkívül eltérőek lehetnek. Ezért szakértői csapatának önállóan kell megterveznie ezt a forgatókönyvet.

### <a name="create-a-backup-of-the-ax-2012-database"></a>Készítsen biztonsági másolatot az AX 2012 adatbázisról

Ehhez szüksége lesz az adatbázis-rendszergazdára. A biztonsági másolatot visszaállítás esetén használhatja. Hivatkozási pontként is használható, amelyet egy bizonyos időre megőriznek, és amely a rendszer állapotát jeleníti meg az átállás pillanatában.

Az alábbi területeket ajánlott ellenőrizni:

- Legyen konkrét időzítése a biztonsági mentéshez.
- Adja meg a használt biztonsági beállításokat (például tömörítés és nem tömörítés) a lehető leggyorsabb biztonsági másolat biztosítása érdekében.

### <a name="export-the-database-to-bacpac"></a>Az adatbázis exportálása bacpac fájlba

Ehhez szüksége lesz az adatbázis-rendszergazdára. A feladat kimenete az az exportfájl, amely a Microsoft Azure alkalmazásra lesz feltöltve az új rendszerhez.

Az alábbi területeket ajánlott ellenőrizni:

- Legyen konkrét időzítése a biztonsági mentéshez.
- Optimalizálja az exportálási folyamatot a lehető leggyorsabb élmény biztosítása érdekében. Az optimalizáláshoz a következőkre lehet szükség:

    - Mérje a rendszer erőforrásait – például a processzort, az operációs rendszer lemezét és a memóriát – exportálás közben.
    - Ha szűk keresztmetszeteket talál az erőforrásoknak, hozzon létre tervet azok enyhítése érdekében. Általában a szükségesnél több erőforrás hozzárendelésével csökkentheti a szűk keresztmetszeteket.

### <a name="upload-the-bacpac-file-to-azure-storage"></a>A bacpac fájl feltöltése az Azure-tárhelyre

Ehhez a feladathoz az adatbázis-rendszergazdára vagy a kiszolgáló rendszergazdáira lesz szükség. A feladat során a bacpac fájlt a rendszer az Azure-tárhelyre helyezi át.

Az alábbi területeket ajánlott ellenőrizni:

- Válassza ki azt a gépet, amelyet a feltöltésre fog használni, és győződjön meg arról, hogy a Azure Storage böngészőeszköz be van-e beállítva, és készen áll-e a használatra.
- Határozza meg a feltöltési folymat konkrét időzítését többszöri méréssel. A feltöltési idők az internetkapcsolat sebességétől és az Azure Datacenter az ön helyéhez viszonyított földrajzi elhelyezkedésétől függően változnak.

### <a name="download-and-import-the-bacpac-file-to-the-azure-sql-database"></a>A bacpac fájl letöltése és importálása az Azure SQL-adatbázisba

Ha ez a feladat élesben történik, a műveletet a Microsoft DSE csapata végzi el. Az átállási tesztelése során azonban az adatbázis-rendszergazda végzi a műveletet. A feladat eredménye az az exportfájl, amely az Azure alkalmazásra lesz feltöltve az új rendszerhez.

Az alábbi területeket ajánlott ellenőrizni:

- Legyen konkrét időzítése az importálási folyamathoz.
- Optimalizálja az exportálási folyamatot a lehető leggyorsabb élmény biztosítása érdekében. Az optimalizáláshoz a következőkre lehet szükség:

    - Mérje a rendszer-erőforrásokat az exportálás során. Íme néhány példa:

        - **Az AOS-számítógépen:** processzor, operációs rendszer lemeze és memória
        - **Az Azure SQL Database példányon:** SQL adatbázis teljesítménye (DTU). Az AOS-számítógépen nyomon követheti az Azure SQL DTU a Microsoft SQL Server Management Studio rendszerben a sys.dm_resource_stats rendszernézet megtekintésével.

    - Ha szűk keresztmetszeteket talál az erőforrásoknak, hozzon létre tervet azok enyhítése érdekében. Általában a szükségesnél több erőforrás hozzárendelésével csökkentheti a szűk keresztmetszeteket. Mivel ez a számítógép a Microsoft keretén belül működik, kérelmet kell küldenie a Microsoftnak az erőforrások növelésére, ha szűk keresztmetszetként azonosítja azokat.

### <a name="run-the-majorversiondataupgradezip-package"></a>Futtassa a MajorVersiondataUpgrade.zip csomagot

Ha ez a feladat élesben történik, a műveletet a Microsoft DSE csapata végzi el. Az átállás tesztelése során azonban a fejlesztők végzik a műveletet. A feladat során a régi adatbázis-szerkezetet átalakítják az új rendszer szerkezetére.

Az adatbázis-szinkronizálási folyamat a feladat részeként fut. Az adatbázis szinkronizálása bizonyos esetekben jelentős mennyiségű időt vehet igénybe – ha például egy fürtözött index megváltozott egy táblázatban –, mivel ez a művelet költséges művelet az SQL-ben.

Hangsúlyosan javasoljuk, hogy az elemzési és hibakeresési folyamatot először fejlesztői környezetben végezze el. Védőfalkörnyezetben a hibakeresési és elemzési lehetőségek korlátozottabbak. A célaz, hogy kevés vagy semmilyen probléma ne legyen az átállási tesztelés során.

Az alábbi területeket ajánlott ellenőrizni:

- Legyen konkrét időzítése az importálási folyamathoz.
- Optimalizálja a folyamatot a leggyorsabb élmény biztosítása érdekében. Az optimalizáláshoz a következőkre lehet szükség:

    - Felügyelje az egyes frissítési parancsfájlok teljesítményét a ReleaseUpdateScriptsExecution táblán keresztül.
    - Állítsa be a parancsfájlokat a teljesítmény optimalizálása érdekében. Ez a feladat megkövetelheti a parancsfájl X ++ kód adatkészletre történő testreszabását.
    - Monitorozza az Azure SQL DTU rendszert a Microsoft Dynamics Lifecycle Services (LCS) figyelési funkciójával vagy a sys.dm_resources_stats rendszernézettel a Management Studio alkalmazásban. Ha erőforrásai a maximumon vannak, előfordulhat, hogy magasabb adatbázisszintet kell kérnie a Microsoft DSE csoporttól.

### <a name="roll-back-to-ax-2012"></a>Visszaállás az AX 2012 rendszerre

A feladat célja az adatbázis visszaállítása a biztonsági mentés segítségével, amely az AX 2012 kikapcsolt állapotában készült, majd az AX 2012 újbóli elindítása. Megtörténhet, hogy az integrált rendszereket is vissza kell állítani. Mivel azonban az integrált rendszerek vállalkozásonkánt eltérőek lehetnek, ettől függetlenül, a saját konkrét körülményei alapján kell megterveznie ezt a forgatókönyvet. Annak ellenére, hogy nem valószínű, hogy szükség lesz visszaállításra, nagyon fontos, hogy legyen tesztelt folyamata abban az esetben, ha ez mégis szükségessé válik.

## <a name="functional-workstream"></a>Funkcionális munkafolyamat

Az adatfrissítés után számos beállítási feladat lesz az új környezetben. A munkafolyamat célja az összes konfigurációs feladat dokumentálása és mennyiségi meghatározása, valamint egy erőforrás hozzárendelése annak biztosítása érdekében, hogy ezek a feladatok a technikai munkafolyamattal együtt a leállási időben elvégezhetők legyenek.

A funkcionális feladatok jellemzően az adott rendszerparaméterek vagy más konfigurációs adatok értékének megváltoztatásával járnak. Ezeket a feladatokat a teljes funkcionális teszten keresztül azonosítják, amely az átállási teszteléstől különálló tevékenység. Ha egy ilyen típusú feladatot azonosít, azt a funkcionális erőforrással és a fejlesztővel együtt kell felülvizsgálni.

Nagyobb módosítások előfordulhat, hogy szükség lesz egy új egyéni adatfrissítési parancsfájl írására az adatok frissítése érdekében az adatfrissítési folyamat során. Azonban a funkcionális erőforrás manuálisan kisebb változtatásokat futtathat az új rendszeren keresztül az adatfrissítés után.

Az új adatfrissítési parancsfájlok nagyobb módosításait meg kell vizsgálni. Ezért futtatni kell a MajorVersionDataUpgrade.zip csomag egy vagy több további ismétlését. Fontos, hogy mérlegelje a csomag újrafuttatásának költségeit a kézi adatbevitel költségével szemben.

Minden manuális módosítás esetén egy feladatot kell hozzáadni az átállási tervezési dokumentumhoz. A feladatban a következő adatoknak kell megjelenniük:

-   Mi a feladat, és mit kell tenni?
-   Ki kell ezt megtennie?
-   Mennyi ideig tart?

