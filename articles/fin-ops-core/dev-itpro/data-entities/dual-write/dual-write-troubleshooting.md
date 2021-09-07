---
title: Általános hibaelhárítás
description: Ez a cikk a Finance and Operations és a Dataverse alkalmazások közötti kettős írású adatintegrációk során felmerülő hibák elhárításával kapcsolatos általános információkat tartalmaz.
author: RamaKrishnamoorthy
ms.date: 03/16/2020
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: b4adc2d83667a05d14a26ace23e5bd8026df4b5f
ms.sourcegitcommit: caa41c076f731f1e02586bc129b9bc15a278d280
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/13/2021
ms.locfileid: "7380212"
---
# <a name="general-troubleshooting"></a>Általános hibaelhárítás

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Ez a cikk a Finance and Operations és a Dataverse alkalmazások közötti kettős írású adatintegrációk során felmerülő hibák elhárításával kapcsolatos általános információkat tartalmaz.

> [!IMPORTANT]
> Előfordulhat, hogy az ebben a témakörben leírt problémák egy része a rendszergazda szerepkört vagy Microsoft Azure Active Directory (Azure AD) bérlői adminisztrátori hitelesítő adatait igénylik. Az egyes problémákat tárgyaló szakaszok leírják, hogy szükség van-e konkrét szerepkörre vagy hitelesítő adatokra.

## <a name="enable-and-view-the-plug-in-trace-log-in-dataverse-to-view-error-details"></a><a id="enable-view-trace"></a>A beépülő modul nyomkövetési naplójának engedélyezése és megtekintése a Dataverse szolgáltatásban a hiba részleteinek megtekintéséhez

**A nyomkövetési napló bekapcsolásához és a hibák megtekintéséhez szükséges szerepkör:** Rendszergazda

Ha be szeretné kapcsolni a nyomkövetési naplót, hajtsa végre az alábbi lépéseket.

1. Jelentkezzen be az ügyfélkapcsolati alkalmazásba, nyissa meg a **Beállítások** lapot, majd a **Rendszer** területen válassza a **Felügyelet** elemet.
2. A **Felügyelet** oldalon válassza az **Rendszerbeállítások** lehetőséget.
3. A **Testreszabás** lap **Beépülő modul és egyéni munkafolyamat tevékenységének nyomon követése** oszlopában válassza az **Összes** lehetőséget, ha engedélyezni szeretné a beépülő modul nyomkövetési naplóját. Ha csak a kivételek bekövetkezésekor szeretné naplózni a nyomkövetési naplókat, akkor válassza ehelyett a **Kivétel** elemet.


Ha meg szeretné tekinteni a nyomkövetési naplót, hajtsa végre az alábbi lépéseket.

1. Jelentkezzen be az ügyfélkapcsolati alkalmazásba, nyissa meg a **Beállítások** lapot, majd a **Testreszabások** területen válassza a **Beépülő modul nyomkövetési naplója** elemet.
2. Keresse meg azokat a nyomkövetési naplókat, ahol a **Típus neve** oszlop értéke **Microsoft.Dynamics.Integrator.DualWriteRuntime.Plugins.PreCommmitPlugin**.
3. A teljes napló megjelenítéséhez kattintson duplán egy elemre, majd a **Végrehajtás** gyorslapján tekintse át az **Üzenetblokk** szövegét.

## <a name="enable-debug-mode-to-troubleshoot-live-synchronization-issues-in-finance-and-operations-apps"></a>Hibakeresési mód engedélyezése az Finance and Operations alkalmazások élő szinkronizálási problémáinak elhárításához

**A hibák megtekintéséhez szükséges szerepkör:** Rendszergazda

A Dataverse alkalmazásból származó kettős írású hibák megjelenhetnek a Finance and Operations alkalmazásban. A hibák szóbeli naplózásának engedélyezéséhez kövesse az alábbi lépéseket:

1. A Finance and Operations alkalmazásban minden projektkonfigurációhoz van egy **IsDebugMode** jelző a **DualWriteProjectConfiguration** táblában.
2. Nyissa meg a **DualWriteProjectConfiguration** elemet az Excel bővítménnyel. A bővítmény használatához engedélyezze a tervezési módot a Finance and Operations Excel bővítményben, és adja hozzá a **DualWriteProjectConfiguration** elemet a laphoz. További információért lásd: Az [entitás adatainak megtekintése és frissítése az Excel segítségével](../../office-integration/use-excel-add-in.md).
3. Állítsa az **IsDebugMode**-ot **Yes**-re a projektben.
4. Futtassa a hibákat létrehozó esetet.
5. A szóbeli naplók a **DualWriteErrorLog** táblában tárolódnak.
6. Az adatok kereséséhez a táblázatkezelőben használja a következő linket: `https://999aos.cloudax.dynamics.com/?mi=SysTableBrowser&tableName=DualWriteErrorLog`, szükség szerint a `999`-t helyettesítve.
7. Frissítsen újra a [KB 4595434](https://fix.lcs.dynamics.com/Issue/Details?kb=4595434&bugId=527820&dbType=3&qc=98e5dc124ac125c57ad633d885ac612aea3ddb8f4abf9d71ab3aa354f2e06cbe) után, amely a 37-es és későbbi platformfrissítésekhez érhető el. Ha ez a javítás telepítve van, akkor a hibakeresési mód több naplót fog rögzíteni.  

## <a name="check-synchronization-errors-on-the-virtual-machine-for-the-finance-and-operations-app"></a>Szinkronizálási hibák keresése a Finance and Operations alkalmazás virtuális gépén

**A hibák megtekintéséhez szükséges szerepkör:** Rendszergazda

1. Jelentkezzen be a Microsoft Dynamics LifeCycle Services (LCS) szolgáltatásba.
2. Nyissa meg azt az LCS-projektet, amelyhez kettős írású tesztelést szeretne végezni.
3. Válassza a **Felhőbeli környezetek** csempét.
4. A távoli asztal használatával jelentkezzen be a Finance and Operations-alkalmazás virtuális gépébe (VM). Az LCS képernyőn látható helyi fiókot használja.
5. Nyissa meg az eseménynaplót.
6. Válassza az **Alkalmazás- és szolgáltatásnaplók \> Microsoft \> Dynamics \> AX-DualWriteSync \> Működő** részt.
7. A legutóbbi hibák listájának áttekintése.

## <a name="unlink-and-link-another-dataverse-environment-from-a-finance-and-operations-app"></a>A Dataverse-környezet leválasztása és másik csatolása a Finance and Operations-alkalmazásból

**A környezet szétválasztásához szükséges szerepkör:** Rendszergazda vagy a Finance and Operations alkalmazásban vagy a Dataverse szolgáltatásban.

1. Bejelentkezés a Finance and Operations alkalmazásba.
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

## <a name="how-to-enable-and-save-network-trace-so-that-traces-can-be-attached-to-support-tickets"></a>Hogyan engedélyezheti és mentheti a hálózati nyomkövetést, hogy a nyomkövetés csatolható legyen a támogatási jegyekhez?

Előfordulhat, hogy a támogatási csapatnak át kell néznie a hálózati nyomvonalakat, hogy bizonyos problémákat elháríthasson. Hálózati nyomvonal létrehozásához kövesse az alábbi lépéseket:

### <a name="chrome"></a>Chrome

1. A megnyitott lapon nyomja meg az **F12** billentyűt, vagy válassza a **Fejlesztői eszközök** lehetőséget a fejlesztői eszközök megnyitásához.
2. Nyissa meg a **Hálózat** lapot, és írja be a szűrő szövegmezőbe az **integ** szót.
3. Futtassa a forgatókönyvet, és figyelje meg a naplózott kéréseket.
4. Kattintson a jobb gombbal a bejegyzésekre, és válassza az **Összes mentése HAR-ként tartalommal** lehetőséget.

### <a name="microsoft-edge"></a>Microsoft Edge

1. A megnyitott lapon nyomja meg az **F12** billentyűt, vagy válassza a **Fejlesztői eszközök** lehetőséget a fejlesztői eszközök megnyitásához.
2. Nyissa meg a **Hálózat** lapot.
3. Futtassa le a forgatókönyvet.
4. Az eredmények HAR-ként történő exportálásához válassza a **mentés** lehetőséget.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
