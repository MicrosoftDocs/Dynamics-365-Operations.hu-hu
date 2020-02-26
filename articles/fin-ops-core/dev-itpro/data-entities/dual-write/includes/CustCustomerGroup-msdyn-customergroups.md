## <a name="customer-groups-to-msdyn_customergroups"></a>A msdyn_customergroups vevői csoportjai

Ez a sablon szinkronizálja az adatokat az Finance and Operations alkalmazások és a(z) Common Data Serviceközött.

Finance and Operations mező | Térkép típusa | Egyéb Dynamics 365 mező | Alapértelmezett érték
---|---|---|---
VEVŐICSOPORTAZONOSÍTÓJA | = | msdyn_groupid | 
LEÍRÁS | = | msdyn_description | 
AZÁRTARTALMAZZAAFORGALMIADÓT | >< | msdyn_issalestaxincludedinprice | 
KIFIZETÉSIFELTÉTELAZONOSÍTÓ | = | msdyn_paymenttermid.msdyn_name | 
ELSZÁMOLÁSIIDŐSZAKFIZETÉSIFELTÉTELÉNEKNEVE | = | msdyn_clearingperiodpaymenttermname.msdyn_name | 
