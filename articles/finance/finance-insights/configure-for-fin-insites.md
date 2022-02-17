---
title: Finance insights konfigurálása
description: Ez a témakör azokat a konfigurációs lépéseket ismerteti, amelyek lehetővé teszik a rendszer számára a Pénzügyi információkban elérhető képességek használatát.
author: ShivamPandey-msft
ms.date: 01/27/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-07-20
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: b9bad6445e9e77688f66c6c4186422d7a898edd7
ms.sourcegitcommit: 7fc0a9a6440ac087292e9e76c26c67f56154b9e6
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/28/2022
ms.locfileid: "8051370"
---
# <a name="configuration-for-finance-insights"></a>Finance insights konfigurálása

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

A Finance Insights egyesíti a Microsoft funkcionalitását Dynamics 365 Finance val vel Dataverse, Azure és AI Builder hogy hatékony előrejelzési eszközöket biztosítson szervezete számára. Ez a témakör azokat a konfigurációs lépéseket ismerteti, amelyek lehetővé teszik a rendszer számára a Pénzügyi információkban elérhető képességek használatát. A témakörben ismertetett eljárások sikeres végrehajtásához rendszergazdai és rendszertestreszabási hozzáféréssel kell rendelkeznie a [Power Portal adminisztrációs központ](https://admin.powerplatform.microsoft.com/), Rendszergazdai hozzáférés be Dynamics 365 Finance, és hozzáférést biztosít a környezetek létrehozásához Microsoft Dynamics Életciklus-szolgáltatások (LCS).

> [!NOTE]
> A Finance Insights beállításának következő eljárásai a következő verzióira érvényesek Dynamics 365 Finance 10.0.21 és újabb verzió.

## <a name="deploy-dynamics-365-finance"></a>Dynamics 365 Finance üzembe helyezése

Kövesse az alábbi lépéseket a környezetek telepítéséhez.

1. LCS-ben hozzon létre vagy frissítsen a Dynamics 365 Finance környezet. A környezethez az alkalmazás 10.0.21-es vagy újabb verziója szükséges.

    > [!NOTE]
    > A környezetnek magas rendelkezésre állású (HA) környezetnek kell lennie. (Az ilyen típusú környezetet 2. szintű környezetnek is nevezik.) További információ: [Környezettervezés](../../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md).

2. Ha a Finance Insights szolgáltatást sandbox környezetben konfigurálja, előfordulhat, hogy a termelési adatokat át kell másolnia ebbe a környezetbe, mielőtt az előrejelzések működni fognak. Az előrejelzési modell több évnyi adatból használatával készít előrejelzéseket. A Contoso bemutató adatai nem tartalmaznak elegendő előzményadatot az előrejelzési modell megfelelő képzéséhez. 

## <a name="configure-your-azure-ad-tenant"></a>Konfigurálja a saját Azure AD bérlő

Azure Active Directory(Azure AD) úgy kell beállítani, hogy együtt lehessen használni Dataverse és a Microsoft Power Platform alkalmazások. Ez a konfiguráció megköveteli, hogy vagy a **Projekt tulajdonos** szerepet vagy a **Környezetvédelmi vezető** szerepet kell hozzárendelni a felhasználóhoz a **Projekt biztonsági szerepkör** mező az LCS-ben.

Győződjön meg arról, hogy a következő beállítás befejeződött:

- Neked van **Rendszergazda** és **Rendszer-testreszabó** elérheti a Power Portal adminisztrációs központjában.
- A Dynamics 365 Finance vagy azzal egyenértékű licenc vonatkozik a Finance Insights bővítményt telepítő felhasználóra.

A következő Azure AD az alkalmazások regisztrálva vannak Azure AD.

|  Pályázat                             | Alkalmazás azonosítója                               |
|------------------------------------------|--------------------------------------|
| Microsoft Dynamics ERP mikroszolgáltatások CDS | 703e2651-d3fc-48f5-942c-74274233dba8 |
    
## <a name="configure-dataverse"></a>Dataverse konfigurálása

A következő lépések segítségével konfigurálhatja a Dataverse-t a Finance Insights alkalmazáshoz.

- Nyissa meg a környezet oldalát az LCS-ben, és ellenőrizze, hogy az **Power Platform-Integráció** szakasz már be van-e állítva.

    - Ha Dataverse már be van állítva, a Dataverse Fel kell tüntetni a Finance környezethez kapcsolódó környezet nevét.
    - Ha Dataverse még nincs beállítva, válassza ki **Beállít**. Beállítása a Dataverse környezet akár egy órát is igénybe vehet. Amikor a beállítás sikeresen befejeződött, a Dataverse Fel kell tüntetni a Finance környezetben hivatkozott környezet nevét.
    - Ha ez az integráció egy meglévővel lett beállítva Microsoft Power Platform környezetben, forduljon a rendszergazdához, és győződjön meg arról, hogy a kapcsolt környezet nincs letiltott állapotban.

        További információkért lásd [Engedélyezve a Power Platform integráció](../../fin-ops-core/dev-itpro/power-platform/enable-power-platform-integration.md). 

        Ahhoz, hogy hozzáférjen a Microsoft Power Platform adminisztrációs webhely, lépjen a következőre <https://admin.powerplatform.microsoft.com/environments>.

## <a name="configure-the-finance-insights-add-in"></a>A Finance Insights bővítmény konfigurálása

Ha korábban telepítette a Finance Insights bővítményt, távolítsa el, mielőtt végrehajtaná a következő eljárást.

> [!NOTE]
> Ha már telepítette a Data Lake-bővítményt az LCS-ben, a Finance Insights azt fogja használni az előrejelzésekhez szükséges adatok mentésére. Ha még nem telepítette a Data Lake-bővítményt az LCS-ben, a Finance Insights bővítmény létrehoz egy felügyelt adattó-bővítményt az Ön számára.

A következő lépések szerint telepítheti a Finance Insights bővítményt.

1. Jelentkezzen be az LCS-be, majd a lap jobb oldalán látható környezet neve alatt válassza ki a **Minden részlet** lehetőséget.
2. A **Környezeti bővítmények** szakaszban válassza az **Új bővítmény telepítése** lehetőséget.
3. A **Finance Insights** bővítmény konfigurálása.
4. Fogadja el a feltételeket, majd válassza ki **Telepítés**.

A bővítmény telepítése eltarthat néhány percig.

## <a name="one-last-thing"></a>Egy utolsó dolog...

A bővítmény sikeres telepítése után akár egy órába is telhet, mire engedélyezheti a Finance Insights funkcióit a **Funkciókezelés** munkaterület be Dynamics 365 Finance. Ha nem akar olyan sokáig várni, manuálisan is futtathatja a **Insights kiépítési állapot ellenőrzése** folyamat. 

1. Ban ben Dynamics 365 Finance, menj **Rendszer adminisztráció \> Beállít \> Folyamat automatizálás**.
2. A **Háttérfolyamatok** fül, talál **Insights kiépítési állapot ellenőrzése**, és válassza ki **Szerkesztés**.
3. Állítsa be a **Következő végrehajtás** mezőt 30 perccel az aktuális idő elé.

   Ennek a változtatásnak ki kell kényszerítenie a **Insights kiépítési állapot ellenőrzése** folyamat azonnal lefut.

   Azután **Insights kiépítési állapot ellenőrzése** A folyamat sikeresen lefut, engedélyezheti a Finance Insights szolgáltatást a **Funkciókezelés** munkaterület.

> [!NOTE]
> Ha a **Insights kiépítési állapot ellenőrzése** a folyamat nem fut le, lépjen ide **Rendszer adminisztráció** > **Érdeklődések** > **Kötegelt munkák**. Ban,-ben **Folyamatautomatizálási szavazórendszer** mezőben módosítsa az értéket **Várakozás** a folyamat elindításához. 
> 
## <a name="feedback-and-support"></a>Visszajelzés és támogatás

Ha szeretne visszajelzést adni, vagy támogatásra van szüksége, küldjön e-mailt a következő címre: [Pénzügyi statisztikák (előnézet)](mailto:fiap@microsoft.com).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
