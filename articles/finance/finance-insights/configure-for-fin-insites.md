---
title: Pénzügyi konfiguráció – információk
description: Ez a cikk bemutatja a konfigurációs lépéseket, amelyek lehetővé teszik a rendszer számára a pénzügyi információkban elérhető képességek használatát.
author: ShivamPandey-msft
ms.date: 01/27/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-07-20
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: ac0f0cb078b6e202540fadbff337a01379febc8a
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8861416"
---
# <a name="configuration-for-finance-insights"></a>Pénzügyi konfiguráció – információk

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

A pénzügyi adatelemzés a Microsoft Dynamics 365 Pénzügy Dataverse és az Azure funkciókat kombinálja, AI Builder és hatékony előrejelzési eszközöket biztosít a szervezet számára. Ez a cikk bemutatja a konfigurációs lépéseket, amelyek lehetővé teszik a rendszer számára a pénzügyi információkban elérhető képességek használatát. [A témakörben található eljárások sikeres befejezéséhez a Power Portal](https://admin.powerplatform.microsoft.com/) adminközpontjában rendszergazdai és rendszer testreszabó hozzáféréssel, a Dynamics 365 Pénzügy rendszergazdai hozzáférésével, Microsoft Dynamics valamint a Lifecycle Services (LCS) környezetek létrehozásához szükséges hozzáféréssel kell rendelkezik.

> [!NOTE]
> A Pénzügyi információk beállításának következő eljárásai a Dynamics 365 Pénzügy 10.0.21-es és újabb verzióira érvényesek.

## <a name="deploy-dynamics-365-finance"></a>A Dynamics 365 Pénzügy telepítése

Kövesse az alábbi lépéseket a környezetek telepítéséhez.

1. Az LCS-ben hozzon létre vagy frissítsen egy Dynamics 365 Pénzügyi környezetet. A környezethez a 10.0.21-es vagy újabb verziójú alkalmazás szükséges.

    > [!NOTE]
    > A környezetnek magas rendelkezésre álló (HA) környezetnek kell lennie. (Az ilyen típusú környezetet 2. szintű környezetnek is nevezik.) További információ: [Környezettervezés](../../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md).

2. Ha a pénzügyi információkat egy üzenetkészlet-környezetben konfigurálja, előfordulhat, hogy termelési adatokat kell másolnia a környezetbe, mielőtt az előrejelzések működni fognak. Az előrejelzési modell több évnyi adatból használatával készít előrejelzéseket. A Contoso bemutató adatai nem tartalmaznak elég előzményadatot az előrejelzési modell megfelelő képzéséhez. 

## <a name="configure-your-azure-ad-tenant"></a>A bérlő Azure AD konfigurálása

Azure Active Directory(Azure AD) konfigurálni kell, hogy használni tudja az alkalmazásokat Dataverse és Microsoft Power Platform az alkalmazásokat. Ehhez a konfigurációhoz vagy a **Projekttulajdonos** **·** **szerepkört, vagy a Környezetkezelő szerepkört hozzá kell rendelni a felhasználóhoz az LCS Projekt biztonsági szerepkör** mezőjében.

Győződjön meg a következő beállításokról:

- A **Power** **Portal** felügyeleti központban rendszergazdai és rendszerszabó hozzáféréssel rendelkezik.
- A Pénzügyi információk bővítményt telepítő felhasználóhoz a Dynamics 365 Pénzügyi vagy ezzel egyenértékű licencet kell alkalmazni.

A következő Azure AD alkalmazások vannak regisztrálva a következőben Azure AD:

|  Alkalmazás                             | Alkalmazás azonosítója                               |
|------------------------------------------|--------------------------------------|
| Microsoft Dynamics ERP mikroszolgáltatások CDS | 703e2651-d3fc-48f5-942c-74274233dba8 |
    
## <a name="configure-dataverse"></a>Dataverse konfigurálása

A következő lépések segítségével konfigurálhatja a Dataverse-t a Finance Insights alkalmazáshoz.

- Nyissa meg a környezet oldalát az LCS-ben, és ellenőrizze, hogy az **Power Platform-Integráció** szakasz már be van-e állítva.

    - Ha Dataverse már be van állítva, Dataverse akkor megjelenik a Pénzügyi környezethez kapcsolódó környezeti név.
    - Ha Dataverse még nincs beállítva, válassza a Beállítás **lehetőséget**. A környezet Dataverse beállítása akár egy óráig is eltelhet. Ha a telepítés sikeresen befejeződött, Dataverse megjelenik a Pénzügyi környezetben összekapcsolt környezet neve.
    - Ha az integráció már meglévő környezetben van Microsoft Power Platform beállítva, forduljon a rendszergazdához, és győződjön meg arról, hogy a kapcsolt környezet nem letiltott állapotban van.

        További információ az integráció [engedélyezése.Power Platform](../../fin-ops-core/dev-itpro/power-platform/enable-power-platform-integration.md) 

        A rendszergazdai webhely Microsoft Power Platform eléréséhez menjen a következő oldalra <https://admin.powerplatform.microsoft.com/environments>:

## <a name="configure-the-finance-insights-add-in"></a>A Finance Insights bővítmény konfigurálása

Ha korábban már telepítette a Pénzügyi információk bővítményt, a következő eljárás előtt távolítsa el azt.

> [!NOTE]
> Ha már telepítette az adatkapcsolat-bővítményt az LCS-be, a Pénzügyi információk segítségével menti az előrejelzésekhez szükséges adatokat. Ha még nem telepítette az adatkapcsolat-bővítményt az LCS-be, a Pénzügyi információk bővítményben létrehozott egy felügyelt adatkapcsolatot.

A következő lépések szerint telepítheti a Finance Insights bővítményt.

1. Jelentkezzen be az LCS-be, majd a lap jobb oldalán látható környezet neve alatt válassza ki a **Minden részlet** lehetőséget.
2. A **Környezeti bővítmények** szakaszban válassza az **Új bővítmény telepítése** lehetőséget.
3. A **Finance Insights** bővítmény konfigurálása.
4. Elfogadja a feltételeket, majd válassza a Telepítés **lehetőséget**.

A bővítmény telepítése eltarthat néhány percig.

## <a name="one-last-thing"></a>Még egy utolsó tetet...

A bővítmény telepítése sikeresen megtörtént, **és** a Pénzügyi információk funkció engedélyezése a Dynamics 365 Pénzügy szolgáltatáskezelési munkaterületén akár egy óráig is eltelhet. Ha nem szeretne túl hosszú ideig várni, manuálisan **futtathatja az Információ létesítés állapotának ellenőrzése** folyamatot. 

1. A Dynamics 365 Pénzügy szolgáltatásban kattintson a Rendszerfelügyelet **\> beállítása folyamatautomatizálási \> folyamat automatizálására**.
2. Az Elemzési **létesítés állapotának ellenőrzése a Háttérfolyamatok** **lapon**, és válassza a Szerkesztés **lehetőséget.**
3. A Következő **végrehajtási mező** beállítása 30 perccel az aktuális idő előtt.

   Ennek a módosításnak arra kell **kényszerítenie az "Adatátépítési állapot** ellenőrzése" folyamatot, hogy azonnal fusson.

   Az **Adatátépítési** **állapot ellenőrzése sikeres futtatása után engedélyezheti a Pénzügyi információk funkciókat a Szolgáltatáskezelés munkaterületen**.

> [!NOTE]
> Ha az **Ellenőrzés létesítés** állapotának ellenőrzése nem fut le, akkor **a Rendszerfelügyelet** > **– Lekérdezések** > **kötegelt feladatoknál ússa le a rendszert**. A Folyamatautomatizálás **lekérdezése rendszermezőben** módosítsa **a** Folyamat kezdeményezése várakozás értékre az értéket. 
> 
## <a name="feedback-and-support"></a>Visszajelzés és támogatás

Ha visszajelzést szeretne küldeni, vagy segítségre van szüksége, [e-mailben küldje el a Pénzügyi információk (Előnézet) címre](mailto:fiap@microsoft.com).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
