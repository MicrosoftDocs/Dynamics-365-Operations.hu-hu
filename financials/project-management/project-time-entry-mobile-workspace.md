---
title: "Projektidő megadása mobil munkaterület a Dynamics 365 for Operations alkalmazás számára"
description: "Ez a témakör a Projektidő megadása mobil munkaterülettel kapcsolatban tartalmaz tájékoztatást. Ez a munkaterület lehetővé teszi a felhasználók számára, hogy beírhassák az időt, és időt takaríthassanak meg egy projektnél mobileszközük használatával."
author: annbe
manager: AnnBe
ms.date: 04/21/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: annbe
ms.search.scope: Operations, Core
ms.custom: 272101
ms.assetid: 4505f021-b9bb-4b87-be24-6bf0bd88ee60
ms.search.region: Global
ms.search.industry: Service industries
ms.author: annbe
ms.dyn365.ops.intro: Version 1611
ms.search.validFrom: 2016-11-30
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: e3e0be36c045acc3750efbb739d79d81ab937c65
ms.contentlocale: hu-hu
ms.lasthandoff: 04/25/2017


---

# <a name="project-time-entry-mobile-workspace"></a>Projektidő megadása mobil munkaterület

[!include[banner](../includes/banner.md)]

"[!include[banner](../includes/banner.md)]"


Ez a témakör a Projektidő megadása mobil munkaterületről nyújt tájékoztatást, amely a Dynamics 365 for Operations mobilalkalmazásban érhető el. Ez a munkaterület lehetővé teszi a felhasználók számára, hogy beírhassák az időt, és időt takaríthassanak meg egy projektnél mobileszközük használatával.

<a name="overview-of-the-project-time-entry-mobile-workspace"></a>A Projektidő megadása mobil munkaterület áttekintése
---------------------------------------------------

Napi munkájuk részeként a projektek résztvevői gyakran a helyszínen dolgoznak, vagy az utazáson vesznek részt. A **Projektidő megadása** mobil munkaterület lehetővé teszi a felhasználók számára, hogy számlázható vagy nem számlázható időt írjanak be projektjükhöz a választott mobileszközön. Ezért a projekt résztvevői bármikor és bárhol rögzíthetik az időbevitelt. Megtekinthetik a már rögzített időbejegyzéseket is. 

A **Projektidő megadása** mobil munkaterület konkrétan az alábbi szolgáltatásokat nyújtja:

-   Bármelyik kiválasztott dátumhoz beírhatja az adott feladatra fordított órák számát.
-   Keresés projektnév vagy vevő alapján, hogy megtalálhassa a projektet, amelynél időt szeretne rögzíteni.
-   Adja meg az eltöltött időhöz tartozó kategóriát és tevékenységet.
-   Rögzítse az időt számlázhatóként vagy nem számlázhatóként a projektnél.
-   Nem kötelező: Adjon meg külső vagy belső megjegyzéseket.

A **Projektidő megadása** mobil munkaterület megadásához lásd a jelen témakör következő szakaszait.

## <a name="prerequisites"></a>Előfeltételek
A **Projektidő megadása** mobil munkaterület használata előtt győződjön meg arról, hogy a rendszergazda biztosítja a következő előfeltételeket.

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
<td>Ha a vállalati hálózatra még nincs telepítve a Dynamics 365 for Operations, rendszergazdájának el kell olvasnia a következő tudnivalókat: <a href="https://docs.microsoft.com/en-us/dynamics365/operations/dev-itpro/deployment/deploy-demo-environment">Deploy a Microsoft Dynamics 365 for Operations demo environment</a>.</td>
</tr>
<tr class="even">
<td>A KB 4018050 végrehajtása kötelező.</td>
<td>Rendszergazda</td>
<td>A 4018050-es tudásbáziscikk egy X++-frissítés vagy metaadat-gyorsjavítás, amely tartalmazza a <strong>Projektidő megadása</strong> mobil munkaterületet. A KB 4018050 végrehajtásához a rendszergazdának követnie kell az alábbi lépéseket.
<ol>
<li>Töltse le a KB 4018050 frissítést a Microsoft Dynamics Lifecycle Services (LCS) webhelyéről.</li>
<li><a href="https://docs.microsoft.com/en-us/dynamics365/operations/dev-itpro/migration-upgrade/install-metadata-hotfix-package">Telepítse a metaadatok gyorsjavítását</a>.</li>
<li><a href="https://docs.microsoft.com/en-us/dynamics365/operations/dev-itpro/deployment/create-apply-deployable-package">Hozzon létre egy telepíthető csomagot</a>, amely tartalmazza az <strong>ApplicationSuite</strong> és a <strong>ProjectMobile</strong> modellt, majd töltse fel a telepíthető csomagot az LCS-be.</li>
<li><a href="https://docs.microsoft.com/en-us/dynamics365/operations/dev-itpro/deployment/apply-deployable-package-system">Alkalmazza a telepíthető csomagot</a> és a Dynamics 365 for Operations rendszerre.</li>
</ol></td>
</tr>
<tr class="odd">
<td>A <strong>Projektidő megadása</strong> mobil munkaterületet közzé kell tenni a Dynamics 365 for Operations mobilalkalmazás számára.</td>
<td>Rendszergazda</td>
<td><ol>
<li>Indítsa el a Dynamics 365 for Operations rendszert a böngészőben.</li>
<li>A <strong>Rendszerparaméterek</strong> oldal <strong>Mobil munkaterületek kezelése</strong> lapján válassza ki a <strong>Projektidő megadása</strong> munkaterületet.</li>
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

## <a name="enter-time-by-using-the-project-time-entry-mobile-workspace"></a>Adja meg az időt a Projektidő megadása mobil munkaterület használatával
1.  A mobileszközön válassza a **Projektidő megadása** munkaterület.
2.  Válassza ki az **Időbejegyzés** lehetőséget. Ekkor az aktuális hét naptári dátumait láthatja.
3.  Válassza ki a kijelölt dátumnál a **Műveletek** &gt; **Új bejegyzés** pontot.
4.  Adja meg a rögzítendő órák számát.
5.  Jelölje ki a projektet az időbejegyzéshez. Megjelenik a kapcsolat nélküli használatra az alkalmazásba betöltött projektek listája. Alapértelmezés szerint 50 elem töltődik be, de a fejlesztő módosíthatja ezt a számot. További információért lásd a [Dynamics 365 for Operations mobilplatformot](/dynamics365/operations/dev-itpro/mobile-apps/mobile-platform).
6.  Ha a projekt nem szerepel a listán, válassza a **Keresés** elemet a Dynamics 365 for Operationsben végzett online keresés érdekében. Végezhet név szerinti keresést, vagy átválthat a projektnév vagy ügyfél szerinti keresésre.
7.  Válasszon egy kategóriát. Megjelenik a kapcsolat nélküli használatra az alkalmazásba betöltött kategóriák listája. Alapértelmezés szerint 50 elem töltődik be, de a fejlesztő módosíthatja ezt a számot. További információért lásd a [Dynamics 365 for Operations mobilplatformot](/dynamics365/operations/dev-itpro/mobile-apps/mobile-platform).
8.  Ha a kategória nem szerepel a listán, válassza a **Keresés** elemet a Dynamics 365 for Operationsben végzett online keresés érdekében. Keressen kategória szerint, vagy váltson át a kategórianév szerinti keresésre.
9.  Válasszon ki egy tevékenységet. Megjelenik a kapcsolat nélküli használatra az alkalmazásba betöltött tevékenységek listája. Alapértelmezés szerint 50 elem töltődik be, de a fejlesztő módosíthatja ezt a számot. További információért lásd a [Dynamics 365 for Operations mobilplatformot](/dynamics365/operations/dev-itpro/mobile-apps/mobile-platform).
10. Ha a tevékenység nem szerepel a listán, válassza a **Keresés** elemet a Dynamics 365 for Operationsben végzett online keresés érdekében. Keressen tevékenységszám szerint, vagy váltson át a cél szerinti keresésre.
11. Válassza ki a sortulajdonságot.
12. Nem kötelező: Adjon meg külső vagy belső megjegyzéseket.
13. Válassza a **Kész** lehetőséget.






