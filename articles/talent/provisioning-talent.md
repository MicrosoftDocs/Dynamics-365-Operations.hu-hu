---
title: "A Microsoft Dynamics 365 for Talent létesítése"
description: "Ez a témakör végigvezeti Önt az új környezet létesítésén a Microsoft Dynamics 365 for Talent számára."
author: rschloma
manager: AnnBe
ms.date: 11/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Talent
ms.custom: 17271
ms.assetid: ba1ad49d-8232-400e-b11f-525423506a3f
ms.search.region: Global
ms.author: rschloma
ms.search.validFrom: 2017-11-20
ms.dyn365.ops.version: Talent July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 8b59ea6a2ac8c1c4e5df6e251fa3390639ff3f30
ms.openlocfilehash: e6266ef5890b5caaf33db76eeccfc8a7a6888a11
ms.contentlocale: hu-hu
ms.lasthandoff: 03/02/2018

---
# <a name="provision-microsoft-dynamics-365-for-talent"></a>A Microsoft Dynamics 365 for Talent létesítése

[!include[banner](includes/banner.md)]

[!include[banner](includes/banner.md)]

Ez a témakör végigvezeti Önt az új termelési környezet létesítésén a Microsoft Dynamics 365 for Talent számára. Ez a témakör feltételezi, hogy a Talent rendszert felhőalapú szolgáltatón (CSP) keresztül vagy vállalati architektúra (EA) megállapodás részeként vásárolta. Ha rendelkezik már meglévő Microsoft Dynamics 365 licenccel, amely már tartalmazza a Talent szolgáltatástervet, és nem tudja elvégezni a témakörben szereplő lépéseket, forduljon a támogatási szolgálathoz.

Első lépésként a globális rendszergazdának be kell jelentkeznie a [Microsoft Dynamics Lifecycle Services](http://lcs.dynamics.com) (LCS) szolgáltatásba, és létre kell hoznia egy új Talent projektet. Hacsak licencelési probléma meg nem akadályozza a Talent létesítését, a Támogatás vagy a Dynamics Service Engineering (DSE) képviselőinek segítségére nincsen szkség.

## <a name="create-an-lcs-project"></a>LCS-projekt létrehozása
Az LCS a Talent kezelésére való használatához előbb egy LCS-projektet kell létrehozni.

1. Jelentkezzen be az [LCS](https://lcs.dynamics.com/Logon/Index)-be azzal a fiókkal, amelyet a Talentre való előfizetéshez használt.
2. Válassza ki a pluszjelet (**+**) projekt létrehozásához.
3. Válassza a **Microsoft Dynamics 365 for Talent** terméknévként és termékverzióként.
4. Válassza a **Dynamics 365 for Talent** módszert.
5. Válassza a **Létrehozása** lehetőséget.

A Talent használatának megkezdésével kapcsolatos tudnivalókhoz lásd az új projektben létrehozott **Talent** módszert. Miután elkészült a projekt létrehozása, hajtsa végre a következő eljárást a Talent környezetének létesítéséhez.

## <a name="provision-a-talent-project"></a>Talent-projekt létesítése
LCS-projekt létrehozása után a Talentet létesítheti egy környezetbe.

1. Az LCS-projektben válassza a **Talent alkalmazás kezelése** csempét.
2. A Talent létesítése mindig Microsoft PowerApps környezetbe történik PowerApps-integráció és a bővíthetőség érdekében. Ha még nem rendelkezik PowerApps környezettel, kövesse a jelen témakör "Új PowerApps-környezet létrehozása (ha szükséges)" szakaszának lépéseit a folytatás előtt.

    > [!NOTE]
    > A meglévő környezetek megtekintéséhez vagy új környezetek létrehozásához a Talentet létesítő bérlő adminisztrátort hozzá kell rendelni a PowerApps P2 licenchez. Ha szervezete nem rendelkezik PowerApps P2 licenccel, kaphat egyet a CSP-től vagy a [PowerApps árképzési lapon](https://powerapps.microsoft.com/en-us/pricing/).

3. Válassza a **Hozzáadás** elemet, majd válassza ki a környezetet, amelybe létesíteni kívánja a Talent rendszert.
4. Válassza az **Igen** lehetőséget a feltételek elfogadásához és a telepítés megkezdéséhez.

    Az új környezet megjelenik a bal oldali navigációs panelen látható környezetek listájában. Azonban a környezet nem indítható el mindaddig, amíg a telepítés állapota nem frissül **Telepítve** értékre. Ez a folyamat jellemzően csak pár percig tart. Ha a jogosultságkezelés folyamata sikertelen, kérje az Ügyfélszolgálat segítségét.

6. Válassza a **Bejelentkezés a Talent rendszerbe** az új környezet használatához.

> [!NOTE]
> Ha még nem írta alá a végső követelményeket, a Talent tesztpéldányát telepítheti a projektben. Ezután ezt a példányt használhatja a megoldás tesztelésére mindaddig, amíg alá nem ír. Ha az új környezet teszteléshez használja, ismételje meg ezt az eljárást, hogy létrehozzon egy éles környezetet.

> [!NOTE]
> Az LCS-n keresztül alkalmazott Talent-környezetek nem tartalmaznak olyan demóadatokat, amelyeknek a konfigurálása HR-feladatokra történ volna, illetve amelyek a Talent-környezetre lennének specifikusak. Ha olyan környezetet szeretne, amely demóadatokat is tartalmaz, akkor javasoljuk, hogy regisztráljon egy 60 napos [Talent-próbakörnyezetre](https://dynamics.microsoft.com/en-us/talent/overview/). Bár a próbakörnyezetek tulajdonosa az a felhasználó, aki kérte pket, más felhasználók is meghívhatók az Alapvető HR környezet rendszergazdai felületén keresztül. A próbakörnyezetek olyan kitalált adatokat tartalmaznak, amelyek segítségével biztonságosan fel lehet fedezni a programot. Nem úgy tervezték, hogy termelési környezetekben használják őket. Kérjük, vegye figyelembe, hogy amikor a próbakörnyezet 60 nap elteltével lejár, a benne lévő összes adat törlődik, és azok nem is állíthatók helyre. Regisztrálhat egy új próbakörnyezetre, miután lejárt a meglévő környezet.

## <a name="create-a-new-powerapps-environment-if-required"></a>Új PowerApps-környezet létrehozása (ha szükséges)
A Talent és PowerApps környezetek közötti integrációval integrálhatja és kiterjesztheti a Talent-adatok használatát a PowerApps-eszközökkel. A PowerApps-környezetek céljának megismerése révén olyan alkalmazásokat készíthet, amelyek megfelelnek a Talent kibővítése iránti igényeinek. Információ a PowerApps-környezetekről, beleértve a környezeti hatásköröket, a környezethez való hozzáférést, valamint a környezet létrehozását és kiválasztását: [PowerApps-környezetek bejelentése](https://powerapps.microsoft.com/en-us/blog/powerapps-environments/). Míg minden bérlő automatikusan telepítésre kerül egy alapértelmezett PowerApps-környezetben, előfordulhat, hogy ez nem a legjobb környezet az Ön Talent-telepítése számára. E lépés során adatintegrációs és tesztelési stratégiákat kell figyelembe venni, ezért javasoljuk, hogy fontolja meg a telepítés különböző szempontjait, mivel később nem könnyű megváltoztatni egyes döntéseket. 

Bár minden bérlő automatikusan telepítésre kerül egy alapértelmezett PowerApps-környezetben, előfordulhat, hogy ez nem a legjobb környezet az Ön Talent-telepítése számára. Az adatintegrálási és -tesztelési stratégiákat is ebben a lépésben kell figyelembe venni. Ezért javasoljuk, hogy vegye figyelembe a telepítés különböző következményeit, mert nem könnyű a későbbiekben megváltoztatni a PowerApps-környezetet.

1. Válassza a **Környezetek kezelése** lehetőséget az LCS-ben. Átkerül a [PowerApps Admin center](https://preview.admin.powerapps.com/environments) oldalra, ahol megtekintheti a meglévő környezeteket és új környezeteket hozhat létre.
2. Válassza ki az **Új környezet** lehetőséget.
3. Adjon egy egyedi nevet a környezet számára, és válassza ki a telepítés helyét.

    > [!NOTE]
    > A Talent nem minden régióban elérhető. Ezért ellenőrizze a rendelkezésre állást, mielőtt kiválasztja a környezetének helyét.

4. Amikor a rendszer megkérdezi, hogy szeretne-e létrehozni egy adatbázist, válassza az **Adatbázis létrehozása** lehetőséget a Common Data Service (CDS) adatbázis létrehozásához, amely tárolni fogja a Talent adatainak egy részét. Adatbázis létrehozásával PowerApps alkalmazásokat is integrálhat a Talent rendszerbe.
5. A rendszer megkérdezi az adatbázisban használandó hozzáférési szintet. Javasoljuk, hogy válassza a **Hozzáférés korlátozása** lehetőséget, mert ez az opció megakadályozza a Talent felhasználóinak, hogy érzékeny adatokhoz közvetlenül hozzáférjenek egy PowerApps alkalmazás használatával.
6. A létrehozott CDS adatbázisban szereplő bemutatóadatok többek között inaktív alkalmazottakat és fiktív címeket adnak hozzá az éles környezethez. Ha el szeretné távolítani a bemutatóadatokat, tegye a következőket, miután befejezte a CDS-adatbázis létrehozását:

    > [!IMPORTANT]
    > Ha korábban létrehozott egy CDS-adatbázist, és bevitte a vállalata éles adatait, akkor ezek a lépések **Minden** adatot eltávolítanak a kijelölt adatbázisból, akár a vállalata éles adatait is.

    1. Jelentkezzen be a [PowerApps](https://preview.web.powerapps.com/home) szolgáltatásba.
    2. Válassza ki a 2. lépésben létrehozott környezetet a jobb felső sarokban megjelenő legördülő listából.
    3. Bontsa ki a **Common Data Service** elemet a bal oldali ablaktáblában, majd válassza az **Entitások** elemet.
    4. A lap jobb oldalán válassza a három pont (**…**) gombot, majd az **Összes adat törlése** lehetőséget.
    5. Válassza az **Adatok törlése** lehetőséget annak megerősítésére, hogy el kívánja távolítani az adatokat. Ez a művelet eltávolítja a CDS-ben alapértelmezés szerint szereplő összes bemutatóadatot. Emellett eltávolítja a kiválasztott adatbázisba bevitt egyéb adatokat is.

Mostantól használhatja az új környezetet.

## <a name="grant-access-to-the-environment"></a>Hozzáférés biztosítása a környezethez
Alapértelmezés szerint a környezetet csak az a globális rendszergazda érheti el, aki létrehozta. Az alkalmazás további felhasználóinak azonban kifejezett módon engedélyezni kell a hozzáférést. Ha hozzáférést szeretne adni, [fel kell vennie a felhasználókat](../dev-itpro/sysadmin/tasks/create-new-users.md), és [hozzájuk kell rendelnie a megfelelő szerepköröket](../dev-itpro/sysadmin/tasks/assign-users-security-roles.md) az Alapvető HR környezetben. emellett hozzá kell adni ezeket a felhasználókat a PowerApps-környezethez, hogy hozzáférhessenek az Attract és az Onboard alkalmazásokhoz. Az eljárás részletei itt láthatók. Ha segítségre van szüksége a következő lépésekkel kapcsolatban, olvassa el [A PowerApps adminisztrációs központjának bemutatása](https://powerapps.microsoft.com/en-us/blog/introducing-admin-center-for-powerapps/) című blogbejegyzést.

Ezt az eljárást az a globális rendszergazda hajtja végre, aki a Talent környezetet telepítette.

1. Nyissa meg a [PowerApps adminisztrációs központját](https://preview.admin.powerapps.com/environments).
2. Jelölje be a megfelelő környezeteket.
3. A **Biztonság** lapon adja hozzá a szükséges felhasználókat a **Környezetkészítő** szerepkörhöz.

Ne feledje, hogy a felhasználók a PowerApps környezethez történő manuális hozzáadásának ezen utolsó lépése ideiglenes. Végül automatikusan fog végbemenni, amikor megtörténik a felhasználók hozzáadása az Alapvető HR környezetben.

