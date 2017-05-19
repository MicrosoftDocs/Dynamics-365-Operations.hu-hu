---
title: "A pénzügyi jelentési adatpiac visszaállítása az adatbázis visszaállítása után"
description: "Ez a témakör ismerteti, hogyan végezhető el a pénzügyi jelentési adatpiac visszaállítása a Microsoft Dynamics 365 for Operations adatbázis visszaállítása után."
author: ShylaThompson
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: Operations, Core
ms.custom: 261824
ms.assetid: d0784b2c-fe10-428d-8d07-fd474ca50fcc
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: d4ce390c62cbfb1f693410b004aa296c0ed75eb2
ms.contentlocale: hu-hu
ms.lasthandoff: 04/25/2017


---

# <a name="reset-the-financial-reporting-data-mart-after-restoring-a-database"></a>A pénzügyi jelentési adatpiac visszaállítása az adatbázis visszaállítása után

[!include[banner](../includes/banner.md)]


Ez a témakör ismerteti, hogyan végezhető el a pénzügyi jelentési adatpiac visszaállítása a Microsoft Dynamics 365 for Operations adatbázis visszaállítása után. 

Számos olyan forgatókönyv van, amikor szükség lehet a Dynamics 365 for Operations adatbázis visszaállítására biztonsági másolatból, vagy az adatbázis másolására egy másik környezetből. Ilyenkor a megfelelő lépéseket is végre kell hajtania annak a biztosítására, hogy a pénzügyi jelentési adatpiac megfelelően használja a visszaállított 365 Dynamics for Operations adatbázist. Ha kérdése van a pénzügyi jelentési adatpiac visszaállításával kapcsolatban a Dynamics 365 for Operations visszaállításán kívüli okokból, olvassa el a következőt: [Felügyeleti jelentéskészítő adatpiac alaphelyzetbe állítása](https://blogs.msdn.microsoft.com/dynamics_financial_reporting/2016/06/28/resetting-the-management-reporter-data-mart/) további információért. Vegye figyelembe, hogy a folyamat lépéseit a Dynamics 365 for Operations 2016 májusi kiadása támogatja (7.0.1265.23014 alkalmazásbild és 7.0.10000.4 pénzügyi jelentési build), valamint az újabb verziók. Ha a Dynamics 365 for Operations egy korábbi verziójával rendelkezik, lépjen kapcsolatba támogatási csoportunkkal segítségért.

## <a name="export-report-definitions"></a>Jelentésdefiníciók exportálása
Először exportálja a Jelentéstervezőben található jelentésterveket, a következő lépések végrehajtásával:

1.  A Jelentéstervezőben kattintson a **Vállalat** &gt; **Építőelem-csoportok** lehetőségére.
2.  Válassza ki az exportálandó építőelem-csoportot, majd kattintson az **Export** lehetőségre. **Megjegyzés:** A Dynamics 365 for Operations, csak egy építőelem-csoportot támogat, az **Alapértelmezett** csoportot.
3.  Válassza ki a jelentésdefiníciókat az exportáláshoz:
    -   Az összes jelentésdefiníció illetve a társított építőelemek exportálásához kattintson az **Összes kijelölése** lehetőségre.
    -   Konkrét jelentések, sorok, oszlopok, fák vagy dimenziókészletek exportálásához kattintson a megfelelő lapra, majd válassza ki az exportálandó tételeket. Ha több cikket szeretne kijelölni egy lapon, nyomja le és tartsa lenyomva a Ctrl-billentyűt. Ha exportálandó jelentéseket jelöl ki, úgy kiválasztásra kerülnek a társított sorok, oszlopok, fák és dimenziókészletek is.

4.  Kattintson az **Exportálás** elemre.
5.  Adjon meg egy fájlnevet, és jelöljön ki egy biztonságos helyet, ahol menteni szeretné az exportált jelentésdefiníciókat.
6.  Kattintson a **Mentés** gombra.

A fájl másolhatók, illetve feltölthető egy biztonságos helyre, hogy később importálható legyen egy másik környezetbe. A Microsoft Azure tárolófiók használatával kapcsolatos információkért lásd: [Adatátvitel az AzCopy parancssori segédprogrammal](https://docs.microsoft.com/en-gb/azure/storage/storage-use-azcopy). 
> [!NOTE]
> A Dynamics 365 for Operations megállapodás részeként a Microsoft nem biztosít tárolófiókot. Be kell szereznie egy tárolófiókot, vagy egy külön Azure-előfizetésből származó tárolófiókot kell használnia. 
> [!WARNING]
> Legyen tisztában a D-meghajtó viselkedésével az Azure virtuális gépeken Ne tárolja itt véglegesen az exportált építőelem-csoportokat. További információt az ideiglenes meghajtókkal kapcsolatban itt talál: [A Windows Azure virtuális gépek ideiglenes meghajtóinak ismertetése](https://blogs.msdn.microsoft.com/mast/2013/12/06/understanding-the-temporary-drive-on-windows-azure-virtual-machines/).

## <a name="stop-services"></a>Szolgáltatások leállítása
A Távoli asztal segítségével csatlakozzon az összes számítógéphez a környezetében, és állítsa le a következő Windows-szolgáltatásokat a services.msc segítségével:

-   Webes közzétételi szolgáltatás (az összes AOS-számítógépen)
-   Microsoft Dynamics 365 for Operations Batch Management Service (csak a nem személyes AOS-számítógépeken)
-   Management Reporter 2012 Process Service (csak a BI-számítógépeken)

Ezek a szolgáltatások nyitott kapcsolattal rendelkeznek a Dynamics 365 for Operations-adatbázissal.

## <a name="reset"></a>Alaphelyzet
#### <a name="locate-the-latest-dataupgradezip-package"></a>Keresse meg a legújabb DataUpgrade.zip csomagot

Keresse meg a legújabb DataUpgrade.zip csomagot a következő utasításokkal: [A DataUpgrade.zip parancsfájl letöltése](..\migration-upgrade\upgrade-data-to-latest-update.md). Az utasítások ismertetik, hogyan keresse meg az adatfrissítési csomagnak a környezetéhez megfelelő verzióját.

#### <a name="execute-scripts-against-dynamics-365-for-operations-database"></a>Parancsfájl-műveletek végrehajtása a Dynamics 365 for Operations adatbázison

Futtassa a következő parancsfájlokat a Dynamics 365 for Operations adatbázison (nem pénzügyi jelentési adatbázison).

-   DataUpgrade.zip\\AosService\\Scripts\\ConfigureAxReportingIntegration.sql
-   DataUpgrade.zip\\AosService\\Scripts\\GrantAzViewChangeTracking.sql

Ezeket a parancsfájlok gondoskodnak arról, hogy helyesek legyenek a felhasználók, a szerepkörök és a változáskövetési beállítások.

#### <a name="execute-powershell-command-to-reset-database"></a>Adatbázis alaphelyzetbe állításához PowerShell-parancs végrehajtása

Hajtsa végre a következő parancsot közvetlenül az AOS-számítógépen Dynamics 365 for Operations és a pénzügyi jelentéskészítés közti integráció alaphelyzetbe állításához:

1.  Nyissa meg a Windows PowerShell alkalmazást rendszergazdaként.
2.  Hajtsa végre: F:
3.  Hajtsa végre: cd F:\\MRApplicationService\\MRInstallDirectory
4.  Hajtsa végre: Import-Module .\\Server\\MRDeploy\\MRDeploy.psd1
5.  Hajtsa végre: Reset-DatamartIntegration -Reason OTHER -ReasonDetail “&lt;az ok, amiért alaphelyzetbe állítom&gt;”
    -   Adja meg az „Y”-t megerősítésként.

A paraméterek magyarázata:

-   A -Reason érvényes értékei: SERVICING, BADDATA, OTHER.
-   A -ReasonDetail paraméter szabad szöveg.
-   A távmérő/környezet felügyelete végzi az ok és reasonDetail rögzítését.

## <a name="start-services"></a>Szolgáltatások indítása
A korábban leállított szolgáltatások újraindításához használja a Services.msc parancsot:

-   Webes közzétételi szolgáltatás (az összes AOS-számítógépen)
-   Microsoft Dynamics 365 for Operations Batch Management Service (csak a nem személyes AOS-számítógépeken)
-   Management Reporter 2012 Process Service (csak a BI-számítógépeken)

## <a name="import-report-definitions"></a>Jelentésdefiníciók importálása
Importálja a jelentésterveket a Jelentéstervezőből, az exportálás során létrehozott fájl használatával:

1.  A Jelentéstervezőben kattintson a **Vállalat** &gt; **Építőelem-csoportok** lehetőségére.
2.  Válassza ki az exportálandó építőelem-csoportot, majd kattintson az **Export** lehetőségre. 
    > [!NOTE]
    > A Dynamics 365 for Operations, csak egy építőelem-csoportot támogat, az **Alapértelmezett** csoportot.
3.  Válassza ki az **Alapértelmezett** építőelemet, és kattintson az **Importálás** lehetőségre.
4.  Válassza ki az exportált jelentésdefiníciókat tartalmazó fájlt, és kattintson a **Megnyitás** lehetőségre.
5.  Jelölje ki az importálandó jelentésdefiníciókat az Importálás párbeszédpanelben:
    -   Az összes jelentésdefiníció illetve az azt támogató építőelemek importálásához kattintson az **Összes kijelölése** lehetőségre.
    -   Konkrét jelentések, sorok, oszlopok, fák vagy dimenziókészletek importálásához válassza ki az importálandó jelentéseket, sorokat, oszlopokat, fákat vagy dimenziókészleteket.

6.  Kattintson az **Importálás** gombra.





