---
title: Alkalmazotti önkiszolgáló munkaterület nevének módosítása
description: Ez a témakör azt mutatja be, hogyan lehet módosítani az alkalmazott önkiszolgáló rendszer munkaterületének megjelenítendő nevét a Dynamics 365 Human Resources szolgáltatásban.
author: andreabichsel
manager: AnnBe
ms.date: 07/09/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: EssWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-07-09
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 2ce008c44ba84c919f4538be4d8e4ff95be018e7
ms.sourcegitcommit: 1ec931f8fe86bde27f6def36ea214a2a05fb22f6
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/13/2020
ms.locfileid: "3554353"
---
# <a name="change-employee-self-service-workspace-name"></a><span data-ttu-id="c84d7-103">Alkalmazotti önkiszolgáló munkaterület nevének módosítása</span><span class="sxs-lookup"><span data-stu-id="c84d7-103">Change Employee self service workspace name</span></span>

<span data-ttu-id="c84d7-104">Ha önkénteseket vagy más nem alkalmazottakat is alkalmaz, előfordulhat, hogy módosítani szeretné az **alkalmazott önkiszolgáló rendszer** munkaterületének nevét.</span><span class="sxs-lookup"><span data-stu-id="c84d7-104">If you have volunteers or other non-employees, you might want to change the name of the **Employee self-service** workspace.</span></span> <span data-ttu-id="c84d7-105">Ezt a munkaterületet módosíthatja ehelyett **Önkiszolgáló rendszerre**.</span><span class="sxs-lookup"><span data-stu-id="c84d7-105">You can change this workspace to **Self service** instead.</span></span>

> [!NOTE]
> <span data-ttu-id="c84d7-106">Az **Alkalmazott önkiszolgáló rendszer** munkaterülete nevének módosítása a belső használatra használt menüelemet is megváltoztatja a Dynamics 365 Human Resources szolgáltatásban.</span><span class="sxs-lookup"><span data-stu-id="c84d7-106">Changing the name of the **Employee self-service** workspace also changes the menu item that is used internally by Dynamics 365 Human Resources.</span></span> <span data-ttu-id="c84d7-107">Ha a **HcmEmployeeSelfServiceWorkspace** menüelemhez korábban alkalmazta a biztonsági testreszabásokat, akkor a **HcmSelfServiceWorkspace** elemhez ugyanezeket a változtatásokat ajánljuk a paritás fenntartása érdekében.</span><span class="sxs-lookup"><span data-stu-id="c84d7-107">If you previously applied security customizations to the **HcmEmployeeSelfServiceWorkspace** menu item, we recommend applying the same changes to **HcmSelfServiceWorkspace** to maintain parity.</span></span>

1. <span data-ttu-id="c84d7-108">A Human Resources szolgáltatásban válassza ki a **Személyzetkezelés** elemet , válassza ki a **hivatkozások** elemet, majd válassza ki a **emberi erőforrás paramétereit**.</span><span class="sxs-lookup"><span data-stu-id="c84d7-108">In Human Resources, select **Personnel management**, select **Links**, and then select **Human resources parameters**.</span></span>

2. <span data-ttu-id="c84d7-109">Válassza ki az **Alkalmazotti önkiszolgáló rendszer** lapját.</span><span class="sxs-lookup"><span data-stu-id="c84d7-109">Select the **Employee self-service** tab.</span></span>

3. <span data-ttu-id="c84d7-110">A **megjelenítendő név** területen válassza az **önkiszolgáló rendszer** elemet.</span><span class="sxs-lookup"><span data-stu-id="c84d7-110">Under **Display name**, select **Self service**.</span></span>

   ![Alkalmazotti önkiszolgáló munkaterület nevének módosítása Önkiszolgáló rendszerre](./media/hr-employee-self-service-workspace-name.png)

4. <span data-ttu-id="c84d7-112">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c84d7-112">Select **Save**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c84d7-113">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="c84d7-113">Additional resources</span></span>

- [<span data-ttu-id="c84d7-114">Alkalmazotti és vezetői önkiszolgálás áttekintése</span><span class="sxs-lookup"><span data-stu-id="c84d7-114">Employee and Manager self-service overview</span></span>](hr-employee-manager-self-service-overview.md)
