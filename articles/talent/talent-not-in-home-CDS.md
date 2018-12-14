---
title: "A Talent nem jelenik meg a Microsoft Dynamics 365 alkalmazások között (CDS1.0)"
description: "Ez a témakör bemutatja, mi a teendő, ha a vevő nem látja a Microsoft Dynamics 365 for Talent alkalmazást a Microsoft Dynamics 365 alkalmazások között."
author: Darinkramer
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.translationtype: HT
ms.sourcegitcommit: d3f974f94b6c327fd70b8098d24f9e1f1e1e8eeb
ms.openlocfilehash: 32ae0ab807e953bd811a557e6878b9bee79d293c
ms.contentlocale: hu-hu
ms.lasthandoff: 12/04/2018

---

# <a name="talent-doesnt-appear-among-the-microsoft-dynamics-365-apps-cds10"></a>A Talent nem jelenik meg a Microsoft Dynamics 365 alkalmazások között (CDS1.0)

[!include [banner](includes/banner.md)]

**Probléma**

A vevő nem látja a Microsoft Dynamics 365 for Talent alkalmazást a Microsoft Dynamics 365 alkalmazások között.

**Felbontás**

A felhasználót hozzá kell adni a környezet Környezetkészítő szerepköréhez a Microsoft PowerApps szolgáltatásban.

1. A rendszergazdának, aki a PowerApps csomag 2 licenccel rendelkezik, meg kell nyitnia a [PowerApps felügyeleti központot](https://preview.admin.powerapps.com/).
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

