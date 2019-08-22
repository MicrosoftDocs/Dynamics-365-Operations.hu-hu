---
title: Szállító integrált alapadatai
description: Ez a cikk a szállítói adatok Finance and Operations és Common Data Service közötti integrációját ismerteti.
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
ms.openlocfilehash: 45808bc35aba04df6fcaf6b1cbfcc2461b0b65cb
ms.sourcegitcommit: 02c223b44ac7196df675afac61c6783f467d1983
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/24/2019
ms.locfileid: "1789195"
---
## <a name="integrated-vendor-master"></a>Szállító integrált alapadatai

[!include [banner](../includes/banner.md)]

[!include [preview](../includes/preview-banner.md)]

A *szállító* kifejezés olyan szállító szervezetet vagy kizárólagos tulajdonost jelöl, amely része az ellátási láncnak és árukat biztosít a cégnek. A *szállító* fogalmat ugyan kiterjedten használják a Microsoft Dynamics 365 for Finance and Operations rendszerben, de nem csak a Dynamics 365 for Customer Engagement szolgáltatásban használatos. Egyes cégek túlterhelik a Számla entitást, hogy mind a vevők, mind a szállítók adatait tudják tárolni. Más vállalkozások egyéni szállítói fogalmat használnak. A Common Data Service integrációja mindkét megoldást támogatja. Ennek megfelelően az egyes üzleti esetekben bármelyiket használhatja.

A szállítói adatok Finance and Operations és Customer Engagement közötti integrációjával több főkiszolgáló használható az adatokhoz. A szállítói adatokat – a forrásuktól függetlenül – a rendszer a háttérben integrálja az alkalmazások között és az infrastruktúra különbségeitől függetlenül. 

### <a name="vendor-data-flow"></a>Szállítói adatok áramlása

Ha a szállítói alapadatokhoz a Customer Engagement rendszert szeretné használni, és el szeretné különíteni a szállítók és a vevők adatait, akkor használhatja az új szállítói kialakítást.

![Szállítói adatok áramlása](media/dual-write-vendor-data-flow.png)

Ha a szállítói alapadatokhoz a Customer Engagement rendszert szeretné használni, akkor érdemes továbbra is a Számla entitást használni a szállítók adatainak tárolásához; használhatja az új, bővített szállítói kialakítást. Ebben a kialakításban a bővített szállítói adatok (például a szállítói csoport vagy a szállítói feladási profilok) tárolása a szállítói információk között történik.

![Bővített szállítói adatok áramlása](media/dual-write-vendor-detail.jpg)

A szállítók és a vevők kapcsolatfelvételi adatai hasonlóak. A személyek kapcsolatfelvételi adatainak a tárolásához és lekéréséhez ugyanazt az entitást használja a rendszer a háttérben.

## <a name="templates"></a>Sablonok

A szállítói adatok között a szállító minden részlete (például a szállítói csoport, a címek, a kapcsolatfelvételi adatok, a fizetési és a számlázási profil) szerepel. Ahogy az alábbi táblázatban látható, az entitásleképezések gyűjteménye együtt működik a szállítói adatokkal végzett interakciók során.

Finance and Operations  | A Customer Engagement alkalmazás
------------------------|---------------------------------
Szállító V2               | Könyvelési számla
Szállító V2               | Msdyn\_vendors
CDS névjegyek V2         | Névjegy
Szállítói csoportok           | Msdyn\_vendorgroups
Szállítói fizetési mód   | Msdyn\_vendorpaymentmethods
Fizetési ütemezés        | Msdyn\_paymentschedules
Fizetési ütemezés        | Msdyn\_paymentschedulelines
Fizetési nap, CDS         | Msdyn\_paymentdays
Fizetési nap sorai, CDS   | Msdyn\_paymentdaylines
Fizetési feltételek        | Msdyn\_paymentterms
Névutótagok            | Msdyn\_nameaffixes

[!include [banner](../includes/dual-write-symbols.md)]

## <a name="vendor-v2-and-account"></a>Szállító V2 és számla 

Azok a cégek, amelyek a Számla entitással tárolják a szállítói adatokat, továbbra is változás nélkül használhatják ezt a megoldást. A Finance and Operations integrációjának köszönhető explicit szállítói funkciókat ugyancsak kihasználhatják.

## <a name="vendor-v2-and-msdyn_vendors"></a>Szállító V2 és Msdyn\_vendors

A szállítókhoz egyéni megoldást használó cégek a Finance and Operations integrációjának köszönhetően kihasználhatják a Common Data Service rendszerben bevezetett kész szállítói fogalmat. 

<!-- ![vendor mappings](media/dual-write-vendors-1.png) -->

<!-- ![vendor mappings](media/dual-write-vendors-2.png) -->

<!-- ![vendor mappings](media/dual-write-vendors-3.png) -->

Forrásmező | Térkép típusa | Célmező
---|---|---
SZÁLLÍTÓSZÁMLASZÁMA | = | msdyn\_vendoraccountnumber
SZÁLLÍTÓICSOPORTAZONOSÍTÓJA | = | msdyn\_vendorgroupid.msdyn\_vendorgroup
SZÁLLÍTÓISZERVEZETNEVE | = | msdyn\_name
SZÁLLÍTÓIFÉLTÍPUSA | \>\< | msdyn\_isperson
SZEMÉLYUTÓNEVE | = | msdyn\_firstname
SZEMÉLYVEZETÉKNEVE | = | msdyn\_lastname
HITELKERET | = | msdyn\_vendorcreditlimit
KÜLSŐENTITÁS | \>\< | msdyn\_isforeignentity
EGYSZERISZÁLLÍTÓ | \>\< | msdyn\_isonetimevendor
CÍMÉPÜLETBLOKKJA | = | msdyn\_addressbuildingcompliment
SZERMÉLYGYERMEKEINEKNEVE | = | msdyn\_childrennames
CÍMVÁROSA | = | msdyn\_addresscity
CÍMORSZÁGÁNAKRÉGIÓAZONOSÍTÓJA | = | msdyn\_addresscountryregionid
CÍMORSZÁGÁNAKRÉGIÓISOKÓDJA | = | msdyn\_addresscountryregionisocode
CÍMMEGYÉJÉNEKAZONOSÍTÓJA | = | msdyn\_addresscountyid
HITELMINŐSÍTÉS | = | msdyn\_creditrating
CÍMLEÍRÁSA | = | msdyn\_addressdescription
CÍMKERÜLETÉNEKNEVE | = | msdyn\_addressdistrictname
DUNSSZÁM | = | msdyn\_dunsnumber
ETNIKUMAZONOSÍTÓ | = | msdyn\_ethnicorigin
FORMÁZOTTELSŐDLEGESCÍM | = | msdyn\_formattedprimaryaddress
SZEMÉLYHOBBIJAI | = | msdyn\_hobbies
SZEMÉLYMONOGRAMJA | = | msdyn\_initials
NYELVAZONOSÍTÓ | = | msdyn\_languageid
SZEMÉLYVEZETÉKNEVÉNEKELŐTAGJA | = | msdyn\_lastnameprefix
SZEMÉLYMÁSODIKUTÓNEVE | = | msdyn\_middlename
SZERVEZETSZÁMA | = | msdyn\_organizationnumber
SAJÁTSZÁMLASZÁM | = | msdyn\_ourvendoraccountnumber
FIZETÉSIAZONOSÍTÓ | = | msdyn\_paymentid
SZEMÉLYUTÓNEVEKIEJTVE | = | msdyn\_phoneticfirstname
SZEMÉLYMÁSODIKUTÓNEVEKIEJTVE | = | msdyn\_phoneticmiddlename
SZEMÉLYVEZETÉKNEVEKIEJTVE | = | msdyn\_phoneticlastname
SZERVEZETNEVEKIEJTVE | = | msdyn\_organizationphoneticname
POSTAFIÓK | = | msdyn\_addresspostbox
ELSŐDLEGESURL | = | msdyn\_primarycontacturl
ELSŐDLEGESEMAILCÍM | = | msdyn\_primaryemailaddress
ELSŐDLEGESEMAILCÍMLEÍRÁSA | = | msdyn\_primaryemailaddressdescription
ELSŐDLEGESFACEBOOKOLDAL | = | msdyn\_primaryfacebook
ELSŐDLEGESFACEBOOKLEÍRÁS | = | msdyn\_primaryfacebookdescription
ELSŐDLEGESFAXSZÁM | = | msdyn\_primaryfaxnumber
ELSŐDLEGESFAXSZÁMLEÍRÁSA | = | msdyn\_primaryfaxnumberdescription
ELSŐDLEGESFAXSZÁMMELLÉKE | = | msdyn\_primaryfaxnumberextension
ELSŐDLEGESLINKEDINFIÓK | = | msdyn\_primarylinkedin
ELSŐDLEGESLINKEDINLEÍRÁS | = | msdyn\_primarylinkedindescription
ELSŐDLEGESTELEFONSZÁM | = | msdyn\_pimaryphonenumber
ELSŐDLEGESTELEFONSZÁMLEÍRÁSA | = | msdyn\_primaryphonenumberdescription
ELSŐDLEGESTELEFONSZÁMMELLÉKE | = | msdyn\_primaryphonenumberextension
ELSŐDLEGESTELEXSZÁM | = | msdyn\_primarytelex
ELSŐDLEGESTELEXSZÁMLEÍRÁSA | = | msdyn\_primarytelexdescription
ELSŐDLEGESTWITTERFIÓK | = | msdyn\_primarytwitter
ELSŐDLEGESTWITTERLEÍRÁS | = | msdyn\_primarytwitterdescription
ELSŐDLEGESURLLEÍRÁSA | = | msdyn\_primaryurldescription
SZEMÉLYSZAKMAIUTÓTAGJA | = | msdyn\_professionalsuffix
SZEMÉLYSZAKMAICÍME | = | msdyn\_professionatitle
CÍMÁLLAMÁNAKAZONOSÍTÓJA | = | msdyn\_addressstateid
CÍMUTCANEVE | = | msdyn\_addressstreet
CÍMHÁZSZÁMA | = | msdyn\_addressstreetnumber
SZÁLLÍTÓISMERTNEVE | = | msdyn\_vendorknownasname
CÍMIRÁNYÍTÓSZÁMA | = | msdyn\_addresszipcode
ALAPÉRTELMEZETTFIZETÉSINAPNEVE | = | msdyn\_defaultpaymentdayname.msdyn\_name
ALAPÉRTELMEZETTFIZETÉSIÜTEMEZÉSNEVE | = | msdyn\_paymentschedule.msdyn\_name
ALAPÉRTELMEZETTFIZETÉSIFELTÉTELEKNEVE | = | msdyn\_paymentterms.msdyn\_name
CSAKELFOGADOTTAJÁNLATOKKAL | \>\< | msdyn\_hasonlytakenbids
KISEBBSÉGHEZTARTOZÓ | \>\< | msdyn\_isminorityowned
SZÁLLÍTÓHELYITULAJDONBAN | \>\< | msdyn\_isvendorlocallyowned
SZOLGÁLTATÁSTULAJDONOSAVETERÁN | \>\< | msdyn\_isserviceveteranowned
TULAJDONOSROKKANT | \>\< | msdyn\_ownerisdisabled
TULAJDONOSNŐ | \>\< | msdyn\_womanowner
SZEMÉLYÉVFORDULÓJÁNAKNAPJA | = | msdyn\_personanniversaryday
SZEMÉLYÉVFORDULÓJÁNAKÉVE | = | msdyn\_anniversaryyear
SZEMÉLYSZÜLETÉSNAPJA | = | msdyn\_birthday
SZEMÉLYSZÜLETÉSIÉVE | = | msdyn\_birthyear
SZERVEZETALKALMAZOTTAINAKSZÁMA | = | msdyn\_numberofemployees
SZÁLLÍTÓVÁRAKOZTATÁSÁNAKFELOLDÁSIDÁTUMA | = | msdyn\_vendoronholdreleasedate
SZÁLLÍTÓIFÉLSZÁMA | = | msdyn\_vendorpartynumber
CÍMHELYAZONOSÍTÓJA | = | msdyn\_addresslocationid
SZEMÉLYÉVFORDULÓJÁNAKHÓNAPJA | = | msdyn\_vendorpersonanniversarymonth
SZEMÉLYSZÜLETÉSIHÓNAPJA | = | msdyn\_vendorpersonbirthmonth
SZEMÉLYCSALÁDIÁLLAPOTA | \>\< | msdyn\_maritalstatus
CÍMFÖLDRAJZISZÉLESSÉGE | \>\> | msdyn\_addresslatitude
CÍMFÖLDRAJZIHOSSZÚSÁGA | \>\> | msdyn\_addresslongitude
VÁRAKOZTATOTT | \>\< | msdyn\_onholdstatus
PÉNZNEMKÓD | = | msdyn\_currencycode.isocurrencycode
SZÁLLÍTÓAHUBZONETERÜLETEN | \>\< | msdyn\_isvendorlocatedinhubzone
SZÁLLÍTÓALAPÉRTELMEZETTFIZETÉSIMÓDJÁNAKNEVE | = | msdyn\_vendorpaymentmethod.msdyn\_name
SZÁMLASZÁLLÍTÓISZÁMLASZÁMA | = | msdyn\_invoicevendoraccountnumber.msdyn\_vendoraccountnumber
SZEMÉLYNEME | \>\< | msdyn\_gender
AZÁRAKFORGALMIADÓVAL | \>\< | msdyn\_priceincludessalestax
FORGALMIADÓCSOPORTKÓDJA | = | msdyn\_taxgroup.msdyn\_name
SZÁLLÍTÓIÁRTŰRÉSHATÁRÁNAKCSOPORTAZONOSÍTÓJA | = | msdyn\_pricetolerancegroup.msdyn\_groupid

## <a name="contacts"></a>Névjegyek

A sablon mind a vevők, mind a szállítók összes elsődleges, másodlagos és harmadlagos kapcsolatfelvételi adatát szinkronizálja a Finance and Operations és a Customer Engagement között. Az entitásleképezés részletei a [Vevő integrált alapadatai](dual-write-customer.md#contacts) című cikkben találhatók.

## <a name="vendor-groups"></a>Szállítói csoportok

A sablon szinkronizálja a szállítói csoportok adatait a Finance and Operations és a Customer Engagement között.

<!-- ![vendor groups mappings](media/dual-write-vendor-groups.png) -->

Forrásmező | Térkép típusa | Célmező
---|---|---
ALAPÉRTELMEZETTFIZETÉSIFELTÉTELNEVE | = | msdyn\_paymentterms.msdyn\_name
LEÍRÁS | = | msdyn\_description
SZÁLLÍTÓICSOPORTAZONOSÍTÓJA | = | msdyn\_vendorgroup
ELSZÁMOLÁSIIDŐSZAKFIZETÉSIFELTÉTELÉNEKNEVE | = | msdyn\_clearingperiodpaymentpermname.msdyn\_name

### <a name="vendor-payment-method"></a>Szállítói fizetési mód

A sablon szinkronizálja a szállítói fizetési mód részleteit a Finance and Operations és a Customer Engagement között.

<!-- ![vendor payment method mappings](media/dual-write-vendor-payment-method.png) -->

Forrásmező | Térkép típusa | Célmező
---|---|---
NÉV | = | msdyn\_name
LEÍRÁS | = | msdyn\_description
ÖSSZEGIDŐSZAKSZERINT | \>\< | msdyn\_sumbyperiod
KEDVEZMÉNYTÜRELMIIDŐSZAKANAPOKBAN | = | msdyn\_discountgraceperioddays
FIZETÉSÁLLAPOTA | \>\< | msdyn\_paymentstatus
FIZETÉSIMÁSOLATOKENGEDÉLYEZÉSE | \>\< | msdyn\_allowpaymentcopies
FIZETÉSTÍPUSA | \>\< | msdyn\_paymenttype
UTOLSÓFÁJLSZÁMA | = | msdyn\_lastfilenumber
UTOLSÓFÁJLSZÁMAMA | = | msdyn\_lastfilenumbertoday
SZÁMLATÍPUS | \>\< | msdyn\_accounttype
ÁTHIDALÓFELADÁSENGEDÉLYEZVE | \>\< | msdyn\_bridgingposting
JÖVŐBENESEDÉKESCSEKKELSZÁMOLÁSIFELADÁSÁNAKENGEDÉLYEZÉSE | \>\< | msdyn\_postdatedcheckclearingposting
KÖTELEZVÉNYVÁZLATTÍPUSA | \>\< | msdyn\_promissorynotedrafttype
BESZEDÉSIMEGBÍZÁS | \>\< | msdyn\_directdebit

