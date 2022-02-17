---
title: A Human Resources szolgáltatás nem jelenik meg a Microsoft Dynamics 365 alkalmazásai között
description: Ez a téma elmagyarázza, mi a teendő, ha a Microsoft Dynamics 365 Human Resources nem szerepel a Microsoft Dynamics 365 alkalmazások között.
author: twheeloc
ms.date: 08/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 4bdbe6c4065a8266fd30a3b093743ded91524f6a
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/31/2022
ms.locfileid: "8069680"
---
# <a name="human-resources-app-doesnt-appear-in-microsoft-dynamics-365-apps"></a>A humánerőforrás alkalmazás nem jelenik meg a Microsoft Dynamics 365 alkalmazások között


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

**Probléma**

A vevő nem látja a Dynamics 365 Human Resources alkalmazást a Microsoft Dynamics 365-alkalmazások között.

**Feloldás**

A felhasználót hozzá kell adni a környezet Környezetkészítő szerepköréhez a Microsoft Power Apps szolgáltatásban.

1. A rendszergazdának, aki a Power Apps 2. csomag licenccel rendelkezik, meg kell nyitnia a [Power Apps felügyeleti központot](https://preview.admin.powerapps.com/).

2. Válassza a **Környezetek** lehetőséget, majd válassza ki a megfelelő környezetet a Human Resources számára.

3. A **Biztonság** lapon a **Környezeti szerepkörök** lapon válassza a **Környezetkészítő** lehetőséget.

    ![Környezeti szerepkörök lap.](media/environment-roles.png)

4. A **Felhasználók** lapon adja hozzá a felhasználót vagy a szervezetet.

    ![Felhasználók lap.](media/environment-maker.png)

5. Válassza a **Mentés** lehetőséget.

6. A felhasználónak most be kell jelentkeznie a [Microsoft Dynamics 365](https://home.dynamics.com/) szolgáltatásba.

7. Válassza a **Szinkronizálás** elemet a felhasználói alkalmazások frissítéséhez.

    ![Szinkronizálás gomb.](media/get-more.png)

    A szinkronizálás befejezése után a Human Resources szolgáltatás megjelenik a kezdőlapon.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
