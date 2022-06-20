---
title: Dynamics 365 Human Resources A 2021. november 19. újdonsága vagy módosult
description: Ez a témakör olyan funkciókat ír le, amelyek vagy újak, vagy módosulnak a Különálló Microsoftban Dynamics 365 Human Resources 2021. november 19. óta.
author: marcelbf
ms.date: 12/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-12-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: d3e08432a4ce4d73cd67ad839191abe9f6e691a6
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8886073"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-november-19-2021"></a>Dynamics 365 Human Resources A 2021. november 19. újdonsága vagy módosult

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Ez a témakör a Microsoft új, módosított vagy hamarosan érkező funkcióit írja le Dynamics 365 Human Resources.

A frissítési folyamattal és ütemezéssel kapcsolatos további tudnivalókért lásd: [Frissítési folyamat](hr-admin-setup-update-process.md).

Az új funkciókról és várható [Dynamics 365 Human Resources általános elérhetőségi dátumukról a 2021-es kiadási hullámban található további tájékoztatás](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>Ebben a verzióban

Ez a kiadás a következő hibajavításokat tartalmazza. A változtatások a 8.1.4591-es buildszámra vonatkoznak.

### <a name="bug-fixes"></a>Hibajavítások

Ez a kiadás az alábbi hibajavításokat tartalmazza.

> [!NOTE]
> Célunk, hogy a lehető leghamarabb eljuttassuk Önhöz ezeket az információkat. Előfordulhat, hogy a cikk első közzététele után frissítjük ezt a cikket, hogy a hibajavítások is szerepeljenek a buildben.

| Kiadás száma | Probléma | Leírás |
|---|---|---|
| 626178 | A vezető önkiszolgáló rendszerében található dolgozói navigációs **folyamat hiányzik.** | Ez a probléma most már javítva van. Navigációs módban a vezetői önkiszolgáló rendszer **részletes adatai érhetők el**. |
| 632573 | Nincs ellenőrzési hiba a tanfolyam mentésekor **.** | Ez a probléma most már javítva van. Ha olyan tanfolyamot hoz létre, **amelynél** a résztvevők minimális száma 0-t **meghaladja**, még akkor is menthető, ha a résztvevők maximális száma 0. |
| 615955 | Hiba: Az új **toborzási** kérelem helyének létrehozásakor a "Mező célja" mezőt ki kell tölteni. | Amikor címet ad meg egy új toborzási kérelem helyének, a következő hibát okozza: a "Cél" mezőt ki kell tölteni. A Cél **mező** azonban nem érhető el a lapon. |
| 620797 | Az üres **Nemek mező** hibát jelez. | Ha egy személyes kapcsolattartó neme nincs megadva, akkor a jelentésen a "Szöveg beviteléhez kattintson vagy ide lépve" felirat jelenik meg – ez félrevezető, mivel a mezőben nem lehet megadni semmit. |
| 620800 | A juttatások kimutatásának hivatkozása rejtett. | A juttatási kimutatás alapértelmezés szerint nem megtekinthető az alkalmazotti **önkiszolgáló szolgáltatásban**.  Az Alkalmazotti önkiszolgáló **szolgáltatás** jobb oldalára felkerült egy hivatkozás a Hivatkozások **szakaszban**. |
| 629778 | Teljesítmény-probléma a CDS-integrációval. | Az engedélyezéshez kapcsolódó kérés teljesítmény problémát okozott. |

## <a name="in-preview"></a>Előnézetben

Az alábbi új funkciók előzetes verzióban érhetők el. A funkciók be- és kikapcsolásával kapcsolatos további információkért lásd: [Funkciók kezelése](hr-admin-manage-features.md).

| Funkció | Kiadási terv | Dokumentáció |
|---|---|---|
| Juttatáskezelési munkaterület | [Juttatáskezelési munkaterület (előzetes verzió)](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/benefits-management-workspace) | [Juttatáskezelési munkaterület](hr-benefits-management-workspace.md) |


## <a name="coming-soon"></a>Hamarosan
A tervezett funkciók és [ütemezett kiadások teljes listáját lásd a Dynamics 365 és az iparági felhők: 2021-es kiadási hullám 2](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
