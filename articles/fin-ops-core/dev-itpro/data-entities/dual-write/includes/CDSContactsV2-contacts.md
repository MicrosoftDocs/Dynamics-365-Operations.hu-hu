## <a name="cds-contacts-v2-to-contacts"></a>CDS V2 kapcsolattartók hozzáadása a kapcsolatok mappához

Ez a sablon szinkronizálja az adatokat az Finance and Operations alkalmazások és a(z) Common Data Serviceközött.

Forrásszűrő: (Kapcsolódókapcsolattípusa = 1)

Fordított forrásszűrő: msdyn_contactforvendor eq igaz és az msdyn_sellable eq hamis és az msdyn_contactpersonid ne "

Finance and Operations mező | Térkép típusa | Egyéb Dynamics 365 mező | Alapértelmezett érték
---|---|---|---
KAPCSOLATTARTÓSZEMÉLYPÁRTSZÁMA | = | msdyn_partynumber | 
TÁRSÍTOTTNÉVJEGYTÍPUS | << | egyik sem | Szállító
UTÓNÉV | = | utónév | 
MÁSODIKUTÓNÉV | = | másodikutónév | 
VEZETÉKNÉV | = | vezetéknév | 
TÁRSÍTOTTNÉVJEGYSZÁM | = | msdyn_vendorcontactid.msdyn_vendoraccountnumber | 
ELSŐDLEGESCÍMVÁROSA | = | address1_city | 
ELSŐDLEGESCÍMORSZÁGRÉGIÓJÁNAKAZONOSÍTÓJA | = | address1_country | 
ELSŐDLEGESCÍMMEGYÉJÉNEKAZONOSÍTÓJA | = | address1_county | 
ELSŐDLEGESFAXSZÁM | = | faxszám | 
ELSŐDLEGESCÍMÁLLAMÁNAKAZONOSÍTÓJA | = | address1_stateorprovince | 
ELSŐDLEGESCÍMUTCÁJA | = | address1_line1 | 
ELSŐDLEGESCÍMIRÁNYÍTÓSZÁMA | = | address1_postalcode | 
ELSŐDLEGESTELEFONSZÁM | = | telefonszám1 | 
ELSŐDLEGESEMAILCÍM | = | emailcím1 | 
MUNKÁLTATÓIRÉSZLEG | = | részleg | 
JEGYZETEK | = | leírás | 
NEM | >< | nemkód | 
KORMÁNYZATIAZONOSÍTÓSZÁM | = | kormányzatiazonosító | 
ELSŐDLEGESURL | = | weboldalurl | 
CSALÁDIÁLLAPOT | >< | családiállapotkódja | 
KÖZVETLENEMAILTKAP | >< | neküldjönemailt | 
FOGLALKOSZTATÁSISZAKMA | = | mukakör | 
HÁZASTÁRSNEVE | = | házastársakneve | 
egyik sem | >> | msdyn_contactforvendor | Igaz
KAPCSOLATTARTÓSZEMÉLYAZONOSÍTÓJA | = | msdyn_contactpersonid | 
