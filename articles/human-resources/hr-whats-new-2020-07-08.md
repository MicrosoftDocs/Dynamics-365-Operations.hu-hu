---
title: A Dynamics 365 Human Resources új vagy módosult elemei (2020. július 08.)
description: Ez a témakör a Microsoft Dynamics 365 Human Resources új vagy módosított szolgáltatásait írja le.
author: Darinkramer
manager: AnnBe
ms.date: 7/08/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 8fe7bc33407bd5781d565f854c0f096766da5fc9
ms.sourcegitcommit: bd9ff0d28718d535356ffbe1cffaaf60310dd430
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/13/2020
ms.locfileid: "3555388"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-july-8-2020"></a>A Dynamics 365 Human Resources új vagy módosult elemei (2020. július 8.)

Ez a témakör a Dynamics 365 Human Resources új vagy módosított szolgáltatásait írja le. A változtatások a 8.1.3382-es buildszámra vonatkoznak. A néhány fejlécben látható, zárójelben lévő számok az LCS támogatási számaira vonatkoznak referenciaképpen.

## <a name="database-logging"></a>Adatbázis naplózása

Az adatbázis-naplózás segítségével meghatározhatja, hogy mely táblát és mezőket kell figyelni. Azt is lehetővé teszi, hogy meghatározza a változáskövetést igénylő eseményeket. Az adatbázis-naplózási funkciók segítségével ezeknek a változásoknak a történetét megjelenítheti. További tájékoztatás: [Adatbázis-naplózás konfigurálása és kezelése](hr-admin-database-logging.md).

## <a name="configure-the-name-of-employee-self-service"></a>Alkalmazotti önkiszolgáló rendszer nevének konfigurálása

Az **Emberi erőforrások paraméterei** részben most már módosítható az **Alkalmazott önkiszolgáló rendszer** munkaterületének neve az **Önkiszolgáló rendszer** értékre. További tájékoztatás: [Alkalmazotti önkiszolgáló munkaterület nevének módosítása](hr-employee-self-service-workspace-name.md)

## <a name="benefits-management-open-enrollment-access-outside-of-period"></a>Juttatáskezelés – nyitott beléptetési hozzáférés az időszakon kívül

Ez a kiadás javítja azt a hibát, amikor az alkalmazottak hozzáférhetnek a nyitott juttatási regisztrációhoz beadási időszakon kívül, illetve élettartam-esemény nélkül. Ennek eredményeképpen, ha a bemutató nyitott regiszrtációra van szükség az Alkalmazotti önkiszolgáló rendszerbe, a nyitott regisztrációs dátumokat a mai (vagy korábbi) értékre kell állítani, hogy elérhető legyen. Ezt a beállítást a **Juttatáskezelés > Szabályok és a beállítási időszakok** területen lehet módosítani.

## <a name="email-employee-enrollment-confirmation"></a>E-mail alkalmazotti regisztrációs visszaigazolás

Ezután e-maileket küldhet az alkalmazottaknak, miután elvégezték a juttatások kiválasztását. Küldhet alapértelmezett üzenetet, vagy használhatja a szervezet e-mail-sablonját. Ezek a beállítások a **Emberi erőforrás paraméterei > Juttatáskezelés** területen találhatók.

## <a name="canceled-leave-still-appears-in-upcoming-time-off-on-people-workspace-441358"></a>A visszavont szabadság még mindig megjelenik a közelgő távollét részben a Személyek munkaterületen (441358)

A visszavont szabadság már nem jelenik meg a szabadságkártyák közelgő távollét részében a **Személyek** munkaterületen.

## <a name="unable-to-use-the-department-entity-property-in-the-positionv2-entity-456486"></a>A részlet entitástulajdonság nem használható a Pozíció V2 entitásban (456486)

Most hozzáadhat egy részleget, ismétlődő kapcsolat létrehozása nélkül.

## <a name="payrollworkerenrolledbenefitdetailentity-should-only-use-calculated-field-for-retirement-plans-459779"></a>A PayrollWorkerEnrolledBenefitDetailEntity csak a nyugdíjazási tervekhez használandó számított használhatná (459779)

A **PayrollWorkerEnrolledBenefitDetailEntity** entitás exportálásakor az exportálás határozza meg, hogy kell-e egy számított mezőt használni egy díjtáblázat alapján, vagy a **ContributionAmountCur** mezőt kell használni a háttér táblán. Az adatentitás által használt logika a díjtáblázatot használja olyan helyzetekben, amikor az alkalmazás általában nem ezt használja. Ez a logika okozza, hogy az entitásexportálások nulla értéket adnak vissza ehhez az oszlophoz, mert nincs számítási díjtábla, és a termék nem teszi lehetővé a vevő számára, hogy megadjon egyet.
 
## <a name="confusing-translations-in-czech-language-in-personnel-management-and-employee-self-service-400276"></a>Zavaros fordítások cseh nyelven a személyzeti menedzsment és az Alkalmazotti önkiszolgáló rendszerben (400276)

Ez a kiadás korrigálja a **vállalati címtár**, a **következő regisztrált tanfolyam**, a **feladat** és **Beosztás** fordítását.
 
## <a name="the-workcalendaremployment-table-doesnt-have-the-created-and-modified-system-fields-enabled-460171"></a>A WorkCalendarEmployment táblánál engedélyezve a létrehozott és a módosított rendszermezők (460171)

A létrehozott és a módosított rendszermezők most már engedélyezve vannak a **WorkCalendarEmployment** táblában az Emberi erőforrások modulban.
 
## <a name="null-reference-exception-for-hire-and-add-details-for-future-employee-455475"></a>Nullértékű hivatkozás kivétele a Jövőbeli alkalmazott felvételéhez és hozzáadásához (455475)

Ez a kiadás kijavít egy hibát (nullértékű hivatkozás) a korszerű alkalmazotti bejegyzésben, amikor egy alkalmazottat a **Felvétel és adatok hozzáadása** beállítással alkalmaz.

## <a name="changes-made-in-the-common-data-service-worker-entity-dont-reflect-in-human-resources-455652"></a>A Common Data Service dolgozó entitásában végrehajtott változtatások nem tükröződnek a humán erőforrásokban (455652)

A Common Data Service **dolgozó** entitás következő mezőiben elvégzett módosítások most már megjelennek az Emberi erőforrások modulban:

- **Otthonról dolgozik**
- **Szolgálati idő dátuma**
- **Évforduló dátuma**
- **Eredeti felvételi dátum**

## <a name="correct-compensation-level-doesnt-default-based-on-the-job-assigned-to-the-position-394136"></a>A megfelelő kompenzációs szint nem az alapértelmezett a beosztáshoz rendelt feladat alapján (394136)

Ezzel a módosítással a helyes kompenzációs szint lesz az alapértelmezett a **Beosztás adatai** elemhez tartozó **Érvényességi dátum** és a **Kompenzációs konstrukció hozzárendelése** elem **Kezdő dátuma** alapján.

## <a name="in-preview"></a>Előnézetben

## <a name="mandatory-fields"></a>Kötelező mezők 

Most már kötelezővé teheti a mezőket a Human Resources személyre szabási funkcióival. Ehhez a funkcióhoz **Mentett nézetek** szükségesek.

## <a name="human-resources-application-in-teams"></a>Human Resources alkalmazás a Teamsben

Az alkalmazottak megtekinthetik és kérhetik a munkából való távollétet a Microsoft Teams alkalmazásban. Ezek egy robottal lépnek interakcióba a szabadságkérelmek létrehozásához. További tájékoztatás: [Human Resources alkalmazás a Teamsben](https://go.microsoft.com/fwlink/?linkid=2127841). 

## <a name="data-management-framework-dmf-entities-for-benefits-management"></a>Az adatkezelési keretrendszer (DMF) entitásai a juttatások kezeléséhez
 
A juttatások kezelése entitások kiadnak. A DMF entitások lehetővé teszik az adatok importálását és exportálását a juttatáskezelés egyszerű konfigurálásához. A juttatáskezelési sablon az adatok áthelyezésére elérhető lesz. A sablon egymást követően exportálja és importálja az adatokat az adatfüggőségek tiszteletben tartásához.

## <a name="buy-and-sell-leave"></a>Szabadság vásárlása és eladása 

Néhány szervezet olyan juttatást biztosít, amely lehetővé teszi az alkalmazottak számára, hogy megvásárolják vagy eladják a szabadságukat. Ezt a folyamatot gyakran manuálisan kell kezelni. Ez a funkció automatizálja a HR osztályhoz tartozó kezelési házirendek és kérelmek kezelését. Racionalizálja a szabadság-kezelési folyamatot, és segít kiküszöbölni a hibákat. További tájékoztatás:

- [Szabadság vásárlásával és eladásával kapcsolatos irányelv kezelése](hr-leave-and-absence-manage-buy-and-sell-leave-policies.md)
- [Szabadság vásárlása és eladása](hr-employee-self-service-buy-sell-leave.md)

## <a name="leave-accrual-for-a-single-company-or-single-plan"></a>Szabadság elhatárolása egyetlen vállalat vagy egy terv esetében

A vevők az elhatárolást egyetlen vállalatra vagy egyetlen szabadságtervhez is feldolgozhatják. Ez a képesség tisztává teszi az elhatárolási folyamatot a különböző szabadságévekkel rendelkező vagy elhatárolási házirendekkel rendelkező vevők esetében. A további tudnivalókat lásd: [Szabadság elhatárolása vállalatonként vagy szabadság tervenként](hr-leave-and-absence-accrue.md#accrue-leave-per-company-or-per-leave-plan).

## <a name="add-attachments-to-time-off-requests"></a>Mellékletek hozzáadása szabadságkérelmekhez

A jóváhagyott szabadságkérelmekhez tartozó mellékletek hozzáadásának lehetősége kritikus az aktuális COVID-19-környezetben. Az alkalmazottak ezután hozzáadhatják ezeket a mellékleteket. Ők is nagyobb betekintést kapnak a szabadságkérelmek frissítései tekintetében. A további tudnivalókat lásd: [Melléklet hozzáadása meglévő kérelemhez](hr-employee-self-service-request-time-off.md#add-an-attachment-to-an-existing-request).

## <a name="add-reason-code-to-accrual-suspensions"></a>Okkódhozzáadása az elhatárolás-felfüggesztésekhez 

Okkódok kerültek hozzáadásra az elhatárolás-felfüggesztéshez.

## <a name="carry-forward-rules"></a>Átvitel szabályai 

Megadhatja, hogy az átviteli szabadságtípust az átviteli egyenlegekhez, ahová az átviteli korrekciók ár lesznek helyezve. Ha például egy alkalmazott 10 napot visz át, akkor a 10 napnál más szabadság-típust is kiválaszthat. További tájékoztatás: [Szabadság és távolléti típusok konfigurálása](hr-leave-and-absence-types.md).

## <a name="suspend-leave-accrual-for-specified-leave-types"></a>Felfüggeszti a távollét elhatárolását a megadott szabadság-típusokhoz

Olyan szabályt hozhat létre, amely felfüggeszti a távolléti elhatárolásokat a fizetés nélküli szabadságokhoz megadott szabadságkérelmekhez. A fizetetlen szabadság lehet egy típus, de ez nem kötelező. Bármilyen szabadságot egy másik szabadság típus alapján fel lehet függeszteni.

## <a name="dmf-entity-available-for-accrual-suspensions"></a>A DMF entitás elérhető az elhatárolás-felfüggesztésekhez 

A DMF entitás immár elérhető az elhatárolás-felfüggesztésekhez.

## <a name="coming-soon"></a>Hamarosan

## <a name="checklist-entities-included-in-common-data-service"></a>Ellenőrzőlista-entitások szerepelnek a következőben: Common Data Service

Az Előkészítés, Felszámolás, Áthelyezések és Üzleti folyamatok hamarosan elérhetők lesznek a Common Data Service alkalmazásban.

## <a name="see-also"></a>Lásd még

[Új vagy módosult elemek a Human Resources szolgáltatásban](hr-admin-whats-new.md)</br>
[A Dynamics 365 Human Resources 2019 második kiadási hullámának áttekintése](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[Rendelés frissítése](hr-admin-setup-update-process.md)</br>
[Szolgáltatások kezelése](hr-admin-manage-features.md)
