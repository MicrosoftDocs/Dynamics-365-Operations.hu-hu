---
title: Integrált vevői alapadat
description: Ez a témakör az ügyféladatok integrációját ismerteti a Finance and Operations és a Common Data Service között.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 07/15/2019
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
ms.openlocfilehash: 6c8c94eb8ff04d489eb24b7e0f4642aef20a3b18
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/27/2019
ms.locfileid: "2182048"
---
## <a name="integrated-customer-master"></a>Integrált vevői alapadat

[!include [banner](../includes/banner.md)]

[!include [preview](../includes/preview-banner.md)]

Az ügyfélbejegyzések általában egynél több alkalmazásban is alapadatok lehetnek. Például az értékesítési tevékenység üzleti vevőrekordokat hozhat be egy Sales alkalmazáson keresztül, és az e-kereskedelmi vagy a kiskereskedelmi értékesítés az ügyfélbejegyzéseket hozhat be egy Finance and Operations alkalmazáson keresztül. Függetlenül attól, hogy honnan származik az ügyfélrekord, az a színfalak mögött az integrálva lesz az alkalmazáshatárokon és infrastrukturális különbségeken túl. Az integrált ügyfél alapadat-kezelés segít a több alapadattal rendelkező forgatókönyveknél abban, hogy átfogó képet kapjon az ügyfélről a teljes Dynamics 365 alkalmazáscsomagban.

## <a name="customer-data-flow"></a>Vevő adatfolyama

A *Vevő* egy jól meghatározott fogalom az alkalmazásokban. Ezért az ügyféladatok integrációja mindössze az ügyfélkoncepció harmonizálását jelenti a két alkalmazás között. A következő ábra ábrázolja az ügyféladatok áramlását.

![Vevő adatfolyama](media/dual-write-customer-data-flow.png)

Az ügyfeleknek általánosságban két típusa van: kereskedelmi/vállalati ügyfelek és a fogyasztók/végfelhasználók. E A két vevőtípust eltérően van tárolva és kezelve a Finance and Operations és Common Data Service programokban.

A Finance and Operations alkalmazásban a kereskedelmi/vállalati vásárlók és fogyasztók/végfelhasználók egy táblában vannak regisztrálva, ennek neve **CustTable** (CustomerCustomerV3Entity), és mindkettő a **Típus** attribútum alapján van osztályozva. (Ha **Típus** beállítása **Szervezet**, akkor a vevő kereskedelmi/vállalati vevő, ha a **Típus** beállítása **Személy**, akkor a vevő fogyasztó/végfelhasználó.) Az elsődleges kapcsolattartó adatait az SMMContactPersonEntity entitáson keresztül kezeli a rendszer.

A Common Data Service megoldásban a kereskedelmi/válalati ügyfelek az Ügyfél entitásban vannak regisztrálva és akkor azonosítják ügyfelként, ha **RelationshipType** attribútum értéke **Ügyfél**. A Névjegy entitás képviseli a fogyasztókat/végfelhasználókat és a kapcsolattartót is. Az ügyfél/végfelhasználó és a kapcsolattartó személy közötti egyértelmű elkülönítés biztosítása érdekében **Kapcsolattartó** entitásnak egy **Eladható**logikai jelölője van. Ha az **Eladható** értéke **Igaz**, a kapcsolattartó fogyasztó/végfelhasználó, és a kapcsolattartóhoz létrehozhatók árajánlatok és megrendelések. Ha az **Eladható** értéke **Hamis**, a kapcsolattartó csak egy ügyfél elsődleges kapcsolattartó személye.

Ha egy nem eladható kapcsolat részt vesz egy árajánlatban vagy rendelési folyamatban, az **Eladható** értéke **Igaz**, hogy a kapcsolattartó eladható kapcsolattartóként legyen megjelölve. Az eladhatóvá válta kapcsolattartó eladható kapcsolattartó marad.

## <a name="templates"></a>Sablonok

Az ügyféladatok a vevőre vonatkozó összes információt tartalmazzák, például a vevőcsoportot, a címeket, a kapcsolattartási adatokat, a fizetési profilt, a számlaprofilt és a hűségi állapotot. Az entitásleképezések gyűjteményei az alábbi tábla szerint működnek együtt az ügyféladata-interakció során.

Finance and Operations alkalmazások    | Egyéb Dynamics 365 alkalmazások
--------------------------|---------------------------------
Vevő V3               | Könyvelési számla
Vevő V3               | Névjegy
CDS névjegyek V2           | Névjegy
Vevőcsoportok           | Msdyn\_customergroups
Vevő fizetési módja   | Msdyn\_customerpaymentmethods
Hűségkártya              | Msdyn\_loyaltycards
Fizetési ütemezés          | Msdyn\_paymentschedules
Fizetési ütemezés          | Msdyn\_paymentschedulelines
Fizetési nap, CDS           | Msdyn\_paymentdays
Fizetési nap sorai, CDS     | Msdyn\_paymentdaylines
Fizetési feltételek          | Msdyn\_paymentterms
Névutótagok              | Msdyn\_nameaffixes

[!include [banner](../includes/dual-write-symbols.md)]

## <a name="customer-v3-to-account"></a>Customer V3 Ügyfélhez

Ez a sablon szinkronizálja a vevői törzsadatokat a kereskedelmi és vállalati ügyfelekhez a Finance and Operations alkalmazások és a Common Data Service között.

<!-- ![](media/dual-write-account-1.png) -->

<!-- ![](media/dual-write-account-2.png) -->

Forrásmező | Térkép típusa | Célmező
---|---|---
CUSTOMERACCOUNT | = | accountnumber
INVOICEADDRESSCITY | = | address2\_city
INVOICEADDRESSCOUNTRYREGIONISOCODE | = | address2\_country
INVOICEADDRESSCOUNTY | = | address2\_county
INVOICEADDRESSLATITUDE | \> | address2\_latitude
INVOICEADDRESSLONGITUDE | \> | address2\_longitude
INVOICEADDRESSSTATE | = | address2\_stateorprovince
INVOICEADDRESSSTREET | = | address2\_line1
INVOICEADDRESSZIPCODE | = | address2\_postalcode
CREDITLIMIT | = | creditlimit
DELIVERYADDRESSCITY | = | address1\_city
DELIVERYADDRESSCOUNTRYREGIONISOCODE | = | address1\_country
DELIVERYADDRESSCOUNTY | = | address1\_county
DELIVERYADDRESSLATITUDE | \> | address1\_latitude
DELIVERYADDRESSLONGITUDE | \> | address1\_longitude
DELIVERYADDRESSZIPCODE | = | address1\_postalcode
ORGANIZATIONNAME | = | név
ORGANIZATIONNUMBEROFEMPLOYEES | = | numberofemployees
PRIMARYCONTACTEMAIL | = | emailaddress1
PRIMARYCONTACTFAX | = | fax
PRIMARYCONTACTPHONE | = | telephone1
PRIMARYCONTACTTWITTER | = | primarytwitterid
PRIMARYCONTACTURL | = | websiteurl
SALESCURRENCYCODE | = | transactioncurrencyid.isocurrencycode
SALESMEMO | = | leírás
CREDITLIMITISMANDATORY | \>\< | msdyn\_creditlimitismandatory
CREDITRATING | = | msdyn\_creditrating
CUSTOMERGROUPID | = | msdyn\_customergroupid.msdyn\_groupid
IDENTIFICATIONNUMBER | = | msdyn\_identificationnumber
INVOICEACCOUNT | = | msdyn\_billingaccount.accountnumber
INVOICEADDRESS | \>\< | msdyn\_invoiceaddress
ISONETIMECUSTOMER | \>\< | msdyn\_onetimecustomer
ONHOLDSTATUS | \>\< | msdyn\_onholdstatus
PARTYCOUNTRY | = | msdyn\_partycountry
PARTYSTATE | = | msdyn\_partystateprovince
PAYMENTDAY | = | msdyn\_paymentday.msdyn\_name
PAYMENTMETHOD | = | msdyn\_customerpaymentmethod.msdyn\_name
PAYMENTSCHEDULE | = | msdyn\_paymentschedule.msdyn\_name
PAYMENTTERMS | = | msdyn\_paymentterm.msdyn\_name
PAYMENTTERMSBASEDAYS | = | msdyn\_paymenttermsbasedays
PRIMARYCONTACTFACEBOOK | = | msdyn\_primaryfacebookid
PRIMARYCONTACTFAXEXTENSION | = | msdyn\_faxextension
PRIMARYCONTACTLINKEDIN | = | msdyn\_primarylinkedinid
TAXEXEMPTNUMBER | = | msdyn\_taxexemptnumber
VENDORACCOUNT | = | msdyn\_vendor.msdyn\_vendoraccountnumber
PRIMARYCONTACTEMAILDESCRIPTION | = | msdyn\_emailaddress1description
PRIMARYCONTACTFACEBOOKDESCRIPTION | = | msdyn\_primaryfacebookdescription
PRIMARYCONTACTFAXDESCRIPTION | = | msdyn\_faxdescription
PRIMARYCONTACTLINKEDINDESCRIPTION | = | msdyn\_primarylinkedindescrption
PRIMARYCONTACTPHONEDESCRIPTION | = | msdyn\_telephone1description
PRIMARYCONTACTPHONEEXTENSION | = | msdyn\_telephone1extension
PRIMARYCONTACTTWITTERDESCRIPTION | = | msdyn\_primarytwitteriddescription
PRIMARYCONTACTURLDESCRIPTION | = | msdyn\_websiteurldescription
LANGUAGEID | \<\< | nincs
DELIVERYADDRESSSTREET | = | address1\_line1
DELIVERYADDRESSSTATE | = | address1\_stateorprovince
nincs | \>\> | address1\_addresstypecode
nincs | \>\> | customertypecode
PARTYTYPE | \<\< | nincs
PARTYNUMBER | = | msdyn\_partynumber

## <a name="customer-v3-to-contact"></a>Customer V3 Névjegyhez

Ez a sablon szinkronizálja a vevői törzsadatokat a fogyasztókhoz és végfelhasználókhoz a Finance and Operations és a más Dynamics 365 alkalmazások között.

<!-- ![](media/dual-write-contact-1.png) -->
<!-- ![](media/dual-write-contact-2.png) -->

Forrásmező | Térkép típusa | Célmező
---|---|---
nincs | \>\> | msdyn\_sellable
PARTYTYPE | \<\< | nincs
PARTYNUMBER | = | msdyn\_partynumber
CUSTOMERACCOUNT | = | msdyn\_contactpersonid
CUSTOMERGROUPID | = | msdyn\_customergroupid.msdyn\_groupid
PERSONFIRSTNAME | = | firstname
PERSONLASTNAME | = | lastname
PERSONMIDDLENAME | = | middlename
PERSONPROFESSIONALTITLE | = | jobtitle
PERSONGENDER | \>\< | gendercode
PERSONMARITALSTATUS | \>\< | familystatuscode
LANGUAGEID | \<\< | nincs
ADDRESSCITY | = | address1\_city
ADDRESSCOUNTRYREGIONISOCODE | = | address1\_country
ADDRESSCOUNTY | = | address1\_county
ADDRESSLATITUDE | \> | address1\_latitude
ADDRESSLONGITUDE | \> | address1\_longitude
ADDRESSLOCATIONROLES | \<\< | nincs
ADDRESSSTATE | = | address1\_stateorprovince
ADDRESSSTREET | = | address1\_line1
ADDRESSZIPCODE | = | address1\_postalcode
ADDRESSPOSTBOX | = | address1\_postofficebox
nincs | \>\> | address1\_addresstypecode
INVOICEADDRESSCITY | = | address2\_city
INVOICEADDRESSCOUNTRYREGIONISOCODE | = | address2\_country
INVOICEADDRESSCOUNTY | = | address2\_county
INVOICEADDRESSLATITUDE | \> | address2\_latitude
INVOICEADDRESSLONGITUDE | \> | address2\_longitude
INVOICEADDRESSSTATE | = | address2\_stateorprovince
INVOICEADDRESSSTREET | = | address2\_line1
INVOICEADDRESSZIPCODE | = | address2\_postalcode
nincs | \>\> | address2\_addresstypecode
DELIVERYADDRESSCITY | = | address3\_city
DELIVERYADDRESSCOUNTRYREGIONISOCODE | = | address3\_country
DELIVERYADDRESSCOUNTY | = | address3\_county
DELIVERYADDRESSLATITUDE | \> | address3\_latitude
DELIVERYADDRESSLONGITUDE | \>\> | address3\_longitude
DELIVERYADDRESSSTATE | = | address3\_stateorprovince
DELIVERYADDRESSSTREET | = | address3\_line1
DELIVERYADDRESSZIPCODE | = | address3\_postalcode
nincs | \>\> | address3\_addresstypecode
PRIMARYCONTACTEMAIL | = | emailaddress1
PRIMARYCONTACTEMAILDESCRIPTION | = | msdyn\_emailaddress1description
PRIMARYCONTACTFAX | = | fax
PRIMARYCONTACTFAXDESCRIPTION | = | msdyn\_faxdescription
PRIMARYCONTACTFAXEXTENSION | = | msdyn\_faxextension
IDENTIFICATIONNUMBER | = | msdyn\_identificationnumber
PARTYCOUNTRY | = | msdyn\_partycountry
PARTYSTATE | = | msdyn\_partystateprovince
PRIMARYCONTACTFACEBOOK | = | msdyn\_primaryfacebookid
PRIMARYCONTACTFACEBOOKDESCRIPTION | = | msdyn\_primaryfacebookdescription
PRIMARYCONTACTLINKEDIN | = | msdyn\_primaryinkedinid
PRIMARYCONTACTLINKEDINDESCRIPTION | = | msdyn\_primarylinkedindescrption
PRIMARYCONTACTPHONE | = | telephone1
PRIMARYCONTACTPHONEDESCRIPTION | = | msdyn\_telephone1description
PRIMARYCONTACTPHONEEXTENSION | = | msdyn\_telephone1extension
PRIMARYCONTACTTWITTER | = | msdyn\_primarytwitterid
PRIMARYCONTACTTWITTERDESCRIPTION | = | msdyn\_primarytwitteriddescription
PRIMARYCONTACTURL | = | websiteurl
PRIMARYCONTACTURLDESCRIPTION | = | msdyn\_websiteurldescription
SALESCURRENCYCODE | = | transactioncurrencyid.isocurrencycode
SALESMEMO | = | leírás

## <a name="contacts"></a>Névjegyek

A sablon mind a vevők, mind a szállítók összes elsődleges, másodlagos és harmadlagos kapcsolatfelvételi adatát szinkronizálja a Finance and Operations és a más Dynamics 365 alkalmazások között.

<!-- ![](media/dual-write-contacts.png) -->

Forrásmező | Térkép típusa | Célmező
---|---|---
CONTACTPERSONPARTYNUMBER | = | msdyn\_partynumber
ASSOCIATEDCONTACTTYPE | \<\< | nincs
FIRSTNAME | = | firstname
MIDDLENAME | = | middlename
LASTNAME | = | lastname
ASSOCIATEDCONTACTNUMBER | = | msdyn\_vendorcontactid.msdyn\_vendoraccountnumber
PRIMARYADDRESSCITY | = | address1\_city
PRIMARYADDRESSCOUNTRYREGIONID | = | address1\_country
PRIMARYADDRESSCOUNTYID | = | address1\_county
PRIMARYFAXNUMBER | = | fax
PRIMARYADDRESSSTATEID | = | address1\_stateorprovince
PRIMARYADDRESSSTREET | = | address1\_line1
PRIMARYADDRESSZIPCODE | = | address1\_postalcode
PRIMARYPHONENUMBER | = | telephone1
PRIMARYEMAILADDRESS | = | emailaddress1
EMPLOYMENTDEPARTMENT | = | department
NOTES | = | leírás
GENDER | \>\< | gendercode
GOVERNMENTIDENTIFICATIONNUMBER | = | governmentid
PRIMARYURL | = | websiteurl
MARITALSTATUS | \>\< | familystatuscode
ISRECEIVINGDIRECTMAIL | \>\< | donotemail
EMPLOYMENTPROFESSION | = | jobtitle
SPOUSENAME | = | spousesname
nincs | \>\> | msdyn\_contactforvendor
nincs | \>\> | msdyn\_contactpersonid

## <a name="customer-groups"></a>Vevőcsoportok

Ez a sablon szinkronizálja a vevőcsoport-adatokat a Finance and Operations és más Dynamics 365 alkalmazások között.

<!-- ![](media/dual-write-customer-groups.png) -->

Forrásmező | Térkép típusa | Célmező
---|---|---
CUSTOMERGROUPID | = | msdyn\_groupid
LEÍRÁS | = | msdyn\_description
ISSALESTAXINCLUDEDINPRICE | \>\< | msdyn\_issalestaxincludedinprice
PAYMENTTERMID | = | msdyn\_paymenttermid.msdyn\_name
CLEARINGPERIODPAYMENTTERMNAME | = | msdyn\_clearingperiodpaymenttermname.msdyn\_name

## <a name="customer-payment-methods"></a>Ügyfél fizetési módok

Ez a sablon szinkronizálja a fizetésimód-adatokat a Finance and Operations és más Dynamics 365 alkalmazások között.

<!-- ![](media/dual-write-customer-payment-methods.png) -->

Forrásmező | Térkép típusa | Célmező
---|---|---
NÉV | = | msdyn\_name
SZÁMLATÍPUS | \>\< | msdyn\_accounttype
DISCOUNTGRACEPERIODDAYS | = | msdyn\_discountgraceperioddays
BRIDGINGPOSTINGENABLED | \>\< | msdyn\_bridgingpostingenabled
ISSEPA | \>\< | msdyn\_issepa
LASTFILENUMBER | = | msdyn\_lastfilenumber
LASTFILENUMBERTODAY | = | msdyn\_lastfilenumbertoday
LEÍRÁS | = | msdyn\_description
PAYMENTTYPE | \>\< | msdyn\_paymenttype
CREATEANDDRAWBILLOFEXCHANGEDURINGINVOICEPOSTING | \>\< | msdyn\_invoiceupdate
PAYMENTSTATUS | \>\< | msdyn\_paymentstatus
SUMBYPERIOD | \>\< | msdyn\_sumbyperiod
ENABLEPOSTDATEDCHECKCLEARINGPOSTING | \>\< | msdyn\_enablepostdatescheckclearingposting
BILLOFEXCHANGEDRAFTTYPE | \>\< | msdyn\_billofexchangedrafttype
DIRECTDEBIT | \>\< | msdyn\_directdebit

## <a name="loyalty-cards"></a>Hűségkártyák

Ez a sablon szinkronizálja a hűségkártya-adatokat a Finance and Operations és más Dynamics 365 alkalmazások között.

<!-- ![](media/dual-write-loyalty-cards.png) -->

Forrásmező | Térkép típusa | Célmező
---|---|---
CARDNUMBER | = | msdyn\_cardnumber
CARDTENDERTYPE | \>\< | msdyn\_cardtendertype
PARTYNUMBER | = | msdyn\_partynumber
REPLACEMENTCARDNUMBER | \> | msdyn\_replacementcardnumber
OMOPERATINGUNITNUMBER | = | msdyn\_operatingunitnumber
LOYALTYENROLLMENTDATE | = | msdyn\_enrollmentdate

## <a name="payment-schedules"></a>Fizetési ütemezések

Ez a sablon szinkronizálja a fizetési ütemezések törzsadatait a vásárlókhoz és beszállítókhoz is a Finance and Operations és más Dynamics 365 alkalmazások között.

<!-- ![](media/dual-write-payment-schedules.png) -->

Forrásmező | Térkép típusa | Célmező
---|---|---
NÉV | = | msdyn\_name
LEÍRÁS | = | msdyn\_description
ALLOCATIONMETHOD | \>\< | msdyn\_allocationmethod
PAYMENTFREQUENCYUNITS | \>\< | msdyn\_paymentfrequencyunit
PAYMENTFREQUENCY | = | msdyn\_paymentfrequency
NUMBEROFPAYMENTS | = | msdyn\_numberofpayments
FIXEDPAYMENTAMOUNT | = | msdyn\_fixedpaymentamount
MINIMUMPAYMENTAMOUNT | = | msdyn\_minimumpaymentamount
SALESTAXALLOCATIONMETHOD | \>\< | msdyn\_salestaxallocationmethod
NOTES | = | msdyn\_note

## <a name="payment-schedule-lines"></a>Fizetési ütemezés sorai

Szinkronizálja a fizetési ütemezés sorok törzsadatait a vásárlókhoz és beszállítókhoz is a Finance and Operations és más Dynamics 365 alkalmazások között.

<!-- ![](media/dual-write-payment-schedule-lines.png) -->

Forrásmező | Térkép típusa | Célmező
---|---|---
PAYMENTSCHEDULENAME | = | msdyn\_paymentschedule.msdyn\_name
PAYMENTSCHEDULENAME | \> | msdyn\_name
LINENUMBER | = | msdyn\_LineNumber
PERIODSAFTERDUEDATE | = | msdyn\_periodsafterduedate
PERCENTORAMOUNT | \>\< | msdyn\_percentoramount
PERCENTORAMOUNTVALUE | = | msdyn\_percentoramountvalue

## <a name="payment-days"></a>Fizetési napok

Ez a sablon szinkronizálja a fizetési napok hivatkozási adatait a vásárlókhoz és beszállítókhoz is a Finance and Operations és más Dynamics 365 alkalmazások között.

<!-- ![](media/dual-write-payment-days.png) -->

Forrásmező | Térkép típusa | Célmező
---|---|---
NÉV | = | msdyn\_name
LEÍRÁS | = | msdyn\_description

## <a name="payment-day-lines"></a>Fizetési nap sorai

Ez a sablon szinkronizálja a fizetésinap-sorok hivatkozási adatait a vásárlókhoz és beszállítókhoz is a Finance and Operations és más Dynamics 365 alkalmazások között.

<!-- ![](media/dual-write-payment-day-lines.png) -->

Forrásmező | Térkép típusa | Célmező
---|---|---
CDSINTEGRATIONKEY | = | msdyn\_paymentdaylineid
FREQUENCY | \>\< | msdyn\_frequency
DAYOFWEEK | \>\< | msdyn\_dayofweek
DAYOFMONTH | = | msdyn\_dayofmonth
NÉV | = | msdyn\_paymentday.msdyn\_name

## <a name="payment-terms"></a>Fizetési feltételek

Ez a sablon szinkronizálja a fizetési feltételek (fizetés feltételei) hivatkozási adatait a vásárlókhoz és beszállítókhoz is a Finance and Operations és a Dynamics 365 alkalmazások között.

<!-- ![](media/dual-write-payment-terms.png) -->

Forrásmező | Térkép típusa | Célmező
---|---|---
LEÍRÁS | = | msdyn\_description
NÉV | = | msdyn\_name
NUMBEROFMONTHS | = | msdyn\_numberofmonth
CUTOFFDAYOFMONTH | = | msdyn\_cutoffdayofmonth
ISCASHPAYMENT | \>\< | msdyn\_iscashpayment
NUMBEROFDAYS | = | msdyn\_days
ISCERTIFIEDCOMPANYCHECK | \>\< | msdyn\_iscertifiedcompanycheck
ISDEFAULTPAYMENTTERM | \>\< | msdyn\_isdefaultpaymentterm
CREDITCARDPAYMENTTYPE | \>\< | msdyn\_creditcardpaymenttype
CREDITCARDCREDITCHECKTYPE | \>\< | msdyn\_creditcardcreditchecktype
PAYMENTDAYNAME | = | msdyn\_paymentdayname.msdyn\_name
PAYMENTMETHODTYPE | \>\< | msdyn\_paymentmethodtype
PAYMENTSCHEDULENAME | = | msdyn\_paymentschedulename.msdyn\_name

## <a name="name-affixes"></a>Névutótagok

Ez a sablon szinkronizálja a névutótagok hivatkozási adatait a vásárlókhoz és beszállítókhoz is a Finance and Operations és más Dynamics 365 alkalmazások között.

<!-- ![](media/dual-write-name-affixes.png) -->

Forrásmező | Térkép típusa | Célmező
---|---|---
AFFIX | = | msdyn\_affix
TÍPUS | \>\< | msdyn\_affixtype
LEÍRÁS | = | msdyn\_description
