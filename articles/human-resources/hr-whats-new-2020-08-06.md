---
title: Új vagy módosult elemek a Dynamics 365 Human Resources szolgáltatásban (2020. augusztus 06.)
description: Ez a témakör olyan funkciókat ismertet, amelyek vagy újak, vagy módosulnak a Microsoftban Dynamics 365 Human Resources 2020. augusztus 6-án.
author: andreabichsel
ms.date: 08/06/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2020-08-06
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 07aeecaeb6605ab48c0ae9c41c95939fbc706a02
ms.sourcegitcommit: 28a726b3b0726ecac7620b5736f5457bc75a5f84
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/29/2022
ms.locfileid: "9070112"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-august-06-2020"></a>Új vagy módosult elemek a Dynamics 365 Human Resources szolgáltatásban (2020. augusztus 06.)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



Ez a cikk a Dynamics 365 Human Resources szolgáltatásban található új vagy módosított funkciókat írja le. A változtatások a 8.1.3444-es buildszámra vonatkoznak. A néhány fejlécben látható, zárójelben lévő számok az LCS támogatási számaira vonatkoznak referenciaképpen.

## <a name="platform-update-1001236-is-now-available"></a>A 10.0.12(36) platformfrissítés elérhető

A további tudnivalókat [lásd a Pénzügyi és üzemeltetési alkalmazások 10.0.12-es verziójának Platformfrissítései (2020. augusztus)](../fin-ops-core/dev-itpro/get-started/whats-new-platform-update-10-0-12.md).

## <a name="data-management-framework-dmf-entities-for-benefits-management"></a>Az adatkezelési keretrendszer (DMF) entitásai a juttatások kezeléséhez
 
A juttatások kezelése entitások kiadnak. A DMF entitások lehetővé teszik az adatok importálását és exportálását a juttatáskezelés egyszerű konfigurálásához. A juttatáskezelési sablon az adatok áthelyezésére elérhető lesz. A sablon egymást követően exportálja és importálja az adatokat az adatfüggőségek tiszteletben tartásához. További tájékoztatás:

- [A DMF entitás támogatása](/dynamics365-release-plan/2020wave1/dynamics365-human-resources/dmf-entity-support) a Dynamics 365 2020-as kiadási hullámának 1. csomagjában
- [Adatkezelés – áttekintés](../fin-ops-core/dev-itpro/data-entities/data-entities-data-packages.md)


## <a name="claire-creates-a-workflow-for-buying-and-selling-leave-requests-446557"></a>Claire munkafolyamatot hoz létre a szabadságkérelmek adás-vételére (446557)

További tájékoztatás:

- [A kérelmek cseréjének engedélyezése az alkalmazottak számára](/dynamics365-release-plan/2020wave1/dynamics365-human-resources/allow-employees-buy-sell-leave) a Dynamics 365 2020-as kiadási hullámának 2. csomagjában
- [Szabadság vásárlásával és eladásával kapcsolatos irányelv kezelése](./hr-leave-and-absence-manage-buy-and-sell-leave-policies.md)
- [Szabadság vásárlása és eladása](./hr-employee-self-service-buy-sell-leave.md)


## <a name="worker-postal-addresses-v2-entity-has-access-across-legal-entities-with-restricted-access-459126"></a>A Dolgozói postai címek V2 entitás hozzáfér a korlátozott hozzáférésű jogi személyekhez (459126).

Ezzel a módosítással a **Dolgozói postai címek V2** entitás a felhasználónak a jogi személyhez adott hozzáférés alapján használ korlátozásokat.

## <a name="workflow-email-hyperlink-fails-to-open-relevant-reviews-437398"></a>A munkafolyamat e-mailjének hivatkozása nem nyitja meg a releváns véleményeket (437398)

Amikor helyőrzőt használ egy teljesítménykimutatás véleményezési munkafolyamatban való megnyitásához, az e-mailben létrehozott hivatkozás már megnyitja a kiválasztott rekordot.

## <a name="new-entities-for-buying-and-selling-leave-473180"></a>Új entitások a szabadság adás-vételére (473180)

Az adatkezelési keretrendszer entitásai már használhatók szabadság megvásárlására és eladására. További információ: [Adatkezelés – áttekintés](../fin-ops-core/dev-itpro/data-entities/data-entities-data-packages.md).

## <a name="when-viewing-record-information-and-using-advanced-filters-a-user-could-gain-access-to-other-employees-records-472490"></a>A rekordok adatainak megtekintésekor és a speciális szűrők használatakor a felhasználó hozzáférhetett más alkalmazottak rekordjaihoz (472490)

A módosítás után az Alkalmazotti önkiszolgáló rendszer felhasználói csak akkor férhetnek hozzá a saját rekordjaikhoz, amikor az Alkalmazotti önkiszolgáló rendszert használják. A rekordok adatainak szűrési beállítások módosítása során történő megtekintése már nem teszi elérhetővé további adatokat.

## <a name="personnel-management-analytics-include-exited-worker-records-382893"></a>A személyzetkezelési analitikának részét képezik a kilépett dolgozók rekordjai (382893).

Ebben a kiadásban a személyzetkezelési analitika már csak az aktív dolgozókat tartalmazza. 
 
## <a name="unable-to-process-a-merit-increase-for-an-employee-473125"></a>Nem lehet feldolgozni az alkalmazottak egyes jutalmazásait (473125)

A módosítás után a fizetésemelések megadhatók, amikor módosítja az új fizetésemelés érvénybe lépésének dátumát.

## <a name="review-workflow-can-be-started-more-than-once-467541"></a>A munkafolyamatok áttekintése többször is elindítható (467541)

A módosítás után csak egyszer indítható el a teljesítmény-áttekintési munkafolyamat. A vezető állapota már nem jeleníti meg a felülvizsgálat kezdetére szolgáló beállítást.

## <a name="leave-request-work-flow-ends-in-error-when-canceling-an-approved-leave-request-472063"></a>A kérelem munkafolyamatának befejezésekor hiba történik, a jóváhagyott szabadságkérelem visszavonásakor (472063)

Ebben a kiadásban egy jóváhagyott szabadságkérelem visszavonásakor a kérelem állapota nem marad jóváhagyott, és a munkafolyamat folytatódni fog.

## <a name="system-suggests-exited-workers-when-creating-a-new-review-form-the-template-460624"></a>A rendszer kilépett dolgozókat javasol, ha sablonból hoz létre új véleményezési űrlapot (460624)

A módosítás után a kilépett dolgozók nem lesznek elérhetők az új értékelések sablonból történő létrehozásakor. Nem hozhat létre véleményt olyan alkalmazottakhoz, akik kívül esnek a foglalkoztatás dátumán.

## <a name="position-hierarchy-circular-reference-detection-415879"></a>Beosztáshierarchia körkörös hivatkozásainak észlelése (415879)

A módosítás után a beosztáshierarchia körkörös hivatkozásainak észlelése egyetlen időpontra korlátozódik. A különböző dátumok körkörös hivatkozását úgy futtathatja, hogy ellenőrzi, hogy a jelentési struktúra nem tartalmaz körkörös hivatkozásokat.

## <a name="buy-and-sell-leave"></a>Szabadság vásárlása és eladása 

Néhány szervezet olyan juttatást biztosít, amely lehetővé teszi az alkalmazottak számára, hogy megvásárolják vagy eladják a szabadságukat. Ezt a folyamatot gyakran manuálisan kell kezelni. Ez a funkció automatizálja a HR osztályhoz tartozó kezelési házirendek és kérelmek kezelését. Racionalizálja a szabadság-kezelési folyamatot, és segít kiküszöbölni a hibákat. További tájékoztatás:

- [A kérelmek cseréjének engedélyezése az alkalmazottak számára](/dynamics365-release-plan/2020wave1/dynamics365-human-resources/allow-employees-buy-sell-leave) a Dynamics 365 2020-as kiadási hullámának 2. csomagjában
- [Szabadság vásárlásával és eladásával kapcsolatos irányelv kezelése](./hr-leave-and-absence-manage-buy-and-sell-leave-policies.md)
- [Szabadság vásárlása és eladása](./hr-employee-self-service-buy-sell-leave.md)

## <a name="leave-accrual-for-a-single-company-or-single-plan"></a>Szabadság elhatárolása egyetlen vállalat vagy egy terv esetében

A vevők az elhatárolást egyetlen vállalatra vagy egyetlen szabadságtervhez is feldolgozhatják. Ez a képesség tisztává teszi az elhatárolási folyamatot a különböző szabadságévekkel rendelkező vagy elhatárolási házirendekkel rendelkező vevők esetében. A további tudnivalókat lásd: [Szabadság elhatárolása vállalatonként vagy szabadság tervenként](hr-leave-and-absence-accrue.md).

## <a name="add-attachments-to-time-off-requests"></a>Mellékletek hozzáadása szabadságkérelmekhez

A jóváhagyott szabadságkérelmekhez tartozó mellékletek hozzáadásának lehetősége kritikus az aktuális COVID-19-környezetben. Az alkalmazottak ezután hozzáadhatják ezeket a mellékleteket. Ők is nagyobb betekintést kapnak a szabadságkérelmek frissítései tekintetében. A további tudnivalókat lásd: [Melléklet hozzáadása meglévő kérelemhez](hr-employee-self-service-request-time-off.md#add-an-attachment-to-an-existing-request).

## <a name="add-reason-code-to-accrual-suspensions"></a>Okkódhozzáadása az elhatárolás-felfüggesztésekhez 

Okkódok kerültek hozzáadásra az elhatárolás-felfüggesztéshez.

## <a name="carry-forward-rules"></a>Átvitel szabályai 

Megadhatja, hogy az átviteli szabadságtípust az átviteli egyenlegekhez, ahová az átviteli korrekciók ár lesznek helyezve. Ha például egy alkalmazott 10 napot visz át, akkor a 10 napnál más szabadság-típust is kiválaszthat. További tájékoztatás: [Szabadság és távolléti típusok konfigurálása](hr-leave-and-absence-types.md).

## <a name="suspend-leave-accrual-for-specified-leave-types"></a>Felfüggeszti a távollét elhatárolását a megadott szabadság-típusokhoz

Olyan szabályt hozhat létre, amely felfüggeszti a távolléti elhatárolásokat a fizetés nélküli szabadságokhoz megadott szabadságkérelmekhez. A fizetetlen szabadság lehet egy típus, de ez nem kötelező. Bármilyen szabadságot egy másik szabadság típus alapján fel lehet függeszteni.

## <a name="in-preview"></a>Előnézetben

### <a name="mandatory-fields"></a>Kötelező mezők

Kötelezővé teheti a mezőket a Human Resources személyre szabási funkcióival. Ehhez a funkcióhoz **Mentett nézetek** szükségesek. További információ a mentett nézetekről:

- [Mentett nézetek – nyilvános megjelenés](/dynamics365-release-plan/2020wave2/finance-operations/finance-operations-crossapp-capabilities/saved-views--general-availability) a Dynamics 365 2020-as kiadási hullámának 2. csomagjában
- [A mentett nézeteket teljes mértékben kihasználó képernyők létrehozása](../fin-ops-core/dev-itpro/user-interface/understanding-saved-views.md)

### <a name="human-resources-application-in-teams"></a>Human Resources alkalmazás a Teamsben

Az alkalmazottak megtekinthetik és kérhetik a munkából való távollétet a Microsoft Teams alkalmazásban. Ezek egy robottal lépnek interakcióba a szabadságkérelmek létrehozásához. További tájékoztatás:

- [Alkalmazott szabadsága és távolléte a Microsoft Teams rendszerben](/dynamics365-release-plan/2020wave1/dynamics365-human-resources/employee-leave-absence-experience-teams) a Dynamics 365 2020-as kiadási hullámának 1. csomagjában
- [Human Resources alkalmazás a Teamsben](./hr-admin-teams-leave-app.md)

### <a name="dmf-entity-available-for-accrual-suspensions"></a>A DMF entitás elérhető az elhatárolás-felfüggesztésekhez

A DMF entitás immár elérhető az elhatárolás-felfüggesztésekhez.

## <a name="coming-soon"></a>Hamarosan

## <a name="checklist-entities-included-in-dataverse"></a>Ellenőrzőlista-entitások szerepelnek a következőben: Dataverse

Az Előkészítés, Felszámolás, Áthelyezések és Üzleti folyamatok hamarosan elérhetők lesznek a Dataverse alkalmazásban.

## <a name="known-issues"></a>Ismert problémák

Előfordulhat, hogy a **Funkciókezelés** munkaterületen olyan általánosan elérhető funkciók jelennek meg, amelyek előnézeti funkcióként le vannak tiltva. Az alábbiakban a helytelen állapottal megjelenő általánosan elérhető szolgáltatások listája látható. 

1.  Juttatáskezelés
2.  Esetkezelés
3.  Adatbázis-naplózás (auditálás)
4.  Szabadságelhatárolás egyetlen vállalatnál vagy egyetlen tervnél
5.  Szabadság- és távollét-elhatárolás felfüggesztése
6.  Egyenlegkorrekció okkódja és megjegyzése
7.  Szabadság vásárlása és eladása
8.  A szabadságok és távollétek naptára
9.  Szabadságáthozat szabályai
10. Szabadságelhatárolás auditálása
11. Szabadságelhatárolás törlése
12. Szabadságelhatárolás kerekítése
13. Több szabadságtípus konfigurálása egyetlen szabadságtervhez
14. Szabadidő-fejlesztések frissítése
15. Alkalmazott teljes munkaidejének megfelelő érték használata az elhatároláshoz
16. Vállalatközi kompenzációs nézet
17. Teljesítményértékelések nyomtatása
18. Szabadságelhatárolás helyesbítése ünnepekkel

## <a name="see-also"></a>Lásd még

[Új vagy módosult elemek a Human Resources szolgáltatásban](hr-admin-whats-new.md)</br>
[A Dynamics 365 Human Resources 2019 második kiadási hullámának áttekintése](/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[Rendelés frissítése](hr-admin-setup-update-process.md)</br>
[Szolgáltatások kezelése](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
