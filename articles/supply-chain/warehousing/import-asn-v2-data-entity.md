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
ms.openlocfilehash: 8f3c42e28b01afd3b7ca8b1af8381dd5377e17eb31da655a397bd7805779f879
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6751697"
---
# <a name="import-inbound-asns-through-the-v2-data-entity"></a>Bejövő ASN-ek importálása a V2 adatentitáson keresztül

[!include [banner](../../includes/banner.md)]

A speciális szállítási értesítések (ASN-ek) a szállítók kézbesítéséről adnak értesítést. Segítenek a feladónak a szállítmány tartalmának leírásában és további információk nyújtásában (például a cikkekről vagy a csomagolásról).

Az ASN-ek segítségével a raktári dolgozók áttekintheti, hogy mi mikor érkezik, akik így felkészülhetnek. Ezenkívül a raktári dolgozók az ASN-ek használatával egyeztethetik a szállítmány részleteit a korábban létrehozott kapcsolódó beszerzési rendeléssel.

Ez a témakör olyan forgatókönyvek gyűjteményét tartalmazza, amelyek példákon keresztül mutatják be az ASN-fájlokkal végzett munkát.

> [!IMPORTANT]
> *A bejövő ASN-ek* importálása csak a speciális raktárkezelési modulban (WMS) engedélyezett cikkekkel használható. Az ASN-ek fogadása előtt egy beszerzési rendelést regisztrálni kell a rendszerben az adott ASN-t küldő szállítóra vonatkozóan.

## <a name="inbound-asn-v2-entity"></a>Bejövő ASN V2 entitás

Bejövő ASN-eket importál a *Bejövő ASN V2* összetett adatentitással. A *Bejövő ASN V2* a következő entitásokat használja:

- Bejövő rakományfejléc
- Bejövő szállítmányfejléc
- Bejövő rakomány csomagolási szerkezetei
- Bejövő rakományok csomagolási szerkezetének esetei
- Bejövő rakományok csomagolási szerkezetének esetsorai
- Bejövő rakományok csomagolási szerkezetének sorai

A *Bejövő ASN V2* összetett adatentitás aszinkron integrációs forgatókönyvekhez készült, ahol XML-fájlokon alapuló importálást kell használni.

## <a name="xml-format-for-importing-asns"></a>Az ASN-ek importálásához használatos XML-formátum

A Microsoft Dynamics 365 Supply Chain Management a következő XML-formátumot támogatja az ASN-k importálásához. Az XML-fájl minden csomópontja egy adott entitás valamelyik attribútumát jelöli.

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

## <a name="examples"></a>Példák

A következő alfejezetekben a szállítói szállítmányok ASN XML-importálási fájljaira talál példákat.

### <a name="example-1"></a>1. példa

A következő példában lévő XML-fájl azt mutatja be, hogyan importálhatók a szállítói szállítmányok a beszerzési rendeléshez, ha nincsenek esetadatok.

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

### <a name="example-2"></a>2. példa

A következő példában lévő XML-fájl azt mutatja be, hogyan importálhatók a szállítói szállítmányok a beszerzési rendeléshez, ha vannak esetadatok.

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

### <a name="example-3"></a>3. példa

A következő példában lévő XML-fájl azt mutatja be, hogyan importálhatók a szállítói szállítmányok több beszerzési rendeléshez, ha vannak esetadatok.

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

## <a name="inspect-the-results-of-importing-an-asn-file"></a>ASN-fájlimportálás eredményeinek ellenőrzése

Az ASN-fájlok importálásának eredményeit az alábbi lépésekkel tekintheti át.

1. Lépjen a **Raktárkezelés \> Rakományok \> Minden rakomány** elemhez.
1. Keressen és nyisson meg egy olyan terhelést, amelyet ASN-importálás részeként hoztak létre.
1. A **Betöltés** gyorslapon az XML-fájlon alapuló értékeket kell látnia.
1. A **Rakománysorok** gyorslapon meg kell jelennie a beszerzési rendelések számának és az XML-fájlon alapuló cikkadatoknak.
1. A Művelet panelen, a **Szállítás és fogadás** lap **Fogadás** csoportjában lévő **Csomagolási struktúra** elem kiválasztásával tekintheti át a rakomány csomagolási szerkezetét.
1. A **Raklapok** gyorslapon az XML-fájlon alapuló azonosítótáblákat kell látnia.
1. A **Rekeszek** gyorslapon az XML-fájlon alapuló rekeszeket kell látnia.
1. A **Cikkek** gyorslapon az XML-fájlon alapuló cikkeket és mennyiségeket kell látnia.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
