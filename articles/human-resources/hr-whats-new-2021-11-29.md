---
title: Újdonságok vagy megváltoztak Dynamics 365 Human Resources 2021. november 19-én
description: Ez a témakör azokat a szolgáltatásokat ismerteti, amelyek újak vagy megváltoztak a Microsoftban Dynamics 365 Human Resources 2021. november 19-én.
author: marcelbf
ms.date: 12/03/2021
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
ms.search.validFrom: 2021-12-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 3a86c1c24fbc758f4e3d0fd8b052e02078bee41e
ms.sourcegitcommit: 88f8a0369ce66b82314db9639491b695e18a7e5c
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/09/2021
ms.locfileid: "7902969"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-november-19-2021"></a>Újdonságok vagy megváltoztak Dynamics 365 Human Resources 2021. november 19-én

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Ez a téma a Microsoft Dynamics 365 Human Resources új, megváltozott vagy hamarosan megjelenő funkcióit ismerteti.

A frissítési folyamattal és ütemezéssel kapcsolatos további tudnivalókért lásd: [Frissítési folyamat](hr-admin-setup-update-process.md).

Az új funkciókkal és azok várható általános elérhetőségi dátumokkal kapcsolatos további információkért lásd a [Dynamics 365 Human Resources 2021-es 2. kiadási hullámot](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>Ebben a verzióban

Ez a kiadás a következő hibajavításokat tartalmazza. A változtatások a 8.1.4591-es buildszámra vonatkoznak.

### <a name="bug-fixes"></a>Hibajavítások

Ez a kiadás az alábbi hibajavításokat tartalmazza.

> [!NOTE]
> Célunk, hogy a lehető leghamarabb eljuttassuk Önhöz ezeket az információkat. Lehet, hogy frissítjük ezt a témát, hogy tartalmazza azokat a hibajavításokat, amelyek a téma eredeti közzététele után kerültek be a buildbe.

| Kiadás száma | Probléma | Leírás |
|---|---|---|
| 626178 | Hiányzik a navigáció a kezelői önkiszolgáló munkavégző **csempéiről** | Ez a probléma most már javítva van. A navigáció a jelentés részleteinek megtekintéséhez elérhető a **Manager önkiszolgáló szolgáltatásában**. |
| 632573 | Nincs érvényesítési hiba a tanfolyam **mentésekor** | Ez a probléma most már javítva van. A **minimális létszámú, 0-nál nagyobb számú tanfolyam** létrehozásakor akkor is menthető, ha a **résztvevők maximális száma** 0. |
| 615955 | Az **új toborzási kérelem helyének létrehozásakor a "Field Purpose** kell kitölteni" hiba. | Új toborzási kérelem helyének címekor a következő hibaüzenet jelenik meg: "A "Cél" mezőt ki kell tölteni. A Cél mező azonban **nem érhető el az** oldalon. |
| 620797 | Az üres **nemek** mezőhiba félrevezető | Ha egy nemet nem ír be személyes partnerhez, a jelentés a "Kattintson ide a szöveg beírásához" – Ez félrevezető, mivel semmit sem lehet beírni a mezőbe. |
| 620800 | Az előnyökre tett nyilatkozat linkje rejtve van | A juttatási kimutatás alapértelmezés szerint nem látható az **Alkalmazott önkiszolgáló**.  A **Hivatkozások** **szakaszban** egy hivatkozás lett hozzáadva az Alkalmazott önkiszolgáló jobb oldalához |
| 629778 | Teljesítmény probléma a CDS-integrációval. | Az engedélyezéssel kapcsolatos kérelem teljesítménybeli problémát okozott. |

## <a name="in-preview"></a>Előnézetben

Az alábbi új funkciók előzetes verzióban érhetők el. A funkciók be- és kikapcsolásával kapcsolatos további információkért lásd: [Funkciók kezelése](hr-admin-manage-features.md).

| Funkció | Kiadási terv | Dokumentáció |
|---|---|---|
| Juttatáskezelési munkaterület | [Juttatáskezelési munkaterület (előzetes verzió)](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/benefits-management-workspace) | [Juttatáskezelési munkaterület](hr-benefits-management-workspace.md) |


## <a name="coming-soon"></a>Hamarosan
A tervezett funkciók és azok ütemezett kiadásainak teljes listáját a [Dynamics 365 és az iparági felhők: 2021-es kiadási hullám 2 című témakörben tekintheti](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/) meg.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
