---
title: A Talent nem jelenik meg a Microsoft Dynamics 365 alkalmazások között (Common Data Service 1.0)
description: Ez a témakör bemutatja, mi a teendő, ha a vevő nem látja a Microsoft Dynamics 365 Talent alkalmazást a Microsoft Dynamics 365 alkalmazások között.
author: andreabichsel
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.openlocfilehash: a44d2e43752960d3026fa7ac92c7b261aee05448
ms.sourcegitcommit: 871707a3fd236da693a3d51f401eb0cb9d4bae39
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/06/2019
ms.locfileid: "2897027"
---
# <a name="talent-doesnt-appear-among-the-microsoft-dynamics-365-apps-common-data-service-10"></a>A Talent nem jelenik meg a Microsoft Dynamics 365 alkalmazások között (Common Data Service 1.0)

**Kibocsátás**

A vevő nem látja a Microsoft Dynamics 365 Talent alkalmazást a Microsoft Dynamics 365 alkalmazások között.

**Felbontás**

A felhasználót hozzá kell adni a környezet Környezetkészítő szerepköréhez a Microsoft Power Apps szolgáltatásban.

1. A rendszergazdának, aki a Power Apps 2. csomag licenccel rendelkezik, meg kell nyitnia a [Power Apps felügyeleti központot](https://preview.admin.powerapps.com/).
2. Válassza a **Környezetek** lehetőséget, majd válassza ki a megfelelő környezetet a Talent számára.
3. A **Biztonság** lapon a **Környezeti szerepkörök** lapon válassza a **Környezetkészítő** lehetőséget.

    ![Környezeti szerepkörök lap](media/environment-roles.png)

4. A **Felhasználók** lapon adja hozzá a felhasználót vagy a szervezetet.

    ![Felhasználók lap](media/environment-maker.png)

5. Válassza a **Mentés** lehetőséget.
6. A felhasználónak most be kell jelentkeznie a [Microsoft Dynamics 365](https://home.dynamics.com/) szolgáltatásba.
7. Válassza a **Szinkronizálás** elemet a felhasználói alkalmazások frissítéséhez.

    ![Szinkronizálás gomb](media/get-more.png)

    A szinkronizálás befejezése után a Talent megjelenik a kezdőlapon.
