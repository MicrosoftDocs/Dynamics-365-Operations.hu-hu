---
title: "Aktuális készlet mobil munkaterület"
description: "Ez a témakör az Aktuális készlet mobil munkaterülettel kapcsolatban tartalmaz tájékoztatást. A munkaterület segítségével bármikor és bárhol, mobilon tájékozódhat a fenntartott és a rendelkezésre álló készletről."
author: Mirzaab
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 267094
ms.assetid: 3fa385ba-894d-4a9e-b394-ef3697abf895
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: mirzaab
ms.dyn365.ops.intro: Version 1611
ms.search.validFrom: 2016-11-30
ms.translationtype: HT
ms.sourcegitcommit: 04d459a2fd0fdf9c201d9e96b37234846eb9ccf0
ms.openlocfilehash: 1029b9f041f318577779658650e07d8377823fea
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---

# <a name="inventory-on-hand-mobile-workspace"></a>Aktuális készlet mobil munkaterület

[!include[banner](../includes/banner.md)]

Ez a témakör az **Aktuális készlet** mobil munkaterülettel kapcsolatban tartalmaz tájékoztatást. A munkaterület segítségével bármikor és bárhol tájékozódhat a fenntartott és a rendelkezésre álló készletről.

A mobil munkaterületet a Microsoft Dynamics 365 for Unified Operations mobilalkalmazásban való használatra tervezték.

## <a name="overview"></a>Áttekintés
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
Az előfeltételek eltérőek a Microsoft Dynamics 365 szervezeténél megvalósított verziójától függően.

### <a name="prerequisites-if-you-use-microsoft-dynamics-365-for-finance-and-operations-enterprise-edition-july-2017"></a>Előfeltételek, ha a Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition kiadást használja (2017. július) 
Amennyiben szervezete telepítette a Microsoft Dynamics 365 for Finance and Operations Enterprise edition (2017. július) rendszert, a rendszergazdának közzé kell tennie az **Aktuális készlet** mobil munkaterületet. Utasításokért lásd: [Mobil munkaterület közzététele](../../dev-itpro/mobile-apps/publish-mobile-workspace.md).

### <a name="prerequisites-if-you-use-microsoft-dynamics-365-for-operations-version-1611-with-platform-update-3-or-later"></a>Előfeltételek, ha a Microsoft Dynamics 365 for Finance and Operations, 1611-es verzióját használja a 3-as vagy újabb platformfrissítéssel
Ha a Microsoft Dynamics 365 for Operations 1611-es verzióját telepítették a szervezeténél a 3-as vagy újabb platformfrissítéssel, akkor a rendszergazdának a következő előfeltételeket kell teljesítenie. 

<table>
<thead>
<tr class="header">
<th>Előfeltételek</th>
<th>Szerep</th>
<th>Leírás</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Telepítse a KB 4013633 programot.</td>
<td>Rendszergazda</td>

<td>A KB 4013633 egy X++-frissítés vagy metaadat-gyorsjavítás, amely tartalmazza az <strong>Aktuális készlet</strong> mobil munkaterületet. A KB 4013633 végrehajtásához a rendszergazdának követnie kell az alábbi lépéseket.
<ol>
<li><a href="../../dev-itpro/migration-upgrade/download-hotfix-lcs.md">Töltse le a metaadatok gyorsjavítását a Microsoft Dynamics Lifecycle Services (LCS) szolgáltatásból</a>.</li>
<li><a href="../../dev-itpro/migration-upgrade/install-metadata-hotfix-package.md">Telepítse a metaadatok gyorsjavítását</a>.</li>
<li><a href="../../dev-itpro/deployment/create-apply-deployable-package.md">Hozzon létre egy telepíthető csomagot</a>, amely tartalmazza a <strong>SCMMobile</strong> modellt, majd töltse fel a telepíthető csomagot az LCS-be.</li>
<li><a href="../../dev-itpro/deployment/apply-deployable-package-system.md">Alkalmazza telepíthető csomagot</a>.</li>

</ol></td>
</tr>
<tr class="even">
<td><strong>Aktuális készlet</strong> mobil munkaterület közzététele.</td>
<td>Rendszergazda</td>
<td>Lásd: <a href="../../dev-itpro/mobile-apps/publish-mobile-workspace.md">Mobil munkaterület közzététele</a>.</td>
</tr>
</tbody>
</table>

## <a name="download-and-install-the-mobile-app"></a>A mobilalkalmazás letöltése és telepítése

Töltse le és telepítse a Dynamics 365 for Unified Operations mobilalkalmazást:

-   [Android-telefonok esetében:](https://go.microsoft.com/fwlink/?linkid=850662)
-   [iPhone esetében:](https://go.microsoft.com/fwlink/?linkid=850663)

## <a name="sign-in-to-the-mobile-app"></a>Bejelentkezés a mobilalkalmazásba

1.  Indítsa el az alkalmazást a mobileszközén.
2.  Adja meg a Dynamics 365 URL-címét.
3.  Az első bejelentkezéskor a rendszer kéri a felhasználónevet és jelszót. Adja meg a hitelesítési adatait.
4.  A bejelentkezést követően megjelennek a vállalata rendelkezésre álló munkaterületek. Vegye figyelembe, hogy ha a rendszergazda később teszi közzé az új munkaterületet, akkor Önnek frissítenie kell a mobil munkaterületek listáját.

    [![Lekérés frissítéshez](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)

## <a name="view-the-on-hand-inventory-for-a-product-by-using-the-inventory-on-hand-mobile-workspace"></a>A termék aktuális készletének megtekintése az Aktuális készlet mobil munkaterület segítségével

1.  A mobileszközön válassza az **Aktuális készlet** munkaterület.

2.  Válassza az **Aktuális ellenőrzése egy cikkhez** lehetőséget. Megjelenik a kapcsolat nélküli használatra az alkalmazásba betöltött termékek listája. Alapértelmezés szerint 50 elem töltődik be, de a fejlesztő módosíthatja ezt a számot. További információért a fejlesztők tekintsék meg a következőt: [Mobil munkafelület](../../dev-itpro/mobile-apps/platform/mobile-platform-home-page.md)
3.  Ha a cikk nem szerepel a listán, válassza a **Továbbiak keresése** lehetőséget. Keressen termékszám alapján, vagy térjen át terméknévalapú keresésre.

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

