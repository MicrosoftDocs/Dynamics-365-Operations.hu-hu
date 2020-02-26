## <a name="customers-v3-to-contacts"></a>V3 ügyfelek a kapcsolatokhoz

Ez a sablon szinkronizálja az adatokat az Finance and Operations alkalmazások és a(z) Common Data Serviceközött.

Forrásszűrő: ((Féltípus == „Személy”))

Fordított forrásszűrő: msdyn_sellable eq igaz és msdyn_contactpersonid ne "

Finance and Operations mező | Térkép típusa | Egyéb Dynamics 365 mező | Alapértelmezett érték
---|---|---|---
egyik sem | >> | msdyn_sellable | Igaz
PARTYTYPE | << | egyik sem | Személy
PARTYNUMBER | = | msdyn_partynumber | 
CUSTOMERACCOUNT | = | msdyn_contactpersonid | 
CUSTOMERGROUPID | = | msdyn_customergroupid.msdyn_groupid | 
PERSONFIRSTNAME | = | utónév | 
PERSONLASTNAME | = | vezetéknév | 
PERSONMIDDLENAME | = | másodikutónév | 
PERSONPROFESSIONALTITLE | = | mukakör | 
PERSONGENDER | >< | nemkód | 
PERSONMARITALSTATUS | >< | családiállapotkódja | 
LANGUAGEID | << | egyik sem | hu-hu
ADDRESSCITY | = | address1_city | 
ADDRESSCOUNTRYREGIONISOCODE | = | address1_country | 
ADDRESSCOUNTY | = | address1_county | 
ADDRESSLATITUDE | > | address1_latitude | 
ADDRESSLONGITUDE | > | address1_longitude | 
ADDRESSLOCATIONROLES | << | egyik sem | Vállalat
ADDRESSSTATE | = | address1_stateorprovince | 
ADDRESSSTREET | = | address1_line1 | 
ADDRESSZIPCODE | = | address1_postalcode | 
ADDRESSPOSTBOX | = | address1_postofficebox | 
egyik sem | >> | address1_addresstypecode | 3
INVOICEADDRESSCITY | = | address2_city | 
INVOICEADDRESSCOUNTRYREGIONISOCODE | = | address2_country | 
INVOICEADDRESSCOUNTY | = | address2_county | 
INVOICEADDRESSLATITUDE | > | address2_latitude | 
INVOICEADDRESSLONGITUDE | > | address2_longitude | 
INVOICEADDRESSSTATE | = | address2_stateorprovince | 
INVOICEADDRESSSTREET | = | address2_line1 | 
INVOICEADDRESSZIPCODE | = | address2_postalcode | 
DELIVERYADDRESSCITY | = | address3_city | 
DELIVERYADDRESSCOUNTRYREGIONISOCODE | = | address3_country | 
DELIVERYADDRESSCOUNTY | = | address3_county | 
DELIVERYADDRESSLATITUDE | > | address3_latitude | 
DELIVERYADDRESSLONGITUDE | >> | address3_longitude | 
DELIVERYADDRESSSTATE | = | address3_stateorprovince | 
DELIVERYADDRESSSTREET | = | address3_line1 | 
DELIVERYADDRESSZIPCODE | = | address3_postalcode | 
PRIMARYCONTACTEMAIL | = | emailcím1 | 
PRIMARYCONTACTEMAILDESCRIPTION | = | msdyn_emailaddress1description | 
PRIMARYCONTACTFAX | = | faxszám | 
PRIMARYCONTACTFAXDESCRIPTION | = | msdyn_faxdescription | 
PRIMARYCONTACTFAXEXTENSION | = | msdyn_faxextension | 
IDENTIFICATIONNUMBER | = | msdyn_identificationnumber | 
PARTYCOUNTRY | = | msdyn_partycountry | 
PARTYSTATE | = | msdyn_partystateprovince | 
PRIMARYCONTACTFACEBOOK | = | msdyn_primaryfacebookid | 
PRIMARYCONTACTFACEBOOKDESCRIPTION | = | msdyn_primaryfacebookdescription | 
PRIMARYCONTACTLINKEDIN | = | msdyn_primarylinkedinid | 
PRIMARYCONTACTLINKEDINDESCRIPTION | = | msdyn_primarylinkedindescrption | 
PRIMARYCONTACTPHONE | = | telefonszám1 | 
PRIMARYCONTACTPHONEDESCRIPTION | = | msdyn_telephone1description | 
PRIMARYCONTACTPHONEEXTENSION | = | msdyn_telephone1extension | 
PRIMARYCONTACTTWITTER | = | msdyn_primarytwitterid | 
PRIMARYCONTACTTWITTERDESCRIPTION | = | msdyn_primarytwitteriddescription | 
PRIMARYCONTACTURL | = | weboldalurl | 
PRIMARYCONTACTURLDESCRIPTION | = | msdyn_websiteurldescription | 
SALESCURRENCYCODE | = | transactioncurrencyid.isocurrencycode | 
SALESMEMO | = | leírás | 
