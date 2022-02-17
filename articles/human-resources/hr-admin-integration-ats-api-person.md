---
title: Személy
description: Ez a témakör a Személy entitást írja le a Dynamics 365 Human Resources rendszerhez.
author: jaredha
ms.date: 02/05/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2021-02-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 728e383be44949ec7f1e51feb5157c61679b3e7b
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/31/2022
ms.locfileid: "8068659"
---
# <a name="person"></a>Személy


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Ez a témakör a Személy entitást írja le a Dynamics 365 Human Resources rendszerhez.

Fizikai név: mshr_dirpersonentity

### <a name="description"></a>Leírás

Ez az entitás tartalmazza a jelölt személyes adatait.

## <a name="json-representation"></a>JSON-ábrázolás

```json
{
    "mshr_partynumber": "String",
    "mshr_name": "String",
    "mshr_namealias": "String",
    "mshr_knownas": "String",
    "mshr_languageid": "String",
    "mshr_addressbooks": "String",
    "mshr_anniversaryday": Int,
    "mshr_anniversarymonth": Int,
    "mshr_anniversaryyear": Int,
    "mshr_birthday": Int,
    "mshr_birthmonth": Int,
    "mshr_birthyear": Int,
    "mshr_childrennames": "String",
    "mshr_gender": Int,
    "mshr_hobbies": "String",
    "mshr_initials": "String",
    "mshr_maritalstatus": Int,
    "mshr_phoneticfirstname": "String",
    "mshr_phoneticlastname": "String",
    "mshr_phoneticmiddlename": "String",
    "mshr_personalsuffix": "String",
    "mshr_personaltitle": "String",
    "mshr_professionalsuffix": "String",
    "mshr_professionaltitle": "String",
    "mshr_fullprimaryaddress": "String",
    "mshr_addresscity": "String",
    "mshr_addresscountryregionid": "String",
    "mshr_addresscountryregionisocode": "String",
    "mshr_addresscounty": "String",
    "mshr_addressdistrictname": "String",
    "mshr_addresslatitude": Decimal,
    "mshr_addresslocationid": "000003212",
    "mshr_addresslocationroles": "Home",
    "mshr_addresslongitude": Decimal,
    "mshr_addressstate": "String",
    "mshr_addressstreet": "String",
    "mshr_addressvalidfrom": "Date",
    "mshr_addressvalidto": "Date",
    "mshr_addresszipcode": "String",
    "mshr_addressisprivate": Int,
    "mshr_addressdescription": "String",
    "mshr_primarycontactemail": "String",
    "mshr_primarycontactemaildescription": "String",
    "mshr_primarycontactemailisim": Int,
    "mshr_primarycontactemailpurpose": "String",
    "mshr_primarycontactfax": "String",
    "mshr_primarycontactfaxdescription": "String",
    "mshr_primarycontactfaxextension": "String",
    "mshr_primarycontactfaxpurpose": "String",
    "mshr_primarycontactphone": "String",
    "mshr_primarycontactphonedescription": "String",
    "mshr_primarycontactphoneextension": "String",
    "mshr_primarycontactphoneismobile": Int,
    "mshr_primarycontactphonepurpose": "String",
    "mshr_primarycontacttelex": "String",
    "mshr_primarycontacttelexdescription": "String",
    "mshr_primarycontacttelexpurpose": "String",
    "mshr_primarycontacturl": "String",
    "mshr_primarycontacturldescription": "String",
    "mshr_primarycontacturlpurpose": "String",
    "mshr_primarycontactfacebook": "String",
    "mshr_primarycontactfacebookdescription": "String",
    "mshr_primarycontactfacebookisprivate": Int,
    "mshr_primarycontactfacebookpurpose": "String",
    "mshr_primarycontactlinkedin": "String",
    "mshr_primarycontactlinkedindescription": "String",
    "mshr_primarycontactlinkedinisprivate": Int,
    "mshr_primarycontactlinkedinpurpose": "String",
    "mshr_primarycontacttwitter": "String",
    "mshr_primarycontacttwitterdescription": "String",
    "mshr_primarycontacttwitterisprivate": Int,
    "mshr_primarycontacttwitterpurpose": "String",
    "mshr_partytype": "String",
    "mshr_namesequencedisplayas": "String",
    "mshr_firstname": "String",
    "mshr_lastnameprefix": "String",
    "mshr_lastname": "String",
    "mshr_middlename": "String",
    "mshr_electroniclocationid": "String",
    "mshr_dirpersonentityid": "Guid",
    "mshr_addresstimezone": Int
}
```

## <a name="properties"></a>Tulajdonságok

| Tulajdonság<br>**Fizikai név**<br>**_Típus_** | Használat | Leírás |
| --- | --- | --- |
| **Személyentitás azonosítója**<br>mshr_dirpersonentityid<br>*GUID* | Írásvédett<br>Szükséges<br>Rendszer által előállított | Az entitásrekord rendszer által generált egyedi azonosítója. |
| **Fél száma**<br>mshr_partynumber<br>*Sztring* | Írásvédett<br>Szükséges<br>Rendszer által előállított | A személy felhasználó által olvasható, rendszer által generált egyedi azonosítója.  |
| **Név**<br>mshr_name<br>*Sztring* | Írásvédett<br>Szükséges | A mező értéke a következők összefűzése: Utónév, Második utónév, Vezetéknév előtagja és Vezetéknév, a **Névsorrend megjelenítése meghatározott sorrendben** mezőben. |
| **Név aliasa**<br>mshr_namealias<br>*Sztring* | Olvasás/írás<br>Választható | A személy számára biztosított aliasnév. |
| **Más néven**<br>mshr_knownas<br>*Sztring* | Olvasás/írás<br>Választható | A személy esetében használható név, ha más néven ismerik. |
| **Nyelvazonosító**<br>mshr_languageid<br>*Sztring* | Olvasás/írás<br>Választható | A személy elsődleges nyelvének nyelvazonosítója az ISO 639-1 formátum szerinti meghatározásnak megfelelően. |
| **Címjegyzékek**<br>mshr_addressbooks<br>*Sztring* | Olvasás/írás<br>Választható | Az a címjegyzék, amelyhez a személy hozzárendelhető. A szervezethez beállított címjegyzékek az mshr_diraddressbooksentity entitásban jelennek meg. |
| **Évforduló napja**<br>mshr_anniversaryday<br>*Int* | Olvasás/írás<br>Választható | A személy évfordulós dátumának napja. |
| **Évforduló hónapja**<br>mshr_anniversarymonth<br>*mshr_monthsofyear beállításkészlet* | Olvasás/írás<br>Választható | A személy évfordulós dátumának hónapja. |
| **Évforduló éve**<br>mshr_anniversaryyear<br>*Int* | Olvasás/írás<br>Választható | A személy évfordulós dátumának éve. |
| **Születésnap**<br>mshr_birthday<br>*Int* | Olvasás/írás<br>Választható | A személy születési dátuma. |
| **Születési hónap**<br>mshr_birthmonth<br>*mshr_monthsofyear beállításkészlet* | Olvasás/írás<br>Választható | A személy születési dátumának hónapja. |
| **Születési év**<br>mshr_birthyear<br>*Int* | Olvasás/írás<br>Választható | A személy születési dátumának éve. |
| **Gyermekek neve**<br>mshr_childrennames<br>*Sztring* | Olvasás/írás<br>Választható | A személy gyermekei nevének sztringje. Nincs szükség elválasztásra. |
| **Nem**<br>mshr_gender<br>*mshr_hcmpersongender beállításkészlet* | Olvasás/írás<br>Választható | A személy neme. |
| **Hobbik**<br>mshr_hobbies<br>*Sztring* | Olvasás/írás<br>Választható | A személy hobbijai. |
| **Kezdőbetűk**<br>mshr_initials<br>*Sztring* | Olvasás/írás<br>Választható | A személy nevének kezdőbetűi. |
| **Családi állapot**<br>mshr_maritalstatus<br>*mshr_hcmpersonmaritalstatus beállításkészlet* | Olvasás/írás<br>Választható | A személy családi állapota. |
| **Utónév fonetikusan**<br>mshr_phoneticfirstname<br>*Sztring* | Olvasás/írás<br>Választható | A személy utónevének fonetikus kiejtése. |
| **Vezetéknév fonetikusan**<br>mshr_phoneticlastname<br>*Sztring* | Olvasás/írás<br>Választható | A személy vezetéknevének fonetikus kiejtése. |
| **Középső név fonetikusan**<br>mshr_phoneticmiddlename<br>*Sztring* | Olvasás/írás<br>Választható | A személy vezetéknevének fonetikus kiejtése. |
| **Személyes utótag**<br>mshr_personalsuffix<br>*Sztring* | Olvasás/írás<br>Választható | A személy személyes utótagja. Érvényes értékek az mshr_dirnameaffixentity entitásban, ahol az mshr_type utótag (200000001). |
| **Személyes megszólítás**<br>mshr_personaltitle<br>*Sztring* | Olvasás/írás<br>Választható | A személy személyes megszólítása. Érvényes értékek az mshr_dirnameaffixentity entitásban, ahol az mshr_type megszólítás (200000000).
| **Szakmai utótag**<br>mshr_professionalsuffix<br>*Sztring* | Olvasás/írás<br>Választható | A szakmai utótag. |
| **Szakmai beosztás**<br>mshr_professionaltitle<br>*Sztring* | Olvasás/írás<br>Választható | A szakmai beosztás. |
| **Teljes elsődleges cím**<br>mshr_fullprimaryaddress<br>*Sztring* | Olvasás/írás<br>Választható | A személy teljes elsődleges címe, az elsődleges címmezők összefűzése. |
| **Város**<br>mshr_addresscity<br>*Sztring* | Olvasás/írás<br>Választható | A személy elsődleges címének városa. Beállítás az mshr_logisticsaddresscityentity entitásban. |
| **Cím Ország Régió**<br>mshr_addresscountryregionid<br>*Sztring* | Olvasás/írás<br>Választható | A személy elsődleges címének országa/régiója. Érvényes értékek az mshr_logisticsaddresscountryregionentity entitásban. |
| **Cím Ország Régió ISO-kód**<br>mshr_addresscountryregionisocode<br>*Sztring* | Olvasás/írás<br>Választható | A személy elsődleges címéhez tartozó ország/régió ISO-kódja. |
| **Cím Megye**<br>mshr_addresscounty<br>*Sztring* | Olvasás/írás<br>Választható | A személy elsődleges címének megyéje. Beállítás az mshr_logisticsaddresscountyentity entitásban. |
| **Cím Körzet Név**<br>mshr_addressdistrictname<br>*Sztring* | Olvasás/írás<br>Választható | A személy elsődleges címének körzete. Beállítás az mshr_logisticsaddressdistrictentity entitásban. |
| **Cím Szélességi fok**<br>mshr_addresslatitude<br>*Sztring* | Olvasás/írás<br>Választható | A személy elsődleges címének szélességi foka. |
| **Cím Helyazonosító**<br>mshr_addresslocationid<br>*Sztring* | Olvasás/írás<br>Választható | A személy elsődleges címe helyének egyedi azonosítója. Érvényes értékek az mshr_logisticspostaladdresslocationcdsentity entitásban. |
| **Cím Hely szerepkörei**<br>mshr_addresslocationroles<br>*Sztring* | Olvasás/írás<br>Választható | A személy elsődleges címe helyének szerepkörei. Beállítás az mshr_logisticslocationrolecdsentity entitásban. |
| **Cím Hosszúsági fok**<br>mshr_addresslongitude<br>*Sztring* |  Olvasás/írás<br>Választható | A személy elsődleges címének hosszúsági foka. |
| **Cím Állam**<br>mshr_addressstate<br>*Sztring* | Olvasás/írás<br>Választható | A személy elsődleges címének állama. Beállítás az mshr_logisticsaddressstateentity entitásban. |
| **Cím Utca**<br>mshr_addressstreet<br>*Sztring* | Olvasás/írás<br>Választható | A személy elsődleges címének utcája. |
| **Cím érvényességének kezdete**<br>mshr_addressvalidfrom<br>*Dátum* | Olvasás/írás<br>Választható | Az a dátum, amelytől a személy elsődleges címe érvényes. |
| **Cím érvényességének vége**<br>mshr_addressvalidto<br>*Dátum* | Olvasás/írás<br>Választható | Az a dátum, ameddig a személy elsődleges címe érvényes. |
| **Cím irányítószám**<br>mshr_addresszipcode<br>*Sztring* | Olvasás/írás<br>Választható | A személy elsődleges címének postai irányítószáma. Beállítás az mshr_logisticsaddresspostalcodeentity entitásban. |
| **A cím privát**<br>mshr_addressisprivate<br>*mshr_noyes beállításkészlet* | Olvasás/írás<br>Választható | Meghatározza, hogy a személy elsődleges címe meg van-e osztva a szervezet más tagjaival. |
| **Cím leírása**<br>mshr_addressdescription<br>*Sztring* | Olvasás/írás<br>Választható | A személy elsődleges címének leírása. |
| **Elsődleges kapcsolattartási e-mail-cím**<br>mshr_primarycontactemail<br>*Sztring* | Olvasás/írás<br>Választható | A személy elsődleges e-mail-címe. |
| **Elsődleges kapcsolattartási e-mail leírása**<br>mshr_primarycontactemaildescription<br>*Sztring* | Olvasás/írás<br>Választható | Az elsődleges e-mail-címhez megadott leírás. |
| **Elsődleges kapcsolattartási e-mail-cím IM**<br>mshr_primarycontactemailisim<br>*mshr_noyes beállításkészlet* | Olvasás/írás<br>Választható | Meghatározza, hogy az elsődleges e-mail-cím elérhető-e azonnali üzenetküldésre. |
| **Elsődleges kapcsolattartási e-mail-cím célja**<br>mshr_primarycontactemailpurpose<br>*Sztring* | Olvasás/írás<br>Választható | Az elsődleges e-mail-cím célja. Beállítás az mshr_logisticslocationroleentity entitásban. |
| **Elsődleges kapcsolattartási fax**<br>mshr_primarycontactfax<br>*Sztring* | Olvasás/írás<br>Választható | Elsődleges faxszám. |
| **Elsődleges kapcsolattartási fax leírása**<br>mshr_primarycontactfaxdescription<br>*Sztring* | Olvasás/írás<br>Választható | Az elsődleges faxszámhoz megadott leírás. |
| **Elsődleges kapcsolattartási faxmellék**<br>mshr_primarycontactfaxextension<br>*Sztring* | Olvasás/írás<br>Választható | Az elsődleges faxszám melléke. |
| **Elsődleges kapcsolattartási fax célja**<br>mshr_primarycontactfaxpurpose<br>*Sztring* | Olvasás/írás<br>Választható | Az elsődleges faxszám célja. Beállítás az mshr_logisticslocationroleentity entitásban.
| **Elsődleges kapcsolattartási telefonszám**<br>mshr_primarycontactphone<br>*Sztring* | Olvasás/írás<br>Választható | Elsődleges telefonszám. |
| **Elsődleges kapcsolattartási telefonszám leírása**<br>mshr_primarycontactphonedescription<br>*Sztring* | Olvasás/írás<br>Választható | Az elsődleges telefonszámhoz megadott leírás. |
| **Elsődleges kapcsolattartási telefonmellék**<br>mshr_primarycontactphoneextension<br>*Sztring* | Olvasás/írás<br>Választható | Az elsődleges telefonszám melléke. |
| **Elsődleges kapcsolattartási telefonszám mobiltelefon**<br>mshr_primarycontactphoneismobile<br>*mshr_noyes beállításkészlet* | Olvasás/írás<br>Választható | Meghatározza, hogy az elsődleges telefonszám mobiltelefonszám-e. |
| **Elsődleges kapcsolattartási telefon célja**<br>mshr_primarycontactphonepurpose<br>*Sztring* | Olvasás/írás<br>Választható | Az elsődleges telefonszám célja. Beállítás az mshr_logisticslocationroleentity entitásban. |
| **Elsődleges kapcsolattartási telexszám**<br>mshr_primarycontacttelex<br>*Sztring* | Olvasás/írás<br>Választható | Elsődleges telexszám. |
| **Elsődleges kapcsolattartási telex leírása**<br>mshr_primarycontacttelexdescription<br>*Sztring* | Olvasás/írás<br>Választható | A személy elsődleges telexszámához megadott leírás. |
| **Elsődleges kapcsolattartási telex célja**<br>mshr_primarycontacttelexpurpose<br>*Sztring* | Olvasás/írás<br>Választható | A személy elsődleges telexszámának célja. Beállítás az mshr_logisticslocationroleentity entitásban. |
| **Elsődleges kapcsolattartási URL**<br>mshr_primarycontacturl<br>*Sztring* | Olvasás/írás<br>Választható | Az elsődleges URL-cím. |
| **Elsődleges kapcsolattartási URL leírása**<br>mshr_primarycontacturldescription<br>*Sztring* | Olvasás/írás<br>Választható | A személy elsődleges URL-címének leírása. |
| **Elsődleges kapcsolattartási URL célja**<br>mshr_primarycontacturldescription<br>*Sztring* | Olvasás/írás<br>Választható | A személy elsődleges URL-címének célja. Beállítás az mshr_logisticslocationroleentity entitásban. |
| **Elsődleges kapcsolattartási Facebook-fiók**<br>mshr_primarycontactfacebook<br>*Sztring* | Olvasás/írás<br>Választható | Elsődleges Facebook-fiók. Azonosító: felhasználói azonosító. |
| **Elsődleges kapcsolattartási Facebook-fiók leírása**<br>mshr_primarycontactfacebookdescription<br>*Sztring* | Olvasás/írás<br>Választható | A személy elsődleges Facebook-fiókjának leírása. |
| **Az elsődleges kapcsolattartási Facebook-fiók privát**<br>mshr_primarycontactfacebookisprivate<br>*mshr_noyes beállításkészlet* | Olvasás/írás<br>Választható | Meghatározza, hogy az elsődleges Facebook-fiók látható-e más felhasználók számára. |
| **Elsődleges kapcsolattartási Facebook-fiók célja**<br>mshr_primarycontactfacebookpurpose<br>*Sztring* | Olvasás/írás<br>Választható | A személy elsődleges Facebook-fiókjának célja. Beállítás az mshr_logisticslocationroleentity entitásban. |
| **Elsődleges kapcsolattartási LinkedIn-fiók**<br>mshr_primarycontactlinkedin<br>*Sztring* | Olvasás/írás<br>Választható | Elsődleges LinkedIn-fiók. Azonosító: felhasználónév. |
| **Elsődleges kapcsolattartási LinkedIn-fiók leírása**<br>mshr_primarycontactlinkedindescription<br>*Sztring* | Olvasás/írás<br>Választható | A személy elsődleges LinkedIn-fiókjának leírása. |
| **Az elsődleges kapcsolattartási LinkedIn-fiók privát**<br>mshr_primarycontactlinkedinisprivate<br>*mshr_noyes beállításkészlet* | Olvasás/írás<br>Választható | Meghatározza, hogy a személy elsődleges LinkedIn-fiókja meg van-e osztva más felhasználókkal. |
| **Elsődleges kapcsolattartási LinkedIn-fiók célja**<br>mshr_primarycontactlinkedinpurpose<br>*Sztring* | Olvasás/írás<br>Választható | A személy elsődleges LinkedIn-fiókjának célja. Beállítás az mshr_logisticslocationroleentity entitásban. |
| **Elsődleges kapcsolattartási Twitter-fiók**<br>mshr_primarycontacttwitter<br>*Sztring* | Olvasás/írás<br>Választható | A személy elsődleges Twitter-fiókja. Azonosító: @felhasználónév. |
| **Elsődleges kapcsolattartási Twitter-fiók leírása**<br>mshr_primarycontacttwitterdescription<br>*Sztring* | Olvasás/írás<br>Választható | A személy elsődleges Twitter-fiókjának leírása. |
| **Az elsődleges kapcsolattartási Twitter-fiók privát**<br>mshr_primarycontacttwitterisprivate<br>*mshr_noyes beállításkészlet* | Olvasás/írás<br>Választható | Meghatározza, hogy a személy elsődleges Twitter-fiókja meg van-e osztva más felhasználókkal. |
| **Elsődleges kapcsolattartási Twitter-fiók célja**<br>mshr_primarycontacttwitterpurpose<br>*Sztring* | Olvasás/írás<br>Választható | A személy elsődleges Twitter-fiókjának célja. Beállítás az mshr_logisticslocationroleentity entitásban. |
| **A fél típusa**<br>mshr_partytype<br>*Sztring* | Olvasás/írás<br>Választható | A személy fél típusa. Jelöltek esetében mindig **Személy**. |
| **Névsorrend megjelenítése meghatározott sorrendben**<br>mshr_namesequencedisplayas<br>*Sztring* | Olvasás/írás<br>Választható | Az a sorrend, amelyben a személy nevének tulajdonságai összefűzve adják ki a Név (mshr_name) tulajdonságértéket. |
| **Utónév**<br>mshr_firstname<br>*Sztring* | Olvasás/írás<br>Szükséges | A személy utóneve. |
| **Második utónév**<br>mshr_middlename<br>*Sztring* | Olvasás/írás<br>Választható | A személy második utóneve. |
| **Vezetéknév előtagja**<br>mshr_lastnameprefix<br>*Sztring* | Olvasás/írás<br>Választható | A személy vezetéknevének előtagja. |
| **Vezetéknév**<br>mshr_lastname<br>*Sztring* | Olvasás/írás<br>Választható | A személy vezetékneve. |
| **Elektronikus helyazonosító**<br>mshr_electroniclocationid<br>*Sztring* | Olvasás/írás<br>Választható | A személy elektronikus helyazonosítója. |
| **Cím időzónája**<br>mshr_addresstimezone<br>*Int* | Olvasás/írás<br>Választható | A személy elsődleges címének időzónája. |

## <a name="see-also"></a>Lásd még

[Pályázó követésrendszer integrációs API bevezetése](hr-admin-integration-ats-api-introduction.md)<br>
[Példa lekérdezésre a Felvenni kívánt jelölt esetében](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
