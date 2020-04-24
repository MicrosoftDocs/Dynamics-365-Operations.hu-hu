---
title: Szabadság- és távollétparaméterek konfigurálása
description: Emberi erőforrások paramétereinek meghatározása a szabadsághoz és a távolléthez a Dynamics 365 Human Resources alkalmazásban.
author: andreabichsel
manager: AnnBe
ms.date: 04/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: eb992cbfbed33f88e125d3a8b721f8815414599a
ms.sourcegitcommit: 79f8aa2c0b166a423db9b8503da53e96e3fc43dc
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2020
ms.locfileid: "3197981"
---
# <a name="configure-leave-and-absence-parameters"></a>Szabadság- és távollétparaméterek konfigurálása

Mielőtt beállítaná a szabadság- és a távollétterveket a Dynamics 365 Human Resources alkalmazásban, célszerű ellenőrizni az összes kapcsolódó emberierőforrás-paraméter beállítását, többek között a következőket:

- A szabadságkérelmek számsorozata
- Családi okból történő és a betegszabadságról szóló amerikai törvény (FMLA) beállításai
- Alkalmazotti önkiszolgáló rendszer beállításai a szabadság- és a távollétkérelmek esetében
- Szabadság- és távollétparaméterek

## <a name="view-and-change-human-resources-parameters"></a>Emberierőforrás-paraméterek megtekintése és módosítása

1. A **Szabadság és távollét** oldalon válassza a **Hivatkozások** lapot.

2. A **Beállítás** alatt válassza az **Emberierőforrás-paraméterek** lehetőséget.

3. A **Számsorozatok** lapon ellenőrizze, a **Számsorozat kódja** beálítást a **Szabadságkérelem azonosítója** esetében, és szükség szerint módosítsa. Ez a beállítás határozza meg a szabadságkérelmekhez automatikusan hozzárendelt azonosítókhoz használt sorrendet.

4. Az **FMLA** lapon ellenőrizze az FMLA beállításait, és szükség esetén módosítsa azokat.

5. Az **Alkalmazotti önkiszolgáló rendszer** lapon jelezze, hogy a vezetők az alkalmazottak nevében beírhatják-e a szabadság- és a távolléti kérelmeket .

6. A **Szabadság és távollét** lapon ellenőrizze a beállításokat, és szükség esetén módosítsa azokat.

7. Válassza a **Mentés** lehetőséget.

## <a name="view-and-change-leave-and-absence-parameters"></a>Szabadság és távollét paramétereinek megtekintése és módosítása

1. A **Szabadság és távollét** oldalon válassza a **Hivatkozások** lapot.

2. A **Beállítás**területen válassza a **Szabadság- és távollétparaméterek** lehetőséget.

3. Az **Általános** lapon állítsa be a következő paramétereket:
 
    - A **Szabadság és távollét mértékegysége** elemet állítsa órára vagy napra. Ha a nap lehetőséget választja , akkor a **Félnapos meghatározás** engedélyezése beállítással lehetővé teheti az alkalmazottak számára, hogy a nap első vagy második felét válasszák ki távollét-kérelmeikben. 

    - Válassza a **Szolgálti hónapok az érvényeség dátumáig** kiválasztásával beállíthatja, hogy az elhatárolási mérték a szolgálati hónapok alapján befolyásolja a szabadságterveket.

    - Válassza az **Egyenleg számítása** lehetőséget, ha az egyenlegeket a mai napig vagy az elhatárolási időszakig szeretné megjeleníteni. Ha az **Egyenleg a mai napig** lehetőséget választja, akkor az egyenleg az összes elhatárolást, kiigazítást és kérelmet megjeleníti a mai napig. Ha az **Egyenleg az elhatárolási időszakig** lehetőséget választja, akkor az egyenleg az elszámolási időszak gyakorisága által meghatározott elhatárolási időszak összes elhatárolását, helyesbítését és kérését jeleníti meg. 

## <a name="configure-calendar-parameters"></a>Naptárparaméterek karbantartása

1. A **Szabadság és távollét** oldalon válassza a **Hivatkozások** lapot.

2. A **Beállítás**területen válassza a **Szabadság- és távollétparaméterek** lehetőséget.

3. A **Naptár** lapon szükség szerint módosítsa a naptár beállításait.

4. Válassza a **Mentés** lehetőséget.

## <a name="see-also"></a>Lásd még

- [Szabadság és távollét áttekintése](hr-leave-and-absence-overview.md)
