---
title: "Költségkezelés mobil munkaterület"
description: "Ez a témakör a Költségkezelés mobil munkaterületről nyújt tájékoztatást, amely a Microsoft Dynamics 365 for Operations mobilalkalmazásban érhető el. A munkaterület segítségével a felhasználók nyugtákat rögzíthetnek, majd tölthetnek fel annak érdekében, hogy később egy költségjelentéshez csatolhassák őket. A mobil munkaterület azt is lehetővé teszi a felhasználók számára, hogy gyorsan létrehozzanak egy kiadási sort egy mellékelt nyugta segítségével."
author: annbe
manager: AnnBe
ms.date: 04/10/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: end user, IT Pro
ms.reviewer: annbe
ms.search.scope: Operations
ms.custom: 274023
ms.assetid: 3605eda1-a7ed-4675-8031-5279c5a8f5e4
ms.search.region: Global
ms.author: annbe
ms.dyn365.ops.intro: Version 1611
ms.search.validFrom: 2016-11-30
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 4e3202de8e5288bbd52e8c28922374de147cc99f
ms.contentlocale: hu-hu
ms.lasthandoff: 05/25/2017


---

# <a name="expense-management-mobile-workspace"></a>Költségkezelés mobil munkaterület

[!include[banner](../includes/banner.md)]


Ez a témakör a Költségkezelés mobil munkaterületről nyújt tájékoztatást, amely a Microsoft Dynamics 365 for Operations mobilalkalmazásban érhető el. A munkaterület segítségével a felhasználók nyugtákat rögzíthetnek, majd tölthetnek fel annak érdekében, hogy később egy költségjelentéshez csatolhassák őket. A mobil munkaterület azt is lehetővé teszi a felhasználók számára, hogy gyorsan létrehozzanak egy kiadási sort egy mellékelt nyugta segítségével.

<a name="overview-of-the-expense-management-mobile-workspace"></a>A Költséggazdálkodás mobil munkaterület áttekintése
---------------------------------------------------

Számos szervezet megköveteli, hogy a nyugta egy példányát csatolja az utazással kapcsolatos vagy az üzleti vonatkozású költségjelentéshez az alkalmazott, amikor visszatérítést igényel. A **Költséggazdálkodás** mobil munkaterület lehetővé teszi a felhasználók számára, hogy gyorsan új költségsorokat hozzanak létre a választott mobileszközön a nyugta csatolt fényképével. Alternatív megoldásként a felhasználók rögzíthetnek egy fényképet a nyugtáról, majd később egy költségjelentéshez csatolhatják azt. A **Költséggazdálkodás** mobil munkaterület a következőket teszi lehetővé egy felhasználó számára:

-   Készítsen fotót a nyugtáról, és töltse azt fel a Microsoft Dynamics 365 for Operations szolgáltatásba. A felhasználó később is csatolhatja a fotót a költségjelentéshez.
-   Fájl feltöltése rögzített nyugtaként. A felhasználó később is csatolhatja a fájlt a költségjelentéshez.
-   Új költségsor létrehozása csatolt nyugta használatával. A felhasználó később is hozzáadhatja a sort a költségjelentéshez, majd beküldheti azt jóváhagyás és visszatérítés céljából.

A témakör fennmaradó szakaszai a **Költséggazdálkodás** mobil munkaterület megvalósítását és használatát mutatják be.

## <a name="prerequisites"></a>Előfeltételek
A **Költséggazdálkodás** mobil munkaterület használata előtt győződjön meg arról, hogy a rendszergazda biztosítja a következő előfeltételeket.

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Előfeltételek</th>
<th>Szerep</th>
<th>Leírás</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>A Microsoft Dynamics 365 for Operations 1611-es verziójához a 3. vagy újabb platformfrissítést kell végrehajtani.</td>
<td>Rendszergazda</td>
<td>Ha a vállalati hálózatra még nincs telepítve a Dynamics 365 for Operations, rendszergazdájának el kell olvasnia a következő tudnivalókat: <a href="/dynamics365/operations/dev-itpro/deployment/deploy-demo-environment">Deploy a Microsoft Dynamics 365 for Operations demo environment</a>.</td>
</tr>
<tr class="even">
<td>A KB 4019015 végrehajtása kötelező.</td>
<td>Rendszergazda</td>
<td>A KB 4019015 (egy X++ frissítés vagy a metaadatok gyorsjavítása) négy mobil munkaterületet tartalmaz az ellátásilánc-kezeléshez. A KB 4019015 végrehajtásához a rendszergazdának követnie kell az alábbi lépéseket:
<ol>
<li>Töltse le a KB 4019015 frissítést a Microsoft Dynamics Lifecycle Services (LCS) webhelyéről.</li>
<li><a href="/dynamics365/operations/dev-itpro/migration-upgrade/install-metadata-hotfix-package">Telepítse a metaadatok gyorsjavítását</a>.</li>
<li><a href="/dynamics365/operations/dev-itpro/deployment/create-apply-deployable-package">Hozzon létre egy telepíthető csomagot</a>, amely tartalmazza az <strong>ApplicationSuite</strong> és az <strong>ExpenseMobile</strong> modellt, majd töltse fel a telepíthető csomagot az LCS-be.</li>
<li><a href="/dynamics365/operations/dev-itpro/deployment/apply-deployable-package-system">Alkalmazza a telepíthető csomagot</a> és a Dynamics 365 for Operations rendszerre.</li>
</ol></td>
</tr>
<tr class="odd">
<td>A <strong>Költséggazdálkodás</strong> mobil munkaterületet közzé kell tenni a Dynamics 365 for Operations mobilalkalmazás számára.</td>
<td>Rendszergazda</td>
<td><ol>
<li>Indítsa el a Dynamics 365 for Operations rendszert a böngészőben.</li>
<li>A <strong>Rendszerparaméterek</strong> lapon válassza a <strong>Mobil munkaterületek kezelése</strong> lehetőséget.</li>
<li>Válassza ki a <strong>Költséggazdálkodás</strong> munkaterület.</li>
<li>Kattintson a <strong>Mobil munkaterület közzététele</strong> lehetőségre.</li>
</ol></td>
</tr>
</tbody>
</table>

## <a name="download-and-install-the-dynamics-365-for-operations-mobile-app"></a>Töltse le és telepítse a Dynamics 365 for Operations mobilalkalmazást
A mobiljához tartozó alkalmazásáruházból töltse le és telepítse a Microsoft Dynamics 365 for Operations mobilalkalmazást.

-   Android: [Dynamics 365 for Operations a Google Play Áruházban](https://play.google.com/store/apps/details?id=com.microsoft.dynamics365.operations.mobile)
-   iPhone: [Dynamics 365 az iTunes App Store áruházban](https://itunes.apple.com/us/app/dynamics-365-for-operations/id1180836730?mt=8)

## <a name="sign-in-to-the-dynamics-365-for-operations-mobile-app"></a>Jelentkezzen be a Dynamics 365 for Operations mobilalkalmazásba
1.  Indítsa el az alkalmazást a mobileszközén.
2.  Írja be a Dynamics_365_for_Operations URL-jét.
3.  Adja meg a vállalatot a bejelentkezéshez. Például írja be azt, hogy **USMF**.
4.  Az első bejelentkezéskor a rendszer kéri a felhasználónevet és jelszót a Dynamics 365 for Operations-fiókjához. Adja meg a hitelesítési adatait.
5.  A bejelentkezést követően megjelennek a vállalata rendelkezésre álló munkaterületek. Vegye figyelembe, hogy ha a rendszergazda később teszi közzé az új munkaterületet, lekéréssel frissítheti mobil munkaterületek listáját. 

[![Lekérés frissítéshez](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)

## <a name="capture-a-receipt-by-using-the-expense-management-mobile-workspace"></a>Nyugta rögzítése a Költséggazdálkodás mobil munkaterület használatával
1.  A mobileszközön válassza a **Költséggazdálkodás** munkaterület.
2.  Válassza a **Nyugta rögzítése** elemet.
3.  Válassza a **Fénykép készítése** vagy a **Kép kiválasztása** lehetőséget.
4.  Ha a **Fénykép készítése** lehetőséget választotta, kövesse az alábbi lépéseket:
    1.  Ekkor a mobileszköz kamerájához kerül, hogy fényképet készíthessen a nyugtáról. Amikor elkészült a fénykép, kattintson az **OK** lehetőségre a fénykép elfogadásához.
    2.  Nem kötelező: Adja meg a fénykép nevét, vagy írja be megjegyzéseit.

     **Ha pedig** a **Kép kiválasztása** lehetőséget választotta, kövesse az alábbi lépéseket:
    1.  A listából válasszon ki egy képet.
    2.  Nem kötelező: Adja meg a kép nevét, vagy írja be megjegyzéseit.

5.  Válassza a **Kész** lehetőséget.

## <a name="quick-expense-entry-by-using-the-expense-management-mobile-workspace"></a>Költségbejegyzés gyors rögzítése a Költséggazdálkodás mobil munkaterület használatával
1.  A mobileszközön válassza a **Költséggazdálkodás** munkaterület.
2.  Válassza ki a **Gyors költségbejegyzés** lehetőséget.
3.  Válassza ki a költség kategóriáját. Megjelenik a kapcsolat nélküli használatra az alkalmazásba betöltött költségkategóriák listája. Alapértelmezés szerint legfeljebb 50 elem töltődik be, de a fejlesztő módosíthatja ezt a számot. További információért lásd a [Dynamics 365 for Operations mobilplatformot](/dynamics365/operations/dev-itpro/mobile-apps/mobile-platform). Ha a kategória nem szerepel a listán, válassza a **Keresés** elemet a Dynamics 365 for Operationsben végzett online keresés érdekében. Keressen költségkategória szerint, vagy váltson át a költségtípus szerinti keresésre.
4.  Adja meg a költségtranzakció dátumát.
5.  Nem kötelező: Adjon kereskedőt a költséghez.
6.  Adja meg a költség összegét.
7.  Válassza ki az illeték pénznemét. Megjelenik a kapcsolat nélküli használatra az alkalmazásba betöltött pénznemkódok listája. Alapértelmezés szerint legfeljebb 400 pénznem töltődik be, de a fejlesztő módosíthatja ezt a számot. További információért lásd a [Dynamics 365 for Operations mobilplatformot](/dynamics365/operations/dev-itpro/mobile-apps/mobile-platform). Ha a Pénznem nem szerepel a listán, válassza a **Keresés** elemet a Dynamics 365 for Operationsben végzett online keresés érdekében. Keressen pénznem szerint, vagy váltson át a név szerinti keresésre.
8.  Válassza ki a **Fénykép készítése** vagy a **Kép kiválasztása** lehetőséget.
9.  Ha a **Fénykép készítése** lehetőséget választotta, akkor a mobileszköz kamerájához kerül, hogy fényképet készíthessen a nyugtáról. Amikor elkészült a fénykép, kattintson az **OK** lehetőségre a fénykép elfogadásához.  Ha pedig a **Kép kiválasztása** lehetőséget választotta, jelöljön ki egy képet a listán.
10. Válassza a **Kész** lehetőséget.






