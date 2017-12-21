---
title: "A Microsoft Dynamics 365 for Talent létesítése"
description: "Ez a témakör végigvezeti Önt az új környezet létesítésén a Microsoft Dynamics 365 for Talent számára."
author: rschloma
manager: AnnBe
ms.date: 11/20/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: Talent
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
ms.sourcegitcommit: 6ffb97b53f522cfe8ccd8e89df854cbc557e4f1f
ms.openlocfilehash: fadc373b2c1c06987f22d4d9c20a9ab07b0c85d5
ms.contentlocale: hu-hu
ms.lasthandoff: 11/20/2017

---
# <a name="provision-microsoft-dynamics-365-for-talent"></a>A Microsoft Dynamics 365 for Talent létesítése
Ez a témakör végigvezeti Önt az új környezet létesítésén a Microsoft Dynamics 365 for Talent számára. Ez a témakör feltételezi, hogy a Talent rendszert felhőalapú szolgáltatón (CSP) keresztül vagy vállalati architektúra (EA) megállapodás részeként vásárolta. Ha rendelkezik már meglévő Microsoft Dynamics 365 licenccel, amely már tartalmazza a Talent szolgáltatástervet, és nem tudja elvégezni a témakörben szereplő lépéseket, forduljon a támogatási szolgálathoz.

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

    Az új környezet megjelenik a bal oldali navigációs panelen látható környezetek listájában. Azonban a környezet nem indítható el mindaddig, amíg a telepítés állapota nem frissül **Telepítve** értékre. Ez a folyamat jellemzően csak pár percig tart. Ha létesítés sikertelen, forduljon a Támogatáshoz.

6. Válassza a **Bejelentkezés a Talent rendszerbe** az új környezet használatához.

> [!NOTE]
> Ha még nem írta alá a végső követelményeket, a Talent tesztpéldányát telepítheti a projektben. Ezután ezt a példányt használhatja a megoldás tesztelésére mindaddig, amíg alá nem ír. Ha az új környezet teszteléshez használja, ismételje meg ezt az eljárást, hogy létrehozzon egy éles környezetet.

## <a name="create-a-new-powerapps-environment-if-required"></a>Új PowerApps-környezet létrehozása (ha szükséges)
1. Válassza a **Környezetek kezelése** lehetőséget az LCS-ben. Átkerül a [PowerApps Admin Center](https://preview.admin.powerapps.com/environments) oldalra, ahol megtekintheti a meglévő környezeteket és új környezeteket hozhat létre.
2. Válassza az (**+**) **Új környezet** gombot.
3. Adjon egy egyedi nevet a környezet számára, és válassza ki a telepítés helyét.

    > [!NOTE]
    > A Talent nem minden régióban elérhető. Ezért ellenőrizze a rendelkezésre állást, mielőtt kiválasztja a környezetének helyét.

4. Amikor a rendszer megkérdezi, hogy szeretne-e létrehozni egy adatbázist, válassza az **Adatbázis létrehozása** lehetőséget a Common Data Service (CDS) adatbázis létrehozásához, amely tárolni fogja a Talent adatainak egy részét. Adatbázis létrehozásával PowerApps alkalmazásokat is integrálhat a Talent rendszerbe.
5. A rendszer megkérdezi az adatbázisban használni kívánt hozzáférési szintet. Javasoljuk, hogy válassza a **Hozzáférés korlátozása** lehetőséget, mert ez az opció megakadályozza a Talent felhasználóinak, hogy érzékeny adatokhoz közvetlenül hozzáférjenek egy PowerApps alkalmazás használatával.
6. A létrehozott CDS-adatbázis bemutatóadatokat tartalmaz. A bemutatóadatok hasznosak, mivel a bemutató-céget tesztelésre, illetve feladatrögzítések vagy feladat-útmutatók létrehozására használhatja. A bemutatóadatok azonban többek között inaktív alkalmazottakat és fiktív címeket adnak hozzá az éles környezethez. Ha el szeretné távolítani a bemutatóadatokat, tegye a következőket, miután befejezte a CDS-adatbázis létrehozását:

    > [!IMPORTANT]
    > Ha korábban létrehozott egy CDS-adatbázist, és bevitte a vállalata éles adatait, vegye figyelembe, hogy ezek a lépések **Minden** adatot eltávolítanak a kijelölt adatbázisból, akár a vállalata éles adatait is.

    1. Jelentkezzen be a [PowerApps](https://preview.web.powerapps.com/home) rendszerbe, és keresse meg a 2. lépésben létrehozott környezetet.
    2. Válassza az **Entitások** elemet. A lap jobb oldalán válassza a három pont (**…**) gombot, majd az **Összes adat törlése** lehetőséget.
    3. Válassza az **Adatok törlése** lehetőséget annak megerősítésére, hogy el kívánja távolítani az adatokat. Ez a művelet eltávolítja a CDS-ben alapértelmezés szerint szereplő összes bemutatóadatot. Emellett eltávolítja a kiválasztott adatbázisba bevitt egyéb adatokat is.

Mostantól használhatja az új környezetet.

