---
title: A Human Resources szolgáltatás nem jelenik meg a Microsoft Dynamics 365 alkalmazásai között
description: Ez a cikk bemutatja, mi a teendő, ha a vevő nem látja a Microsoft Dynamics 365 Human Resources alkalmazást a Microsoft Dynamics 365 alkalmazások között.
author: andreabichsel
manager: tfehr
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 9be1c2b862a01d6f14ad98dbcb01e061649c6af0
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/17/2021
ms.locfileid: "5463984"
---
# <a name="human-resources-doesnt-appear-in-microsoft-dynamics-365-apps"></a>A Human Resources szolgáltatás nem jelenik meg a Microsoft Dynamics 365 alkalmazásai között

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

**Kibocsátás**

A vevő nem látja a Dynamics 365 Human Resources alkalmazást a Microsoft Dynamics 365-alkalmazások között.

**Feloldás**

A felhasználót hozzá kell adni a környezet Környezetkészítő szerepköréhez a Microsoft Power Apps szolgáltatásban.

1. A rendszergazdának, aki a Power Apps 2. csomag licenccel rendelkezik, meg kell nyitnia a [Power Apps felügyeleti központot](https://preview.admin.powerapps.com/).

2. Válassza a **Környezetek** lehetőséget, majd válassza ki a megfelelő környezetet a Human Resources számára.

3. A **Biztonság** lapon a **Környezeti szerepkörök** lapon válassza a **Környezetkészítő** lehetőséget.

    ![Környezeti szerepkörök lap](media/environment-roles.png)

4. A **Felhasználók** lapon adja hozzá a felhasználót vagy a szervezetet.

    ![Felhasználók lap](media/environment-maker.png)

5. Válassza a **Mentés** lehetőséget.

6. A felhasználónak most be kell jelentkeznie a [Microsoft Dynamics 365](https://home.dynamics.com/) szolgáltatásba.

7. Válassza a **Szinkronizálás** elemet a felhasználói alkalmazások frissítéséhez.

    ![Szinkronizálás gomb](media/get-more.png)

    A szinkronizálás befejezése után a Human Resources szolgáltatás megjelenik a kezdőlapon.


[!INCLUDE[footer-include](../includes/footer-banner.md)]