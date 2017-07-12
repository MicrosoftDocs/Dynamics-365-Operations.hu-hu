---
title: "A Microsoft Dynamics AX 2012 frissítése Dynamics 365 for Finance and Operations Enterprise Edition rendszerre"
description: "Ez a téma azt a folyamatot írja le, amelyet a Microsoft Dynamics AX 2012 rendszert futtató ügyfelek használhatnak adataik és kódjaik Microsoft Dynamics 365 for Finance and Operations Enterprise edition rendszerre történő áthelyezésére."
author: tariqbell
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Developer, IT Pro
ms.reviewer: margoc
ms.search.scope: Operations Platform
ms.search.region: Global
ms.author: tabell
ms.search.validFrom: 2017-06-16
ms.dyn365.ops.version: Platform update 8
ms.translationtype: Human Translation
ms.sourcegitcommit: 6816e3820ab77c71bbf9bde4a068375448331671
ms.openlocfilehash: 13507fcf9c0d626709aeb4e00a8632411204c20f
ms.contentlocale: hu-hu
ms.lasthandoff: 06/15/2017

---

# <a name="upgrade-microsoft-dynamics-ax-2012-to-microsoft-dynamics-365-for-finance-and-operations-enterprise-edition"></a>A Microsoft Dynamics AX 2012 frissítése Microsoft Dynamics 365 for Finance and Operations Enterprise Edition rendszerre

[!include[banner](../includes/banner.md)]

A Microsoft Dynamics 365 for Finance and Operations Enterprise edition 8. platformfrissítése frissítési útvonalat biztosít a Microsoft Dynamics AX 2012-es verzióját használó ügyfelek számára adataik és kódjaik Finance and Operations programba történő áthelyezésére. A frissítési folyamat a következő elemekre épül:

- Az AX 2012 rendszerből származó meglévő egyéni alkalmazáskód kiemelését segítő eszközök.
- Az adatfrissítési folyamat, amellyel az adatbázist továbbíthatja. Ezzel a teljes tranzakciós előzményeket frissítheti.

## <a name="overview"></a>Áttekintés

A frissítési folyamat három átfogó fázisban jeleníthető meg: Elemzés, Végrehajtás és Ellenőrzés.

A következő ábra bemutatja a végponttól végpontig terjedő frissítési folyamatot, valamint az egyes fázisok részét képező tevékenységeket. 

![Frissítési folyamat](./media/upgrade-process.png)

## <a name="analyze"></a>Elemzés

Az Elemzés fázisban végzett tevékenységek segítenek megbecsülni a frissítéshez szükséges ráfordítást. Segítséget nyújtanak a projekttervet készítésében is. Ezeket a tevékenységeket a Finance and Operations megvásárlása előtt elvégezheti. Segítenek abban, hogy megalapozott vásárlási döntést hozzon létre megadva egy adatpontot a szükséges ráfordításról és erőforrásokról.

### <a name="sign-up-for-a-public-preview-in-lcs"></a>Regisztráljon egy nyilvános előnézetre az LCS-ben

A Finance and Operations beszerzése előtt az Elemzés tevékenységeinek elvégzésére regisztrálhat egy nyilvános előnézetre. A nyilvános előnézet lehetővé teszi a saját Finance and Operations környezetek telepítését. Ezenkívül hozzáférést biztosít a Microsoft Dynamics Lifecycle Services (LCS) eszközeihez, amelyek az AX 2012 környezet és a meglévő egyéni kódjának értékelésére szolgálnak.

Ha van egy meglévő LCS-projektje AX 2012 rendszeren, továbbra is regisztrálnia kell egy további új projekthez a Finance and Operations értékeléséhez.

Az ügyfelek nyilvános előnézetének módjáról itt kap tájékoztatást: https://mbs.microsoft.com/customersource/global/AX/news-events/news/Microsoft_Dynamics_AX_Public_Preview.

A partnerek nyilvános előnézetének módjáról itt kap tájékoztatást: https://mbs.microsoft.com/customersource/global/AX/news-events/news/Microsoft_Dynamics_AX_Public_Preview.

Ne feledje, hogy ez a nyilvános előnézet eltér a [30 napos próbaverziótól](https://aka.ms/D365OperationTrials). A harmincnapos próbaverziók a Finance and Operations olyan telepített példányát teszik elérhetővé, amelynek segítségével fel tudja fedezni és értékelni tudja az alkalmazást. Azonban az Elemzés tevékenységekhez a teljes LCS-tapasztalat és -eszközök szükségesek.

### <a name="select-the-upgrade-methodology"></a>Frissítési módszertan kiválasztása
Az új LCS-projektben állítsa a projekt módszertanát **AX 2012 frissítése a Dynamics 365 for Operations rendszerre** lehetőségre. Ez a módszer kifejezetten az AX 2012 rendszert használó, frissíteni kívánó ügyfeleknek van szánva. Leírja részletesen a három fázist, és hivatkozásokat tartalmaz a folyamattal kapcsolatos összes alátámasztó dokumentumokhoz.

![Frissítési módszertan(./media/methodology.png)
 
### <a name="run-the-upgrade-analyzer"></a>A frissítési elemző futtatása
A frissítési elemzőeszköz az AX 2012-környezetre vonatkozóan fut, és meghatározza azokat a feladatokat, amelyeket az AX 2012 környezet előkészítéséhez meg kell tennie a frissítés egyenletesebb és kisebb költséggel járó végrehajtása érdekében:

- **Adatok törlése** – Ez a folyamat segít azonosítani azokat az adatokat, amelyeket működésképtelenné válás nélkül eltávolíthat. Az eszköz azonosítja azokat a különböző típusú adatokat, amelyeket csökkenthet egy karbantartási folyamat futtatásával. Mindegyik adattípushoz tartozik egy magyarázat a tisztítás hatásáról. Ezután eldöntheti, hogy futtatja-e a törlési folyamatot. A Finance and Operations rendszer előfizetésének egyik része az adatbázisméreten alapul. Ezért a méret csökkentésével csökkenti az előfizetési költség ezen összetevőjét, és egyben csökkenti a frissítési élesítési folyamatához szükséges időt. A kisebb adatbázis gyorsabb frissítést biztosít.
- **SQL-konfiguráció** – Ez a folyamat áttekinti az SQL-konfigurációt, és optimalizálásokat javasol. Azáltal, hogy biztosítja az SQL optimális működését, ez az eljárás segít csökkenteni a frissítés élesítési folyamatához szükséges időt.
- **Elavult funkciók** – Ez a folyamat azonosítja a jelenleg használt funkciókat, amelyek azonban nem érhetők el a Finance and Operations rendszerben. Ezért a folyamat segít a funkcióbeli hiányosságok korai felismerésében. Javaslatokat kínál alternatívákra is.

Ezenkívül a lépés részeként telepítenie kell KBXXXXXXX programot AX 2012 környezetben. Ez a gyorsjavítás frissítés előtti ellenőrzőlistát tartalmaz. Az AX 2012 környezetben ezt az ellenőrzőlistát arra használhatja, hogy bevigye a frissítési eljáráshoz szükséges adatokat. Például egy frissítés előtti ellenőrzőlista-feladat esetén megadhatja a Microsoft Azure Active Directory (Azure AD) bejelentkezési adatait minden aktuális AX 2012-felhasználó számára, így minden felhasználó be tud jelentkezni a Finance and Operations rendszerbe.

Ezen lépés kimenete az AX 2012 rendszerben a rendszergazdák frissítési projekttervében a munkafolyamat lesz.

További tudnivalókért lásd: [Elemzés: Használja a frissítési elemzőt az áttelepítési munka megtervezéséhez](upgrade-analyzer-tool.md).

### <a name="run-the-code-upgrade-estimation-tools"></a>A kódfrissítési becslések eszközök futtatása
Ez a lépés az AX 2012 rendszerből származó kódot veszi át, az új formátumra alakítja, és a visszajelzést nyújt azon ütközésekről, amelyeket a fejlesztőnek később meg kell oldania. Ez a lépés képezi a kódfrissítés költségének becslését.

Ennek a lépésnek a végrehajtásához modelltárként kell exportálni a kódot az AX 2012 rendszerből, majd feltölteni az LCS Kódfrissítés eszközébe. A Kódfrissítés eszköz a kód frissített verzióját hozza létre, valamint jelentést készít a fennmaradó és megoldandó ütközésekről. A fejlesztői ellenőrizheti a frissített kódot és a jelentést, hogy meghatározza a kódállomány frissítéséhez szükséges ráfordítást.

Ezen lépés kimenete a Microsoft Dynamics AX rendszer fejlesztők frissítési projekttervében szereplő munkafolyamatot képviseli.

További tudnivalókért lásd: [Elemzés: a kód frissítéséhez szükséges ráfordítás megbecsülése](analyze-code-upgrade.md).

### <a name="deploy-a-demo-environment"></a>Bemutatókörnyezet telepítése
A bemutatókörnyezetek olyan alapértelmezett környezetek, amelyek bemutató (nem saját) adatokat és a szabványos kódot (testreszabás nélkül) tartalmaznak. Azt ajánljuk, hogy telepítse a bemutatókörnyezetet az új funkciók értékeléséhez és azon folyamatok alapvető igazítási hiányelemzésének elvégzéséhez, amelyek használatosak az AX 2012 rendszerben, de módosulhattak a Finance and Operations rendszerben. A bemutatókörnyezeteket az Azure rendszeren telepítheti vagy letölthető őket virtuális gépként (VM), amelyet a saját hardverén futtat. Ha az Azure-rendszerben telepíti őket, meg kell adnia Azure-előfizetését, mert továbbra is egy nyilvános előnézeti projektet használ, és még nem vásárolt Finance and Operations előfizetést.

Ezen lépés kimenete a funkcionális felhasználók vagy az üzleti felhasználók frissítési projekttervében szereplő munkafolyamatot képviseli.

További tudnivalókért lásd: [Elemzés: Védőfalkörnyezet telepítése](analysis-sandbox.md)

### <a name="create-a-project-plan"></a>Projektterv létrehozása
A frissítés módszertan tartalmaz egy projekttervezési sablont. Ebben a lépésben az Elemzés szakasz előző lépéseinek kimenetét használjuk a frissítési projekt projekttervének kitöltésére. A projektterv az ellenőrzés minden részletét tartalmazza: adatfrissítés tesztelése, átállási tesztelés, a funkcionális teszthez „megfelelt” ismétlései, valamint az ezekhez a feladatokhoz szükséges különböző erőforrás-hozzárendelésekkel kapcsolatos részleteket.

Ebben a szakaszban a projektterv egy adatpontot hoz létre, amely segít megérteni azt az idő- és költségbefektetést, amely a Finance and Operations rendszerre történő frissítéssel jár.

## <a name="execute"></a>Végrehajtás
A Végrehajtás fázisban végighalad az Elemzés fázisában eltervezett feladatokon. A Végrehajtás szakaszra történő lépéshez meg kell vásárolnia a Finance and Operations rendszert, és rendelkeznie kell mindazon elérhető erőforrásokkal, amelyek a frissítéshez szükségesek.

### <a name="switch-to-the-lcs-implementation-project"></a>Váltás az LCS végrehajtási projektre
Az Elemzés szakaszban használt nyilvános előnézeti projekt célja megvalósult. Most elvetheti azt. A fennmaradó lépésekhez csak az Elemzés szakasz utolsó lépésében létrehozott projektterv szükséges.

Finance and Operations előfizetés megvásárlásakor információkat kap arról, hogyan regisztrálhat egy új LCS projekthez. Ez a projekt végrehajtási projektként ismert, és ez lesz az előfizetés új állandó LCS projektje, amíg rendelkezik az adott előfizetéssel. Ez a projekt abban különbözik a nyilvános előnézeti projekttől, hogy ezt a Microsoft kezeli. Ezért ez a projekt a következő jellemzőkkel rendelkezik:

- A projekt minden környezetét az Azure üzemelteti.
- A projekthez társított Azure-előfizetést a Microsoft kezeli. Emiatt az Azure-költségeket nem számlázzák külön. A költségeket a Finance and Operations előfizetése fedezi.
- A projekt termelési környezetét a Microsoft kezeli. Ezért a kódtelepítéseket, a frissítéseket és az infrastruktúra karbantartását közvetlenül a Microsoft futtatja, nem az ön munkatársai. 

### <a name="perform-the-ax-2012-preparation-tasks"></a>Az AX 2012 előkészítő feladatok végrehajtása
Hajtsa végre a frissítési elemzőeszköz által felismert és a frissítési projektterv leírásában szereplő műveleteket. Ezeket a feladatokat a Microsoft Dynamics AX rendszergazdájának és adatbázis-rendszergazdának (DBA) kell végrehajtania.

[Adatfrissítés AX 2012 rendszerről Dynamics 365 for Operations rendszerre – Frissítés előtti ellenőrzőlista AX 2012 rendszerben](prepare-data-upgrade.md)

### <a name="perform-code-upgrade"></a>Kódfrissítés végrehajtása
Végezze el az Elemzés szakasz kódfrissítési becslési lépése alatt tervezett feladatokat. Ezeket a feladatokat a fejlesztőknek kell futtatniuk.

Ettől kezdve az AX 2012 rendszerben történő kódmódosításokat be kell fagyasztani. Az AX 2012 rendszerben csak a sürgősségi kódmódosításokat lehet engedélyezni. Módosítás esetén manuálisan kell átvinni az új kódállományba.

### <a name="develop-new-code"></a>Új kód készítése
Hajtsa végre az Elemzés fázis „Bemutatókörnyezet telepítése” során végrehajtott igazítási hiányelemzés feladatait. Ezek a feladatok valószínűleg olyan funkcionális feladatok kombinációi, amelyek meghatározzák azokat a testreszabási konfigurációs és fejlesztési feladatokat, amelyek a felhasznált új funkciókhoz kapcsolódnak.

### <a name="data-upgrade-development-environment"></a>Adatfrissítés (fejlesztői környezet)
A kódfrissítési feladatok után első alkalommal frissítheti az AX 2012 adatbázist a Finance and Operations rendszerre. Ez az első frissítés fejlesztői környezetben történik, így könnyebben orvosolhatja vagy háríthatja el az ebben a szakaszban talált problémákat. Fejlesztői környezetben a probléma azonnal elhárítható, a kód módosítható, és a frissítés perceken belül futtatható. A nagyobb védőfalkörnyezetek nem nyújtják ezt a gyorsaságot, és legalább néhány órának kell eltelnie a problémák elhárításához és helyreállításához, a kód frissítéséhez, a frissített kód telepítéséhez és a frissítés újbóli futtatásához.

Az alábbi ábra bemutatja a folyamatot. Készítsen biztonsági másolatot az AX 2012 adatbázisról, töltse fel az Azure-rendszerbe, állítsa vissza a Finance and Operations környezetbe, majd futtassa az adatfrissítést.

![Adatfrissítés fejlesztői környezetben](./media/data-upgrade-dev.png)
 
Az adatfrissítés egy speciális telepíthető csomag futtatásával történik. Ugyanez a mechanizmus használatos az új Finance and Operations kód egyik környezetből másik környezetbe történő telepítésekor.

Az adatbázisban az adatoknak a folyamat során történő konvertálásához használt alapul szolgáló keretrendszer nagyjából megegyezik az AX 2012 rendszer frissítési keretrendszerével, amely **ReleaseUpdatexxx** osztályokat futtató X ++ kötegfeladatokon alapulnak.

A részleteket lásd: [Adatfrissítés az AX 2012 rendszerről a Dynamics 365 for Operations rendszerre fejlesztői környezetben](data-upgrade-2012.md).

### <a name="data-upgrade-sandbox-environments"></a>Adatfrissítés (védőfalkörnyezetben)
Az adatfrissítés fejlesztői környezetben történő befejeződése után ugyanaz a folyamat védőfalkörnyezetben is futtatható. A védőfalkörnyezet az a környezet, ahol üzleti felhasználók és a funkcionális csapat tagjai a frissített AX 2012-adatok és kódok használatával tesztelhetik az üzleti folyamatokat.

Az alábbi ábra a védőfalkörnyezetben történő adatfrissítés futtatását mutatja be. A különbség az, hogy a hagyományos SQL biztonsági másolat helyett egy bacpac eszköz használatos. Az eszközre szükség van a Microsoft SQL Server és az Azure SQL Database adatbázis közötti konvertálás érdekében. Szabványos SQL-eszköz, és nem a Finance and Operations saját eszköze.

![Adatfrissítés védőfalkörnyezetben](./media/data-upgrade-sandbox.png)

A részleteket lásd: [Adatfrissítés az AX 2012 rendszerről a Dynamics 365 for Operations rendszerre védőfalkörnyezetben](upgrade-data-sandbox.md).
 
## <a name="validate"></a>Ellenőrzés
Amikor belép az Ellenőrzés szakaszba, olyan környezetek lesznek elérhetők, amelyek tartalmazzák a frissített egyéni kódot és a frissített adatokat. Ez a szakasz leírja azt az ellenőrzési és tesztelési folyamatot, amely biztosítja a frissített környezet elvárt működését. Bemutatja az élesítés előkészítési folyamatát is.

### <a name="perform-cutover-testing-and-create-a-cutover-plan"></a>Átállási teszt végrehajtása és átállási terv létrehozása
Az _átállás_ kifejezést itt az új rendszer élesítését lehetővé tevő végső folyamat leírására használjuk. Ez a folyamat az AX 2012 kikapcsolása után és a Finance and Operations bekapcsolása előtt bekövetkező feladatokból áll. 

A vizsgálat célja az átállási folyamat gyakorlása. Ezzel zökkenőmentes élményt nyújthat mindazoknak, akik a tényleges átállás élesítése során érintettek.

Két fő munkafolyamat van:

- **Technikai munkafolyamat** – Ez a munkafolyamat az adatfrissítési folyamat. A vállalkozása korlátozza az engedélyezett leállási idő küszöbértékét. A leállás során sem az AX 2012, sem a Finance and Operations nem lesz elérhető. Megtörténhet, hogy a technikai munkafolyamatnak finomhangolnia kell kell az adatfrissítési eljárás teljesítményét a vállalat leállási ideje küszöbértékének megfelelően. 
- **Funkcionális munkafolyamat** – Az adatok frissítése után a Finance and Operations környezetben több konfigurációs műveletet kell elvégezni. Mindezeket a feladatokat dokumentálni kell és számszerűsíteni kell, és egy erőforrást kell hozzájuk rendelni, mivel be kell illeszkedniük a technikai munkafolyamatokkal együtt a vállalkozás leállási idejébe.

Részletekért lásd: 
- [Érvényesítés: Átállási tesztelés](upgrade-cutover-testing.md)
- [Ellenőrzés– Alkalmazás-ellenőrzési folyamat](app-validation-process.md)

### <a name="functional-test-pass"></a>Sikeres funkcionális tesztelés
Töltsön ki az összes üzleti folyamatban egy teljes sikeres funkcionális tesztet. Ez a teszt a Finance and Operations rendszert érintő üzleti folyamatok sikeres kiterjedt újraellenőrzése lesz. Ezek az üzleti folyamatok magukban foglalják az AX 2012 rendszerből származtatott régi folyamatokat és az új funkciókat tartalmazó új folyamatokat, amelyeket először a Finance és Operations programban vettek fel. 

A kód minőségétől függően a probléma megoldásához és az újbóli teszteléshez a sikeres funkcionális teszt több ismétlésére lehet szükség. Egy hiba kijavítása után tesztelje újból a résztvevő összes folyamatot annak biztosítása érdekében, hogy az alsóbb vagy a felsőbb rétegbeli folyamatot ne érintse a módosítás.

A részleteket lásd: [Ellenőrzés: funkcionális tesztelés](upgrade-functional-validation.md).

### <a name="pre-go-live-checklist"></a>Élesítés előtti ellenőrzőlista
Az élesítés előtti ellenőrzőlista javasolt eljárás, amely segít a végleges átállás során fellépő hibák esélyének csökkentésében. Az élesítés előtt egy héttel hagyja abba az AX 2012 rendszer konfigurációs módosításait (a \<modul\>\Beállítás pontban). A konfigurációs módosítások korlátozása pusztán az eljárással kapcsolatos. A Microsoft Dynamics AX rendszergazdák elfogadják, hogy az ilyen típusú módosításokat ezen a ponton várakoztassák.

Javasoljuk, hogy fagyassza be a kódmódosításokat is a Finance and Operations kódállományában. További módosítások nem engedélyezhetők, hacsak nem értékelték ezeket, amelyből kiderült, hogy nem blokkolnák az élesítést.  

A konfigurációs korlátozás és a kódmódosítás befagyasztása után az adatfrissítést utoljára futtatni kell az átállás előtt. Ezzel a módszerrel biztos lehet benne, hogy minden továbbra is az elvárt módon működik. 

Részletekért lásd: [Érvényesítés: Előkészítés élesítésre](upgrade-go-live-prep.md).



### <a name="supported-upgrade-paths"></a>Támogatott frissítési útvonalak
2017 júniusától a Microsoft Dynamics 365 for Finance and Operations Enterprise edition 0617-es verziójáról történő frissítést a Microsoft Dynamics AX 2012 R3 támogatja. A rendszer támogatja az AX 2012 R3 minden kumulatív frissítését (CU).

A Microsoft Dynamics AX 2012 R2 és a Microsoft Dynamics AX 2012 eredeti verziója jelenleg nem támogatott. A támogatás 2017-ben később jelenik meg.

Csak a Finance and Operations felhőalapú verziójára történő frissítés támogatott. A helyszíni verzióra történő frissítés nem támogatott. A helyszíni verzióra történő frissítés támogatása 2017-ben később jelenik meg.

