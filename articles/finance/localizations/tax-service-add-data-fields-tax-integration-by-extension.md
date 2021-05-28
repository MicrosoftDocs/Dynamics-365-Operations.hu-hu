---
title: Adatmezők hozzáadása az adóintegrációhoz bővítmények használatával
description: Ebből a témakörből megtudhatja, hogyan vehet fel adatmezőket az X++ bővítmények használatával az adóintegrációban.
author: qire
ms.date: 04/20/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: a3da8e1b8176eb25fe4e0a320aa3e907c06e09c5
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/11/2021
ms.locfileid: "6021392"
---
# <a name="add-data-fields-in-the-tax-integration-by-using-extension"></a><span data-ttu-id="038a3-103">Adatmezők hozzáadása az adóintegrációhoz bővítmény használatával</span><span class="sxs-lookup"><span data-stu-id="038a3-103">Add data fields in the tax integration by using extension</span></span>

[!include [banner](../includes/banner.md)]


<span data-ttu-id="038a3-104">Ebből a témakörből megtudhatja, hogyan vehet fel adatmezőket az X++ bővítmények használatával az adóintegrációban.</span><span class="sxs-lookup"><span data-stu-id="038a3-104">This topic explains how to use X++ extensions to add data fields in the tax integration.</span></span> <span data-ttu-id="038a3-105">Ezek a mezők kiterjeszthetőek az adózási szolgáltatás adózási adatmodelljéhez, és az adókódok meghatározására használhatók.</span><span class="sxs-lookup"><span data-stu-id="038a3-105">These fields can be extended to the tax data model of the tax service and used to determine tax codes.</span></span> <span data-ttu-id="038a3-106">További információt az [Adatmezők hozzáadása az adókonfigurációkban](tax-service-add-data-fields-tax-configurations.md) részben talál.</span><span class="sxs-lookup"><span data-stu-id="038a3-106">For more information, see [Add data fields in tax configurations](tax-service-add-data-fields-tax-configurations.md).</span></span>

## <a name="data-model"></a><span data-ttu-id="038a3-107">Adatmodell</span><span class="sxs-lookup"><span data-stu-id="038a3-107">Data model</span></span>

<span data-ttu-id="038a3-108">Az adatmodellben lévő adatokat objektumok hordozzák és az osztályok hajtják végre.</span><span class="sxs-lookup"><span data-stu-id="038a3-108">The data in the data model is carried by objects and implemented by classes.</span></span>

<span data-ttu-id="038a3-109">Alább felsoroltuk a főbb objektumokat:</span><span class="sxs-lookup"><span data-stu-id="038a3-109">Here is a list of the major objects:</span></span>

* <span data-ttu-id="038a3-110">AxClass/TaxIntegration **Document** Object</span><span class="sxs-lookup"><span data-stu-id="038a3-110">AxClass/TaxIntegration **Document** Object</span></span>
* <span data-ttu-id="038a3-111">AxClass/TaxIntegration **Line** Object</span><span class="sxs-lookup"><span data-stu-id="038a3-111">AxClass/TaxIntegration **Line** Object</span></span>
* <span data-ttu-id="038a3-112">AxClass/TaxIntegration **TaxLine** Object</span><span class="sxs-lookup"><span data-stu-id="038a3-112">AxClass/TaxIntegration **TaxLine** Object</span></span>

<span data-ttu-id="038a3-113">A következő ábra megmutatja, hogyan kapcsolódnak ezek az objektumok.</span><span class="sxs-lookup"><span data-stu-id="038a3-113">The following illustration shows how these objects are related.</span></span>

<span data-ttu-id="038a3-114">[![Adatmodellobjektum-kapcsolat](./media/tax-service-customize-image1.png)](./media/tax-service-customize-image1.png)</span><span class="sxs-lookup"><span data-stu-id="038a3-114">[![Data model object relationship](./media/tax-service-customize-image1.png)](./media/tax-service-customize-image1.png)</span></span>

<span data-ttu-id="038a3-115">A **Dokumentum** objektumok számos **Vonal** objektumot tartalmazhatnak.</span><span class="sxs-lookup"><span data-stu-id="038a3-115">A **Document** object can contain many **Line** objects.</span></span> <span data-ttu-id="038a3-116">Minden objektum az adószolgáltatás metaadatait tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="038a3-116">Each object contains metadata for the tax service.</span></span>

- <span data-ttu-id="038a3-117">A `TaxIntegrationDocumentObject` objektum `originAddress` metaadatokkal rendelkezik, amelyek a forráscímre vonatkozó információkat tartalmaz és `includingTax` metaadatokat tartalmaznak, ami azt jelzi, hogy a sor összege tartalmazza-e az áfát.</span><span class="sxs-lookup"><span data-stu-id="038a3-117">`TaxIntegrationDocumentObject` has `originAddress` metadata, which contains information about the source address, and `includingTax` metadata, which indicates whether the line amount includes sales tax.</span></span>
- <span data-ttu-id="038a3-118">A `TaxIntegrationLineObject` rendelkezik `itemId`, `quantity` és `categoryId` metaadatokkal.</span><span class="sxs-lookup"><span data-stu-id="038a3-118">`TaxIntegrationLineObject` has `itemId`, `quantity`, and `categoryId` metadata.</span></span>

> [!NOTE]
> <span data-ttu-id="038a3-119">`TaxIntegrationLineObject` megvalósítja a **Díj** objektumokat is.</span><span class="sxs-lookup"><span data-stu-id="038a3-119">`TaxIntegrationLineObject` also implements **Charge** objects.</span></span>

## <a name="integration-flow"></a><span data-ttu-id="038a3-120">Integrációs folyamat</span><span class="sxs-lookup"><span data-stu-id="038a3-120">Integration flow</span></span>

<span data-ttu-id="038a3-121">A folyamat során az adatokat a tevékenységek manipulálják.</span><span class="sxs-lookup"><span data-stu-id="038a3-121">The data in the flow is manipulated by activities.</span></span>

### <a name="key-activities"></a><span data-ttu-id="038a3-122">Kulcsfontosságú tevékenységek</span><span class="sxs-lookup"><span data-stu-id="038a3-122">Key activities</span></span>

* <span data-ttu-id="038a3-123">AxClass/TaxIntegration **Calculation** ActivityOnDocument</span><span class="sxs-lookup"><span data-stu-id="038a3-123">AxClass/TaxIntegration **Calculation** ActivityOnDocument</span></span>
* <span data-ttu-id="038a3-124">AxClass/TaxIntegration **CurrencyExchange** ActivityOnDocument</span><span class="sxs-lookup"><span data-stu-id="038a3-124">AxClass/TaxIntegration **CurrencyExchange** ActivityOnDocument</span></span>
* <span data-ttu-id="038a3-125">AxClass/TaxIntegration **DataPersistence** ActivityOnDocument</span><span class="sxs-lookup"><span data-stu-id="038a3-125">AxClass/TaxIntegration **DataPersistence** ActivityOnDocument</span></span>
* <span data-ttu-id="038a3-126">AxClass/TaxIntegration **DataRetrieval** ActivityOnDocument</span><span class="sxs-lookup"><span data-stu-id="038a3-126">AxClass/TaxIntegration **DataRetrieval** ActivityOnDocument</span></span>
* <span data-ttu-id="038a3-127">AxClass/TaxIntegration **SettingRetrieval** ActivityOnDocument</span><span class="sxs-lookup"><span data-stu-id="038a3-127">AxClass/TaxIntegration **SettingRetrieval** ActivityOnDocument</span></span>

<span data-ttu-id="038a3-128">A tevékenységek a következő sorrendben futnak:</span><span class="sxs-lookup"><span data-stu-id="038a3-128">Activities are run in the following order:</span></span>

1. <span data-ttu-id="038a3-129">Beállítása lekérése</span><span class="sxs-lookup"><span data-stu-id="038a3-129">Setting Retrieval</span></span>
2. <span data-ttu-id="038a3-130">Adatlekérés</span><span class="sxs-lookup"><span data-stu-id="038a3-130">Data Retrieval</span></span>
3. <span data-ttu-id="038a3-131">Számítási szolgáltatás</span><span class="sxs-lookup"><span data-stu-id="038a3-131">Calculation Service</span></span>
4. <span data-ttu-id="038a3-132">Pénznemátváltás</span><span class="sxs-lookup"><span data-stu-id="038a3-132">Currency Exchange</span></span>
5. <span data-ttu-id="038a3-133">Adatperzisztencia</span><span class="sxs-lookup"><span data-stu-id="038a3-133">Data Persistence</span></span>

<span data-ttu-id="038a3-134">Például bővítse ki az **Adatlekérést** a **Számítási szolgáltatás** előtt.</span><span class="sxs-lookup"><span data-stu-id="038a3-134">For example, extend **Data Retrieval** before **Calculation Service**.</span></span>

#### <a name="data-retrieval-activities"></a><span data-ttu-id="038a3-135">Adatlekérési tevékenységek</span><span class="sxs-lookup"><span data-stu-id="038a3-135">Data Retrieval activities</span></span>

<span data-ttu-id="038a3-136">Az **adatlekérési** tevékenységek adatokat kérnek le az adatbázisból.</span><span class="sxs-lookup"><span data-stu-id="038a3-136">**Data Retrieval** activities retrieve data from the database.</span></span> <span data-ttu-id="038a3-137">A különböző tranzakciók adapterei különböző tranzakciótáblákból származó adatok beolvasására érhetők el:</span><span class="sxs-lookup"><span data-stu-id="038a3-137">Adapters for different transactions are available to retrieve data from different transaction tables:</span></span>

- <span data-ttu-id="038a3-138">AxClass/TaxIntegration **PurchTable** DataRetrieval</span><span class="sxs-lookup"><span data-stu-id="038a3-138">AxClass/TaxIntegration **PurchTable** DataRetrieval</span></span>
- <span data-ttu-id="038a3-139">AxClass/TaxIntegration **PurchParmTable** DataRetrieval</span><span class="sxs-lookup"><span data-stu-id="038a3-139">AxClass/TaxIntegration **PurchParmTable** DataRetrieval</span></span>
- <span data-ttu-id="038a3-140">AxClass/TaxIntegration **PurchREQTable** DataRetrieval</span><span class="sxs-lookup"><span data-stu-id="038a3-140">AxClass/TaxIntegration **PurchREQTable** DataRetrieval</span></span>
- <span data-ttu-id="038a3-141">AxClass/TaxIntegration **PurchRFQTable** DataRetrieval</span><span class="sxs-lookup"><span data-stu-id="038a3-141">AxClass/TaxIntegration **PurchRFQTable** DataRetrieval</span></span>
- <span data-ttu-id="038a3-142">AxClass/TaxIntegration **VendInvoiceInfoTable** DataRetrieval</span><span class="sxs-lookup"><span data-stu-id="038a3-142">AxClass/TaxIntegration **VendInvoiceInfoTable** DataRetrieval</span></span>
- <span data-ttu-id="038a3-143">AxClass/TaxIntegration **SalesTable** DataRetrieval</span><span class="sxs-lookup"><span data-stu-id="038a3-143">AxClass/TaxIntegration **SalesTable** DataRetrieval</span></span>
- <span data-ttu-id="038a3-144">AxClass/TaxIntegration **SalesParm** DataRetrieval</span><span class="sxs-lookup"><span data-stu-id="038a3-144">AxClass/TaxIntegration **SalesParm** DataRetrieval</span></span>

<span data-ttu-id="038a3-145">Ezekben az **Adatlekérési** tevékenységekben az adatok másolása történik az adatbázisból a `TaxIntegrationDocumentObject` és a `TaxIntegrationLineObject` elemekbe.</span><span class="sxs-lookup"><span data-stu-id="038a3-145">In these **Data Retrieval** activities, data is copied from the database to `TaxIntegrationDocumentObject` and `TaxIntegrationLineObject`.</span></span> <span data-ttu-id="038a3-146">Mivel ezek a tevékenységek kiterjesztik ugyanazt az absztrakt sablonosztályt, közös módszereik vannak.</span><span class="sxs-lookup"><span data-stu-id="038a3-146">Because all these activities extend the same abstract template class, they have common methods.</span></span>

#### <a name="calculation-service-activities"></a><span data-ttu-id="038a3-147">Számítási szolgáltatás tevékenységek</span><span class="sxs-lookup"><span data-stu-id="038a3-147">Calculation Service activities</span></span>

<span data-ttu-id="038a3-148">A **Számítási szolgáltatás** tevékenység egy kapcsolat az adószolgáltatás és az adóintegráció között.</span><span class="sxs-lookup"><span data-stu-id="038a3-148">The **Calculation Service** activity is the link between the tax service and the tax integration.</span></span> <span data-ttu-id="038a3-149">Ez a tevékenység a következő funkciókért felelős:</span><span class="sxs-lookup"><span data-stu-id="038a3-149">This activity is responsible for the following functions:</span></span>

1. <span data-ttu-id="038a3-150">A kérelem létrehozása.</span><span class="sxs-lookup"><span data-stu-id="038a3-150">Construct the request.</span></span>
2. <span data-ttu-id="038a3-151">A kérelem feladása az adószolgáltatásba.</span><span class="sxs-lookup"><span data-stu-id="038a3-151">Post the request to the tax service.</span></span>
3. <span data-ttu-id="038a3-152">Választ kap z adószolgáltatásból.</span><span class="sxs-lookup"><span data-stu-id="038a3-152">Get the response from the tax service.</span></span>
4. <span data-ttu-id="038a3-153">A válasz elemzése.</span><span class="sxs-lookup"><span data-stu-id="038a3-153">Parse the response.</span></span>

<span data-ttu-id="038a3-154">A kérelemhez hozzáadott adatmező a többi metaadattal együtt lesz feladva.</span><span class="sxs-lookup"><span data-stu-id="038a3-154">A data field that you add to the request will be posted together with other metadata.</span></span> 

## <a name="extension-implementation"></a><span data-ttu-id="038a3-155">Kiterjesztés megvalósítása</span><span class="sxs-lookup"><span data-stu-id="038a3-155">Extension implementation</span></span>

<span data-ttu-id="038a3-156">Ez a szakasz részletes lépéseket tartalmaz, amelyek ismertetik a bővítmény megvalósításának lépéseit.</span><span class="sxs-lookup"><span data-stu-id="038a3-156">This section provides detailed steps that explain how to implement the extension.</span></span> <span data-ttu-id="038a3-157">Példaként a **Költségközpont** és a **Projekt** pénzügyi dimenzióit használja.</span><span class="sxs-lookup"><span data-stu-id="038a3-157">It uses the **Cost center** and **Project** financial dimensions as examples.</span></span>

### <a name="step-1-add-the-data-variable-in-the-object-class"></a><span data-ttu-id="038a3-158">1. lépés</span><span class="sxs-lookup"><span data-stu-id="038a3-158">Step 1.</span></span> <span data-ttu-id="038a3-159">Az adatváltozó hozzáadása az objektumosztályhoz</span><span class="sxs-lookup"><span data-stu-id="038a3-159">Add the data variable in the object class</span></span>

<span data-ttu-id="038a3-160">Az objektumosztály tartalmazza az adatváltozót és az adat beolvasó/beállító metódusait.</span><span class="sxs-lookup"><span data-stu-id="038a3-160">The object class contains the data variable and getter/setter methods for the data.</span></span> <span data-ttu-id="038a3-161">Adja hozzá az adatmezőt a `TaxIntegrationDocumentObject` vagy `TaxIntegrationLineObject` elemhez a mező szintjétől függően.</span><span class="sxs-lookup"><span data-stu-id="038a3-161">Add the data field to either `TaxIntegrationDocumentObject` or `TaxIntegrationLineObject`, depending on the level of the field.</span></span> <span data-ttu-id="038a3-162">A következő példa a sorszintet használja, a fájlnév `TaxIntegrationLineObject_Extension.xpp`.</span><span class="sxs-lookup"><span data-stu-id="038a3-162">The following example uses the line level, and the file name is `TaxIntegrationLineObject_Extension.xpp`.</span></span>

> [!NOTE]
> <span data-ttu-id="038a3-163">Ha a hozzáadott adatmező dokumentumszinten van, módosítsa a fájl nevét `TaxIntegrationDocumentObject_Extension.xpp` névre.</span><span class="sxs-lookup"><span data-stu-id="038a3-163">If the data field that you're adding is at the document level, change the file name to `TaxIntegrationDocumentObject_Extension.xpp`.</span></span>

```X++
[ExtensionOf(classStr(TaxIntegrationLineObject))]
final class TaxIntegrationLineObject_Extension
{
    private OMOperatingUnitNumber costCenter;
    private ProjId projectId;

    /// <summary>
    /// Gets a costCenter.
    /// </summary>
    /// <returns>The cost center.</returns>
    public final OMOperatingUnitNumber getCostCenter()
    {
        return this.costCenter;
    }

    /// <summary>
    /// Sets the cost center.
    /// </summary>
    /// <param name = "_value">The cost center.</param>
    public final void setCostCenter(OMOperatingUnitNumber _value)
    {
        this.costCenter = _value;
    }

    /// <summary>
    /// Gets a project ID.
    /// </summary>
    /// <returns>The project ID.</returns>
    public final ProjId getProjectId()
    {
        return this.projectId;
    }

    /// <summary>
    /// Sets the project ID.
    /// </summary>
    /// <param name = "_value">The project ID.</param>
    public final void setProjectId(ProjId _value)
    {
        this.projectId = _value;
    }
}
```

<span data-ttu-id="038a3-164">A **Költségközpont** és a **Projekt** privát változóként kerül hozzáadásra.</span><span class="sxs-lookup"><span data-stu-id="038a3-164">**Cost center** and **Project** are added as private variables.</span></span> <span data-ttu-id="038a3-165">Hozzon létre beolvasó és beállító metódusokat ezekhez az adatmezőkhöz az adatok manipulálásához.</span><span class="sxs-lookup"><span data-stu-id="038a3-165">Create getter and setter methods for these data fields to manipulate the data.</span></span>

### <a name="step-2-retrieve-data-from-the-database"></a><span data-ttu-id="038a3-166">2. lépés</span><span class="sxs-lookup"><span data-stu-id="038a3-166">Step 2.</span></span> <span data-ttu-id="038a3-167">Adatok lekérése az adatbázisból</span><span class="sxs-lookup"><span data-stu-id="038a3-167">Retrieve data from the database</span></span>

<span data-ttu-id="038a3-168">Határozza meg a tranzakciót, és bővítse ki a megfelelő adapterosztályokat az adatok beolvasása érdekében.</span><span class="sxs-lookup"><span data-stu-id="038a3-168">Specify the transaction, and extend the appropriate adapter classes to retrieve the data.</span></span> <span data-ttu-id="038a3-169">Ha például egy **Beszerzési rendelési** tranzakciót használ, ki kell terjesztenie a `TaxIntegrationPurchTableDataRetrieval` és `TaxIntegrationVendInvoiceInfoTableDataRetrieval` értékeket.</span><span class="sxs-lookup"><span data-stu-id="038a3-169">For example, if you use a **Purchase order** transaction, you must extend `TaxIntegrationPurchTableDataRetrieval` and `TaxIntegrationVendInvoiceInfoTableDataRetrieval`.</span></span> 

> [!NOTE]
> <span data-ttu-id="038a3-170">A `TaxIntegrationPurchParmTableDataRetrieval` öröklődik a `TaxIntegrationPurchTableDataRetrieval` értékből.</span><span class="sxs-lookup"><span data-stu-id="038a3-170">`TaxIntegrationPurchParmTableDataRetrieval` is inherited from `TaxIntegrationPurchTableDataRetrieval`.</span></span> <span data-ttu-id="038a3-171">Nem szabad megváltoztatni, kivéve, ha a logika a `purchTable` és a `purchParmTable` táblákban eltér.</span><span class="sxs-lookup"><span data-stu-id="038a3-171">It should not be changed unless the logic of the `purchTable` and `purchParmTable` tables differs.</span></span>

<span data-ttu-id="038a3-172">Ha az adatmezőt minden tranzakcióhoz hozzá kell adni, bővítse ki az összes `DataRetrieval` osztályt.</span><span class="sxs-lookup"><span data-stu-id="038a3-172">If the data field should be added for all transactions, extend all `DataRetrieval` classes.</span></span>

<span data-ttu-id="038a3-173">Mivel minden **Adatlekérési** tevékenység ugyanazt a sablonosztályt bővíti ki, az osztálystruktúrák, a változók és a metódusok hasonlóak.</span><span class="sxs-lookup"><span data-stu-id="038a3-173">Because all **Data Retrieval** activities extend the same template class, the class structures, variables, and methods are similar.</span></span>

```X++
protected TaxIntegrationDocumentObject document;

/// <summary>
/// Copies to the document.
/// </summary>
protected abstract void copyToDocument()
{
    // It is recommended to implement as:
    //
    // this.copyToDocumentByDefault();
    // this.copyToDocumentFromHeaderTable();
    // this.copyAddressToDocument();
}
 
/// <summary>
/// Copies to the current line of the document.
/// </summary>
/// <param name = "_line">The current line of the document.</param>
protected abstract void copyToLine(TaxIntegrationLineObject _line)
{
    // It is recommended to implement as:
    //
    // this.copyToLineByDefault(_line);
    // this.copyToLineFromLineTable(_line);
    // this.copyQuantityAndTransactionAmountToLine(_line);
    // this.copyAddressToLine(_line);
    // this.copyToLineFromHeaderTable(_line);
}
```

<span data-ttu-id="038a3-174">A következő az alapszerkezetet mutatja be a `PurchTable` tábla használata esetén.</span><span class="sxs-lookup"><span data-stu-id="038a3-174">The following example shows the basic structure when the `PurchTable` table is used.</span></span>

```X++
public class TaxIntegrationPurchTableDataRetrieval extends TaxIntegrationAbstractDataRetrievalTemplate
{
    protected PurchTable purchTable;
    protected PurchLine purchLine;

    // Query builder methods
    [Replaceable]
    protected SysDaQueryObject getDocumentQueryObject()
    [Replaceable]
    protected SysDaQueryObject getLineQueryObject()
    [Replaceable]
    protected SysDaQueryObject getDocumentChargeQueryObject()
    [Replaceable]
    protected SysDaQueryObject getLineChargeQueryObject()

    // Data retrieval methods
    protected void copyToDocument()
    protected void copyToDocumentFromHeaderTable()
    protected void copyToLine(TaxIntegrationLineObject _line)
    protected void copyToLineFromLineTable(TaxIntegrationLineObject _line)
    ...
}
```

<span data-ttu-id="038a3-175">A `CopyToDocument` metódus meghívásakor a `this.purchTable` puffer már létezik.</span><span class="sxs-lookup"><span data-stu-id="038a3-175">When the `CopyToDocument` method is called, the `this.purchTable` buffer already exists.</span></span> <span data-ttu-id="038a3-176">Ennek a metódusnak az a célja, hogy a `DocumentObject` osztályban létrehozott beállítási módszerrel a `this.purchTable` tábla összes szükséges adatát átmásolja a `document` objektumba.</span><span class="sxs-lookup"><span data-stu-id="038a3-176">The purpose of this method is to copy all the required data from `this.purchTable` to the `document` object by using the setter method that was created in the `DocumentObject` class.</span></span>

<span data-ttu-id="038a3-177">Hasonlóképpen, a `this.purchLine` puffer már létezik a `CopyToLine` metódusban.</span><span class="sxs-lookup"><span data-stu-id="038a3-177">Likewise, a `this.purchLine` buffer already exists in the `CopyToLine` method.</span></span> <span data-ttu-id="038a3-178">Ennek a metódusnak az a célja, hogy a `LineObject` osztályban létrehozott beállítási módszerrel a `this.purchLine` tábla összes szükséges adatát átmásolja a `_line` objektumba.</span><span class="sxs-lookup"><span data-stu-id="038a3-178">The purpose of this method is to copy all the required data from `this.purchLine` to the `_line` object by using the setter method that was created in the `LineObject` class.</span></span>

<span data-ttu-id="038a3-179">A legegyértelműbb megközelítés az, hogy `CopyToDocument` és a `CopyToLine` metódusokat kiterjesztik.</span><span class="sxs-lookup"><span data-stu-id="038a3-179">The most straightforward approach is to extend the `CopyToDocument` and `CopyToLine` methods.</span></span> <span data-ttu-id="038a3-180">Javasoljuk azonban, hogy először próbálja ki a `copyToDocumentFromHeaderTable` és a `copyToLineFromLineTable` metódusokat.</span><span class="sxs-lookup"><span data-stu-id="038a3-180">However, we recommend that you try the `copyToDocumentFromHeaderTable` and `copyToLineFromLineTable` methods first.</span></span> <span data-ttu-id="038a3-181">Ha nem úgy működnek, ahogy szeretné, implementálja a saját metódusát, és hívja be a `CopyToDocument` és `CopyToLine` metódusokban.</span><span class="sxs-lookup"><span data-stu-id="038a3-181">If they don't work as you require, implement your own method, and call it in `CopyToDocument` and `CopyToLine`.</span></span> <span data-ttu-id="038a3-182">Három gyakori helyzet van, amikor ezt a megközelítést használhatja:</span><span class="sxs-lookup"><span data-stu-id="038a3-182">There are three common situations where you might use this approach:</span></span>

- <span data-ttu-id="038a3-183">A szükséges mező `PurchTable` vagy `PurchLine`.</span><span class="sxs-lookup"><span data-stu-id="038a3-183">The required field is in `PurchTable` or `PurchLine`.</span></span> <span data-ttu-id="038a3-184">Ebben a helyzetben kiterjesztheti a `copyToDocumentFromHeaderTable` és `copyToLineFromLineTable` metódusokat.</span><span class="sxs-lookup"><span data-stu-id="038a3-184">In this situation, you can extend `copyToDocumentFromHeaderTable` and `copyToLineFromLineTable`.</span></span> <span data-ttu-id="038a3-185">Itt található a mintakód.</span><span class="sxs-lookup"><span data-stu-id="038a3-185">Here is the sample code.</span></span>

    ```X++
    /// <summary>
    /// Copies to the current line of the document from.
    /// </summary>
    /// <param name = "_line">The current line of the document.</param>
    protected void copyToLineFromLineTable(TaxIntegrationLineObject _line)
    {
        next copyToLineFromLineTable(_line);
        // if we already added XXX in TaxIntegrationLineObject
        _line.setXXX(this.purchLine.XXX);
    }
    ```

- <span data-ttu-id="038a3-186">A szükséges adatok nincsenek a tranzakció alapértelmezett táblájában.</span><span class="sxs-lookup"><span data-stu-id="038a3-186">The required data isn't in the default table of the transaction.</span></span> <span data-ttu-id="038a3-187">Vannak azonban csatlakoztatás kapcsolatok az alapértelmezett táblával, és erre a mezőre a legtöbb sorban szükség van.</span><span class="sxs-lookup"><span data-stu-id="038a3-187">However, there are some join relationships with the default table, and the field is required on most lines.</span></span> <span data-ttu-id="038a3-188">Ebben az esetben cserélje le a `getDocumentQueryObject` vagy `getLineObject` objektumot a tábla lekérdezéséhez az egyesítés kapcsolattal.</span><span class="sxs-lookup"><span data-stu-id="038a3-188">In this situation, replace `getDocumentQueryObject` or `getLineObject` to query the table by join relationship.</span></span> <span data-ttu-id="038a3-189">A következő példában a **Szállítás most** mező integrálva van az értékesítési rendeléssel sor szinten.</span><span class="sxs-lookup"><span data-stu-id="038a3-189">In the following example, the **Deliver Now** field is integrated with the sales order at the line level.</span></span>

    ```X++
    public class TaxIntegrationSalesTableDataRetrieval
    {
        protected MCRSalesLineDropShipment mcrSalesLineDropShipment;

        /// <summary>
        /// Gets the query for the lines of the document.
        /// </summary>
        /// <returns>The query for the lines of the document</returns>
        [Replaceable]
        protected SysDaQueryObject getLineQueryObject()
        {
            return SysDaQueryObjectBuilder::from(this.salesLine)
                .where(this.salesLine, fieldStr(SalesLine, SalesId)).isEqualToLiteral(this.salesTable.SalesId)
                .outerJoin(this.mcrSalesLineDropShipment)
                .where(this.mcrSalesLineDropShipment, fieldStr(MCRSalesLineDropShipment, SalesLine)).isEqualTo(this.salesLine, fieldStr(SalesLine, RecId))
                .toSysDaQueryObject();
        }
    }
    ```

    <span data-ttu-id="038a3-190">Ebben a példában egy `mcrSalesLineDropShipment` puffer van deklarálva, és a lekérdezés a `getLineQueryObject` objektumban van definiálva.</span><span class="sxs-lookup"><span data-stu-id="038a3-190">In this example, a `mcrSalesLineDropShipment` buffer is declared, and the query is defined in `getLineQueryObject`.</span></span> <span data-ttu-id="038a3-191">A lekérdezés a `MCRSalesLineDropShipment.SalesLine == SalesLine.RecId` kapcsolatot használja.</span><span class="sxs-lookup"><span data-stu-id="038a3-191">The query uses the relationship `MCRSalesLineDropShipment.SalesLine == SalesLine.RecId`.</span></span> <span data-ttu-id="038a3-192">A helyzet kibővítése során lecserélheti a `getLineQueryObject` objektumot a saját létrehozott lekérdezésére.</span><span class="sxs-lookup"><span data-stu-id="038a3-192">While you're extending in this situation, you can replace `getLineQueryObject` with your own constructed query object.</span></span> <span data-ttu-id="038a3-193">Azonban vegye figyelembe a következő pontokat:</span><span class="sxs-lookup"><span data-stu-id="038a3-193">However, note the following points:</span></span>

    * <span data-ttu-id="038a3-194">Mivel a `getLineQueryObject` metódus visszatérési értéke `SysDaQueryObject`, ezt az objektumot a SysDa megközelítéssel kell létrehoznia.</span><span class="sxs-lookup"><span data-stu-id="038a3-194">Because the return value of the `getLineQueryObject` method is `SysDaQueryObject`, you must construct this object by using the SysDa approach.</span></span>
    * <span data-ttu-id="038a3-195">A létező tábla nem távolítható el.</span><span class="sxs-lookup"><span data-stu-id="038a3-195">Can't remove existed table.</span></span>

- <span data-ttu-id="038a3-196">A szükséges adatok bonyolult illesztési kapcsolattal kapcsolódnak a tranzakciós táblához, vagy a kapcsolat nem egy az egyhez (1:1), hanem egy a sokhoz (1:N).</span><span class="sxs-lookup"><span data-stu-id="038a3-196">The required data is related to the transaction table by a complicated join relationship, or the relation isn't one to one (1:1) but one to many (1:N).</span></span> <span data-ttu-id="038a3-197">Ebben a helyzetben a dolgok egy kicsit bonyolulttá válnak.</span><span class="sxs-lookup"><span data-stu-id="038a3-197">In this situation, things become a little complicated.</span></span> <span data-ttu-id="038a3-198">Ez a helyzet a pénzügyi dimenziók példájára vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="038a3-198">This situation applies to the example of financial dimensions.</span></span> 

    <span data-ttu-id="038a3-199">Ebben az esetben saját metódust valósíthat meg az adatok beolvasására.</span><span class="sxs-lookup"><span data-stu-id="038a3-199">In this situation, you can implement your own method to retrieve the data.</span></span> <span data-ttu-id="038a3-200">Itt van a mintakód a `TaxIntegrationPurchTableDataRetrieval_Extension.xpp` fájlban.</span><span class="sxs-lookup"><span data-stu-id="038a3-200">Here is the sample code in the `TaxIntegrationPurchTableDataRetrieval_Extension.xpp` file.</span></span>

    ```X++
    [ExtensionOf(classStr(TaxIntegrationPurchTableDataRetrieval))]
    final class TaxIntegrationPurchTableDataRetrieval_Extension
    {
        private const str CostCenterKey = 'CostCenter';
        private const str ProjectKey = 'Project';

        /// <summary>
        /// Copies to the current line of the document from.
        /// </summary>
        /// <param name = "_line">The current line of the document.</param>
        protected void copyToLineFromLineTable(TaxIntegrationLineObject _line)
        {
            Map dimensionAttributeMap = this.getDimensionAttributeMapByDefaultDimension(this.purchline.DefaultDimension);
            if (dimensionAttributeMap.exists(CostCenterKey))
            {
                _line.setCostCenter(dimensionAttributeMap.lookup(CostCenterKey));
            }
            if (dimensionAttributeMap.exists(ProjectKey))
            {
                _line.setProjectId(dimensionAttributeMap.lookup(ProjectKey));
            }
            next copyToLineFromLineTable(_line);
        }
        private Map getDimensionAttributeMapByDefaultDimension(RefRecId _defaultDimension)
        {
            DimensionAttribute dimensionAttribute;
            DimensionAttributeValue dimensionAttributeValue;
            DimensionAttributeValueSetItem dimensionAttributeValueSetItem;
            Map ret = new Map(Types::String, Types::String);

            select Name, RecId from dimensionAttribute
                join dimensionAttributeValue
                    where dimensionAttributeValue.dimensionAttribute == dimensionAttribute.RecId
                join DimensionAttributeValueSetItem
                    where DimensionAttributeValueSetItem.DimensionAttributeValue == DimensionAttributeValue.RecId
                        && DimensionAttributeValueSetItem.DimensionAttributeValueSet == _defaultDimension;

            while(dimensionAttribute.RecId)
            {
                ret.insert(dimensionAttribute.Name, dimensionAttributeValue.DisplayValue);
                next dimensionAttribute;
            }
            return ret;
        }
    }
    ```

### <a name="step-3-add-data-to-the-request"></a><span data-ttu-id="038a3-201">3. lépés</span><span class="sxs-lookup"><span data-stu-id="038a3-201">Step 3.</span></span> <span data-ttu-id="038a3-202">Adatok hozzáadása a kérelemhez</span><span class="sxs-lookup"><span data-stu-id="038a3-202">Add data to the request</span></span>

<span data-ttu-id="038a3-203">Terjessza ki a `copyToTaxableDocumentHeaderWrapperFromTaxIntegrationDocumentObject` vagy `copyToTaxableDocumentLineWrapperFromTaxIntegrationLineObjectByLine` metódust az adatok hozzáadásához a kérelemhez.</span><span class="sxs-lookup"><span data-stu-id="038a3-203">Extend the `copyToTaxableDocumentHeaderWrapperFromTaxIntegrationDocumentObject` or `copyToTaxableDocumentLineWrapperFromTaxIntegrationLineObjectByLine` method to add data to the request.</span></span> <span data-ttu-id="038a3-204">Itt van a mintakód a `TaxIntegrationCalculationActivityOnDocument_CalculationService_Extension.xpp` fájlban.</span><span class="sxs-lookup"><span data-stu-id="038a3-204">Here is the sample code in the `TaxIntegrationCalculationActivityOnDocument_CalculationService_Extension.xpp` file.</span></span>

```X++
[ExtensionOf(classStr(TaxIntegrationCalculationActivityOnDocument_CalculationService))]
final static class TaxIntegrationCalculationActivityOnDocument_CalculationService_Extension
{
    // Define key for the form in post request
    private const str IOCostCenter = 'Cost Center';
    private const str IOProject = 'Project';

    /// <summary>
    /// Copies to <c>TaxableDocumentLineWrapper</c> from <c>TaxIntegrationLineObject</c> by line.
    /// </summary>
    /// <param name = "_destination"><c>TaxableDocumentLineWrapper</c>.</param>
    /// <param name = "_source"><c>TaxIntegrationLineObject</c>.</param>
    protected static void copyToTaxableDocumentLineWrapperFromTaxIntegrationLineObjectByLine(Microsoft.Dynamics.TaxCalculation.ApiContracts.TaxableDocumentLineWrapper _destination, TaxIntegrationLineObject _source)
    {
        next copyToTaxableDocumentLineWrapperFromTaxIntegrationLineObjectByLine(_destination, _source);
        // Set the field we need to integrated for tax service
        _destination.SetField(IOCostCenter, _source.getCostCenter());
        _destination.SetField(IOProject, _source.getProjectId());
    }
}
```

<span data-ttu-id="038a3-205">Ebben a kódban a `_destination` a burkoló objektum, amely a közzétételi kérés létrehozásához használható, és a `_source` a `TaxIntegrationLineObject` objektum.</span><span class="sxs-lookup"><span data-stu-id="038a3-205">In this code, `_destination` is the wrapper object that is used to generate the post request, and `_source` is the `TaxIntegrationLineObject` object.</span></span> 

> [!NOTE]
> * <span data-ttu-id="038a3-206">Adja meg a kérelem űrlapon használt kulcsot, mint `private const str`.</span><span class="sxs-lookup"><span data-stu-id="038a3-206">Define the key that is used in the request form as `private const str`.</span></span>
> * <span data-ttu-id="038a3-207">Állítsa be a mezőt a `copyToTaxableDocumentLineWrapperFromTaxIntegrationLineObjectByLine` metódusban a `SetField` metódus használatával.</span><span class="sxs-lookup"><span data-stu-id="038a3-207">Set the field in the `copyToTaxableDocumentLineWrapperFromTaxIntegrationLineObjectByLine` method by using the `SetField` method.</span></span> <span data-ttu-id="038a3-208">A második paraméter adattípusának `string` típusúnak kell lennie:</span><span class="sxs-lookup"><span data-stu-id="038a3-208">The data type of the second parameter should be `string`.</span></span> <span data-ttu-id="038a3-209">Ha az adattípus nem, `string` konvertálja azt `string` típusúra.</span><span class="sxs-lookup"><span data-stu-id="038a3-209">If the data type isn't `string`, convert it to `string`.</span></span>

## <a name="appendix"></a><span data-ttu-id="038a3-210">Melléklet</span><span class="sxs-lookup"><span data-stu-id="038a3-210">Appendix</span></span>

<span data-ttu-id="038a3-211">Ez a függelék a pénzügyi dimenziók (**Költségközpont** és **Projekt**) sorszintű integrálásához szükséges teljes mintakódot mutatja.</span><span class="sxs-lookup"><span data-stu-id="038a3-211">This appendix shows the complete sample code for the integration of financial dimensions (**Cost center** and **Project**) at the line level.</span></span>

### <a name="taxintegrationlineobject_extensionxpp"></a><span data-ttu-id="038a3-212">TaxIntegrationLineObject_Extension.xpp</span><span class="sxs-lookup"><span data-stu-id="038a3-212">TaxIntegrationLineObject_Extension.xpp</span></span>

```X++
[ExtensionOf(classStr(TaxIntegrationLineObject))]
final class TaxIntegrationLineObject_Extension
{
    private OMOperatingUnitNumber costCenter;
    private ProjId projectId;

    /// <summary>
    /// Gets a costCenter.
    /// </summary>
    /// <returns>The cost center.</returns>
    public final OMOperatingUnitNumber getCostCenter()
    {
        return this.costCenter;
    }

    /// <summary>
    /// Sets the cost center.
    /// </summary>
    /// <param name = "_value">The cost center.</param>
    public final void setCostCenter(OMOperatingUnitNumber _value)
    {
        this.costCenter = _value;
    }

    /// <summary>
    /// Gets a project ID.
    /// </summary>
    /// <returns>The project ID.</returns>
    public final ProjId getProjectId()
    {
        return this.projectId;
    }

    /// <summary>
    /// Sets the project ID.
    /// </summary>
    /// <param name = "_value">The project ID.</param>
    public final void setProjectId(ProjId _value)
    {
        this.projectId = _value;
    }
}
```

### <a name="taxintegrationpurchtabledataretrieval_extensionxpp"></a><span data-ttu-id="038a3-213">TaxIntegrationPurchTableDataRetrieval_Extension.xpp</span><span class="sxs-lookup"><span data-stu-id="038a3-213">TaxIntegrationPurchTableDataRetrieval_Extension.xpp</span></span>

```X++
[ExtensionOf(classStr(TaxIntegrationPurchTableDataRetrieval))]
final class TaxIntegrationPurchTableDataRetrieval_Extension
{
    private const str CostCenterKey = 'CostCenter';
    private const str ProjectKey = 'Project';

    /// <summary>
    /// Copies to the current line of the document from.
    /// </summary>
    /// <param name = "_line">The current line of the document.</param>
    protected void copyToLineFromLineTable(TaxIntegrationLineObject _line)
    {
        Map dimensionAttributeMap = this.getDimensionAttributeMapByDefaultDimension(this.purchline.DefaultDimension);
        if (dimensionAttributeMap.exists(CostCenterKey))
        {
            _line.setCostCenter(dimensionAttributeMap.lookup(CostCenterKey));
        }
        if (dimensionAttributeMap.exists(ProjectKey))
        {
            _line.setProjectId(dimensionAttributeMap.lookup(ProjectKey));
        }
        next copyToLineFromLineTable(_line);
    }
    private Map getDimensionAttributeMapByDefaultDimension(RefRecId _defaultDimension)
    {
        DimensionAttribute dimensionAttribute;
        DimensionAttributeValue dimensionAttributeValue;
        DimensionAttributeValueSetItem dimensionAttributeValueSetItem;
        Map ret = new Map(Types::String, Types::String);
        select Name, RecId from dimensionAttribute
            join dimensionAttributeValue
                where dimensionAttributeValue.dimensionAttribute == dimensionAttribute.RecId
            join DimensionAttributeValueSetItem
                where DimensionAttributeValueSetItem.DimensionAttributeValue == DimensionAttributeValue.RecId
                    && DimensionAttributeValueSetItem.DimensionAttributeValueSet == _defaultDimension;
        while(dimensionAttribute.RecId)
        {
            ret.insert(dimensionAttribute.Name, dimensionAttributeValue.DisplayValue);
            next dimensionAttribute;
        }
        return ret;
    }
}
```

### <a name="taxintegrationcalculationactivityondocument_calculationservice_extensionxpp"></a><span data-ttu-id="038a3-214">TaxIntegrationCalculationActivityOnDocument_CalculationService_Extension.xpp</span><span class="sxs-lookup"><span data-stu-id="038a3-214">TaxIntegrationCalculationActivityOnDocument_CalculationService_Extension.xpp</span></span>

```X++
[ExtensionOf(classStr(TaxIntegrationCalculationActivityOnDocument_CalculationService))]
final static class TaxIntegrationCalculationActivityOnDocument_CalculationService_Extension
{
    // Define key for the form in post request
    private const str IOCostCenter = 'Cost Center';
    private const str IOProject = 'Project';

    /// <summary>
    /// Copies to <c>TaxableDocumentLineWrapper</c> from <c>TaxIntegrationLineObject</c> by line.
    /// </summary>
    /// <param name = "_destination"><c>TaxableDocumentLineWrapper</c>.</param>
    /// <param name = "_source"><c>TaxIntegrationLineObject</c>.</param>
    protected static void copyToTaxableDocumentLineWrapperFromTaxIntegrationLineObjectByLine(Microsoft.Dynamics.TaxCalculation.ApiContracts.TaxableDocumentLineWrapper _destination, TaxIntegrationLineObject _source)
    {
        next copyToTaxableDocumentLineWrapperFromTaxIntegrationLineObjectByLine(_destination, _source);
        // Set the field we need to integrated for tax service
        _destination.SetField(IOCostCenter, _source.getCostCenter());
        _destination.SetField(IOProject, _source.getProjectId());
    }
}
```
