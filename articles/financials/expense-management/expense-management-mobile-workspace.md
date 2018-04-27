---
title: "Költségkezelés mobil munkaterület"
description: "Ez a témakör a Költséggazdálkodás mobil munkaterülettel kapcsolatban tartalmaz tájékoztatást. A munkaterület segítségével a felhasználók nyugtákat rögzíthetnek, majd tölthetnek fel annak érdekében, hogy később egy költségjelentéshez csatolhassák őket. A felhasználók gyorsan létrehozhatnak költségsorokat egy mellékelt nyugta használatával, valamint létrehozhatják és kezelhetik költségjelentéseiket."
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
ms.custom: 274023
ms.assetid: 3605eda1-a7ed-4675-8031-5279c5a8f5e4
ms.search.region: Global
ms.author: knelson
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: 6f6add07a2426b1846cbeb9dee149a63f66f779e
ms.contentlocale: hu-hu
ms.lasthandoff: 03/26/2018

---

# <a name="expense-management-mobile-workspace"></a>Költségkezelési mobil munkaterület

[!INCLUDE [banner](../includes/banner.md)]

Ez a témakör a **Költséggazdálkodás** mobil munkaterülettel kapcsolatban tartalmaz tájékoztatást. A munkaterület segítségével a felhasználók nyugtákat rögzíthetnek, majd tölthetnek fel annak érdekében, hogy később egy költségjelentéshez csatolhassák őket. A felhasználók gyorsan létrehozhatnak költségsorokat egy mellékelt nyugta használatával, valamint létrehozhatják és kezelhetik költségjelentéseiket. Ezenkívül a jóváhagyók a **Költséggazdálkodás** mobil munkaterület segítségével megtekinthetik a hozzájuk rendelt költségjelentéseket, majd jóváhagyhatják vagy elutasíthatják az adott költségjelentéseket.


A mobil munkaterületet a Microsoft Dynamics 365 for Unified Operations mobilalkalmazásban való használatra tervezték.


## <a name="overview"></a>Áttekintés

Számos szervezet megköveteli, hogy a nyugta egy példányát csatolja az utazással kapcsolatos vagy az üzleti vonatkozású költségjelentéshez az alkalmazott, amikor visszatérítést igényel. A **Költséggazdálkodás** mobil munkaterület lehetővé teszi a felhasználók számára, hogy gyorsan új költségsorokat hozzanak létre a választott mobileszközön a nyugta csatolt fényképével. Alternatív megoldásként a felhasználók rögzíthetnek egy fényképet a nyugtáról, majd később egy költségjelentéshez csatolhatják azt. Az alkalmazottak maguk is létrehozhatják és kezelhetik a költségjelentéseiket, majd beküldhetik őket jóváhagyásra és visszatérítésre a mobileszközük használatával.


A **Költségkezelés** mobil munkaterület használatával a felhasználók a következő feladatokat hajthatják végre:

- Készítsen fotót a nyugtáról, és töltse azt fel a Microsoft Dynamics 365 for Finance and Operations szolgáltatásba. A fotót később is csatolhatja a költségjelentéshez.
- Fájl feltöltése rögzített nyugtaként. A fájlt később is csatolhatja a költségjelentéshez.
- Új költségsor létrehozása csatolt nyugta használatával. Később is hozzáadhatja a sort a költségjelentéshez, majd beküldheti azt jóváhagyás és visszatérítés céljából.

Amennyiben a Microsoft Dynamics 365 for Finance and Operations rendszert használja, a következő funkciók is elérhetők:

- Új költségjelentés készítése.
- Hitelkártya-tranzakciók és egyéb, korábban létrehozott költségek csatolása egy költségjelentéshez.
- Új költségek létrehozása egy költségjelentéshez.
- Nyugta csatolása egy költségjelentéshez tartozó bármely költséghez vagy fénykép készítése által, vagy egy rögzített nyugta képfájljának feltöltésével.
- A vállalat költségirányelveitől függően vendégek listáját is hozzáadhatja egy költséghez.
- A vállalat költségirányelveitől függően a költségek részletezése is lehetséges.
- Költségjelentés benyújtása jóváhagyásra és visszatérítésre.
- Jóváhagyhatja vagy elutasíthatja az olyan költségjelentéseket, amelyeknek Ön a hozzárendelt jóváhagyója.

## <a name="prerequisites"></a>Előfeltételek
Az előfeltételek eltérnek a Microsoft Dynamics 365 szervezeténél megvalósított verziójától függően.

### <a name="prerequisites-if-you-use-microsoft-dynamics-365-for-finance-and-operations"></a>Előfeltételek, ha a Microsoft Dynamics 365 for Finance and Operations rendszert használja 
Amennyiben szervezete telepítette a Microsoft Dynamics 365 for Finance and Operations rendszert, a rendszergazdának közzé kell tennie a **Költséggazdálkodás** mobil munkaterület. Utasításokért lásd: [Mobil munkaterület közzététele](../../dev-itpro/mobile-apps/publish-mobile-workspace.md).

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
<td>Telepítse a KB 4019015 programot.</td>
<td>Rendszergazda</td>
<td>A 4019015-es tudásbáziscikk egy X++-frissítés vagy metaadat-gyorsjavítás, amely tartalmazza a <strong>Költséggazdálkodás</strong> mobil munkaterületet. A KB 4019015 végrehajtásához a rendszergazdának követnie kell az alábbi lépéseket.
<ol>
<li><a href="../../dev-itpro/migration-upgrade/download-hotfix-lcs.md">Töltse le a metaadatok gyorsjavítását a Microsoft Dynamics Lifecycle Services (LCS) szolgáltatásból</a>.</li>
<li><a href="../../dev-itpro/migration-upgrade/install-metadata-hotfix-package.md">Telepítse a metaadatok gyorsjavítását</a>.</li>
<li><a href="../../dev-itpro/deployment/create-apply-deployable-package.md">Hozzon létre egy telepíthető csomagot</a>, amely tartalmazza az <strong>ApplicationSuite</strong> és az <strong>ExpenseMobile</strong> modelleket, majd töltse fel a telepíthető csomagot az LCS-be.</li>
<li><a href="../../dev-itpro/deployment/apply-deployable-package-system.md">Alkalmazza telepíthető csomagot</a>.</li>
</ol></td>
</tr>
<tr class="even">
<td>Tegye közzé a <strong>Költségkezelés</strong> mobil munkaterületet.</td>
<td>Rendszergazda</td>
<td>Lásd: <a href="../../dev-itpro/mobile-apps/publish-mobile-workspace.md">Mobil munkaterület közzététele</a>.</td>
</tr>
</tbody>
</table>

## <a name="download-and-install-the-dynamics-365-for-operations-mobile-app"></a>Töltse le és telepítse a Dynamics 365 for Operations mobilalkalmazást
Töltse le és telepítse a Dynamics 365 for Unified Operations mobilalkalmazást:

- [Android-telefonok esetében:](https://go.microsoft.com/fwlink/?linkid=850662)
- [iPhone esetében:](https://go.microsoft.com/fwlink/?linkid=850663)

## <a name="sign-in-to-the-mobile-app"></a>Bejelentkezés a mobilalkalmazásba
1. Indítsa el az alkalmazást a mobileszközén.
2. Adja meg a Dynamics 365 URL-címét.
4. Az első bejelentkezéskor a rendszer kéri a felhasználónevet és jelszót. Adja meg a hitelesítési adatait.
5. A bejelentkezést követően megjelennek a vállalata rendelkezésre álló munkaterületek. Vegye figyelembe, hogy ha a rendszergazda később teszi közzé az új munkaterületet, akkor Önnek frissítenie kell a mobil munkaterületek listáját.


[![Lekérés frissítéshez](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)

## <a name="capture-a-receipt-by-using-the-expense-management-mobile-workspace"></a>Nyugta rögzítése a Költséggazdálkodás mobil munkaterület használatával

1. A mobileszközön nyissa meg a **Költséggazdálkodás** munkaterület.
2. Válassza a **Nyugta rögzítése** elemet.
3. Válassza a **Fénykép készítése** vagy a **Kép kiválasztása** lehetőséget.
4. Tegye a következők egyikét:

    - Ha a **Fénykép készítése** lehetőséget választotta, kövesse az alábbi lépéseket:

        1. Ekkor a mobileszköz kamerájához kerül, hogy fényképet készíthessen a nyugtáról. Amikor elkészült a fénykép, válassza az **OK** lehetőséget a fénykép elfogadásához.
        2. Nem kötelező: Adja meg a fénykép nevét, vagy írja be megjegyzéseit.

    - Ha a **Kép kiválasztása** lehetőséget választotta, kövesse az alábbi lépéseket:

        1. A listából válasszon ki egy képet.
        2. Nem kötelező: Adja meg a kép nevét, vagy írja be megjegyzéseit.

5. Válassza a **Kész** lehetőséget.

## <a name="quickly-enter-expenses-by-using-the-expense-management-mobile-workspace"></a>Költségek gyors rögzítése a Költséggazdálkodás mobil munkaterület használatával
1. A mobileszközön nyissa meg a **Költséggazdálkodás** munkaterület.
2. Válassza ki a **Gyors költségbejegyzés** lehetőséget.
3. Válassza ki a költség kategóriáját. Megjelenik a kapcsolat nélküli használatra az alkalmazásba betöltött költségkategóriák listája. Alapértelmezés szerint 50 elem töltődik be, de a fejlesztő módosíthatja ezt a számot. További információért a fejlesztők tekintsék meg a következőt: [Mobil munkafelület](../../dev-itpro/mobile-apps/platform/mobile-platform-home-page.md) Ha a kategória nem szerepel a listán, válassza a **Keresés** lehetőséget az online kereséshez. Keressen költségkategória szerint, vagy váltson át a költségtípus szerinti keresésre.
4. Adja meg a költségtranzakció dátumát.
5. Nem kötelező: Adjon kereskedőt a költséghez.
6. Adja meg a költség összegét.
7. Válassza ki az illeték pénznemét. Megjelenik a kapcsolat nélküli használatra az alkalmazásba betöltött pénznemkódok listája. Alapértelmezés szerint 400 pénznem töltődik be, de a fejlesztő módosíthatja ezt a számot. További információért a fejlesztők tekintsék meg a következőt: [Mobil munkafelület](../../dev-itpro/mobile-apps/platform/mobile-platform-home-page.md) Ha a pénznem nem szerepel a listán, válassza a **Keresés** lehetőséget az online kereséshez. Keressen pénznem szerint, vagy váltson át a név szerinti keresésre.
8. Válassza a **Fénykép készítése** vagy a **Kép kiválasztása** lehetőséget.
9. Tegye a következők egyikét:

    - Ha a **Fénykép készítése** lehetőséget választotta, akkor a mobileszköz kamerájához kerül, hogy fényképet készíthessen a nyugtáról. Amikor elkészült a fénykép, válassza az **OK** lehetőséget a fénykép elfogadásához.
    - Ha a **Kép kiválasztása** lehetőséget választotta, jelöljön ki egy képet a listán.

10. Válassza a **Kész** lehetőséget.

## <a name="approve-an-expense-report-by-using-the-expense-management-mobile-workspace-if-you-use-the-july-2017-update"></a>A költségjelentések jóváhagyását a Költségkezelési mobil munkaterület segítségével is elvégezheti (ha a 2017. júliusi frissítést használja)
1. A mobileszközön nyissa meg a **Költséggazdálkodás** munkaterület.
2. A **Költségjóváhagyások** megmutatja a jóváhagyásra Önhöz rendelt költségjelentések számát. A szám körülbelül 30 percenként frissül. Válassza ki a **Költségjóváhagyások** lehetőséget.

    Megjelenik egy lista a jóváhagyásra Önhöz rendelt költségjelentésekkel.
    
3. Válasszon ki egy költségjelentést a költség részleteinek megtekintéséhez.
4. Válasszon ki egy költséget a részleteinek megtekintéséhez. A költségnél megjelenített információk tartalmazzák az összes nyugta, vendég és részletezés adatait.
5. A **Költségjelentés** oldalra visszatérve jóváhagyhatja vagy elutasíthatja a költségjelentést.
6. Adja meg a jóváhagyás műveletére vonatkozó esetleges megjegyzéseket.
7. Válassza a **Kész** lehetőséget.

## <a name="create-a-new-expense-report-and-submit-it-for-approval-by-using-the-expense-management-mobile-workspace-if-you-use-the-july-2017-update"></a>Hozzon létre egy új költségjelentést, és küldje be jóváhagyásra a Költségkezelési mobil munkaterület segítségével (ha a 2017. júliusi frissítést használja)
1. A mobileszközön nyissa meg a **Költséggazdálkodás** munkaterület.
2. Válassza ki a **Költségbejegyzés** lehetőséget.
3. Válassza az **Új jelentés** lehetőséget, vagy válasszon ki egy meglévő költségjelentést a listáról.
4. Az új költségjelentéseknék adja meg a célt és a további rendelkezésre álló adatokat. Ezek az információk változóak, attól függően, hogy milyen módon konfigurálták a Költséggazdálkodás modult a vállalatánál.
5. Válassza a **Kész** lehetőséget.
6. Meglévő költségek, mint a hitelkártya-tranzakciók költségjelentéshez való hozzáadásához válassza a **Csatolás** lehetőséget.
7. Jelöljön ki egy vagy több költséget a listán.
8. Válassza a **Kész** lehetőséget.
9. Ha új költséget szeretne hozzáadni a költségjelentéshez, válassza ki az **Új költség** lehetőséget.
10. Válassza ki a költség kategóriáját. Megjelenik a kapcsolat nélküli használatra az alkalmazásba betöltött költségkategóriák listája. Alapértelmezés szerint 50 elem töltődik be, de a fejlesztő módosíthatja ezt a számot. További információért a fejlesztők tekintsék meg a következőt: [Mobil munkafelület](../../dev-itpro/mobile-apps/platform/mobile-platform-home-page.md) Ha a kategória nem szerepel a listán, válassza a **Keresés** lehetőséget az online kereséshez. Keressen költségkategória szerint, vagy váltson át a költségtípus szerinti keresésre.
11. Nem kötelező: Adjon kereskedőt a költséghez.
12. Adja meg a költségtranzakció dátumát.
13. Adja meg a költség összegét.
14. Válassza ki az illeték pénznemét. Megjelenik a kapcsolat nélküli használatra az alkalmazásba betöltött pénznemkódok listája. Alapértelmezés szerint 400 pénznem töltődik be, de a fejlesztő módosíthatja ezt a számot. További információért a fejlesztők tekintsék meg a következőt: [Mobil munkafelület](../../dev-itpro/mobile-apps/platform/mobile-platform-home-page.md) Ha a pénznem nem szerepel a listán, válassza a **Keresés** lehetőséget az online kereséshez. Keressen pénznem szerint, vagy váltson át a név szerinti keresésre.
15. Válassza a **Kész** lehetőséget.
16. Ha további részleteket szeretne hozzáadni a költséghez, válassza ki a **További részletek hozzáadása** lehetőséget. A rendelkezésre álló mezők a Költséggazdálkodás Ön vállalatánál való konfigurációjától függnek.
17. Ha a vállalati irányelv nyugtát ír elő a költséghez, válassza ki a **Nyugták** lehetőséget, majd kövesse az alábbi lépéseket:

    1. Válassza ki a **Nyugta rögzítése** vagy a **Nyugta csatolása** lehetőséget.
    2. Tegye a következők egyikét:

        - Ha a **Nyugta rögzítése** lehetőséget választotta, kövesse az alábbi lépéseket:

            1. Válassza a **Fénykép készítése** vagy a **Kép kiválasztása** lehetőséget.
            2. Tegye a következők egyikét:

                - Ha a **Fénykép készítése** lehetőséget választotta, kövesse az alábbi lépéseket:

                    1. Ekkor a mobileszköz kamerájához kerül, hogy fényképet készíthessen a nyugtáról. Amikor elkészült a fénykép, válassza az **OK** lehetőséget a fénykép elfogadásához.
                    2. Nem kötelező: Adja meg a fénykép nevét, vagy írja be megjegyzéseit.

                - Ha a **Kép kiválasztása** lehetőséget választotta, kövesse az alábbi lépéseket:

                    1. A listából válasszon ki egy képet.
                    2. Nem kötelező: Adja meg a kép nevét, vagy írja be megjegyzéseit.

            3.  Válassza a **Kész** lehetőséget.

        - Ha a **Nyugta csatolása** lehetőséget választotta, kövesse az alábbi lépéseket:

            1.  Jelöljön ki egy vagy több képet a listán.
            2.  Válassza a **Kész** lehetőséget.

    3. Válassza ki a **Vissza** gombot a költségrészletekhez való visszatéréshez.

18. Ha a vállalati irányelv vendégeket ír elő a költséghez, válassza ki a **Vendégek** lehetőséget, majd kövesse az alábbi lépéseket:

    1. Válassza ki a **Vendég**, **Előző vendégek** vagy **Munkatársak** lehetőséget.
    2. Tegye a következők egyikét:

        - Ha a **Vendég** lehetőséget választotta, kövesse az alábbi lépéseket:

            1. Adja meg a vendég nevét.
            2. Választható: Adja meg a vendég szervezetét és/vagy országát.
            3. Választható: A vendég szakmai beosztásának megadása.
            4. Válassza a **Kész** lehetőséget.

        - Ha az **Előző vendégek** lehetőséget választotta, kövesse az alábbi lépéseket:

            1. Jelöljön ki egy vagy több korábbi vendéget a listán. Megjelenik egy lista azokról a korábbi vendégekről, akiket korábbi költségjelentésekhez adott hozzá, és amelyek betöltődtek az alkalmazásába offline használatra. Alapértelmezés szerint 50 elem töltődik be, de a fejlesztő módosíthatja ezt a számot. További információért a fejlesztők tekintsék meg a következőt: [Mobil munkafelület](../../dev-itpro/mobile-apps/platform/mobile-platform-home-page.md) Ha a korábbi vendég nem szerepel a listán, válassza a **Keresés** lehetőséget az online kereséshez. Végezhet név szerinti keresést, vagy átválthat a szervezet, ország vagy beosztás szerinti keresésre.
            2. Válassza a **Kész** lehetőséget.

        - Ha a **Munkatársak** lehetőséget választotta, kövesse az alábbi lépéseket:

            1. Jelöljön ki egy vagy több munkatársat a listán. Megjelenik a kapcsolat nélküli használatra az alkalmazásba betöltött munkatársak listája. Alapértelmezés szerint 50 elem töltődik be, de a fejlesztő módosíthatja ezt a számot. További információért a fejlesztők tekintsék meg a következőt: [Mobil munkafelület](../../dev-itpro/mobile-apps/platform/mobile-platform-home-page.md) Ha a munkatárs nem szerepel a listán, válassza a **Keresés** lehetőséget az online kereséshez. Végezhet név szerinti keresést, vagy átválthat a vállalat vagy beosztás szerinti keresésre.
            2. Válassza a **Kész** lehetőséget.

    3. Válassza ki a **Vissza** gombot a költségrészletekhez való visszatéréshez.

19. Ha a vállalati irányelv a költségek részletezését írja elő, válassza ki a **Részletezés** lehetőséget, majd kövesse az alábbi lépéseket:

    1. Válassza ki a részletezni kívánt első dátumot.
    2. Válassza a **Részletezés hozzáadása** elemet.
    3. Válassza ki a költségrészletezés alkategóriáját. Megjelenik a kapcsolat nélküli használatra az alkalmazásba betöltött költségalkategóriák listája. Alapértelmezés szerint 50 elem töltődik be, de a fejlesztő módosíthatja ezt a számot. További információért a fejlesztők tekintsék meg a következőt: [Mobil munkafelület](../../dev-itpro/mobile-apps/platform/mobile-platform-home-page.md) Ha az alkategória nem szerepel a listán, válassza a **Keresés** lehetőséget az online kereséshez. Keresés a költség alkategóriájának neve alapján.
    4. A részletezés tranzakciós összegének megadása.
    5. Szükség esetén módosítsa a tranzakció dátumát.
    6. Válassza a **Kész** lehetőséget.
    7. Ismételje meg a fenti lépéseket addig, amíg be nem fejezte az összes részletezés hozzáadását a kiválasztott dátum esetében.
    8. Ha további napokat szeretne megadni, választhatja a **Másolás következő napra** lehetőséget, amellyel átviheti a következő napra is a részletezéseket. Másik lehetőségéként kiválaszthatja a részletezendő dátumot, majd részletezéseket adhat hozzá ugyanúgy, mint az első dátum esetében.
    9. Miután befejezte a költség részletezését, válassza ki a **Vissza** gombot a költség adataihoz való visszatéréshez.

20. Válassza ki a **Vissza** gombot a **Költségjelentés** oldalhoz való visszatéréshez.
21. Ismételje meg az előző lépéseket addig, amíg be nem fejezte az összes költség megadását.
22. Válassza a **Beküldés** lehetőséget.
23. Adja meg a jóváhagyóra vonatkozó esetleges megjegyzéseket.
24. Válassza a **Kész** lehetőséget.

