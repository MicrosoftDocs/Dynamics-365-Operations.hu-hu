---
title: Bejövő ASN-ek importálása a V2 adatentitáson keresztül
description: Ez a témakör áttekinti a bejövő speciális szállítási értesítések (ASN-ek) Bejövő ASN V2 adatentitáson keresztül történő importálását.
author: GalynaFedorova
ms.date: 05/31/2021
ms.topic: article
ms.search.form: WHSInboundASNV2Entity, WHSInboundASNEntity
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-06-04
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 470cc0c39f211a5d0f106c4c6e193867388e2b53
ms.sourcegitcommit: e6437d994c3be0c5bb4a9263af3aa8351020d83a
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/14/2021
ms.locfileid: "6249111"
---
# <a name="import-inbound-asns-through-the-v2-data-entity"></a><span data-ttu-id="3faa3-103">Bejövő ASN-ek importálása a V2 adatentitáson keresztül</span><span class="sxs-lookup"><span data-stu-id="3faa3-103">Import inbound ASNs through the V2 data entity</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="3faa3-104">A speciális szállítási értesítések (ASN-ek) a szállítók kézbesítéséről adnak értesítést.</span><span class="sxs-lookup"><span data-stu-id="3faa3-104">Advanced shipping notices (ASNs) notify you about vendor deliveries.</span></span> <span data-ttu-id="3faa3-105">Segítenek a feladónak a szállítmány tartalmának leírásában és további információk nyújtásában (például a cikkekről vagy a csomagolásról).</span><span class="sxs-lookup"><span data-stu-id="3faa3-105">They help the sender describe the contents of a shipment and additional information about it, such as the items and packaging.</span></span>

<span data-ttu-id="3faa3-106">Az ASN-ek segítségével a raktári dolgozók áttekintheti, hogy mi mikor érkezik,</span><span class="sxs-lookup"><span data-stu-id="3faa3-106">ASNs can help warehouse workers learn what is arriving when.</span></span> <span data-ttu-id="3faa3-107">akik így felkészülhetnek.</span><span class="sxs-lookup"><span data-stu-id="3faa3-107">Therefore, they can prepare.</span></span> <span data-ttu-id="3faa3-108">Ezenkívül a raktári dolgozók az ASN-ek használatával egyeztethetik a szállítmány részleteit a korábban létrehozott kapcsolódó beszerzési rendeléssel.</span><span class="sxs-lookup"><span data-stu-id="3faa3-108">In addition, warehouse workers can use ASNs to match the details of a shipment to the related purchase order that was previously created.</span></span>

<span data-ttu-id="3faa3-109">Ez a témakör olyan forgatókönyvek gyűjteményét tartalmazza, amelyek példákon keresztül mutatják be az ASN-fájlokkal végzett munkát.</span><span class="sxs-lookup"><span data-stu-id="3faa3-109">This topic presents a collection of scenarios that show, through examples, how to work with ASN files.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3faa3-110">*A bejövő ASN-ek* importálása csak a speciális raktárkezelési modulban (WMS) engedélyezett cikkekkel használható.</span><span class="sxs-lookup"><span data-stu-id="3faa3-110">*Inbound ASN* import applies only to items that are enabled for advanced warehouse management (WMS).</span></span> <span data-ttu-id="3faa3-111">Az ASN-ek fogadása előtt egy beszerzési rendelést regisztrálni kell a rendszerben az adott ASN-t küldő szállítóra vonatkozóan.</span><span class="sxs-lookup"><span data-stu-id="3faa3-111">Before you receive an ASN, a purchase order must be registered in the system against the vendor who is sending that ASN.</span></span>

## <a name="inbound-asn-v2-entity"></a><span data-ttu-id="3faa3-112">Bejövő ASN V2 entitás</span><span class="sxs-lookup"><span data-stu-id="3faa3-112">Inbound ASN V2 entity</span></span>

<span data-ttu-id="3faa3-113">Bejövő ASN-eket importál a *Bejövő ASN V2* összetett adatentitással.</span><span class="sxs-lookup"><span data-stu-id="3faa3-113">You import inbound ASNs by using the *Inbound ASN V2* composite data entity.</span></span> <span data-ttu-id="3faa3-114">A *Bejövő ASN V2* a következő entitásokat használja:</span><span class="sxs-lookup"><span data-stu-id="3faa3-114">*Inbound ASN V2* takes advantage of the following entities:</span></span>

- <span data-ttu-id="3faa3-115">Bejövő rakományfejléc</span><span class="sxs-lookup"><span data-stu-id="3faa3-115">Inbound load header</span></span>
- <span data-ttu-id="3faa3-116">Bejövő szállítmányfejléc</span><span class="sxs-lookup"><span data-stu-id="3faa3-116">Inbound shipment header</span></span>
- <span data-ttu-id="3faa3-117">Bejövő rakomány csomagolási szerkezetei</span><span class="sxs-lookup"><span data-stu-id="3faa3-117">Inbound load packing structures</span></span>
- <span data-ttu-id="3faa3-118">Bejövő rakományok csomagolási szerkezetének esetei</span><span class="sxs-lookup"><span data-stu-id="3faa3-118">Inbound load packing structure cases</span></span>
- <span data-ttu-id="3faa3-119">Bejövő rakományok csomagolási szerkezetének esetsorai</span><span class="sxs-lookup"><span data-stu-id="3faa3-119">Inbound load packing structure case lines</span></span>
- <span data-ttu-id="3faa3-120">Bejövő rakományok csomagolási szerkezetének sorai</span><span class="sxs-lookup"><span data-stu-id="3faa3-120">Inbound load packing structure lines</span></span>

<span data-ttu-id="3faa3-121">A *Bejövő ASN V2* összetett adatentitás aszinkron integrációs forgatókönyvekhez készült, ahol XML-fájlokon alapuló importálást kell használni.</span><span class="sxs-lookup"><span data-stu-id="3faa3-121">The *Inbound ASN V2* composite data entity is intended for asynchronous integration scenarios where XML file–based imports are used.</span></span>

## <a name="xml-format-for-importing-asns"></a><span data-ttu-id="3faa3-122">Az ASN-ek importálásához használatos XML-formátum</span><span class="sxs-lookup"><span data-stu-id="3faa3-122">XML format for importing ASNs</span></span>

<span data-ttu-id="3faa3-123">A Microsoft Dynamics 365 Supply Chain Management a következő XML-formátumot támogatja az ASN-k importálásához.</span><span class="sxs-lookup"><span data-stu-id="3faa3-123">Microsoft Dynamics 365 Supply Chain Management supports the following XML format for importing ASNs.</span></span> <span data-ttu-id="3faa3-124">Az XML-fájl minden csomópontja egy adott entitás valamelyik attribútumát jelöli.</span><span class="sxs-lookup"><span data-stu-id="3faa3-124">Each node in the XML file represents an attribute from an individual entity.</span></span>

```xml
<?xml version="1.0" encoding="utf-8"?>
<Document>
    <WHSInboundLoadHeaderEntity>
        <WHSInboundShipmentHeaderEntity>
            <WHSInboundLoadPackingStructureEntity>
                <WHSInboundLoadPackingStructureCaseEntity>
                    <WHSInboundPackingStructureCaseLineV2Entity>
                    </WHSInboundPackingStructureCaseLineV2Entity>
                </WHSInboundLoadPackingStructureCaseEntity>
                <WHSInboundLoadPackingStructureLineV2Entity>
                </WHSInboundLoadPackingStructureLineV2Entity>
            </WHSInboundLoadPackingStructureEntity>
        </WHSInboundShipmentHeaderEntity>
    </WHSInboundLoadHeaderEntity>
</Document>
```

## <a name="examples"></a><span data-ttu-id="3faa3-125">Példák</span><span class="sxs-lookup"><span data-stu-id="3faa3-125">Examples</span></span>

<span data-ttu-id="3faa3-126">A következő alfejezetekben a szállítói szállítmányok ASN XML-importálási fájljaira talál példákat.</span><span class="sxs-lookup"><span data-stu-id="3faa3-126">The following subsections provide examples of ASN XML import files for vendor shipments.</span></span>

### <a name="example-1"></a><span data-ttu-id="3faa3-127">1. példa</span><span class="sxs-lookup"><span data-stu-id="3faa3-127">Example 1</span></span>

<span data-ttu-id="3faa3-128">A következő példában lévő XML-fájl azt mutatja be, hogyan importálhatók a szállítói szállítmányok a beszerzési rendeléshez, ha nincsenek esetadatok.</span><span class="sxs-lookup"><span data-stu-id="3faa3-128">The following example shows an XML file for importing vendor shipments for one purchase order when no case details are included.</span></span>

```xml
<?xml version="1.0" encoding="utf-8"?>
<Document>
    <WHSInboundLoadHeaderEntity TRACTORNUMBER="0000101">
        <WHSInboundShipmentHeaderEntity VENDORSHIPMENTID="VendASN_01" VENDORADDRESSCOUNTRYREGIONID = "USA" VENDORADDRESSSTREET = "123 Coffee Street" VENDORADDRESSSTATEID = "WA" VENDORADDRESSCITY = "Redmond" VENDORADDRESSZIPCODE = "98052">
            <WHSInboundLoadPackingStructureEntity LICENSEPLATENUMBER="LP_ASN_001">
                <WHSInboundLoadPackingStructureLineV2Entity PURCHASEORDERNUMBER="00000176" ITEMNUMBER="A0001" QUANTITY="1" UNITSYMBOL="ea" />
            </WHSInboundLoadPackingStructureEntity>
        </WHSInboundShipmentHeaderEntity>
    </WHSInboundLoadHeaderEntity>
</Document>
```

### <a name="example-2"></a><span data-ttu-id="3faa3-129">2. példa</span><span class="sxs-lookup"><span data-stu-id="3faa3-129">Example 2</span></span>

<span data-ttu-id="3faa3-130">A következő példában lévő XML-fájl azt mutatja be, hogyan importálhatók a szállítói szállítmányok a beszerzési rendeléshez, ha vannak esetadatok.</span><span class="sxs-lookup"><span data-stu-id="3faa3-130">The following example shows an XML file for importing vendor shipments for one purchase order when case details are included.</span></span>

```xml
<?xml version="1.0" encoding="utf-8"?>
<Document>
    <WHSInboundLoadHeaderEntity ESTIMATEDARRIVALDATETIME="2021-04-25T11:00:00+00:00">
        <WHSInboundShipmentHeaderEntity VENDORSHIPMENTID="MVR_SNN_0004">
            <WHSInboundLoadPackingStructureEntity LICENSEPLATENUMBER="MVR_SNN_0004" PACKEDTOTALQUANTITY="2.00">
                <WHSInboundLoadPackingStructureCaseEntity PARENTPACKINGSTRUCTURELICENSEPLATENUMBER="MVR_SNN_0004" LICENSEPLATENUMBER="MVR_SNN_0004A" PACKEDTOTALQUANTITY="2.00" />
                <WHSInboundLoadPackingStructureLineV2Entity PURCHASEORDERNUMBER="00000175" ITEMNUMBER="A0001" PURCHASEORDERLINENUMBER="1" QUANTITY="2.00" UNITSYMBOL="ea" />
            </WHSInboundLoadPackingStructureEntity>
        </WHSInboundShipmentHeaderEntity>
    </WHSInboundLoadHeaderEntity>
</Document>
```

### <a name="example-3"></a><span data-ttu-id="3faa3-131">3. példa</span><span class="sxs-lookup"><span data-stu-id="3faa3-131">Example 3</span></span>

<span data-ttu-id="3faa3-132">A következő példában lévő XML-fájl azt mutatja be, hogyan importálhatók a szállítói szállítmányok több beszerzési rendeléshez, ha vannak esetadatok.</span><span class="sxs-lookup"><span data-stu-id="3faa3-132">The following example shows an XML file for importing vendor shipments for multiple purchase orders when case details are included.</span></span>

```xml
<?xml version="1.0" encoding="utf-8"?>
<Document>
    <WHSInboundLoadHeaderEntity TRACTORNUMBER="0000101">
        <WHSInboundShipmentHeaderEntity VENDORSHIPMENTID="VendASN_01" VENDORADDRESSCOUNTRYREGIONID = "USA" VendorAddressStreet = "123 Coffee Street" VENDORADDRESSSTATEID = "WA" VENDORADDRESSCITY = "Redmond" VENDORADDRESSZIPCODE = "98052">
            <WHSInboundLoadPackingStructureEntity LICENSEPLATENUMBER="LP_ASN_001">
                <WHSInboundLoadPackingStructureLineV2Entity PURCHASEORDERNUMBER="00000176" ITEMNUMBER="A0001" QUANTITY="100" UNITSYMBOL="ea" />
            </WHSInboundLoadPackingStructureEntity>
        </WHSInboundShipmentHeaderEntity>
        <WHSInboundShipmentHeaderEntity VENDORSHIPMENTID="VendASN_02" VENDORADDRESSCOUNTRYREGIONID = "USA" VendorAddressStreet = "123 Coffee Street" VENDORADDRESSSTATEID = "WA" VENDORADDRESSCITY = "Redmond" VENDORADDRESSZIPCODE = "98052">
            <WHSInboundLoadPackingStructureEntity LICENSEPLATENUMBER="LP_ASN_001">
                <WHSInboundLoadPackingStructureLineV2Entity PURCHASEORDERNUMBER="00000177" ITEMNUMBER="A0001" QUANTITY="200" UNITSYMBOL="ea" />
                <WHSInboundLoadPackingStructureLineV2Entity PURCHASEORDERNUMBER="00000177" ITEMNUMBER="P0004" QUANTITY="300" UNITSYMBOL="ea" ITEMBATCHNUMBER="BN0001" />
            </WHSInboundLoadPackingStructureEntity>
            <WHSInboundLoadPackingStructureEntity LICENSEPLATENUMBER="LP_ASN_002">
                <WHSInboundLoadPackingStructureCaseEntity LICENSEPLATENUMBER="LP_ASN_002_C01">
                    <WHSInboundLoadPackingStructureCaseLineV2Entity PURCHASEORDERNUMBER="00000177" ITEMNUMBER="A0001" QUANTITY="400" UNITSYMBOL="ea" />
                </WHSInboundLoadPackingStructureCaseEntity>
            </WHSInboundLoadPackingStructureEntity>
        </WHSInboundShipmentHeaderEntity>
    </WHSInboundLoadHeaderEntity>
</Document>
```

## <a name="inspect-the-results-of-importing-an-asn-file"></a><span data-ttu-id="3faa3-133">ASN-fájlimportálás eredményeinek ellenőrzése</span><span class="sxs-lookup"><span data-stu-id="3faa3-133">Inspect the results of importing an ASN file</span></span>

<span data-ttu-id="3faa3-134">Az ASN-fájlok importálásának eredményeit az alábbi lépésekkel tekintheti át.</span><span class="sxs-lookup"><span data-stu-id="3faa3-134">Follow these steps to inspect the results of importing an ASN file.</span></span>

1. <span data-ttu-id="3faa3-135">Lépjen a **Raktárkezelés \> Rakományok \> Minden rakomány** elemhez.</span><span class="sxs-lookup"><span data-stu-id="3faa3-135">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="3faa3-136">Keressen és nyisson meg egy olyan terhelést, amelyet ASN-importálás részeként hoztak létre.</span><span class="sxs-lookup"><span data-stu-id="3faa3-136">Find and open a load that was created as part of an ASN import.</span></span>
1. <span data-ttu-id="3faa3-137">A **Betöltés** gyorslapon az XML-fájlon alapuló értékeket kell látnia.</span><span class="sxs-lookup"><span data-stu-id="3faa3-137">On the **Load** FastTab, you should see values that are based on the XML file.</span></span>
1. <span data-ttu-id="3faa3-138">A **Rakománysorok** gyorslapon meg kell jelennie a beszerzési rendelések számának és az XML-fájlon alapuló cikkadatoknak.</span><span class="sxs-lookup"><span data-stu-id="3faa3-138">On the **Load lines** FastTab, you should see purchase order numbers and item details that are based on the XML file.</span></span>
1. <span data-ttu-id="3faa3-139">A Művelet panelen, a **Szállítás és fogadás** lap **Fogadás** csoportjában lévő **Csomagolási struktúra** elem kiválasztásával tekintheti át a rakomány csomagolási szerkezetét.</span><span class="sxs-lookup"><span data-stu-id="3faa3-139">On the Action Pane, on the **Ship and receive** tab, in the **Receive** group, select **Packing structure** to review the packing structure of the load.</span></span>
1. <span data-ttu-id="3faa3-140">A **Raklapok** gyorslapon az XML-fájlon alapuló azonosítótáblákat kell látnia.</span><span class="sxs-lookup"><span data-stu-id="3faa3-140">On the **Pallets** FastTab, you should see license plates that are based on the XML file.</span></span>
1. <span data-ttu-id="3faa3-141">A **Rekeszek** gyorslapon az XML-fájlon alapuló rekeszeket kell látnia.</span><span class="sxs-lookup"><span data-stu-id="3faa3-141">On the **Cases** FastTab, you should see cases that are based on the XML file.</span></span>
1. <span data-ttu-id="3faa3-142">A **Cikkek** gyorslapon az XML-fájlon alapuló cikkeket és mennyiségeket kell látnia.</span><span class="sxs-lookup"><span data-stu-id="3faa3-142">On the **Items** FastTab, you should see items and quantities that are based on the XML file.</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
