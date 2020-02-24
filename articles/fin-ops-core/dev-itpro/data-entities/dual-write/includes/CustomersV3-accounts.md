## <a name="customers-v3-to-accounts"></a>V3 vevők a számlákhoz

Ez a sablon szinkronizálja az adatokat az Finance and Operations alkalmazások és a(z) Common Data Serviceközött.

Forrásszűrő: ((Féltípus == „Szervezet”))

Fordított forrásszűrő: customertypecode eq 3

Finance and Operations mező | Térkép típusa | Egyéb Dynamics 365 mező | Alapértelmezett érték
---|---|---|---
VEVŐISZÁMLA | = | számlaszám | 
SZÁMLACÍMVÁROSA | = | address2_city | 
SZÁMLACÍMVÁROSMEGYERÉGIÓISOKÓDJA | = | address2_country | 
SZÁMLACÍMMEGYÉJE | = | address2_county | 
SZÁMLACÍMFÖLDRAJZISZÉLESSÉGE | > | address2_latitude | 
SZÁMLACÍMFÖLDRAJZIHOSSZÚSÁGA | > | address2_longitude | 
SZÁMLACÍMÁLLAMA | = | address2_stateorprovince | 
SZÁMLACÍMUTCÁJA | = | address2_line1 | 
SZÁMLACÍMIRÁNYÍTÓSZÁMA | = | address2_postalcode | 
HITELKERET | = | hitelkeret | 
SZÁLLÍTÁSICÍMVÁROSA | = | address1_city | 
SZÁLLÍTÁSICÍMVÁROSMEGYERÉGIÓISOKÓDJA | = | address1_country | 
SZÁLLÍTÁSICÍMMEGYÉJE | = | address1_county | 
SZÁLLÍTÁSICÍMFÖLDRAJZISZÉLESSÉGE | > | address1_latitude | 
SZÁLLÍTÁSICÍMFÖLDRAJZIHOSSZÚSÁGA | > | address1_longitude | 
SZÁLLÍTÁSICÍMIRÁNYÍTÓSZÁMA | = | address1_postalcode | 
SZERVEZETNEVE | = | név | 
SZERVEZETALKALMAZOTTAINAKSZÁMA | = | alkalmazottakszáma | 
ELSŐDLEGESKAPCSOLATTARTÓEMAIL | = | emailcím1 | 
ELSŐDLEGESKAPCSOLATTARTÓFAXSZÁM | = | faxszám | 
ELSŐDLEGESKAPCSOLATTARTÓTELEFONSZÁM | = | telefonszám1 | 
ELSŐDLEGESKAPCSOLATTARTÓTWITTER | = | elsődlegestwitterazonosító | 
ELSŐDLEGESKAPCSOLATTARTÓURL | = | weboldalurl | 
ÉRTÉKESÍTÉSIVALUTAKÓD | = | transactioncurrencyid.isocurrencycode | 
ÉRTÉKESÍTÉSIMEMO | = | leírás | 
AHITELKERETKÖTELEZŐ | >< | msdyn_creditlimitismandatory | 
HITELMINŐSÍTÉS | = | msdyn_creditrating | 
VEVŐICSOPORTAZONOSÍTÓJA | = | msdyn_customergroupid.msdyn_groupid | 
AZONOSÍTÓSZÁM | = | msdyn_identificationnumber | 
SZÁMLAFOGADÓ | = | msdyn_billingaccount.accountnumber | 
SZÁMLÁZÁSICÍM | >< | msdyn_invoiceaddress | 
ISONETIMEVEVŐ | >< | msdyn_onetimecustomer | 
VÁRAKOZTATOTT | >< | msdyn_onholdstatus | 
FÉLORSZÁGA | = | msdyn_partycountry | 
FÉLÁLLAMA | = | msdyn_partystateprovince | 
FIZETÉSNAPJA | = | msdyn_paymentday.msdyn_name | 
FIZETÉSIMÓD | = | msdyn_customerpaymentmethod.msdyn_name | 
KIFIZETÉSIÜTEMEZÉS | = | msdyn_paymentschedule.msdyn_name | 
FIZETÉSIFELTÉTELEK | = | msdyn_paymentterm.msdyn_name | 
FIZETÉSIFELTÉTELEKALAPNAPJAI | = | msdyn_paymenttermsbasedays | 
ELSŐDLEGESKAPCSOLATTARTÓFACEBOOKJA | = | msdyn_primaryfacebookid | 
ELSŐDLEGESKAPCSOLATTARTÓFAXMELLÉK | = | msdyn_faxextension | 
ELSŐDLEGESKAPCSOLATTARTÓLINKEDIN | = | msdyn_primarylinkedinid | 
ADÓMENTESSÉGSZÁMA | = | msdyn_taxexemptnumber | 
SZÁLLÍTÓISZÁMLA | = | msdyn_vendor.msdyn_vendoraccountnumber | 
ELSŐDLEGESKAPCSOLATTARTÓEMAILLEÍRÁSA | = | msdyn_emailaddress1description | 
ELSŐDLEGESKAPCSOLATTARTÓFACEBOOKLEÍRÁSA | = | msdyn_primaryfacebookdescription | 
ELSŐDLEGESKAPCSOLATTARTÓFAXLEÍRÁSA | = | msdyn_faxdescription | 
ELSŐDLEGESKAPCSOLATTARTÓLINKEDINLEÍRÁSA | = | msdyn_primarylinkedindescrption | 
ELSŐDLEGESKAPCSOLATTARTÓTELEFONSZÁMLEÍRÁSA | = | msdyn_telephone1description | 
ELSŐDLEGESKAPCSOLATTARTÓTELEFONMELLÉKE | = | msdyn_telephone1extension | 
ELSŐDLEGESKAPCSOLATTARTÓTWITTERLEÍRÁSA | = | msdyn_primarytwitteriddescription | 
ELSŐDLEGESKAPCSOLATTARTÓURLLEÍRÁSA | = | msdyn_websiteurldescription | 
NYELVAZONOSÍTÓ | << | egyik sem | hu-hu
SZÁLLÍTÁSICÍMUTCÁJA | = | address1_line1 | 
SZÁLLÍTÁSICÍMÁLLAMA | = | address1_stateorprovince | 
egyik sem | >> | address1_addresstypecode | 2
egyik sem | >> | ügyféltípuskód | 3
FÉLTÍPUSA | << | egyik sem | Szervezet
FÉLSZÁMA | = | msdyn_partynumber | 
KAPCSOLATTARTÓSZEMÉLYAZONOSÍTÓJA | = | primarycontactid.msdyn_contactpersonid | 
