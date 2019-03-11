---
title: Költségkontroll mobil munkaterület
description: Ez a témakör a Költségellenőrzés mobil munkaterületről nyújt tájékoztatást. A munkaterület lehetővé teszi a költséghelyek vezetői számára, hogy bármikor és bárhol megtekinthessék a költséghely teljesítményével kapcsolatos információkat.
author: AndersGirke
manager: AnnBe
ms.date: 12/01/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 267114
ms.assetid: 612f2988-b2b9-420d-9825-40b99dc0e204
ms.search.region: global
ms.author: aevengir
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: b6cdb69f32de2118e685c149605d50b78105c098
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2019
ms.locfileid: "317568"
---
# <a name="cost-controlling-mobile-workspace"></a>Költségkontroll mobil munkaterület

[!include [banner](../includes/banner.md)]

Ez a témakör a **Költségellenőrzés** mobil munkaterületről nyújt tájékoztatást. A munkaterület lehetővé teszi a költséghelyek vezetői számára, hogy bármikor és bárhol megtekinthessék a költséghely teljesítményével kapcsolatos információkat.

A mobil munkaterületet a Microsoft Dynamics 365 for Unified Operations Mobile alkalmazásban való használatra tervezték.

## <a name="overview"></a>Áttekintés
A **Költségkontroll** mobil munkaterületen azonnal megtekinthető a költséghelyek aktuális teljesítménye, és a tényleges költségek összevethetők a tervezett költségekkel. Az egyes költségtényezők állapotáig leáshat.

Például egy alkalmazott meghívót kap egy nemzetközi konferenciára, de a szervezetnek fedeznie kell az utazási költségeket. Az alkalmazott megkérdezi a vezetőjét, hogy részt vehet-e a konferencián. A vezető megnyitja a **Költségkontroll** mobil munkaterületet a mobiltelefonján, és megnézi, hogy van-e költségvetése ahhoz, hogy az alkalmazott részt vehessen a konferencián.

### <a name="data-security"></a>Adatbiztonság
A **Költségkontroll** mobil munkaterület adatait felhasználói hitelesítő adatok védik. A költséghely vezetői csak a saját költséghelyük adatait láthatják. A hozzáférési szint biztonságának kezelése a **Költségkönyvelési** modulon belül történik.

A **Költségkontroll** mobil munkaterület konfigurációját a költségkönyvelők határozzák meg a **Költségkönyvelés** modulban. A munkaterület a mobilalkalmazásban való közzététele után elérhetővé válik az alkalmazásban. Ennek következtében a szervezet összes költséghelyének vezetője ugyanabban a formátumban láthatja az adatokat.

### <a name="actions-views-and-links"></a>Műveletek, nézetek és hivatkozások
A **Költségellenőrzés** mobil munkaterület a következő műveleteket, nézeteket és hivatkozásokat biztosítja:

-   **Műveletek:**

    -   Használja a **Konfiguráció kiválasztása** lehetőséget az elrendezés kiválasztásához.
    -   Használja a **Költségobjektum kiválasztása** elemet azon költséghelyek kiválasztásához, amelyek adatait szűrni szeretné.
    
        > [!NOTE]
        > A listában megjelenő költséghelyek attól függnek, hogy milyen hozzáférést engedélyezett a **Költségkönyvelés** modulban.

-   **Nézetek:** Annak alapján, hogy milyen műveletek vannak kiválasztva, és milyen a **Költségkönyvelés** modul konfigurációja, a következő információkat tekintheti meg a kártyákon:

    -   Tényleges kontra költségvetés (aktuális időszak)
    -   Tényleges kontra módosított költségvetés (aktuális időszak)
    -   Tényleges és költségvetési (előző időszak)
    -   Tényleges és módosított költségvetési (előző időszak)
    -   Tényleges és költségvetési (folyó év mai napig)
    -   Tényleges és módosított költségvetési (folyó év mai napig)

    A következő összegek jelennek meg minden kártyán: a Tényleges, Költségvetés, Eltérés és Eltérés %.

-   **Hivatkozások:**

    -   Aktuális időszak részletei
    -   Előző időszak részletei
    -   Folyó év mai dátumig részletei

    Ha kiválaszt egy hivatkozást, egy kártya jelenik meg minden egyes költségösszetevőhöz. A kártyákon a következő összegek jelennek meg: Aktuális, Költségvetés, Költségvetés eltérése, Költségvetés eltérése %, Módosított költségvetés, Módosított költségvetés eltérése és Módosított költségvetés eltérése %.
    
    [![Kártya költségösszetevőhöz ](./media/Cost-controlling.png)](./media/Cost-controlling.png)

## <a name="prerequisites"></a>Előfeltételek
Az előfeltételek eltérnek a Microsoft Dynamics 365 szervezeténél megvalósított verziójától függően.

### <a name="prerequisites-if-you-use-microsoft-dynamics-365-for-finance-and-operations"></a>Előfeltételek a Microsoft Dynamics 365 for Finance and Operations használatakor
Amennyiben szervezete telepítette a Microsoft Dynamics 365 for Finance and Operations rendszert, a rendszergazdának közzé kell tennie a **Költségkontroll** mobil munkaterület. Utasításokért lásd: [Mobil munkaterület közzététele](../../dev-itpro/mobile-apps/publish-mobile-workspace.md).

### <a name="prerequisites-if-you-use-microsoft-dynamics-365-for-operations-version-1611-with-platform-update-3-or-later"></a>Előfeltételek a Microsoft Dynamics 365 for Operations1611-es verzió és platform update 3 vagy újabb használatakor
Amennyiben szervezete telepítette a Microsoft Dynamics 365 for Operations 1611-es verziójánnak 3. vagy újabb platformfrissítését, a rendszergazdának végre kell hajtania a következő előfeltételeket.

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

<td>A 4013633-es tudásbáziscikk egy X++-frissítés vagy metaadat-gyorsjavítás, amely tartalmazza a <strong>Költségellenőrzés</strong> mobil munkaterületet. A KB 4013633 végrehajtásához a rendszergazdának követnie kell az alábbi lépéseket.
<ol>
<li><a href="../../dev-itpro/migration-upgrade/download-hotfix-lcs.md">Metaadat-gyorsjavítások letöltése a Microsoft Dynamics Lifecycle Services (LCS) szolgáltatásból</a>.</li>
<li><a href="../../dev-itpro/migration-upgrade/install-metadata-hotfix-package.md">Telepítse a metaadatok gyorsjavítását</a>.</li>
<li><a href="../../dev-itpro/deployment/create-apply-deployable-package.md">Hozzon létre egy telepíthető csomagot</a>, amely tartalmazza a <strong>SCMMobile</strong> modellt, majd töltse fel a telepíthető csomagot az LCS-be.</li>
<li><a href="../../dev-itpro/deployment/apply-deployable-package-system.md">Alkalmazza telepíthető csomagot</a>.</li>

</ol></td>
</tr>
<tr class="even">
<td>Tegye közzé a <strong>Költségellenőrzés</strong> mobil munkaterületet.</td>
<td>Rendszergazda</td>
<td>Lásd: <a href="../../dev-itpro/mobile-apps/publish-mobile-workspace.md">Mobil munkaterület közzététele</a>.</td>
</tr>
</tbody>
</table>


## <a name="download-and-install-the-mobile-app"></a>A mobilalkalmazás letöltése és telepítése
Töltse le és telepítse a Dynamics 365 for Unified Operations mobilalkalmazást:

-   [Android telefonok esetében:](https://go.microsoft.com/fwlink/?linkid=850662)
-   [iPhone esetében:](https://go.microsoft.com/fwlink/?linkid=850663)

## <a name="sign-in-to-the-mobile-app"></a>Bejelentkezés a mobilalkalmazásba

1.  Indítsa el az alkalmazást a mobileszközén.
2.  Adja meg a Dynamics 365 URL-címét.
3.  Az első bejelentkezéskor a rendszer kéri a felhasználónevet és jelszót. Adja meg a hitelesítési adatait.
4.  A bejelentkezést követően megjelennek a vállalata rendelkezésre álló munkaterületek. Vegye figyelembe, hogy ha a rendszergazda később teszi közzé az új munkaterületet, akkor Önnek frissítenie kell a mobil munkaterületek listáját.

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

