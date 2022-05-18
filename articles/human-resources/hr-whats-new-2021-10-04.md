---
title: Új vagy módosult elemek a Dynamics 365 Human Resources szolgáltatásban (2021. október 5.)
description: Ez a témakör a Microsoft Dynamics 365 Human Resources új vagy módosított szolgáltatásait írja le a 2021. október 5-i kiadásban.
author: marcelbf
ms.date: 10/05/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-10-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 3cf83421d5385e3c95dfda6db35edfb8eb4b9336
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/04/2022
ms.locfileid: "8695760"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-october-5-2021"></a>Új vagy módosult elemek a Dynamics 365 Human Resources szolgáltatásban (2021. október 5.)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Ez a téma a Microsoft Dynamics 365 Human Resources új, megváltozott vagy hamarosan megjelenő funkcióit ismerteti.

A frissítési folyamattal és ütemezéssel kapcsolatos további tudnivalókért lásd: [Frissítési folyamat](hr-admin-setup-update-process.md).

Az új funkciókról és azok várható nyilvános megjelenési dátumáról további információkat a [Dynamics 365 Human Resources 2021-es kiadás 2. hullámának áttekintése](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/) című fejezetben talál.

## <a name="in-this-release"></a>Ebben a verzióban

Ez a kiadás az alábbi új funkciókat és hibajavításokat tartalmazza. A változtatások a 8.1.4485-es buildszámra vonatkoznak.

### <a name="new-features"></a>Új funkciók

Az alábbi funkciók általában a következő verzióval lesznek elérhetők.

| Funkció | Kiadási terv | Dokumentáció |
|---|---|---|
| Platform frissítése erre: 10.0.21 (45) | -- | [A Pénzügy és műveletek alkalmazások 10.0.21-es verziójának platformfrissítései (2021. október)](/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-21) |


### <a name="bug-fixes"></a>Hibajavítások

Ez a kiadás az alábbi hibajavításokat tartalmazza.

> [!NOTE]
> Célunk, hogy a lehető leghamarabb eljuttassuk Önhöz ezeket az információkat. Lehet, hogy frissítjük ezt a témát, hogy tartalmazza azokat a hibajavításokat, amelyek a téma eredeti közzététele után kerültek be a buildbe.

| Kiadás száma | Probléma | Leírás |
|---|---|---|
| 598896 | Az alkalmazott összege csak azután jelenik meg, hogy az alkalmazott befejezte a beléptetést | Az **Alkalmazott önkiszolgálás** oldalon nem volt látható a juttatásra vonatkozó alkalmazotti összeg. Az alkalmazotti összeg immár meg van jelenítve **Önkiszolgáló juttatásfizetés** oldalán.  |
| 613440 | Nem lehet exportálni az adatokat az **Adatkezelésből** | Amikor egy projekt adatait exportálja az **Adatkezelésben**, az exportálás váratlanul leáll. |
| 618327 | A lezárt és a jövőbeli időszakok a juttatási kimutatás **Jelentésparaméterek** lapján jelennek meg | Amikor az **Alkalmazott önkiszolgáló rendszer** **Juttatáskimutatás** elemére navigál, a **Jelentés paraméterei** lapon a **Belefoglalandó rekordok** és a **Futtatás háttérben** gyorslapokat jeleníti meg. Ezek a szakaszok el lett távolítva.|
| 618326 | Az **Alkalmazotti önkiszolgáló** rendszerben helytelen **Jelentés paraméterei** lap jelenik meg a juttatáskimutatáshoz| Amikor a felhasználó a **Juttatásikimutatási jelentés** céloldalra navigál, kiválaszthatja azokat a juttatásiterv-időszakokat, amelyek már le vannak zárva, illetve jövőbe vannak dátumozva, és ez üres lapot ad. A listában csak az aktuális juttatási terv időszakának kell megjelennie. |

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
|Hiba történt a jelentésnek a **GER jelentéscél** használatával való elküldésekor | A juttatáskimutatás beállítható úgy, hogy e-mail paramétereket használjon a **GER jelentéscélok** oldalon. A beállítás befejezése és a jelentés nyomtatása során a felhasználó formázási hibát kap, és a juttatáskimutatás nem lesz elküldve.|

## <a name="feature-management-changes"></a>Funkciókezelés módosításainak áttekintése

| Funkció | Leírás |
|---|---|
|Teljesítménynaplók bővített jelentésnézete | Ez a funkció alapértelmezés szerint ebben a kiadásban válik elérhetővé. |

## <a name="coming-soon"></a>Hamarosan

A tervbe vett funkciók és azok tervezett kiadásainak teljes listáját lásd: [A Dynamics 365 Human Resources 2021-es kiadás 2. hullámának áttekintése](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/).

| Funkció | Részletek |
|---|---|
| Platform frissítése erre: 10.0.22 (46) | A 10.0.22-es platformfrissítés bevezetése a tervek szerint a 2021. november 1-i szolgáltatási kiadással kezdődik. A további tudnivalókat [lásd a Pénzügy és műveletek alkalmazások 10.0.22-es verziójának Platformfrissítései (2021. november)](/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-22). |



## <a name="see-also"></a>Lásd még

[Újdonságok és változások a Human Resources szolgáltatásban](hr-admin-whats-new.md)</br>
[A Dynamics 365 Human Resources 2021-es kiadás 2. hullámának áttekintése](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/)</br>
[Rendelés frissítése](hr-admin-setup-update-process.md)</br>
[Szolgáltatások kezelése](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
