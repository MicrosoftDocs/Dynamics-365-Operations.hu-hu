---
title: Az ER megoldások teljesítményének javítása a paraméterek SZÁMÍTOTT MEZŐ-adatforrások hozzáadásával
description: Ez a témakör azt mutatja be, hogyan lehet elősegíteni a Electroinic jelentéskészítés (ER) megoldások hatékonyságát a paraméterek SZÁMÍTOTT MEZŐ-adatforrások hozzáadásával.
author: NickSelin
manager: AnnBe
ms.date: 09/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: a87098e82284a4951f3a4de050f6ba3f587fd20a
ms.sourcegitcommit: 5472005274f2f94fba82dda90de128f39d8b8390
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/02/2020
ms.locfileid: "3760082"
---
# <a name="improve-the-performance-of-er-solutions-by-adding-parameterized-calculated-field-data-sources"></a><span data-ttu-id="01a36-103">Az ER megoldások teljesítményének javítása a paraméterek SZÁMÍTOTT MEZŐ-adatforrások hozzáadásával</span><span class="sxs-lookup"><span data-stu-id="01a36-103">Improve the performance of ER solutions by adding parameterized CALCULATED FIELD data sources</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="01a36-104">Ez a témakör azt mutatja be, hogyan lehet [teljesítménykövetést](trace-execution-er-troubleshoot-perf.md) végezni a futtatott [elektronikus jelentéskészítési (ER)](general-electronic-reporting.md) formátumokon, majd felhasználni az információkat ezekből a követésekből a teljesítmény javításához egy paraméterezett **Számított mező** adatforrás konfigurálásával.</span><span class="sxs-lookup"><span data-stu-id="01a36-104">This topic explains how you can take [performance traces](trace-execution-er-troubleshoot-perf.md) of [Electronic reporting (ER)](general-electronic-reporting.md) formats that are run, and then use the information from those traces to help improve performance by configuring a parameterized **Calculated field** data source.</span></span>

<span data-ttu-id="01a36-105">Az ER üzleti dokumentumok létrehozására használatos konfigurációinak tervezési folyamatának részeként meghatározhatja azt a módszert, amellyel a rendszer adatokat kérhet le az alkalmazásból, majd a létrehozott kimenetbe illesztheti őket.</span><span class="sxs-lookup"><span data-stu-id="01a36-105">As part of the process of designing ER configurations to generate business documents, you define the method that is used to retrieve data from the application and enter it in the generated output.</span></span> <span data-ttu-id="01a36-106">A **Számított mező** típusú paraméterezett ER adatforrás tervezésével csökkenthető az adatbázis-hívások száma, és jelentősen csökkenthető az idő és költség, amely az ER formátumvégrehajtás részleteinek gyűjtéséhez kapcsolódik.</span><span class="sxs-lookup"><span data-stu-id="01a36-106">By designing a parametrized ER data source of the **Calculated field** type, you can reduce the number of database calls, and significantly reduce the time and cost that are involved in collecting the details of ER format execution.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="01a36-107">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="01a36-107">Prerequisites</span></span>

- <span data-ttu-id="01a36-108">A jelen témakörben szereplő példák végrehajtásához hozzáféréssel kell rendelkeznie a következő [szerepkörök](../sysadmin/tasks/assign-users-security-roles.md) egyikéhez:</span><span class="sxs-lookup"><span data-stu-id="01a36-108">To complete the examples in this topic, you must have the access to one of the following [roles](../sysadmin/tasks/assign-users-security-roles.md):</span></span>

    - <span data-ttu-id="01a36-109">Elektronikus jelentések fejlesztője</span><span class="sxs-lookup"><span data-stu-id="01a36-109">Electronic reporting developer</span></span>
    - <span data-ttu-id="01a36-110">Elektronikus jelentések funkcióival foglalkozó konzulens</span><span class="sxs-lookup"><span data-stu-id="01a36-110">Electronic reporting functional consultant</span></span>
    - <span data-ttu-id="01a36-111">Rendszergazda</span><span class="sxs-lookup"><span data-stu-id="01a36-111">System administrator</span></span>

- <span data-ttu-id="01a36-112">A vállalatot **DEMF** értékre kell beállítani.</span><span class="sxs-lookup"><span data-stu-id="01a36-112">The company must be set to **DEMF**.</span></span>
- <span data-ttu-id="01a36-113">Kövesse a témakör [1. függelékének](#appendix1) lépéseit a minta Microsoft ER-megoldás szállítói kifizetések feldolgozásához szükséges összetevőinek letöltéséhez, amelyek szükségesek a témakör példáinak elvégzéséhez.</span><span class="sxs-lookup"><span data-stu-id="01a36-113">Follow the steps in [Appendix 1](#appendix1) of this topic to download the components of the sample Microsoft ER solution that is required to complete the examples in this topic.</span></span>
- <span data-ttu-id="01a36-114">Kövesse a jelen témakör [2. függelékének](#appendix2) lépéseit, hogy a konfigurálja az ER-paraméterek minimális halmazát, amelyek szükségesek az ER.keretrendszerhez, hogy elősegítsék a minta Microsoft ER-megoldás teljesítményének javítását.</span><span class="sxs-lookup"><span data-stu-id="01a36-114">Follow the steps in [Appendix 2](#appendix2) of this topic to configure the minimal set of ER parameters that is required to use the ER framework to help improve the performance of the sample Microsoft ER solution.</span></span>

## <a name="import-the-sample-er-solution"></a><span data-ttu-id="01a36-115">A minta ER-megoldás importálása</span><span class="sxs-lookup"><span data-stu-id="01a36-115">Import the sample ER solution</span></span>

<span data-ttu-id="01a36-116">Tegyük fel, hogy egy új ER-megoldást kell terveznie, amellyel szállítói tranzakciókat bemutató új jelentést hozhat létre.</span><span class="sxs-lookup"><span data-stu-id="01a36-116">Imagine that you must design an ER solution to generate a new report that shows vendor transactions.</span></span> <span data-ttu-id="01a36-117">Jelenleg a kiválasztott szállítóhoz tartozó tranzakciókat a **Szállítói tranzakciók** oldalon találja (lépjen a **Kötelezettségek** \> **Szállítók** \> **Minden szállító** pontra, válasszon a szállítók közül, majd a Műveleti ablaktábla **Szállító** lapján, a **Tranzakciók** csoportban válassza a **Tranzakciók** elemet).</span><span class="sxs-lookup"><span data-stu-id="01a36-117">Currently, you can find the transactions for a selected vendor on the **Vendor transactions** page (go to **Account payable** \> **Vendors** \> **All vendors**, select a vendor, and then, on the Action Pane, on the **Vendor** tab, in the **Transactions** group, select **Transactions**).</span></span> <span data-ttu-id="01a36-118">Önnek azonban az összes szállítói tranzakció együttes megjelenítésére van szükség, egyetlen elektronikus dokumentumban, XML formátumban.</span><span class="sxs-lookup"><span data-stu-id="01a36-118">However, you want to have all vendor transactions together in one electronic document in XML format.</span></span> <span data-ttu-id="01a36-119">Ez a megoldás több olyan ER-konfigurációt is magában foglal, amelyek a szükséges adatmodell-, modell-hozzárendelési és formátum-összetevőket tartalmazzák.</span><span class="sxs-lookup"><span data-stu-id="01a36-119">This solution will consist of several ER configurations that contain the required data model, model mapping, and format components.</span></span>

<span data-ttu-id="01a36-120">Az első lépés az, hogy a minta ER-megoldást importálni kell a szállítói tranzakciók jelentésének előállításához.</span><span class="sxs-lookup"><span data-stu-id="01a36-120">The first step is to import the sample ER solution to generate a vendor transactions report.</span></span>

1. <span data-ttu-id="01a36-121">Jelentkezzen be a vállalata részére biztosított Microsoft Dynamics 365 Finance-példányba.</span><span class="sxs-lookup"><span data-stu-id="01a36-121">Sign in to the instance of Microsoft Dynamics 365 Finance that is provisioned for your company.</span></span>
2. <span data-ttu-id="01a36-122">Ebben a témakörben létrehozzuk és módosítjuk a konfigurációkat a **Litware, Inc.** mintavállalatra vonatkozóan.</span><span class="sxs-lookup"><span data-stu-id="01a36-122">In this topic, you will create and modify configurations for the **Litware, Inc.** sample company.</span></span> <span data-ttu-id="01a36-123">Győződjön meg róla, hogy ezt a konfigurációszolgáltatót hozzáadták a Finance-példányhoz, és aktívként megjelölték.</span><span class="sxs-lookup"><span data-stu-id="01a36-123">Make sure that this configuration provider has been added to your Finance instance and is marked as active.</span></span> <span data-ttu-id="01a36-124">További információért tekintse át a [Konfigurációszolgáltatók létrehozása és megjelölése aktívként](tasks/er-configuration-provider-mark-it-active-2016-11.md) eljárást.</span><span class="sxs-lookup"><span data-stu-id="01a36-124">For more information, see [Create configuration providers and mark them as active](tasks/er-configuration-provider-mark-it-active-2016-11.md).</span></span>
3. <span data-ttu-id="01a36-125">Az **Elektronikus jelentéskészítés** munkaterületen válassza ki a **Jelentéskészítési konfiguráció** csempét.</span><span class="sxs-lookup"><span data-stu-id="01a36-125">In the **Electronic reporting** workspace, select the **Reporting configurations** tile.</span></span>
4. <span data-ttu-id="01a36-126">A **Konfigurációk** lapon importálja az előfeltételként az Finance-ba letöltött ER-konfigurációkat, a következő sorrendben: adatmodell, modell-hozzárendelés, formátum.</span><span class="sxs-lookup"><span data-stu-id="01a36-126">On the **Configurations** page, import the ER configurations that you downloaded as a prerequisite into Finance, in the following order: data model, model mapping, format.</span></span> <span data-ttu-id="01a36-127">Minden konfiguráció esetén hajtsa végre az alábbi lépéseket:</span><span class="sxs-lookup"><span data-stu-id="01a36-127">For each configuration, follow these steps:</span></span>

    1. <span data-ttu-id="01a36-128">A Műveleti ablaktáblában válassza az **Átváltás** \> **Betöltés XML-fájlból** elemet.</span><span class="sxs-lookup"><span data-stu-id="01a36-128">On the Action Pane, select **Exchange** \> **Load from XML file**.</span></span>
    2. <span data-ttu-id="01a36-129">A **Tallózás** gombbal válassza ki a megfelelő, XML-formátumú fájlt az ER-konfigurációhoz.</span><span class="sxs-lookup"><span data-stu-id="01a36-129">Select **Browse**, and select the appropriate file for the ER configuration in XML format.</span></span>
    3. <span data-ttu-id="01a36-130">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="01a36-130">Select **OK**.</span></span>

![A Konfigurációk oldalon importált konfigurációk](./media/er-calculated-field-ds-performance-imported-configurations.png)

## <a name="review-the-sample-er-solution"></a><span data-ttu-id="01a36-132">A minta ER-megoldás áttekintése</span><span class="sxs-lookup"><span data-stu-id="01a36-132">Review the sample ER solution</span></span>

### <a name="review-the-model-mapping"></a><span data-ttu-id="01a36-133">A modell-leképezés áttekintése</span><span class="sxs-lookup"><span data-stu-id="01a36-133">Review the model mapping</span></span>

1. <span data-ttu-id="01a36-134">A **Konfigurációk** oldalon, a konfigurációk bal oldali panelen található fájában bontsa ki a **Teljesítményjavítás modellje** elemet, majd válassza a **Teljesítményfejlesztés leképezése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="01a36-134">On the **Configurations** page, in the configuration tree, expand **Performance improvement model**, and select **Performance improvement mapping**.</span></span>
2. <span data-ttu-id="01a36-135">A Műveleti ablaktáblán kattintson a **Tervező** elemre.</span><span class="sxs-lookup"><span data-stu-id="01a36-135">On the Action Pane, select **Designer**.</span></span>
3. <span data-ttu-id="01a36-136">A **Modell leképezése adatforráshoz** oldalon a Műveleti panelen válassza a **Tervező** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="01a36-136">On the **Model to datasource mapping** page, on the Action Pane, select **Designer**.</span></span>

    <span data-ttu-id="01a36-137">Ez az ER-leképezés a következők műveletek elvégzésére van tervezve:</span><span class="sxs-lookup"><span data-stu-id="01a36-137">This ER model mapping is designed to perform the following actions:</span></span>

    - <span data-ttu-id="01a36-138">A VendTrans táblában (**Trans** adatforrás) tárolt szállítói tranzakciók listájának beolvasása.</span><span class="sxs-lookup"><span data-stu-id="01a36-138">Fetch the list of vendor transactions that are stored in the VendTrans table (**Trans** data source).</span></span>
    - <span data-ttu-id="01a36-139">Minden tranzakcióhoz aVendTable táblából beolvassa annak a szállítónak a rekordját, akinek a tranzakciót feladták (**\#Vend** adatforrás).</span><span class="sxs-lookup"><span data-stu-id="01a36-139">For every transaction, fetch, from the VendTable table, the record of a vendor that the transaction has been posted for (**\#Vend** data source).</span></span>

    > [!NOTE]
    > <span data-ttu-id="01a36-140">A **\#Vend** adatforrás be van állítva a megfelelő szállítói rekord beolvasása a meglévő sok az egyhez kapcsolat használatával **\@.\>Relations'.VendTable\_AccountNum**.</span><span class="sxs-lookup"><span data-stu-id="01a36-140">The **\#Vend** data source is configured to fetch the corresponding vendor record by using the existing many-to-one relation **\@.'\>Relations'.VendTable\_AccountNum**.</span></span>

    <span data-ttu-id="01a36-141">A modell-leképezés ebben a konfigurációban implementálja az alap adatmodellt bármely ER formátumhoz, amely ehhez a modellhez lett készítve és a Finance által futtatva lett.</span><span class="sxs-lookup"><span data-stu-id="01a36-141">The model mapping in this configuration implements the base data model for any ER formats that are created for this model and run in Finance.</span></span> <span data-ttu-id="01a36-142">Tehát a **Trans** adatforrás tartalma ER-formátumoknak, például absztrakt **modell** adatforrásoknak van kitéve.</span><span class="sxs-lookup"><span data-stu-id="01a36-142">Therefore, the content of the **Trans** data source is exposed for ER formats such as abstract **model** data sources.</span></span>

    ![Trans adatforrás a modell-leképezés tervező oldalán](media/er-calculated-field-ds-performance-mapping-1.png)

4. <span data-ttu-id="01a36-144">Zárja be a **Modell-hozzárendelési tervező** lapot.</span><span class="sxs-lookup"><span data-stu-id="01a36-144">Close the **Model mapping designer** page.</span></span>
5. <span data-ttu-id="01a36-145">Zárja be a **Modell hozzárendelése adatforráshoz** lapot.</span><span class="sxs-lookup"><span data-stu-id="01a36-145">Close the **Model to datasource mapping** page.</span></span>

### <a name="review-format"></a><span data-ttu-id="01a36-146">Formátum áttekintése</span><span class="sxs-lookup"><span data-stu-id="01a36-146">Review format</span></span>

1. <span data-ttu-id="01a36-147">A **Konfigurációk** oldalon, a konfigurációk bal oldali panelen található fájában bontsa ki a **Teljesítményjavítás modellje** elemet, majd válassza a **Teljesítményfejlesztés formátuma** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="01a36-147">On the **Configurations** page, in the configuration tree, expand **Performance improvement model**, and select **Performance improvement format**.</span></span>
2. <span data-ttu-id="01a36-148">A Műveleti ablaktáblán kattintson a **Tervező** elemre.</span><span class="sxs-lookup"><span data-stu-id="01a36-148">On the Action Pane, select **Designer**.</span></span>
3. <span data-ttu-id="01a36-149">A **Formátumtervező** oldalon a **Hozzárendelés** fülön válassz a **Kibontás/összecsukás** elemet.</span><span class="sxs-lookup"><span data-stu-id="01a36-149">On the **Format designer** page, on the **Mapping** tab, select **Expand/Collapse**.</span></span>
4. <span data-ttu-id="01a36-150">Bontsa ki a **Modell**, **Adatok** és **Tranzakció** elemeket.</span><span class="sxs-lookup"><span data-stu-id="01a36-150">Expand the **Model**, **Data,** and **Transaction** items.</span></span>

    <span data-ttu-id="01a36-151">Ez az ER-formátum úgy van kialakítva, hogy a szállítói tranzakciók jelentését XML-formátumban hozza létre.</span><span class="sxs-lookup"><span data-stu-id="01a36-151">This ER format is designed to generate a vendor transactions report in XML format.</span></span>

    ![Az adatforrások és a konfigurált kötések formátumelemeinek formázása a Formátumtervezés oldalon](media/er-calculated-field-ds-performance-format.png)

5. <span data-ttu-id="01a36-153">Zárja be a **Formátumtervező** lapot.</span><span class="sxs-lookup"><span data-stu-id="01a36-153">Close the **Format designer** page.</span></span>

## <a name="run-the-sample-er-solution-to-trace-execution"></a><span data-ttu-id="01a36-154">A minta ER-megoldás futtatása a végrehajtás nyomon követéséhez</span><span class="sxs-lookup"><span data-stu-id="01a36-154">Run the sample ER solution to trace execution</span></span>

<span data-ttu-id="01a36-155">Tegyük fel, hogy befejezte az ER-megoldás első verziójának tervezését.</span><span class="sxs-lookup"><span data-stu-id="01a36-155">Imagine that you've finished designing the first version of the ER solution.</span></span> <span data-ttu-id="01a36-156">Ezt követően tesztelni szeretné a megoldást a Finance and Operations példányában, és elemezni a végrehajtás teljesítményét.</span><span class="sxs-lookup"><span data-stu-id="01a36-156">You now want to test the solution in your Finance instance and analyze the execution performance.</span></span>

### <a name="turn-on-the-er-performance-trace"></a><span data-ttu-id="01a36-157">Az ER teljesítmény-nyomkövetésének bekapcsolása</span><span class="sxs-lookup"><span data-stu-id="01a36-157">Turn on the ER performance trace</span></span>

1. <span data-ttu-id="01a36-158">Válassza a **DEMF** vállalatot.</span><span class="sxs-lookup"><span data-stu-id="01a36-158">Select the **DEMF** company.</span></span>
2. <span data-ttu-id="01a36-159">Hajtsa végre a következő lépéseket a [Teljesítmény-követés bekapcsolása](trace-execution-er-troubleshoot-perf.md#turn-on-the-er-performance-trace) alatt teljesítmény-nyomkövetés előállításához az ER-formátum futtatása során.</span><span class="sxs-lookup"><span data-stu-id="01a36-159">Follow the steps in [Turn on the ER performance trace](trace-execution-er-troubleshoot-perf.md#turn-on-the-er-performance-trace) to generate a performance trace while an ER format is run.</span></span>

    ![A Felhasználói paraméterek párbeszédablak](media/er-calculated-field-ds-performance-format-user-parameters.png)

### <a name="run-the-er-format"></a><a id="run-format"></a><span data-ttu-id="01a36-161">Az ER-formátum futtatása</span><span class="sxs-lookup"><span data-stu-id="01a36-161">Run the ER format</span></span>

1. <span data-ttu-id="01a36-162">Nyissa meg a következőt: **Szervezeti adminisztráció** \> **Elektronikus jelentéskészítés** \> **Konfigurációk**.</span><span class="sxs-lookup"><span data-stu-id="01a36-162">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="01a36-163">A **Konfigurációk** oldalon található konfigurációs fában válassza ki a **Teljesítmény-javítás formátuma** elemet.</span><span class="sxs-lookup"><span data-stu-id="01a36-163">On the **Configurations** page, in the configuration tree, select **Performance improvement format**.</span></span>
3. <span data-ttu-id="01a36-164">A Műveleti ablaktáblán kattintson a **Futtatás** elemre.</span><span class="sxs-lookup"><span data-stu-id="01a36-164">On the Action Pane, select **Run**.</span></span>

## <a name="use-the-performance-trace-to-analyze-model-mapping-performance"></a><span data-ttu-id="01a36-165">A teljesítmény nyomon követése használata a modell-leképezés teljesítményének elemzéséhez</span><span class="sxs-lookup"><span data-stu-id="01a36-165">Use the performance trace to analyze model mapping performance</span></span>

1. <span data-ttu-id="01a36-166">A **Konfigurációk** oldalon található konfigurációs fában válassza ki a **Teljesítmény-javítás leképezése** elemet.</span><span class="sxs-lookup"><span data-stu-id="01a36-166">On the **Configurations** page, in the configuration tree, select **Performance improvement mapping**.</span></span>
2. <span data-ttu-id="01a36-167">A Műveleti ablaktáblán kattintson a **Tervező** elemre.</span><span class="sxs-lookup"><span data-stu-id="01a36-167">On the Action Pane, select **Designer**.</span></span>
3. <span data-ttu-id="01a36-168">A **Modell leképezések** oldalon a Műveleti panelen válassza a **Tervező** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="01a36-168">On the **Model mappings** page, on the Action Pane, select **Designer**.</span></span>
4. <span data-ttu-id="01a36-169">A **Modell-hozzárendelési tervező** lapon a Műveleti ablaktáblában válassza ki a **Teljesítmény-nyomkövetés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="01a36-169">On the **Model mapping designer** page, on the Action Pane, select **Performance trace**.</span></span>
5. <span data-ttu-id="01a36-170">Válassza ki a legutóbb létrehozott nyomkövetést, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="01a36-170">Select the most recent trace that was generated, and then select **OK**.</span></span>

<span data-ttu-id="01a36-171">Az aktuális modell-hozzárendelés bizonyos adatforráselemeihez új információk jelennek meg:</span><span class="sxs-lookup"><span data-stu-id="01a36-171">New information is now available for some data source items of the current model mapping:</span></span>

- <span data-ttu-id="01a36-172">Az adatforrás által az adatok lekérésére fordított tényleges idő</span><span class="sxs-lookup"><span data-stu-id="01a36-172">The actual time that was spent getting data by using the data source</span></span>
- <span data-ttu-id="01a36-173">Ugyanez az időtartam a teljes modell-hozzárendelés lefuttatására fordított összes idő százalékaként kifejezve</span><span class="sxs-lookup"><span data-stu-id="01a36-173">The same time expressed as a percentage of the total time that was spent running the whole model mapping</span></span>

![Végrehajtási idő részletei a Modell-hozzárendelés tervező lapján](./media/er-calculated-field-ds-performance-mapping-2.png)

<span data-ttu-id="01a36-175">A **Teljesítményadatok** rácsa azt jeleníti meg, hogy a **Trans** adatforrás egy alkalommal hívja meg a VendTrans táblát.</span><span class="sxs-lookup"><span data-stu-id="01a36-175">The **Performance statistics** grid shows that the **Trans** data source calls the VendTrans table one time.</span></span> <span data-ttu-id="01a36-176">A **\[265\]\[Q:265\]** érték a **Trans** adatforrásban azt jelzi, hogy az 265 szállítói tranzakciót beolvasták az alkalmazás táblából, és vissza lettek küldve az adatmodellhez.</span><span class="sxs-lookup"><span data-stu-id="01a36-176">The value **\[265\]\[Q:265\]** of the **Trans** data source indicates that 265 vendor transactions have been fetched from the application table and returned to the data model.</span></span>

<span data-ttu-id="01a36-177">A **Teljesítményadatok** rácsa azt is jelzi, hogy az aktuális modell-hozzárendelés ismétlődő adatbázis-igényléseket hoz-e, miközben a **\#Vend** adatforrás fut.</span><span class="sxs-lookup"><span data-stu-id="01a36-177">The **Performance statistics** grid also shows that the current model mapping duplicates database requests while the **\#Vend** data source is run.</span></span> <span data-ttu-id="01a36-178">Ez a duplikálása a következő okok miatt történik meg:</span><span class="sxs-lookup"><span data-stu-id="01a36-178">This duplication occurs for the following reasons:</span></span>

- <span data-ttu-id="01a36-179">A szállítói táblát két alkalommal kell meghívni mind a 265 ismétlődő szállítói tranzakcióhoz, ez összesen 530 hívás:</span><span class="sxs-lookup"><span data-stu-id="01a36-179">The vendor table is called two times for each of the 265 iterated vendor transactions, for a total of 530 calls:</span></span>

    - <span data-ttu-id="01a36-180">Egy hívás történik a szállítói számla számának megadásához.</span><span class="sxs-lookup"><span data-stu-id="01a36-180">One call is made to enter the vendor account number.</span></span>
    - <span data-ttu-id="01a36-181">Egy hívás történik a szállítói nevének megadásához.</span><span class="sxs-lookup"><span data-stu-id="01a36-181">One call is made to enter the vendor name.</span></span>

- <span data-ttu-id="01a36-182">A szállítói táblát mindegyik ismétlődő szállítói tranzakcióhoz meg kell hívni, még akkor is, ha a beolvasott tranzakciók csak öt szállítóhoz lettek feladva.</span><span class="sxs-lookup"><span data-stu-id="01a36-182">The vendor table is called for each iterated vendor transaction, even though the fetched transactions have been posted for only five vendors.</span></span> <span data-ttu-id="01a36-183">A 530 hívásból 525 ismétlődő.</span><span class="sxs-lookup"><span data-stu-id="01a36-183">Of the 530 calls, 525 are duplicates.</span></span> <span data-ttu-id="01a36-184">A következő ábra mutatja az ismétlődő hívásokról kapott üzenetet (adatbázis-kérelmek).</span><span class="sxs-lookup"><span data-stu-id="01a36-184">The following illustration shows the message that you receive about duplicate calls (database requests).</span></span>

![Ismétlődő adatbázis-kérelmekkel kapcsolatos üzenet a Modell-hozzárendelési tervező oldalon](./media/er-calculated-field-ds-performance-mapping-2a.png)

<span data-ttu-id="01a36-186">A teljes modell-leképezés végrehajtási idejéből (kb. nyolc másodperc) több mint 80 százalék (kb. hat másodperc) telt el az értékek lehívásával a VendTable alkalmazástáblából.</span><span class="sxs-lookup"><span data-stu-id="01a36-186">Of the total model mapping execution time (approximately eight seconds), notice that more than 80 percent (approximately six seconds) has been spent retrieving values from the VendTable application table.</span></span> <span data-ttu-id="01a36-187">Ez a százalékos érték túl nagy az öt szállító két attribútumához képest, összehasonlítva a VendTrans-alkalmazás táblából származó adatok mennyiségével.</span><span class="sxs-lookup"><span data-stu-id="01a36-187">That percentage is too large for two attributes of five vendors, compared with the volume of information from the VendTrans application table.</span></span>

<span data-ttu-id="01a36-188">Ha csökkenteni szeretné az összes tranzakció szállítói adatainak beolvasásához szükséges hívások számát, valamint szeretné segíteni modell-hozzárendelés teljesítményének javítását, használhatja a **\#Vend** adatforrás gyorsítótárazását.</span><span class="sxs-lookup"><span data-stu-id="01a36-188">To reduce the number of calls that are made to get the vendor details for every transaction, and to improve the performance of the model mapping, you can use caching for the **\#Vend** data source.</span></span>

> [!NOTE]
> <span data-ttu-id="01a36-189">A **Trans\\\#Vend** adatforrást a program a **Trans** adatforrás aktuális tranzakciójának hatókörében gyorsítótárazza a futásidőben.</span><span class="sxs-lookup"><span data-stu-id="01a36-189">The **Trans\\\#Vend** data source will be cached in the scope of the current transaction of the **Trans** data source at runtime.</span></span>

<span data-ttu-id="01a36-190">A **\#Vend** adatforrás gyorsítótárazásával csökkenthető az ismétlődő hívások száma 525-ről 260-ra, de nem lehet a duplikálást teljes mértékben kiküszöbölni.</span><span class="sxs-lookup"><span data-stu-id="01a36-190">By caching the **\#Vend** data source, you reduce the number of duplicated calls from 525 to 260, but you don't completely eliminate the duplication.</span></span> <span data-ttu-id="01a36-191">A duplikálások teljes megszüntetéséhez beállítható a **Számított mezőtípus**, ami egy új, paraméterezett adatforrás.</span><span class="sxs-lookup"><span data-stu-id="01a36-191">To completely eliminate duplication, you can configure a new parameterized data source of the **Calculated field** type.</span></span>

## <a name="improve-the-model-mapping-based-on-information-from-the-execution-trace"></a><span data-ttu-id="01a36-192">A modell-hozzárendelés javítása a végrehajtási nyomkövetésből származó információk alapján</span><span class="sxs-lookup"><span data-stu-id="01a36-192">Improve the model mapping based on information from the execution trace</span></span>

### <a name="change-the-logic-of-the-model-mapping"></a><span data-ttu-id="01a36-193">A modell-hozzárendelés logikájának megváltoztatása</span><span class="sxs-lookup"><span data-stu-id="01a36-193">Change the logic of the model mapping</span></span>

<span data-ttu-id="01a36-194">Hajtsa végre a következő lépéseket a gyorsítótárazás és a **Számított mező** típusú adatforrás használatához , hogy megakadályozza az ismétlődő hívásokat az adatbázis felé.</span><span class="sxs-lookup"><span data-stu-id="01a36-194">Follow these steps to use caching and a data source of the **Calculated field** type, to help prevent duplicate calls to the database.</span></span>

1. <span data-ttu-id="01a36-195">A **Konfigurációk** oldalon található konfigurációs fában válassza ki a **Teljesítmény-javítás leképezése** elemet.</span><span class="sxs-lookup"><span data-stu-id="01a36-195">On the **Configurations** page, in the configuration tree, select **Performance improvement mapping**.</span></span>
2. <span data-ttu-id="01a36-196">A Műveleti ablaktáblán kattintson a **Tervező** elemre.</span><span class="sxs-lookup"><span data-stu-id="01a36-196">On the Action Pane, select **Designer**.</span></span>
3. <span data-ttu-id="01a36-197">A **Modell leképezések** oldalon a Műveleti panelen válassza a **Tervező** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="01a36-197">On the **Model mappings** page, on the Action Pane, select **Designer**.</span></span>
4. <span data-ttu-id="01a36-198">A **Model-leképezés tervező** lapon hajtsa végre az alábbi lépéseket, ha **Táblázatrekord** típusú adatforrás hozzáadásához a VendTable alkalmazástábla rekordjainak eléréséhez:</span><span class="sxs-lookup"><span data-stu-id="01a36-198">On the **Model mapping designer** page, follow these steps to add a data source of the **Table records** type to access records in the VendTable application table:</span></span>

    1. <span data-ttu-id="01a36-199">Az **Adatforrástípusok** panelen bontsa ki a **Dynamics 365 for Operations** elemet, és válassza a **Táblarekordok** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="01a36-199">In the **Data source types** pane, expand **Dynamics 365 for Operations**, and select **Table records**.</span></span>
    2. <span data-ttu-id="01a36-200">Válassza a **Gyökér hozzáadása** elemet.</span><span class="sxs-lookup"><span data-stu-id="01a36-200">Select **Add root**.</span></span>
    3. <span data-ttu-id="01a36-201">A párbeszédpanel **Név** mezőjébe írja be a **Vend** kifejezést.</span><span class="sxs-lookup"><span data-stu-id="01a36-201">In the dialog box, in the **Name** field, enter **Vend**.</span></span>
    4. <span data-ttu-id="01a36-202">A **Tábla** mezőbe írja be a **VendTable** kifejezést.</span><span class="sxs-lookup"><span data-stu-id="01a36-202">In the **Table** field, enter **VendTable**.</span></span>
    5. <span data-ttu-id="01a36-203">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="01a36-203">Select **OK**.</span></span>

5. <span data-ttu-id="01a36-204">A **Számított** mezőtípus adatforrásaihoz a hívásokat csak akkor lehet paraméterezni, ha azok az adatforrások egy tárolóban találhatók.</span><span class="sxs-lookup"><span data-stu-id="01a36-204">You can parameterize calls to data sources of the **Calculated field** type only if those data sources reside in a container.</span></span> <span data-ttu-id="01a36-205">Ennek megfelelően a következő lépések végrehajtásával adjon hozzá egy adatforrást az **Üres tároló** típushoz, hogy a **Kiszámított mező** típus új paraméterekkel rendelkezzen:</span><span class="sxs-lookup"><span data-stu-id="01a36-205">Therefore, follow these steps to add a data source of the **Empty container** type to hold a new parameterized data source of the **Calculated field** type:</span></span>

    1. <span data-ttu-id="01a36-206">Az **Adatforrástípusok** panelen bontsa ki az **Általános** elemet, és válassza a **Tároló űrítése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="01a36-206">In the **Data source types** pane, expand **General**, and select **Empty container**.</span></span>
    2. <span data-ttu-id="01a36-207">Válassza a **Gyökér hozzáadása** elemet.</span><span class="sxs-lookup"><span data-stu-id="01a36-207">Select **Add root**.</span></span>
    3. <span data-ttu-id="01a36-208">A párbeszédpanel **Név** mezőjébe írja be a **Box** kifejezést.</span><span class="sxs-lookup"><span data-stu-id="01a36-208">In the dialog box, in the **Name** field, enter **Box**.</span></span>
    3. <span data-ttu-id="01a36-209">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="01a36-209">Select **OK**.</span></span>

    ![A Box adatforrás a modell-leképezés tervező oldalán](./media/er-calculated-field-ds-performance-mapping-3.png)

6. <span data-ttu-id="01a36-211">Hajtsa végre a következő lépéseket a **Számított mező** típusú paraméterezett adatforrásának hozzáadásához:</span><span class="sxs-lookup"><span data-stu-id="01a36-211">Follow these steps to add a parameterized data source of the **Calculated field** type:</span></span>

    1. <span data-ttu-id="01a36-212">Az **Adatforrás** ablaktáblán válassz a **Box** elemét.</span><span class="sxs-lookup"><span data-stu-id="01a36-212">In the **Data sources** pane, select **Box**.</span></span>
    2. <span data-ttu-id="01a36-213">Az **Adatforrástípusok** panelen bontsa ki a **Funkciók** elemet, és válassza a **Számított mező** elemet.</span><span class="sxs-lookup"><span data-stu-id="01a36-213">In the **Data source types** pane, expand **Functions**, and select **Calculated field**.</span></span>
    3. <span data-ttu-id="01a36-214">Válassza a **Hozzáadás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="01a36-214">Select **Add**.</span></span>
    4. <span data-ttu-id="01a36-215">A párbeszédpanel **Név** mezőjébe írja be a **Vend** kifejezést.</span><span class="sxs-lookup"><span data-stu-id="01a36-215">In the dialog box, in the **Name** field, enter **Vend**.</span></span>
    5. <span data-ttu-id="01a36-216">Válassza a **Képlet szerkesztése** elemet.</span><span class="sxs-lookup"><span data-stu-id="01a36-216">Select **Edit formula**.</span></span>
    6. <span data-ttu-id="01a36-217">A **Képlettervező** lapon válassza ki a **Paraméterek** lehetőséget annak meghatározzák hogy az adatforrás hívásakor milyen paramétereket kell megadni.</span><span class="sxs-lookup"><span data-stu-id="01a36-217">On the **Formula designer** page, select **Parameters** to specify the parameters that must be provided when this data source is called.</span></span>
    7. <span data-ttu-id="01a36-218">A **Paraméterek** párbeszédpanelen kattintson az **Új** gombra.</span><span class="sxs-lookup"><span data-stu-id="01a36-218">In the **Parameters** dialog box, select **New**.</span></span>
    8. <span data-ttu-id="01a36-219">A **Név** mezőbe írja be a következőt: **parmVendAccNumber**.</span><span class="sxs-lookup"><span data-stu-id="01a36-219">In the **Name** field, enter **parmVendAccNumber**.</span></span>
    9. <span data-ttu-id="01a36-220">A **Típus** mezőben válassza ki a **Karakterlánc** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="01a36-220">In the **Type** field, select **String**.</span></span>
    10. <span data-ttu-id="01a36-221">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="01a36-221">Select **OK**.</span></span>
    11. <span data-ttu-id="01a36-222">A **Képlet** mezőbe írja be: **FIRSTORNULL(FILTER(Vend, Vend.AccountNum=parmVendAccNumber))**.</span><span class="sxs-lookup"><span data-stu-id="01a36-222">In the **Formula** field, enter **FIRSTORNULL(FILTER(Vend, Vend.AccountNum=parmVendAccNumber))**.</span></span>
    12. <span data-ttu-id="01a36-223">Válassza a **Mentés** lehetőséget, majd a **Képlettervező** oldalt.</span><span class="sxs-lookup"><span data-stu-id="01a36-223">Select **Save**, and close the **Formula designer** page.</span></span>
    13. <span data-ttu-id="01a36-224">Az új adatforrás hozzáadásához kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="01a36-224">Select **OK** to add the new data source.</span></span>

7. <span data-ttu-id="01a36-225">Hajtsa végre a következő lépéseket a hozzáadott adatforrás a végrehajtás közben gyorsítótárban történő megjelöléséhez:</span><span class="sxs-lookup"><span data-stu-id="01a36-225">Follow these steps to mark the added data source as cached during the execution:</span></span>

    1. <span data-ttu-id="01a36-226">Válassza az **Adatforrások** ablaktábla **Box\\Vend** elemét.</span><span class="sxs-lookup"><span data-stu-id="01a36-226">In the **Data sources** pane, select **Box\\Vend**.</span></span>
    2. <span data-ttu-id="01a36-227">Válassza a **Gyorsítótárazás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="01a36-227">Select **Cache**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="01a36-228">A **Box\\Vend** adatforrást a program a **Trans** adatforrás szállítói tranzakciójának hatókörében gyorsítótárazza a futásidőben.</span><span class="sxs-lookup"><span data-stu-id="01a36-228">The **Box\\Vend** data source will be cached in the scope of all vendor transactions of the **Trans** data source at runtime.</span></span>

8. <span data-ttu-id="01a36-229">A következő lépésekkel frissítheti a beágyazott **Trans\\\#Vend** adatforrást, **Box\\Vend** adatforrást használja:</span><span class="sxs-lookup"><span data-stu-id="01a36-229">Follow these steps to update the nested **Trans\\\#Vend** data source so that it uses the **Box\\Vend** data source:</span></span>

    1. <span data-ttu-id="01a36-230">Bontasa ki az **Adatforrások** ablaktábla **Trans** elemét.</span><span class="sxs-lookup"><span data-stu-id="01a36-230">In the **Data sources** pane, expand **Trans**.</span></span>
    2. <span data-ttu-id="01a36-231">Válassza ki a **Trans\\\#Vend** adatforrást, majd válassza a **Szerkesztés** \> **Képlet szerkesztése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="01a36-231">Select the **Trans\\\#Vend** data source, and then select **Edit** \> **Edit formula**.</span></span>
    3. <span data-ttu-id="01a36-232">A **Képlettervező** lap **Képlet** mezőjébe írja be a mezőbe a következőt: **Box.Vend(\@.AccountNum)**.</span><span class="sxs-lookup"><span data-stu-id="01a36-232">On the **Formula designer** page, in the **Formula** field, enter **Box.Vend(\@.AccountNum)**.</span></span>
    4. <span data-ttu-id="01a36-233">Válassza a **Mentés** lehetőséget, majd zárja be a **Képlettervező** oldalt.</span><span class="sxs-lookup"><span data-stu-id="01a36-233">Select **Save**, and then close the **Formula designer** page.</span></span>
    5. <span data-ttu-id="01a36-234">A kiválasztott adatforrás változásainak befejezéséhez kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="01a36-234">Select **OK** to complete your changes to the selected data source.</span></span>

9. <span data-ttu-id="01a36-235">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="01a36-235">Select **Save**.</span></span>

    ![A Vend adatforrás a Modell-leképezés tervező oldalán](./media/er-calculated-field-ds-performance-mapping-4.png)

10. <span data-ttu-id="01a36-237">Zárja be a **Modell-hozzárendelési tervező** lapot.</span><span class="sxs-lookup"><span data-stu-id="01a36-237">Close the **Model mapping designer** page.</span></span>
11. <span data-ttu-id="01a36-238">Zárja be a **Modell-hozzárendelések** lapot.</span><span class="sxs-lookup"><span data-stu-id="01a36-238">Close the **Model mappings** page.</span></span>

### <a name="complete-the-modified-version-of-the-er-model-mapping"></a><span data-ttu-id="01a36-239">Az ER-modell-hozzárendelés módosított verziójának elvégzése</span><span class="sxs-lookup"><span data-stu-id="01a36-239">Complete the modified version of the ER model mapping</span></span>

1. <span data-ttu-id="01a36-240">A **Konfigurációk** lap **Verziók** gyorslapján válassza ki az **1.2**-es verziót a **Teljesítményjavítás-leképezés** konfigurációhoz.</span><span class="sxs-lookup"><span data-stu-id="01a36-240">On the **Configurations** page, on the **Versions** FastTab, select version **1.2** of the **Performance improvement mapping** configuration.</span></span>
2. <span data-ttu-id="01a36-241">Válassza ki az **Állapot módosítása** \> **Kész** elemet majd válassza az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="01a36-241">Select **Change status** \> **Complete**, and then select **OK**.</span></span>

## <a name="run-the-modified-er-solution-to-trace-execution"></a><span data-ttu-id="01a36-242">A módosított ER-megoldás futtatása a végrehajtás nyomon követéséhez</span><span class="sxs-lookup"><span data-stu-id="01a36-242">Run the modified ER solution to trace execution</span></span>

<span data-ttu-id="01a36-243">Ismételje meg a jelen témakörben korábban ismertetett, [ER-formátum futtatása](#run-format) szakasz lépéseit az új teljesítmény-nyomkövetés létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="01a36-243">Repeat the steps in the [Run the ER format](#run-format) section earlier in this topic to generate a new performance trace.</span></span>

## <a name="use-the-performance-trace-to-analyze-adjustments-to-the-model-mapping"></a><span data-ttu-id="01a36-244">A teljesítmény nyomon követése használata a modell-leképezés módosításainak elemzéséhez</span><span class="sxs-lookup"><span data-stu-id="01a36-244">Use the performance trace to analyze adjustments to the model mapping</span></span> 

1. <span data-ttu-id="01a36-245">A **Konfigurációk** oldalon található konfigurációs fában válassza ki a **Teljesítmény-javítás leképezése** elemet.</span><span class="sxs-lookup"><span data-stu-id="01a36-245">On the **Configurations** page, in the configuration tree, select **Performance improvement mapping**.</span></span>
2. <span data-ttu-id="01a36-246">A Műveleti ablaktáblán kattintson a **Tervező** elemre.</span><span class="sxs-lookup"><span data-stu-id="01a36-246">On the Action Pane, select **Designer**.</span></span>
3. <span data-ttu-id="01a36-247">A **Modell leképezések** oldalon a Műveleti panelen válassza a **Tervező** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="01a36-247">On the **Model mappings** page, on the Action Pane, select **Designer**.</span></span>
4. <span data-ttu-id="01a36-248">A **Modell-hozzárendelési tervező** lapon a Műveleti ablaktáblában válassza ki a **Teljesítmény-nyomkövetés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="01a36-248">On the **Model mapping designer** page, on the Action Pane, select **Performance trace**.</span></span>
5. <span data-ttu-id="01a36-249">Válassza ki a legutóbb létrehozott nyomkövetést, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="01a36-249">Select the most recent trace that was generated, and then select **OK**.</span></span>

<span data-ttu-id="01a36-250">Megfigyelheti, hogy az Ön által a modell-hozzárendelésen végzett kiigazításokkal megszüntette az adatbázisba intézett ismétlődő lekérdezéseket.</span><span class="sxs-lookup"><span data-stu-id="01a36-250">Notice that the adjustments that you made to the model mapping have eliminated duplicate queries to database.</span></span> <span data-ttu-id="01a36-251">Az adott modellhozzárendeléshez tartozó, adatbázistáblákba és adatforrásokba küldött lehívások száma csökkent.</span><span class="sxs-lookup"><span data-stu-id="01a36-251">The number of calls to database tables and data sources for this model mapping has also been reduced.</span></span>

![Híváslánc információk a Modell-leképezés tervező oldalán 1](./media/er-calculated-field-ds-performance-mapping-5.png)

<span data-ttu-id="01a36-253">A teljes végrehajtási idő csökkent a 20-adára csökkent (mintegy 8 másodperc helyett mintegy 400 ezredmásodperc).</span><span class="sxs-lookup"><span data-stu-id="01a36-253">The total execution time has been reduced about 20 times (from about 8 seconds to about 400 milliseconds).</span></span> <span data-ttu-id="01a36-254">Ezáltal a teljes ER-megoldás teljesítménye javult.</span><span class="sxs-lookup"><span data-stu-id="01a36-254">Therefore, the performance of the whole ER solution has been improved.</span></span>

![Híváslánc információk a Modell-leképezés tervező oldalán 2](./media/er-calculated-field-ds-performance-mapping-5a.png)

## <a name="appendix-1-download-the-components-of-the-sample-microsoft-er-solution"></a><a name="appendix1"></a><span data-ttu-id="01a36-256">1. függelék: A minta Microsoft ER megoldás komponenseinek letöltése</span><span class="sxs-lookup"><span data-stu-id="01a36-256">Appendix 1: Download the components of the sample Microsoft ER solution</span></span>

<span data-ttu-id="01a36-257">A következő fájlokat le kell töltenie, és helyben tárolnia.</span><span class="sxs-lookup"><span data-stu-id="01a36-257">You must download the following files and store them locally.</span></span>

| <span data-ttu-id="01a36-258">Fájl</span><span class="sxs-lookup"><span data-stu-id="01a36-258">File</span></span>                                        | <span data-ttu-id="01a36-259">Tartalom</span><span class="sxs-lookup"><span data-stu-id="01a36-259">Content</span></span> |
|---------------------------------------------|---------|
| <span data-ttu-id="01a36-260">Teljesítményjavítás modell.verzió.1</span><span class="sxs-lookup"><span data-stu-id="01a36-260">Performance improvement model.version.1</span></span>     | [<span data-ttu-id="01a36-261">Minta ER-adatmodell konfigurációja</span><span class="sxs-lookup"><span data-stu-id="01a36-261">Sample ER data model configuration</span></span>](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg) |
| <span data-ttu-id="01a36-262">Teljesítmény-javítás leképezés.verzió.1.1</span><span class="sxs-lookup"><span data-stu-id="01a36-262">Performance improvement mapping.version.1.1</span></span> | [<span data-ttu-id="01a36-263">Minta ER-adatmodell leképezési konfigurációja</span><span class="sxs-lookup"><span data-stu-id="01a36-263">Sample ER model mapping configuration</span></span>](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg) |
| <span data-ttu-id="01a36-264">Teljesítmény-javítás formátum.verzió.1.1</span><span class="sxs-lookup"><span data-stu-id="01a36-264">Performance improvement format.version.1.1</span></span>  | [<span data-ttu-id="01a36-265">Minta ER-formátum konfigurációja</span><span class="sxs-lookup"><span data-stu-id="01a36-265">Sample ER format configuration</span></span>](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg) |

## <a name="appendix-2-configure-the-er-framework"></a><a name="appendix2"></a><span data-ttu-id="01a36-266">2. melléklet: Az ER-keretrendszer konfigurálása</span><span class="sxs-lookup"><span data-stu-id="01a36-266">Appendix 2: Configure the ER framework</span></span>

<span data-ttu-id="01a36-267">Mielőtt elkezdené használni az ER keretrendszert a minta Microsoft ER-megoldás teljesítményének javítása érdekében, konfigurálnia kell az ER-paraméterek minimális készletét.</span><span class="sxs-lookup"><span data-stu-id="01a36-267">Before you can start to use the ER framework to improve the performance of the sample Microsoft ER solution, you must configure the minimal set of ER parameters.</span></span>

### <a name="configure-er-parameters"></a><a id="ConfigureParameters"></a><span data-ttu-id="01a36-268">ER-paraméterek konfigurálása</span><span class="sxs-lookup"><span data-stu-id="01a36-268">Configure ER parameters</span></span>

1. <span data-ttu-id="01a36-269">Ugorjon a **Szervezeti adminisztráció** \> **Munkaterületek** \> **Elektronikus jelentés** pontra.</span><span class="sxs-lookup"><span data-stu-id="01a36-269">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
2. <span data-ttu-id="01a36-270">A **Lokalizációs konfigurációk** oldalon, a **Kapcsolódó hivatkozások** szakaszban, válassza az **Elektronikus jelentéskészítés paraméterei** elemet.</span><span class="sxs-lookup"><span data-stu-id="01a36-270">On the **Localization configurations** page, in the **Related links** section, select **Electronic reporting parameters**.</span></span>
3. <span data-ttu-id="01a36-271">Az **Elektronikus jelentéskészítési paraméterek** oldalon, az **Általános** lapon a **Tervezői mód engedélyezése** lehetőséget állítsa **Igen** értékre.</span><span class="sxs-lookup"><span data-stu-id="01a36-271">On the **Electronic reporting parameters** page, on the **General** tab, set the **Enable design mode** option to **Yes**.</span></span>
4. <span data-ttu-id="01a36-272">A **Mellékletek** lapon állítsa be a következő paramétereket:</span><span class="sxs-lookup"><span data-stu-id="01a36-272">On the **Attachments** tab, set the following parameters:</span></span>

    - <span data-ttu-id="01a36-273">A **Konfigurációk** mezőben válassza ki a **Fájl** típust az **DEMF** vállalat esetében.</span><span class="sxs-lookup"><span data-stu-id="01a36-273">In the **Configurations** field, select the **File** type for the **DEMF** company.</span></span>
    - <span data-ttu-id="01a36-274">A **Feladatarchívum**, **Ideiglenes**, **Alap** és **Egyebek** mezőkben válassza a **Fájl** típust.</span><span class="sxs-lookup"><span data-stu-id="01a36-274">In the **Job archive**, **Temporary**, **Baseline**, and **Others** fields, select the **File** type.</span></span>

<span data-ttu-id="01a36-275">Az ER-paraméterekkel kapcsolatos további tudnivalókat lásd: [ER-keretrendszer konfigurálása](electronic-reporting-er-configure-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="01a36-275">For more information about ER parameters, see [Configure the ER framework](electronic-reporting-er-configure-parameters.md).</span></span>

### <a name="activate-an-er-configuration-provider"></a><a id="ActivateProvider"></a><span data-ttu-id="01a36-276">ER-konfigurációszolgáltató aktiválása</span><span class="sxs-lookup"><span data-stu-id="01a36-276">Activate an ER configuration provider</span></span>

<span data-ttu-id="01a36-277">Minden hozzáadott ER-konfigurációt egy ER-konfigurációszolgáltató által birtokoltként kell megjelölni.</span><span class="sxs-lookup"><span data-stu-id="01a36-277">Every ER configuration that is added is marked as owned by an ER configuration provider.</span></span> <span data-ttu-id="01a36-278">Erre a célra az **Elektronikus jelentéskészítés** munkaterületen aktiválható ER-konfigurációszolgáltató használatos.</span><span class="sxs-lookup"><span data-stu-id="01a36-278">The ER configuration provider that is activated in the **Electronic reporting** workspace is used for this purpose.</span></span> <span data-ttu-id="01a36-279">Éppen ezért aktiválnia kell egy ER-konfigurációszolgáltatót az **Elektronikus jelentéskészítés** munkaterületen, mielőtt elkezdené az ER-konfigurációk hozzáadását vagy szerkesztését.</span><span class="sxs-lookup"><span data-stu-id="01a36-279">Therefore, you must activate an ER configuration provider in the **Electronic reporting** workspace before you start to add or edit ER configurations.</span></span>

> [!NOTE]
> <span data-ttu-id="01a36-280">Csak az ER-konfiguráció tulajdonosa szerkesztheti a konfigurációt.</span><span class="sxs-lookup"><span data-stu-id="01a36-280">Only the owner of an ER configuration can edit the configuration.</span></span> <span data-ttu-id="01a36-281">Éppen ezért aktiválnia kell a megfelelő ER-konfigurációszolgáltatót az **Elektronikus jelentéskészítés** munkaterületen, mielőtt elkezdené az ER-konfigurációk hozzáadását vagy szerkesztését.</span><span class="sxs-lookup"><span data-stu-id="01a36-281">Therefore, before an ER configuration can be edited, the appropriate ER configuration provider must be activated in the **Electronic reporting** workspace.</span></span>

#### <a name="review-the-list-of-er-configuration-providers"></a><a id="ReviewProvidersList"></a><span data-ttu-id="01a36-282">Az ER-konfigurációszolgáltatók listájának áttekintése</span><span class="sxs-lookup"><span data-stu-id="01a36-282">Review the list of ER configuration providers</span></span>

1. <span data-ttu-id="01a36-283">Ugorjon a **Szervezeti adminisztráció** \> **Munkaterületek** \> **Elektronikus jelentés** pontra.</span><span class="sxs-lookup"><span data-stu-id="01a36-283">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
2. <span data-ttu-id="01a36-284">A **Lokalizációs konfigurációk** oldalon, a **Kapcsolódó hivatkozások** szakaszban, válassza a **Konfigurációszolgáltatók** elemet.</span><span class="sxs-lookup"><span data-stu-id="01a36-284">On the **Localization configurations** page, in the **Related links** section, select **Configuration providers**.</span></span>
3. <span data-ttu-id="01a36-285">A **Konfigurációszolgáltatók tábla** oldalon minden szolgáltatói rekordnak egyedi neve és URL-címe van.</span><span class="sxs-lookup"><span data-stu-id="01a36-285">On the **Configuration provider table** page, each provider record has a unique name and URL.</span></span> <span data-ttu-id="01a36-286">Tekintse át az oldal tartalmát.</span><span class="sxs-lookup"><span data-stu-id="01a36-286">Review the contents of this page.</span></span> <span data-ttu-id="01a36-287">Ha a már létezik a **Litware, Inc.** rekordja, hagyja ki a következő eljárást: [Új ER-konfigurációszolgáltató hozzáadása](#ActivateProvider).</span><span class="sxs-lookup"><span data-stu-id="01a36-287">If a record for **Litware, Inc.** already exists, skip the next procedure, [Add a new ER configuration provider](#ActivateProvider).</span></span>

#### <a name="add-a-new-er-configuration-provider"></a><a id="ActivateProvider"></a><span data-ttu-id="01a36-288">Új ER-konfigurációszolgáltató hozzáadása</span><span class="sxs-lookup"><span data-stu-id="01a36-288">Add a new ER configuration provider</span></span>

1. <span data-ttu-id="01a36-289">Ugorjon a **Szervezeti adminisztráció** \> **Munkaterületek** \> **Elektronikus jelentés** pontra.</span><span class="sxs-lookup"><span data-stu-id="01a36-289">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
2. <span data-ttu-id="01a36-290">A **Lokalizációs konfigurációk** oldalon, a **Kapcsolódó hivatkozások** szakaszban, válassza a **Konfigurációszolgáltatók** elemet.</span><span class="sxs-lookup"><span data-stu-id="01a36-290">On the **Localization configurations** page, in the **Related links** section, select **Configuration providers**.</span></span>
3. <span data-ttu-id="01a36-291">A **Konfigurációszolgáltatók** oldalon válassza az **Új** elemet.</span><span class="sxs-lookup"><span data-stu-id="01a36-291">On the **Configuration providers** page, select **New**.</span></span>
4. <span data-ttu-id="01a36-292">A **Név** mezőbe írja be a következőt: **Litware, Inc.**.</span><span class="sxs-lookup"><span data-stu-id="01a36-292">In the **Name** field, enter **Litware, Inc.**</span></span>
5. <span data-ttu-id="01a36-293">Az **Internetcím** mezőben adja meg a következőt: `https://www.litware.com`.</span><span class="sxs-lookup"><span data-stu-id="01a36-293">In the **Internet address** field, enter `https://www.litware.com`.</span></span>
6. <span data-ttu-id="01a36-294">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="01a36-294">Select **Save**.</span></span>

#### <a name="activate-an-er-configuration-provider"></a><a id="ActivateAddedProvider"></a><span data-ttu-id="01a36-295">ER-konfigurációszolgáltató aktiválása</span><span class="sxs-lookup"><span data-stu-id="01a36-295">Activate an ER configuration provider</span></span>

1. <span data-ttu-id="01a36-296">Ugorjon a **Szervezeti adminisztráció** \> **Munkaterületek** \> **Elektronikus jelentés** pontra.</span><span class="sxs-lookup"><span data-stu-id="01a36-296">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
2. <span data-ttu-id="01a36-297">A **Lokalizációs konfigurációk** oldalon, a **Konfigurációszolgáltatók** szakaszban válassza ki a **Litware, Inc.** csempét, majd válassza a **Beállítás aktívként** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="01a36-297">On the **Localization configurations** page, in the **Configuration providers** section, select the **Litware, Inc.** tile, and then select **Set active**.</span></span>

<span data-ttu-id="01a36-298">További információért az ER-konfigurációszolgáltatókkal kapcsolatban tekintse át a [Konfigurációszolgáltatók létrehozása és megjelölése aktívként](tasks/er-configuration-provider-mark-it-active-2016-11.md) eljárást.</span><span class="sxs-lookup"><span data-stu-id="01a36-298">For more information about ER configuration providers, see [Create configuration providers and mark them as active](tasks/er-configuration-provider-mark-it-active-2016-11.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="01a36-299">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="01a36-299">Additional resources</span></span>

- [<span data-ttu-id="01a36-300">Elektronikus jelentések áttekintése</span><span class="sxs-lookup"><span data-stu-id="01a36-300">Electronic Reporting overview</span></span>](general-electronic-reporting.md)
- [<span data-ttu-id="01a36-301">Az ER-formátumok végrehajtásának nyomon követése a teljesítménnyel kapcsolatos problémák elhárítása érdekében</span><span class="sxs-lookup"><span data-stu-id="01a36-301">Trace the execution of ER formats to troubleshoot performance issues</span></span>](trace-execution-er-troubleshoot-perf.md)
- [<span data-ttu-id="01a36-302">ER adatforrások paraméterezett hívásainak támogatása a Számított mezőtípusban</span><span class="sxs-lookup"><span data-stu-id="01a36-302">Support parameterized calls of ER data sources of the Calculated field type</span></span>](er-calculated-field-type.md)
