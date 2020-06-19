---
title: A Human Resources szolgáltatás nem jelenik meg a Microsoft Dynamics 365 alkalmazásai között
description: Ez a cikk bemutatja, mi a teendő, ha a vevő nem látja a Microsoft Dynamics 365 Human Resources alkalmazást a Microsoft Dynamics 365 alkalmazások között.
author: andreabichsel
manager: AnnBe
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
ms.openlocfilehash: cbf47b4673e1c97965bba7728e5669b7639c4d56
ms.sourcegitcommit: ba340f836e472f13f263dec46a49847c788fca44
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/04/2020
ms.locfileid: "3431084"
---
# <a name="human-resources-doesnt-appear-in-microsoft-dynamics-365-apps"></a>A Human Resources szolgáltatás nem jelenik meg a Microsoft Dynamics 365 alkalmazásai között

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
