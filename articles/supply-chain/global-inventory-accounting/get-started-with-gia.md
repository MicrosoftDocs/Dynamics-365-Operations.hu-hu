---
title: Első lépések a Global Inventory Accounting szolgáltatással
description: Ez a témakör azt ismerteti, hogyan lehet elkezdeni a Global Inventory Accounting szolgáltatást.
author: AndersGirke
ms.date: 06/18/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.custom: intro-internal
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2021-06-18
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 88f1e9ef8c8b2aa494c44ea3b33713adc470eb96
ms.sourcegitcommit: 2e554371f5005ef26f8131ac27eb171f0bb57b4e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/04/2022
ms.locfileid: "8384797"
---
# <a name="get-started-with-global-inventory-accounting"></a>Első lépések a Global Inventory Accounting szolgáltatással

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]
<!--KFM: Preview until 4/30/2022 -->

A Global Inventory Accounting szolgáltatás segítségével több készlet könyveléseit végezheti el a beállított Global Inventory Accounting főkönyvben. Minden Global Inventory Accounting főkönyvhöz egy *szabályt* társít. Egy szabály a következő típusú könyvelési irányelvek gyűjteményét jelenti:

- Költségobjektum
- Bemeneti mérték alapja
- Költségforgalom-feltételezés
- Költségösszetevő

> [!NOTE]
> Még a Global Inventory Accounting bekapcsolása után is elvégezheti szokás szerint a készletkönyvelést a Microsoft Dynamics 365 Supply Chain Management szolgáltatásban.

A Global Inventory Accounting szolgáltatás egy bővítmény. Ahhoz, hogy hozzáférhetővé váljanak a funkciók, telepítenie kell a Microsoft Dynamics Lifecycle Services (LCS) felületéről. Kiválaszthatja, hogy a termelési környezetekben való bekapcsolás előtt szeretné-e értékelni tesztkörnyezetben.

A Global Inventory Accounting jelenleg nem támogatja a Supply Chain Management eszközbe beépített költségkezelési funkciókat. Ezért fontos, hogy meggyőződjön, hogy a jelenleg elérhető funkciókészlet kielégíti-e a követelményeket.

## <a name="how-to-get-the-global-inventory-accounting-public-preview"></a><a name="sign-up"></a>A Global Inventory Accounting nyilvános előzetes verzió beszerzése

> [!IMPORTANT]
> A Global Inventory Accounting csak akkor használható, ha engedélyezve van az LCS-szolgáltatásban engedélyezett, nagy rendelkezésre állású környezet (nem OneBox környezet). Ezenkívül a Supply Chain Management 10.0.19-es vagy újabb verziójának is futnia kell.

A Global Inventory Accounting nyilvános előnézetére való regisztrációhoz küldje el e-mailben az LCS-környezetazonosítót a [Global Inventory Accounting csoportnak](mailto:GlobalInvAccount@microsoft.com). Ha jóváhagyta a programot, a csoport egy követő e-mailt küld, amely tartalmaz egy Global Inventory Accounting bétakulcsot és a szolgáltatási végpontokat. Miután megkapja a béta kulcsot, [telepítheti a bővítményt](#install).

## <a name="licensing"></a>Licenckezelés

A Global Inventory Accounting szolgáltatás egy licencben szerepel az Supply Chain Management szolgáltatásban elérhető készletkönyvelési standard funkciókkal. Nem kell további licencet vásárolnia a Global Inventory Accounting szolgáltatás használatához.

## <a name="prerequisites"></a>Előfeltételek

### <a name="set-up-microsoft-power-platform-integration"></a>Microsoft Power Platform-integráció beállítása

A bővítmények funkcióit a következő lépések segítségével kell Microsoft Power Platform platformmal integrálni.

1. Nyissa meg azt a LCS-környezetet, amelyhez hozzá szeretné adni a szolgáltatást.
1. Lépjen a **Teljes részletek** elemre.
1. Válassza a **Beállítás**  lehetőséget a **Power Platform-integráció** szakaszban.
1. A **Power Platform környezetének** beállítása párbeszédpanelen jelölje be a jelölőnégyzetet, majd válassza a **Beállítás** lehetőséget. A beállítás általában 60 és 90 perc közötti időt vesz igénybe.
1. A Microsoft Power Platform környezet beállítása után az oldal megjeleníti a környezet nevét. Ezenkívül az **Power Platform Integráció** szakasz a "Power Platform környezet beállítása kész" utasítást is megjeleníti. A Global Inventory Accountinghoz nem szükséges kétírásos alkalmazás.

További információkért lásd: [Engedélyezés a környezet üzemelő példánya után](../../fin-ops-core/dev-itpro/power-platform/enable-power-platform-integration.md#enable-after-deploy).

### <a name="set-up-dataverse"></a>Dataverse beállítása

A következő lépések szerint adja hozzá a Global Inventory Accounting szolgáltatási elveket a Dataverse beállítása előtt.

1. Telepítse az Azure AD Windows PowerShell modul v2 verzióját az [Azure Active Directory PowerShell for Graph telepítése](/powershell/azure/active-directory/install-adv2) részben leírtak szerint.
1. Futtassa a következő PowerShell-parancsot.

    ```powershell
    Connect-AzureAD # (open a sign in window and sign in as a tenant user)

    New-AzureADServicePrincipal -AppId "7a1dd80f-c961-4a67-a2f5-d6a5d2f52cf9" -DisplayName "d365-scm-costaccountingservice"

    New-AzureADServicePrincipal -AppId "5f58fc56-0202-49a8-ac9e-0946b049718b" -DisplayName "d365-scm-operationdataservice"
    ```

Ezután hozza létre az alkalmazásfelhasználókat a Global Inventory Accounting szoláltatáshoz a Dataverse szolgáltatásban a következő lépések segítségével.

1. Nyissa meg a Dataverse környezete URL-címét.
1. Lépjen a **Speciális beállítások \> Rendszer \> Biztonság \> Felhasználók** lehetőségre, és hozzon létre egy alkalmazásfelhasználót. A **Nézet** mező használatával módosítsa az oldal nézetét az *Alkalmazásfelhasználók* lehetőségre.
1. Válassza az **Új** lehetőséget.
1. Állítsa az **Alkalmazásazonosító** mező értékét erre: *7a1dd80f-c961-4a67-a2f5-d6a5d2f52cf9*.
1. Válassza a **Szerepkör hozzárendelése**, majd a *Rendszergazda* lehetőséget. Ha van *Common Data Service-felhasználó* nevű szerepkör, válassza ki azt is.
1. Ismételje meg az előző lépéseket, de állítsa az **Alkalmazásazonosító** mezőt a következőre: *5f58fc56-0202-49a8-ac9e-0946b049718b*.

További tudnivalókért lásd: [Alkalmazásfelhasználó létrehozása](/power-platform/admin/create-users-assign-online-security-roles#create-an-application-user).

Ha a Dataverse telepítés alapértelmezett nyelve nem angol, kövesse az alábbi lépéseket.

1. Ugrás ide: **Speciális beállítások \> Adminisztráció \> Nyelvek**.
1. Válassza az *Angol* (*LanguageCode=1033*), és majd az **Alkalmaz** lehetőséget.

## <a name="install-the-add-in"></a><a name="install"></a>Telepítse a bővítményt

A következő lépések szerint telepítheti a bővítményt a Global Inventory Accounting használata érdekében.

1. [Regisztrálás](#sign-up) a Global Inventory Accounting nyilvános előzetes verziójára.
1. Bejelentkezés az [LCS](https://lcs.dynamics.com/Logon/Index) alkalmazásba.
1. Lépjen a **Előzetes funkció kezelése** lehetőségre.
1. Válassza ki a plusz jelet (**+**).
1. A **Kód** mezőbe írja be a Global Inventory Accounting szolgáltatáshoz tartozó bővítmény bétakulcsát. (A bétakulcsot e-mailben kellett volna megkapni a kijelentkezett verzióban.)
1. Válassza a **Blokkolás feloldása** lehetőséget.
1. Nyissa meg azt a LCS-környezetet, amelyhez hozzá szeretné adni a szolgáltatást.
1. Lépjen a **Teljes részletek** elemre.
1. Menjen a **Power Platform Integráció** gombra, és válassza a **Telepítőt**.
1. A **Power Platform környezetének** beállítása párbeszédpanelen jelölje be a jelölőnégyzetet, majd válassza a **Beállítás** lehetőséget. A beállítás általában 60 és 90 perc közötti időt vesz igénybe.
1. A Microsoft Power Platform környezet beállítása után a **Környezet bővítmény** gyorslapját választva válassza az **Új bővítmény telepítése** lehetőséget.
1. Válassza a **Globális Inventory Accounting** eseményt.
1. Kövesse a telepítési útmutatót, és fogadja el a feltételeit és kikötéseit.
1. Válassza a **Telepítés** parancsot.
1. A **Környezeti bővítmények** gyorslapon látható, hogy a Global Inventory Accounting szolgáltatás telepítése folyamatban van. Néhány perc múlva az állapotot változik *Telepítés folyamatban* állapotról *Telepítve* értékre. (Elképzelhető, hogy frissíteni kell a lapot a változás megtekintéséhez.) Ezen a ponton a Global Inventory Accounting szolgáltatás készen áll a használatra.

## <a name="set-up-the-integration"></a>Integráció beállítása

A következő lépések szerint állíthatja be a Global Inventory Accounting és a Supply Chain Management közötti integrációt.

1. Jelentkezzen be a Supply Chain Management alkalmazásba.
1. Lépjen a **Rendszerfelügyelet \> Funkciókezelés** elemre.
1. Válassza a **Frissítések keresése** elemet.
1. A Mind **lapon** keresse meg a globális készletkönyvelés nevű *(Előnézet) funkciót*.
1. Válassza az **Engedélyezés most** lehetőséget.
1. Ugrás a **Globális készletkönyvelés \> Beállítása \> Global Inventory Accounting paraméterei \> Integrációs paraméterek**.
1. Az **Adatszolgáltatás végpontja** és a **Global Inventory Accounting végpont** mezőiben adja meg az URL-címeket abból az e-mailből, amit a globális készletkönyvelési csoport küldött, amikor előképként jelentkezett.

A Global Inventory Accounting készen áll a használatra.
