---
title: Egységes termékélmény
description: Ez a témakör a termékadatok integrációját ismerteti a Finance and Operations alkalmazások és a Common Data Service között.
author: t-benebo
manager: AnnBe
ms.date: 09/3/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 9dc26e0e50c0b77555d09e4a50b846c80b1d5760
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/30/2019
ms.locfileid: "2249328"
---
# <a name="unified-product-experience"></a>Egységes termékélmény

[!include [banner](../includes/banner.md)]

[!include [preview](../includes/preview-banner.md)]

Ha egy üzleti ökoszisztéma Dynamics 365 alkalmazásokból áll, mint például a Finance, a Supply Chain Management és a Sales, akkor az természetes a vevők számára, hogy ezeket az alkalmazásokat használják a termék adatainak forrásának. Ennek az az oka, hogy ezek az alkalmazások megbízható termék-infrastruktúrát biztosítanak, kiegészítve a kifinomult árképzési koncepciókkal és az aktuális készlet pontos adataival. Azoknak a vevőknek, akik egy külső Termékéletciklus-kezelő (PLM) rendszert használnak a termék adatainak lekéréséhez, a termékeket becsatornázhatják a Finance and Operations alkalmazásokból más Dynamics 365 alkalmazásokba. Az egységes termék élmény az integrált termékadat-modellt elérhetővé teszi a Common Data Service szolgáltatásban, így az alkalmazás minden felhasználója, beleértve a Power Platform felületet is igénybe veheti Finance and Operations alkalmazáskból származó fejlett termékadatokat.

Itt a termék adatmodellje a Sales megoldásból.

![Adatmodell Sales termékekhez](media/dual-write-product-4.jpg)

Itt a Finance and Operations alkalmazások termék adatmodellje.

![A Finance and Operations termékeinek adatmodellje](media/dual-write-products-5.jpg)

Ez a két termékadat-modell integrálva lett a Common Data Service szolgáltatásba az alábbiakban látható módon.

![Adatmodell a Dynamics 365 alkalmazások termékeihez](media/dual-write-products-6.jpg)

A termékekhez kapcsolódó kettős írású entitásleképezések csak egyirányú adatátvitelre vannak tervezve, és ez csaknem valós idejű élmény a Finance and Operations és a Common Data Service között. A termék-infrastruktúra azonban nyitott, hogy szükség esetén kétirányú lehessen. A vevők saját felelősségükre testreszabhatják, mivel a Microsoft nem javasolja ezt a megközelítést.

## <a name="templates"></a>Sablonok

A termékinformációk tartalmazzák a termékhez és annak meghatározásához kapcsolódó összes információt, például a termék dimenzióit, illetve a nyomon követési és tárolási dimenziókat. A következő táblázat bemutatja a termékek és a kapcsolódó információk szinkronizálására létrehozott entitás-leképezések gyűjteményét.

Finance and Operations | Egyéb Dynamics 365 alkalmazások
-----------------------|--------------------------------
Kiadott termékek V2 | msdyn\_sharedproductdetails
Kiadott CDS-egyedi termékek | Termék
Termékszám alapján azonosított vonalkód | msdyn\_productbarcodes
Alapértelmezett rendelésbeállítások | msdyn\_productdefaultordersettings
Termékspecifikus alapértelmezett rendelésbeállítások | msdyn_productspecificdefaultordersettings
Termékdimenzió-csoportok | msdyn\_productdimensiongroups
Tárolásidimenzió-csoportok | msdyn\_productstoragedimensiongroups
Nyomonkövetésidimenzió-csoportok | msdyn\_producttrackingdimensiongroups
Színek | msdyn\_productcolors
Méretek | msdyn\_productsizes
Stílusok | msdyn\_productsytles
Konfigurációk | msdyn\_productconfigurations
Alaptermékszínek | msdyn_sharedproductcolors
Alaptermékméretek | msdyn_sharedproductsizes
Alaptermékstílusok | msdyn_sharedproductstyles
Alaptermék-konfigurációk | msdyn_sharedproductconfigurations
Minden termék | msdyn_globalproducts
Egység | uoms
Egységek átváltása | msdyn_ unitofmeasureconversions
Termékspecifikus mértékegység-átváltás | msdyn_productspecificunitofmeasureconversion
Webhelyek | msdyn\_operationalsites
Raktárak | msdyn\_inventwarehouses

[!include [symbols](../includes/dual-write-symbols.md)]

## <a name="integration-of-products"></a>Termékek integrálása

Ebben a modellben a termék a következő két entitás kombinációjával van ábrázolva a Common Data Service: **Termék** és **msdyn\_sharedproductdetails** helyeken. Ahol az első egység a termék definícióját tartalmazza (a termék egyedi azonosítója, a termék neve és a leírás), a második entitás a termék szintjén tárolt mezőket tartalmazza. Ennek a két entitásnak a kombinációja a terméknek a készletezési egység (SKU) fogalma alapján történő meghatározására szolgál. Minden kiadott termék adatai megjelennek az említett entitásokban (Termék és Megosztott termék részletei). Az összes termék nyomon követésére (kiadott és nem kiadott) a **Globális termék** entitás használatos. 

Mivel a termék SKU-ként képviselteti magát, az egyedi termékek, alaptermékek és termékváltozatok koncepciója a következő módon rögzíthető Common Data Service szolgáltatásban:

- **A termékek altípus termékkel rendelkező termékek** saját maguk által meghatározott termékek. Nem kell definiálni dimenziókat ezekhez. Egy példa erre egy meghatározott könyv. Ezeknél a termékeknél egy rekord jön létre a **Termék** entitásban, és egy rekord jön létre a **msdyn\_sharedproductdetails** entitásban. Nem jön létre termékcsaládrekord.
- Az **Alaptermékek** általános termékként használatosak, amelyek meghatározzák az üzleti folyamatokban történő működéséthez kapcsolódó definíciókat és szabályokat. Ezeknek a definícióknak alapján egyedei termékeket lehet létrehozni, amelyek a termék változatát jelentik. Például a póló az alaptermék, és a szín és a méret dimenzióként is megadható. A változatok adhatók ki, amelyek ezen dimenziók különböző kombinációi, például a kis kék póló vagy egy közepes zöld póló. Az integrációban egy rekord jön létre változatonként a terméktáblában. Ez a rekord tartalmazza a változatspecifikus adatokat, például a különböző dimenziókat. A termék általános információinak tárolása a **msdyn\_sharedproductdetails** entitásban történik. (Ez az általános információ az alaptermékben található.) Ezenkívül egy termékcsalád-rekord készül alaptermékenként. Az alaptermék adatait a rendszer szinkronizálja Common Data Service szolgáltatásba a kiadott alaptermék létrehozásával (de a változatok megjelenése előtt).
- Az **Egyedi termékek** a termékek a termék összes altípusára és az összes termékváltozatra utalnak. 

![Adatmodell termékekhez](media/dual-write-product.png)

Ha a kettős írás funkció engedélyezve van, a Finance and Operations modul alkalmazásai szinkronizálva lesznek a többi Dynamics 365 alkalmazásban a **Vázlat** állapotban. Az első azonos pénznemű árlistához lesznek hozzáadva. Más szóval a Dynamics 365 alkalmazás első árlistájához lesznek hozzáadva amely megfelel annak a jogi személynek a pénznemének, ahol a termék ki van adva a Finance and Operations alkalmazásban. 

Ha azt szeretné, hogy az **Aktív** állapotú termék szinkronizálva legyen az értékesítési rendelések ajánlataiban akkor az alábbi beállítást kell választani: a **Rendszer > Adminisztráció > Rendszeradminisztráció > Rendszerbeállítások > Sales** alatt válassza a **Termékek létrehozása az aktív állapotban = igen** értéket. 

### <a name="cds-released-distinct-products-to-product"></a>A CDS egyedi termékeket adott ki a Termékhez

A **Termék** entitás a termék meghatározására szolgáló mezőket tartalmazza. Tartalmazza az egyedi termékeket (termék altípusú termékeket) és a termékváltozatokat. A következő táblázat a leképezéseket mutatja be.

Forrásmező | Térkép típusa | Célmező
---|---|---
PRODUCTNUMBER | >> | productnumber
PRODUCTNAME | >> | név
PRODUCTDESCRIPTION | >> | leírás
ITEMNUMBER | >> | msdyn_itemnumber
PÉNZNEMKÓD | >> | transactioncurrencyid.isocurrencycode
SALESUNITSYMBOL | >> | defaultuomid.msdyn_symbol
SALESPRICE | >> | ár
UNITCOST | >> | currentcost
PRODUCTTYPE | >> | producttypecode
SALESUNITDECIMALPRECISION | >> | quantitydecimal
ISCATCHWEIGHTPRODUCT | >> | msdyn_iscatchweight
PRODUCTCOLORID | >> | msdyn_productcolor.msdyn_productcolorname
PRODUCTCONFIGURATIONID | >> | msdyn_productconfiguration.msdyn_productconfiguration
PRODUCTSIZEID | >> | msdyn_productsize.msdyn_productsize
PRODUCTSTYLEID | >> | msdyn_productstyle.msdyn_productstyle

### <a name="released-products-v2-to-msdyn_sharedproductdetails"></a>Released products V2 to msdyn\_sharedproductdetails

A **msdyn\_sharedproductdetails** entitás tartalmazza a termék meghatározására szolgáló mezőket a Finance and Operations megoldásól, illetve ez tartalmazza a termék pénzügyi és vezetési információit. A következő táblázat a leképezéseket mutatja be.

Forrásmező | Térkép típusa | Célmező
---|---|---
PRODUCTNUMBER | > | msdyn_globalproduct.msdyn_productnumber
INTRASTATCHARGEPERCENTAGE | > | msdyn_intrastatchargepercentage
ITEMNUMBER | >> | msdyn_itemnumber
APPROXIMATESALESTAXPERCENTAGE | > | msdyn_approximatesalestaxpercentage
BESTBEFOREPERIODDAYS | > | msdyn_bestbeforeperioddays
CARRYINGCOSTABCCODE | >> | msdyn_carryingcostabccode
CONSTANTSCRAPQUANTITY | > | msdyn_constantscrapquantity
COSTCHARGESQUANTITY | > | msdyn_costchargesquantity
DEFAULTRECEIVINGQUANTITY | > | msdyn_defaultreceivingquantity
FIXEDPURCHASEPRICECHARGES | > | msdyn_fixedpurchasepricecharges
FIXEDSALESPRICECHARGES | > | msdyn_fixedsalespricecharges
GROSSDEPTH | > | msdyn_grossdepth
GROSSPRODUCTHEIGHT | > | msdyn_grossproductheight
GROSSPRODUCTWIDTH | > | msdyn_grossproductwidth
INVENTORYUNITSYMBOL | > | msdyn_inventoryunitsymbol.msdyn_symbol
ISDISCOUNTPOSREGISTRATIONPROHIBITED | >> | msdyn_isdiscountposregistrationprohibited
ISEXEMPTFROMAUTOMATICNOTIFICATIONANDCANCELLATION | >> | msdyn_exemptautomaticnotificationcancel
ISINSTALLMENTELIGIBLE | >> | msdyn_isinstallmenteligible
ISINTERCOMPANYPURCHASEUSAGEBLOCKED | >> | msdyn_isintercompanypurchaseusageblocked
ISINTERCOMPANYSALESUSAGEBLOCKED | >> | msdyn_isintercompanysalesusageblocked
ISMANUALDISCOUNTPOSREGISTRATIONPROHIBITED | >> | msdyn_ismanualdiscposregistrationprohibited
ISPHANTOM | >> | msdyn_isphantom
ISPOSREGISTRATIONBLOCKED | >> | msdyn_isposregistrationblocked
ISPOSREGISTRATIONQUANTITYNEGATIVE | >> | msdyn_isposregistrationquantitynegative
ISPURCHASEPRICEAUTOMATICALLYUPDATED | >> | msdyn_ispurchasepriceautomaticallyupdated
ISPURCHASEPRICEINCLUDINGCHARGES | >> | msdyn_ispurchasepriceincludingcharges
ISSALESWITHHOLDINGTAXCALCULATED | >> | msdyn_issaleswithholdingtaxcalculated
ISRESTRICTEDFORCOUPONS | >> | msdyn_isrestrictedforcoupons
ISSALESPRICEADJUSTMENTALLOWED | >> | msdyn_issalespriceadjustmentallowed
ISSALESPRICEINCLUDINGCHARGES | >> | msdyn_issalespriceincludingcharges
ISSCALEPRODUCT | >> | msdyn_isscaleproduct
ISSHIPALONEENABLED | >> | msdyn_isshipaloneenabled
ISUNITCOSTPRODUCTVARIANTSPECIFIC | >> | msdyn_isunitcostproductvariantspecific
ISVARIANTSHELFLABELSPRINTINGENABLED | >> | msdyn_isvariantshelflabelsprintingenabled
ISZEROPRICEPOSREGISTRATIONALLOWED | >> | msdyn_iszeropriceposregistrationallowed
KEYINPRICEREQUIREMENTSATPOSREGISTER | >> | msdyn_keyinpricerequirementsatposregister
KEYINQUANTITYREQUIREMENTSATPOSREGISTER | >> | msdyn_keyinquantityrequirementsatposregister
MARGINABCCODE | >> | msdyn_marginabccode
MAXIMUMPICKQUANTITY | > | msdyn_maximumpickquantity
MUSTKEYINCOMMENTATPOSREGISTER | >> | msdyn_mustkeyincommentatposregister
NECESSARYPRODUCTIONWORKINGTIMESCHEDULINGPROPERTYID | > | msdyn_necessaryproductionworkingtimeschedulingp
NETPRODUCTWEIGHT | > | msdyn_netproductweight
PACKINGDUTYQUANTITY | > | msdyn_packingdutyquantity
POSREGISTRATIONACTIVATIONDATE | > | msdyn_posregistrationactivationdate
POSREGISTRATIONBLOCKEDDATE | > | msdyn_posregistrationblockeddate
POSREGISTRATIONPLANNEDBLOCKEDDATE | > | msdyn_posregistrationplannedblockeddate
POTENCYBASEATTIBUTETARGETVALUE | > | msdyn_potencybaseattibutetargetvalue
POTENCYBASEATTRIBUTEVALUEENTRYEVENT | >> | msdyn_potencybaseattributevalueentryevent
PRODUCTTYPE | >> | msdyn_producttype
PRODUCTIONCONSUMPTIONDENSITYCONVERSIONFACTOR | > | msdyn_productionconsumptiondensityconversion
PRODUCTIONCONSUMPTIONDEPTHCONVERSIONFACTOR | > | msdyn_productionconsumptiondepthconversion
PRODUCTIONCONSUMPTIONHEIGHTCONVERSIONFACTOR | > | msdyn_productionconsumptionheightconversion
PRODUCTIONCONSUMPTIONWIDTHCONVERSIONFACTOR | > | msdyn_productionconsumptionwidthconversion
PRODUCTVOLUME | > | msdyn_productvolume
PURCHASECHARGESQUANTITY | > | msdyn_purchasechargesquantity
PURCHASEOVERDELIVERYPERCENTAGE | > | msdyn_purchaseoverdeliverypercentage
PURCHASEPRICE | > | msdyn_purchaseprice
PURCHASEPRICEDATE | > | msdyn_purchasepricedate
PURCHASEPRICINGPRECISION | > | msdyn_purchasepricingprecision
PURCHASEUNDERDELIVERYPERCENTAGE | > | msdyn_purchaseunderdeliverypercentage
RAWMATERIALPICKINGPRINCIPLE | >> | msdyn_rawmaterialpickingprinciple
SALESCHARGESQUANTITY | > | msdyn_saleschargesquantity
SALESOVERDELIVERYPERCENTAGE | > | msdyn_salesoverdeliverypercentage
SALESPRICE | > | msdyn_salesprice
SALESPRICECALCULATIONCHARGESPERCENTAGE | > | msdyn_salespricecalculationchargespercentage
SALESPRICECALCULATIONCONTRIBUTIONRATIO | > | msdyn_salespricecalculationcontributionratio
SALESPRICECALCULATIONMODEL | >> | msdyn_salespricecalculationmodel
SALESPRICEDATE | > | msdyn_salespricedate
SALESPRICINGPRECISION | > | msdyn_salespricingprecision
SALESUNDERDELIVERYPERCENTAGE | > | msdyn_salesunderdeliverypercentage
SALESUNITSYMBOL | > | msdyn_salesunitsymbol.msdyn_symbol
SCALEINDICATOR | >> | msdyn_scaleindicator
SELLSTARTDATE | > | msdyn_sellstartdate
SHELFADVICEPERIODDAYS | > | msdyn_shelfadviceperioddays
SHELFLIFEPERIODDAYS | > | msdyn_shelflifeperioddays
SHIPSTARTDATE | > | msdyn_shipstartdate
TAREPRODUCTWEIGHT | > | msdyn_tareproductweight
TRANSFERORDEROVERDELIVERYPERCENTAGE | > | msdyn_transferorderoverdeliverypercentage
TRANSFERORDERUNDERDELIVERYPERCENTAGE | > | msdyn_transferorderunderdeliverypercentage
UNITCOST | > | msdyn_unitcost
UNITCOSTDATE | > | msdyn_unitcostdate
UNITCOSTQUANTITY | > | msdyn_unitcostquantity
VARIABLESCRAPPERCENTAGE | > | msdyn_variablescrappercentage
WAREHOUSEMOBILEDEVICEDESCRIPTIONLINE1 | > | msdyn_warehousemobiledevicedescriptionline1
WAREHOUSEMOBILEDEVICEDESCRIPTIONLINE2 | > | msdyn_warehousemobiledevicedescriptionline2
WILLINVENTORYISSUEAUTOMATICALLYREPORTASFINISHED | >> | msdyn_willinventoryissueautoreportasfinished
WILLINVENTORYRECEIPTIGNOREFLUSHINGPRINCIPLE | >> | msdyn_willinventoryreceiptignoreflushing
WILLPICKINGWORKBENCHAPPLYBOXINGLOGIC | >> | msdyn_willpickingworkbenchapplyboxinglogic
WILLTOTALPURCHASEDISCOUNTCALCULATIONINCLUDEPRODUCT | >> | msdyn_willtotalpurchdiscountcalcincludeproduct
WILLTOTALSALESDISCOUNTCALCULATIONINCLUDEPRODUCT | >> | msdyn_willtotalsalesdiscountcalcincludeproduct
WILLWORKCENTERPICKINGALLOWNEGATIVEINVENTORY | >> | msdyn_willworkcenterpickingallownegativeinvent
YIELDPERCENTAGE | > | msdyn_yieldpercentage
ISUNITCOSTAUTOMATICALLYUPDATED | >> | msdyn_isunitcostautomaticallyupdated
PURCHASEUNITSYMBOL | > | msdyn_purchaseunitsymbol.msdyn_symbol
PURCHASEPRICEQUANTITY | > | msdyn_purchasepricequantity
ISUNITCOSTINCLUDINGCHARGES | >> | msdyn_isunitcostincludingcharges
FIXEDCOSTCHARGES | >> | msdyn_fixedcostcharges
MINIMUMCATCHWEIGHTQUANTITY | >> | msdyn_minimumcatchweightquantity
MAXIMUMCATCHWEIGHTQUANTITY | >> | msdyn_maximumcatchweightquantity
ALTERNATIVEITEMNUMBER | >> | msdyn_alternativeitemnumber.msdyn_itemnumber
BOMUNITSYMBOL | >> | msdyn_bomunitsymbol.msdyn_symbol
CATCHWEIGHTUNITSYMBOL | >> | msdyn_catchweightunitsymbol.msdyn_symbol
COMPARISONPRICEBASEUNITSYMBOL | >> | msdyn_comparisonpricebaseunitsymbol.msdyn_symbol
PRIMARYVENDORACCOUNTNUMBER | >> | msdyn_vendorid.msdyn_vendoraccountnumber
ISCATCHWEIGHTPRODUCT | >> | msdyn_iscatchweight
PRODUCTDIMENSIONGROUPNAME | >> | msdyn_productdimensiongroupid.msdyn_groupname

## <a name="all-product-to-msdyn_global-products"></a>Minden termék msdyn_global termékekhez

A minden termék entitás tartalmazza a Finance and Operations alkalmazások összes rendelkezésre álló termékét, a kiadott termékeket és a nem kiadott termékeket is. Ezek a termékek a következő hozzárendelések segítségével érhetők el a Common Data Service szolgáltatásban.

Forrásmező | Térkép típusa | Célmező
---|---|---
PRODUCTNAME | >> | msdyn_productname
PRODUCTNUMBER | >> | msdyn_productnumber

## <a name="product-dimensions"></a>Termékdimenziók 

Termékdimenziók olyan jellemzők, amelyek termékváltozat azonosítására szolgálnak. A négy termékdimenzió (szín, méret, stílus és konfiguráció) a termék változatának meghatározásához hozzá van hozzárendelve a Common Data Service szolgáltatáshoz is. A következő ábra a Szín cikkdimenzió adatmodelljét mutatja be. Ugyanez a modell a méretekre, stílusokra és a konfigurációkra is érvényes. 

![Adatmodell termékekhez](media/dual-write-product-2.PNG)

### <a name="colors"></a>Színek

A lehetséges színek a következő leképezéseken keresztül érhetők el Common Data Service szolgáltatásban.

Forrásmező | Térkép típusa | Célmező
---|---|---
COLORID | \>\> | msdyn\_productcolorname

### <a name="sizes"></a>Méretek

A lehetséges méretek a következő leképezéseken keresztül érhetők el Common Data Service szolgáltatásban.

Forrásmező | Térkép típusa | Célmező
---|---|---
SIZEID | \>\> | msdyn\_productsize

### <a name="styles"></a>Stílusok

A lehetséges stílusok a következő leképezéseken keresztül érhetők el Common Data Service szolgáltatásban.

Forrásmező | Térkép típusa | Célmező
---|---|---
STYLEID | \>\> | msdyn\_productstyle

### <a name="configurations"></a>Konfigurációk

A lehetséges konfigurációk a következő leképezéseken keresztül érhetők el Common Data Service szolgáltatásban.

Forrásmező | Térkép típusa | Célmező
---|---|---
CONFIGURATIONID | \>\> | msdyn\_name

Ha egy terméknek különböző a termékdimenziói vannak (például a az alaptermék mérete és szín termékdimenziók tartoznak), akkor mindegyik különböző termék (azaz a termék variánsa) ezen termékdimenziók kombinációja. A B0001 termékszámű termék például egy extra kis méretűfekete póló, és a B0002 termékszám egy kis fekete póló. Ebben az esetben a termékdimenziók meglévő kombinációinak meghatározása történik. Például az előző példából származó póló lehet extra kicsi és fekete, kicsi és fekete, közepes és fekete, illetve nagy és fekete, de nem lehet extra nagy és fekete. Más szóval az a termékdimenziók, amelyek az alaptermékhez tartozhatnak meghatározottak, és a változatokat ezen értékek alapján lehet kiadni.

Annak érdekében, hogy nyomon követhesse a termékdimenziókat, amit egy alaptermék felvehet a következő entitások jönnek létre és lesznek leképezve a Common Data Service szolgáltatásban az egyes termékdimenziókhoz. A további tudnivalókat lásd: [Termékinformációk áttekintése](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/pim/product-information).

### <a name="shared-product-color"></a>Megosztott termékszín

A **Megosztott termékszín** entitás azt jelzi, hogy egy adott alapterméknek milyen színei lehetnek. Ezt a koncepciót a program a Common Data Service szolgáltatásba is áthelyezi az adatok konzisztenciájának fenntartására. A következő táblázat a leképezéseket mutatja be.

Forrásmező | Térkép típusa | Célmező
---|---|---
PRODUCTCOLORID | \>\> | msdyn\_productcolorid.msdyn\_productcolorname
PRODUCTMASTERNUMBER | \>\> | msdyn\_sharedproductdetailid. msdyn\_itemnumber
REPLENISHMENTWEIGHT | \>\> | msdyn\_replenishmentweight
DISPLAYSEQUENCENUMBER | \>\> | msdyn\_retaildisplayorder

### <a name="shared-product-size"></a>Megosztott termékméret

A **Megosztott termékméret** entitás azt jelzi, hogy egy adott alapterméknek milyen méretei lehetnek. Ezt a koncepciót a program a Common Data Service szolgáltatásba is áthelyezi az adatok konzisztenciájának fenntartására. A következő táblázat a leképezéseket mutatja be.

Forrásmező | Térkép típusa | Célmező
---|---|---
PRODUCTMASTERNUMBER | \>\> | msdyn\_sharedproductdetailid. msdyn\_itemnumber
PRODUCTSIZEID | \>\> | msdyn\_productsizeid.msdyn\_productsize
REPLENISHMENTWEIGHT | \>\> | msdyn\_replenishmentweight
DISPLAYSEQUENCENUMBER | \>\> | msdyn\_displaysequencenumber

### <a name="shared-product-style"></a>Megosztott termékstílus

A **Megosztott termékstílus** entitás azt jelzi, hogy egy adott alapterméknek milyen stílusai lehetnek. Ezt a koncepciót a program a Common Data Service szolgáltatásba is áthelyezi az adatok konzisztenciájának fenntartására. A következő táblázat a leképezéseket mutatja be.

Forrásmező | Térkép típusa | Célmező
---|---|---
PRODUCTMASTERNUMBER | \>\> | msdyn\_sharedproductdetailsid.msdyn\_itemnumber
PRODUCTSTYLEID | \>\> | msdyn\_productstyleintegration
PRODUCTSTYLEID | \>\> | msdyn\_productstyleid.msdyn\_productstyle
REPLENISHMENTWEIGHT | \>\> | msdyn\_replenishmentweight
DISPLAYSEQUENCENUMBER | \>\> | msdyn\_displaysequencenumber

### <a name="shared-product-configuration"></a>Termékkonfiguráció megosztása

A **Megosztott termékkonfiguráció** entitás azt jelzi, hogy egy adott alapterméknek milyen konfigurációi lehetnek. Ezt a koncepciót a program a Common Data Service szolgáltatásba is áthelyezi az adatok konzisztenciájának fenntartására. A következő táblázat a leképezéseket mutatja be.

Forrásmező | Térkép típusa | Célmező
---|---|---
CONTAINERUNITSYMBOL | \>\> | msdyn\_containerunitsymbol
PRODUCTCONFIGURATIONID | \>\> | msdyn\_productconfigurationid.msdyn\_productconfiguration
PRODUCTMASTERNUMBER | \>\> | msdyn\_sharedproductdetailid. msdyn\_itemnumber
REPLENISHMENTWEIGHT | \>\> | msdyn\_replenishmentweight
DISPLAYSEQUENCENUMBER | \>\> | msdyn\_displaysequencenumber

## <a name="product-number-identifier-bar-codes"></a>Termékszámot azonosító vonalkódok

A termék vonalkódja a termékek egyedileg történő azonosítására szolgál. A termékvonalkódok a következő leképezések segítségével érhetők el a Common Data Service szolgáltatásban.

Forrásmező | Térkép típusa | Célmező
---|---|---
PRODUCTNUMBER | \> | msdyn\_productnumberid.productnumber
BARCODE | \> | msdyn\_name
BARCODE | \> | msdyn\_barcode
PRODUCTQUANTITY | \> | msdyn\_productquantity
PRODUCTDESCRIPTION | \> | msdyn\_productdescription
BARCODESETUPID | \> | msdyn\_barcodesetupid
PRODUCTQUANTITYUNITSYMBOL | \> | msdyn\_unitofmeasureid.name
ISDEFAULTSCANNEDBARCODE | \>\> | msdyn\_isdefaultscannedbarcode
ISDEFAULTPRINTEDBARCODE | \>\> | msdyn\_isdefaultprintedbarcode
ISDEFAULTDISPLAYEDBARCODE | \>\> | msdyn\_isdefaultdisplayedbarcode

## <a name="default-order-settings-and-product-specific-default-order-settings"></a>Alapértelmezett rendelési beállítások és termékspecifikus alapértelmezett rendelési beállítások

Az alapértelmezett rendelési beállítások határozzák meg azt a helyet és raktárt, ahol a cikkek beszerzése és tárolása történik, illetve azt a minimális, maximális, többszörös és szokásos mennyiséget, amely felhasználásra kerül a kereskedéshez vagy a készletgazdálkodáshoz, valamint az átfutási időket, a leállító jelzőket és a rendelési ígéret módszerét. Ezek az információk a CDS-ben az alapértelmezett rendelési beállításokkal és a termékre vonatkozó alapértelmezett rendelésbeállítások entitással lesznek elérhetők. További információ az [Alapértelmezett rendelési beállítások oldalon](https://docs.microsoft.com/en-us/dynamics365/unified-operations/supply-chain/production-control/default-order-settings)olvasható.

### <a name="default-order-settings"></a>Alapértelmezett rendelésbeállítások

Az alapértelmezett rendelési beállítások következő leképezések segítségével érhetők el a Common Data Service szolgáltatásban.

Forrásmező | Térkép típusa | Célmező
---|---|---
INVENTWAREHOUSEID | = | msdyn_inventorywarehouse.msdyn_warehouseidentifier
INVENTORYSITEID | = | msdyn_inventorysite.msdyn_siteid
INVENTORYATPDELAYEDDEMANDOFFSETDAYS | = | msdyn_inventoryatpdelayeddemandoffsetdays
INVENTORYATPDELAYEDSUPPLYOFFSETDAYS | = | msdyn_inventoryatpdelayedsupplyoffsetdays
ITEMNUMBER | = | msdyn_itemnumber.msdyn_itemnumber
INVENTORYATPBACKWARDDEMANDTIMEFENCEDAYS | = | msdyn_inventoryatpbackwarddemandtimefencedays
INVENTORYATPBACKWARDSUPPLYTIMEFENCEDAYS | = | msdyn_inventoryatpbackwardsupplytimefencedays
INVENTORYATPTIMEFENCEDAYS | = | msdyn_inventoryatptimefencedays
MAXIMUMINVENTORYORDERQUANTITY | = | msdyn_maximuminventoryorderquantity
MAXIMUMPROCUREMENTORDERQUANTITY | = | msdyn_maximumprocurementorderquantity
MAXIMUMSALESORDERQUANTITY | = | msdyn_maximumsalesorderquantity
MINIMUMINVENTORYORDERQUANTITY | = | msdyn_minimuminventoryorderquantity
MINIMUMPROCUREMENTORDERQUANTITY | = | msdyn_minimumprocurementorderquantity
MINIMUMSALESORDERQUANTITY | = | msdyn_minimumsalesorderquantity
STANDARDINVENTORYORDERQUANTITY | = | msdyn_standardinventoryorderquantity
STANDARDPROCUREMENTORDERQUANTITY | = | msdyn_standardprocurementorderquantity
STANDARDSALESORDERQUANTITY | = | msdyn_standardsalesorderquantity
INVENTORYLEADTIMEDAYS | = | msdyn_inventoryleadtimedays
INVENTORYQUANTITYMULTIPLES | = | msdyn_inventoryquantitymultiples
PROCUREMENTQUANTITYMULTIPLES | = | msdyn_procurementquantitymultiples
SALESQUANTITYMULTIPLES | = | msdyn_salesquantitymultiples
PROCUREMENTSITEID | = | msdyn_procurementsite.msdyn_siteid
PROCUREMENTLEADTIMEDAYS | = | msdyn_procurementleadtimedays
SALESSITEID | = | msdyn_salessite.msdyn_siteid
SALESATPDELAYEDDEMANDOFFSETDAYS | = | msdyn_salesatpdelayeddemandoffsetdays
SALESATPDELAYEDSUPPLYOFFSETDAYS | = | msdyn_salesatpdelayedsupplyoffsetdays
SALESATPBACKWARDDEMANDTIMEFENCEDAYS | = | msdyn_salesatpbackwarddemandtimefencedays
SALESATPBACKWARDSUPPLYTIMEFENCEDAYS | = | msdyn_salesatpbackwardsupplytimefencedays
SALESATPTIMEFENCEDAYS | = | msdyn_salesatptimefencedays
SALESLEADTIMEDAYS | = | msdyn_salesleadtimedays
PROCUREMENTWAREHOUSEID | = | msdyn_procurementwarehouse.msdyn_warehouseidentifier
SALESWAREHOUSEID | = | msdyn_saleswarehouse.msdyn_warehouseidentifier
AREINVENTORYORDERPROMISINGDEFAULTSOVERRIDDEN | >< | msdyn_areinventoryorderdefaultsoverridden
INVENTORYORDERPROMISINGMETHOD | >< | msdyn_inventoryorderpromisingmethod
ISINVENTORYATPINCLUDINGPLANNEDORDERS | >< | msdyn_isinventoryatpincludingplannedorders
ISINVENTORYUSINGWORKINGDAYS | >< | msdyn_isinventoryusingworkingdays
ISINVENTORYSITEMANDATORY | >< | msdyn_isinventorysitemandatory
ISINVENTORYPROCESSINGSTOPPED | >< | msdyn_isinventoryprocessingstopped
ISPROCUREMENTUSINGWORKINGDAYS | >< | msdyn_isprocurementusingworkingdays
ISPROCUREMENTSITEMANDATORY | >< | msdyn_isprocurementsitemandatory
ISPROCUREMENTPROCESSINGSTOPPED | >< | msdyn_isprocurementprocessingstopped
ARESALESORDERPROMISINGDEFAULTSOVERRIDDEN | >< | msdyn_aresalesorderdefaultsoverridden
SALESORDERPROMISINGMETHOD | >< | msdyn_salesorderpromisingmethod
ISSALESATPINCLUDINGPLANNEDORDERS | >< | msdyn_issalesatpincludingplannedorders
ISSALESSITEMANDATORY | >< | msdyn_issalessitemandatory
ISSALESLEADTIMEOVERRIDDEN | >< | msdyn_issalesleadtimeoverridden
ISSALESPROCESSINGSTOPPED | >< | msdyn_issalesprocessingstopped
ISINVENTORYWAREHOUSEMANDATORY | >< | msdyn_isinventorywarehousemandatory
ISPROCUREMENTWAREHOUSEMANDATORY | >< | msdyn_isprocurementwarehousemandatory
ISSALESWAREHOUSEMANDATORY | >< | msdyn_issaleswarehousemandatory

### <a name="product-specific-default-order-settings"></a>Termékspecifikus alapértelmezett rendelésbeállítások

A termékspecifikus rendelési beállítások következő leképezések segítségével érhetők el a Common Data Service szolgáltatásban.

Forrásmező | Térkép típusa | Célmező
---|---|---
INVENTORYWAREHOUSEID | = | msdyn_inventorywarehouse.msdyn_warehouseidentifier
INVENTORYSITEID | = | msdyn_inventorysite.msdyn_siteid
INVENTORYATPDELAYEDDEMANDOFFSETDAYS | = | msdyn_inventoryatpdelayeddemandoffsetdays
INVENTORYATPDELAYEDSUPPLYOFFSETDAYS | = | msdyn_inventoryatpdelayedsupplyoffsetdays
ITEMNUMBER | = | msdyn_itemnumber.msdyn_itemnumber
INVENTORYATPBACKWARDDEMANDTIMEFENCEDAYS | = | msdyn_inventoryatpbackwarddemandtimefencedays
INVENTORYATPBACKWARDSUPPLYTIMEFENCEDAYS | = | msdyn_inventoryatpbackwardsupplytimefencedays
INVENTORYATPTIMEFENCEDAYS | = | msdyn_inventoryatptimefencedays
MAXIMUMINVENTORYORDERQUANTITY | = | msdyn_maximuminventoryorderquantity
MAXIMUMPROCUREMENTORDERQUANTITY | = | msdyn_maximumprocurementorderquantity
MAXIMUMSALESORDERQUANTITY | = | msdyn_maximumsalesorderquantity
MINIMUMINVENTORYORDERQUANTITY | = | msdyn_minimuminventoryorderquantity
MINIMUMPROCUREMENTORDERQUANTITY | = | msdyn_minimumprocurementorderquantity
MINIMUMSALESORDERQUANTITY | = | msdyn_minimumsalesorderquantity
STANDARDINVENTORYORDERQUANTITY | = | msdyn_standardinventoryorderquantity
STANDARDPROCUREMENTORDERQUANTITY | = | msdyn_standardprocurementorderquantity
STANDARDSALESORDERQUANTITY | = | msdyn_standardsalesorderquantity
INVENTORYLEADTIMEDAYS | = | msdyn_inventoryleadtimedays
INVENTORYQUANTITYMULTIPLES | = | msdyn_inventoryquantitymultiples
PROCUREMENTQUANTITYMULTIPLES | = | msdyn_procurementquantitymultiples
SALESQUANTITYMULTIPLES | = | msdyn_salesquantitymultiples
PROCUREMENTSITEID | = | msdyn_procurementsite.msdyn_siteid
PROCUREMENTLEADTIMEDAYS | = | msdyn_procurementleadtimedays
SALESSITEID | = | msdyn_salessite.msdyn_siteid
SALESATPDELAYEDDEMANDOFFSETDAYS | = | msdyn_salesatpdelayeddemandoffsetdays
SALESATPDELAYEDSUPPLYOFFSETDAYS | = | msdyn_salesatpdelayedsupplyoffsetdays
SALESATPBACKWARDDEMANDTIMEFENCEDAYS | = | msdyn_salesatpbackwarddemandtimefencedays
SALESATPBACKWARDSUPPLYTIMEFENCEDAYS | = | msdyn_salesatpbackwardsupplytimefencedays
SALESATPTIMEFENCEDAYS | = | msdyn_salesatptimefencedays
SALESLEADTIMEDAYS | = | msdyn_salesleadtimedays
PROCUREMENTWAREHOUSEID | = | msdyn_procurementwarehouse.msdyn_warehouseidentifier
SALESWAREHOUSEID | = | msdyn_saleswarehouse.msdyn_warehouseidentifier
AREINVENTORYDEFAULTORDERSETTINGSOVERRIDDEN | >< | msdyn_areinventoryorderdefaultsoverridden
INVENTORYORDERPROMISINGMETHOD | >< | msdyn_inventoryorderpromisingmethod
ISINVENTORYATPINCLUDINGPLANNEDORDERS | >< | msdyn_isinventoryatpincludingplannedorders
ISINVENTORYUSINGWORKINGDAYS | >< | msdyn_isinventoryusingworkingdays
ISINVENTORYSITEMANDATORY | >< | msdyn_isinventorysitemandatory
ISINVENTORYPROCESSINGSTOPPED | >< | msdyn_isinventoryprocessingstopped
ISPROCUREMENTUSINGWORKINGDAYS | >< | msdyn_isprocurementusingworkingdays
ISPROCUREMENTSITEMANDATORY | >< | msdyn_isprocurementsitemandatory
ISPROCUREMENTPROCESSINGSTOPPED | >< | msdyn_isprocurementprocessingstopped
ARESALESDEFAULTORDERSETTINGSOVERRIDDEN | >< | msdyn_aresalesorderdefaultsoverridden
SALESORDERPROMISINGMETHOD | >< | msdyn_salesorderpromisingmethod
ISSALESATPINCLUDINGPLANNEDORDERS | >< | msdyn_issalesatpincludingplannedorders
ISSALESSITEMANDATORY | >< | msdyn_issalessitemandatory
ISSALESLEADTIMEOVERRIDDEN | >< | msdyn_issalesleadtimeoverridden
ISSALESPROCESSINGSTOPPED | >< | msdyn_issalesprocessingstopped
ISINVENTORYWAREHOUSEMANDATORY | >< | msdyn_isinventorywarehousemandatory
ISPROCUREMENTWAREHOUSEMANDATORY | >< | msdyn_isprocurementwarehousemandatory
ISSALESWAREHOUSEMANDATORY | >< | msdyn_issaleswarehousemandatory
OPERATIONALSITEID | = | msdyn_operationalsite.msdyn_siteid
PRODUCTCOLORID | = | msdyn_productcolor.msdyn_productcolorname
PRODUCTCONFIGURATIONID | = | msdyn_productconfiguration.msdyn_productconfiguration
PRODUCTSIZEID | = | msdyn_productsize.msdyn_productsize
PRODUCTSTYLEID | = | msdyn_productstyle.msdyn_productstyle

## <a name="unit-of-measure-and-unit-of-measure-conversions"></a>Mértékegység és mértékegység-átváltások

A mértékegységek és a kapcsolódó átváltások a diagramon látható adatmodellben érhetők el a Common Data Service szolgáltatásban.

![Adatmodell termékekhez](media/dual-write-product-3.PNG)

A mértékegység fogalma integrálva van a Finance and Operations alkalmazások és más Dynamics 365 alkalmazások között. A Finance and Operations alkalmazás minden egységosztálya esetében létrejön egy egységcsoport a Dynamics 365 alkalmazásban, amely az egységosztályhoz tartozó mértékegységeket tartalmazza. Minden egységcsoporthoz egy alapértelmezett alapegység is létrejön. 

### <a name="unit-of-measure"></a>Mértékegység

A következő leképezések a Finance and Operations alkalmazások mértékegységeit elérhetővé teszik a Common Data Service szolgáltatásban.

Forrásmező | Térkép típusa | Célmező
---|---|---
UNITSYMBOL | >> | msdyn_symbol
UNITCLASS | >> | msdyn_externalunitclassname
DECIMALPRECISION | >> | msdyn_decimalprecision
ISBASEUNIT | >> | msdyn_isbaseunit
ISSYSTEMUNIT | >> | msdyn_issystemunit
SYSTEMOFUNITS | >> | msdyn_systemofunits
UNITSYMBOL | >> | név
UNITDESCRIPTION | >> | msdyn_description

### <a name="unit-of-measure-conversions"></a>Mértékegység-átváltások

A következő leképezések a Finance and Operations alkalmazások mértékegységátváltásait elérhetővé teszik a Common Data Service szolgáltatásban.

Forrásmező | Térkép típusa | Célmező
---|---|---
DENOMINATOR | = | msdyn_denominator
NUMERATOR | = | msdyn_numerator
FACTOR | = | msdyn_factor
INNEROFFSET | = | msdyn_inneroffset
OUTEROFFSET | = | msdyn_outeroffset
ROUNDING | >< | msdyn_rounding
TOUNITSYMBOL | = | msdyn_tounit.msdyn_symbol
FROMUNITSYMBOL | = | msdyn_fromunit.msdyn_symbol

### <a name="product-specific-unit-of-measure-conversions"></a>Termékspecifikus mértékegység-átváltások

A következő leképezések a Finance and Operations alkalmazások termékspecifikus mértékegységátváltásait elérhetővé teszik a Common Data Service szolgáltatásban.

Forrásmező | Térkép típusa | Célmező
---|---|---
DENOMINATOR | = | msdyn_denominator
NUMERATOR | = | msdyn_numerator
FACTOR | = | msdyn_factor
FROMUNITSYMBOL | = | msdyn_fromunit.msdyn_symbol
TOUNITSYMBOL | = | msdyn_tounit.msdyn_symbol
PRODUCTNUMBER | = | msdyn_globalproduct.msdyn_productnumber
INNEROFFSET | = | msdyn_inneroffset
OUTEROFFSET | = | msdyn_outeroffset
ROUNDING | >< | msdyn_rounding

## <a name="product-policies-dimension-tracking-and-storage-groups"></a>Termékirányelvek: dimenzió, nyomon követés és tárolás csoportjai

A termékirányelvek a termékek és a készletbeli jellemzőik meghatározására használt irányelvek halmazai. A termékdimenzió-csoport, a termékkövetési-dimenziócsoport és a tárolási dimenziócsoport a termékirányelvekként találhatók meg. 

### <a name="product-dimension-group"></a>Termékdimenzió-csoport

A termékdimenzió csoportja határozza meg, hogy mely cikkdimenziók határozzák meg a terméket. A négy lehetséges termékdimenzió létezik: méret, szín, stílus és konfiguráció. Ezek a termékdimenzió-csoportok a következő hozzárendelések segítségével érhetők el a Common Data Service szolgáltatásban. 

Forrásmező | Térkép típusa | Célmező
---|---|---
WILLSALESPRICESEARCHUSEPRODUCTSTYLE | >< | msdyn_willsalespricesearchuseproductstyle
WILLPURCHASEPRICESEARCHUSEPRODUCTSIZE | >< | msdyn_willpurchasepricesearchuseproductsize
WILLSALESPRICESEARCHUSEPRODUCTCONFIGURATION | >< | msdyn_willsalespricesearchuseprodconfig
WILLSALESPRICESEARCHUSEPRODUCTCOLOR | >< | msdyn_willsalespricesearchuseproductcolor
WILLPURCHASEPRICESEARCHUSEPRODUCTSTYLE | >< | msdyn_willpurchasepricesearchuseproductstyle
WILLPURCHASEPRICESEARCHUSEPRODUCTCONFIGURATION | >< | msdyn_willpurchpricesearchuseprodconfig
WILLPURCHASEPRICESEARCHUSEPRODUCTCOLOR | >< | msdyn_willpurchpricesearchuseproductcolor
ISPRODUCTSTYLEACTIVE | >< | msdyn_isproductstyleactive
ISPRODUCTSIZEACTIVE | >< | msdyn_isproductsizeactive
ISPRODUCTCONFIGURATIONACTIVE | >< | msdyn_isproductconfigurationactive
ISPRODUCTCOLORACTIVE | >< | msdyn_isproductcoloractive
GROUPNAME | = | msdyn_groupname
GROUPDESCRIPTION | = | msdyn_groupdescription
PRODUCTVARIANTNOMENCLATURENAME | = | msdyn_productvariantnomenclaturename
WILLSALESPRICESEARCHUSEPRODUCTSIZE | >< | msdyn_willsalespricesearchuseproductsize

### <a name="product-tracking-dimension-group"></a>Terméknyomon-követés dimenziócsoport

A termék nyomon követési dimenziócsoportja a termék készletben történő nyomon követésére használt módszert jelöli. Ezek a következő hozzárendelések segítségével érhetők el a Common Data Service szolgáltatásban. 

Forrásmező | Térkép típusa | Célmező
---|---|---
SERIALNUMBERCAPTURINGOPERATION | >< | msdyn_serialnumbercapturingoperation
GROUPNAME | = | msdyn_groupname
GROUPDESCRIPTION | = | msdyn_groupdescription
ISSERIALNUMBERENABLEDFORPRODUCTIONCONSUMPTIONPROCESS | >< | msdyn_issnenabledforpcprocess
ISSERIALNUMBERCONTROLENABLED | >< | msdyn_isserialnumbercontrolenabled
ISSERIALNUMBERENABLEDFORSALESPROCESS | >< | msdyn_isserialnumberenabledforsalesprocess
ISSERIALNUMBERACTIVE | >< | msdyn_isserialnumberactive
ISSALESPRICEBYSERIALNUMBER | >< | msdyn_issalespricebyserialnumber
ISSALESPRICEBYBATCHNUMBER | >< | msdyn_issalespricebybatchnumber
ISPURCHASEPRICEBYSERIALNUMBER | >< | msdyn_ispurchasepricebyserialnumber
ISPURCHASEPRICEBYBATCHNUMBER | >< | msdyn_ispurchasepricebybatchnumber
ISPRIMARYSTOCKINGENABLEDFORSERIALNUMBER | >< | msdyn_isprimarystockingenabledforsn
ISPRIMARYSTOCKINGENABLEDFORBATCHNUMBER | >< | msdyn_isprimarystockingenabledforbn
ISPHYSICALINVENTORYENABLEDFORSERIALNUMBER | >< | msdyn_isphysicalinventoryenabledforsn
ISPHYSICALINVENTORYENABLEDFORBATCHNUMBER | >< | msdyn_isphysicalinventoryenabledforbn
ISFINANCIALINVENTORYENABLEDFORSERIALNUMBER | >< | msdyn_isfinancialinventoryenabledforsn
ISFINANCIALINVENTORYENABLEDFORBATCHNUMBER | >< | msdyn_isfinancialinventoryenabledforbn
ISCOVERAGEPLANENABLEDFORSERIALNUMBER | >< | msdyn_iscoverageplanenabledforserialnumber
ISCOVERAGEPLANENABLEDFORBATCHNUMBER | >< | msdyn_iscoverageplanenabledforbatchnumber
ISBLANKRECEIPTALLOWEDFORSERIALNUMBER | >< | msdyn_isblankreceiptallowedforserialnumber
ISBLANKRECEIPTALLOWEDFORBATCHNUMBER | >< | msdyn_isblankreceiptallowedforbatchnumber
ISBLANKISSUEALLOWEDFORSERIALNUMBER | >< | msdyn_isblankissueallowedforserialnumber
ISBLANKISSUEALLOWEDFORBATCHNUMBER | >< | msdyn_isblankissueallowedforbatchnumber
ISBATCHNUMBERACTIVE | >< | msdyn_isbatchnumberactive
ISINVENTORYOWNERACTIVE | >< | msdyn_isinventoryowneractive

### <a name="product-storage-dimension-group"></a>Terméktárolási dimenziócsoportok

A termék tárolási dimenziócsoportja képviseli azt a módszert amelyet használnak a termék elhelyezésének definiálásához a raktárban. Ezek a következő hozzárendelések segítségével érhetők el a Common Data Service szolgáltatásban. 

Forrásmező | Térkép típusa | Célmező
---|---|---
WILLSALESPRICESEARCHUSEWAREHOUSE | >< | msdyn_willsalespricesearchusewarehouse
WILLSALESPRICESEARCHUSESITE | >< | msdyn_willsalespricesearchusesite
WILLSALESPRICESEARCHUSEINVENTORYSTATUS | >< | msdyn_willsalespricesearchuseinventorystatus
WILLPURCHASEPRICESEARCHUSEWAREHOUSE | >< | msdyn_willpurchasepricesearchusewarehouse
WILLPURCHASEPRICESEARCHUSESITE | >< | msdyn_willpurchasepricesearchusesite
WILLPURCHASEPRICESEARCHUSEINVENTORYSTATUS | >< | msdyn_willpurchpricesearchuseinventstatus
WILLCOVERAGEPLANNINGUSEWAREHOUSE | >< | msdyn_willcoverageplanusewarehouse
WILLCOVERAGEPLANNINGUSELOCATION | >< | msdyn_iscoverageplanenabledforlocation
WILLCOVERAGEPLANNINGUSEINVENTORYSTATUS | >< | msdyn_willcoverageplanuseinventorystatus
AREADVANCEDWAREHOUSEMANAGEMENTPROCESSESENABLED | >< | msdyn_areadvancedwmprocessesenabled
ISWAREHOUSEPRIMARYSTORAGEDIMENSION | >< | msdyn_iswarehouseprimarystoragedimension
ISWAREHOUSEMANDATORY | >< | msdyn_iswarehousemandatory
ISPHYSICALINVENTORYENABLEDFORWAREHOUSE | >< | msdyn_isphysicalinventoryenabledforwarehouse
ISPHYSICALINVENTORYENABLEDFORLOCATION | >< | msdyn_isphysicalinventoryenabledforlocation
ISLOCATIONACTIVE | >< | msdyn_islocationactive
ISFINANCIALINVENTORYENABLEDFORWAREHOUSE | >< | msdyn_isfinancialinventoryenabledforwarehouse
GROUPNAME | = | msdyn_groupname
GROUPDESCRIPTION | = | msdyn_groupdescription
ISBLANKRECEIPTALLOWEDFORLOCATION | >< | msdyn_isblankreceiptallowedforlocation
ISBLANKISSUEALLOWEDFORLOCATION | >< | msdyn_isblankissueallowedforlocation

