## <a name="main-account-to-msdyn_mainaccounts"></a>Az msdyn_mainaccounts fő számlája

Ez a sablon szinkronizálja az adatokat az Finance and Operations alkalmazások és a(z) Common Data Serviceközött.

Finance and Operations mező | Térkép típusa | Egyéb Dynamics 365 mező | Alapértelmezett érték
---|---|---|---
FŐSZÁMLAAZONOSÍTÓJA | = | msdyn_accountnumber | 
SZÁMLATÜKÖR | = | msdyn_chartofaccounts.msdyn_name | 
NÉV | = | msdyn_name | 
EGYENLEGELLENŐRZÉSE | >< | msdyn_balancecontrol | 
ÁRFOLYAMKORREKCIÓARÁNYA | = | msdyn_exchangeadjustmentratetype. msdyn_name | 
ZÁRÁS | >< | msdyn_closing | 
ÁRFOLYAMKORREKCIÓARÁNYTÍPUSÁNAKJELENTÉSE | = | msdyn_reportingexchangeadjustmentratetype.msdyn_name | 
TERHELÉSIHITELEZÉSIKÉRELEM | >< | msdyn_debitcreditrequirement | 
PÉNZÜGYIJELETÉSKÉSZÍTÉSÁRFOLYAMTÍPUSA | = | msdyn_financialreportingexchangeratetype.msdyn_name | 
DEVIZAÁTÉRTÉKELÉS | >< | msdyn_foreigncurrencyrevaluation | 
FŐSZÁMLAKATEGÓRIÁJA | = | msdyn_mainaccountcategoryname | 
AFIZETÉSIHIVATKOZÁSMEGADÁSAKÖTELEZŐ | >< | msdyn_mandatorypaymentreference | 
PÉNZÜGYI | >< | msdyn_monetary | 
ELTÉRŐISZÁMLAMEGJELENÍTETTÉRTÉKE | = | msdyn_offsetaccount | 
FELADÁSTÍPUSA | >< | msdyn_postingtype | 
SRUKÓD | = | msdyn_srucode | 
PÉNZNEMEKÉRVÉNYESÍTÉSE | >< | msdyn_validatecurrencycode | 
FELHASZNÁLÓÉRVÉNYESÍTÉSE | >< | msdyn_validateuser | 
ALAPÉRTELMEZETTTERHELÉSHITEL | >< | msdyn_debitcreditdefault | 
ALAPÉRTELMEZETTPÉNZNEM | = | msdyn_defaultcurrency.isocurrencycode | 
FŐSZÁMLATÍPUSA | >< | msdyn_mainaccounttype | 
PÉNZÜGYIJELENTÉSPÉNZNEMÉNEKFORDÍTÁSITÍPUSA | >< | msdyn_financialreportingcurrencytrantype | 
FELHASZNÁLÓ | = | msdyn_user | 
FELADÁSITÍPUSÉRVÉNYESÍTÉSE | >< | msdyn_validateposting | 
