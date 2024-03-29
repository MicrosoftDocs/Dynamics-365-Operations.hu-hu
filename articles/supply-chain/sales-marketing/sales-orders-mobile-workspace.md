---
title: Értékesítési rendelések mobil munkaterület
description: Ez a cikk az Értékesítési rendelések mobileszköz munkaterületről nyújt tájékoztatást. A munkaterület segítségével bármikor és bárhol is legyen, naprakész maradhat az értékesítési rendeléseivel kapcsolatban.
author: Henrikan
ms.date: 05/24/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: 267134
ms.assetid: 0ce96511-002b-4de7-b31e-4303f94edc84
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: henrikan
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: 38971f2a5f3f3d2692de0e52365e2215170101cc
ms.sourcegitcommit: 12b3dbee905f8b2eb2e6c383c822a0fc9fccf063
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/01/2022
ms.locfileid: "9103180"
---
# <a name="sales-orders-mobile-workspace"></a>Értékesítési rendelések mobil munkaterület

[!include [banner](../includes/banner.md)]
[!include [mobile app deprecation](../../fin-ops-core/dev-itpro/includes/mobile-app-deprecation-banner.md)]

Ez a cikk az Értékesítési rendelések mobileszköz **munkaterületről** nyújt tájékoztatást. A munkaterület segítségével bármikor és bárhol is legyen, naprakész maradhat az értékesítési rendeléseivel kapcsolatban. 

Ez a mobil munkaterület a Pénzügy és műveletek (Dynamics 365) mobilalkalmazással való használatra szolgál.

## <a name="overview"></a>Áttekintés
Az **Értékesítési rendelések** mobil munkaterület teszi lehetővé az egyes értékesítési rendeléssel kapcsolatos részletes információk megtekintését. Ezek az információk magában foglalják a rendelés állapotát, az ügyfél kapcsolattartási információit és a rendelésfelvevő elérhetőségi adatait. Az **Értékesítési rendelések** mobil munkaterület azonnali rálátást biztosít az értékesítési rendelésekre. Megtekintheti az összes értékesítési rendelést, az értékesítési rendeléseket ügyfelek szerint, vagy megtekintheti egy adott értékesítési rendelés információit. 

A mobil munkaterület két nézetet kínál, ahol részletesen elemezheti az értékesítési rendeléseket.

### <a name="view-all-sales-orders"></a>Összes értékesítési rendelés megtekintése
Ez a nézet az összes értékesítési rendelést megjeleníti.

-   A következő szűrők egyikének segítségével kiválaszthatja a megtekinteni kívánt értékesítési rendeléseket:

    -   Keresés értékesítési rendelés szerint
    -   Keresés vevői számla alapján
    -   Keresés vevő neve szerint
    -   Keresés állapot szerint
    -   Keresés kiadási állapot szerint
    -   Keresés a létrehozás dátuma és ideje alapján
    
-   A értékesítési rendelések kiválasztását követően megtekintheti az adott rendelések részleteit. Az alábbi adatokat is megjelenítheti:

    -   Ügyfél neve és címadatai
    -   Az értékesítési rendelés különböző dátumai, így például a kért szállítási dátum, valamint a megerősített szállítási dátum
    -   A rendelés felvevőjének kapcsolatfelvételi adatai
    -   Vevői kapcsolattartási adatok
    -   Rendeléssorok
    -   Szállítmányok, amelyek megmutatják, hogyan és mikor szállították ki az értékesítési rendelést

### <a name="view-orders-for-a-customer"></a>Vevő rendeléseinek megtekintése
Ez a nézet értékesítési rendeléseket jelenít meg vevőnként.

-   A következő szűrők segítségével tekintheti meg egy vevő rendeléseit:

    -   Keresés név szerint
    -   Keresés számla alapján

-   Miután kiválasztott egy ügyfelet, a következő információkat tekintheti meg:

    -   Vevő neve és csoportja
    -   Vevői kapcsolattartási adatok
    -   Vevői értékesítési rendelések és az értékesítési rendelések részletei:
    
        -   Ügyfél neve és címadatai
        -   Különböző értékesítésirendelés-dátumok
        -   A rendelés felvevőjének kapcsolatfelvételi adatai
        -   Vevői kapcsolattartási adatok
        -   Rendeléssorok
        -   Szállítmányok, amelyek megmutatják, hogyan és mikor szállították ki az értékesítési rendelést

## <a name="prerequisites"></a>Előfeltételek
Az előfeltételek eltérnek a Microsoft Dynamics 365 szervezeténél megvalósított verziójától függően.

### <a name="prerequisites-if-you-use-supply-chain-management"></a>Előfeltételek a Supply Chain Management használatakor 
Amennyiben szervezete telepítette a Supply Chain Management rendszert, a rendszergazdának közzé kell tennie az **Értékesítési rendelés** mobil munkaterületet. Utasításokért lásd: [Mobil munkaterület közzététele](../../fin-ops-core/dev-itpro/mobile-apps/publish-mobile-workspace.md).

### <a name="prerequisites-if-you-use-dynamics-365-for-operations-version-1611-with-platform-update-3-or-later"></a>Előfeltételek a Dynamics 365 for Operations1611-es verzió és platform update 3 vagy újabb használatakor
Amennyiben szervezete telepítette a Dynamics 365 for Operations 1611-es verziójánnak 3. vagy újabb platformfrissítését, a rendszergazdának végre kell hajtania a következő előfeltételeket. 

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

<td>A 4013633-es tudásbáziscikk egy X++-frissítés vagy metaadat-gyorsjavítás, amely tartalmazza az <strong>Értékesítési rendelések</strong> mobil munkaterületet. A KB 4013633 végrehajtásához a rendszergazdának követnie kell az alábbi lépéseket.
<ol>
<li><a href="/dynamics365/fin-ops-core/dev-itpro/migration-upgrade/download-hotfix-lcs">Metaadat-gyorsjavítások letöltése a Microsoft Dynamics Lifecycle Services (LCS) szolgáltatásból</a>.</li>
<li><a href="/dynamics365/fin-ops-core/dev-itpro/migration-upgrade/install-metadata-hotfix-package">Telepítse a metaadatok gyorsjavítását</a>.</li>
<li><a href="/dynamics365/fin-ops-core/dev-itpro/deployment/create-apply-deployable-package">Hozzon létre egy telepíthető csomagot</a>, amely tartalmazza a <strong>SCMMobile</strong> modellt, majd töltse fel a telepíthető csomagot az LCS-be.</li>
<li><a href="/dynamics365/fin-ops-core/dev-itpro/deployment/apply-deployable-package-system">Alkalmazza telepíthető csomagot</a>.</li>

</ol></td>
</tr>
<tr class="even">
<td>Tegye közzé az <strong>Értékesítési rendelések</strong> mobil munkaterületet.</td>
<td>Rendszergazda</td>
<td>Lásd: <a href="/dynamics365/fin-ops-core/dev-itpro/mobile-apps/publish-mobile-workspace">Mobil munkaterület közzététele</a>.</td>
</tr>
</tbody>
</table>

## <a name="download-and-install-the-mobile-app"></a>A mobilalkalmazás letöltése és telepítése
Töltse le és telepítse a Pénzügy és műveletek (Dynamics 365) mobilalkalmazást:

-   [Android telefonok esetében:](https://go.microsoft.com/fwlink/?linkid=850662)
-   [iPhone esetében:](https://go.microsoft.com/fwlink/?linkid=850663)

## <a name="sign-in-to-the-mobile-app"></a>Bejelentkezés a mobilalkalmazásba

1.  Indítsa el az alkalmazást a mobileszközén.
2.  Adja meg a Dynamics 365 URL-címét.
3.  Az első bejelentkezéskor a rendszer kéri a felhasználónevet és jelszót. Adja meg a hitelesítési adatait.
4.  A bejelentkezést követően megjelennek a vállalata rendelkezésre álló munkaterületek. Vegye figyelembe, hogy ha a rendszergazda később teszi közzé az új munkaterületet, akkor Önnek frissítenie kell a mobil munkaterületek listáját.

[![Frissítés húzással.](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)

## <a name="view-information-about-sales-orders-for-a-customer-by-using-the-sales-order-mobile-workspace"></a>Az Értékesítési rendelés mobil munkaterület használatával megtekintheti az ügyfelek értékesítési rendelésekre vonatkozó adatait

1.  A mobileszközön válassza az **Értékesítési rendelések** munkaterület.
2.  Válassza ki a **Vevő rendeléseinek megtekintése** lehetőséget.
3.  Keresse ki a kívánt ügyfél adatait a Számla vagy a Vevő neve információknál.
4.  Válassza ki az ügyfelet.
5.  Válassza ki a **Kapcsolattartó adatai** vagy az **Értékesítési rendelések** lehetőséget. Az **Értékesítési rendelések** kiválasztása esetén megjelenik egy lista a vevő számára az értékesítési rendelésekről.
6.  Válassza ki az **Értékesítési rendelés** lehetőséget. Megtekintheti az értékesítési rendelések sorairól, a szállítmányokról, a vevői kapcsolattartási adatokról és a megrendelő elérhetőségéről szóló információkat.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]

