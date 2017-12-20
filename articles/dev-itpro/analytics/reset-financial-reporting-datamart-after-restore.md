---
title: "A pénzügyi jelentési adatpiac alaphelyzetbe állítása."
description: "Ez a témakör a pénzügyi jelentési adatpiac alaphelyzetbe állítását ismerteti."
author: aolson
manager: AnnBe
ms.date: 12/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 261824
ms.search.region: Global
ms.author: aloson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 0786d3377b914791106ef30455d676e5ab2ae03d
ms.openlocfilehash: c708fa18b8676d8ff57c26b3176a36d86df29387
ms.contentlocale: hu-hu
ms.lasthandoff: 12/07/2017

---

# <a name="reset-the-financial-reporting-data-mart"></a><span data-ttu-id="00ae3-103">A pénzügyi jelentési adatpiac alaphelyzetbe állítása.</span><span class="sxs-lookup"><span data-stu-id="00ae3-103">Reset the Financial reporting data mart</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="00ae3-104">Ez a témakör a pénzügyi jelentési adatpiac alaphelyzetbe állítását mutatja be a következő verziókhoz :</span><span class="sxs-lookup"><span data-stu-id="00ae3-104">This topic explains how to reset the Financial reporting data mart for the following versions:</span></span>

- <span data-ttu-id="00ae3-105">Microsoft Dynamics 365 for Finance and Operations: Financial Reporting, 7.2.6.0-s és későbbi verziók</span><span class="sxs-lookup"><span data-stu-id="00ae3-105">Microsoft Dynamics 365 for Finance and Operations Financial reporting release 7.2.6.0 and later</span></span>
- <span data-ttu-id="00ae3-106">Microsoft Dynamics 365 for Finance and Operations: Financial Reporting, 7.0.10000.4-es és későbbi verziók</span><span class="sxs-lookup"><span data-stu-id="00ae3-106">Microsoft Dynamics 365 for Finance and Operations Financial reporting release 7.0.10000.4 and later</span></span>
- <span data-ttu-id="00ae3-107">Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition (on-premises)</span><span class="sxs-lookup"><span data-stu-id="00ae3-107">Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (on-premises)</span></span>

<span data-ttu-id="00ae3-108">A Finance and Operations Financial Reporting 7.2.6.0-s verziójának beszerzéséhez töltse le a 4052514-es tudásbáziscikket a <https://support.microsoft.com/en-us/help/4052514> oldalról.</span><span class="sxs-lookup"><span data-stu-id="00ae3-108">To get Finance and Operations Financial reporting release 7.2.6.0, you can download KB 4052514 from <https://support.microsoft.com/en-us/help/4052514>.</span></span>

## <a name="reset-the-financial-reporting-data-mart-for-finance-and-operations-financial-reporting-release-7260-and-later"></a><span data-ttu-id="00ae3-109">A pénzügyi jelentési adatpiac alaphelyzetbe állítása a Finance and Operations Financial Reporting 7.2.6.0-s és későbbi verzióinál</span><span class="sxs-lookup"><span data-stu-id="00ae3-109">Reset the Financial reporting data mart for Finance and Operations Financial reporting release 7.2.6.0 and later</span></span>

### <a name="reset-the-financial-reporting-data-mart-from-report-designer"></a><span data-ttu-id="00ae3-110">A pénzügyi jelentési adatpiac alaphelyzetbe állítása a Jelentéstervezőből</span><span class="sxs-lookup"><span data-stu-id="00ae3-110">Reset the Financial reporting data mart from Report designer</span></span>

> [!NOTE]
> <span data-ttu-id="00ae3-111">Ezen folyamat lépései a Finance and Operations Financial Reporting 7.2.6.0 és későbbi verzióiban támogatottak.</span><span class="sxs-lookup"><span data-stu-id="00ae3-111">The steps in this process are supported for Finance and Operations Financial reporting release 7.2.6.0 and later.</span></span> <span data-ttu-id="00ae3-112">Ha Ön korábbi kiadást használ, forduljon a támogatási csapathoz segítségért.</span><span class="sxs-lookup"><span data-stu-id="00ae3-112">If you have an earlier release, contact the Support team for assistance.</span></span>

<span data-ttu-id="00ae3-113">Bizonyos esetekben előfordulhat, hogy alaphelyzetbe kell állítania a pénzügyi jelentési adatpiacot.</span><span class="sxs-lookup"><span data-stu-id="00ae3-113">In specific scenarios, you might have to reset the data mart for Financial reporting.</span></span> <span data-ttu-id="00ae3-114">A feladat a Jelentéstervező ügyfélprogramban végezhető el.</span><span class="sxs-lookup"><span data-stu-id="00ae3-114">You can complete this task in the Report designer client.</span></span> <span data-ttu-id="00ae3-115">Íme néhány forgatókönyv, ahol alaphelyzetbe kell állítania az adatpiacot:</span><span class="sxs-lookup"><span data-stu-id="00ae3-115">Here are some scenarios where you might have to reset the data mart:</span></span>

- <span data-ttu-id="00ae3-116">A Finance and Operations adatbázist visszaállították, de az adatpiac adatbázis visszaállítására nem került sor.</span><span class="sxs-lookup"><span data-stu-id="00ae3-116">The Finance and Operations database was restored, but the data mart database wasn't restored.</span></span>
- <span data-ttu-id="00ae3-117">Egy adott időszakban hibás adatok jelennek meg.</span><span class="sxs-lookup"><span data-stu-id="00ae3-117">You see incorrect data for a period.</span></span>
- <span data-ttu-id="00ae3-118">A Támogatás arra utasítja, hogy hibaelhárítás részeként állítsa alaphelyzetbe az adatpiacot.</span><span class="sxs-lookup"><span data-stu-id="00ae3-118">Support instructs you to reset the data mart as part of a troubleshooting step.</span></span>

<span data-ttu-id="00ae3-119">Az adatpiac alaphelyzetbe állítása csak olyan időszakokban végezhető el, amikor az adatbázisban az adatfeldolgozás mennyisége kicsi.</span><span class="sxs-lookup"><span data-stu-id="00ae3-119">The data mart reset should be done only during times when the amount of processing on the database is small.</span></span> <span data-ttu-id="00ae3-120">A pénzügyi jelentések nem érhetők el a visszaállítási folyamat során.</span><span class="sxs-lookup"><span data-stu-id="00ae3-120">Financial reporting will be unavailable during the reset process.</span></span>

#### <a name="reset-the-data-mart"></a><span data-ttu-id="00ae3-121">Az adatpiac alaphelyzetbe állítása</span><span class="sxs-lookup"><span data-stu-id="00ae3-121">Reset the data mart</span></span>

<span data-ttu-id="00ae3-122">Az adatpiac visszaállításához a Jelentéstervezőben az **Eszközök** menüben válassza a **Data Mart alaphelyzetbe állítása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="00ae3-122">To reset the data mart, in Report designer, on the **Tools** menu, select **Reset Data Mart**.</span></span> <span data-ttu-id="00ae3-123">A megjelenő párbeszédpanel két részből áll: **Statisztika** és **Alaphelyzetbe állítás**.</span><span class="sxs-lookup"><span data-stu-id="00ae3-123">The dialog box that appears has two sections: **Statistics** and **Reset**.</span></span>

<span data-ttu-id="00ae3-124">[![Data Mart alaphelyzetbe állítása párbeszédpanel](./media/Statistics.png)](./media/Statistics.png)</span><span class="sxs-lookup"><span data-stu-id="00ae3-124">[![Reset Data Mart dialog box](./media/Statistics.png)](./media/Statistics.png)</span></span>

##### <a name="integration-attempts"></a><span data-ttu-id="00ae3-125">Integrációs kísérletek</span><span class="sxs-lookup"><span data-stu-id="00ae3-125">Integration attempts</span></span>

<span data-ttu-id="00ae3-126">Az **Integrációs kísérletek** rács mutatja, hogy a rendszer hányszor próbált tranzakciókat integrálni.</span><span class="sxs-lookup"><span data-stu-id="00ae3-126">The **Integration attempts** grid shows how many times the system has tried to integrate transactions.</span></span> <span data-ttu-id="00ae3-127">A rendszer napokon keresztül továbbra is törekszik az adatok integrálására, ha az első néhány kísérlet sikertelen volt.</span><span class="sxs-lookup"><span data-stu-id="00ae3-127">The system continues to try to integrate data over a period of days if the first few attempts aren't successful.</span></span> <span data-ttu-id="00ae3-128">Akkor tudhatja, hogy az adatpiacot alaphelyzetbe kell állítani, ha a kísérletek száma 8 vagy több, és ha sok dimenziókombináció vagy tranzakciós rekord van jelen.</span><span class="sxs-lookup"><span data-stu-id="00ae3-128">You will know that the data mart must be reset is if the number of attempts is 8 or more, and if there are many Dimension combination or Transaction records.</span></span> <span data-ttu-id="00ae3-129">Ebben a helyzetben az adatokból nem lehet jelentést készíteni.</span><span class="sxs-lookup"><span data-stu-id="00ae3-129">In this situation, the data won't be reported on.</span></span>

##### <a name="data-status"></a><span data-ttu-id="00ae3-130">Adatok állapota</span><span class="sxs-lookup"><span data-stu-id="00ae3-130">Data status</span></span>

<span data-ttu-id="00ae3-131">Az **Adatok állapota** rács pillanatképet ad az adatpiacon található tranzakciókról, átváltási árfolyamokról és dimenzióértékekről.</span><span class="sxs-lookup"><span data-stu-id="00ae3-131">The **Data status** grid provides a snapshot of the transactions, exchange rates, and dimension values in the data mart.</span></span> <span data-ttu-id="00ae3-132">Az elavult rekordok nagy száma azt jelzi, hogy számos rekordfrissítésre került sor.</span><span class="sxs-lookup"><span data-stu-id="00ae3-132">A large number of stale records indicates that numerous updates to the records have occurred.</span></span> <span data-ttu-id="00ae3-133">Ebben a helyzetben a jelentések generálása lassabb lehet.</span><span class="sxs-lookup"><span data-stu-id="00ae3-133">This situation might cause slower report generation times.</span></span>

##### <a name="misaligned-main-account-categories"></a><span data-ttu-id="00ae3-134">Rosszul igazított főszámla-kategóriák</span><span class="sxs-lookup"><span data-stu-id="00ae3-134">Misaligned main account categories</span></span>

<span data-ttu-id="00ae3-135">Ha olyan kiadást használ, amely korábbi, mint a Microsoft Dynamics 365 for Finance and Operations Financial Feporting 7.2.1-es kiadása, előfordulhat, hogy vissza kell állítania az adatpiacot, ha átnevez számlákat, illetve áthelyez számlákat a számlakategóriák között.</span><span class="sxs-lookup"><span data-stu-id="00ae3-135">If you're using a release that is earlier than Microsoft Dynamics 365 for Finance and Operations Financial reporting release 7.2.1, you might have to reset the data mart if you rename accounts and move accounts between account categories.</span></span> <span data-ttu-id="00ae3-136">Ezek a műveletek a főszámla-kategóriák téves igazítását okozhatják.</span><span class="sxs-lookup"><span data-stu-id="00ae3-136">These actions can cause main account categories to become misaligned.</span></span> <span data-ttu-id="00ae3-137">A **Rosszul igazított főszámla-kategóriák** mező mutatja, hogy tapasztalja-e ezt a problémát.</span><span class="sxs-lookup"><span data-stu-id="00ae3-137">The **Misaligned main account categories** field shows whether you're experiencing that issue.</span></span>

### <a name="reset-the-data-mart-in-finance-and-operations-financial-reporting-release-7260"></a><span data-ttu-id="00ae3-138">Az adatpiac alaphelyzetbe állítása a Finance and Operations Financial Reporting 7.2.6.0 kiadásában</span><span class="sxs-lookup"><span data-stu-id="00ae3-138">Reset the data mart in Finance and Operations Financial reporting release 7.2.6.0</span></span>

<span data-ttu-id="00ae3-139">Az adatpiac alaphelyzetbe állításához a Finance and Operations Financial Reporting 7.2.6.0 és korábbi kiadásában a **Data Mart alaphelyzetbe állítása** párbeszédablakban jelölje be a **Data Mart alaphelyzetbe állítása** jelölőnégyzetet, majd válassza az **OK** gombot.</span><span class="sxs-lookup"><span data-stu-id="00ae3-139">To reset the data mart in Finance and Operations Financial reporting release 7.2.6.0 and earlier, in the **Reset Data Mart** dialog box, select the **Reset data mart** check box, and then select **OK**.</span></span> <span data-ttu-id="00ae3-140">A data mart alaphelyzetbe állítását csakis ütemezett leállás során kell elvégezni.</span><span class="sxs-lookup"><span data-stu-id="00ae3-140">You should reset the data mart only during scheduled downtime.</span></span>

<span data-ttu-id="00ae3-141">[![Data Mart alaphelyzetbe állítása jelölőnégyzet](./media/Reset-72.jpg)](./media/Reset-72.jpg)</span><span class="sxs-lookup"><span data-stu-id="00ae3-141">[![Reset data mart check box](./media/Reset-72.jpg)](./media/Reset-72.jpg)</span></span>

### <a name="reset-the-data-mart-and-select-a-reason-in-microsoft-dynamics-365-for-finance-and-operations-financial-reporting-release-730"></a><span data-ttu-id="00ae3-142">Az adatpiac alaphelyzetbe állítása és okának kiválasztása a Microsoft Dynamics 365 for Finance and Operations Financial reporting 7.3.0 kiadásában</span><span class="sxs-lookup"><span data-stu-id="00ae3-142">Reset the data mart and select a reason in Microsoft Dynamics 365 for Finance and Operations Financial reporting release 7.3.0</span></span>

<span data-ttu-id="00ae3-143">Ha úgy dönt, hogy az adatpiac alaphelyzetbe állítására van szükség, jelölje be a **Data Mart alaphelyzetbe állítása** jelölőnégyzetet, majd válasszon ki egy okot az **Ok** mezőben.</span><span class="sxs-lookup"><span data-stu-id="00ae3-143">If you determine that a data mart reset is required, select the **Reset data mart** check box, and then select a reason in the **Reason** field.</span></span> <span data-ttu-id="00ae3-144">Ehhez a következő lehetőségek állnak rendelkezésre:</span><span class="sxs-lookup"><span data-stu-id="00ae3-144">The following options are available:</span></span>

- <span data-ttu-id="00ae3-145">**Hiányzó vagy hibás adatok** – A statisztikák alapján megállapította, hogy adatok hiányozhatnak.</span><span class="sxs-lookup"><span data-stu-id="00ae3-145">**Missing or incorrect data** – Based on the statistics, you've determined that data might be missing.</span></span> <span data-ttu-id="00ae3-146">A folytatás előtt azt javasoljuk, hogy a Támogatással együtt állapítsa meg, mi volt ennek a legfőbb oka.</span><span class="sxs-lookup"><span data-stu-id="00ae3-146">Before you continue, we recommend that you work with Support to determine the root cause.</span></span>
- <span data-ttu-id="00ae3-147">**Adatbázis visszaállítása** – A Finance and Operations adatbázist visszaállították, de a pénzügyi jelentési adatpiac visszaállítására nem került sor.</span><span class="sxs-lookup"><span data-stu-id="00ae3-147">**Restore database** – The Finance and Operations database was restored, but the database for the Financial reporting data mart wasn't restored.</span></span>
- <span data-ttu-id="00ae3-148">**Egyéb** – más okból kerül sor az adatpiac alaphelyzetbe állítására.</span><span class="sxs-lookup"><span data-stu-id="00ae3-148">**Other** – You're resetting the data mart for another reason.</span></span> <span data-ttu-id="00ae3-149">Ha aggódik amiatt, hogy probléma van, forduljon a Támogatáshoz annak azonosításához.</span><span class="sxs-lookup"><span data-stu-id="00ae3-149">If you're concerned that there is an issue, contact Support to identify it.</span></span>

> [!NOTE]
> <span data-ttu-id="00ae3-150">Ellenőrizze, hogy az összes meglévő feladat integrálása befejeződött-e, mielőtt elvégezné a lépéseket.</span><span class="sxs-lookup"><span data-stu-id="00ae3-150">Verify that all existing tasks have finished integrating before you complete the steps.</span></span> <span data-ttu-id="00ae3-151">Az integráció állapotának megtekintéséhez válassza az **Eszközök** &gt; **Integráció állapota** elemet.</span><span class="sxs-lookup"><span data-stu-id="00ae3-151">You can view the status of the integration by selecting **Tools** &gt; **Integration status**.</span></span>

#### <a name="clear-users-and-companies"></a><span data-ttu-id="00ae3-152">Felhasználók és vállalatok törlése</span><span class="sxs-lookup"><span data-stu-id="00ae3-152">Clear users and companies</span></span>

<span data-ttu-id="00ae3-153">Jelölje be a **Felhasználók és vállalatok törlése** jelölőnégyzetet, ha visszaállította az adatbázist, de ezt követően módosította a felhasználókat vagy a vállalatokat.</span><span class="sxs-lookup"><span data-stu-id="00ae3-153">Select the **Clear users and companies** check box if you restored your database, but you then made changes to users or companies.</span></span> <span data-ttu-id="00ae3-154">Ezt a jelölőnégyzetet ritkán kell kiválasztania.</span><span class="sxs-lookup"><span data-stu-id="00ae3-154">You should rarely have to select this check box.</span></span>

<span data-ttu-id="00ae3-155">Ha készen áll az alaphelyzetbe állítás megkezdéséhez, válassza az **OK** gombot.</span><span class="sxs-lookup"><span data-stu-id="00ae3-155">When you're ready to start the reset process, select **OK**.</span></span> <span data-ttu-id="00ae3-156">A rendszer kéri, hogy erősítse meg, hogy készen áll a folyamat elindítására.</span><span class="sxs-lookup"><span data-stu-id="00ae3-156">You're prompted to confirm that you're ready to start the process.</span></span> <span data-ttu-id="00ae3-157">Ne feledje, hogy a pénzügyi jelentéskészítés nem lesz elérhető a visszaállítás alatt és az azt követő kezdeti adatintegráció során.</span><span class="sxs-lookup"><span data-stu-id="00ae3-157">Note that Financial reporting won't be available during the reset and the initial data integration that occurs afterward.</span></span>

<span data-ttu-id="00ae3-158">Ha szeretné ellenőrizni az integráció állapotát, akkor válassza az **Eszközök** &gt; **Integráció állapota** lehetőséget az integráció utolsó futtatásának és állapotának megjelenítéséhez.</span><span class="sxs-lookup"><span data-stu-id="00ae3-158">If you want to review the status of the integration, select **Tools** &gt; **Integration status** to see the last time that the integration was run and the status.</span></span>

<span data-ttu-id="00ae3-159">[![Az integráció állapotának megjelenítése](./media/Integration.png)](./media/Integration.png)</span><span class="sxs-lookup"><span data-stu-id="00ae3-159">[![View the status of the integration](./media/Integration.png)](./media/Integration.png)</span></span>

## <a name="reset-the-financial-reporting-data-mart-for-finance-and-operations-financial-reporting-release-70100004-and-later"></a><span data-ttu-id="00ae3-160">A pénzügyi jelentési adatpiac alaphelyzetbe állítása a Finance and Operations Financial Reporting 7.0.10000.4-s és későbbi verzióinál</span><span class="sxs-lookup"><span data-stu-id="00ae3-160">Reset the Financial reporting data mart for Finance and Operations Financial reporting release 7.0.10000.4 and later</span></span>

<span data-ttu-id="00ae3-161">Ha bármikor visszaállítja a Dynamics 365 for Operations adatbázist egy biztonsági másolatból, vagy átmásolja az adatbázist egy másik környezetből, az e szakaszban található lépéseket kell követnie annak érdekében, hogy a pénzügyi jelentési adatpiac megfelelően használja a visszaállított Finance and Operations adatbázist.</span><span class="sxs-lookup"><span data-stu-id="00ae3-161">If you ever restore your Finance and Operations database from a backup or copy the database from another environment, you must follow the steps in this section to help guarantee that the Financial reporting data mart correctly uses the restored Finance and Operations database.</span></span>

> [!NOTE]
> <span data-ttu-id="00ae3-162">A folyamat lépései a Microsoft Dynamics AX 7.0.1 verzió (2016. május) kiadásánál támogatottak (7.0.1265.23014 alkalmazásbuild és 7.0.10000.4 Financial reporting build), valamint az újabb verzióknál.</span><span class="sxs-lookup"><span data-stu-id="00ae3-162">The steps in this process are supported for Microsoft Dynamics AX application version 7.0.1 (May 2016) (application build 7.0.1265.23014 and Financial reporting build 7.0.10000.4) and later.</span></span> <span data-ttu-id="00ae3-163">Ha a Finance and Operations egy korábbi verziójával rendelkezik, lépjen kapcsolatba támogatással segítségért.</span><span class="sxs-lookup"><span data-stu-id="00ae3-163">If you have an earlier version of Finance and Operations, contact Support for assistance.</span></span>

### <a name="export-report-definitions"></a><span data-ttu-id="00ae3-164">Jelentésdefiníciók exportálása</span><span class="sxs-lookup"><span data-stu-id="00ae3-164">Export report definitions</span></span>

<span data-ttu-id="00ae3-165">Először kövesse ezeket a lépéseket a jelentéstervek exportálásához a Jelentéskészítőből.</span><span class="sxs-lookup"><span data-stu-id="00ae3-165">First, follow these steps to export the report designs from Report designer.</span></span>

1. <span data-ttu-id="00ae3-166">A Jelentéstervezőben válassza a **Vállalat** &gt; **Építőelem-csoportok** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="00ae3-166">In Report designer, select **Company** &gt; **Building Block Groups**.</span></span>
2. <span data-ttu-id="00ae3-167">Válassza ki az exportálandó építőelem-csoportot, majd válassza az **Export** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="00ae3-167">Select the building block group to export, and then select **Export**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="00ae3-168">A Dynamics 365 for Finance and Operations csak egy építőelem-csoportot támogat, az **Alapértelmezett** csoportot.</span><span class="sxs-lookup"><span data-stu-id="00ae3-168">For Finance and Operations, only one building block group is supported, **Default**.</span></span>

3. <span data-ttu-id="00ae3-169">Válassza ki a jelentésdefiníciókat az exportáláshoz:</span><span class="sxs-lookup"><span data-stu-id="00ae3-169">Select the report definitions to export:</span></span>

    - <span data-ttu-id="00ae3-170">Ha az összes jelentésdefiníciót és társított építőelemet exportálni szeretné, válassza az **Az összes kijelölése** elemet.</span><span class="sxs-lookup"><span data-stu-id="00ae3-170">To export all your report definitions and the associated building blocks, select **Select All**.</span></span>
    - <span data-ttu-id="00ae3-171">Konkrét jelentések, sorok, oszlopok, fák vagy dimenziókészletek exportálásához válassza a megfelelő lapot, majd válassza ki az exportálandó tételeket.</span><span class="sxs-lookup"><span data-stu-id="00ae3-171">To export specific reports, rows, columns, trees, or dimension sets, select the appropriate tab, and then select the items to export.</span></span> <span data-ttu-id="00ae3-172">Ha több tételt szeretne kijelölni egy lapon, nyomja le és tartsa lenyomva a Ctrl billentyűt. Ha jelentéseket jelöl ki az exportálásához, a rendszer a társított sorokat, oszlopokat, fákat és dimenziókészleteket is kijelöli.</span><span class="sxs-lookup"><span data-stu-id="00ae3-172">Press and hold the Ctrl key to select multiple items on a tab. When you select reports to export, the associated rows, columns, trees, and dimension sets are selected.</span></span>

4. <span data-ttu-id="00ae3-173">Válassza az **Exportálás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="00ae3-173">Select **Export**.</span></span>
5. <span data-ttu-id="00ae3-174">Adjon meg egy fájlnevet, és jelöljön ki egy biztonságos helyet, ahol menteni szeretné az exportált jelentésdefiníciókat.</span><span class="sxs-lookup"><span data-stu-id="00ae3-174">Enter a file name, and select a secure location where you want to save the exported report definitions.</span></span>
6. <span data-ttu-id="00ae3-175">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="00ae3-175">Select **Save**.</span></span>

<span data-ttu-id="00ae3-176">A fájlt átmásolhatja vagy feltöltheti egy biztonságos helyre.</span><span class="sxs-lookup"><span data-stu-id="00ae3-176">You can copy or upload the file to a secure location.</span></span> <span data-ttu-id="00ae3-177">Ily módon a fájl később importálható egy másik környezetbe.</span><span class="sxs-lookup"><span data-stu-id="00ae3-177">In this way, the file can be imported into a different environment later.</span></span> <span data-ttu-id="00ae3-178">A Microsoft Azure tárolófiók használatával kapcsolatos információkért lásd: [Adatátvitel az AzCopy parancssori segédprogrammal](/azure/storage/storage-use-azcopy).</span><span class="sxs-lookup"><span data-stu-id="00ae3-178">For information about how to use a Microsoft Azure storage account, see [Transfer data with the AzCopy Command-Line Utility](/azure/storage/storage-use-azcopy).</span></span>

> [!NOTE]
> <span data-ttu-id="00ae3-179">A Dynamics 365 for Finance and Operations megállapodás részeként a Microsoft nem biztosít tárolófiókot.</span><span class="sxs-lookup"><span data-stu-id="00ae3-179">Microsoft doesn't provide a storage account as part of your Finance and Operations agreement.</span></span> <span data-ttu-id="00ae3-180">Be kell szereznie egy tárolófiókot, vagy egy külön Azure-előfizetésből származó tárolófiókot kell használnia.</span><span class="sxs-lookup"><span data-stu-id="00ae3-180">You must either purchase a storage account or use a storage account from a separate Azure subscription.</span></span>

> [!WARNING]
> <span data-ttu-id="00ae3-181">Legyen tisztában a D meghajtó viselkedésével az Azure virtuális gépeken (VM-eken).</span><span class="sxs-lookup"><span data-stu-id="00ae3-181">Be aware of the behavior of drive D on Azure virtual machines (VMs).</span></span> <span data-ttu-id="00ae3-182">Az exportált épületblokk-csoportokat ne tárolja véglegesen a D meghajtón. További információ az ideiglenes meghajtókról: [A Windows Azure virtuális gépek ideiglenes meghajtóinak ismertetése](https://blogs.msdn.microsoft.com/mast/2013/12/06/understanding-the-temporary-drive-on-windows-azure-virtual-machines/).</span><span class="sxs-lookup"><span data-stu-id="00ae3-182">Don't permanently store your exported building block groups on drive D. For more information about temporary drives, see [Understanding the temporary drive on Windows Azure Virtual Machines](https://blogs.msdn.microsoft.com/mast/2013/12/06/understanding-the-temporary-drive-on-windows-azure-virtual-machines/).</span></span>

### <a name="stop-services"></a><span data-ttu-id="00ae3-183">Szolgáltatások leállítása</span><span class="sxs-lookup"><span data-stu-id="00ae3-183">Stop services</span></span>

<span data-ttu-id="00ae3-184">A következő Microsoft Windows szolgáltatások nyitott kapcsolatot létesítenek a Finance and Operations adatbázissal.</span><span class="sxs-lookup"><span data-stu-id="00ae3-184">The following Microsoft Windows services will have open connections to the Finance and Operations database.</span></span> <span data-ttu-id="00ae3-185">Ezért a Távoli asztal segítségével csatlakoznia kell az összes számítógéphez a környezetében, és le kell állítania le ezeket a szolgáltatásokat a services.msc segítségével:</span><span class="sxs-lookup"><span data-stu-id="00ae3-185">Therefore, you must use Microsoft Remote Desktop to connect to all the computers in the environment and then use services.msc to stop these services.</span></span>

- <span data-ttu-id="00ae3-186">Webes közzétételi szolgáltatás (az összes Application Object Servers [AOS] számítógépen)</span><span class="sxs-lookup"><span data-stu-id="00ae3-186">World wide web publishing service (on all Application Object Servers [AOS] computers)</span></span>
- <span data-ttu-id="00ae3-187">Microsoft Dynamics 365 for Finance and Operations Batch Management Service (csak a nem személyes AOS-számítógépeken)</span><span class="sxs-lookup"><span data-stu-id="00ae3-187">Microsoft Dynamics 365 for Finance and Operations Batch Management Service (on non-private AOS computers only)</span></span>
- <span data-ttu-id="00ae3-188">Management Reporter 2012 Process Service (csak a Business intelligence [BI] számítógépeken)</span><span class="sxs-lookup"><span data-stu-id="00ae3-188">Management Reporter 2012 Process Service (on Business intelligence [BI] computers only)</span></span>

### <a name="reset"></a><span data-ttu-id="00ae3-189">Alaphelyzet</span><span class="sxs-lookup"><span data-stu-id="00ae3-189">Reset</span></span>

#### <a name="download-the-latest-minorversiondataupgradezip-package"></a><span data-ttu-id="00ae3-190">Töltse le a legújabb MinorVersionDataUpgrade.zip csomagot</span><span class="sxs-lookup"><span data-stu-id="00ae3-190">Download the latest MinorVersionDataUpgrade.zip package</span></span>

<span data-ttu-id="00ae3-191">Töltse le a legújabb MinorVersionDataUpgrade.zip csomagot.</span><span class="sxs-lookup"><span data-stu-id="00ae3-191">Download the latest MinorVersionDataUpgrade.zip package.</span></span> <span data-ttu-id="00ae3-192">Az adatfrissítési csomag helyes verziójának megkeresésével és letöltésével kapcsolatban lásd: [A legfrissebb adatfrissítési telepíthető csomag letöltése](..\migration-upgrade\upgrade-data-to-latest-update.md#download-the-latest-data-upgrade-deployable-packages).</span><span class="sxs-lookup"><span data-stu-id="00ae3-192">For instructions about how to find and download the correct version of the data upgrade package, see the[Download the latest data upgrade deployable package](..\migration-upgrade\upgrade-data-to-latest-update.md#download-the-latest-data-upgrade-deployable-packages).</span></span> <span data-ttu-id="00ae3-193">A MinorVersionDataUpgrade.zip csomag letöltéséhez nincs szükség frissítésre.</span><span class="sxs-lookup"><span data-stu-id="00ae3-193">An upgrade isn't required in order to download the MinorVersionDataUpgrade.zip package.</span></span> <span data-ttu-id="00ae3-194">Ezért csak kövesse az adott témakör „A legfrissebb adatok frissítési telepíthető csomag letöltése” szakaszában leírt lépéseket.</span><span class="sxs-lookup"><span data-stu-id="00ae3-194">Therefore, you just have follow the steps in the "Download the latest data upgrade deployable package" section of that topic.</span></span> <span data-ttu-id="00ae3-195">A témakörben szereplő minden egyéb lépést kihagyhat.</span><span class="sxs-lookup"><span data-stu-id="00ae3-195">You can skip all the other steps in the topic.</span></span>

#### <a name="run-scripts-against-the-finance-and-operations-database"></a><span data-ttu-id="00ae3-196">Parancsfájl-műveletek futtatása a Dynamics 365 for Finance and Operations adatbázison</span><span class="sxs-lookup"><span data-stu-id="00ae3-196">Run scripts against the Finance and Operations database</span></span>

<span data-ttu-id="00ae3-197">Futtassa a következő parancsfájlokat a Dynamics 365 for Finance and Operations adatbázison (nem a Financial reporting adatbázison):</span><span class="sxs-lookup"><span data-stu-id="00ae3-197">Run the following scripts against the Finance and Operations database (not against the Financial reporting database):</span></span>

- <span data-ttu-id="00ae3-198">DataUpgrade.zip\\AosService\\Scripts\\ConfigureAxReportingIntegration.sql</span><span class="sxs-lookup"><span data-stu-id="00ae3-198">DataUpgrade.zip\\AosService\\Scripts\\ConfigureAxReportingIntegration.sql</span></span>
- <span data-ttu-id="00ae3-199">DataUpgrade.zip\\AosService\\Scripts\\GrantAzViewChangeTracking.sql</span><span class="sxs-lookup"><span data-stu-id="00ae3-199">DataUpgrade.zip\\AosService\\Scripts\\GrantAzViewChangeTracking.sql</span></span>

<span data-ttu-id="00ae3-200">Ezeket a parancsfájlok segítenek garantálni, hogy helyesek legyenek a felhasználók, a szerepkörök és a változáskövetési beállítások.</span><span class="sxs-lookup"><span data-stu-id="00ae3-200">These scripts help guarantee that the users, roles, and change tracking settings are correct.</span></span>

#### <a name="run-a-windows-powershell-command-to-reset-the-database"></a><span data-ttu-id="00ae3-201">Futtasson egy Windows PowerShell parancsot az adatbázis visszaállításához</span><span class="sxs-lookup"><span data-stu-id="00ae3-201">Run a Windows PowerShell command to reset the database</span></span>

<span data-ttu-id="00ae3-202">Az AOS-számítógépen indítsa el a Microsoft Windows PowerShell szolgáltatást rendszergazdaként, majd futtassa a következő parancsokat a Dynamics 365 for Finance and Operations és a Financial reporting közti integráció alaphelyzetbe állításához.</span><span class="sxs-lookup"><span data-stu-id="00ae3-202">On the AOS computer, start Microsoft Windows PowerShell as an administrator, and run the following commands to reset the integration between Finance and Operations and Financial reporting.</span></span>

```
F:
cd F:\MRApplicationService\MRInstallDirectory
Import-Module .\Server\MRDeploy\MRDeploy.psd1
Reset-DatamartIntegration -Reason OTHER -ReasonDetail "<reason for resetting>"
```

<span data-ttu-id="00ae3-203">Itt a **Reset-DatamartIntegration** utasítás paramétereinek magyarázata:</span><span class="sxs-lookup"><span data-stu-id="00ae3-203">Here is an explanation of the parameters in the **Reset-DatamartIntegration** command:</span></span>

- <span data-ttu-id="00ae3-204">Az **-Reason** érvényes értékei: **SERVICING**, **BADDATA** és **OTHER**.</span><span class="sxs-lookup"><span data-stu-id="00ae3-204">The valid values for **-Reason** are **SERVICING**, **BADDATA**, and **OTHER**.</span></span>
- <span data-ttu-id="00ae3-205">A **ReasonDetail** paraméter szabad szöveg.</span><span class="sxs-lookup"><span data-stu-id="00ae3-205">The **-ReasonDetail** parameter is free text.</span></span>
- <span data-ttu-id="00ae3-206">A távmérő/környezet felügyelete végzi az ok és az ok részletei rögzítését.</span><span class="sxs-lookup"><span data-stu-id="00ae3-206">The reason and reason detail will be recorded in telemetry/environment monitoring.</span></span>

> [!NOTE]
> <span data-ttu-id="00ae3-207">Miután futtatta a parancsokat, az **Y** megadásával meg kell erősítenie, hogy vissza akarja állítani az adatbázist.</span><span class="sxs-lookup"><span data-stu-id="00ae3-207">After you run the commands, you will be asked to enter **Y** to confirm that you want to reset the database.</span></span>

#### <a name="restart-services"></a><span data-ttu-id="00ae3-208">Szolgáltatások újraindítása</span><span class="sxs-lookup"><span data-stu-id="00ae3-208">Restart services</span></span>

<span data-ttu-id="00ae3-209">A korábban leállított szolgáltatások újraindításához használja a Services.msc parancsot:</span><span class="sxs-lookup"><span data-stu-id="00ae3-209">Use services.msc to restart the services that you stopped earlier:</span></span>

- <span data-ttu-id="00ae3-210">Webes közzétételi szolgáltatás (az összes AOS-számítógépen)</span><span class="sxs-lookup"><span data-stu-id="00ae3-210">World wide web publishing service (on all AOS computers)</span></span>
- <span data-ttu-id="00ae3-211">Microsoft Dynamics 365 for Finance and Operations Batch Management Service (csak a nem személyes AOS-számítógépeken)</span><span class="sxs-lookup"><span data-stu-id="00ae3-211">Microsoft Dynamics 365 for Finance and Operations Batch Management Service (on non-private AOS computers only)</span></span>
- <span data-ttu-id="00ae3-212">Management Reporter 2012 Process Service (csak a BI-számítógépeken)</span><span class="sxs-lookup"><span data-stu-id="00ae3-212">Management Reporter 2012 Process Service (on BI computers only)</span></span>

#### <a name="import-report-definitions"></a><span data-ttu-id="00ae3-213">Jelentésdefiníciók importálása</span><span class="sxs-lookup"><span data-stu-id="00ae3-213">Import report definitions</span></span>

<span data-ttu-id="00ae3-214">Importálja a jelentésterveket a Jelentéstervezőből az exportálás során létrehozott fájl használatával.</span><span class="sxs-lookup"><span data-stu-id="00ae3-214">Import your report designs from Report designer by using the file that was created during the export.</span></span>

1. <span data-ttu-id="00ae3-215">A Jelentéstervezőben válassza a **Vállalat** &gt; **Építőelem-csoportok** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="00ae3-215">In Report designer, select **Company** &gt; **Building Block Groups**.</span></span>
2. <span data-ttu-id="00ae3-216">Válassza ki az exportálandó építőelem-csoportot, majd válassza az **Export** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="00ae3-216">Select the building block group to export, and then select **Export**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="00ae3-217">A Dynamics 365 for Finance and Operations csak egy építőelem-csoportot támogat, az **Alapértelmezett** csoportot.</span><span class="sxs-lookup"><span data-stu-id="00ae3-217">For Finance and Operations, only one building block group is supported, **Default**.</span></span>

3. <span data-ttu-id="00ae3-218">Válassza ki az **Alapértelmezett** építőelemet, majd válassza az **Importálás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="00ae3-218">Select the **Default** building block, and then select **Import**.</span></span>
4. <span data-ttu-id="00ae3-219">Válassza ki az exportált jelentésdefiníciókat tartalmazó fájlt, és válassza a **Megnyitás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="00ae3-219">Select the file that contains the exported report definitions, and then select **Open**.</span></span>
5. <span data-ttu-id="00ae3-220">Az **Importálás** párbeszédpanelen válassza ki az importálni kívánt jelentésdefiníciókat:</span><span class="sxs-lookup"><span data-stu-id="00ae3-220">In the **Import** dialog box, select the report definitions to import:</span></span>

    - <span data-ttu-id="00ae3-221">Ha az összes jelentésdefiníciót és társított építőelemet importálni szeretné, válassza **Az összes kijelölése** elemet.</span><span class="sxs-lookup"><span data-stu-id="00ae3-221">To import all the report definitions and the associated building blocks, select **Select All**.</span></span>
    - <span data-ttu-id="00ae3-222">Konkrét jelentések, sorok, oszlopok, fák vagy dimenziókészletek importálásához válassza ki az importálni kívánt elemeket.</span><span class="sxs-lookup"><span data-stu-id="00ae3-222">To import specific reports, rows, columns, trees, or dimension sets, select the reports, rows, columns, trees, or dimension sets to import.</span></span>

6. <span data-ttu-id="00ae3-223">Válassza az **Importálás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="00ae3-223">Select **Import**.</span></span>

## <a name="reset-the-financial-reporting-data-mart-for-finance-and-operations-on-premises"></a><span data-ttu-id="00ae3-224">Az adatpiac alaphelyzetbe állítása a Finance and Operations (on-premises) rendszerben</span><span class="sxs-lookup"><span data-stu-id="00ae3-224">Reset the Financial reporting data mart for Finance and Operations (on-premises)</span></span>

1. <span data-ttu-id="00ae3-225">Az összes felhasználót utasítsa arra, hogy lépjen ki a Jelentéstervezőből és a Finance and Operations pénzügyi jelentési területéről.</span><span class="sxs-lookup"><span data-stu-id="00ae3-225">Instruct all users to exit Report designer and the Financial reporting area of Finance and Operations.</span></span>
2. <span data-ttu-id="00ae3-226">Futtassa a következő parancsfájlt a Financial reporting adatbázison (MRDB).</span><span class="sxs-lookup"><span data-stu-id="00ae3-226">Run the following script against the Financial reporting database (MRDB).</span></span>

    ```
    DECLARE @triggerIds table(id uniqueidentifier, taskTypeId uniqueidentifier)
    INSERT INTO @triggerIds SELECT tr.[Id], tt.[Id]
    FROM [Scheduling].[Task] t with(nolock)
    JOIN [Scheduling].[Trigger] tr ON t.[TriggerId] = tr.[Id]
    JOIN [Scheduling].[TaskState] ts ON ts.[TaskId] = t.[Id]
    LEFT JOIN [Scheduling].[TaskCategory] tc ON tc.[Id] = t.[CategoryId]
    JOIN [Scheduling].[TaskType] tt ON t.[TypeId] = tt.[Id]
    WHERE tt.[Id] IN ('D81C1197-D486-4FB7-AF8C-078C110893A0', '55D3F71A-2618-4EAE-9AA6-D48767B974D8') -- 'Maintenance Task', 'Map Task'
    PRINT 'Disable integration tasks'
    UPDATE [Scheduling].[Trigger] SET IsEnabled = 0 WHERE [Id] in (SELECT id FROM @triggerIds)
    ```

3. <span data-ttu-id="00ae3-227">A Finance and Operations adatbázis (AXDB) FINANCIALREPORTS táblájának összes rekordját csonkolja vagy törölje.</span><span class="sxs-lookup"><span data-stu-id="00ae3-227">Truncate or delete all records from the FINANCIALREPORTS table in the Finance and Operations database (AXDB).</span></span>
4. <span data-ttu-id="00ae3-228">A Finance and Operations adatbázis esetlegesen létező FINANCIALREPORTVERSION táblájának összes rekordját csonkolja vagy törölje.</span><span class="sxs-lookup"><span data-stu-id="00ae3-228">Truncate or delete all records from the FINANCIALREPORTVERSION table, if this table exists in the Finance and Operations database.</span></span> <span data-ttu-id="00ae3-229">Ha a tábla nem létezik a Finance and Operations adatbázisban, hagyja ki ezt a lépést.</span><span class="sxs-lookup"><span data-stu-id="00ae3-229">If the table doesn't exist in the Finance and Operations database, skip this step.</span></span>
5. <span data-ttu-id="00ae3-230">Futtassa a **ResetDatamart.sql** parancsfájlt a Financial reporting adatbázison.</span><span class="sxs-lookup"><span data-stu-id="00ae3-230">Run the **ResetDatamart.sql** script against the Financial reporting database.</span></span> <span data-ttu-id="00ae3-231">Ez a parancsfájl letiltja az adatpiac integrációját, törli az adatpiac összes adatát, majd újraindítja az adatpiac integrációját.</span><span class="sxs-lookup"><span data-stu-id="00ae3-231">This script disables the data mart integration, deletes all the data mart data, and then reenables the data mart integration.</span></span>

    ```
    DECLARE @triggerIds table(id uniqueidentifier, taskTypeId uniqueidentifier)
    INSERT INTO @triggerIds SELECT tr.[Id], tt.[Id]
    FROM [Scheduling].[Task] t with(nolock)
    JOIN [Scheduling].[Trigger] tr ON t.[TriggerId] = tr.[Id]
    JOIN [Scheduling].[TaskState] ts ON ts.[TaskId] = t.[Id]
    LEFT JOIN [Scheduling].[TaskCategory] tc ON tc.[Id] = t.[CategoryId]
    JOIN [Scheduling].[TaskType] tt ON t.[TypeId] = tt.[Id]
    WHERE tt.[Id] IN ('D81C1197-D486-4FB7-AF8C-078C110893A0', '55D3F71A-2618-4EAE-9AA6-D48767B974D8') -- 'Maintenance Task', 'Map Task'
    PRINT 'Disable integration tasks'
    UPDATE [Scheduling].[Trigger] SET IsEnabled = 0 WHERE [Id] in (SELECT id FROM @triggerIds)
    ------------------------------
    PRINT 'Drop archive tables'
    ------------------------------
    DECLARE @tableId nvarchar(max)
    DECLARE dropCursor CURSOR LOCAL FAST_FORWARD FOR
    SELECT Id FROM [Datamart].Archive
    OPEN dropCursor
    FETCH NEXT FROM dropCursor INTO @tableId
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF EXISTS (SELECT 1 FROM INFORMATION_SCHEMA.TABLES t WHERE t.TABLE_NAME = 'FactStaging' + @tableId and t.TABLE_SCHEMA = 'Datamart')
        EXEC('DROP TABLE [Datamart].FactStaging' + @tableId)
        IF EXISTS (SELECT 1 FROM INFORMATION_SCHEMA.TABLES t WHERE t.TABLE_NAME = 'DimensionCombinationStaging' + @tableId and t.TABLE_SCHEMA = 'Datamart')
        EXEC('DROP TABLE [Datamart].DimensionCombinationStaging' + @tableId)
        FETCH NEXT FROM dropCursor INTO @tableId
    END
    CLOSE dropCursor
    DEALLOCATE dropCursor
    IF EXISTS (SELECT 1 FROM INFORMATION_SCHEMA.TABLES t WHERE t.TABLE_NAME = 'DimensionCombinationProcessing' and t.TABLE_SCHEMA = 'Datamart')
        EXEC('DROP TABLE [Datamart].DimensionCombinationProcessing')
    ------------------------------
    PRINT 'Begin Truncating tables'
    ------------------------------
    DECLARE @tablename nvarchar(200)
    DECLARE @schemaname nvarchar(200)
    DECLARE clear_tables CURSOR
        FOR SELECT TABLE_NAME, TABLE_SCHEMA FROM INFORMATION_SCHEMA.TABLES WHERE TABLE_SCHEMA = 'Datamart' AND TABLE_TYPE='BASE TABLE'
    PRINT 'remove check constraints'
    OPEN clear_tables
    FETCH NEXT FROM clear_tables INTO @tablename, @schemaname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @tablename <> 'VersionHistory'
        BEGIN
        EXEC('ALTER TABLE [' + @schemaname + '].[' + @tablename + '] NOCHECK CONSTRAINT ALL')
        END
        FETCH NEXT FROM clear_tables INTO @tablename, @schemaname
    END
    CLOSE clear_tables
    ------------------------------
    PRINT 'delete data from tables and rebuild indexes'
    ------------------------------
    OPEN clear_tables
    FETCH NEXT FROM clear_tables INTO @tablename, @schemaname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @tablename <> 'VersionHistory'
        BEGIN
            IF(EXISTS (select TOP 1 1 from sys.foreign_keys where referenced_object_id = OBJECT_ID(@schemaname + '.' + @tablename)) OR
            EXISTS(SELECT TOP 1 1 FROM sys.sql_expression_dependencies sed
            INNER JOIN sys.objects o ON sed.referencing_id = o.[object_id]
            WHERE o.[type] = 'V' 
            AND referenced_schema_name = @schemaname
            AND referenced_entity_name = @tablename))
            BEGIN
            PRINT 'deleting from ' + @tablename
            EXEC('DELETE FROM [' + @schemaname + '].[' + @tablename + ']')
            END
            ELSE
            BEGIN
            PRINT 'truncating from ' + @tablename
            EXEC('TRUNCATE TABLE [' + @schemaname + '].[' + @tablename + ']')
            END
        END
        EXEC('ALTER INDEX ALL ON [' + @schemaname + '].[' + @tablename + '] REBUILD')
        FETCH NEXT FROM clear_tables INTO @tablename, @schemaname
    END
    CLOSE clear_tables
    ------------------------------
    PRINT 'reenable check constraints'
    ------------------------------
    OPEN clear_tables
    FETCH NEXT FROM clear_tables INTO @tablename, @schemaname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @tablename <> 'VersionHistory'
        BEGIN
        EXEC('ALTER TABLE [' + @schemaname + '].[' + @tablename +'] WITH CHECK CHECK CONSTRAINT ALL')
        END
        FETCH NEXT FROM clear_tables INTO @tablename, @schemaname
    END
    CLOSE clear_tables
    DEALLOCATE clear_tables
    ------------------------------
    PRINT 'Complete Truncating tables'
    ------------------------------
    ------------------------------
    PRINT 'Remove indexes from DimensionCombination'
    ------------------------------
    DECLARE @indexname nvarchar(200)
    DECLARE drop_indexes CURSOR
    FOR SELECT Name FROM sys.indexes WHERE object_id = OBJECT_ID('[Datamart].[DimensionCombination]') AND is_primary_key = 0
    OPEN drop_indexes
    FETCH NEXT FROM drop_indexes INTO @indexname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        EXEC('DROP INDEX [' + @indexname + '] on [Datamart].[DimensionCombination]')
        FETCH NEXT FROM drop_indexes INTO @indexname
    END
    CLOSE drop_indexes
    DEALLOCATE drop_indexes
    ------------------------------
    PRINT 'Drop Columns on DimensionCombination'
    ------------------------------
    DECLARE @objectname nvarchar(200)
    DECLARE drop_objects CURSOR
    FOR SELECT Name FROM sys.columns WHERE object_id = OBJECT_ID('[Datamart].[DimensionCombination]')
    OPEN drop_objects
    FETCH NEXT FROM drop_objects INTO @objectname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @objectname NOT IN ('Id', 'Description', 'SourceKey', 'OrganizationId', 'InactiveDimensions')
        BEGIN
        EXEC('ALTER TABLE [Datamart].[DimensionCombination] DROP COLUMN ' + @objectname)
        END
        FETCH NEXT FROM drop_objects INTO @objectname
    END
    CLOSE drop_objects
    DEALLOCATE drop_objects
    ------------------------------
    PRINT 'Drop Columns on DimensionCombinationResolving'
    ------------------------------
    DECLARE drop_objects CURSOR
    FOR SELECT Name FROM sys.columns WHERE object_id = OBJECT_ID('[Datamart].[DimensionCombinationResolving]')
    OPEN drop_objects
    FETCH NEXT FROM drop_objects INTO @objectname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @objectname NOT IN ('Id', 'Description', 'SourceKey', 'OrganizationId')
        BEGIN
        EXEC('ALTER TABLE [Datamart].[DimensionCombinationResolving] DROP COLUMN ' + @objectname)
        END
        FETCH NEXT FROM drop_objects INTO @objectname
    END
    CLOSE drop_objects
    DEALLOCATE drop_objects
    ------------------------------
    PRINT 'Drop Columns on DimensionCombinationStaging'
    ------------------------------
    DECLARE drop_objects CURSOR
    FOR SELECT Name FROM sys.columns WHERE object_id = OBJECT_ID('[Datamart].[DimensionCombinationStaging]')
    OPEN drop_objects
    FETCH NEXT FROM drop_objects INTO @objectname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @objectname NOT IN ('Id', 'OrganizationId', 'Description', 'SourceKey', 'OrganizationKey', 'FreshnessDate')
        BEGIN
        EXEC('ALTER TABLE [Datamart].[DimensionCombinationStaging] DROP COLUMN ' + @objectname)
        END
        FETCH NEXT FROM drop_objects INTO @objectname
    END
    CLOSE drop_objects
    DEALLOCATE drop_objects
    ------------------------------
    PRINT 'Drop Columns on DimensionCombinationUnreferenced'
    ------------------------------
    DECLARE drop_objects CURSOR
    FOR SELECT Name FROM sys.columns WHERE object_id = OBJECT_ID('[Datamart].[DimensionCombinationUnreferenced]')
    OPEN drop_objects
    FETCH NEXT FROM drop_objects INTO @objectname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @objectname NOT IN ('Id', 'Description', 'SourceKey', 'OrganizationId')
        BEGIN
        EXEC('ALTER TABLE [Datamart].[DimensionCombinationUnreferenced] DROP COLUMN ' + @objectname)
        END
        FETCH NEXT FROM drop_objects INTO @objectname
    END
    CLOSE drop_objects
    DEALLOCATE drop_objects
    ------------------------------
    PRINT 'Drop Columns on DimensionValueAttributeValue'
    ------------------------------
    DECLARE drop_objects CURSOR
    FOR SELECT Name FROM sys.columns WHERE object_id = OBJECT_ID('[Datamart].[DimensionValueAttributeValue]')
    OPEN drop_objects
    FETCH NEXT FROM drop_objects INTO @objectname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @objectname NOT IN ('DimensionValueId')
        BEGIN
        EXEC('ALTER TABLE [Datamart].[DimensionValueAttributeValue] DROP COLUMN ' + @objectname)
        END
        FETCH NEXT FROM drop_objects INTO @objectname
    END
    CLOSE drop_objects
    DEALLOCATE drop_objects
    ------------------------------
    PRINT 'Drop Columns on FactAttributeValue'
    ------------------------------
    DECLARE drop_objects CURSOR
    FOR SELECT Name FROM sys.columns WHERE object_id = OBJECT_ID('[Datamart].[FactAttributeValue]')
    OPEN drop_objects
    FETCH NEXT FROM drop_objects INTO @objectname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @objectname NOT IN ('FactId')
        BEGIN
        EXEC('ALTER TABLE [Datamart].[FactAttributeValue] DROP COLUMN ' + @objectname)
        END
        FETCH NEXT FROM drop_objects INTO @objectname
    END
    CLOSE drop_objects
    DEALLOCATE drop_objects
    ------------------------------
    PRINT 'Remove constraints from TranslatedPeriodBalance'
    ------------------------------
    DECLARE @name nvarchar(200)
    DECLARE drop_constraints CURSOR
    FOR SELECT Name FROM sys.default_constraints WHERE parent_object_id = OBJECT_ID('[Datamart].[TranslatedPeriodBalance]')
    OPEN drop_constraints
    FETCH NEXT FROM drop_constraints INTO @name
    WHILE @@FETCH_STATUS = 0
    BEGIN
        EXEC('ALTER TABLE [Datamart].[TranslatedPeriodBalance] DROP CONSTRAINT [' + @name + ']')
        FETCH NEXT FROM drop_constraints INTO @name
    END
    CLOSE drop_constraints
    DEALLOCATE drop_constraints
    ------------------------------
    PRINT 'Drop Columns on TranslatedPeriodBalance'
    ------------------------------
    DECLARE drop_objects CURSOR
    FOR SELECT Name FROM sys.columns WHERE object_id = OBJECT_ID('[Datamart].[TranslatedPeriodBalance]')
    OPEN drop_objects
    FETCH NEXT FROM drop_objects INTO @objectname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @objectname NOT IN ('PeriodId', 'DimensionsId', 'ScenarioId', 'FactType', 'PostingLayerId')
        BEGIN
        EXEC('ALTER TABLE [Datamart].[TranslatedPeriodBalance] DROP COLUMN ' + @objectname)
        END
        FETCH NEXT FROM drop_objects INTO @objectname
    END
    CLOSE drop_objects
    DEALLOCATE drop_objects
    ------------------------------
    PRINT 'Remove constraints from TranslatedPeriodBalanceChanges'
    ------------------------------
    DECLARE drop_constraints CURSOR
    FOR SELECT Name FROM sys.default_constraints WHERE parent_object_id = OBJECT_ID('[Datamart].[TranslatedPeriodBalanceChanges]')
    OPEN drop_constraints
    FETCH NEXT FROM drop_constraints INTO @name
    WHILE @@FETCH_STATUS = 0
    BEGIN
        EXEC('ALTER TABLE [Datamart].[TranslatedPeriodBalanceChanges] DROP CONSTRAINT [' + @name + ']')
        FETCH NEXT FROM drop_constraints INTO @name
    END
    CLOSE drop_constraints
    DEALLOCATE drop_constraints
    ------------------------------
    PRINT 'Drop Columns on TranslatedPeriodBalanceChanges'
    ------------------------------
    DECLARE drop_objects CURSOR
    FOR SELECT Name FROM sys.columns WHERE object_id = OBJECT_ID('[Datamart].[TranslatedPeriodBalanceChanges]')
    OPEN drop_objects
    FETCH NEXT FROM drop_objects INTO @objectname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @objectname NOT IN ('PeriodId', 'DimensionsId', 'ScenarioId', 'FactType', 'PostingLayerId')
        BEGIN
        EXEC('ALTER TABLE [Datamart].[TranslatedPeriodBalanceChanges] DROP COLUMN ' + @objectname)
        END
        FETCH NEXT FROM drop_objects INTO @objectname
    END
    CLOSE drop_objects
    DEALLOCATE drop_objects
    -- Rebuild dropped indexes that are dynamic
    EXEC [Datamart].ConfigureIndexesAndConstraints
    ------------------------------------------
    ------------------------------------------
    PRINT 'Reset the map tokens'
    UPDATE [Connector].[Map] SET InitalLoad = 0, ReaderToken=NULL, LastQuerySuccess='1900-01-01' WHERE MapId IN (SELECT t.[Id]
    FROM [Scheduling].[Task] t with(nolock)
    JOIN [Scheduling].[Trigger] tr ON t.[TriggerId] = tr.[Id]
    JOIN [Scheduling].[TaskState] ts ON ts.[TaskId] = t.[Id]
    LEFT JOIN [Scheduling].[TaskCategory] tc ON tc.[Id] = t.[CategoryId]
    JOIN [Scheduling].[TaskType] tt ON t.[TypeId] = tt.[Id]
    WHERE tt.[Id] = '55D3F71A-2618-4EAE-9AA6-D48767B974D8')
    PRINT 'Reset the tasks'
    UPDATE [Scheduling].[TaskState] SET StateType = 0, Progress = 0.0, LastRunTime = NULL, NextRunTime = NULL WHERE TaskId IN (SELECT ts.[TaskId]
    FROM [Scheduling].[Task] t with(nolock)
    JOIN [Scheduling].[Trigger] tr ON t.[TriggerId] = tr.[Id]
    JOIN [Scheduling].[TaskState] ts ON ts.[TaskId] = t.[Id]
    LEFT JOIN [Scheduling].[TaskCategory] tc ON tc.[Id] = t.[CategoryId]
    JOIN [Scheduling].[TaskType] tt ON t.[TypeId] = tt.[Id]
    WHERE tt.[Id] IN ('D81C1197-D486-4FB7-AF8C-078C110893A0', '55D3F71A-2618-4EAE-9AA6-D48767B974D8'))
    PRINT 'Enable integration tasks, RunImmediately'
    UPDATE [Scheduling].[Trigger] SET IsEnabled = 1, RunImmediately = 1, StartBoundary = '1900-01-01' 
    WHERE Id in (SELECT [id] from @triggerIds WHERE taskTypeId = '55D3F71A-2618-4EAE-9AA6-D48767B974D8')
    PRINT 'Enable the Maintenance Task'
    UPDATE [Scheduling].[Trigger] SET IsEnabled = 1, RunImmediately = 0, StartBoundary = GETDATE() WHERE Id in
    (SELECT [id] from @triggerIds WHERE taskTypeId = 'D81C1197-D486-4FB7-AF8C-078C110893A0')
    ------------------------------------------
    ------------------------------------------
    ```

6. <span data-ttu-id="00ae3-232">A alaphelyzetbe állítás után manuálisan ellenőrizheti az adatok újbóli betöltését a Financial reporting adatbázison futtatott következő lekérdezéssel.</span><span class="sxs-lookup"><span data-stu-id="00ae3-232">After the reset, you can manually verify the data reload by running the following query against the Financial reporting database.</span></span>

    ```
    select ReaderObjectName, WriterObjectName, LastRunTime, StateType from Connector.MapsWithDetail with (nolock)
    ```

    <span data-ttu-id="00ae3-233">Győződjön meg arról, hogy rendelkezik-e az összes sor egy **LastRunTime** értékkel, és hogy a **StateType** értéke **5**.</span><span class="sxs-lookup"><span data-stu-id="00ae3-233">Confirm that all rows have a **LastRunTime** value, and that **StateType** is set to **5**.</span></span> <span data-ttu-id="00ae3-234">A **StateType** **5** értéke jelzi, hogy az adatok újratöltése sikeres volt.</span><span class="sxs-lookup"><span data-stu-id="00ae3-234">A **StateType** value of **5** indicates that the data was successfully reloaded.</span></span> <span data-ttu-id="00ae3-235">A **7** érték a hibás állapotot jelzi.</span><span class="sxs-lookup"><span data-stu-id="00ae3-235">A value of **7** indicates a faulted state.</span></span> <span data-ttu-id="00ae3-236">Előfordul, a szervezeti hierarchia leképezése ezt az állapotot tartalmazza az első futtatáskor.</span><span class="sxs-lookup"><span data-stu-id="00ae3-236">Sometimes, the Organization Hierarchy map has this state the first time that it runs.</span></span> <span data-ttu-id="00ae3-237">Azonban a hibaállapot ilyenkor elvileg automatikusan megoldódik.</span><span class="sxs-lookup"><span data-stu-id="00ae3-237">However, the faulted state but should be automatically resolved.</span></span>

