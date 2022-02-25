---
title: Skálázási egységek elosztott hibridtopológiában
description: Ez a témakör további információt biztosít a Felhőalapú és peremhálózati skálázási egységgel kapcsolatban a gyártási és raktárkezelési munkaterhelésekhez.
author: cabeln
ms.date: 04/22/2021
ms.topic: article
ms.search.form: ScaleUnitWorkloadsWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: cabeln
ms.search.validFrom: 2021-04-13
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: ef81ef7ad726ebe0cc6a0acd58cb68d07e222a42
ms.sourcegitcommit: 0d14c4a1e6cf533dd20463f1a84eae8f6d88f71b
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/14/2022
ms.locfileid: "8119187"
---
# <a name="scale-units-in-a-distributed-hybrid-topology"></a>Skálázási egységek elosztott hibridtopológiában

[!include [banner](../includes/banner.md)]

> [!IMPORTANT]
> A Microsoft Dynamics 365 Supply Chain Management skálázási egysége a szolgáltatás használatát szabályozó feltételekkel érhető el az Ön számára. A további tudnivalókat lásd: [Microsoft Dynamics Jogi információk](https://go.microsoft.com/fwlink/?LinkID=290927).
>
> A felhő- és peremhálózati egységek engedélyezésekor meg kell erősítenie, hogy megértette, hogy a felhő- és peremhálózati egységek konfigurálásához és feldolgozásához kapcsolódó egyes adatokat az Egyesült Államokban található adatközpontban lehet tárolni. Ha további információkat szeretne megtudni a felhő- és szélskálázi egységek adatainak feldolgozásával kapcsolatban, tekintse meg az [Adatfeldolgozás a skálázási egységek kezelése során](#data-processing-management) témakör későbbi részét.

## <a name="core-value-proposition-for-a-distributed-hybrid-topology"></a>Elosztott hibridtopológia alapvető értékajánlata

A gyártással és elosztással foglalkozó vállalatoknak képesnek kell lenniük a kulcsfontosságú üzleti folyamatok futtatására nonstop, megszakítás nélkül és megfelelő méretben. Az elosztott hibridtopológia lehetővé teszi a vállalatok számára, hogy megszakítás nélkül futtassák a kulcsfontosságú feladathoz kapcsolódó termelési és raktári folyamatokat, még akkor is, ha időnként hálózati kapcsolati vagy késleltetési problémák lépnek fel.

Az elosztott hibridtopológia bemutatja a *skálázási egységek* fogalmát, amely lehetővé teszi az üzletek és raktárak végrehajtási terhelésének elosztását a különböző környezetekben. Ez a funkció javítja a teljesítményt, megakadályozhatja a szolgáltatás megszakadását, és maximalizálhatja az üzemidőt. A skálázási egységek a Supply Chain Management előfizetés következő bővítményei révén biztosítottak:

- Felhőbeli skálázási egység bővítmény a következőhöz: Dynamics 365 Supply Chain Management
- Peremhálózati skálázási egység bővítmény a következőhöz: Dynamics 365 Supply Chain Management

A számítási feladat képességei folyamatosan kerülnek kiadásra a növekményes fejlesztésekkel.

## <a name="scale-units-and-dedicated-workloads"></a>Skálázási egységek és dedikált számítási feladatok

A skálázási egységek kiterjesztik a központi Supply Chain Management központ környezetét a dedikált feldolgozási kapacitás hozzáadásával. A skálázási egységek futhatnak a felhőben. Alternatív megoldásként a helyszíni létesítmény peremhálózatán is futhatnak.

:::image type="content" source="./media/cloud_edge-HeroDiagram.png" alt-text="Dynamics 365 skálázási egységekkel.":::

A skálázási egységek biztosítják a hozzárendelt munkaterhelések ellenállóképességét, megbízhatóságát és skálázását. A Peremhálózati skálázási egységek ideiglenesen leválaszthatók a felhőközponti környezetről, és a dolgozók továbbra is a peremhálózaton maradhatnak a hozzárendelt számítási feladatban.

A *számítási feladat* egy meghatározott üzleti funkciókészlet, amelyet figyelembe lehet venni, és egy skálázási egységre delegálható. Bár a raktárkezelés számítási feladata ki van adva, a gyártásvégrehajtás számítási feladata még előzetes verzióban van.

Konfigurálhatja a központi környezetet és a felhőbeli skálázási egységet a kiválasztott számítási feladathoz a [Scale Unit Manager portál](https://sum.dynamics.com) használatával. Egy skálázási egységhez több számítási feladatot is hozzárendelhet. Az aktuális verzióban a felhőbeli skálázási egységek előfeltételeivel és korlátozásokkal kapcsolatos tudnivalókat lásd a későbbi [Felhőbeli skálázási egységekre vonatkozó előfeltételek és korlátozások](#cloud-scale-unit-prerequisites) című témakörben.

### <a name="dedicated-warehouse-management-workload-capabilities-in-a-scale-unit"></a>Dedikált raktárkezelési számítási feladatok képességei egy skálázási egységben

A raktárkezelési terhelés lehetővé teszi a raktári műveletek átméretzását és futtatását olyan környezetben, ahol különálló karbantartási ablakok vannak használatban. A raktárkezelési terhelés támogatja a legtöbb nagyvállalati raktárkezelési folyamatot. További információk: [Raktárkezelés munkaterhelései felhőalapú és peremhálózat-lépték szerinti egységekhez](cloud-edge-workload-warehousing.md).

### <a name="dedicated-manufacturing-execution-workload-capabilities-in-a-scale-unit"></a>Dedikált gyártási végrehajtási számítási feladatok képességei egy skálázási egységben

A gyártási terhelés a következő lehetőségeket biztosítja:

- A gépkezelők és az üzemirányítók hozzáférhetnek az üzemeltetési termelési tervhez.
- A gépkezelők diszkrét és folyamatgyártási feladatok futtatásával naprakészen tarthatják a tervet.
- Az üzemvezető módosíthatja az üzemeltetési tervet.
- A dolgozók hozzáférhetnek a munkaidőhöz és a jelenléthez a peremhálózati érkezéskori és távozáskori blokkoláshoz a megfelelő dolgozói fizetésszámítás biztosítása érdekében.

További információk: [Gyártási végrehajtás munkaterhelései felhőalapú és peremhálózat-lépték szerinti egységekhez](cloud-edge-workload-manufacturing.md).

## <a name="considerations-before-you-enable-the-distributed-hybrid-topology-for-supply-chain-management"></a>Szempontok a Supply Chain Management osztott, hibrid topológiájának engedélyezése előtt

Az osztott, hibrid topológia engedélyezésével a Supply Chain Management felhőkörnyezetét úgy lehet átváltani, hogy központként működjön. További olyan környezeteket is társíthat, amelyek skálázási egységként vannak konfigurálva a felhőben vagy a peremen.

### <a name="prerequisites-and-limitations-for-cloud-scale-units"></a><a name="cloud-scale-unit-prerequisites"></a>Előfeltételek és korlátozások a felhőalapú skálázási egységekhez

A skálázási egységek jelenlegi kiadásakor egyes funkciók még nem érhetők el, de idővel a növekményes kiadásokban is hozzáadhatóak.

#### <a name="you-must-be-a-licensed-customer-of-supply-chain-management"></a>Supply Chain Management licencelt vevőnek kell lennie

Ahhoz, hogy előkészüljön az osztott topológiába, Supply Chain Management licenccel kell rendelkeznie. A meglévő felhőkörnyezet a hibrid topológia központja lesz. A tesztkörnyezeteket és működési környezeteket is központi környezetként adhat meg, és a beszerzett bővítményeknek megfelelően skálázhatja az egységeket.

#### <a name="your-existing-project-must-be-administered-via-the-global-commercial-version-of-lcs"></a>A meglévő projektet az LCS globális kereskedelmi verzióján keresztül kell adminisztrálni

A meglévő Microsoft Dynamics Lifecyle Services (LCS) projektnek meg kell felelnie a következő verziókövetelményeknek:

- A projektet az LCS globális kereskedelmi verzióján keresztül kell adminisztrálni, a [lcs.dynamics.com](https://lcs.dynamics.com) weboldalon.
- Az LCS helyi verziói (például az [eu.lcs.dynamics.com](https://eu.lcs.dynamics.com) és a [fr.lcs.dynamics.com](https://fr.lcs.dynamics.com)) nem támogatottak.
- Az LCS kormányzati felhőverziói nem támogatottak.
- Az LCS Mooncake verziója nem támogatott.

#### <a name="your-current-production-environment-must-be-of-the-self-service-type-in-lcs"></a>A jelenlegi működési környezetnek önkiszolgáló típusúnak kell lennie az LCS szolgáltatásban

A jelenlegi működési környezetnek **Önkiszolgáló** típusúnak kell lennie az LCS szolgáltatásban. Ez a típus azt jelzi, hogy az LCS-projekt bérlőjét már konvertálták, hogy az támogassa az Azure Service Fabric tárhelymodellt.

> [!IMPORTANT]
> A szolgáltatott infrastruktúraként (IaaS) futtatott környezetek nem támogatottak. Ezek a környezetek általában **Microsoft által kezelt** típussal vannak megjelölve az LCS-ben. Ha ilyen típusú környezettel rendelkezik, a Microsoft kapcsolattartóval együtt kell dolgoznia az **Önkiszolgáló** típussal való áttelepítési időrendet.

A Microsoft összes Supply Chain Management felhőkörnyezetének átállása folyamatban van az IaaS-modellről a Service Fabricben tárolt topológiára. Ez az áthelyezés jobb skálázhatóságot eredményez, és megkönnyíti a szolgáltatásmenedzsmentet. Így a telepítési és karbantartási műveletek gyorsabbak. Hasonlóképpen a szolgáltatásösszetevőket a mikroszolgáltatások koncepciójának megfelelően áttelepítik, és a szolgáltatásgazda modell egy virtuális gép (VM) modellről egy könnyű tárolóra bontott architektúrára [telepíti át](/virtualization/windowscontainers/about/containers-vs-vm).

Végső soron ugyanaz a Service Fabric-alapú tárolóra bontott szolgáltatási infrastruktúra fogja működtetni a szolgáltatás felhő- és peremhálózati példányait is, attól függetlenül, hogy a példány a felhő egy központja, vagy a felhőben vagy a peremhálózaton található skálázási egység.

Ahhoz, hogy a mérlegegységeket támogató topológiába felvehető legyen, a projekt bérlőjét át kell átállás a Szolgáltatás anyaga által tárolt modellre. Ezenkívül minden központként viselkedő környezetet konvertálni kell.

> [!TIP]
> Az LCS projektbérlő állapotának lekérdezéséhez keresse meg a környezet típusát az [LCS](https://lcs.dynamics.com/) szolgáltatásban, vagy forduljon partneréhez vagy a Microsoft kapcsolattartóhoz.

#### <a name="local-business-data-on-premises-environments-arent-supported-as-hubs-for-scale-units"></a>A helyi üzleti adatok (helyszíni) környezetek nem támogatottak skálázási egységek központjaként

A helyszíni környezetek nem működnek skálázási egység központként. A központi környezeteket mindig a felhőben kell tárolni.

#### <a name="scale-unit-management-capabilities-are-limited"></a>A skálázási egység kezelési képességei korlátozottak

Korlátozottak azok a vezetői képességek, amelyek segítenek a munkaterhelések mozgásában. Egyes vezetői műveletek nem támogatottak az önkiszolgáló módban, és előfordulhat, hogy partnerétől vagy a Microsoft kapcsolattartótól kell segítséget kérnie. Ilyen lehet például a skálázási egységek közötti munkaterhelési mozgás, vagy a vészhelyzeti forgatókönyvekben az ideiglenes ad hoc mozgások.

#### <a name="metrics-and-measurements-arent-yet-available"></a>A metrikák és a mértékek még nem érhetők el

Még nem állnak rendelkezésre azok a metrikák és mértékek, amelyek segítenek kiválasztani a legjobb alkalmazást a skálázási egységekhez. A Microsoft kapcsolattartó vagy megvalósítási partner segítségével válassza ki a leginkább megfelelő alkalmazást.

### <a name="data-processing-during-management-of-scale-units"></a><a name="data-processing-management"></a>Adatfeldolgozás a skálázási egységek kezelése során

Ha engedélyezi a Dynamics 365 környezetben a felhő- és peremhálózati skálázási egységek osztott, hibrid topológiáját, néhány kezelő szolgáltatás az LCS esetében is csak az Egyesült Államokban működik. Ez a viselkedés befolyásolja a [Scale Unit Manager portál](https://sum.dynamics.com) által használt egyes adminisztratív és konfigurációs információk átvitelét és tárolását. Íme néhány példa:

- A bérlőnevek és azonosító
- Az LCS projektazonosítókra
- A bejelentkezéshez használt rendszergazdai és projekttulajdonos e-mail-címek
- A központ és a skálázási egységek környezeti azonosítói
- Számítási feladat konfigurációk, beleértve a jogi személyek és létesítmények nevét és fizikai címét, hogy a topológia megjeleníthető legyen egy földrajzi leképezésben
- A térképelemzési lapon megjelenő összegyűjtött metrikák (például a késés és az átviteli sebesség) segítik a skálázási egységek legelőnyösebb használatának kiválasztását

Az egyesült államokbeli adatforrásba továbbított és abban tárolt adatok a Microsoft adatmegőrzési irányelveinek megfelelően törlődnek. Az Ön adatainak védelme fontos a Microsoft számára. További információért olvassa el [adatvédelmi nyilatkozatunkat](https://go.microsoft.com/fwlink/?LinkId=521839).

## <a name="onboarding-in-two-stages"></a>Két fokozatban történő előkészítés

Az osztott, hibrid topológiába való előkészítés két fokozatban történik. Az első fokozatban ellenőrizni kell a testreszabásokat annak érdekében, hogy működjenek abban az osztott topológiában, amely rendelkezik skálázási egységekkel. A teszt- és termelési környezetek csak a második fokozatban lesznek áttelepítve.

### <a name="stage-1-evaluate-customizations-in-one-box-development-environments"></a>1. fokozat: A testreszabások kiértékelése különálló fejlesztői környezetekben

A teszt- vagy működési környezetek előkészítése előtt ajánlott a skálázási egységek egy fejlesztői beállításban, például egy különálló környezetben (más néven 1. szintű környezetben) ellenőrizni, hogy érvényesíteni tudja a folyamatokat, a testreszabásokat és a megoldásokat. Ebben a fokozatban az adatok és a testreszabások alkalmazva lesznek a különálló környezetekre. Az egyik környezet a központ szerepét, a másik a skálázási egységek szerepét veszik át. Ez a beállítás a legjobb lehetőség a problémák azonosításához és megoldásához. A legutolsó korai hozzáférés (PEAP) build is használható ennek a fokozatnak a befejezéséhez.

Az 1. fokozatban a [skálázási egység telepítési eszközöket egy különálló fejlesztői környezetekben](https://github.com/microsoft/SCMScaleUnitDevTools) kell használni. Ezekkel az eszközökkel központi és skálázási egységeket konfigurálhat egy vagy két különálló környezetben. Az eszközök bináris kiadásként és forráskódként érhetők el a GitHubban lévő adatforrásban. A projekt wiki tanulmányozása, amely tartalmazza az eszközök használatáról szóló [Használati útmutató lépésről lépésre](https://github.com/microsoft/SCMScaleUnitDevTools/wiki/Step-by-step-usage-guide) részt.

### <a name="stage-2-acquire-add-ins-and-deploy-in-your-sandbox-and-production-environments"></a>2. fokozat: Bővítmények beszerzése és üzembe helyezése a teszt és működési környezetekbe

Ahhoz, hogy az új topológiába felvehető legyen az egyik teszt- vagy termelési környezet, egy vagy több felhő skálázási egységhez (illetve a peremhálózati skálázási egységekhez) kell bővítményeket szerezni. A bővítmények megfelelő projekt- és környezeti réseket fognak engedélyezni az [LCS](https://lcs.dynamics.com/) szolgáltatásban, hogy telepíteni lehessen a skálázási egység környezeteket.

> [!NOTE]
> A skálázási egység bővítmények nincsenek összekapcsolva korlátozott számú felhasználókkal, a meglévő előfizetéssel bármelyik felhasználó használhatja őket – a rendszergazda által hozzárendelt szerepkörök alapján.

A skálázási egységek több raktározási egységben (SKU-k) és árképzési lehetőségekben fel vannak ajánlva. Tehát kiválaszthatja azt a beállítást, amely a legjobban megfelel a tervezett havi tranzakciómennyiségének és teljesítménykövetelményének.

A belépési szintű termékváltozatot *Alapszintűként*, a jobban teljesítő termékváltozatot pedig *Standardként* ismerheti. Minden egyes termékváltozat előre betöltődik a meghatározott számú havi tranzakciókkal. A havi tranzakció költségvetését azonban növelheti úgy, hogy minden egyes termékváltozathoz hozzáad egy kerettúllépés bővítményt.

:::image type="content" source="media/SKUs-highlevel.png" alt-text="Bővítmények a felhőbeli skálázási egységekhez.":::

> [!TIP]
> Az igényeknek leginkább megfelelő méret azonosítása érdekében működjön együtt partnerével és a Microsofttal, és ismerkedjen meg a szükséges havi tranzakciómérettel.

Az egyes skálázási egység bővítmények beszerzése nem csak havi tranzakciómennyiséget ad, hanem adott számú környezeti tárolót is az LCS-ben. Minden egyes felhő skálázási egység bővítményénél jogosult egy új üzemelési pontra és egy új tesztkörnyezetre. Az előkészítési folyamat során a rendszer egy új LCS-projektet ad hozzá, amely ezeket a pontokat fogja tartalmazni. A pontok használati jogosultsága úgy van kötve, hogy a pontokat olyan skálázási egységekként kell használni, amelyek felhőközponttal rendelkeznek.

A kerettúllépés bővítmények nem jogosítják fel új környezeti pontokra.

Ha több tesztkörnyezetet szeretne beszerezni, akkor további normál tesztkörnyezet-pontot vásárolhat. A Microsoft ezután segít Önnek engedélyezni ezeket a pontokat a hibrid tipológia tesztkörnyezeti skálázási egységeiként.

## <a name="onboard-to-the-distributed-hybrid-topology-for-supply-chain-management"></a>A Supply Chain Management osztott, hibrid topológiába való felvétele

### <a name="select-your-lcs-project-tenant-and-the-detailed-onboarding-process"></a>Válassza ki az LCS-projekt bérlőjét és a részletes felvételi folyamatot

Miután megtervezte, hogyan fog előkészülni az osztott, hibrid topológiára a Supply Chain Management esetében, a [Scale Unit Manager portált](https://aka.ms/SCMSUM) fogja használni a felvételi folyamat megkezdéséhez. A portálon válassza ki a **Dynamics 365 bérlők** fület. Ez a fül megjeleníti azoknak a bérlőknek a listáját, amelyeknek a fiókja a része, és ahol Ön egy LCS-projekt tulajdonosa vagy környezeti rendszergazdája.

Ha a keresett bérlő nem szerepel a listában, nyissa meg az [LCS](https://lcs.dynamics.com/v2) szolgáltatást, és győződjön meg arról, hogy ön vagy az adott bérlő LCS-projektjének környezeti rendszergazdája, vagy a projekt tulajdonosa. Csak az Azure Active Directory (Azure AD) fiókok a kiválasztott bérlőből jogosultak a regisztrációs élmény befejezéséhez.

> [!NOTE]
> Miután alkalmazta a módosításokat az LCS-re, akár 30 percet is igénybe vehet, mire a bérlők listája tükrözi a módosításokat.

Minden bérlő esetében a lista a felvételi állapotot jeleníti meg.

:::image type="content" source="media/cloud_edge-EnableHybrid1.png" alt-text="Bérlők listája a Dynamics 365 bérlők fülön.":::

Válassza a **Kattintson ide az első lépésekhez** az LCS-bérlő beléptetési kérelem beküldéséhez. El kell fogadnia a feltételeket. Meg kell adnia egy üzleti e-mail-címet is, ahol a Microsoft elküldheti a felvételi folyamathoz kapcsolódó kommunikációt.

:::image type="content" source="media/cloud_edge-EnableHybrid2.png" alt-text="Regisztrálás elküldése a bérlő számára.":::

A Microsoft áttekinti a kérést, és a regisztrációs űrlapon megadott címre küldött e-mailben tájékoztatja a következő lépésekről. A Microsoft szorosan együttműködik Önnel, hogy az üzleti forgatókönyvéhez engedélyezze a skálázási egységeket a hibrid topológiában.

A felvétel befejezése után a port használatával konfigurálhatja a skálázási egységeket és a munkaterheléseket.

### <a name="manage-scale-units-and-workloads-by-using-the-scale-unit-manager-portal"></a><a name="scale-unit-manager-portal"></a> A mérlegegységek és terhelések kezelése az Egységkezelő portál segítségével

Nyissa meg a [Skálázásiegység-kezelő portált](https://aka.ms/SCMSUM), és jelentkezzen be a bérlői fiókjával. A **Skálázási egységek konfigurálása** lapon hozzáadhat egy központi környezetet, ha az még nem szerepel a listán. Ezután kiválaszthatja a központot, amelyet a skálázási egységekkel és a számítási feladatokkal konfigurálni kíván.

:::image type="content" source="media/cloud_edge-Manage.png" alt-text="Mérlegegység-kezelő portál, Mértékegységek konfigurálása lap.":::

Ha egy vagy több, az előfizetésben elérhető skálázási egységet szeretne hozzáadni, válassza a **Skálázási egységek hozzáadása** lehetőséget.

A **Definiált számítási feladatok** lapon a **Számítási feladatok létrehozása** gombbal hozzáadhat egy raktárkezelési számítási feladatot az egyik skálázási egységhez. Minden számítási feladathoz meg kell adnia a számítási feladatok tulajdonában lévő folyamatok kontextusát. A raktárkezelési munkaterhelések esetében a kontextus egy adott hely és jogi személy adott raktára.

:::image type="content" source="media/cloud_edge-DefineWorkload.png" alt-text="Terhelések párbeszédpanel definiálása":::

#### <a name="manage-workloads"></a><a name="manage-workloads"></a> Terhelések kezelése

Ha egy vagy több terhelés engedélyezve van, **a** Terhelések kezelése funkcióval kezdeményezheti és kezelheti az alábbi táblázatban felsorolt folyamatokat.

| Feldolgozás | Leírás |
|---|---|
| Skálaegység-kommunikáció szüneteltetése | Szünetelteti a központ és a mérlegegység közötti t csővezeték-üzeneteket. Ezzel a folyamattal leállíthatja a kommunikációt, és leállíthatja az adattárat a központ és a mérlegegységek között. Ezt a folyamatot előbb kell futtatnia, mielőtt futtat egy ellátásilánc-kezelési szervizműveletet a központon vagy a mérlegegységen, de ez más esetekben is használható. |
| Skálaegység-kommunikáció folytatása | A központ és a mérlegegység közötti csővezeték-üzenetek folytatása. Lehet, hogy ezt a folyamatot kell használnia, például miután vagy a központon, vagy a mérlegegységen futtatta az ellátásilánc-kezeléshez szükséges szervizműveletet. |
| Terhelések frissítése | Új funkciók szinkronizálása a központ és az egység terhelése között. Lehet, hogy ezt a folyamatot kell használnia, például amikor a szervizelés miatt módosítani kellett az adatcsere lekérdezéseit, és/vagy új táblákat vagy mezőket adott hozzá a terheléshez. |
| Terhelések átvitele egy mérlegegységbe | A központon futó terhelés ütemezése egy mérlegegységbe való mozgatása érdekében. Ennek a folyamatnak a futtatásakor az adatok szinkronizálása meg fog változni, és mind a központ, mind a mérlegegység úgy lesz beállítva, hogy megváltoztassa a terhelés tulajdonosát. |
| Mérlegegység átvitele a központba | Olyan terhelés ütemezése, amely jelenleg egy mérlegegységen fut a központba való mozgatása érdekében. Ennek a folyamatnak a futtatásakor az adatok szinkronizálása meg fog változni, és mind a központ, mind a mérlegegység úgy lesz beállítva, hogy megváltoztassa a terhelés tulajdonosát.
| Rendkívüli váltás központra | <p>Azonnal át kell utalni egy meglévő terhelést a központba. *Ez a folyamat csak a központ aktuálisan elérhető adatainak tulajdonosát fogja megváltoztatni.*</p><p><strong>Figyelmeztetés:</strong> Ez a folyamat adatvesztést okozhat az nem szinkronizált adatok miatt, illetve az üzleti feldolgozás sikertelenségében. Ezért csak olyan olyan 4000 forintos adatokat szabad használni, ahol az üzleti folyamatokat fel kell használni a központon, mivel a mérlegegységben olyan kimaradás van, amely nem enyhíthető időn belül.</p> |
| Elosztott topológia elosztása | A mérlegegység-telepítés eltávolítása, és csak a központon való futtatás a terhelés feldolgozása nélkül. |

:::image type="content" source="media/sum-manage-workloads.png" alt-text="Skálázásiegység- és számításifeladat-kezelési élmény.":::

> [!TIP]
> Idővel további növekményes fejlesztések lesznek hozzáadva a Scale Unit Manager tapasztalatokhoz, így egyszerűbbé teszik az életciklus-kezelési műveleteket. A jelenlegi változattal kapcsolatos különleges képességek egy olyan, a hajóra vonatkozó útmutatóban dokumentáltak, amely elérhető az ellátásilánc-kezelés elosztott topológiája részére való továbbirányítás folyamatában lévő vevők számára. <!-- KFM: Add a link to the handbook when it is published -->

## <a name="feature-management-considerations-for-workloads"></a>A szolgáltatáskezeléssel kapcsolatos szempontok a terhelésekkel kapcsolatban

Ez a szakasz bemutatja azokat a fontos szempontokat, amelyekre figyelembe kell venni a terhelések telepítése, a szolgáltatások hozzáadása, illetve az elosztott topológia telepítésében található funkciók eltávolítása. Számos helyzet befolyásolhatja, hogy a [módosítások](#manage-workloads) elvégzését követően kell-e terhelésfrissítést futtatnia. Ezt általában akkor kell megtennie, amikor frissíti vagy hozzáadja az új adatcsere-lekérdezéseket, és/vagy amikor új táblákat vagy mezőket ad hozzá egy korábban telepített terheléshez.

### <a name="mandatory-features-for-installing-a-workload"></a>A terhelés telepítésének kötelező szolgáltatásai

Terhelés telepítésekor a telepítési folyamat egy terhelésdefiníciót hoz létre, amely a két telepítés közötti adatszinkronizálás során használt adattáblák adatait tartalmazza. A rendszer automatikusan kezeli a terhelésdefiníció létrehozását a Funkciókezelésben jelenleg [engedélyezett funkciók alapján](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md). Az alábbi táblázat felsorolja azokat a funkciókat, amelyeken engedélyezni kell a raktár vagy a gyártási terhelés futtatásához szükséges terhelésdefiníciókat.

| Kötelező funkció | Munkaterhelés |
|---|---|
| GUID-azonosítók automatikus hozzárendelése a WHS-felhasználók létrehozásához | Raktár |
| Szervezeti szintű munkazárolás | Raktár |
| Szállítmányhullám-címke részletei | Raktár |
| Skálázási egység támogatása a raktári alkalmazás munkalistáihoz | Raktár |
| Termelési üzem végrehajtása | Gyártás |

Ha egy terhelést a [mérlegegység-telepítési eszközökkel telepít az egy dobozos fejlesztői környezetekhez vagy a mérlegegység-kezelő](https://github.com/microsoft/SCMScaleUnitDevTools)[portálhoz](https://sum.dynamics.com), minden kötelező szolgáltatást automatikusan engedélyez a rendszer. Ha azonban olyan kézi teszttelepítést ad meg, amelyből hiányzik egy vagy több kötelező funkció, a terhelés telepítése sikertelen lesz, és egy üzenet jelenik meg, amely felsorolja a hiányzó funkciókat. Ezt követően manuálisan kell engedélyeznie ezeket a szolgáltatásokat, és újra kell telepítenie a terhelést.

### <a name="enabling-or-disabling-features-that-have-data-synchronization-dependencies"></a>Az adatszinkronizálási függőségekkel kapcsolatos funkciók engedélyezése vagy letiltása

A központ és a mérlegegységei között szinkronizált adatok kiválasztását befolyásoló funkciók szintén hatással vannak a terhelés meghatározásának a létrehozási folyamatára. Emiatt a terhelés telepítése előtt engedélyezni kell ezeket a funkciókat. Ha a terhelés futtatása közben engedélyezi ezt a szolgáltatástípust, a szolgáltatás engedélyezése után újra létre kell hoznia a [terhelés](#manage-workloads)-definíciót egy terhelésfrissítés futtatásával. Hasonlóképpen, ha a terhelés futtatása közben letilt egy olyan funkciót, amely adatszinkronizálási függőségeket tartalmaz, akkor egy terhelésfrissítés futtatásával el kell távolítania a megfelelő adatszinkronizálási adatokat a [terhelésdefinícióból](#manage-workloads).

[!INCLUDE [cloud-edge-privacy-notice](../../includes/cloud-edge-privacy-notice.md)]

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
