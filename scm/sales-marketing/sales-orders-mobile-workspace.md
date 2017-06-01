---
title: "Értékesítési rendelések mobil munkaterület"
description: "Ez a témakör az Értékesítési rendelések mobil munkaterületről nyújt tájékoztatást, amely a Microsoft Dynamics 365 for Operations mobilalkalmazásban érhető el. A munkaterület segítségével bármikor és bárhol is legyen, naprakész maradhat az értékesítési rendeléseivel kapcsolatban."
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
ms.custom: 267134
ms.assetid: 0ce96511-002b-4de7-b31e-4303f94edc84
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: mirzaab
ms.dyn365.ops.intro: Version 1611
ms.search.validFrom: 2016-11-30
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 11898146a13756a6bb22a769e37e8773484e0d04
ms.contentlocale: hu-hu
ms.lasthandoff: 05/25/2017


---

# <a name="sales-orders-mobile-workspace"></a>Értékesítési rendelések mobil munkaterület

[!include[banner](../includes/banner.md)]


Ez a témakör az Értékesítési rendelések mobil munkaterületről nyújt tájékoztatást, amely a Microsoft Dynamics 365 for Operations mobilalkalmazásban érhető el. A munkaterület segítségével bármikor és bárhol is legyen, naprakész maradhat az értékesítési rendeléseivel kapcsolatban. 

<a name="overview-of-the-sales-orders-mobile-workspace"></a>Az Értékesítési rendelések mobil munkaterület áttekintése
---------------------------------------------

Az **Értékesítési rendelések** mobil munkaterület hozzáfér a Microsoft Dynamics 365 for Operations szolgáltatáshoz, így Ön megtekintheti az egyes értékesítési rendelések részletes adatait. Ezek az információk magában foglalják a rendelés állapotát, az ügyfél kapcsolattartási információit és a rendelésfelvevő elérhetőségi adatait. Az **Értékesítési rendelések** mobil munkaterület azonnali rálátást biztosít az értékesítési rendelésekre. Megtekintheti az összes értékesítési rendelést, az értékesítési rendeléseket ügyfelek szerint, vagy megtekintheti egy adott értékesítési rendelés információit. 

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
Az **Értékesítési rendelések** mobil munkaterület használata előtt győződjön meg arról, hogy a rendszergazda biztosítja a következő előfeltételeket.

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
<td>Ha a vállalati hálózatra még nincs telepítve a Dynamics 365 for Operations, a rendszergazdának el kell olvasnia a következő tudnivalókat: <a href="/dynamics365/operations/dev-itpro/deployment/deploy-demo-environment/">Deploy a Microsoft Dynamics 365 for Operations demo environment</a>.</td>
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
<td>Az <strong>Értékesítési rendelések</strong> mobil munkaterületet közzé kell tenni a Dynamics 365 for Operations mobilalkalmazás számára.</td>
<td>Rendszergazda</td>
<td><ol>
<li>Indítsa el a Dynamics 365 for Operations rendszert a böngészőben.</li>
<li>A <strong>Rendszerparaméterek</strong> lapon válassza a <strong>Mobil munkaterületek kezelése</strong> lehetőséget.</li>
<li>Válassza ki a <strong>Értékesítési rendelések</strong> munkaterület.</li>
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

## <a name="view-information-about-sales-orders-for-a-customer-by-using-the-mobile-workspace"></a>A mobil munkaterület használatával megtekintheti az ügyfelek értékesítési rendelésekre vonatkozó adatait
1.  A mobileszközön válassza az **Értékesítési rendelések** munkaterület.
2.  Válassza ki a **Vevő rendeléseinek megtekintése** lehetőséget.
3.  Keresse ki a kívánt ügyfél adatait a Számla vagy a Vevő neve információknál.
4.  Válassza ki az ügyfelet.
5.  Válassza ki a **Kapcsolattartó adatai** vagy az **Értékesítési rendelések** lehetőséget. Az **Értékesítési rendelések** kiválasztása esetén megjelenik egy lista a vevő számára az értékesítési rendelésekről.
6.  Válassza ki az **Értékesítési rendelés** lehetőséget. Megtekintheti az értékesítési rendelések sorairól, a szállítmányokról, a vevői kapcsolattartási adatokról és a megrendelő elérhetőségéről szóló információkat.





