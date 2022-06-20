---
title: A Készlet láthatósága bővítmény telepítése
description: Ez a témakör azt mutatja be, hogyan lehet telepíteni a Microsoft készlet láthatósági bővítményét Dynamics 365 Supply Chain Management.
author: yufeihuang
ms.date: 05/27/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: ce81ed2ed79bfe5c7fff9724e14af150817af11f
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8895699"
---
# <a name="install-and-set-up-inventory-visibility"></a>Inventory Visibility telepítése és beállítása

[!include [banner](../includes/banner.md)]

Ez a témakör azt mutatja be, hogyan lehet telepíteni a Microsoft készlet láthatósági bővítményét Dynamics 365 Supply Chain Management.

A Készletláthatóság kiegészítő telepítéséhez a Microsoft Dynamics Lifecycle Services (LCS) szolgáltatást kell használnia. Az LCS egy olyan együttműködési portál, amely olyan környezetet és rendszeresen frissített szolgáltatásokat biztosít, amelyek segítenek a pénzügyi és üzemeltetési alkalmazások életciklusának kezelésében. További tudnivalókért lásd: [Lifecycle Services-erőforrások](../../fin-ops-core/dev-itpro/lifecycle-services/lcs.md).

> [!TIP]
> Javasoljuk, hogy csatlakozzon a Készlet láthatósági bővítmények felhasználócsoporthoz, ahol hasznos segédeket találhat, behasználhatja a legújabb frissítéseit, és bármilyen kérdést feladhat, amelyek a készlet láthatóságának használatával kapcsolatban előfordulhatnak. A csatlakozáshoz e-mailt küld a készlet láthatósági [termékcsoportjának inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com) az ellátásilánc-kezelési környezet azonosítójával együtt.

## <a name="inventory-visibility-prerequisites"></a>Készletláthatóság előfeltételei

A Készletláthatóság telepítése előtt a következő feladatokat kell elvégeznie:

- Szerezzen be egy LCS megvalósítási projektet, ahol legalább egy környezetet telepítettek.
- Győződjön meg arról, hogy a bővítmények beállításának előfeltételei teljesültek. Az előfeltételekkel kapcsolatos információkért lásd: [Add-inek áttekintése](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md). A Készlet láthatósága nem igényel kettős írású csatolást.

> [!NOTE]
> A jelenleg támogatott országok és régiók közé tartozik Kanada (CCA, ECA), az Egyesült Államok (WUS, EUS), az Európai Unió (NEU, WEU), az Egyesült Királyság (SUK, WUK), Ausztrália (EAU, SEAU), Japán (EJP, WJP) és Brazília (SBR, SCUS).

Ha bármilyen kérdése van ezekkel az előfeltételekkel kapcsolatban, kérjük, forduljon a Készlet láthatósága termékcsapatához a [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com) címen.

## <a name="install-the-inventory-visibility-add-in"></a><a name="install-add-in"></a>A Készlet láthatósága bővítmény telepítése

A bővítmény telepítése előtt regisztráljon egy alkalmazást, és adjon hozzá egy ügyféltitkot a Azure Active Directory (Azure AD) címre az Azure-előfizetése alatt. Útmutatásért lásd: [Alkalmazás regisztrálása](/azure/active-directory/develop/quickstart-register-app) és [Ügyféltitok hozzáadása](/azure/active-directory/develop/quickstart-register-app#add-a-certificate). Mindenképpen jegyezze fel az **Alkalmazás (ügyfél) azonosító**, az **Ügyféltitok** és a **Bérlő azonosító** értékeit, mert később szüksége lesz rájuk.

> [!IMPORTANT]
> Ha több LCS-környezete van, mindegyikhez Azure AD hozzon létre egy másik alkalmazást. Ha ugyanazt az alkalmazásazonosítót és bérlőazonosítót használja a készlet láthatósági bővítményének különböző környezetekben való telepítéséhez, jogkivonat-probléma fog előfordulni a régebbi környezetekben. Emiatt csak az utolsó telepítés lesz érvényes.

Miután regisztrált egy alkalmazást, és hozzáad egy ügyféltitkot a Azure AD rendszerhez, kövesse az alábbi lépéseket a Készletláthatóság kiegészítő telepítéséhez.

1. Bejelentkezés az [LCS](https://lcs.dynamics.com/Logon/Index) alkalmazásba.
1. A kezdőlapon válassza ki azt a projektet, amelyben a környezet telepítve van.
1. A projekt oldalon jelölje ki azt a környezetet, amelyben telepíteni szeretné a bővítményt.
1. A környezet oldalon görgessen lefelé, amíg meg nem találja a **Környezeti bővítmények** részt az **Power Platform integráció** szakaszban. Itt található a Dataverse környezet neve. Győződjön meg arról, hogy a Dataverse-környezet nevét szeretné használni a Készlet láthatóságához.

    > [!NOTE]
    > Jelenleg csak az LCS használatával létrehozott Dataverse környezetek támogatottak. Ha a Dataverse környezetet más módon hozták létre (például a Power Apps felügyeleti központ használatával), és ha az az Ön Supply Chain Management környezetéhez kapcsolódik, akkor először a Készletláthatóság termékcsapattal kell felvennie a kapcsolatot a hozzárendelési probléma megoldása érdekében a [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com) címen. Ezután telepítheti a Készletláthatóság funkciót.

1. A **Környezeti bővítmények** szakaszban válassza az **Új bővítmény telepítése** lehetőséget.

    ![Környezeti oldal az LCS-ben](media/inventory-visibility-environment.png "Környezeti oldal az LCS-ben")

1. Válassza az **Új bővítmény telepítése** hivatkozást. Megjelenik az elérhető bővítmények listája.
1. A listában válassza a **Készletláthatóság** lehetőséget.
1. Állítsa be a következő mezőket a környezetének megfelelően:

    - **AAD alkalmazás (ügyfél) azonosítója** - Adja meg a korábban létrehozott és feljegyzett Azure AD alkalmazás azonosítóját.
    - **AAD bérlő azonosítója** - Adja meg a bérlő azonosítóját, amelyet korábban feljegyzett.

    ![Bővítményoldal beállítása](media/inventory-visibility-setup.png "Bővítményoldal beállítása")

1. Egyetért a feltételekkel a **Feltételek** jelölőnégyzet kiválasztásával.
1. Válassza a **Telepítés** parancsot. A bővítmény állapota a következő: **Telepítés**. Ha a telepítés befejeződött, frissítse az oldalt. Az állapotnak **Telepítettre** kell változnia.
1. A Dataverse-ben válassza ki az **Alkalmazások** szakaszt a bal oldali navigációban, és ellenőrizze, hogy sikeresen telepítve van-e **Készlet láthatósága** Power Apps. Ha az **Alkalmazások** szakasz nem létezik, lépjen kapcsolatba a Készletláthatóság termékcsapattal az [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com) címen.

> [!NOTE]
> Ha az LCS-lapról több mint egy óráig tart a telepítés, akkor a felhasználói fióknak valószínűleg nincs engedélye a megoldások telepítésére a környezetben Dataverse. A probléma megoldásához hajtsa végre a következő lépéseket:
>
> 1. A Készlet láthatósági bővítményének telepítési folyamatának megszakítása az LCS-lapon
> 1. Jelentkezzen be a [Microsoft 365 rendszergazdai](https://admin.microsoft.com) központba, és győződjön meg róla, hogy a bővítmény telepítéséhez használni kívánt felhasználói fiókhoz hozzá van rendelve a "Dynamics 365 Unified Operations Terv" licenc. Szükség esetén rendelje hozzá a licencet.
> 1. Jelentkezzen be a rendszergazdai [Power Platform központba](https://admin.powerplatform.microsoft.com) a megfelelő felhasználói fiók segítségével. Ezután a következő lépések szerint telepítse a készlet láthatósági bővítményét:
>     1. Válassza ki azt a környezetet, ahová telepíteni szeretné a bővítményt.
>     1. Válassza ki a **Dynamics 365-alkalmazásokat**.
>     1. Válassza a **Telepítési alkalmazást**.
>     1. A készlet **láthatóságának kiválasztása**
>
> 1. A telepítés befejeződése után menjen vissza az LCS lapra, és próbálja **újratelepíteni a Készlet láthatósága** bővítményt.

## <a name="uninstall-the-inventory-visibility-add-in"></a><a name="uninstall-add-in"></a>A Készletláthatóság kiegészítő eltávolítása

A Készletláthatóság kiegészítő eltávolításához válassza az LCS oldalon az **Eltávolítás** lehetőséget. Az eltávolítási folyamat megszünteti a Készletláthatóság bővítményt, törli a bővítmény LCS-ből történő regisztrációját, és törli a Készletláthatóság bővítmény adatcache-ében tárolt ideiglenes adatokat. A Dataverse előfizetésben tárolt elsődleges készletadatok azonban nem törlődnek.

A Dataverse előfizetésen tárolt készletadatok eltávolításához nyissa meg a [Power Apps](https://make.powerapps.com), válassza a navigációs sávon a **Környezet** lehetőséget, és válassza ki az LCS-környezetéhez kapcsolt Dataverse környezetet. Ezután lépjen a **Megoldások** menüpontba, és törölje a következő öt megoldást ebben a sorrendben:

1. Horgonymegoldás a Dynamics 365 megoldásokban a készletláthatósági alkalmazáshoz
1. Dynamics 365 FNO SCM Készletláthatósági alkalmazások megoldása
1. Készletszolgáltatás konfigurációja
1. Készletláthatóság önállóan
1. Dynamics 365 FNO SCM készletláthatóság alapmegoldás

Miután törölte ezeket a megoldásokat, a táblázatokban tárolt adatok is törlődnek.

## <a name="set-up-inventory-visibility-in-supply-chain-management"></a><a name="setup-dynamics-scm"></a>Készletláthatóság beállítása a Supply Chain Management szolgáltatásban

### <a name="deploy-the-inventory-visibility-integration-package"></a><a name="deploy-inventory-visibility-package"></a>A Készlet láthatósága integrációs csomag központi telepítése

Ha a Supply Chain Management 10.0.17-es vagy korábbi verziója fut, a csomagfájl beszerzéséért forduljon a Készlet láthatósága támogatási csapathoz az [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com) címen. Ezután telepítse a csomagot az LCS-be.

> [!NOTE]
> Ha a telepítés során nem egyező verziók fordulnak elő, manuálisan kell importálnia az X++ projektet a fejlesztői környezetbe. Ezt követően hozza létre a telepíthető csomagot a fejlesztői környezetben, és telepítse az éles környezetben.
>
> A kód része a Supply Chain Management 10.0.18-as verziójának. Ha azt a verziót vagy egy későbbi verziót futtat, nem szükséges a telepítés.

Győződjön meg arról, hogy az alábbi funkciók be vannak kapcsolva a Supply Chain Management-környezetben. (Alapértelmezés szerint be vannak kapcsolva.)

| Funkció leírása | Kódverzió | Osztály váltása |
|---|---|---|
| Készletdimenziók használatának engedélyezése vagy letiltása az InventSum táblán      | 10.0.11 | InventUseDimOfInventSumToggle      |
| Készletdimenziók használatának engedélyezése vagy letiltása az InventSumDelta táblán | 10.0.12 | InventUseDimOfInventSumDeltaToggle |

### <a name="set-up-inventory-visibility-integration"></a><a name="setup-inventory-visibility-integration"></a>Készletláthatósági integráció beállítása

Ha telepítette a bővítményt, a következő lépések alkalmazásával készítse elő a Supply Chain Management rendszert a bővítménnyel való munkára.

1. A Supply Chain Management alkalmazásban nyissa meg a **[Funkciókezelés](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)** munkaterületet, és kapcsolja be a következő funkciókat:
    - *Készletláthatósági integráció* – Szükséges.
    - *Készletláthatósági integráció foglaláseltolása* – Ajánlott, de nem kötelező. A 10.0.22-es vagy újabb verzió szükséges. További információért lásd a [Készletláthatósági foglalások](inventory-visibility-reservations.md) című részt.

1. Menjen a **Készletgazdálkodás \> Beállítás \> Készletláthatósági integrációs paraméterek** menüpontba.
1. Nyissa meg az **Általános** lapot, és adja meg a következő beállításokat:
    - **Készletláthatósági végpont** – Adja meg annak a környezetnek az URL-címét, ahol a Készletláthatóságot futtatja. További információért lásd: [A szolgáltatás végpontjának keresése](inventory-visibility-configuration.md#get-service-endpoint).
    - **Rekordok maximális száma egy kérelemben** – Állítsa be az egy kérelembe foglalható rekordok maximális számát. 1000-nél kisebb vagy azzal egyenlő egész számot kell megadnia. Az alapértelmezett érték 512. Javasoljuk, hogy tartsa meg az alapértelmezett értéket, hacsak nem kapott ajánlást a Microsoft ügyfélszolgálatától, vagy más miatt biztos abban, hogy módosítania kell.

1. Ha engedélyezte a *Készletláthatósági integráció foglaláseltolása* funkciót, nyissa meg a **Foglaláseltolás** lapot, és végezze el a következő beállításokat:
    - **Foglalási eltolás engedélyezése** – A funkció engedélyezéséhez állítsa *Igen* értékre.
    - **Foglaláseltolás módosítója** – Válassza ki azt a készlettranzakció-állapotot, amely a készlet láthatósága alapján eltolja a foglalásokat. Ez a beállítás határozza meg azt a rendelésfeldolgozási szakaszt, amely az eltolásokat kiváltja. A szakasz nyomon követhető a megrendelés készlettranzakciós státusza alapján. A következők közül választhat:
        - *Megrendeléskor* - A *Tranzakciókor* státusz esetén a megrendelés létrehozásakor a megrendelés elküldi az ellentételezési kérelmet. Az eltolásmennyiség a létrehozott rendelés mennyisége lesz.
        - *Tartalékolás* - A *Megrendelt tartalékolás tranzakciós* státusz esetén a rendelés akkor küld beszámítási kérelmet, amikor lefoglalják, felveszik, feladják a csomagolólapot vagy kiszámlázzák. A kérés csak egyszer, az első lépésben aktiválódik, amikor az említett folyamat bekövetkezik. Az eltolás mennyisége az a mennyiség, amelynél a készlettranzakció állapota a *Megrendelt* állapotról *Lefoglalt rendeltre* (vagy későbbi állapotra) változott a megfelelő rendelési sorban.

1. Lépjen a **Készletkezelés \> Időszakos \> Készlet láthatósági integrációja** elemre, és engedélyezze a feladatot. A rendszer a Supply Chain Management minden készletváltozási eseményét feladja a Készlet láthatósága számára.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
