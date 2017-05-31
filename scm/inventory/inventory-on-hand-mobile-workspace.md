---
title: "Aktuális készlet mobil munkaterület"
description: "Ez a témakör az Aktuális készlet mobil munkaterületről nyújt tájékoztatást, amely a Microsoft Dynamics 365 for Operations mobilalkalmazásban érhető el. A munkaterület segítségével bármikor és bárhol, mobilon tájékozódhat a fenntartott és a rendelkezésre álló készletről."
author: YuyuScheller
manager: AnnBe
ms.date: 05/10/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: annbe
ms.search.scope: Operations, Core
ms.custom: 267094
ms.assetid: 3fa385ba-894d-4a9e-b394-ef3697abf895
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: mirzaab
ms.dyn365.ops.intro: Version 1611
ms.search.validFrom: 2016-11-30
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 7387df37e047d5ab7a90b696a6ffa249094499c4
ms.contentlocale: hu-hu
ms.lasthandoff: 05/25/2017


---

# <a name="inventory-on-hand-mobile-workspace"></a>Aktuális készlet mobil munkaterület

[!include[banner](../includes/banner.md)]


Ez a témakör az Aktuális készlet mobil munkaterületről nyújt tájékoztatást, amely a Microsoft Dynamics 365 for Operations mobilalkalmazásban érhető el. A munkaterület segítségével bármikor és bárhol, mobilon tájékozódhat a fenntartott és a rendelkezésre álló készletről.

<a name="overview-of-the-inventory-on-hand-mobile-workspace"></a>Az Aktuális készlet mobil munkaterület áttekintése
--------------------------------------------------

Általában a cégek készleténél több szállításra és bevételezésre kerül sor mindennap. Ezek a mozgások folyamatosan módosítják az aktuális készlet állapotát. Az **Aktuális készlet** mobil munkaterület segítségével átláthatja a több vállalatot érintő aktuális készlet állapotát, így tetszés szerinti a mobileszközön a legfrissebb adatok alapján tájékozódhat a készletadatokról. Függetlenül attól, hogy a raktárban, beszerzésnél, értékesítésben, gyártásban vagy a vezetőségben dolgozik-e, vagy más szerepkörrel rendelkezik, az aktuális készletadatokat bárhol és bármikor elérheti. 

A mobil munkaterületen azonnal megtekinthető az aktuális, különböző létesítményeket felölelő állapot. Továbbá megtekinthető a különböző létesítményeket felölelő aktuális készlet, az aktuális anyagfoglalások és a le nem foglalt aktuális készlet. Ezenkívül az aktuális készlet cikkszámok megadásával lekérdezhető, és az aktuális termékekre vagy változatokra szűrt keresés végezhető. 

A mobil munkaterület konkrétan az alábbi szolgáltatásokat nyújtja:

-   Kereshet terméktípus és termék neve alapján termékeket, és megtekintheti a rájuk vonatkozó aktuális készletállapotot.

-   A kijelölt termékeknél a következő információkat tekintheti meg:
    -   Aktuális készlet telephely szerint
    -   Aktuális készlet raktár szerint
    -   Aktuális készlet hely szerint
    -   Aktuális készlet köteg szerint (kötegvezérelt termékeknél)
    -   Aktuális készlet készlet állapota szerint
    
-   Az aktuális termékkészlet az alábbi módon jelenik meg:
    -   Fizikai készlet alapján (Ez a nézet a teljes mennyiséget jelöli.)
    -   Fizikai fenntartott alapján (Ez a nézet a fenntartott mennyiséget jelöli.)
    -   Elérhető fizikai alapján (Ez a nézet a rendelkezésre álló, nem fenntartott mennyiséget jelöli.)

## <a name="prerequisites"></a>Előfeltételek
Az **Aktuális készlet** mobil munkaterület használata előtt győződjön meg arról, hogy a rendszergazda biztosítja a következő előfeltételeket.

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
<td>Ha a vállalati hálózatra még nincs telepítve a Dynamics 365 for Operations, a rendszergazdának el kell olvasnia a következő tudnivalókat: <a href="/dynamics365/operations/dev-itpro/deployment/deploy-demo-environment">Deploy a Microsoft Dynamics 365 for Operations demo environment</a>.</td>
</tr>
<tr class="even">
<td>A KB 4013633 végrehajtása kötelező.</td>
<td>Rendszergazda</td>
<td>A KB 4013633 (egy X++ frissítés vagy a metaadatok gyorsjavítása) négy mobil munkaterületet tartalmaz az ellátásilánc-kezeléshez. A KB 4013633 végrehajtásához a rendszergazdának követnie kell az alábbi lépéseket:
<ol>
<li>Töltse le a KB 4013633 frissítést a Microsoft Dynamics Lifecycle Services (LCS) webhelyéről.</li>
<li><a href="/dynamics365/operations/dev-itpro/migration-upgrade/install-metadata-hotfix-package">Telepítse a metaadatok gyorsjavítását</a>.</li>
<li><a href="/dynamics365/operations/dev-itpro/deployment/create-apply-deployable-package">Hozzon létre egy telepíthető csomagot</a>, amely tartalmazza a <strong>SCMMobile</strong> modellt, majd töltse fel a telepíthető csomagot az LCS-be.</li>
<li><a href="/dynamics365/operations/dev-itpro/deployment/apply-deployable-package-system">Alkalmazza a telepíthető csomagot</a> és a Dynamics 365 for Operations rendszerre.</li>
</ol></td>
</tr>
<tr class="odd">
<td>Az <strong>Aktuális készlet</strong> mobil munkaterületet közzé kell tenni a Dynamics 365 for Operations mobilalkalmazás számára.</td>
<td>Rendszergazda</td>
<td><ol>
<li>Indítsa el a Dynamics 365 for Operations rendszert a böngészőben.</li>
<li>A <strong>Rendszerparaméterek</strong> lapon válassza a <strong>Mobil munkaterületek kezelése</strong> lehetőséget.</li>
<li>Válassza ki az <strong>Aktuális készlet</strong> munkaterületet.</li>
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

## <a name="view-the-onhand-inventory-for-a-product-by-using-the-inventory-onhand-mobile-workspace"></a>A termék aktuális készletének megtekintése az Aktuális készlet mobil munkaterület segítségével
1.  A mobileszközön válassza az **Aktuális készlet** munkaterület.
2.  Válassza az **Aktuális ellenőrzése egy cikkhez** lehetőséget. Megjelenik a kapcsolat nélküli használatra az alkalmazásba betöltött termékek listája. Alapértelmezés szerint 50 elem töltődik be, de a fejlesztő módosíthatja ezt a számot. További információért lásd a [Dynamics 365 for Operations mobilplatformot](/dynamics365/operations/dev-itpro/mobile-apps/mobile-platform).
3.  Ha a cikk nem szerepel a listán, válassza a **Továbbiak keresése** elemet a Dynamics 365 for Operationsben végzett online keresés érdekében. Keressen termékszám alapján, vagy térjen át terméknévalapú keresésre.
4.  Válasszon ki egy terméket. Ha a cikkhez tartozik kép, a kép megjelenik.
5.  Az aktuális készlet állapotának megjelenítéséhez a következő lehetőségek közül választhat:
    -   Aktuális megjelenítése telephely szerint
    -   Aktuális megjelenítése raktár szerint
    -   Aktuális megjelenítése hely szerint
    -   Aktuális megjelenítése köteg szerint (kötegvezérelt termékeknél)
    -   Aktuális megjelenítése készletállapot szerint

    Az aktuális termékkészlet az alábbi módon jelenik meg:
    -   Fizikai készlet alapján (Ez a nézet a teljes mennyiséget jelöli.)
    -   Fizikai fenntartott alapján (Ez a nézet a fenntartott mennyiséget jelöli.)
    -   Elérhető fizikai alapján (Ez a nézet a rendelkezésre álló, nem fenntartott mennyiséget jelöli.)






