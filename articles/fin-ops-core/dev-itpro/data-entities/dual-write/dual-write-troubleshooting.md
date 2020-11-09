---
title: Általános hibaelhárítás
description: Ez a cikk a Finance and Operations és a Common Data Service alkalmazások közötti kettős írású adatintegrációk során felmerülő hibák elhárításával kapcsolatos általános információkat tartalmaz.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 03/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: c3352afd93dfc7c37a8af9dabaf85b7a1debad30
ms.sourcegitcommit: 0a741b131ed71f6345d4219a47cf5f71fec6744b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "3997254"
---
# <a name="general-troubleshooting"></a>Általános hibaelhárítás

[!include [banner](../../includes/banner.md)]



Ez a cikk a Finance and Operations és a Common Data Service alkalmazások közötti kettős írású adatintegrációk során felmerülő hibák elhárításával kapcsolatos általános információkat tartalmaz.

> [!IMPORTANT]
> Előfordulhat, hogy az ebben a témakörben leírt problémák egy része a rendszergazda szerepkört vagy Microsoft Azure Active Directory (Azure AD) bérlői adminisztrátori hitelesítő adatait igénylik. Az egyes problémákat tárgyaló szakaszok leírják, hogy szükség van-e konkrét szerepkörre vagy hitelesítő adatokra.

## <a name="when-you-try-to-install-the-dual-write-package-by-using-the-package-deployer-tool-no-available-solutions-are-shown"></a>Amikor a Package Deployer eszközzel próbálja meg telepíteni a kettős írású csomagot, nem jelennek meg a rendelkezésre álló megoldások

A Package Deployer eszköz egyes verziói nem kompatibilisek a kettős írású megoldáscsomaggal. A csomag sikeres telepítéséhez győződjön meg arról, hogy a Package Deployer eszköz [9.1.0.20](https://www.nuget.org/packages/Microsoft.CrmSdk.XrmTooling.PackageDeployment.Wpf/9.1.0.20) vagy újabb verzióját használja.

A Package Deployer eszköz telepítését követően telepítse a megoldást tartalmazó csomagot a következő lépések végrehajtásával.

1. Töltse le a legújabb megoldáscsomag-fájlt a Yammer.com oldalról. A csomag zip-fájljának letöltése után kattintson rá jobb gombbal, és válassza a **Tulajdonságok** elemet. Válassza ki a **Zárolás feloldása** jelölőnégyzetet, majd válassza az **Alkalmazás** lehetőséget. Ha nem látja a **Zárolás feloldása** jelölőnégyzetet, akkor a zip-fájl zárolása már fel van oldva, és kihagyhatja ezt a lépést.

    ![Tulajdonságok párbeszédpanel](media/unblock_option.png)

2. Csomagolja ki a csomag zip-fájlját, és másolja az összes fájlt a **Dynamics365FinanceAndOperationsCommon.PackageDeployer.2.0.438** mappába.

    ![A Dynamics365FinanceAndOperationsCommon.PackageDeployer.2.0.438 mappa tartalma](media/extract_package.png)

3. Illessze be az összes másolt fájlt a Package Deployer eszköz **Eszközök** mappájába. 
4. Futtassa a **PackageDeployer.exe** fájlt a Common Data Service-környezet kiválasztásához és a megoldások telepítéséhez.

    ![Az Eszközök mappa tartalma](media/paste_copied_files.png)

## <a name="enable-and-view-the-plug-in-trace-log-in-common-data-service-to-view-error-details"></a>A beépülő modul nyomkövetési naplójának engedélyezése és megtekintése a Common Data Service szolgáltatásban a hiba részleteinek megtekintéséhez

**A nyomkövetési napló bekapcsolásához és a hibák megtekintéséhez szükséges szerepkör:** Rendszergazda

Ha be szeretné kapcsolni a nyomkövetési naplót, hajtsa végre az alábbi lépéseket.

1. Jelentkezzen be az a modellel vezérelt alkalmazásba a Dynamics 365-ben, nyissa meg a **Beállítások** lapot, majd a **Rendszer** területen válassza a **Felügyelet** elemet.
2. A **Felügyelet** oldalon válassza az **Rendszerbeállítások** lehetőséget.
3. A **Testreszabás** lap **Beépülő modul és egyéni munkafolyamat tevékenységének nyomon követése** mezőjében válassza az **Összes** lehetőséget, ha engedélyezni szeretné a beépülő modul nyomkövetési naplóját. Ha csak a kivételek bekövetkezésekor szeretné naplózni a nyomkövetési naplókat, akkor válassza ehelyett a **Kivétel** elemet.


Ha meg szeretné tekinteni a nyomkövetési naplót, hajtsa végre az alábbi lépéseket.

1. Jelentkezzen be az a modellel vezérelt alkalmazásba a Dynamics 365-ben, nyissa meg a **Beállítások** lapot, majd a **Testreszabások** területen válassza a **Beépülő modul nyomkövetési naplója** elemet.
2. Keresse meg azokat a nyomkövetési naplókat, ahol a **Típus neve** mező értéke **Microsoft.Dynamics.Integrator.DualWriteRuntime.Plugins.PreCommmitPlugin**.
3. A teljes napló megjelenítéséhez kattintson duplán egy elemre, majd a **Végrehajtás** gyorslapján tekintse át az **Üzenetblokk** szövegét.

## <a name="enable-debug-mode-to-troubleshoot-live-synchronization-issues-in-finance-and-operations-apps"></a>Hibakeresési mód engedélyezése az Finance and Operations alkalmazások élő szinkronizálási problémáinak elhárításához

**A hibák megtekintéséhez szükséges szerepkör:** a rendszeradminisztrátor A kettős írás hibák, amelyek származhatnak a Common Data Service szolgáltatásból, megjelenhetnek a Finance and Operations alkalmazásban. Bizonyos esetekben a hibaüzenet teljes szövege nem érhető el, mivel az üzenet túl hosszú, vagy személyes azonosításra alkalmas adatokat (PII) tartalmaz. A hibák részletes naplózását a következő lépések végrehajtásával kapcsolhatja be.

1. A Finance and Operations-alkalmazások minden projektkonfigurációjában van egy **IsDebugMode** tulajdonság a **DualWriteProjectConfiguration** entitásban. Nyissaa meg a **DualWriteProjectConfiguration** entitást az Excel-bővítmény használatával.

    > [!TIP]
    > Az entitás megnyitásának egyszerű módja a **Tervező** mód bekapcsolása az Excel-bővítményben, majd adja hozzá a **DualWriteProjectConfigurationEntity** entitást a munkalaphoz. További információért lásd: [Entitásadatok megnyitása az Excel programban, és frissítésük az Excel-bővítmény használatával](../../office-integration/use-excel-add-in.md).

2. Állítsa a projekt **IsDebugMode** tulajdonságát **Igen** értékre.
3. Futtassa a hibákat létrehozó esetet.
4. A részletes naplók a DualWriteErrorLog táblában érhetők el. Az adatoknak a tábla böngészőjében való kereséséhez használja a következő URL-címet (helyettesítse az **XXX** részt a megfelelő elemmel):

    `https://XXXaos.cloudax.dynamics.com/?mi=SysTableBrowser&tableName=>DualWriteErrorLog`

## <a name="check-synchronization-errors-on-the-virtual-machine-for-the-finance-and-operations-app"></a>Szinkronizálási hibák keresése a Finance and Operations alkalmazás virtuális gépén

**A hibák megtekintéséhez szükséges szerepkör:** Rendszergazda

1. Jelentkezzen be a Microsoft Dynamics LifeCycle Services (LCS) szolgáltatásba.
2. Nyissa meg azt az LCS-projektet, amelyhez kettős írású tesztelést szeretne végezni.
3. Válassza a **Felhőbeli környezetek** csempét.
4. A távoli asztal használatával jelentkezzen be a Finance and Operations-alkalmazás virtuális gépébe (VM). Az LCS képernyőn látható helyi fiókot használja.
5. Nyissa meg az eseménynaplót.
6. Válassza az **Alkalmazás- és szolgáltatásnaplók \> Microsoft \> Dynamics \> AX-DualWriteSync \> Működő** részt.
7. A legutóbbi hibák listájának áttekintése.

## <a name="unlink-and-link-another-common-data-service-environment-from-a-finance-and-operations-app"></a>A Common Data Service-környezet leválasztása és másik csatolása a Finance and Operations-alkalmazásból

**A környezet szétválasztásához szükséges szerepkör:** Rendszergazda vagy a Finance and Operations alkalmazásban vagy a Common Data Service szolgáltatásban.

1. Bejelentkezés a Finance and Operations alkalmazásba.
2. Nyissa meg a **Munkaterületek \> Adatkezelés** pontot, és válassza a **Kettős írás** csempét.
3. Válassza ki az összes futó leképezést, és kattintson a **Leállítás** elemre.
4. Válassza a **Környezet leválasztása** elemet.
5. A művelet jóváhagyásához válassza az **Igen** lehetőséget.

Ezután új környezet csatolható.

## <a name="unable-to-view-the-sales-order-line-information-form"></a>Nem lehet megtekinteni az értékesítésirendelés-sor adatai képernyőt 

Amikor értékesítési rendelést hoz létre a Dynamics 365 Sales modulban, akkor ha a **+ Termékek hozzáadása** gombra kattint, előfordulhat, hogy a rendszer átirányítja a Dynamics 365 Projektműveletek rendelési sor űrlapjára. Az értékesítésirendelés-sor **adatainak** űrlapját nem lehet arról az űrlapról megtekinteni. Az **adatok** beállítása nem jelenik meg a legördülő listában az **új rendelési sor** alatt. Ennek az az oka, hogy a Projektműveletek már telepítve van a környezetben.

Az **Adatok** űrlapbeállítás újbóli engedélyezéséhez kövesse az alábbi lépéseket:
1. Lépjen a **Rendeléssor** entitásra.
2. Keresse meg az **Adatok** űrlapot az űrlapok csomópont alatt. 
3. Válassza ki az **Adatok** űrlapot, és kattintson a **Biztonsági szerepkörök engedélyezése** pontra. 
4. Módosítsa a biztonsági beállítást: **Megjelenítés mindenkinek**.
