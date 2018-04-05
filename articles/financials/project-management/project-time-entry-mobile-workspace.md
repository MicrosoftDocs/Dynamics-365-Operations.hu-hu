---
title: "Projektidő megadása mobil munkaterület"
description: "Ez a témakör a Projektidő megadása mobil munkaterülettel kapcsolatban tartalmaz tájékoztatást. Ez a munkaterület lehetővé teszi a felhasználók számára, hogy beírhassák az időt, és időt takaríthassanak meg egy projektnél mobileszközük használatával."
author: KimANelson
manager: AnnBe
ms.date: 12/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 272101
ms.assetid: 4505f021-b9bb-4b87-be24-6bf0bd88ee60
ms.search.region: Global
ms.search.industry: Service industries
ms.author: knelson
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: 9bf79af6eea6f899158fc3c8d523587cb11c90ad
ms.contentlocale: hu-hu
ms.lasthandoff: 03/26/2018

---

# <a name="project-time-entry-mobile-workspace"></a>Projektidő megadása mobil munkaterület

[!include[banner](../includes/banner.md)]

Ez a témakör a **Projektidő megadása** mobil munkaterülettel kapcsolatban tartalmaz tájékoztatást. Ez a munkaterület lehetővé teszi a felhasználók számára, hogy beírhassák az időt, és időt takaríthassanak meg egy projektnél mobileszközük használatával.

A mobil munkaterületet a Microsoft Dynamics 365 for Unified Operations mobilalkalmazásban való használatra tervezték. 

## <a name="overview"></a>Áttekintés
Napi munkájuk részeként a projektek résztvevői gyakran a helyszínen dolgoznak, vagy az utazáson vesznek részt. A **Projektidő megadása** mobil munkaterület lehetővé teszi a felhasználók számára, hogy számlázható vagy nem számlázható időt írjanak be projektjükhöz a választott mobileszközön. Ezért a projekt résztvevői bármikor és bárhol rögzíthetik az időbevitelt. Megtekinthetik a már rögzített időbejegyzéseket is. 

A **Projektidő megadása** mobil munkaterületen a felhasználók a következő feladatokat hajthatják végre:

-   Bármelyik kiválasztott dátumhoz beírhatja az adott feladatra fordított órák számát.
-   Keresés projektnév vagy vevő alapján, hogy megtalálhassa a projektet, amelynél időt szeretne rögzíteni.
-   Adja meg az eltöltött időhöz tartozó kategóriát és tevékenységet.
-   Rögzítse az időt számlázhatóként vagy nem számlázhatóként a projektnél.
-   Nem kötelező: Adjon meg külső vagy belső megjegyzéseket.

## <a name="prerequisites"></a>Előfeltételek
Az előfeltételek eltérőek a Microsoft Dynamics 365 szervezeténél megvalósított verziójától függően.

### <a name="prerequisites-if-you-use-microsoft-dynamics-365-for-finance-and-operations"></a>Előfeltételek, ha a Microsoft Dynamics 365 for Finance and Operations rendszert használja
Amennyiben szervezete telepítette a Microsoft Dynamics 365 for Finance and Operations rendszert, a rendszergazdának közzé kell tennie a **Projektidő megadása** mobil munkaterület. Utasításokért lásd: [Mobil munkaterület közzététele](../../dev-itpro/mobile-apps/publish-mobile-workspace.md).

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

<td>Telepítse a KB 4018050 programot.</td>
<td>Rendszergazda</td>
<td>A 4018050-es tudásbáziscikk egy X++-frissítés vagy metaadat-gyorsjavítás, amely tartalmazza a <strong>Projektidő megadása</strong> mobil munkaterületet. A KB 4018050 végrehajtásához a rendszergazdának követnie kell az alábbi lépéseket.
<ol>
<li><a href="../../dev-itpro/migration-upgrade/download-hotfix-lcs.md">Töltse le a metaadatok gyorsjavítását a Microsoft Dynamics Lifecycle Services (LCS) szolgáltatásból</a>.</li>
<li><a href="../../dev-itpro/migration-upgrade/install-metadata-hotfix-package.md">Telepítse a metaadatok gyorsjavítását</a>.</li>
<li><a href="../../dev-itpro/deployment/create-apply-deployable-package.md">Hozzon létre egy telepíthető csomagot</a>, amely tartalmazza az <strong>ApplicationSuite</strong> és a <strong>ProjectMobile</strong> modellt, majd töltse fel a telepíthető csomagot az LCS-be.</li>
<li><a href="../../dev-itpro/deployment/apply-deployable-package-system.md">Alkalmazza telepíthető csomagot</a>.</li>

</ol></td>
</tr>
<tr class="even">
<td>Tegye közzé a <strong>Projektidő megadása</strong> mobil munkaterületet.</td>
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

## <a name="enter-time-by-using-the-project-time-entry-mobile-workspace"></a>Adja meg az időt a Projektidő megadása mobil munkaterület használatával
1.  A mobileszközön válassza a **Projektidő megadása** munkaterület.
2.  Válassza ki az **Időbejegyzés** lehetőséget. Megjelennek az aktuális hét naptári dátumai.
3.  Válassza ki a kijelölt dátumnál a **Műveletek** &gt; **Új bejegyzés** pontot.
4.  Adja meg a rögzítendő órák számát.
5.  Jelölje ki a projektet az időbejegyzéshez. Megjelenik a kapcsolat nélküli használatra az alkalmazásba betöltött projektek listája. Alapértelmezés szerint 50 elem töltődik be, de a fejlesztő módosíthatja ezt a számot. További információ: lásd: [Mobil munkafelület](../../dev-itpro/mobile-apps/platform/mobile-platform-home-page.md)
6.  Ha a projekt nem szerepel a listán, válassza a **Keresés** lehetőséget. Végezhet név szerinti keresést, vagy átválthat a projektnév vagy ügyfél szerinti keresésre.
7.  Válasszon egy kategóriát. Megjelenik a kapcsolat nélküli használatra az alkalmazásba betöltött kategóriák listája. Alapértelmezés szerint 50 elem töltődik be, de a fejlesztő módosíthatja ezt a számot. További információ: lásd: [Mobil munkafelület](../../dev-itpro/mobile-apps/platform/mobile-platform-home-page.md)
8.  Ha a kategória nem szerepel a listán, válassza a **Keresés** lehetőséget. Keressen kategória szerint, vagy váltson át a kategórianév szerinti keresésre.
9.  Válasszon ki egy tevékenységet. Megjelenik a kapcsolat nélküli használatra az alkalmazásba betöltött tevékenységek listája. Alapértelmezés szerint 50 elem töltődik be, de a fejlesztő módosíthatja ezt a számot. További információ: lásd: [Mobil munkafelület](../../dev-itpro/mobile-apps/platform/mobile-platform-home-page.md)
10. Ha a tevékenység nem szerepel a listán, válassza a **Keresés** lehetőséget. Keressen tevékenységszám szerint, vagy váltson át a cél szerinti keresésre.

11. Válassza ki a sortulajdonságot.
12. Nem kötelező: Adjon meg külső vagy belső megjegyzéseket.
13. Válassza a **Kész** lehetőséget.

