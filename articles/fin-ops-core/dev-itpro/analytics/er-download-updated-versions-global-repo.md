---
title: Az ER-konfigurációk frissített verzióinak importálása
description: Ez a témakör azt mutatja be, hogyan lehet importálni az elektronikus jelentéskészítési (ER) konfigurációk frissített verzióit a konfigurációs szolgáltatás globális tárából.
author: NickSelin
manager: AnnBe
ms.date: 06/09/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERSolutionImport, ERWorkspace, ERSolutionRepositoryTable
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 105843
ms.assetid: dc44dea2-22ce-401e-98b9-d289e0e2825b
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: 897663998c6c95ff6d7172de2abc4d4dd6ec5f12
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/05/2020
ms.locfileid: "4679510"
---
# <a name="import-updated-versions-of-er-configurations"></a><span data-ttu-id="6d923-103">Az ER-konfigurációk frissített verzióinak importálása</span><span class="sxs-lookup"><span data-stu-id="6d923-103">Import updated versions of ER configurations</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6d923-104">Az elektronikus jelentéskészítési (ER) [adattárak](general-electronic-reporting.md#Repository) az [ER-konfigurációk](general-electronic-reporting.md#Configuration) megosztására szolgálnak.</span><span class="sxs-lookup"><span data-stu-id="6d923-104">Electronic reporting (ER) [repositories](general-electronic-reporting.md#Repository) are used to share [ER configurations](general-electronic-reporting.md#Configuration).</span></span> <span data-ttu-id="6d923-105">Az ER-konfigurációkat különböző adattárakból [importálhatja](download-electronic-reporting-configuration-lcs.md) a Microsoft Dynamics 365 Finance-példányába.</span><span class="sxs-lookup"><span data-stu-id="6d923-105">You can [import](download-electronic-reporting-configuration-lcs.md) ER configurations from different repositories into your instance of Microsoft Dynamics 365 Finance.</span></span> <span data-ttu-id="6d923-106">Az ER-konfigurációk importálásakor a [konfigurációszolgáltatók](general-electronic-reporting.md#Provider) közzétehetik új [verziók](general-electronic-reporting.md#component-versioning) adattárait, így azok megoszthatók.</span><span class="sxs-lookup"><span data-stu-id="6d923-106">When you import ER configurations, [configuration providers](general-electronic-reporting.md#Provider) can publish new [versions](general-electronic-reporting.md#component-versioning) repositories so that they can be shared.</span></span>

<span data-ttu-id="6d923-107">Ez a témakör azt mutatja be, hogyan lehet importálni az ER-konfigurációk frissített verzióit a konfigurációs szolgáltatás globális tárából.</span><span class="sxs-lookup"><span data-stu-id="6d923-107">This topic explains how to import updated versions of ER configurations from the Global repository of the Configuration service.</span></span> <span data-ttu-id="6d923-108">A további tudnivalókat lásd: [Microsoft Dynamics 365 for Finance and Operations - Regulatory services, konfigurációs szolgáltatás](https://docs.microsoft.com/business-applications-release-notes/october18/dynamics365-finance-operations/regulatory-service-configuration).</span><span class="sxs-lookup"><span data-stu-id="6d923-108">For more information, see [Microsoft Dynamics 365 for Finance and Operations - Regulatory Services, Configuration service](https://docs.microsoft.com/business-applications-release-notes/october18/dynamics365-finance-operations/regulatory-service-configuration).</span></span>

## <a name="review-the-available-updated-versions"></a><span data-ttu-id="6d923-109">A rendelkezésre álló frissített verziók áttekintése</span><span class="sxs-lookup"><span data-stu-id="6d923-109">Review the available updated versions</span></span>

1. <span data-ttu-id="6d923-110">Jelentkezzen be a Finance and Operations rendszerbe az alábbi szerepkörök egyikének használatával:</span><span class="sxs-lookup"><span data-stu-id="6d923-110">Sign in to Finance by using one of the following roles:</span></span>

    - <span data-ttu-id="6d923-111">Elektronikus jelentések fejlesztője</span><span class="sxs-lookup"><span data-stu-id="6d923-111">Electronic reporting developer</span></span>
    - <span data-ttu-id="6d923-112">Elektronikus jelentések funkcióival foglalkozó konzulens</span><span class="sxs-lookup"><span data-stu-id="6d923-112">Electronic reporting functional consultant</span></span>
    - <span data-ttu-id="6d923-113">Rendszergazda</span><span class="sxs-lookup"><span data-stu-id="6d923-113">System administrator</span></span>

2. <span data-ttu-id="6d923-114">Ugorjon a **Szervezeti adminisztráció** \> **Munkaterületek** \> **Elektronikus jelentés** pontra.</span><span class="sxs-lookup"><span data-stu-id="6d923-114">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
3. <span data-ttu-id="6d923-115">A **Honosítási konfigurációk** oldalon, a **Kapcsolódó hivatkozások** szakaszban, válassza a **Konfigurációk verziófrissítéseinek importálása** elemet.</span><span class="sxs-lookup"><span data-stu-id="6d923-115">On the **Localization configurations** page, in the **Related links** section, select **Import configurations versions updates**.</span></span>

    ![Honosítási konfigurációk oldala](./media/er-download-updated-versions-global-repo1.png)

4. <span data-ttu-id="6d923-117">Az **Elektronikus jelentéskészítési konfigurációk verziófrissítéseinek importálása** párbeszédpanel **Futtatási mód** mezőjében válassza a **Csak rendelkezésre álló frissítések megjelenítése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="6d923-117">In the **Import electronic reporting configurations versions updates** dialog box, in the **Run mode** field, select **Only show available updates**.</span></span> <span data-ttu-id="6d923-118">Majd kattintson az **OK** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="6d923-118">Then select **OK**.</span></span> 

    ![A Futtatási mód mező Csak rendelkezésre álló frissítések megjelenítése beállítással](./media/er-download-updated-versions-global-repo2.png)

5. <span data-ttu-id="6d923-120">Tekintse át a kapott üzeneteket.</span><span class="sxs-lookup"><span data-stu-id="6d923-120">Review the messages that you receive.</span></span> <span data-ttu-id="6d923-121">Ezek az üzenetek a következő információkat tartalmazzák az aktuális Finance-példányban található ER-konfigurációkról, valamint a globális adattár tartalmának összehasonlításáról:</span><span class="sxs-lookup"><span data-stu-id="6d923-121">These messages provide the following information about the ER configurations in the current Finance instance and how they compare to the content of the Global repository:</span></span>

    - <span data-ttu-id="6d923-122">Az ER-konfigurációk teljes száma</span><span class="sxs-lookup"><span data-stu-id="6d923-122">The total number of ER configurations</span></span>
    - <span data-ttu-id="6d923-123">A globális adattárban nem szereplő ER-konfigurációk száma.</span><span class="sxs-lookup"><span data-stu-id="6d923-123">ER configurations that aren't present in the Global repository</span></span>
    - <span data-ttu-id="6d923-124">Azok az ER-konfigurációk, amelyekhez a legfrissebb verzió már elérhető az aktuális Finance-példányban (ha meg szeretné tekinteni ezeknek az ER-konfigurációknak a teljes listáját, válassza az **Üzenet részletei** hivatkozást).</span><span class="sxs-lookup"><span data-stu-id="6d923-124">ER configurations for which the latest version is already available in the current Finance instance (To view the full list of these ER configurations, select the **Message details** link.)</span></span>

        !["A következő konfigurációk legújabb verziói már importálva vannak" üzenet és az üzenet részletei](./media/er-download-updated-versions-global-repo3.png)

    - <span data-ttu-id="6d923-126">Azok az ER-konfigurációk, amelyekhez a legfrissebb verzió elérhető a globális adattárban, és amelyek az aktuális Finance-példányba importálhatók (ha meg szeretné tekinteni ezeknek az ER-konfigurációknak a teljes listáját, válassza az **Üzenet részletei** hivatkozást).</span><span class="sxs-lookup"><span data-stu-id="6d923-126">ER configurations for which the latest version is available in the Global repository and can be imported into the current Finance instance (To view the full list of these ER configurations, select the **Message details** link.)</span></span>

        !["Elérhető frissítések" üzenet és az üzenet részletei](./media/er-download-updated-versions-global-repo4.png)

## <a name="import-available-updated-versions"></a><span data-ttu-id="6d923-128">A rendelkezésre álló frissített verziók importálása</span><span class="sxs-lookup"><span data-stu-id="6d923-128">Import available updated versions</span></span>

1. <span data-ttu-id="6d923-129">Jelentkezzen be a Finance and Operations rendszerbe az alábbi szerepkörök egyikének használatával:</span><span class="sxs-lookup"><span data-stu-id="6d923-129">Sign in to Finance by using one of the following roles:</span></span>

    - <span data-ttu-id="6d923-130">Elektronikus jelentések fejlesztője</span><span class="sxs-lookup"><span data-stu-id="6d923-130">Electronic reporting developer</span></span>
    - <span data-ttu-id="6d923-131">Elektronikus jelentések funkcióival foglalkozó konzulens</span><span class="sxs-lookup"><span data-stu-id="6d923-131">Electronic reporting functional consultant</span></span>
    - <span data-ttu-id="6d923-132">Rendszergazda</span><span class="sxs-lookup"><span data-stu-id="6d923-132">System administrator</span></span>

2. <span data-ttu-id="6d923-133">Ugorjon a **Szervezeti adminisztráció** \> **Munkaterületek** \> **Elektronikus jelentés** pontra.</span><span class="sxs-lookup"><span data-stu-id="6d923-133">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
3. <span data-ttu-id="6d923-134">A **Honosítási konfigurációk** oldalon, a **Kapcsolódó hivatkozások** szakaszban, válassza a **Konfigurációk verziófrissítéseinek importálása** elemet.</span><span class="sxs-lookup"><span data-stu-id="6d923-134">On the **Localization configurations** page, in the **Related links** section, select **Import configurations versions updates**.</span></span>
4. <span data-ttu-id="6d923-135">Az **Elektronikus jelentéskészítési konfigurációk verziófrissítéseinek importálása** párbeszédpanel **Futtatási mód** mezőjében válassza a **Legújabb frissítések importálása** lehetőséget, ha a globális adattárból az ER-konfigurációk legfrissebb verzióit szeretné importálni az aktuális Finance-példányba.</span><span class="sxs-lookup"><span data-stu-id="6d923-135">In the **Import electronic reporting configurations versions updates** dialog box, in the **Run mode** field, select **Import latest updates** to import the latest versions of ER configurations from the Global repository into the current Finance instance.</span></span>
5. <span data-ttu-id="6d923-136">Ha ütemezni szeretne egy kötegelt feladatot az importáláshoz, a **Futtatás a háttérben** gyorslapon állítsa a **Kötegelt feldolgozás** beállítást **Igen** értékre.</span><span class="sxs-lookup"><span data-stu-id="6d923-136">To schedule a batch job for the import, on the **Run in the background** FastTab, set the **Batch processing** option to **Yes**.</span></span> <span data-ttu-id="6d923-137">Ha időnként meg szeretné ismételni az importálást, konfigurálja a szükséges ismétlődést.</span><span class="sxs-lookup"><span data-stu-id="6d923-137">If you want to repeat the import periodically, configure the required recurrence.</span></span>

    ![Futtatási mód mező a Legújabb frissítések importálása beállítással](./media/er-download-updated-versions-global-repo5.png)

6. <span data-ttu-id="6d923-139">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="6d923-139">Select **OK**.</span></span>
7. <span data-ttu-id="6d923-140">A következő lépések egyikével megtudhatja, hogy mely konfigurációverziók importálása történt meg:</span><span class="sxs-lookup"><span data-stu-id="6d923-140">To learn what configuration versions have been imported, follow one of these steps:</span></span>

    - <span data-ttu-id="6d923-141">Ha az importálást interaktívan futtatja a kötegelt feladat használata helyett, tekintse át a kapott üzeneteket.</span><span class="sxs-lookup"><span data-stu-id="6d923-141">If you run the import interactively instead of using a batch job, review the messages that you receive.</span></span>

        ![Interaktív importálás futtatása közben kapott üzenetek](./media/er-download-updated-versions-global-repo6.png)

    - <span data-ttu-id="6d923-143">Ha kötegelt módban futtatja az importálást, hajtsa végre a következő lépéseket:</span><span class="sxs-lookup"><span data-stu-id="6d923-143">If you run the import in batch mode, follow these steps:</span></span>

        1. <span data-ttu-id="6d923-144">Lépjen az **Általános** \> **Lekérdezések** \> **Kötegelt feladatok** \> **Saját kötegelt feladatok** pontra.</span><span class="sxs-lookup"><span data-stu-id="6d923-144">Go to **Common** \> **Inquiries** \> **Batch jobs** \> **My batch jobs**.</span></span>
        2. <span data-ttu-id="6d923-145">Keresse meg és jelölje ki az **Elektronikus jelentéskészítési konfigurációk verziófrissítéseinek importálása** feladatot, majd a művelet ablaktáblán a **Kötegelt feladat** lapon válassza a **Kötegelt feladat előzményei** lehetőséget a feladatok előzményeinek megtekintéséhez.</span><span class="sxs-lookup"><span data-stu-id="6d923-145">Find and select the **Import electronic reporting configurations versions updates** job, and then, on the Action Pane, on the **Batch job** tab, select **Batch job history** to view the job history.</span></span>
        3. <span data-ttu-id="6d923-146">A **Kötegelt feladat előzményei** oldalon válassza a **Napló** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="6d923-146">On the **Batch job history** page, select **Log**.</span></span> <span data-ttu-id="6d923-147">Ezután a megjelenő üzenetben válassza ki az **Üzenet részletei** hivatkozást a feladat naplójának megtekintéséhez.</span><span class="sxs-lookup"><span data-stu-id="6d923-147">Then, in the message that you receive, select the **Message details** link to view the job log.</span></span>

        ![Feladat naplója](./media/er-download-updated-versions-global-repo7.png)

> [!IMPORTANT]
> <span data-ttu-id="6d923-149">A program nem javasolja ismétlődő kötegeltfeladat-ütemezést az ER-konfigurációk frissített verzióinak közvetlenül a globális adattárból a működési környezetbe való importálásához, mert az importált verziók azonnal használhatók.</span><span class="sxs-lookup"><span data-stu-id="6d923-149">We don't recommend that you schedule a recurring batch job to import updated versions of ER configurations directly from the Global repository into a production environment, because the imported versions will immediately be available for use.</span></span> <span data-ttu-id="6d923-150">Ehelyett ennek a módszernek a segítségével egy tesztkörnyezetbe telepítse az ER-konfigurációk verzióit.</span><span class="sxs-lookup"><span data-stu-id="6d923-150">Instead, use this approach to deploy versions of ER configurations to a sandbox environment.</span></span> <span data-ttu-id="6d923-151">Ezeket azután a tesztkörnyezetében lehet értékelni, mielőtt termelési környezetbe telepítené őket.</span><span class="sxs-lookup"><span data-stu-id="6d923-151">They can then be evaluated in the sandbox environment before they are deployed to a production environment.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="6d923-152">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="6d923-152">Additional resources</span></span>

- [<span data-ttu-id="6d923-153">Elektronikus jelentéskészítés (ER) áttekintése</span><span class="sxs-lookup"><span data-stu-id="6d923-153">Electronic reporting (ER) overview</span></span>](general-electronic-reporting.md)
- [<span data-ttu-id="6d923-154">ER-konfigurációk letöltése a konfigurációs szolgáltatás globális tárából</span><span class="sxs-lookup"><span data-stu-id="6d923-154">Download ER configurations from the Global repository of Configuration service</span></span>](er-download-configurations-global-repo.md)
