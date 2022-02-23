---
title: Az Attract-felhasználók nem tudnak állásokra jelentkezni a karrierportálon
description: Ez a témakör azt mutatja be, hogyan lehet elhárítani azt a hibát, amely miatt a felhasználók nem tudnak állásokra jelentkezni a karrier portálról.
author: andreabichsel
manager: AnnBe
ms.date: 09/23/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-09-23
ms.dyn365.ops.version: Platform update 24
ms.openlocfilehash: e1d72bef6d8bbe15e27326f66341915ba44a09b4
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4461366"
---
# <a name="attract-users-cant-apply-for-jobs-from-career-portal"></a>Az Attract-felhasználók nem tudnak állásokra jelentkezni a karrierportálon

[!include [banner](includes/banner.md)]

## <a name="issue"></a>Kiadás

Az Attract-felhasználók nem tudnak állásokra jelentkezni a karrierportálon. Amikor egy olyan munkára próbálnak jelentkezni, amely a Dynamics 365 Talent: Attract alkalmazásban lett létrehozva, a böngésző folyamatosan betölti az oldalt, és nem teljesíti a műveletet.

## <a name="cause"></a>Ok

Ez a probléma akkor fordul elő, ha a Talent kapcsolati csoport nem rendelkezik a Talent felhasználói szerepkörrel.

## <a name="resolution"></a>Felbontás

Rendelje hozzá a Talent felhasználói szerepkört a Talent kapcsolati csapathoz.

1. Jelentkezzen be az [Power Platform felügyeleti központba](https://admin.powerplatform.microsoft.com) a következő adminisztrátori hitelesítő adatokkal:

   - Dynamics 365 adminisztrátor
   - Globális adminisztrátor
   - Power Platform adminisztrátor

2. Válassza ki a navigációs ablak **Környezetek** elemét, majd válassza ki azt a környezetet, amelyben a Talent felhasználói szerepkört társítani szeretné a Talent-kapcsolati csapathoz.

   ![Környezet kiválasztása](./media/attract-troubleshoot-career-portal-select-environment.png)

3. A **Környezetek** ablaktáblán válassza ki a **Környezet URL-címét**, és jelentkezzen be a környezet adminisztrátori portálján (például https:<orgname>.crm.dynamics.com).

4. Válassza a **Beállítások** lehetőséget, válassza a **Rendszer** elemet , majd válassza a **Biztonság** elemet.

   ![Navigálás a Biztonság részhez](./media/attract-troubleshoot-career-portal-security.png)

5. Válassza a **Csapatok** lehetőséget.

   ![Csapatok kiválasztása](./media/attract-troubleshoot-career-portal-security-teams.png)

6. Keressen a **Talent kapcsolati csapat** kifejezésre a keresőmezőben, majd válassza ki a csapatot a keresési eredmények közül.

7. Válassza a menüszalag **SZEREPKÖRÖK KEZELÉSE** elemét.

8. A **Csapatszerepkörök kezelése** párbeszédablakban válassza ki a **Talent felhasználó** elemet a választható szerepkörök listájából, majd válassza az **OK** lehetőséget a szerepkör alkalmazásához.

   ![Szerepkör alkalmazása](./media/attract-troubleshoot-career-portal-apply-role.png)

9. Tesztelje a módosításokat:

   1. Jelentkezzen be a karrierportálra egy új böngészőablakból.
   2. Pályázzon állásra a karrierportálról. 