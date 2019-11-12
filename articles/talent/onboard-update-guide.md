---
title: Felvételi útmutatók frissítése a Dynamics 365 Talent – Onboard szolgáltatásban
description: Ez a témakör azt ismerteti, hogy miként frissíthetők a Microsoft Dynamics 365 Talent – Onboard felvételi útmutatói, illetve hogyan lehet a meglévő útmutatók módosításait leküldeni.
author: andreabichsel
manager: ''
ms.date: 06/21/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: HcmCourseType, HcmCourseTypeGroup, HRMCourseTable
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Talent
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2019-06-21
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 071aa79ea75e9a94187dd74dabab940e2cce0f92
ms.sourcegitcommit: 75db3b75d35d27034f9b56e7119c9d0cb7666830
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/03/2019
ms.locfileid: "2551956"
---
# <a name="update-onboarding-guides-in-dynamics-365-talent---onboard"></a>Felvételi útmutatók frissítése a Dynamics 365 Talent – Onboard szolgáltatásban

[!include [banner](includes/banner.md)]

Ha módosítania kell a felvételi útmutatókat a Microsoft Dynamics 365 Talent: Onboard szolgáltatásban, frissítheti őket, és érvényesítheti a változtatásokat, még akkor is, ha már kiküldte az útmutatókat. A felvételi útmutató frissítéséhez két lehetőség közül választhat:

- Szerkessze közvetlenül a felvételi útmutatót, és mentse a változtatásokat.
- Szerkessze a felvételi sablont, majd érvényesítse a változtatásokat az abból létrehozott összes felvételi útmutatóban.

## <a name="edit-an-onboarding-guide-directly"></a>Felvételi útmutató szerkesztése közvetlenül

1. A bal oldali menüben válassza a **Guides** lehetőséget.
2. Jelölje ki a szerkeszteni kívánt útmutatót.
3. Végezze el az összes kívánt változtatást, majd válassza a **Mentés** gombra (a lemez szimbólumra).

    ![[A felvételi útmutató módosításainak mentéése](./media/onboard-save.png)](./media/onboard-save.png)

Az Onboard automatikusan e-mailt küld az újonnan felvett személynek, amelyben bemutatja a változtatásokat. Az egyszerű azonosítás érdekében egy piros **Új** címke jelenik meg minden egyes változtatás mellett.

## <a name="update-multiple-guides-by-editing-the-onboarding-template"></a>Több útmutató frissítése a felvételi sablon szerkesztésével

1. A bal oldali menüben válassza a **Sablonok** lehetőséget.
2. A **Saját sablonok** területen válassza ki a szerkeszteni kívánt sablont.
3. Végezze el az összes kívánt változtatást, majd válassza a **Mentés** gombra (a lemez szimbólumra).
4. Ha azt szeretné, hogy a módosítások a sablonon alapuló összes útmutatóban érvényesüljenek, válassza a **Módosítások áttolása** lehetőséget.

    ![[A felvételi sablon változtatásainak érvényesítése az abból létrehozott összes felvételi útmutatóban](./media/onboard-push-changes.png)](./media/onboard-push-changes.png)

A módosítások láthatóvá válnak az új dolgozóknak, akik megnyitják a felvételi útmutatókat. Az Onboard azonban nem küld e-mail-értesítést az új dolgozók számára, hogy tudassa velük, hogy a felvételi útmutató módosult. Az egyszerű azonosítás érdekében egy piros **Új** címke jelenik meg minden egyes változtatás mellett. 
