---
title: Egy végrehajtott ER formátum hibakeresési adatforrásai az adatfolyam elemzéséhez és átalakításához
description: Ez a témakör azt mutatja be, hogyan lehet hibakeresést végezni egy végrehajtott ER-formátum adatforrásaiból, hogy jobban megérthesse a konfigurált adatáramlást és átalakítást.
author: NickSelin
manager: AnnBe
ms.date: 04/22/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERSolutionTable, EROperationDesigner
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-04-01
ms.dyn365.ops.version: Release 10.0.11
ms.openlocfilehash: 5b51c4beac0ddf1e2b53fe300e10c0f608e5d1e1
ms.sourcegitcommit: 153bb33722c02501bf7bcfd56ac887602d5dfbd3
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/29/2020
ms.locfileid: "3318666"
---
# <a name="debug-data-sources-of-an-executed-er-format-to-analyze-data-flow-and-transformation"></a><span data-ttu-id="e7444-103">Egy végrehajtott ER formátum hibakeresési adatforrásai az adatfolyam elemzéséhez és átalakításához</span><span class="sxs-lookup"><span data-stu-id="e7444-103">Debug data sources of an executed ER format to analyze data flow and transformation</span></span>

[!include[banner](../includes/banner.md)]

[!include[banner](../includes/preview-banner.md)]

<span data-ttu-id="e7444-104">Amikor egy elektronikus jelentéskészítési (ER) megoldást [konfigurál](tasks/er-format-configuration-2016-11.md) kimenő dokumentumok létrehozásához meghatározhatja azt a módszert, amellyel a rendszer adatokat kérhet le az alkalmazásból, majd a létrehozott kimeneti fájlba illesztheti őket.</span><span class="sxs-lookup"><span data-stu-id="e7444-104">When you [configure](tasks/er-format-configuration-2016-11.md) an Electronic reporting (ER) solution to generate outbound documents, you define the methods that are used to get data out of the application and enter it in the output that is generated.</span></span> <span data-ttu-id="e7444-105">Ha hatékonyabbá szeretné tenni az ER-megoldás életciklus-támogatását, a megoldásnak egy ER [adatmodellből](general-electronic-reporting.md#DataModelComponent) és annak [leképezési](general-electronic-reporting.md#ModelMappingComponent) összetevőiből kell állnia , valamint egy ER [formátumból](general-electronic-reporting.md#FormatComponentOutbound) és annak leképezési összetevőiből, így a modell-leképezés alkalmazásspecifikus legyen, míg a többi komponens alkalmazásól független maradjon.</span><span class="sxs-lookup"><span data-stu-id="e7444-105">To make the life cycle support of the ER solution more efficient, your solution should consist of an ER [data model](general-electronic-reporting.md#DataModelComponent) and its [mapping](general-electronic-reporting.md#ModelMappingComponent) components, and also an ER [format](general-electronic-reporting.md#FormatComponentOutbound) and its mapping components, so that the model mapping is application-specific, whereas other components remain application-agnostic.</span></span> <span data-ttu-id="e7444-106">Emiatt ER számos összetevő [hatással lehet](general-electronic-reporting.md#FormatComponentOutbound) az adatok beviteli folyamatára a létrejövő kimenetben.</span><span class="sxs-lookup"><span data-stu-id="e7444-106">Therefore, several ER components might [affect](general-electronic-reporting.md#FormatComponentOutbound) the process of entering data in the generated output.</span></span>

<span data-ttu-id="e7444-107">Előfordulhat, hogy a létrejövő kimenet adatai eltérően jelennek meg az alkalmazás adatbázisában szereplő ugyanezen adatoktól.</span><span class="sxs-lookup"><span data-stu-id="e7444-107">Sometimes, the data of the generated output looks different than the same data in the application database.</span></span> <span data-ttu-id="e7444-108">Ezekben az esetekben meg kell határozni, hogy melyik ER-összetevő felelős az adatok átalakításáért.</span><span class="sxs-lookup"><span data-stu-id="e7444-108">In these cases, you will want to determine which ER component is responsible for the data transformation.</span></span> <span data-ttu-id="e7444-109">Az ER-adatforrás-hibakereső funkció jelentősen csökkenti a vizsgálathoz szükséges időt és költségeket.</span><span class="sxs-lookup"><span data-stu-id="e7444-109">The ER data source debugger feature significantly reduces the time and cost that are involved in this investigation.</span></span> <span data-ttu-id="e7444-110">Az ER-formátum végrehajtását félbeszakíthatja, és megnyithatja az adatforrás-hibakereső felületét.</span><span class="sxs-lookup"><span data-stu-id="e7444-110">You can interrupt the execution of an ER format and open the data source debugger interface.</span></span> <span data-ttu-id="e7444-111">Itt böngészhet az elérhető adatforrások között, és kiválaszthat egy egyedi adatforrást a végrehajtáshoz.</span><span class="sxs-lookup"><span data-stu-id="e7444-111">There, you can browse the available data sources and select an individual data source for execution.</span></span> <span data-ttu-id="e7444-112">Ez a manuális végrehajtás egy ER-formátum tényleges futtatásakor szimulálja az adatforrás végrehajtását.</span><span class="sxs-lookup"><span data-stu-id="e7444-112">This manual execution simulates the execution of the data source during the real run of an ER format.</span></span> <span data-ttu-id="e7444-113">Az eredmény olyan oldalon jelenik meg, ahol elemezni lehet a kapott adatokat.</span><span class="sxs-lookup"><span data-stu-id="e7444-113">The result is presented on a page where you can analyze the data that is received.</span></span>

<span data-ttu-id="e7444-114">Ha be kívánja kapcsolni az adatforrás hibakeresési funkcióját, állítsa be az **Adatok hibakeresésének engedélyezése a formátum futtatása során** lehetőséget **Igen** értékre az ER felhasználói paraméterei.</span><span class="sxs-lookup"><span data-stu-id="e7444-114">To turn on the data source debugging feature, set the **Enable data debugging at format run** option to **Yes** in the ER user parameters.</span></span> <span data-ttu-id="e7444-115">Ezt követően elindíthatja az adatforrás hibakeresését, miközben a kimenő dokumentumok létrehozásához futtat egy ER-formátumot.</span><span class="sxs-lookup"><span data-stu-id="e7444-115">You can then start data source debugging while you run an ER format to generate outbound documents.</span></span> <span data-ttu-id="e7444-116">A **Hibakeresés indítása** lehetőséggel is elindíthatja az adatforrás hibakeresését egy ER-formátumhoz, amely konfigurálva van az [ER művelettervezőben](./tasks/er-format-configuration-2016-11.md#design-the-format-of-an-electronic-document).</span><span class="sxs-lookup"><span data-stu-id="e7444-116">You can also use the **Start debugging** option to initiate data source debugging for an ER format that is configured in the [ER Operation designer](./tasks/er-format-configuration-2016-11.md#design-the-format-of-an-electronic-document).</span></span>

<span data-ttu-id="e7444-117">Ez a témakör a végrehajtható ER formátumokhoz tartozó adatforrás-hibakeresés kezdeményezéséhez tartalmaz útmutatást.</span><span class="sxs-lookup"><span data-stu-id="e7444-117">This topic provides guidelines for initiating data source debugging for executed ER formats.</span></span> <span data-ttu-id="e7444-118">Bemutatja, hogy az adatok hogyan segítenek az adatáramlás és az adatok átalakítások megértésében.</span><span class="sxs-lookup"><span data-stu-id="e7444-118">It explains how the information can help you understand the data flow and data transformations.</span></span> <span data-ttu-id="e7444-119">Az ebben a témakörben szereplő példák a szállítói kifizetések feldolgozásának üzleti folyamatát használják.</span><span class="sxs-lookup"><span data-stu-id="e7444-119">The examples in this topic use the business process for vendor payments processing.</span></span>

## <a name="limitations"></a><span data-ttu-id="e7444-120">Korlátozások</span><span class="sxs-lookup"><span data-stu-id="e7444-120">Limitations</span></span>

<span data-ttu-id="e7444-121">Az adatforrás-hibakereső használható a kimenő dokumentumok létrehozásához futtatott, ER formátumokban használt adatforrások adatainak eléréséhez.</span><span class="sxs-lookup"><span data-stu-id="e7444-121">The data source debugger can be used to access the data of data sources that are used in ER formats that are run to generate outbound documents.</span></span> <span data-ttu-id="e7444-122">Nem használható a bejövő dokumentumok elemzésére szolgál ER-formátumok adatforrásainak hibakeresésére.</span><span class="sxs-lookup"><span data-stu-id="e7444-122">It can't be used to debug data sources of ER formats that are designed to parse inbound documents.</span></span>

<span data-ttu-id="e7444-123">A következő ER-formátum beállítások nem érhetők el az adatforrások hibakereséséhez:</span><span class="sxs-lookup"><span data-stu-id="e7444-123">The following settings of ER formats aren't currently accessible for data source debugging:</span></span>

- <span data-ttu-id="e7444-124">Formátumalakítások</span><span class="sxs-lookup"><span data-stu-id="e7444-124">Format transformations</span></span>
- <span data-ttu-id="e7444-125">Formátum és leképezés ellenőrzési szabályai</span><span class="sxs-lookup"><span data-stu-id="e7444-125">Format and mapping validation rules</span></span>
- <span data-ttu-id="e7444-126">Kifejezések engedélyezése</span><span class="sxs-lookup"><span data-stu-id="e7444-126">Enabling expressions</span></span>
- <span data-ttu-id="e7444-127">A memóriában tárolt adatgyűjtés részletei</span><span class="sxs-lookup"><span data-stu-id="e7444-127">Details of in-memory data collection</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e7444-128">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="e7444-128">Prerequisites</span></span>

- <span data-ttu-id="e7444-129">A jelen témakörben szereplő példák végrehajtásához hozzáféréssel kell rendelkeznie a következő [szerepkörök](../sysadmin/tasks/assign-users-security-roles.md) egyikéhez:</span><span class="sxs-lookup"><span data-stu-id="e7444-129">To complete the examples in this topic, you must have the access to one of the following [roles](../sysadmin/tasks/assign-users-security-roles.md):</span></span>

    - <span data-ttu-id="e7444-130">Elektronikus jelentések fejlesztője</span><span class="sxs-lookup"><span data-stu-id="e7444-130">Electronic reporting developer</span></span>
    - <span data-ttu-id="e7444-131">Elektronikus jelentések funkcióival foglalkozó konzulens</span><span class="sxs-lookup"><span data-stu-id="e7444-131">Electronic reporting functional consultant</span></span>
    - <span data-ttu-id="e7444-132">Rendszergazda</span><span class="sxs-lookup"><span data-stu-id="e7444-132">System administrator</span></span>

- <span data-ttu-id="e7444-133">A vállalatot **DEMF** értékre kell beállítani.</span><span class="sxs-lookup"><span data-stu-id="e7444-133">The company must be set to **DEMF**.</span></span>

- <span data-ttu-id="e7444-134">Kövesse a témakör [1. függelékének](#appendix1) lépéseit a Microsoft ER-megoldás szállítói kifizetések feldolgozásához szükséges összetevőinek letöltéséhez.</span><span class="sxs-lookup"><span data-stu-id="e7444-134">Follow the steps in [Appendix 1](#appendix1) of this topic to download the components of the Microsoft ER solution that are required to process vendor payments.</span></span>
- <span data-ttu-id="e7444-135">Kövesse a témakör [2. függelékének](#appendix2) lépéseit a szállítói kifizetések feldolgozásához szükséges Kötelezettségek előkészítéséhez az Ön által letöltött ER-megoldás segítségével.</span><span class="sxs-lookup"><span data-stu-id="e7444-135">Follow the steps in [Appendix 2](#appendix2) of this topic to prepare Accounts payable for vendor payment processing by using the ER solution that you will download.</span></span>

## <a name="process-a-vendor-payment-to-get-a-payment-file"></a><span data-ttu-id="e7444-136">Szállítói kifizetések feldolgozása kifizetési fájl beszerzéséhez</span><span class="sxs-lookup"><span data-stu-id="e7444-136">Process a vendor payment to get a payment file</span></span>

1. <span data-ttu-id="e7444-137">A szállítói kifizetések feldolgozásához kövesse a témakör [3. függelékének](#appendix3) lépéseit.</span><span class="sxs-lookup"><span data-stu-id="e7444-137">Follow the steps in [Appendix 3](#appendix3) of this topic to process vendor payments.</span></span>

    ![Szállítói kifizetések feldolgozása folyamatban](./media/er-data-debugger-process-payment.png)

2. <span data-ttu-id="e7444-139">Töltse le és mentse a zip-fájlt a helyi számítógépére.</span><span class="sxs-lookup"><span data-stu-id="e7444-139">Download and save the zip file to your local computer.</span></span>
3. <span data-ttu-id="e7444-140">Bontsa ki az **ISO20022 Credit transfer.xml** fizetési fájlt a zip-fájlból.</span><span class="sxs-lookup"><span data-stu-id="e7444-140">Extract the **ISO20022 Credit transfer.xml** payment file from the zip file.</span></span>
4. <span data-ttu-id="e7444-141">A kibontott kifizetési fájlt nyissa meg az XML-fájlmegjelenítő segítségével.</span><span class="sxs-lookup"><span data-stu-id="e7444-141">Open the extracted payment file by using the XML file viewer.</span></span>

    <span data-ttu-id="e7444-142">A fizetési fájlban a szállító bankszámlájának nemzetközi bankszámlaszám-kódja (IBAN) nem tartalmaz szóközöket.</span><span class="sxs-lookup"><span data-stu-id="e7444-142">In the payment file, the International Bank Account Number (IBAN) code of the vendor bank account contains no spaces.</span></span> <span data-ttu-id="e7444-143">Ennek megfelelően különbözik a **Bankszámlák** lapon [megadott](#enteredIBANcode) értéktől.</span><span class="sxs-lookup"><span data-stu-id="e7444-143">Therefore, it differs from the value that was [entered](#enteredIBANcode) on the **Bank accounts** page.</span></span>

    ![IBAN-kód szóközök nélkül](./media/er-data-debugger-payment-file.png)

    <span data-ttu-id="e7444-145">Az ER adatforrás-hibakeresővel megtudhatja, hogy a rendszer melyik összetevőjét használja az IBAN-kód szóközeinek törlésére.</span><span class="sxs-lookup"><span data-stu-id="e7444-145">You can use the ER data source debugger to learn which component of the ER solution is used to truncate spaces in the IBAN code.</span></span>

## <a name="turn-on-data-source-debugging"></a><span data-ttu-id="e7444-146">Adatforrás hibakeresésének bekapcsolása</span><span class="sxs-lookup"><span data-stu-id="e7444-146">Turn on data source debugging</span></span>

1. <span data-ttu-id="e7444-147">Nyissa meg a következőt: **Szervezeti adminisztráció** \> **Elektronikus jelentéskészítés** \> **Konfigurációk**.</span><span class="sxs-lookup"><span data-stu-id="e7444-147">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="e7444-148">A **Konfigurációk** oldal műveleti ablaktábláján, a **Konfigurációk** lapon, a **Speciális beállítások** csoportban válassza a **Felhasználói paraméterek** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="e7444-148">On the **Configurations** page, on the Action Pane, on the **Configurations** tab, in the **Advanced settings** group, select **User parameters**.</span></span>
3. <span data-ttu-id="e7444-149">Az **Adatok hibakeresésének engedélyezése a formátum futtatása során** lehetőséget állítsa **Igen** értékre.</span><span class="sxs-lookup"><span data-stu-id="e7444-149">Set the **Enable data debugging at format run** option to **Yes**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e7444-150">Ez a paraméter a felhasználó- és a vállalatspecifikus.</span><span class="sxs-lookup"><span data-stu-id="e7444-150">This parameter is user-specific and company-specific.</span></span>

    ![A Felhasználói paraméterek párbeszédablak](./media/er-data-debugger-user-parameters.png)

## <a name="process-a-vendor-payment-for-debugging"></a><span data-ttu-id="e7444-152">Szállítói fizetés feldolgozása hibakereséshez</span><span class="sxs-lookup"><span data-stu-id="e7444-152">Process a vendor payment for debugging</span></span>

1. <span data-ttu-id="e7444-153">A szállítói kifizetések feldolgozásához kövesse a témakör [3. függelékének](#appendix3) lépéseit.</span><span class="sxs-lookup"><span data-stu-id="e7444-153">Follow the steps in [Appendix 3](#appendix3) of this topic to process vendor payments.</span></span>
2. <span data-ttu-id="e7444-154">Az üzenetablakban válassza az **Igen** lehetőséget annak megerősítéséhez, hogy szeretné megszakítani a szállítói kifizetések feldolgozását, és ehelyett elindítani az adatforrás hibakeresését az **Adatforrások hibakeresése** oldalon.</span><span class="sxs-lookup"><span data-stu-id="e7444-154">In the message box, select **Yes** to confirm that you want to interrupt vendor payment processing and instead start data source debugging on the **Debug Datasources** page.</span></span>

    ![Megerősítő üzenet mezője](./media/er-data-debugger-start-debugging.png)

## <a name="debug-data-sources-that-are-used-in-payment-processing"></a><span data-ttu-id="e7444-156">A fizetés feldolgozásakor használt adatforrások hibakeresése</span><span class="sxs-lookup"><span data-stu-id="e7444-156">Debug data sources that are used in payment processing</span></span>

### <a name="debug-the-model-mapping"></a><span data-ttu-id="e7444-157">A modell-leképezés hibakeresése</span><span class="sxs-lookup"><span data-stu-id="e7444-157">Debug the model mapping</span></span>

1. <span data-ttu-id="e7444-158">A Műveleti panel **Adatforrások hibakeresése** válassza ki a **Modell-leképezés** lehetőséget a hibakeresés elindításához ebből az ER-összetevőből.</span><span class="sxs-lookup"><span data-stu-id="e7444-158">On the **Debug Datasources** page, on the Action Pane, select **Model mapping** to start to debug from this ER component.</span></span>
2. <span data-ttu-id="e7444-159">A bal oldali adatforrás ablaktáblán válassza ki a **\$notSentTransactions** adatforrást, majd válassza az **Összes rekord beolvasása** parancsot.</span><span class="sxs-lookup"><span data-stu-id="e7444-159">In the data source pane on the left, select the **\$notSentTransactions** data source, and then select **Read all records**.</span></span>

    <span data-ttu-id="e7444-160">Kiválaszthatja az **1 rekord beolvasása**, a **10 rekord beolvasása**, **100 rekord beolvasása** illetve az **Összes rekord beolvasása** a kiválasztott adatforrás megfelelő számú rekordja beolvasásának a kényszerítéséhez.</span><span class="sxs-lookup"><span data-stu-id="e7444-160">You can select **Read 1 record**, **Read 10 records**, **Read 100 records**, or **Read all records** to force the appropriate number of records to be read from the selected data source.</span></span> <span data-ttu-id="e7444-161">Ily módon szimulálható az adatforrás elérése a futó ER-formátumból.</span><span class="sxs-lookup"><span data-stu-id="e7444-161">In this way, you can simulate access to the data source from the running ER format.</span></span>

3. <span data-ttu-id="e7444-162">A jobb oldali adatpanelen válassza az **Összes kibontása** elemet.</span><span class="sxs-lookup"><span data-stu-id="e7444-162">In the data pane on the right, select **Expand all**.</span></span>

    <span data-ttu-id="e7444-163">Láthatja, hogy a **Rekordlista** típusú adatforrás egyetlen rekordot tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="e7444-163">You can see that the selected data source of the **Record list** type contains a single record.</span></span>

4. <span data-ttu-id="e7444-164">Bontsa ki a **\$notSentTransactions** adatforrást, és válassza ki a beágyazott **vendBankAccountInTransactionCompany ()** metódust.</span><span class="sxs-lookup"><span data-stu-id="e7444-164">Expand the **\$notSentTransactions** data source, and select the nested **vendBankAccountInTransactionCompany()** method.</span></span>
5. <span data-ttu-id="e7444-165">Bontsa ki a **vendBankAccountInTransactionCompany()** metódust, és válassza ki a beágyazott **IBAN** mezőt.</span><span class="sxs-lookup"><span data-stu-id="e7444-165">Expand the **vendBankAccountInTransactionCompany()** method, and select the nested **IBAN** field.</span></span>
6. <span data-ttu-id="e7444-166">Válassza ki az **Érték beolvasása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="e7444-166">Select **Get value**.</span></span>

    <span data-ttu-id="e7444-167">Az **Érték beolvasása** lehetőség kiválasztásával kényszerítheti a kiválasztott adatforrás kiválasztott mezőjének értékének beolvasását.</span><span class="sxs-lookup"><span data-stu-id="e7444-167">You can select **Get value** to force the value of a selected field of the selected data source to be read.</span></span> <span data-ttu-id="e7444-168">Ily módon szimulálható ezen mező elérése a futó ER-formátumból.</span><span class="sxs-lookup"><span data-stu-id="e7444-168">In this way, you can simulate access to this field from the running ER format.</span></span>

7. <span data-ttu-id="e7444-169">Válassza az **Összes kibontása** elemet.</span><span class="sxs-lookup"><span data-stu-id="e7444-169">Select **Expand all**.</span></span>

    ![Az IBAN-mező értéke a modell-leképezésben](./media/er-data-debugger-debugging-model-mapping.png)

    <span data-ttu-id="e7444-171">Látható, hogy a modell-leképezés nem felelős a levágott szóközökért, mivel a szállítói bankszámlához visszaküldött IBAN-kód szóközöket tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="e7444-171">As you can see, the model mapping isn't responsible for the truncated spaces, because the IBAN code that it returns for the vendor bank account includes spaces.</span></span> <span data-ttu-id="e7444-172">Ennek megfelelően folytatnia kell az adatforrás hibakeresését.</span><span class="sxs-lookup"><span data-stu-id="e7444-172">Therefore, you must continue data source debugging.</span></span>

### <a name="debug-the-format-mapping"></a><span data-ttu-id="e7444-173">A Formátum-leképezés hibakeresése</span><span class="sxs-lookup"><span data-stu-id="e7444-173">Debug the format mapping</span></span>

1. <span data-ttu-id="e7444-174">A Műveleti panel **Adatforrások hibakeresése** lapján válassza ki a **Formátumleképezés** lehetőséget a hibakeresés folytatásához ebből az ER-összetevőből.</span><span class="sxs-lookup"><span data-stu-id="e7444-174">On the **Debug Datasources** page, on the Action Pane, select **Format mapping** to continue to debug from this ER component.</span></span>
2. <span data-ttu-id="e7444-175">Válassza ki a **\$PaymentByDebtor** adatforrást, majd válassza az **Összes rekord beolvasása** parancsot.</span><span class="sxs-lookup"><span data-stu-id="e7444-175">Select the **\$PaymentByDebtor** data source, and then select **Read all records**.</span></span>
3. <span data-ttu-id="e7444-176">A **\$PaymentByDebtor** kibontása.</span><span class="sxs-lookup"><span data-stu-id="e7444-176">Expand **\$PaymentByDebtor**.</span></span>
4. <span data-ttu-id="e7444-177">Bontsa ki a **\$PaymentByDebtor.Lines** elemet, majd válassza az **Összes rekord beolvasása** parancsot.</span><span class="sxs-lookup"><span data-stu-id="e7444-177">Expand **\$PaymentByDebtor.Lines**, and then select **Read all records**.</span></span>
5. <span data-ttu-id="e7444-178">Bontsa ki a **\$PaymentByDebtor.Lines.CreditorAccount** elemet.</span><span class="sxs-lookup"><span data-stu-id="e7444-178">Expand **\$PaymentByDebtor.Lines.CreditorAccount**.</span></span>
6. <span data-ttu-id="e7444-179">Bontsa ki a **\$PaymentByDebtor.Lines.CreditorAccount.Identification**elemet, majd válassza a **\$PaymentByDebtor.Lines.CreditorAccount.Identification.IBAN** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="e7444-179">Expand **\$PaymentByDebtor.Lines.CreditorAccount.Identification**, and then select **\$PaymentByDebtor.Lines.CreditorAccount.Identification.IBAN**.</span></span>
7. <span data-ttu-id="e7444-180">Válassza ki az **Érték beolvasása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="e7444-180">Select **Get value**.</span></span>
8. <span data-ttu-id="e7444-181">Válassza az **Összes kibontása** elemet.</span><span class="sxs-lookup"><span data-stu-id="e7444-181">Select **Expand all**.</span></span>

    ![Az IBAN-mező értéke a formátumleképezésben](./media/er-data-debugger-debugging-format-mapping.png)

    <span data-ttu-id="e7444-183">Látható, hogy a formátumleképezés adatforrásai nem felelősek a levágott szóközökért, mivel a szállítói bankszámlához visszaküldött IBAN-kód szóközöket tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="e7444-183">As you can see, the data sources of the format mapping aren't responsible for the truncated spaces, because the IBAN code that they return for the vendor bank account includes spaces.</span></span> <span data-ttu-id="e7444-184">Ennek megfelelően folytatnia kell az adatforrás hibakeresését.</span><span class="sxs-lookup"><span data-stu-id="e7444-184">Therefore, you must continue data source debugging.</span></span>

### <a name="debug-the-format"></a><span data-ttu-id="e7444-185">A formátum hibakeresése</span><span class="sxs-lookup"><span data-stu-id="e7444-185">Debug the format</span></span>

1. <span data-ttu-id="e7444-186">A Műveleti panel **Adatforrások hibakeresése** lapján válassza ki a **Formátum** lehetőséget a hibakeresés folytatásához ebből az ER-összetevőből.</span><span class="sxs-lookup"><span data-stu-id="e7444-186">On the **Debug Datasources** page, on the Action Pane, select **Format** to continue to debug from this ER component.</span></span>
2. <span data-ttu-id="e7444-187">A formátumelemek kibontásával válassza ki az **ISO20022CTReports** \> **XMLHeader** \> **Document** \> **CstmrCdtTrfInitn** \> **PmtInf** elemet, majd válassza ki az **Összes rekord beolvasása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="e7444-187">Expand the format elements to select **ISO20022CTReports** \> **XMLHeader** \> **Document** \> **CstmrCdtTrfInitn** \> **PmtInf**, and then select **Read all records**.</span></span>
3. <span data-ttu-id="e7444-188">A formátumelemek kibontásával válassza ki az **ISO20022CTReports** \> **XMLHeader** \> **Document** \> **CstmrCdtTrfInitn** \> **PmtInf** \> **CdtTrfTxInf**, majd válassza az **Összes rekord beolvasása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="e7444-188">Expand the format elements to select **ISO20022CTReports** \> **XMLHeader** \> **Document** \> **CstmrCdtTrfInitn** \> **PmtInf** \> **CdtTrfTxInf**, and then select **Read all records**.</span></span>
4. <span data-ttu-id="e7444-189">A formátumelemek kibontásával válassza ki az **ISO20022CTReports** \> **XMLHeader** \> **Document** \> **CstmrCdtTrfInitn** \> **PmtInf** \> **CdtTrfTxInf** \> **CdtrAcct** \> **Id** \> **IBAN** \> **BankIBAN** elemeket, majd válassz az **Érték lekérése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="e7444-189">Expand the format elements to select **ISO20022CTReports** \> **XMLHeader** \> **Document** \> **CstmrCdtTrfInitn** \> **PmtInf** \> **CdtTrfTxInf** \> **CdtrAcct** \> **Id** \> **IBAN** \> **BankIBAN**, and then select **Get value**.</span></span>
5. <span data-ttu-id="e7444-190">Válassza az **Összes kibontása** elemet.</span><span class="sxs-lookup"><span data-stu-id="e7444-190">Select **Expand all**.</span></span>

    ![Az IBAN-mező értéke a formátumban](./media/er-data-debugger-debugging-format.png)

   <span data-ttu-id="e7444-192">Látható, hogy a formátumkapcsolás nem felelős a levágott szóközökért, mivel a szállítói bankszámlához visszaküldött IBAN-kód szóközöket tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="e7444-192">As you can see, the format binding isn't responsible for the truncated spaces because the IBAN code that it returns for the vendor bank account includes spaces.</span></span> <span data-ttu-id="e7444-193">Ennélfogva a **BankIBAN** elem úgy van beállítva, hogy olyan formátumátalakítást használjon, amely törli a szóközöket.</span><span class="sxs-lookup"><span data-stu-id="e7444-193">Therefore, the **BankIBAN** element is configured to use a format transformation that truncates spaces.</span></span>

6. <span data-ttu-id="e7444-194">Zárja be az adatforrás-hibakeresőt.</span><span class="sxs-lookup"><span data-stu-id="e7444-194">Close the data source debugger.</span></span>

### <a name="review-the-format-transformations"></a><span data-ttu-id="e7444-195">A formátum-átalakítások áttekintése</span><span class="sxs-lookup"><span data-stu-id="e7444-195">Review the format transformations</span></span>

1. <span data-ttu-id="e7444-196">Nyissa meg a következőt: **Szervezeti adminisztráció** \> **Elektronikus jelentéskészítés** \> **Konfigurációk**.</span><span class="sxs-lookup"><span data-stu-id="e7444-196">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="e7444-197">A **Konfigurációk** lapon válassza ki a **Kifizetési modell** \> **ISO20022 jóváírás-átutalás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="e7444-197">On the **Configurations** page, select **Payment model** \> **ISO20022 Credit transfer**.</span></span>
3. <span data-ttu-id="e7444-198">Válassza ki a **Tervezőt**, majd az elemelek kibontásával válassza ki a **Dokumentum** \> **CstmrCdtTrfInitn** \> **PmtInf** \> **CdtTrfTxInf** \> **CdtrAcct** \> **Id** \> **IBAN** \> **BankIBAN** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="e7444-198">Select **Designer**, and then expand the elements to select **Document** \> **CstmrCdtTrfInitn** \> **PmtInf** \> **CdtTrfTxInf** \> **CdtrAcct** \> **Id** \> **IBAN** \> **BankIBAN**.</span></span>

    ![A BankIBAN elem a Formátumtervező oldalon](./media/er-data-debugger-referred-transformation.png)

    <span data-ttu-id="e7444-200">Amint látható, a **BankIBAN** elem úgy van beállítva, hogy a **nem alfanumerikus elemek eltávolítása** átalakítást használja.</span><span class="sxs-lookup"><span data-stu-id="e7444-200">As you can see, the **BankIBAN** element is configured to use the **remove not alphanumeric** transformation.</span></span>

4. <span data-ttu-id="e7444-201">Válassza ki az **Átalakítások** lapot.</span><span class="sxs-lookup"><span data-stu-id="e7444-201">Select the **Transformations** tab.</span></span>

    ![A BankIBAN elem Átalakítások lapja](./media/er-data-debugger-transformation.png)

    <span data-ttu-id="e7444-203">Amint látható, a **nem alfanumerikus elemek eltávolítása** van beállítva, hogy olyan kifejezést használjon, amely eltávolítja a szóközöket a megadott karaktersorozatból.</span><span class="sxs-lookup"><span data-stu-id="e7444-203">As you can see, the **remove not alphanumeric** transformation is configured to use an expression that truncates spaces from the text string that is provided.</span></span>

## <a name="start-to-debug-in-the-operation-designer"></a><span data-ttu-id="e7444-204">Hibaelhárítás indítása a művelettervezőben</span><span class="sxs-lookup"><span data-stu-id="e7444-204">Start to debug in the Operation designer</span></span>

<span data-ttu-id="e7444-205">Ha olyan vázlatverziót konfigurál az ER-formátumból, amely közvetlenül a Művelettervezőből futtatható, akkor az adatforrás-hibakeresőt a Műveleti ablaktáblán a **Hibakeresés indítása** elem kiválasztásával érheti el.</span><span class="sxs-lookup"><span data-stu-id="e7444-205">When you configure a draft version of the ER format that can be run directly from the Operation designer, you can access the data source debugger by selecting **Start Debugging** on the Action Pane.</span></span>

![Hibakeresés indítása gomb a Formátumtervező oldalán](./media/er-data-debugger-run-from-designer.png)

<span data-ttu-id="e7444-207">A szerkesztés alatt álló ER formátum leképezési és fomrátum komponensei érhetők el a hibakereséshez.</span><span class="sxs-lookup"><span data-stu-id="e7444-207">The format mapping and format components of the ER format that is being edited are available for debugging.</span></span>

## <a name="start-to-debug-in-the-model-mapping-designer"></a><span data-ttu-id="e7444-208">Hibaelhárítás indítása a Modelleképezés-tervezőben</span><span class="sxs-lookup"><span data-stu-id="e7444-208">Start to debug in the Model mapping designer</span></span>

<span data-ttu-id="e7444-209">Ha olyan ER modell-leképezést konfigurál, amely a **Modell-leképezés** oldalról futtatható akkor az adatforrás-hibakeresőt a Műveleti ablaktáblán a **Hibakeresés indítása** elem kiválasztásával érheti el.</span><span class="sxs-lookup"><span data-stu-id="e7444-209">When you configure an ER model mapping that can be run from the **Model mapping** page, you can access the data source debugger by selecting **Start Debugging** on the Action Pane.</span></span>

![Hibakeresés indítása gomb a Modell-leképezés-tervező oldalán](./media/er-data-debugger-run-from-designer-mapping.png)

<span data-ttu-id="e7444-211">A szerkesztés alatt álló ER-leképezés modell-leképezési összetevője elérhető a hibakereséshez.</span><span class="sxs-lookup"><span data-stu-id="e7444-211">The model mapping component of the ER mapping that is being edited is available for debugging.</span></span>

## <a name="appendix-1-get-an-er-solution"></a><a name="appendix1"></a><span data-ttu-id="e7444-212">1. függelék: ER-megoldás lekérése</span><span class="sxs-lookup"><span data-stu-id="e7444-212">Appendix 1: Get an ER solution</span></span>

### <a name="download-an-er-solution"></a><span data-ttu-id="e7444-213">Egy ER-megoldás letöltése</span><span class="sxs-lookup"><span data-stu-id="e7444-213">Download an ER solution</span></span>

<span data-ttu-id="e7444-214">Ha ER-megoldást szeretne használni egy elektronikus fizetési fájl generálásához egy feldolgozás alatt álló szállítói kifizetéshez akkor [letöltheti](download-electronic-reporting-configuration-lcs.md) az **ISO20022 átutalás** ER fizetési formátumot, amely a Microsoft Dynamics Lifecycle Services (LCS) megosztott Közös eszközök könyvtárából vagy a Globális adattárból tölthető le.</span><span class="sxs-lookup"><span data-stu-id="e7444-214">If you want to use an ER solution to generate an electronic payment file for a vendor payment that is processed, you can [download](download-electronic-reporting-configuration-lcs.md) the **ISO20022 Credit transfer** ER payment format that is available from the Shared asset library in Microsoft Dynamics Lifecycle Services (LCS) or from the Global repository.</span></span>

![Az ER fizetési formátum importálása a Konfigurációk tárháza oldalon](./media/er-data-debugger-import-from-repo.png)

<span data-ttu-id="e7444-216">A kiválasztott ER-formátumon kívül a következő [konfigurációkat](general-electronic-reporting.md#Configuration) automatikusan importálni kell a Microsoft Dynamics 365 Finance példányba az **ISO20022-átutalás** ER-megoldás részeként:</span><span class="sxs-lookup"><span data-stu-id="e7444-216">In addition to the selected ER format, the following [configurations](general-electronic-reporting.md#Configuration) must be automatically imported into your Microsoft Dynamics 365 Finance instance as part of the **ISO20022 Credit transfer** ER solution:</span></span>

- <span data-ttu-id="e7444-217">**Fizetési modell** [ER adatmodellkonfiguráció](general-electronic-reporting.md#DataModelComponent)</span><span class="sxs-lookup"><span data-stu-id="e7444-217">**Payment model** [ER data model configuration](general-electronic-reporting.md#DataModelComponent)</span></span>
- <span data-ttu-id="e7444-218">**ISO20022 átutalás** [ER formátumkonfiguráció](general-electronic-reporting.md#FormatComponentOutbound)</span><span class="sxs-lookup"><span data-stu-id="e7444-218">**ISO20022 Credit transfer** [ER format configuration](general-electronic-reporting.md#FormatComponentOutbound)</span></span>
- <span data-ttu-id="e7444-219">**Fizetési modell hozzárendelése 1611** [ER modell leképezésének konfigurációja](general-electronic-reporting.md#ModelMappingComponent)</span><span class="sxs-lookup"><span data-stu-id="e7444-219">**Payment model mapping 1611** [ER model mapping configuration](general-electronic-reporting.md#ModelMappingComponent)</span></span>
- <span data-ttu-id="e7444-220">**Fizetési modell hozzárendelése célhelyhez ISO20022** ER modell leképezésének konfigurációja</span><span class="sxs-lookup"><span data-stu-id="e7444-220">**Payment model mapping to destination ISO20022** ER model mapping configuration</span></span>

<span data-ttu-id="e7444-221">Ezeket a konfigurációkat az ER keretrendszer **Konfiguráció** lapján lehet megtekinteni (**Szervezeti adminisztráció** \> **Elektronikus jelentéskészítés** \> **Konfigurációk**).</span><span class="sxs-lookup"><span data-stu-id="e7444-221">You can find these configurations on the **Configurations** page of the ER framework (**Organization administration** \> **Electronic reporting** \> **Configurations**).</span></span>

![A Konfigurációk oldalon importált konfigurációk](./media/er-data-debugger-configurations.png)

<span data-ttu-id="e7444-223">Ha a konfigurációs fából hiányzik a korábban felsorolt konfigurációk valamelyike, akkoe manuálisan le kell tölteni őket a LCS megosztott eszköz könyvtárából, ugyan úgy, ahogy letöltötte az **ISO20022 átutalás** ER fizetési formátumot.</span><span class="sxs-lookup"><span data-stu-id="e7444-223">If any of the previously listed configurations are missing in the configuration tree, you must manually download them from the LCS Shared asset library in the same way that you downloaded the **ISO20022 Credit transfer** ER payment format.</span></span>

### <a name="analyze-the-downloaded-er-solution"></a><span data-ttu-id="e7444-224">A letöltött ER-megoldás elemzése</span><span class="sxs-lookup"><span data-stu-id="e7444-224">Analyze the downloaded ER solution</span></span>

#### <a name="review-the-model-mapping"></a><span data-ttu-id="e7444-225">A modell-leképezés áttekintése</span><span class="sxs-lookup"><span data-stu-id="e7444-225">Review the model mapping</span></span>

1. <span data-ttu-id="e7444-226">Nyissa meg a következőt: **Szervezeti adminisztráció** \> **Elektronikus jelentéskészítés** \> **Konfigurációk**.</span><span class="sxs-lookup"><span data-stu-id="e7444-226">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="e7444-227">Válassza a **Fizetési modell** \> **Kifizetési modell leképezés 1611** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="e7444-227">Select **Payment model** \> **Payment model mapping 1611**.</span></span>
3. <span data-ttu-id="e7444-228">Válassza a **Tervező** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="e7444-228">Select **Designer**.</span></span>
4. <span data-ttu-id="e7444-229">Válassza ki a **Fizetési modell-leképezés ISO20022 CT** leképezésrekordot.</span><span class="sxs-lookup"><span data-stu-id="e7444-229">Select the **Payment model mapping ISO20022 CT** mapping record.</span></span>
5. <span data-ttu-id="e7444-230">Válassza ki a **Tervezőt** elemet, majd tekintse át a megnyitott modell-leképezést.</span><span class="sxs-lookup"><span data-stu-id="e7444-230">Select **Designer**, and then review the model mapping that is opened.</span></span>

    <span data-ttu-id="e7444-231">Figyelje meg, hogy az adatmodell **Fizetések** mezője a **\$notSentTransactions** adatforráshoz van kapcsolva, amely a feldolgozás alatt álló szállítói kifizetési sorok listáját adja vissza.</span><span class="sxs-lookup"><span data-stu-id="e7444-231">Notice that the **Payments** field of the data model is bound to the **\$notSentTransactions** data source that returns the list of vendor payment lines that are being processed.</span></span>

    ![Kifizetések mező a Modell-leképezés tervező lapján](./media/er-data-debugger-model-mapping.png)

#### <a name="review-the-format-mapping"></a><span data-ttu-id="e7444-233">A formátumleképezés áttekintése</span><span class="sxs-lookup"><span data-stu-id="e7444-233">Review the format mapping</span></span>

1. <span data-ttu-id="e7444-234">Nyissa meg a következőt: **Szervezeti adminisztráció** \> **Elektronikus jelentéskészítés** \> **Konfigurációk**.</span><span class="sxs-lookup"><span data-stu-id="e7444-234">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="e7444-235">Válassza ki a **Kifizetési modell** \> **ISO20022 átutalás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="e7444-235">Select **Payment model** \> **ISO20022 Credit transfer**.</span></span>
3. <span data-ttu-id="e7444-236">Válassza a **Tervező** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="e7444-236">Select **Designer**.</span></span>
4. <span data-ttu-id="e7444-237">A **Leképezés** lapon tekintse át a megnyitott formátumleképezést.</span><span class="sxs-lookup"><span data-stu-id="e7444-237">On the **Mapping** tab, review the format mapping that is opened.</span></span>

    <span data-ttu-id="e7444-238">Figyelje meg, hogy a **Dokumentum** \> **CstmrCdtTrfInitn** \> **PmtInf** eleme a **ISO20022CTReports** \> **XMLHeader** fájlnak a **\$PaymentByDebtor** adatforráshoz van kapcsolva, amely úgy van konfigurálva, hogy az adatmodell **Fizetések** mezőjének rekordjait csoportosítsa.</span><span class="sxs-lookup"><span data-stu-id="e7444-238">Notice that the **Document** \> **CstmrCdtTrfInitn** \> **PmtInf** element of the **ISO20022CTReports** \> **XMLHeader** file is bound to the **\$PaymentByDebtor** data source that is configured to group records of the data model's **Payments** field.</span></span>

    ![A PmtInf elem a Formátumtervező oldalon](./media/er-data-debugger-format-mapping.png)

#### <a name="review-the-format"></a><span data-ttu-id="e7444-240">A formátum áttekintése</span><span class="sxs-lookup"><span data-stu-id="e7444-240">Review the format</span></span>

1. <span data-ttu-id="e7444-241">Nyissa meg a következőt: **Szervezeti adminisztráció** \> **Elektronikus jelentéskészítés** \> **Konfigurációk**.</span><span class="sxs-lookup"><span data-stu-id="e7444-241">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="e7444-242">Válassza ki a **Kifizetési modell** \> **ISO20022 átutalás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="e7444-242">Select **Payment model** \> **ISO20022 Credit transfer**.</span></span>
3. <span data-ttu-id="e7444-243">Válassza ki a **Tervezőt** elemet, majd tekintse át a megnyitott formátumot.</span><span class="sxs-lookup"><span data-stu-id="e7444-243">Select **Designer**, and then review the format that is opened.</span></span>

    <span data-ttu-id="e7444-244">Figyelje meg, hogy a **Dokumentum** \> **CstmrCdtTrfInitn** \> **PmtInf** \> **CdtTrfTxInf** \> **CdtrAcct** \> **Id** \> **IBAN** \> **BankIBAN** alatt található formátumelem úgy van konfigurálva, hogy megadja a szállítói számla IBAN-kódját a fizetési fájlba.</span><span class="sxs-lookup"><span data-stu-id="e7444-244">Notice that the format element under **Document** \> **CstmrCdtTrfInitn** \> **PmtInf** \> **CdtTrfTxInf** \> **CdtrAcct** \> **Id** \> **IBAN** \> **BankIBAN** is configured to enter the IBAN code of the vendor account in the payment file.</span></span>

    ![A BankIBAN elem a Formátumtervező oldalon](./media/er-data-debugger-format.png)

## <a name="appendix-2-configure-accounts-payable"></a><a name="appendix2"></a><span data-ttu-id="e7444-246">2. melléklet: Kötelezettségek konfigurálása</span><span class="sxs-lookup"><span data-stu-id="e7444-246">Appendix 2: Configure Accounts payable</span></span>

### <a name="modify-a-vendor-property"></a><span data-ttu-id="e7444-247">Szállítói tulajdonság módosítása</span><span class="sxs-lookup"><span data-stu-id="e7444-247">Modify a vendor property</span></span>

1. <span data-ttu-id="e7444-248">Nyissa meg a következőt: **Kötelezettségek** \> **Szállítók** \> **Minden szállító**.</span><span class="sxs-lookup"><span data-stu-id="e7444-248">Go to **Accounts payable** \> **Vendors** \> **All vendors**.</span></span>
2. <span data-ttu-id="e7444-249">Válassza ki a **DE-01002** szállítót és ezt követően a Műveleti paneé **Szállító** lapján, a **Beállítás** csoportban válassza a **Bankszámlák** elemet.</span><span class="sxs-lookup"><span data-stu-id="e7444-249">Select vendor **DE-01002**, and then, on the Action Pane, on the **Vendor** tab, in the **Set up** group, select **Bank accounts**.</span></span>
3. <span data-ttu-id="e7444-250">Az **Azonosítás** gyorslap **IBAN** mezőjébe, <a name="enteredIBANcode"></a>írja be a **GB33 BUKB 2020 1555 5555 55** értéket.</span><span class="sxs-lookup"><span data-stu-id="e7444-250">On the **Identification** FastTab, in the **IBAN** field, <a name="enteredIBANcode"></a>enter **GB33 BUKB 2020 1555 5555 55**.</span></span>
4. <span data-ttu-id="e7444-251">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="e7444-251">Select **Save**.</span></span>

![IBAN mező beállítva a Szállítói bankszámlák lapon](./media/er-data-debugger-iban.png)

### <a name="set-up-a-method-of-payment"></a><span data-ttu-id="e7444-253">Egy fizetési mód beállítása</span><span class="sxs-lookup"><span data-stu-id="e7444-253">Set up a method of payment</span></span>

1. <span data-ttu-id="e7444-254">Nyissa meg a következőt: **Kötelezettségek** \> **Kifizetés beállítása** \> **Fizetési módok**.</span><span class="sxs-lookup"><span data-stu-id="e7444-254">Go to **Accounts payable** \> **Payment setup** \> **Methods of payment**.</span></span>
2. <span data-ttu-id="e7444-255">Válassza ki a **SEPA CT** fizetési módot.</span><span class="sxs-lookup"><span data-stu-id="e7444-255">Select the **SEPA CT** payment method.</span></span>
3. <span data-ttu-id="e7444-256">Állítsa a **Fájlformátumok** gyorslap **Fájlformátumok** szakaszán az **Általános elektronikus exportformátum** beállítását **Igen** értékre.</span><span class="sxs-lookup"><span data-stu-id="e7444-256">On the **File formats** FastTab, in the **File formats** section, set the **Generic electronic Export format** option to **Yes**.</span></span>
4. <span data-ttu-id="e7444-257">Az **Exportálási formátum konfigurálása** mezőben válassza ki az **ISO20022-átutalás** ER-formátumot.</span><span class="sxs-lookup"><span data-stu-id="e7444-257">In the **Export format configuration** field, select the **ISO20022 Credit transfer** ER format.</span></span>
5. <span data-ttu-id="e7444-258">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="e7444-258">Select **Save**.</span></span>

![Fájlformátum beállításai a Fizetési módok lapon](./media/er-data-debugger-payment-method.png)

### <a name="add-a-vendor-payment"></a><span data-ttu-id="e7444-260">Szállítói kifizetés hozzáadása</span><span class="sxs-lookup"><span data-stu-id="e7444-260">Add a vendor payment</span></span>

1. <span data-ttu-id="e7444-261">Ugorjon a **Kötelezettségek** \> **Fizetések** \> **Szállítói kifizetés naplója** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="e7444-261">Go to **Accounts payable** \> **Payments** \> **Vendor payment journal**.</span></span>
2. <span data-ttu-id="e7444-262">Adjon hozzá egy új kifizetési naplót.</span><span class="sxs-lookup"><span data-stu-id="e7444-262">Add a new payment journal.</span></span>
3. <span data-ttu-id="e7444-263">Válassza ki a **Sorok** lehetőséget, és adjon hozzá egy új fizetési sort.</span><span class="sxs-lookup"><span data-stu-id="e7444-263">Select **Lines**, and add a new payment line.</span></span>
4. <span data-ttu-id="e7444-264">Válassza a **DE-01002** szállítót a **Számla** mezőben.</span><span class="sxs-lookup"><span data-stu-id="e7444-264">In the **Account** field, select vendor **DE-01002**.</span></span>
5. <span data-ttu-id="e7444-265">Adjon meg egy értéket a **Terhelés** mezőben.</span><span class="sxs-lookup"><span data-stu-id="e7444-265">In the **Debit** field, enter a value.</span></span>
6. <span data-ttu-id="e7444-266">A **Fizetési mód** mezőben válassza a **SEPA CT** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="e7444-266">In the **Method of payment** field, select **SEPA CT**.</span></span>
7. <span data-ttu-id="e7444-267">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="e7444-267">Select **Save**.</span></span>

![A szállítói kifizetés hozzáadva a Szállítói fizetések lapon](./media/er-data-debugger-payment-journal.png)

## <a name="appendix-3-process-a-vendor-payment"></a><a name="appendix3"></a><span data-ttu-id="e7444-269">3. melléklet: Egy szállítói fizetés feldolgozása</span><span class="sxs-lookup"><span data-stu-id="e7444-269">Appendix 3: Process a vendor payment</span></span>

1. <span data-ttu-id="e7444-270">Ugorjon a **Kötelezettségek** \> **Fizetések** \> **Szállítói kifizetés naplója** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="e7444-270">Go to **Accounts payable** \> **Payments** \> **Vendor payment journal**.</span></span>
2. <span data-ttu-id="e7444-271">A **Szállítói fizetési napló** lapon válassza ki a korábban létrehozott fizetési naplót, majd válassza ki a **Sorok** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="e7444-271">On the **Vendor payment journal** page, select the payment journal that you previously created, and then select **Lines**.</span></span>
3. <span data-ttu-id="e7444-272">Válassza ki a kifizetési sort, majd válassza a **Kifizetési állapota** \> **Nincs** elemet.</span><span class="sxs-lookup"><span data-stu-id="e7444-272">Select the payment line, and then select **Payment status** \> **None**.</span></span>
4. <span data-ttu-id="e7444-273">**Kifizetések létrehozása** kiválasztása.</span><span class="sxs-lookup"><span data-stu-id="e7444-273">Select **Generate payments**.</span></span>
5. <span data-ttu-id="e7444-274">A **Fizetési mód** mezőben válassza a **SEPA CT** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="e7444-274">In the **Method of payment** field, select **SEPA CT**.</span></span>
6. <span data-ttu-id="e7444-275">A **Bankszámla** mezőben válassza a **DEMF OPER** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="e7444-275">In the **Bank account** field, select **DEMF OPER**.</span></span>
7. <span data-ttu-id="e7444-276">A **Kifizetések létrehozása** párbeszédpanelen válassza az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="e7444-276">In the **Generate payments** dialog box, select **OK**.</span></span>
8. <span data-ttu-id="e7444-277">Az **Elektronikus jelentési paraméterek** párbeszédablakban válassza az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="e7444-277">In the **Electronic report parameters** dialog box, select **OK**.</span></span>
