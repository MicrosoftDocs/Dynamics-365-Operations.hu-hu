---
title: "A pénzügyi jelentési adatpiac visszaállítása az adatbázis visszaállítása után"
description: "Ez a témakör ismerteti, hogyan végezhető el a pénzügyi jelentési adatpiac visszaállítása a Microsoft Dynamics 365 for Finance and Operations adatbázis visszaállítása után."
author: ShylaThompson
manager: AnnBe
ms.date: 08/15/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: shylaw
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 261824
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 47e70cb1291e390b42b7feff844b2aca141f09b7
ms.openlocfilehash: 200b1a03a0ea95ec2d75850f9a8aebda966e38d6
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---

# <a name="reset-the-financial-reporting-data-mart-after-restoring-a-database"></a>A pénzügyi jelentési adatpiac visszaállítása az adatbázis visszaállítása után

[!include[banner](../includes/banner.md)]


Ez a témakör ismerteti, hogyan végezhető el a pénzügyi jelentési adatpiac visszaállítása a Microsoft Dynamics 365 for Finance and Operations adatbázis visszaállítása után.

Ha bármikor visszaállítsa a Dynamics 365 for Operations adatbázist egy biztonsági másolatból, vagy másolja az adatbázist egy másik környezetből, biztosítania kell, hogy a pénzügyi jelentési adatpiac megfelelően használja a visszaállított 365 Dynamics for Finance and Operations adatbázist. 
> [!Note] 
> A folyamat lépéseit a Dynamics 365 for Operations 2016 májusi kiadása támogatja (7.0.1265.23014 alkalmazásbild és 7.0.10000.4 pénzügyi jelentési build), valamint az újabb verziók. Ha a Dynamics 365 for Finance and Operations egy korábbi verziójával rendelkezik, lépjen kapcsolatba támogatási csoportunkkal segítségért.

## <a name="export-report-definitions"></a>Jelentésdefiníciók exportálása
Először exportálja a Jelentéstervezőben található jelentésterveket, a következő lépések végrehajtásával:

1.  A Jelentéstervezőben kattintson a **Vállalat** &gt; **Építőelem-csoportok** lehetőségére.
2.  Válassza ki az exportálandó építőelem-csoportot, majd kattintson az **Export** lehetőségre. 

    > [!Note] 
    > A Dynamics 365 for Finance and Operations csak egy építőelem-csoportot támogat, az **Alapértelmezett** csoportot.
    
3.  Válassza ki a jelentésdefiníciókat az exportáláshoz:
    -   Az összes jelentésdefiníció illetve a társított építőelemek exportálásához kattintson az **Összes kijelölése** lehetőségre.
    -   Konkrét jelentések, sorok, oszlopok, fák vagy dimenziókészletek exportálásához kattintson a megfelelő lapra, majd válassza ki az exportálandó tételeket. Ha több tételt szeretne kijelölni egy lapon, nyomja le és tartsa lenyomva a Ctrl-billentyűt. Ha jelentéseket jelöl ki az exportálásához, a rendszer a társított sorokat, oszlopokat, fákat és dimenziókészleteket is kijelöli.

4.  Kattintson az **Exportálás** elemre.
5.  Adjon meg egy fájlnevet, és jelöljön ki egy biztonságos helyet, ahol menteni szeretné az exportált jelentésdefiníciókat.
6.  Kattintson a **Mentés** gombra.

A fájl másolhatók, illetve feltölthető egy biztonságos helyre, hogy később importálható legyen egy másik környezetbe. A Microsoft Azure tárolófiók használatával kapcsolatos információkért lásd: [Adatátvitel az AzCopy parancssori segédprogrammal](/azure/storage/storage-use-azcopy). 
> [!NOTE]
> A Dynamics 365 for Finance and Operations megállapodás részeként a Microsoft nem biztosít tárolófiókot. Be kell szereznie egy tárolófiókot, vagy egy külön Azure-előfizetésből származó tárolófiókot kell használnia. 
> [!WARNING]
> Legyen tisztában a D-meghajtó viselkedésével az Azure virtuális gépeken Ne tárolja itt véglegesen az exportált építőelem-csoportokat. További információt az ideiglenes meghajtókkal kapcsolatban itt talál: [A Windows Azure virtuális gépek ideiglenes meghajtóinak ismertetése](https://blogs.msdn.microsoft.com/mast/2013/12/06/understanding-the-temporary-drive-on-windows-azure-virtual-machines/).

## <a name="stop-services"></a>Szolgáltatások leállítása
A Távoli asztal segítségével csatlakozzon az összes számítógéphez a környezetében, és állítsa le a következő Windows-szolgáltatásokat a services.msc segítségével:

-   Webes közzétételi szolgáltatás (az összes AOS-számítógépen)
-   Microsoft Dynamics 365 for Finance and Operations Batch Management Service (csak a nem személyes AOS-számítógépeken)
-   Management Reporter 2012 Process Service (csak a BI-számítógépeken)

Ezek a szolgáltatások nyitott kapcsolattal rendelkeznek a Dynamics 365 for Finance and Operations-adatbázissal.

## <a name="reset"></a>Alaphelyzet
### <a name="locate-and-download-the-latest-minorversiondataupgradezip-package"></a>Keresse meg és töltse le a legújabb MinorVersionDataUpgrade.zip csomagot

Keresse meg a legújabb MinorVersionDataUpgrade.zip csomagot a következő utasításokkal: [A legfrissebb adatok frissítési telepíthető csomag letöltése](..\migration-upgrade\upgrade-data-to-latest-update.md#download-the-latest-data-upgrade-deployable-packages). Az utasítások ismertetik, hogyan keresse meg és töltse le az adatfrissítési csomag megfelelő verzióját. A MinorVersionDataUpgrade.zip csomag letöltéséhez nincs szükség frissítésre. A MinorVersionDataUpgrade.zip csomag másolatának visszaszerzéséhez végre kell hajtania „A legfrissebb adatok frissítési telepíthető csomag letöltése” rész lépéseit a többi lépés végrehajtása nélkül.

### <a name="execute-scripts-against-finance-and-operations-database"></a>Parancsfájl-műveletek végrehajtása a Dynamics 365 for Finance and Operations adatbázison

Futtassa a következő parancsfájlokat a Dynamics 365 for Finance and Operations adatbázison (nem pénzügyi jelentési adatbázison).

-   DataUpgrade.zip\\AosService\\Scripts\\ConfigureAxReportingIntegration.sql
-   DataUpgrade.zip\\AosService\\Scripts\\GrantAzViewChangeTracking.sql

Ezeket a parancsfájlok gondoskodnak arról, hogy helyesek legyenek a felhasználók, a szerepkörök és a változáskövetési beállítások.

### <a name="execute-powershell-command-to-reset-database"></a>Adatbázis alaphelyzetbe állításához PowerShell-parancs végrehajtása

Az AOS-számítógépen a PowerShellben rendszergazdaként hajtsa végre a következő parancsot a Dynamics 365 for Finance and Operations és a pénzügyi jelentéskészítés közti integráció alaphelyzetbe állításához:

```
F:
cd F:\MRApplicationService\MRInstallDirectory
Import-Module .\Server\MRDeploy\MRDeploy.psd1
Reset-DatamartIntegration -Reason OTHER -ReasonDetail “<my reason for resetting>”

```
> [!NOTE]
> A parancsok végrehajtását követően adja meg az „Y”-t megerősítésként.

A paraméterek magyarázata:

-   A -Reason érvényes értékei: SERVICING, BADDATA, OTHER.
-   A -ReasonDetail paraméter szabad szöveg.
-   A távmérő/környezet felügyelete végzi az ok és reasonDetail rögzítését.

## <a name="start-services"></a>Szolgáltatások indítása
A korábban leállított szolgáltatások újraindításához használja a Services.msc parancsot:

-   Webes közzétételi szolgáltatás (az összes AOS-számítógépen)
-   Microsoft Dynamics 365 for Finance and Operations Batch Management Service (csak a nem személyes AOS-számítógépeken)
-   Management Reporter 2012 Process Service (csak a BI-számítógépeken)

## <a name="import-report-definitions"></a>Jelentésdefiníciók importálása
Importálja a jelentésterveket a Jelentéstervezőből, az exportálás során létrehozott fájl használatával:

1.  A Jelentéstervezőben kattintson a **Vállalat** &gt; **Építőelem-csoportok** lehetőségére.
2.  Válassza ki az exportálandó építőelem-csoportot, majd kattintson az **Export** lehetőségre. 

    > [!NOTE]
    > A Dynamics 365 for Finance and Operations csak egy építőelem-csoportot támogat, az **Alapértelmezett** csoportot.
    
3.  Válassza ki az **Alapértelmezett** építőelemet, és kattintson az **Importálás** lehetőségre.
4.  Válassza ki az exportált jelentésdefiníciókat tartalmazó fájlt, és kattintson a **Megnyitás** lehetőségre.
5.  Jelölje ki az importálandó jelentésdefiníciókat az Importálás párbeszédpanelben:
    -   Az összes jelentésdefiníció illetve az azt támogató építőelemek importálásához kattintson az **Összes kijelölése** lehetőségre.
    -   Konkrét jelentések, sorok, oszlopok, fák vagy dimenziókészletek importálásához válassza ki az importálandó jelentéseket, sorokat, oszlopokat, fákat vagy dimenziókészleteket.

6.  Kattintson az **Importálás** gombra.





