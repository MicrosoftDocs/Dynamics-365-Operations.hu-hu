---
title: "Raktár beállítása a raktári konfigurációs sablon segítségével"
description: "Ez a témakör bemutatja, hogyan lehetséges egy raktár beállítása a raktári konfigurációs sablon segítségével."
author: perlynne
manager: AnnBe
ms.date: 11/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: DataManagementWorkspace, DMFQuickImportExportEnhanced, DMFDefinitionGroupTemplate, DMFEntityTemplateDefinitionLoadDialog
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2017-12-31
ms.dyn365.ops.version: 7.3
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: d2177ddaff8ff6dcef106a008842149c381c00db
ms.contentlocale: hu-hu
ms.lasthandoff: 04/13/2018

---

# <a name="set-up-a-warehouse-by-using-a-warehouse-configuration-template"></a><span data-ttu-id="75032-103">Raktár beállítása a raktári konfigurációs sablon segítségével</span><span class="sxs-lookup"><span data-stu-id="75032-103">Set up a warehouse by using a warehouse configuration template</span></span>

[!INCLUDE [banner](../includes/banner.md)]

<span data-ttu-id="75032-104">Ez a témakör bemutatja, hogyan lehetséges egy raktár beállítása a raktári konfigurációs sablon segítségével.</span><span class="sxs-lookup"><span data-stu-id="75032-104">This topic explains how to set up a warehouse by using a warehouse configuration template.</span></span> <span data-ttu-id="75032-105">Számos előre definiált konfigurációs sablont használhat.</span><span class="sxs-lookup"><span data-stu-id="75032-105">There are several predefined configuration templates that you can use.</span></span> <span data-ttu-id="75032-106">Ha tájékoztatást szeretne ezen sablonok használatáról, lásd a [Konfigurációs adatsablonok](../../dev-itpro/data-entities/configuration-data-templates.md) című részt.</span><span class="sxs-lookup"><span data-stu-id="75032-106">For information about how to use these templates, see [Configuration data templates](../../dev-itpro/data-entities/configuration-data-templates.md).</span></span>

## <a name="scenarios-where-configuration-templates-can-be-helpful"></a><span data-ttu-id="75032-107">Esetek, amikor a konfigurációs sablonok hasznosak lehetnek</span><span class="sxs-lookup"><span data-stu-id="75032-107">Scenarios where configuration templates can be helpful</span></span>

<span data-ttu-id="75032-108">A konfigurációs sablonok számos helyzetben hasznosak lehetnek.</span><span class="sxs-lookup"><span data-stu-id="75032-108">Configuration templates can be helpful in many scenarios.</span></span> <span data-ttu-id="75032-109">Íme néhány példa:</span><span class="sxs-lookup"><span data-stu-id="75032-109">Here are some examples:</span></span>

- <span data-ttu-id="75032-110">Már befejezte és tesztelte a konfigurációs beállításokat tesztkörnyezetben, és most szeretné átmásolni a beállítást az éles környezetbe is.</span><span class="sxs-lookup"><span data-stu-id="75032-110">You've completed and tested a configuration setup in a test environment, and you now want to copy the setup to a production environment.</span></span>
- <span data-ttu-id="75032-111">Be szeretné vezetni a raktárbeállításokat több jogi személynél, illetve új raktárat szeretne létrehozni ugyanannál a jogi személynél.</span><span class="sxs-lookup"><span data-stu-id="75032-111">You want to roll the warehouse setup out to several legal entities or create a new warehouse in the same legal entity.</span></span>
- <span data-ttu-id="75032-112">Szeretne gyorsan felkészülni a raktárfunkciók bemutatójára.</span><span class="sxs-lookup"><span data-stu-id="75032-112">You want to quickly prepare for a demo of the warehouse functionality.</span></span>
- <span data-ttu-id="75032-113">Azt szeretné, hogy a meglévő elemek és raktárak a Raktárkezelésben használják a funkciót a Készletkezelés modul funkciója helyett.</span><span class="sxs-lookup"><span data-stu-id="75032-113">You want existing items and warehouses to use the functionality in Warehouse management instead of the functionality in Inventory management.</span></span>

<span data-ttu-id="75032-114">Ez a témakör az első esetre fókuszál.</span><span class="sxs-lookup"><span data-stu-id="75032-114">This topic focuses on the first of these scenarios.</span></span> <span data-ttu-id="75032-115">Megmutatja, hogyan használhat konfigurációs sablont egy konfigurációs beállítás tesztkörnyezetből éles környezetbe való másolására.</span><span class="sxs-lookup"><span data-stu-id="75032-115">It shows how you can use a configuration template to copy a configuration setup from a test environment to a production environment.</span></span>

## <a name="copy-a-configuration-setup-from-a-test-environment-to-a-production-environment"></a><span data-ttu-id="75032-116">Konfigurációs beállítás átmásolása egy tesztkörnyezetből egy éles környezetbe</span><span class="sxs-lookup"><span data-stu-id="75032-116">Copy a configuration setup from a test environment to a production environment</span></span>

<span data-ttu-id="75032-117">Ebben az esetben a raktár konfigurációs beállításai és egyes tranzakciós folyamatok már léteznek egy tesztkörnyezetben.</span><span class="sxs-lookup"><span data-stu-id="75032-117">For this scenario, the configuration setup for a warehouse and some transaction processes already exist in a test environment.</span></span> <span data-ttu-id="75032-118">Át szeretné másolni a raktárra vonatokozó konfigurációs beállításokat a tesztkörnyezetből az éles környezetbe.</span><span class="sxs-lookup"><span data-stu-id="75032-118">You now want to copy the configuration setup for the warehouse from the test environment to a production environment.</span></span>

> [!NOTE]
> <span data-ttu-id="75032-119">Fontos, hogy a további kapcsolódó beállítási adatot is szerepeltesse akkor, amikor egy konfigurációs beállítást másol.</span><span class="sxs-lookup"><span data-stu-id="75032-119">It's important that you include other related setup data when you copy a configuration setup.</span></span> <span data-ttu-id="75032-120">A termékek beállításakor például át kell másolnia a beállításokat egy tesztkörnyezetből.</span><span class="sxs-lookup"><span data-stu-id="75032-120">For example, you want to set up products by copying the setup from a test environment.</span></span> <span data-ttu-id="75032-121">Azonban nem állíthat be rögzített kitárolási helyet a termék számára a termék létrehozása előtt.</span><span class="sxs-lookup"><span data-stu-id="75032-121">However, you can't set up a fixed picking location for a product before that product is created.</span></span> <span data-ttu-id="75032-122">Annak ellenére, hogy az egyes konfigurációs sablonok nem támogatják az ilyen típusú függőséget, vannak olyan alapértelmezett adatsablonok, amelyek igen.</span><span class="sxs-lookup"><span data-stu-id="75032-122">Although individual configuration templates don't support this type of dependency, there are default data templates that support it.</span></span> <span data-ttu-id="75032-123">Ezeket az alapértelmezett adatsablonokat egyszerűen szerepeltetheti egy konfigurálási folyamatban.</span><span class="sxs-lookup"><span data-stu-id="75032-123">You can easily include these default data templates in a configuration process.</span></span>

### <a name="export-a-default-warehouse-template"></a><span data-ttu-id="75032-124">Alapértelmezett raktársablon exportálása</span><span class="sxs-lookup"><span data-stu-id="75032-124">Export a default warehouse template</span></span> 

1. <span data-ttu-id="75032-125">Nyissa meg az **Adatkezelés** munkaterületet.</span><span class="sxs-lookup"><span data-stu-id="75032-125">Open the **Data management** workspace.</span></span>

    > [!NOTE]
    > <span data-ttu-id="75032-126">A munkaterület első használatakor be kell töltenie az összes adatentitást a folytatáshoz.</span><span class="sxs-lookup"><span data-stu-id="75032-126">If you're using this workspace for the first time, you must load all the data entities before you continue.</span></span>

2. <span data-ttu-id="75032-127">Válassza ki a **Sablonok** mozaikot, majd az **Alapértelmezett sablonok betöltése** lehetőséget az alapértelmezett sablonok betöltéséhez.</span><span class="sxs-lookup"><span data-stu-id="75032-127">Select the **Templates** tile, and then select **Load default templates** to load the default templates.</span></span>

    > [!NOTE]
    > <span data-ttu-id="75032-128">Az **Alapértelmezett sablonok betöltése** lehetőség csak a **Bővített** nézetben áll rendelkezésre.</span><span class="sxs-lookup"><span data-stu-id="75032-128">**Load default templates** is available only in the **Enhanced** view.</span></span> <span data-ttu-id="75032-129">Válassza ki a **Keretrendszer paraméterei** lehetőséget, majd az **Alapértelmezettek megtekintése** elemet, és válassza a **Bővített nézet** pontot.</span><span class="sxs-lookup"><span data-stu-id="75032-129">Select **Framework parameters**, and then, in the **View defaults** field, select **Enhanced view**.</span></span>

3. <span data-ttu-id="75032-130">Az alapértelmezett sablonok betöltése után módosíthatja őket, hogy megfeleljenek az üzleti követelményeinek.</span><span class="sxs-lookup"><span data-stu-id="75032-130">After the default templates are loaded, you can change them so that they meet your business requirements.</span></span>

    > [!NOTE]
    > <span data-ttu-id="75032-131">Alapértelmezett sablonok betöltéséhez és importálásához rendszergazdai hozzáféréssel kell rendelkeznie.</span><span class="sxs-lookup"><span data-stu-id="75032-131">To load default templates and import templates, you must have system administrator access.</span></span> <span data-ttu-id="75032-132">Ez a követelmény segít annak garantálásában, hogy minden entitás megfelelően betöltődjön a sablonba.</span><span class="sxs-lookup"><span data-stu-id="75032-132">This requirement helps guarantee that all entities are correctly loaded into the template.</span></span>

4. <span data-ttu-id="75032-133">Győződjön meg arról, hogy annál a jogi személynál van, amelyből szeretné exportálni a vállalatspecifikus adatokat.</span><span class="sxs-lookup"><span data-stu-id="75032-133">Make sure that you're in the legal entity that you want to export the company-specific data from.</span></span>
5. <span data-ttu-id="75032-134">A munkaterületen válassza az **Exportálás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="75032-134">In the workspace, select **Export**.</span></span>
6. <span data-ttu-id="75032-135">Hozzon létre egy új exportálási projektet.</span><span class="sxs-lookup"><span data-stu-id="75032-135">Create a new export project.</span></span>
7. <span data-ttu-id="75032-136">Válassza a **+ Sablon hozzáadása** lehetőséget, és keresse ki a **400 - WMS** alapértelmezett raktári sablont.</span><span class="sxs-lookup"><span data-stu-id="75032-136">Select **+ Add template**, and find the **400 - WMS** default warehouse template.</span></span> <span data-ttu-id="75032-137">Ez a sablon adatentitásokat ad a raktári konfigurációhoz.</span><span class="sxs-lookup"><span data-stu-id="75032-137">This template adds data entities for warehouse configuration.</span></span>

    > [!NOTE]
    > <span data-ttu-id="75032-138">Ha szűrni kell az exportálás alatt lévő adatokat (például csak az adott raktárhoz kapcsolódó adatokat szeretné átmásolni), akkor ki kell értékelnie minden egyes adatentitást, és hozzá kell adnia a szűrést egy lekérdezés útján.</span><span class="sxs-lookup"><span data-stu-id="75032-138">If the data that you're exporting must be filtered (for example, you want to export only the data that is related to a specific warehouse), you must evaluate each data entity and add filtering via a query.</span></span> <span data-ttu-id="75032-139">Azt is megteheti, hogy exportálja az összes adatot, majd törli azokat a rekordokat, amelyek nem szükségesek célfájlokban.</span><span class="sxs-lookup"><span data-stu-id="75032-139">Alternatively, you can export all data and then delete the records that aren't required in the destination files.</span></span>

8. <span data-ttu-id="75032-140">Válassza az **Exportálás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="75032-140">Select **Export**.</span></span> <span data-ttu-id="75032-141">A projekt összes adatentitásához kapcsolódó adatokat exportálja a rendszer.</span><span class="sxs-lookup"><span data-stu-id="75032-141">Data that is related to all the data entities in the project is exported.</span></span>

<span data-ttu-id="75032-142">Az adatcsomag zip-fájlját letöltheti.</span><span class="sxs-lookup"><span data-stu-id="75032-142">You can download a zip file for the data package.</span></span> <span data-ttu-id="75032-143">Ez a fájl minden adatot a kijelölt formátumban (például Excel-formátumban) tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="75032-143">This file contains all the data in the selected format (for example, Excel format).</span></span> <span data-ttu-id="75032-144">Ahogyan említettük, előfordulhat, hogy az adatcsomagfájlok egyes rekordjait frissíteni kell, hogy importálhassa őket az éles környezetbe.</span><span class="sxs-lookup"><span data-stu-id="75032-144">As has been mentioned, some records in the data package files might have to be updated before you can import them into the production environment.</span></span> <span data-ttu-id="75032-145">Rekord frissítése során győződjön meg arról, hogy nem módosítja a fájl nevét.</span><span class="sxs-lookup"><span data-stu-id="75032-145">If you update a record, make sure that you don't change the file name.</span></span>

### <a name="import-a-warehouse-configuration-setup"></a><span data-ttu-id="75032-146">Raktári konfiguráció beállításának importálása</span><span class="sxs-lookup"><span data-stu-id="75032-146">Import a warehouse configuration setup</span></span>

1. <span data-ttu-id="75032-147">A cél környezetben győződjön meg róla, hogy annál a vállalatnál van, amelybe a raktár adatait importálni szeretné.</span><span class="sxs-lookup"><span data-stu-id="75032-147">In the destination environment, make sure that you're in the company that you want to import the warehouse data into.</span></span>

    > [!NOTE]
    > <span data-ttu-id="75032-148">Az importálást megelőzően meg kell határoznia minden esetleges adatfüggőséget.</span><span class="sxs-lookup"><span data-stu-id="75032-148">Before you do the import, you should identify any data dependencies.</span></span> <span data-ttu-id="75032-149">A **Raktárkezelés** sablon például tartalmaz egy **Raktári intézkedéskódok** nevű adatentitást.</span><span class="sxs-lookup"><span data-stu-id="75032-149">For example, the **Warehouse management** template includes a data entity that is named **Warehouse disposition codes**.</span></span> <span data-ttu-id="75032-150">Ez az entitás olyan adatokat tartalmaz, amelyek az **Intézkedési kódok** beállító oldalához kapcsolódnak (**Raktárkezelés** > **Beállítás** > **Mobileszköz** > **Intézkedési kódok**).</span><span class="sxs-lookup"><span data-stu-id="75032-150">This entity contains data that is related to the **Disposition codes** setup page (**Warehouse management** > **Setup** > **Mobile device** > **Disposition codes**).</span></span> <span data-ttu-id="75032-151">Ha már egy korábbi beállítás kezeli a visszáru feldolgozását az értékesítési rendeléseknél, akkor a **Visszáru intézkedési kódja** mező értéket tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="75032-151">If an existing setup already handles the return process for sales orders, the **Return disposition code** field contains a value.</span></span> <span data-ttu-id="75032-152">Az ebben a mezőben szereplő intézkedési kód az **Intézkedési kód** adatentitáshoz kapcsolódik, amely része az **Értékesítés és marketing** sablonnak.</span><span class="sxs-lookup"><span data-stu-id="75032-152">The disposition code in this field is related to the **Disposition code** data entity, which is part of the **Sales and marketing** template.</span></span> <span data-ttu-id="75032-153">Ha az **Intézkedési kód** adatentitás adatai nincsenek importálva a **Raktári intézkedési kódok** mező előtt, akkor az importálás sikertelen lesz.</span><span class="sxs-lookup"><span data-stu-id="75032-153">If the data from the **Disposition code** data entity isn't imported before the data from the **Warehouse disposition codes** field, the import will fail.</span></span>

2. <span data-ttu-id="75032-154">Az **Adatkezelés** munkaterületen válassza az **Importálás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="75032-154">In the **Data management** workspace, select **Import**.</span></span>
3. <span data-ttu-id="75032-155">Hozzon létre egy új importálási projektet.</span><span class="sxs-lookup"><span data-stu-id="75032-155">Create a new import project.</span></span>
4. <span data-ttu-id="75032-156">Válassza a **+ Fájl hozzáadása** lehetőséget, majd töltse fel az adatcsomag zip-fájlját.</span><span class="sxs-lookup"><span data-stu-id="75032-156">Select **+ Add file**, and upload the zip file for the data package.</span></span>
5. <span data-ttu-id="75032-157">Válassza az **Importálás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="75032-157">Select **Import**.</span></span> <span data-ttu-id="75032-158">Aa **Bővített** nézetben a **Szűrő** beállítással gyorsan áttekintheti az importálás során esetlegesen előforduló hibákat.</span><span class="sxs-lookup"><span data-stu-id="75032-158">In the **Enhanced** view, you can use the **Filter** option to quickly get an overview of issues that might occur during the import.</span></span>

<span data-ttu-id="75032-159">A **Végrehajtás megtekintése** napló részletes információt nyújt minden egyes importált adatentitásról.</span><span class="sxs-lookup"><span data-stu-id="75032-159">The **View execution** log provides detailed information about each data entity that is imported.</span></span> <span data-ttu-id="75032-160">Az előkészítési adatok nézetének segítségével gyorsan megtekintheti a céladatokat.</span><span class="sxs-lookup"><span data-stu-id="75032-160">You can use the staging data view to quickly get to the target data.</span></span> <span data-ttu-id="75032-161">Ezzel a módszerrel megnézheti, hogy néznek ki az importált adatok a kapcsolódó lapokon az alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="75032-161">In this way, you can see what the imported data looks like on the related pages in the application.</span></span> <span data-ttu-id="75032-162">Az alapértelmezett adatsablonok használata esetén az egyes adatentitások importálási sorrendje az előre meghatározott módon történik annak biztosítása érdekében, hogy először az összes függő adat importálása történjen meg.</span><span class="sxs-lookup"><span data-stu-id="75032-162">When you use the default data templates, the import sequence for each data entity works in the predefined manner, to help guarantee that all dependent data is imported first.</span></span> <span data-ttu-id="75032-163">Ha egyéni adatentitások is a projekt részét képezik, gondoskodnia kell arról, hogy meg van adva a megfelelő sorrend.</span><span class="sxs-lookup"><span data-stu-id="75032-163">If custom data entities are part of the project, you must make sure that the correct sequence is defined.</span></span> <span data-ttu-id="75032-164">További tájékoztatás: [Konfigurációs adatsablonok](../../dev-itpro/data-entities/configuration-data-templates.md).</span><span class="sxs-lookup"><span data-stu-id="75032-164">For more information, see [Configuration data templates](../../dev-itpro/data-entities/configuration-data-templates.md).</span></span>

<span data-ttu-id="75032-165">Ha további információt szeretne arról, hogy miként használhatja a raktársablont egy raktárkonfiguráció adott vállalattól egy új vállalathoz való átmásolásához azonos példányban, nézze meg ezt a 3 perces videót a YouTube-on.</span><span class="sxs-lookup"><span data-stu-id="75032-165">To learn more about how to use warehouse template to copy the configuration of a warehouse from one company to a new company within the same instance, see this 3-minute video on YouTube.</span></span>

> [!Video https://www.youtube.com/embed/K2WIfFlqJYs]


## <a name="related-topic"></a><span data-ttu-id="75032-166">Kapcsolódó témakör</span><span class="sxs-lookup"><span data-stu-id="75032-166">Related topic</span></span>

[<span data-ttu-id="75032-167">Konfigurációs adatsablonok</span><span class="sxs-lookup"><span data-stu-id="75032-167">Configuration data templates</span></span>](../../dev-itpro/data-entities/configuration-data-templates.md)

