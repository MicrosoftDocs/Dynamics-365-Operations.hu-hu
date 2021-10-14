---
title: Új vagy módosult elemek a Dynamics 365 Human Resources szolgáltatásban (2021. szeptember 20.)
description: Ez a témakör a Microsoft Dynamics 365 Human Resources új vagy módosított szolgáltatásait írja le a 2021. szeptember 20-i kiadásban.
author: marcelbf
ms.date: 09/20/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-09-20
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 3f4fc4768f8c96678b216709f78af6d3ddfd4132
ms.sourcegitcommit: ba8ca42e43e1a5251cbbd6ddb292566164d735dd
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/25/2021
ms.locfileid: "7556933"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-september-20-2021"></a>Új vagy módosult elemek a Dynamics 365 Human Resources szolgáltatásban (2021. szeptember 20.)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Ez a téma a Microsoft Dynamics 365 Human Resources új, megváltozott vagy hamarosan megjelenő funkcióit ismerteti.

A frissítési folyamattal és ütemezéssel kapcsolatos további tudnivalókért lásd: [Frissítési folyamat](hr-admin-setup-update-process.md).

Az új funkciókról és azok várható nyilvános megjelenési dátumáról további információkat a [Dynamics 365 Human Resources 2021-es kiadás 2. hullámának áttekintése](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/) című fejezetben talál.

## <a name="in-this-release"></a>Ebben a verzióban

Ez a kiadás az alábbi új funkciókat és hibajavításokat tartalmazza. A változtatások a 8.1.4464-es buildszámra vonatkoznak.

### <a name="new-features"></a>Új funkciók

Az alábbi funkciók általában a következő verzióval lesznek elérhetők.

| Funkció | Kiadási terv | Dokumentáció |
|---|---|---|
| Egyszerűsített bérintegrációs (Bérintegrációs API-k) engedélyezése | [Egyszerűsített integráció engedélyezése a bérszolgáltatókkal](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-simplified-integration-payroll-providers) | [Bérlista-integrációs API](hr-admin-integration-payroll-api-introduction.md) |
| Az alkalmazottak kifizetésre készként való jelölésének engedélyezése | [Az alkalmazottak kifizetésre készként való jelölésének engedélyezése](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-employees-be-marked-as-ready-pay) | [Kifizetésre kész](/dynamics365/human-resources/hr-compensation-payroll) |

### <a name="bug-fixes"></a>Hibajavítások

Ez a kiadás az alábbi hibajavításokat tartalmazza.

> [!NOTE]
> Célunk, hogy a lehető leghamarabb eljuttassuk Önhöz ezeket az információkat. Lehet, hogy frissítjük ezt a témát, hogy tartalmazza azokat a hibajavításokat, amelyek a téma eredeti közzététele után kerültek be a buildbe.

| Kiadás száma | Probléma | Leírás |
|---|---|---|
| 619774 | A címleírás szerkesztése nincs szinkronizálva valós időben a Dataverse-be. | Dolgozói cím leírásának szerkesztésekor a frissített leírás nem szinkronizálható a valós időben a Dataverse-szel. A **Logisztikai hely** táblában található előfizetés frissítve lett frissítés küldésekor. |
| 614603| Hiba a **Dolgozó** lapon, ha nincs kiválasztva a **Dolgozó személyzeti műveletek** paraméter. | Új dolgozó felvételekor vagy a **Dolgozó** lapra való navigáláskor a következő hiba jelenik meg: "A **Személyzeti művelet típusa** mezőt ki kell tölteni", még akkor is, ha a **Személyzeti műveletek** ki vannak kapcsolva. |
| 615367 | A **Jóváhagyott szabadság** lapon egy figyelmeztetés jelenik meg, és ez helytelenül jelenik meg. | Ha a szabadságegység beállítása **Nap**, mielőtt engedélyezné a **Szabadságegységek konfigurálása szabadságtípusonként** parancsot, a **Jóváhagyott szabadság** lap érvénytelen figyelmeztetést és helytelen oszlopokat jelenít meg. |


## <a name="in-preview"></a>Előnézetben

Az alábbi új funkciók előzetes verzióban érhetők el. A funkciók be- és kikapcsolásával kapcsolatos további információkért lásd: [Funkciók kezelése](hr-admin-manage-features.md).

| Funkció | Kiadási terv | Dokumentáció |
|---|---|---|
| Juttatáskezelési munkaterület | [Juttatáskezelési munkaterület (előzetes verzió)](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/benefits-management-workspace) | [Juttatáskezelési munkaterület](hr-benefits-management-workspace.md) |
| A Jogosultság egyéni mezői |[Egyéni mezők támogatása a jogosultságok feldolgozásában](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/custom-field-support-benefits-management) | [Egyéni mezők használata a jogosultsági feldolgozásban](/dynamics365/human-resources/hr-benefits-setup-eligibility-rules#using-custom-fields-in-eligibility-rules) |
| Juttatási kimutatás |[Juttatási kimutatás](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/benefits-summary-statement) | [Juttatási kimutatás](hr-benefits-statement.md) |

### <a name="benefits-statement-known-issues"></a>Juttatáskimutatás – ismert problémák

| Probléma | Leírás |
|---|---|
| Az **Alkalmazotti önkiszolgáló rendszer** **Jelentés paraméterei** lapja juttatáskimutatáshoz helytelen. | Amikor az **Alkalmazott önkiszolgáló rendszer** **Juttatáskimutatás** elemére navigál, a **Jelentés paraméterei** lapon a **Belefoglalandó rekordok** és a **Futtatás háttérben** gyorslapokat jeleníti meg.  Ezeket el kell távolítani. |
| A lezárt és a jövőbeli időszakok a juttatási kimutatás **Jelentésparaméterek** lapján jelennek meg. | Amikor a felhasználó a **Juttatásikimutatási jelentés** céloldalra navigál, kiválaszthatja azokat a juttatásiterv-időszakokat, amelyek már le vannak zárva, illetve jövőbe vannak dátumozva, és ez üres lapot ad. A listában csak az aktuális juttatási terv időszakának kell megjelennie. |
|Hiba történt a jelentésnek a GER jelentéscél használatával való elküldésekor. | A juttatáskimutatás beállítható úgy, hogy e-mail paramétereket használjon a **GER jelentéscélok** oldalon. A beállítás befejezése és a jelentés nyomtatása során a felhasználó formázási hibát kap, és a juttatáskimutatás nem lesz elküldve.|


## <a name="coming-soon"></a>Hamarosan

A tervbe vett funkciók és azok tervezett kiadásainak teljes listáját lásd: [A Dynamics 365 Human Resources 2021-es kiadás 2. hullámának áttekintése](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/).

| Funkció | Részletek |
|---|---|
| Platform frissítése erre: 10.0.21 (45) | A 10.0.21-es platformfrissítés bevezetése a tervek szerint a 2021. október 4-i szolgáltatási kiadással kezdődik. További információért lásd: [Platformfrissítések a Finance and Operations alkalmazások 10.0.21-es verziójához (2021. október](/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-21)). |
|Teljesítménynaplók bővített jelentésnézete | Ez a funkció alapértelmezés szerint a következő bevezetés során válik elérhetővé. |


## <a name="see-also"></a>Lásd még

[Újdonságok és változások a Human Resources szolgáltatásban](hr-admin-whats-new.md)</br>
[A Dynamics 365 Human Resources 2021-es kiadás 2. hullámának áttekintése](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/)</br>
[Rendelés frissítése](hr-admin-setup-update-process.md)</br>
[Szolgáltatások kezelése](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
