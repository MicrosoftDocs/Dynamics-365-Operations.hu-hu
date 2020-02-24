## <a name="withholding-tax-codes-to-msdyn_withholdingtaxcodes"></a>A msdyn_withholdingtaxcodes adóelőleg kódja

Ez a sablon szinkronizálja az adatokat az Finance and Operations alkalmazások és a(z) Common Data Serviceközött.

Finance and Operations mező | Térkép típusa | Egyéb Dynamics 365 mező | Alapértelmezett érték
---|---|---|---
ELŐLEGKÓD | = | msdyn_name | 
ADÓELŐLEGNEVE | = | msdyn_description | 
ADÓELŐLEGKEREKÍTÉSE | = | msdyn_roundoff | 
ADÓELŐLEGKEREKÍTÉSÉNEKTÍPUSA | >< | msdyn_roundofftype | 
VALUTAKÓDAZONOSÍTÓJA | = | msdyn_currency.isocurrencycode | 
ADÓELŐLEGALAP | >< | msdyn_taxableamountorigin | 
