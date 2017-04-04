---
title: "A pénzügyi jelentési adatok Intelligens bekezdéskijelölés visszaállítása után az adatbázis visszaállítása"
description: "Ez a témakör ismerteti a Microsoft Dynamics 365 műveletek adatbázis visszaállítása után a pénzügyi jelentési adatok Intelligens bekezdéskijelölés visszaállítása."
author: twheeloc
manager: AnnBe
ms.date: 2016-12-08 16 - 20 - 13
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
translationtype: Human Translation
ms.sourcegitcommit: 4d6cf88788dcc5e982e509137aa444a020137a5e
ms.openlocfilehash: 3967cbb869fbb23d5d7716f619e4c22b4a273921
ms.lasthandoff: 03/29/2017


---

# <a name="reset-the-financial-reporting-data-mart-after-restoring-a-database"></a>A pénzügyi jelentési adatok Intelligens bekezdéskijelölés visszaállítása után az adatbázis visszaállítása

Ez a témakör ismerteti a Microsoft Dynamics 365 műveletek adatbázis visszaállítása után a pénzügyi jelentési adatok Intelligens bekezdéskijelölés visszaállítása. 

Van szükség, ahol a Dynamics 365 műveletek adatbázis visszaállítása biztonsági másolatból, vagy az adatbázis másolása másik környezet különböző okokból. Ilyenkor is hajtsa végre a megfelelő lépéseket annak biztosítására, hogy a pénzügyi jelentési adatok Intelligens bekezdéskijelölés megfelelően használja a visszaállított 365 Dynamics műveletek adatbázis szükséges. Ha a pénzügyi jelentési adatok Intelligens bekezdéskijelölés okból kívül a Dynamics 365 műveletek adatbázis visszaállítása alapértelmezettre kérdése van, olvassa el a [alaphelyzetbe állítása a Management Reporter adatok Intelligens bekezdéskijelölés](https://blogs.msdn.microsoft.com/dynamics_financial_reporting/2016/06/28/resetting-the-management-reporter-data-mart/) további információt. Vegye figyelembe, hogy a folyamat lépései Dynamics 365 művelet támogatott május 2016 kiadás (App build 7.0.1265.23014 és pénzügyi jelentési build 7.0.10000.4) és az újabb verziókban. Ha egy korábbi verziója Dynamics 365 műveletekhez, lépjen kapcsolatba támogatási csoportunkhoz segítségért.

## <a name="export-report-definitions"></a>A jelentésdefiníciók exportálása
Először exportálja a jelentés formatervezési minták a Report Designer, a következő lépésekkel található:

1.  A Report Designer go **vállalat**&gt;**építőelem csoportok**.
2.  Válassza ki az építőelem exportálása, majd kattintson **Export**. **Megjegyzés:** a Dynamics 365 műveletekhez, csak egy építőelem csoport támogat, **alapértelmezett**.
3.  Válassza ki a jelentésdefiníció exportálása:
    -   Az összes jelentésdefiníció illetve a társított építőelemek exportálásához kattintson az **Összes kijelölése** lehetőségre.
    -   Konkrét jelentések, sorok, oszlopok, fák vagy dimenziókészletek exportálásához kattintson a megfelelő lapra, majd válassza ki az exportálandó tételeket. Ha több cikket szeretne kijelölni egy lapon, nyomja le és tartsa lenyomva a Ctrl-billentyűt. Jelentések exportálása választásakor a kapcsolódó sorok, oszlopok, fák és a Dimenziókészletek jelöltünk ki.

4.  Kattintson a **Export**.
5.  Adjon meg egy fájlnevet, és jelöljön ki egy biztonságos helyre, ahol szeretné menteni az exportált jelentésdefiníciók.
6.  Click **Save**.

A fájl másolhatók, illetve biztonságos helyre, hogy később importálható különböző környezeti feltöltve. A Microsoft Azure tároló fiók használatával kapcsolatos információ található a [adatátvitel és a AzCopy parancssori segédprogram](https://docs.microsoft.com/en-gb/azure/storage/storage-use-azcopy). **Megjegyzés:** a Microsoft nem nyújt a tároló fiók a Dynamics 365 részeként megállapodás műveleteket. A tároló fiókok beszerzés, vagy egy külön Azure előfizetésből tároló fiók használata. **Fontos:** tudják, hogy a D meghajtó Azure virtuális gépek viselkedését. Az exportált építőelem csoportok Itt ne véglegesen. További információt az ideiglenes meghajtók, lásd: [ismertetése a Windows Azure virtuális gépek ideiglenes meghajtó](https://blogs.msdn.microsoft.com/mast/2013/12/06/understanding-the-temporary-drive-on-windows-azure-virtual-machines/).

## <a name="stop-services"></a>Szolgáltatások leállítása
A távoli asztal segítségével csatlakozni a számítógépeknek a környezetében, és a következő Windows-szolgáltatások leállítása services.msc segítségével:

-   Webes közzététel szolgáltatás (az összes AOS-számítógépen)
-   A Microsoft Dynamics 365 műveletek kötegelt Management szolgáltatás (a nem személyes AOS számítógépek)
-   Management Reporter 2012 folyamat szolgáltatás (csak a számítógépeken BI)

Ezeket a szolgáltatásokat fogja a Dynamics 365 műveletek adatbázis megnyitott kapcsolattal rendelkeznek.

## <a name="reset"></a>Alaphelyzet
#### <a name="locate-the-latest-dataupgradezip-package"></a>Keresse meg a legújabb DataUpgrade.zip csomag

Keresse meg a legújabb DataUpgrade.zip csomagot, található utasításokat a [a DataUpgrade.zip parancsfájl letöltése](..\migration-upgrade\upgrade-data-to-latest-update.md). A használati utasítás keresse meg az adatok frissítési csomag a környezetnek megfelelő verzióját ismertetik.

#### <a name="execute-scripts-against-dynamics-365-for-operations-database"></a>Parancsfájl-műveletek adatbázis Dynamics 365 ellen végrehajtása

Futtassa a következő parancsfájlok a Dynamics 365 műveletek adatbázis (nem pénzügyi jelentési adatbázis) ellen.

-   DataUpgrade.zip\\AosService\\parancsfájlok\\ConfigureAxReportingIntegration.sql
-   DataUpgrade.zip\\AosService\\parancsfájlok\\GrantAzViewChangeTracking.sql

Ezeket a parancsfájlokat győződjön meg arról, hogy a felhasználók, szerepkörök és Változáskövetési beállítások helyesek.

#### <a name="execute-powershell-command-to-reset-database"></a>Adatbázis alaphelyzetbe PowerShell parancs végrehajtása

Közvetlenül az AOS-számítógéphez Dynamics 365 műveletekre és a pénzügyi beszámolás együttműködéséhez alaphelyzetbe hajtsa végre a következő parancsot:

1.  Nyissa meg a Windows PowerShell rendszergazdaként.
2.  Végrehajtás: F:
3.  Végrehajtani: F: cd\\MRApplicationService\\MRInstallDirectory
4.  Végrehajtás: Import-Module. \\Server\\MRDeploy\\MRDeploy.psd1
5.  Végrehajtás: Reset-DatamartIntegration-egyéb okból - ReasonDetail "&lt;alaphelyzetbe állítása a okát&gt;"
    -   Adja meg az "Y" megerősítését fogja kérni.

Paraméterek magyarázata:

-   Az érvényes értékek-oka van: karbantartás, BADDATA, egyéb.
-   A - ReasonDetail paraméter nem szabad szöveg.
-   A távmérő és a környezetre felügyelete okát és reasonDetail lesznek rögzítve.

## <a name="start-services"></a>Szolgáltatások indítása
A korábban leállított szolgáltatások újraindításához Services.msc parancsot használja:

-   Webes közzététel szolgáltatás (az összes AOS-számítógépen)
-   A Microsoft Dynamics 365 műveletek kötegelt Management szolgáltatás (a nem személyes AOS számítógépek)
-   Management Reporter 2012 folyamat szolgáltatás (csak a számítógépeken BI)

## <a name="import-report-definitions"></a>A jelentésdefiníciók importálása
A jelentés formatervezési minták importálása a Report Designer, az exportálás során létrehozott fájl használata:

1.  A Report Designer go **vállalat**&gt;**építőelem csoportok**.
2.  Válassza ki az építőelem exportálása, majd kattintson **Export**. **Megjegyzés:** a Dynamics 365 műveletekhez, csak egy építőelem csoport támogat, **alapértelmezett**.
3.  Válassza ki a **alapértelmezett** blokk, és kattintson **importálás**.
4.  Válassza ki az exportált jelentés meghatározásokat tartalmazó fájlt és kattintson **nyitott**.
5.  Jelölje ki az importálandó jelentésdefiníciókat az Importálás párbeszédpanelben:
    -   Az összes jelentésdefiníció illetve az azt támogató építőelemek importálásához kattintson az **Összes kijelölése** lehetőségre.
    -   Konkrét jelentések, sorok, oszlopok, fák vagy dimenziókészletek importálásához válassza ki az importálandó jelentéseket, sorokat, oszlopokat, fákat vagy dimenziókészleteket.

6.  Click **Import**.



