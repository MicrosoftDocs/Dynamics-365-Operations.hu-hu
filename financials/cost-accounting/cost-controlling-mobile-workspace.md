---
title: "Költségkontroll mobil munkaterület"
description: "Ez a témakör a Költségkontroll mobil munkaterületről nyújt tájékoztatást, amely a Microsoft Dynamics 365 for Operations mobilalkalmazásban érhető el. A munkaterület lehetővé teszi a költséghelyek vezetői számára, hogy bármikor és bárhol megtekinthessék a költséghely teljesítményével kapcsolatos információkat."
author: YuyuScheller
manager: AnnBe
ms.date: 05/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.reviewer: annbe
ms.search.scope: Operations, Core
ms.custom: 267114
ms.assetid: 612f2988-b2b9-420d-9825-40b99dc0e204
ms.search.region: global
ms.author: yuyus
ms.dyn365.ops.intro: Version 1611
ms.search.validFrom: 2016-11-30
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: 31a9650774b2ddb70827ffa210154ca10c761236
ms.contentlocale: hu-hu
ms.lasthandoff: 04/25/2017


---

# <a name="cost-controlling-mobile-workspace"></a>Költségkontroll mobil munkaterület

[!include[banner](../includes/banner.md)]


Ez a témakör a Költségkontroll mobil munkaterületről nyújt tájékoztatást, amely a Microsoft Dynamics 365 for Operations mobilalkalmazásban érhető el. A munkaterület lehetővé teszi a költséghelyek vezetői számára, hogy bármikor és bárhol megtekinthessék a költséghely teljesítményével kapcsolatos információkat. 

<a name="overview-of-the-cost-controlling-mobile-workspace"></a>A Költségkontroll mobil munkaterület áttekintése
-------------------------------------------------

A **Költségkontroll** mobil munkaterületen azonnal megtekinthető a költséghelyek aktuális teljesítménye, és a tényleges költségek összevethetők a tervezett költségekkel. Az egyes költségtényezők állapotáig leáshat. Például egy alkalmazott meghívót kap egy nemzetközi konferenciára, de a szervezetnek fedeznie kell az utazási költségeket. Az alkalmazott megkérdezi a vezetőjét, hogy részt vehet-e a konferencián. A vezető megnyitja a **Költségkontroll** mobil munkaterületet a mobiltelefonján, és megnézi, hogy van-e költségvetése ahhoz, hogy az alkalmazott részt vehessen a konferencián.

### <a name="data-security"></a>Adatbiztonság

A **Költségkontroll** mobil munkaterület adatait felhasználói hitelesítő adatok védik. A költséghely vezetői csak a saját költséghelyük adatait láthatják. A hozzáférési szint biztonságának kezelése a **Költségkönyvelési** modulon belül történik. A **Költségkontroll** mobil munkaterület konfigurációját a költségkönyvelők határozzák meg a **Költségkönyvelés** modulban. A munkaterület a Microsoft Dynamics 365 for Operations mobilalkalmazásban való közzététele után elérhetővé válik az alkalmazásban. Ennek következtében a szervezet összes költséghelyének vezetője ugyanabban a formátumban láthatja az adatokat.

### <a name="actions-views-and-links"></a>Műveletek, nézetek és hivatkozások

A Dynamics 365 for Operations alkalmazás **Költségkontroll** mobil munkaterülete a következő műveleteket, nézeteket és hivatkozásokat biztosítja:

-   **Műveletek:**
    -   Használja a **Konfiguráció kiválasztása** lehetőséget az elrendezés kiválasztásához.
    -   Használja a **Költségobjektum kiválasztása** elemet azon költséghelyek kiválasztásához, amelyek adatait szűrni szeretné. **Megjegyzés:** a listában megjelenő költséghelyek attól függnek, hogy milyen hozzáférést engedélyezett a **Költségkönyvelés** modulban.
-   **Nézetek:** Annak alapján, hogy milyen műveletek vannak kiválasztva, és milyen a **Költségkönyvelés** modul konfigurációja, a következő információkat tekintheti meg a kártyákon.
    -   Tényleges és költségvetési (aktuális időszak)
    -   Tényleges és módosított költségvetési (aktuális időszak)
    -   Tényleges és költségvetési (előző időszak)
    -   Tényleges és módosított költségvetési (előző időszak)
    -   Tényleges és költségvetési (folyó év mai napig)
    -   Tényleges és módosított költségvetési (folyó év mai napig)

    A következő összegek jelennek meg minden kártyán: a Tényleges, Költségvetés, Eltérés és Eltérés (%).
-   **Hivatkozások:**
    -   Aktuális időszak részletei
    -   Előző időszak részletei
    -   Folyó év mai dátumig részletei

    Ha kiválaszt egy hivatkozást, egy kártya jelenik meg minden egyes költségösszetevőhöz. A kártyákon a következő összegek jelennek meg: Aktuális, Költségvetés, Költségvetés eltérése, Költségvetés eltérése (%), Módosított költségvetés, Módosított költségvetés eltérése és Módosított költségvetés eltérése (%). 
    
    [![Kártya költségösszetevőhöz ](./media/cost-controlling.png)](./media/cost-controlling.png)

## <a name="prerequisites"></a>Előfeltételek
A **Költségkontroll** mobil munkaterület használata előtt győződjön meg arról, hogy a rendszergazda biztosítja a következő előfeltételeket.

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
<td>Dynamics 365 for Operations 1611-es verziójához 3. vagy újabb platformfrissítését kell végrehajtani.</td>
<td>Rendszergazda</td>
<td>Ha a vállalati hálózatra még nincs telepítve a Dynamics 365 for Operations, a rendszergazdának el kell olvasnia a következő tudnivalókat: <a href="http://ax.help.dynamics.com/en/wiki/deploy-an-ax7-demo-environment/">Deploy a Microsoft Dynamics 365 for Operations demo environment</a>.</td>
</tr>
<tr class="even">
<td>A KB 4013633 végrehajtása kötelező.</td>
<td>Rendszergazda</td>
<td>A KB 4013633 (egy X++ frissítés vagy a metaadatok gyorsjavítása) négy mobil munkaterületet tartalmaz az ellátásilánc-kezeléshez. A KB 4013633 végrehajtásához a rendszergazdának követnie kell az alábbi lépéseket:
<ol>
<li>Töltse le a KB 4013633 frissítést a Microsoft Dynamics Lifecycle Services (LCS) webhelyéről.</li>
<li><a href="https://ax.help.dynamics.com/en/wiki/configuring-and-installing-a-metadata-hotfix-package/">Telepítse a metaadatok gyorsjavítását</a>.</li>
<li><a href="https://ax.help.dynamics.com/en/wiki/create-and-apply-a-deployable-package/">Hozzon létre egy telepíthető csomagot</a>, amely tartalmazza a <strong>SCMMobile</strong> modellt, majd töltse fel a telepíthető csomagot az LCS-be.</li>
<li><a href="https://ax.help.dynamics.com/en/wiki/apply-a-deployable-package-on-a-dynamics-ax-system/">Alkalmazza a telepíthető csomagot</a> és a Dynamics 365 for Operations rendszerre.</li>
</ol></td>
</tr>
<tr class="odd">
<td>A <strong>Költségkontroll</strong> mobil munkaterületet közzé kell tenni a Dynamics 365 for Operations mobilalkalmazás számára.</td>
<td>Rendszergazda</td>
<td><ol>
<li>Indítsa el a Dynamics 365 for Operations rendszert a böngészőben.</li>
<li>A <strong>Rendszerparaméterek</strong> lapon válassza a <strong>Mobil munkaterületek kezelése</strong> lehetőséget.</li>
<li>Válassza ki a <strong>Költségobjektum-áttekintés</strong> munkaterületet.</li>
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

## <a name="view-the-performance-of-your-cost-center-by-using-the-cost-controlling-mobile-workspace"></a>A költséghely teljesítményének megtekintése a Költségkontroll mobil munkaterület segítségével
1.  A mobileszközön válassza a **Költségkontroll** munkaterület.
2.  Válassza a **Költségobjektum-kontroll** elemet.
3.  Válassza a **Műveletek** lehetőséget.
4.  Válassza a **Konfiguráció kiválasztása** elemet egy költségkontroll-elrendezés kiválasztásához.
5.  Válassza a **Kész** lehetőséget.
6.  Válassza a **Műveletek** lehetőséget.
7.  Válassza a **Költségobjektum kiválasztása** elemet, és válassza ki a költséghelyeket, amelyekhez hozzáférése van.
8.  Válassza a **Kész** lehetőséget.
9.  Tekintse meg a költséghely összteljesítményét.
10. Válassza az **Aktuális időszak részletei** hivatkozást.
11. Tekintse meg az egyedi költségelemek teljesítményét.
12. Konkrét költségelemekre is kereshet.





