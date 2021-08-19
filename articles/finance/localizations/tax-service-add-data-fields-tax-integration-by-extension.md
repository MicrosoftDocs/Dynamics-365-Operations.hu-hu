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
ms.openlocfilehash: 8bdd56ebdd50c1eae98094725a01bf9c5ec52bb4e689eb282f80631810a65725
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6721658"
---
# <a name="add-data-fields-in-the-tax-integration-by-using-extension"></a>Adatmezők hozzáadása az adóintegrációhoz bővítmény használatával

[!include [banner](../includes/banner.md)]


Ebből a témakörből megtudhatja, hogyan vehet fel adatmezőket az X++ bővítmények használatával az adóintegrációban. Ezek a mezők kiterjeszthetőek az adózási szolgáltatás adózási adatmodelljéhez, és az adókódok meghatározására használhatók. További információt az [Adatmezők hozzáadása az adókonfigurációkban](tax-service-add-data-fields-tax-configurations.md) részben talál.

## <a name="data-model"></a>Adatmodell

Az adatmodellben lévő adatokat objektumok hordozzák és az osztályok hajtják végre.

Alább felsoroltuk a főbb objektumokat:

* AxClass/TaxIntegration **Document** Object
* AxClass/TaxIntegration **Line** Object
* AxClass/TaxIntegration **TaxLine** Object

A következő ábra megmutatja, hogyan kapcsolódnak ezek az objektumok.

[![Adatmodellobjektum-kapcsolat.](./media/tax-service-customize-image1.png)](./media/tax-service-customize-image1.png)

A **Dokumentum** objektumok számos **Vonal** objektumot tartalmazhatnak. Minden objektum az adószolgáltatás metaadatait tartalmazza.

- A `TaxIntegrationDocumentObject` objektum `originAddress` metaadatokkal rendelkezik, amelyek a forráscímre vonatkozó információkat tartalmaz és `includingTax` metaadatokat tartalmaznak, ami azt jelzi, hogy a sor összege tartalmazza-e az áfát.
- A `TaxIntegrationLineObject` rendelkezik `itemId`, `quantity` és `categoryId` metaadatokkal.

> [!NOTE]
> `TaxIntegrationLineObject` megvalósítja a **Díj** objektumokat is.

## <a name="integration-flow"></a>Integrációs folyamat

A folyamat során az adatokat a tevékenységek manipulálják.

### <a name="key-activities"></a>Kulcsfontosságú tevékenységek

* AxClass/TaxIntegration **Calculation** ActivityOnDocument
* AxClass/TaxIntegration **CurrencyExchange** ActivityOnDocument
* AxClass/TaxIntegration **DataPersistence** ActivityOnDocument
* AxClass/TaxIntegration **DataRetrieval** ActivityOnDocument
* AxClass/TaxIntegration **SettingRetrieval** ActivityOnDocument

A tevékenységek a következő sorrendben futnak:

1. Beállítása lekérése
2. Adatlekérés
3. Számítási szolgáltatás
4. Pénznemátváltás
5. Adatperzisztencia

Például bővítse ki az **Adatlekérést** a **Számítási szolgáltatás** előtt.

#### <a name="data-retrieval-activities"></a>Adatlekérési tevékenységek

Az **adatlekérési** tevékenységek adatokat kérnek le az adatbázisból. A különböző tranzakciók adapterei különböző tranzakciótáblákból származó adatok beolvasására érhetők el:

- AxClass/TaxIntegration **PurchTable** DataRetrieval
- AxClass/TaxIntegration **PurchParmTable** DataRetrieval
- AxClass/TaxIntegration **PurchREQTable** DataRetrieval
- AxClass/TaxIntegration **PurchRFQTable** DataRetrieval
- AxClass/TaxIntegration **VendInvoiceInfoTable** DataRetrieval
- AxClass/TaxIntegration **SalesTable** DataRetrieval
- AxClass/TaxIntegration **SalesParm** DataRetrieval

Ezekben az **Adatlekérési** tevékenységekben az adatok másolása történik az adatbázisból a `TaxIntegrationDocumentObject` és a `TaxIntegrationLineObject` elemekbe. Mivel ezek a tevékenységek kiterjesztik ugyanazt az absztrakt sablonosztályt, közös módszereik vannak.

#### <a name="calculation-service-activities"></a>Számítási szolgáltatás tevékenységek

A **Számítási szolgáltatás** tevékenység egy kapcsolat az adószolgáltatás és az adóintegráció között. Ez a tevékenység a következő funkciókért felelős:

1. A kérelem létrehozása.
2. A kérelem feladása az adószolgáltatásba.
3. Választ kap z adószolgáltatásból.
4. A válasz elemzése.

A kérelemhez hozzáadott adatmező a többi metaadattal együtt lesz feladva. 

## <a name="extension-implementation"></a>Kiterjesztés megvalósítása

Ez a szakasz részletes lépéseket tartalmaz, amelyek ismertetik a bővítmény megvalósításának lépéseit. Példaként a **Költségközpont** és a **Projekt** pénzügyi dimenzióit használja.

### <a name="step-1-add-the-data-variable-in-the-object-class"></a>1. lépés Az adatváltozó hozzáadása az objektumosztályhoz

Az objektumosztály tartalmazza az adatváltozót és az adat beolvasó/beállító metódusait. Adja hozzá az adatmezőt a `TaxIntegrationDocumentObject` vagy `TaxIntegrationLineObject` elemhez a mező szintjétől függően. A következő példa a sorszintet használja, a fájlnév `TaxIntegrationLineObject_Extension.xpp`.

> [!NOTE]
> Ha a hozzáadott adatmező dokumentumszinten van, módosítsa a fájl nevét `TaxIntegrationDocumentObject_Extension.xpp` névre.

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

A **Költségközpont** és a **Projekt** privát változóként kerül hozzáadásra. Hozzon létre beolvasó és beállító metódusokat ezekhez az adatmezőkhöz az adatok manipulálásához.

### <a name="step-2-retrieve-data-from-the-database"></a>2. lépés Adatok lekérése az adatbázisból

Határozza meg a tranzakciót, és bővítse ki a megfelelő adapterosztályokat az adatok beolvasása érdekében. Ha például egy **Beszerzési rendelési** tranzakciót használ, ki kell terjesztenie a `TaxIntegrationPurchTableDataRetrieval` és `TaxIntegrationVendInvoiceInfoTableDataRetrieval` értékeket. 

> [!NOTE]
> A `TaxIntegrationPurchParmTableDataRetrieval` öröklődik a `TaxIntegrationPurchTableDataRetrieval` értékből. Nem szabad megváltoztatni, kivéve, ha a logika a `purchTable` és a `purchParmTable` táblákban eltér.

Ha az adatmezőt minden tranzakcióhoz hozzá kell adni, bővítse ki az összes `DataRetrieval` osztályt.

Mivel minden **Adatlekérési** tevékenység ugyanazt a sablonosztályt bővíti ki, az osztálystruktúrák, a változók és a metódusok hasonlóak.

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

A következő az alapszerkezetet mutatja be a `PurchTable` tábla használata esetén.

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

A `CopyToDocument` metódus meghívásakor a `this.purchTable` puffer már létezik. Ennek a metódusnak az a célja, hogy a `DocumentObject` osztályban létrehozott beállítási módszerrel a `this.purchTable` tábla összes szükséges adatát átmásolja a `document` objektumba.

Hasonlóképpen, a `this.purchLine` puffer már létezik a `CopyToLine` metódusban. Ennek a metódusnak az a célja, hogy a `LineObject` osztályban létrehozott beállítási módszerrel a `this.purchLine` tábla összes szükséges adatát átmásolja a `_line` objektumba.

A legegyértelműbb megközelítés az, hogy `CopyToDocument` és a `CopyToLine` metódusokat kiterjesztik. Javasoljuk azonban, hogy először próbálja ki a `copyToDocumentFromHeaderTable` és a `copyToLineFromLineTable` metódusokat. Ha nem úgy működnek, ahogy szeretné, implementálja a saját metódusát, és hívja be a `CopyToDocument` és `CopyToLine` metódusokban. Három gyakori helyzet van, amikor ezt a megközelítést használhatja:

- A szükséges mező `PurchTable` vagy `PurchLine`. Ebben a helyzetben kiterjesztheti a `copyToDocumentFromHeaderTable` és `copyToLineFromLineTable` metódusokat. Itt található a mintakód.

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

- A szükséges adatok nincsenek a tranzakció alapértelmezett táblájában. Vannak azonban csatlakoztatás kapcsolatok az alapértelmezett táblával, és erre a mezőre a legtöbb sorban szükség van. Ebben az esetben cserélje le a `getDocumentQueryObject` vagy `getLineObject` objektumot a tábla lekérdezéséhez az egyesítés kapcsolattal. A következő példában a **Szállítás most** mező integrálva van az értékesítési rendeléssel sor szinten.

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

    Ebben a példában egy `mcrSalesLineDropShipment` puffer van deklarálva, és a lekérdezés a `getLineQueryObject` objektumban van definiálva. A lekérdezés a `MCRSalesLineDropShipment.SalesLine == SalesLine.RecId` kapcsolatot használja. A helyzet kibővítése során lecserélheti a `getLineQueryObject` objektumot a saját létrehozott lekérdezésére. Azonban vegye figyelembe a következő pontokat:

    * Mivel a `getLineQueryObject` metódus visszatérési értéke `SysDaQueryObject`, ezt az objektumot a SysDa megközelítéssel kell létrehoznia.
    * A létező tábla nem távolítható el.

- A szükséges adatok bonyolult illesztési kapcsolattal kapcsolódnak a tranzakciós táblához, vagy a kapcsolat nem egy az egyhez (1:1), hanem egy a sokhoz (1:N). Ebben a helyzetben a dolgok egy kicsit bonyolulttá válnak. Ez a helyzet a pénzügyi dimenziók példájára vonatkozik. 

    Ebben az esetben saját metódust valósíthat meg az adatok beolvasására. Itt van a mintakód a `TaxIntegrationPurchTableDataRetrieval_Extension.xpp` fájlban.

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

### <a name="step-3-add-data-to-the-request"></a>3. lépés Adatok hozzáadása a kérelemhez

Terjessza ki a `copyToTaxableDocumentHeaderWrapperFromTaxIntegrationDocumentObject` vagy `copyToTaxableDocumentLineWrapperFromTaxIntegrationLineObjectByLine` metódust az adatok hozzáadásához a kérelemhez. Itt van a mintakód a `TaxIntegrationCalculationActivityOnDocument_CalculationService_Extension.xpp` fájlban.

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

Ebben a kódban a `_destination` a burkoló objektum, amely a közzétételi kérés létrehozásához használható, és a `_source` a `TaxIntegrationLineObject` objektum. 

> [!NOTE]
> * Adja meg a kérelem űrlapon használt kulcsot, mint `private const str`.
> * Állítsa be a mezőt a `copyToTaxableDocumentLineWrapperFromTaxIntegrationLineObjectByLine` metódusban a `SetField` metódus használatával. A második paraméter adattípusának `string` típusúnak kell lennie: Ha az adattípus nem, `string` konvertálja azt `string` típusúra.

## <a name="appendix"></a>Melléklet

Ez a függelék a pénzügyi dimenziók (**Költségközpont** és **Projekt**) sorszintű integrálásához szükséges teljes mintakódot mutatja.

### <a name="taxintegrationlineobject_extensionxpp"></a>TaxIntegrationLineObject_Extension.xpp

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

### <a name="taxintegrationpurchtabledataretrieval_extensionxpp"></a>TaxIntegrationPurchTableDataRetrieval_Extension.xpp

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

### <a name="taxintegrationcalculationactivityondocument_calculationservice_extensionxpp"></a>TaxIntegrationCalculationActivityOnDocument_CalculationService_Extension.xpp

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
