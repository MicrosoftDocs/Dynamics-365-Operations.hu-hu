---
title: Pénzügyi konfiguráció – információk
description: Ez a témakör azokat a konfigurációs lépéseket ismerteti, amelyek lehetővé teszik a rendszer számára a Pénzügyi információkban elérhető képességek használatát.
author: ShivamPandey-msft
ms.date: 1/03/2021
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
ms.openlocfilehash: 5668d3ddff777645b4f1c6608f025d0c5a63208a
ms.sourcegitcommit: 03fa7556840aa59f825697f6f9edeb58ea673fca
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/04/2021
ms.locfileid: "7752978"
---
# <a name="configuration-for-finance-insights"></a>Pénzügyi konfiguráció – információk

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

A Pénzügyi információk a Microsoft Dynamics 365 Finance és a Dataverse, az Azure és az AI Builder funkcióit kombinálva hatékony előrejelző eszközöket biztosítanak a szervezet számára. Ez a témakör azokat a konfigurációs lépéseket ismerteti, amelyek lehetővé teszik a rendszer számára a Pénzügyi információkban elérhető képességek használatát. A témakörben található eljárások sikeres befejezéséhez rendszergazdai és rendszer szabó hozzáféréssel kell rendelkezik a Power Portal admin center, a System Administrator hozzáférése a [...](https://admin.powerplatform.microsoft.com/)Dynamics 365 Finance Microsoft Dynamics Lifecycle Services (LCS) szolgáltatásban, valamint hozzáféréssel kell lennie a környezetek létrehozásához.

> [!NOTE]
> A pénzügyi információk beállításának következő eljárásai a Dynamics 365 Finance 10.0.21-es és újabb verziókra érvényesek.

## <a name="deploy-dynamics-365-finance"></a>Dynamics 365 Finance üzembe helyezése

Kövesse az alábbi lépéseket a környezetek telepítéséhez.

1. Az LCS-kben hozzon létre vagy frissítsen egy Dynamics 365 Finance környezetet. A környezethez a 10.0.21-es vagy újabb verziójú alkalmazás szükséges.

    > [!NOTE]
    > A környezetnek magas rendelkezésre álló (HA) környezetnek kell lennie. (Az ilyen típusú környezetet 2. szintű környezetnek is nevezik.) További információ: [Környezettervezés](../../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md).

2. Ha a pénzügyi információkat egy üzenetkészlet-környezetben konfigurálja, előfordulhat, hogy termelési adatokat kell másolnia a környezetbe, mielőtt az előrejelzések működni fognak. Az előrejelzési modell több évnyi adatból használatával készít előrejelzéseket. A Contoso bemutató adatai nem tartalmaznak elég előzményadatot az előrejelzési modell megfelelő képzéséhez. 

## <a name="configure-dataverse"></a>Dataverse konfigurálása

A következő lépések segítségével konfigurálhatja a Dataverse-t a Finance Insights alkalmazáshoz.

- Nyissa meg a környezet oldalát az LCS-ben, és ellenőrizze, hogy az **Power Platform-Integráció** szakasz már be van-e állítva.

    - Ha már be van állítva, akkor a Dataverse-környezethez kapcsolt Finance-környezet nevének szerepelnie kell a listában.
    - Ha még nincs beállítva, válassza a **Telepítőt**. A környezet Dataverse beállítása akár egy óráig is eltelhet. Ha a telepítés sikeresen befejeződött, megjelenik a Pénzügyi környezethez kapcsolt Dataverse környezet neve.

## <a name="configure-the-finance-insights-add-in"></a>A Finance Insights bővítmény konfigurálása

Ha korábban már telepítette a Pénzügyi információk bővítményt, a következő eljárás előtt távolítsa el azt.

> [!NOTE]
> Ha már telepítette az adatkapcsolat-bővítményt az LCS-be, a Pénzügyi információk segítségével menti az előrejelzésekhez szükséges adatokat. Ha még nem telepítette az adatkapcsolat-bővítményt az LCS-be, a Pénzügyi információk bővítményben létrehozott egy felügyelt adatkapcsolatot.

A következő lépések szerint telepítheti a Finance Insights bővítményt.

1. Jelentkezzen be az LCS-be, majd a lap jobb oldalán látható környezet neve alatt válassza ki a **Minden részlet** lehetőséget.
2. A **Környezeti bővítmények** szakaszban válassza az **Új bővítmény telepítése** lehetőséget.
3. A **Finance Insights** bővítmény konfigurálása.
4. Elfogadja a feltételeket, majd válassza a **Telepítés** lehetőséget.

A bővítmény telepítése eltarthat néhány percig.

## <a name="one-last-thing"></a>Még egy utolsó tetet...

A bővítmény telepítése után előfordulhat, hogy a pénzügyi információk funkciójának engedélyezése akár egy óráig is eltelhet a funkciókezelés **·** Dynamics 365 Finance munkaterületén. Ha nem szeretne túl hosszú ideig várni, manuálisan futtathatja az **Információ létesítés állapotának ellenőrzése** folyamatot. 

1. Menjen Dynamics 365 Finance a Rendszerfelügyelet – **\> Beállítási folyamat \> automatizálása gombra.**
2. Az Elemzési **létesítés állapotának ellenőrzése a Háttérfolyamatok** **·** lapon, és válassza a **Szerkesztés** lehetőséget.
3. A **Következő végrehajtási mező** beállítása 30 perccel az aktuális idő előtt.

   Ennek a módosításnak arra kell kényszerítenie az **"Adatátépítési állapot** ellenőrzése" folyamatot, hogy azonnal fusson.

   Az Adatátépítési állapot ellenőrzése sikeres futtatása után engedélyezheti a Pénzügyi információk funkciókat a **·** **Szolgáltatáskezelés** munkaterületen.

## <a name="feedback-and-support"></a>Visszajelzés és támogatás

Ha visszajelzést szeretne küldeni, vagy ha segítségre van szüksége, e-mailt küld a Pénzügyi információk [(Előnézet)](mailto:fiap@microsoft.com) címre.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
