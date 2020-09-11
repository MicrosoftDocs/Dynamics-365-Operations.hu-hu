---
title: Új vagy módosult elemek a Dynamics 365 Human Resources (2020. április 13.) szolgáltatásban
description: Ez a cikk a Microsoft Dynamics 365 Human Resources új vagy módosított szolgáltatásait írja le a 2020. április 13-i kiadásban.
author: Darinkramer
manager: AnnBe
ms.date: 4/13/2020
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
ms.search.validFrom: 2020-04-13
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 729490e7516d8c7aef7232c9f5c227d3207dcd68
ms.sourcegitcommit: 2bcacef1e010c312f019dbf9740ce87d627848a7
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/20/2020
ms.locfileid: "3712424"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-april-13-2020"></a>Új vagy módosult elemek a Dynamics 365 Human Resources (2020. április 13.) szolgáltatásban

Ez a cikk a Dynamics 365 Human Resources szolgáltatásban található új vagy módosított funkciókat írja le. A változtatások a 8.1.3136-es buildszámra vonatkoznak. A néhány fejlécben látható, zárójelben lévő számok az LCS támogatási számaira vonatkoznak referenciaképpen.

## <a name="new-production-release-cadence"></a>Új termelési kiadás ütemezése

Az eheti kiadástól kezdődően a program a Human Resources kiadási ritmusa heti frissítésről a kétheti frissítésre módosul. A biztonságos telepítési gyakorlattal való összehangolás biztosításához és a szolgáltatásban a stabilitás és megbízhatóság magas színvonalának megőrzéséhez a szolgáltatás frissítései minden régióban két hetes ütemezésre váltanak. További tesztek és nyomon követések lettek bevezetve a sikeres telepítés megerősítéséhez a folyamat minden egyes fázisában. A kiadás ritmusával kapcsolatos további tudnivalókat lásd: [Frissítési folyamat](hr-admin-setup-update-process.md).

## <a name="rounding-precision-field-isnt-editable-after-specifying-a-rounding-type-435616"></a>A kerekítési pontosság mező nem szerkeszthető a kerekítési típus megadása után (435616)

Ezzel a módosítással a **Kerekítési pontosság** mező már elérhető a **Kerekítési típus** mező frissítése után.

## <a name="cant-edit-leave-enrollment-end-date-when-the-leave-plan-doesnt-have-accrual-periods-413628"></a>Nem lehet módosítani a szabadságterv záró dátumát, ha a szabadságterv nem rendelkezik elhatárolási időszakokkal (413628)

Most szerkesztheti a regisztráció záró dátumát anélkül, hogy az „Elhatárolási dátum mezőt ki kell tölteni” hibaüzenetet kapná.

## <a name="employment-entity-doesnt-sync-to-common-data-service-430834"></a>A foglalkoztatás entitása nem szinkronizál a Common Data Service szolgáltatásba (430834)

A módosítás javítja azt a hibát, amikor a pénzügyi dimenziók hozzáadását követően a foglalkoztatási adatok nem lettek szinkronizálva a Common Data Service szolgáltatásba. 

## <a name="remove-multi-parenting-for-work-calendar-time-interval-entity-431775"></a>Több szülő eltávolítása a Munkanaptár időintervalluma entitáshoz (431775)

Ez a módosítás eltávolítja a több szülőt eltávolítása a **Munkanaptár időintervalluma** entitáshoz.

## <a name="filter-with-cast-function-doesnt-work-on-odata-call-position-worker-assignment-entity-431699"></a>A CAST funkcióval rendelkező szűrő nem működik az Beosztáshoz rendelt dolgozó entitás OData hívásakor (431699)

A frissítés tartalmaz egy módosítást, amely lehetővé teszi, hogy a OData CAST funkciójával szűrni lehessen a **Beosztáshoz rendelt dolgozó** entitásra.

## <a name="in-preview"></a>Előnézetben

## <a name="leave-suspension"></a>Szabadság felfüggesztése

Egy alkalmazottra vonatkozóan felfüggesztheti a szabadságokat és a távollétet. A szabadság felfüggesztése kiválasztott távolléti típusoknál leállítja az elhatárolást. Ha a felfüggesztés a könyvelés feldolgozását követően következik be, akkor a szabadság felfüggesztése az alkalmazott szabadságának egyenlegéhez egy arányosan korrigált kiigazítást hoz létre. További információ: [Szabadság felfüggesztése](hr-leave-and-absence-suspend-leave.md).

## <a name="carry-forward-rules"></a>Átvitel szabályai

Megadhatja, hogy az átviteli szabadságtípust az átviteli egyenlegekhez, ahová az átviteli korrekciók ár lesznek helyezve. Ha például egy alkalmazott 10 napot visz át, akkor a 10 napnál más szabadság-típust is kiválaszthat. További tájékoztatás: [Szabadság és távolléti típusok konfigurálása](hr-leave-and-absence-types.md).

## <a name="known-issues"></a>Ismert problémák

## <a name="employment-details-entity"></a>Foglalkoztatás részletei entitás

A **Foglalkoztatási részletei** entitás frissítve lett a következő mezőkkel:

- **PayFrequency**
- **Foglalkoztatási kategóriaazonosítója**
- **Foglalkoztatási típus**
- **EmploymentType azonosító**
- **Juttatás foglalkoztatási állapota**

Ezeknek a mezőknek a beállítási adatai a **Funkciókezelés** munkaterületen engedélyezve vannak a juttatások kezeléséhez. Ne töltse ki vagy frissítse ezeket a mezőket a **Foglalkoztatás részletei** entitásban, mert ez hibákat fog eredményezni az importálás során.

## <a name="sharepoint-preview-doesnt-work-in-some-environments"></a>SharePoint előnézet nem használható bizonyos környezetekben

Ha egy, a SharePoint-ban tárolt dokumentum előnézete nem működik, próbálja meg a következő eljárást:

1. Ellenőrizze, hogy az Adminisztrátor felhasználói fiók rendelkezik-e a felhasználói rekordhoz társított e-mail-címmel. Ezt az információt a **Felhasználó** oldalon lehet megtekinteni. Ha nincs beállítva e-mail-cím, akkor az e-mail-címet és a szolgáltatót hozzá kell adnia az OData Excel-bővítménnyel. Alapértelmezés szerint az e-mail-cím nem szerepel az Excel-tervben. Szerkesztenie kell az Excel-tervet, minden mezőt fel kell venni, alkalmazni kell, majd frissíteni kell. Miután befejezte ezeket a lépéseket, frissítheti az adminisztrátori fiókot.

2. Miután az Adminisztrátor fiókhoz hozzá van rendelve egy e-mail-fiók, az Adminisztrátori hitelesítő adatokkal jelentkezzen be a Human Resources szolgáltatásokba.

3. A dokumentum előnézetének indításához nyisson meg egy mellékletet SharePoint-ban.

4. Jelentkezzen be egy másik olyan felhasználói fiókkal, amely hozzáférhet a mellékletekhez, és ellenőrizze, hogy az előnézet a várt módon működik-e.

## <a name="see-also"></a>Lásd még

[Új vagy módosult elemek a Human Resources szolgáltatásban](hr-admin-whats-new.md)</br>
[A Dynamics 365 Human Resources 2019 második kiadási hullámának áttekintése](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[Rendelés frissítése](hr-admin-setup-update-process.md)</br>
[Szolgáltatások kezelése](hr-admin-manage-features.md)