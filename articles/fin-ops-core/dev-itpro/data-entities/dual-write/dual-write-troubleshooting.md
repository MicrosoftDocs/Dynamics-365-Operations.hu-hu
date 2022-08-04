---
title: Általános hibaelhárítás
description: Ez a témakör általános hibaelhárítási információkat tartalmaz a pénzügyek és a műveletalkalmazások, illetve a Dataverse.
author: RamaKrishnamoorthy
ms.date: 04/18/2022
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: 2f263e331d23ce0ddf60a4abc2467513aa342445
ms.sourcegitcommit: 6781fc47606b266873385b901c302819ab211b82
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/02/2022
ms.locfileid: "9112364"
---
# <a name="general-troubleshooting"></a>Általános hibaelhárítás

[!include [banner](../../includes/banner.md)]



Ez a témakör általános hibaelhárítási információkat tartalmaz a pénzügyek és a műveletalkalmazások, illetve a Dataverse.

> [!IMPORTANT]
> Az ebben a témakörben említett problémák egy része a rendszergazdai szerepkörhöz vagy a Microsoft Azure Active Directory (Azure AD) bérlői rendszergazdai hitelesítő adatokhoz lehet szükséges. Az egyes problémákat tárgyaló szakaszok leírják, hogy szükség van-e konkrét szerepkörre vagy hitelesítő adatokra.

## <a name="enable-and-view-the-plug-in-trace-log-in-dataverse-to-view-error-details"></a><a id="enable-view-trace"></a>A beépülő modul nyomkövetési naplójának engedélyezése és megtekintése a Dataverse szolgáltatásban a hiba részleteinek megtekintéséhez

A nyomkövetési naplók jól használhatók a Pénzügy & Műveletek és az Dataverse. A naplók részletes adatokat nyújthatnak a Dynamics 365 műszaki és mérnöki támogatást nyújtó csapatok számára. Ez a cikk a nyomkövetési naplók engedélyezésével és a naplók megtekintésével foglalkozik. A nyomkövetési naplókat a Dynamics 365 Beállítások lapján lehet kezelni, és rendszergazdai szintű jogosultságok szükségesek a módosításhoz és a megtekintéshez. 

**A nyomkövetési napló bekapcsolásához és a hibák megtekintéséhez szükséges szerepkör:** Rendszergazda

### <a name="turn-on-the-trace-log"></a>A nyomkövetési napló bekapcsolva
Ha be szeretné kapcsolni a nyomkövetési naplót, hajtsa végre az alábbi lépéseket.

1.  Jelentkezzen be a Dynamics 365 programba, majd válassza **a** beállításokat a felső navigációs sávon. A Rendszerek lapon kattintson a Felügyelet **gombra**.
2.  Kattintson az Adminisztráció lapon a Rendszerbeállítások **elemre**.
3.  Válassza a **Testreszabás lapot** és a beépülő modult, majd az egyéni munkaáramlási tevékenység nyomkövetési szakaszában módosítsa a legördülő **lapokat Mind beállításra**. Ezzel minden tevékenységet nyomon követ, és átfogó adathalmazt biztosít a csapatoknak, akiknek át kell vizsgálniuk a potenciális problémákat.

> [!NOTE]
> A legördülő lista kivételre **való** beállítása csak kivételek (hibák) esetén nyújt nyomkövetési információkat.

Ha engedélyezve van, a beépülő modulok nyomkövetési naplóit addig gyűjti a rendszer, amíg manuálisan ki nem kikapcsolása meg nem történik úgy, hogy visszatér erre a helyre, és be nem választja a **Ki gombra**.

### <a name="view-the-trace-log"></a>A nyomkövetési napló megtekintése
Ha meg szeretné tekinteni a nyomkövetési naplót, hajtsa végre az alábbi lépéseket.

1. A Dynamics 365 Beállításai lapon válassza **a** felső navigációs sávOn a Beállítások lehetőséget. 
2. Válassza **ki a Nyomkövetés nyomkövetési** naplót **a** lap Testreszabásai szakaszában.
3. A nyomkövetési naplók listájában a típusnév és/vagy az üzenetnév alapján található bejegyzés.
4. A teljes napló megtekintéséhez nyissa meg a kívánt bejegyzést. A Végrehajtás szakasz üzenetblokkja elérhető információt nyújt a beépülő modul számára. Ha rendelkezésre áll, a kivétel adatai is meg lesznek adni. 

A nyomkövetési naplók tartalmát átmásolhatja egy másik alkalmazásba, például jegyzettömbbe vagy más eszközbe, hogy a naplókat és szövegfájlokat megtekintve könnyebben megtekintsen minden tartalmat. 

## <a name="enable-debug-mode-to-troubleshoot-live-synchronization-issues-in-finance-and-operations-apps"></a>Hibakeresési mód engedélyezése a pénzügyi és műveleti alkalmazások élő szinkronizálási problémáinak hibaelhárításához

**A hibák megtekintéséhez szükséges szerepkör:** Rendszergazda

A két írásos hibák, Dataverse amelyek származnak, megjelennek a Pénzügy és műveletek alkalmazásban. A hibák szóbeli naplózásának engedélyezéséhez kövesse az alábbi lépéseket:

1. A Pénzügy és műveletek alkalmazás minden projektkonfigurációjában van egy IsDebugMode **jelző** a **DualWriteProjectConfiguration táblán**.
2. Nyissa meg a **DualWriteProjectConfiguration** elemet az Excel bővítménnyel. A bővítmény csak akkor használható, ha engedélyezi a tervező módot a pénzügyben és az Excel-bővítményben **, és hozzáadhatja a laphoz a DualWriteProjectConfiguration** tulajdonságot. További információért lásd: Az [entitás adatainak megtekintése és frissítése az Excel segítségével](../../office-integration/use-excel-add-in.md).
3. Állítsa az **IsDebugMode**-ot **Yes**-re a projektben.
4. Futtassa a hibákat létrehozó esetet.
5. A szóbeli naplók a **DualWriteErrorLog** táblában tárolódnak.
6. Az adatok kereséséhez a táblázatkezelőben használja a következő linket: `https://999aos.cloudax.dynamics.com/?mi=SysTableBrowser&tableName=DualWriteErrorLog`, szükség szerint a `999`-t helyettesítve.
7. Frissítsen újra a [KB 4595434](https://fix.lcs.dynamics.com/Issue/Details?kb=4595434&bugId=527820&dbType=3&qc=98e5dc124ac125c57ad633d885ac612aea3ddb8f4abf9d71ab3aa354f2e06cbe) után, amely a 37-es és későbbi platformfrissítésekhez érhető el. Ha ez a javítás telepítve van, akkor a hibakeresési mód több naplót fog rögzíteni.  

## <a name="check-synchronization-errors-on-the-virtual-machine-for-the-finance-and-operations-app"></a>Szinkronizálási hibák ellenőrzése a virtuális számítógépen a Pénzügy és műveletek alkalmazáshoz

**A hibák megtekintéséhez szükséges szerepkör:** Rendszergazda

1. Jelentkezzen be a Microsoft Dynamics LifeCycle Services (LCS) szolgáltatásba.
2. Nyissa meg azt az LCS-projektet, amelyhez kettős írású tesztelést szeretne végezni.
3. Válassza a **Felhőbeli környezetek** csempét.
4. A Távoli asztalon bejelentkezhet a pénzügyek és műveletek alkalmazás virtuális gépére (VM). Az LCS képernyőn látható helyi fiókot használja.
5. Nyissa meg az eseménynaplót.
6. Válassza az **Alkalmazás- és szolgáltatásnaplók \> Microsoft \> Dynamics \> AX-DualWriteSync \> Működő** részt.
7. A legutóbbi hibák listájának áttekintése.

## <a name="dual-write-ui-landing-page-showing-blank"></a>Üresen maradó kettős írású felhasználói felület lapja
Amikor a kettős Microsoft Edge írású lapot a vagy a Króm böngészőben nyitja meg, a kezdőlap nem töltődik be, és egy üres oldalt vagy egy hibát lát, mint például: "Valami nem sikerült".
Az Devtoolsban egy hiba látható a konzolnaplókban:

>bundle.eed39124e62c58ef34d2.js:37 DOMException: Nem sikerült beolvasni a "sessionStorage" tulajdonságot a "Window" alkalmazásból: A dokumentum hozzáférése megtagadva. : t.storeInSessionStorage (https://dataintegrator.trafficmanager.net/bundle.eed39124e62c58ef34d2.js:16:136860) új t (https://dataintegrator.trafficmanager.net/bundle.eed39124e62c58ef34d2.js:69:20103) (ci) (https://dataintegrator.trafficmanager.net/bundle.eed39124e62c58ef34d2.js:37:44115) (eo ) (https://dataintegrator.trafficmanager.net/bundle.eed39124e62c58ef34d2.js:37:58728) a(z) vnál (https://dataintegrator.trafficmanager.net/bundle.eed39124e62c58ef34d2.js:37:65191) a Nr (https://dataintegrator.trafficmanager.net/bundle.eed39124e62c58ef34d2.js:37:84692) vb vagy (https://dataintegrator.trafficmanager.net/bundle.eed39124e62c58ef34d2.js:37:85076) Ss (https://dataintegrator.trafficmanager.net/bundle.eed39124e62c58ef34d2.js:37:91750) és (https://dataintegrator.trafficmanager.net/bundle.eed39124e62c58ef34d2.js:37:91130) hs (https://dataintegrator.trafficmanager.net/bundle.eed39124e62c58ef34d2.js:37:90151)

A felhasználói felület a böngésző "munkamenet-tárolója" használatával tárol néhány tulajdonságértéket a kezdőlap betöltéséhez. Ahhoz, hogy ez működjön, a webhely böngészőjében engedélyezve kell lennie a külső felek által használt süteményeknek. A hiba azt jelzi, hogy a felhasználói felület nem férhet hozzá a munkamenet-tárolóhoz. Erre a problémára két helyzet közül lehet példa:

1.  A felhasználói felületet az Edge/Króm módban nyitja meg, és az incogn helyen külső fél által használt sütemény nem lesz elérhető.
2.  Az Edge/Krómban teljesen le van tiltva a külső felek süteménye.

### <a name="mitigation"></a>Kockázatcsökkentés
A böngésző beállításaiban meg kell engedni a harmadik fél által használt süteményeket.

### <a name="google-chrome-browser"></a>Króm böngésző
1. lehetőség:
1.  Lépjen a beállításokhoz, chrome://settings/ a címsávban, majd lépjen az Adatvédelmi és biztonsági > és egyéb webhelyadatokra.
2.  Válassza az "Összes sütemény engedélyezése" lehetőséget. Ha nem ezt szeretné tenni, használja a második lehetőséget.

2. lehetőség:
1.  Lépjen a beállításokhoz, chrome://settings/ a címsávban, majd lépjen az Adatvédelmi és biztonsági > és egyéb webhelyadatokra.
2.  Ha a "Harmadik fél által használt sütemények blokkolása az Incogntóban" vagy a "Harmadik fél által történő sütemények blokkolása" beállítás van megjelölve, kattintson a " **Mindig használható sütemények" webhelyre, és kattintson a Hozzáadás gombra**. 
3.  Adja meg a Pénzügy & Műveleti alkalmazások webhelynevét – https://<your_FinOp_instance>.cloudax.dynamics.com. Győződjön meg róla, hogy a "Minden sütemény, csak ezen a helyen" jelölőnégyzetet bejel választja. 

### <a name="microsoft-edge-browser"></a>Microsoft Edge böngésző
1.  A Beállítások – > webhely engedélyei – > a sütemények és a webhely adatai.
2.  A "Harmadik fél által használt sütemények blokkolása" kikapcsolása.  

## <a name="unlink-and-link-another-dataverse-environment-from-a-finance-and-operations-app"></a>Egy másik környezet leválasztása Dataverse és csatolása egy pénzügyi és műveleti alkalmazásból

**A környezet leválasztához szükséges szerepkör: a** Pénzügy és a Műveletek alkalmazás vagy Dataverse a.

1. Jelentkezzen be a Pénzügy és műveletek alkalmazásba.
2. Nyissa meg a **Munkaterületek \> Adatkezelés** pontot, és válassza a **Kettős írás** csempét.
3. Válassza ki az összes futó leképezést, és kattintson a **Leállítás** elemre.
4. Válassza a **Környezet leválasztása** elemet.
5. A művelet jóváhagyásához válassza az **Igen** lehetőséget.

Ezután új környezet csatolható.

## <a name="unable-to-view-the-sales-order-line-information-form"></a>Nem lehet megtekinteni az értékesítésirendelés-sor adatai képernyőt 

Amikor értékesítési rendelést hoz létre a Dynamics 365 Sales modulban, akkor ha a **+ Termékek hozzáadása** gombra kattint, előfordulhat, hogy a rendszer átirányítja a Dynamics 365 Project Operations rendelési sor űrlapjára. Az értékesítésirendelés-sor **adatainak** űrlapját nem lehet arról az űrlapról megtekinteni. Az **adatok** beállítása nem jelenik meg a legördülő listában az **új rendelési sor** alatt. Ennek az az oka, hogy a Projektműveletek már telepítve van a környezetben.

Az **Adatok** űrlapbeállítás újbóli engedélyezéséhez kövesse az alábbi lépéseket:

1. Lépjen a **Rendeléssor** táblára.
2. Keresse meg az **Adatok** űrlapot az űrlapok csomópont alatt.
3. Válassza ki az **Adatok** űrlapot, és kattintson a **Biztonsági szerepkörök engedélyezése** pontra.
4. Módosítsa a biztonsági beállítást: **Megjelenítés mindenkinek**.

## <a name="how-to-ensure-data-integration-is-using-the-most-current-finance-and-operations-schema"></a>Hogyan lehet gondoskodni az adatintegrációról a legfrissebb pénzügyi és műveleti sémát használva?

Ha nem használja a legfrissebb sémát, akkor adatintegrációja során problémákba okozhatja az adatintegráció. A következő lépések segítséget fognak tenni az entitáslista frissítésében a pénzügyek és műveletek alkalmazásában, valamint az adatentitásban található entitások frissítésében.

### <a name="refresh-entity-list-in-finance-and-operations-environment"></a>Entitáslista frissítése a pénzügyi és műveleti környezetben
1.  Jelentkezzen be a pénzügyi és műveleti környezetbe.
2.  Válassza ki **az Adatkezelést**.
3.  Az Adatkezelési keretrendszeren belül válassza ki a **Keretrendszer paramétereit**.
4.  Az Adatimportási **és -exportálási keretrendszer paraméterei** lapon jelölje **ki** az Entitásbeállítások lapot, és válassza az **Entitáslista frissítése lehetőséget**. Az érintett entitások számától függően a frissítés több mint 30 percig is eltarthat.
5.  Nyissa meg az **Adatkezelést**, és válassza **ki az Adatentitások** listában a várt entitások érvényességét. Ha a várt entitások nincsenek felsorolva, ellenőrizze, hogy az entitások megjelennek-e a pénzügyi és műveleti környezetben, és szükség szerint állítsa vissza a hiányzó entitásokat.

#### <a name="if-the-refresh-fails-to-resolve-the-issue-delete-and-re-add-the-entities"></a>Ha a frissítés nem oldja meg a problémát, törölje és adja hozzá újra az entitásokat.

> [!NOTE]
> Lehet, hogy le kell állítania minden olyan feldolgozási csoportot, amely aktív módon használja az entitásokat a törlés előtt.

1.  Válassza **ki az adatkezelést** a pénzügyi és műveleti környezetben, és válassza ki az **Adatentitások lehetőséget**.
2.  Problémákat okozható entitások keresése, valamint megjegyzés megadása a célentitásról, az előkészítő tábláról, az entitásnévről és egyéb beállításokról. Az entitás vagy entitások törlése a listából.
3.  Válassza az **Új** lehetőséget, és adja hozzá újra az entitásokat a 2. lépésben származó adatok használatával. 

#### <a name="refresh-entities-in-data-integrator"></a>Entitások frissítése az Adatentitásban
Jelentkezzen be az Power Platform Adminisztrációs központba, és válassza az Adatintegráció **lehetőséget**. Nyissa meg azt a projektet, amelyben a problémák fordulnak elő, és válassza az **Entitások frissítése lehetőséget**.

## <a name="how-to-enable-and-save-network-trace-so-that-traces-can-be-attached-to-support-tickets"></a>Hogyan engedélyezheti és mentheti a hálózati nyomkövetést, hogy a nyomkövetés csatolható legyen a támogatási jegyekhez?

Előfordulhat, hogy a támogatási csapatnak át kell néznie a hálózati nyomvonalakat, hogy bizonyos problémákat elháríthasson. Hálózati nyomvonal létrehozásához kövesse az alábbi lépéseket:

### <a name="google-chrome-browser"></a>Króm böngésző

1. A megnyitott lapon nyomja meg az **F12** billentyűt, vagy válassza a **Fejlesztői eszközök** lehetőséget a fejlesztői eszközök megnyitásához.
2. Nyissa meg a **Hálózat** lapot, és írja be a szűrő szövegmezőbe az **integ** szót.
3. Futtassa a forgatókönyvet, és figyelje meg a naplózott kéréseket.
4. Kattintson a jobb gombbal a bejegyzésekre, és válassza az **Összes mentése HAR-ként tartalommal** lehetőséget.

### <a name="microsoft-edge-browser"></a>Microsoft Edge böngésző

1. A megnyitott lapon nyomja meg az **F12** billentyűt, vagy válassza a **Fejlesztői eszközök** lehetőséget a fejlesztői eszközök megnyitásához.
2. Nyissa meg a **Hálózat** lapot.
3. Futtassa le a forgatókönyvet.
4. Az eredmények HAR-ként történő exportálásához válassza a **mentés** lehetőséget.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]

