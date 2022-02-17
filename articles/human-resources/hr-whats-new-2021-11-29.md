---
title: Mi új vagy megváltozott Dynamics 365 Human Resources 2021. november 19
description: Ez a témakör az önálló Microsoft új vagy módosított szolgáltatásait írja le Dynamics 365 Human Resources 2021. november 19-re.
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
ms.openlocfilehash: 618d90f95637002f444b334e16d3fef466dda65e
ms.sourcegitcommit: 7893ffb081c36838f110fadf29a183f9bdb72dd3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/02/2022
ms.locfileid: "8087474"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-november-19-2021"></a>Mi új vagy megváltozott Dynamics 365 Human Resources 2021. november 19

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Ez a téma a Microsoft Dynamics 365 Human Resources új, megváltozott vagy hamarosan megjelenő funkcióit ismerteti.

A frissítési folyamattal és ütemezéssel kapcsolatos további tudnivalókért lásd: [Frissítési folyamat](hr-admin-setup-update-process.md).

Az új funkciókkal és várható általános elérhetőségükkel kapcsolatos további információkért lásd: [Dynamics 365 Human Resources 2021-es kiadási hullám 2](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>Ebben a verzióban

Ez a kiadás a következő hibajavításokat tartalmazza. A változtatások a 8.1.4591-es buildszámra vonatkoznak.

### <a name="bug-fixes"></a>Hibajavítások

Ez a kiadás az alábbi hibajavításokat tartalmazza.

> [!NOTE]
> Célunk, hogy a lehető leghamarabb eljuttassuk Önhöz ezeket az információkat. Lehet, hogy frissítjük ezt a témát, hogy tartalmazza azokat a hibajavításokat, amelyek a téma eredeti közzététele után kerültek be a buildbe.

| Kiadás száma | Probléma | Leírás |
|---|---|---|
| 626178 | Hiányzik a navigáció a dolgozó lapkából **Menedzser önkiszolgáló** | Ez a probléma most már javítva van. A navigáció elérhető a jelentés részleteinek megtekintéséhez **Menedzser önkiszolgáló**. |
| 632573 | Nincs érvényesítési hiba az a **Tanfolyam** | Ez a probléma most már javítva van. Tanfolyam létrehozásakor a **Minimális résztvevők száma** 0-nál nagyobbra még akkor is engedélyezték a mentést, ha a **A résztvevők maximális száma** az 0. |
| 615955 | Hiba "Mező **Célja** ki kell tölteni' új toborzási kérelem hely létrehozásakor. | Amikor létrehoz egy címet egy új toborzási kérelem helyéhez, a következő hibaüzenet jelenik meg: "A "Cél" mezőt ki kell tölteni." Azonban a **Célja** mező nem érhető el az oldalon. |
| 620797 | Üres **Nem** mező hiba félrevezető | Ha nem ad meg nemet egy személyes kapcsolathoz, a jelentésben megjelenik a „Szöveg beviteléhez kattintson vagy koppintson ide” felirat – Ez félrevezető, mivel semmit nem lehet beírni a mezőbe. |
| 620800 | Az előnyökről szóló nyilatkozat linkje el van rejtve | A haszonnyilatkozat alapértelmezés szerint nem látható itt **Alkalmazotti önkiszolgáló**.  A jobb oldalához egy hivatkozás került hozzáadásra **Alkalmazotti önkiszolgáló** alatt **Linkek** szakasz |
| 629778 | Teljesítményhiba a CDS-integrációval. | Az engedélyezéssel kapcsolatos kérés teljesítményproblémát okozott. |

## <a name="in-preview"></a>Előnézetben

Az alábbi új funkciók előzetes verzióban érhetők el. A funkciók be- és kikapcsolásával kapcsolatos további információkért lásd: [Funkciók kezelése](hr-admin-manage-features.md).

| Funkció | Kiadási terv | Dokumentáció |
|---|---|---|
| Juttatáskezelési munkaterület | [Juttatáskezelési munkaterület (előzetes verzió)](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/benefits-management-workspace) | [Juttatáskezelési munkaterület](hr-benefits-management-workspace.md) |


## <a name="coming-soon"></a>Hamarosan
A tervezett szolgáltatások teljes listáját és ütemezett kiadásaikat lásd: [Dynamics 365 és iparági felhők: 2021-es kiadási hullám, 2](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
