---
title: Munkaidőnaptár létrehozása
description: A Dynamics 365 Human Resources alkalmazásban munkaidőnaptárt, szabadnapokat és munkaidőket definiálhat.
author: andreabichsel
ms.date: 04/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 8ea55ad7f86e0c7d5ccc6e6de0af475299b05639
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/18/2021
ms.locfileid: "6052433"
---
# <a name="create-a-working-time-calendar"></a>Munkaidőnaptár létrehozása

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

A Dynamics 365 Human Resources alkalmazásban a munkaidőnaptár jeleníti meg azokat a napokat és órákat, amikor az alkalmazottak dolgoznak a szervezetben. Amikor egy alkalmazott szabadságra vonatkozó kérelmet küld, nem kell aggódnia a szabadnapok és a leállások miatt.

A szabadságkérelmek egyszerűsítése érdekében konfigurálja a következő elemeket a szervezetnél:

- Munkaidőnaptár
- Szabadnapok és leállások
- Nem munkaidő

Az utolsó két elemet a munkaidőnaptár beállítása közben is felveheti. Külön is konfigurálhatja vagy módosíthatja ezeket.

## <a name="set-up-a-working-time-calendar"></a>Munkaidőnaptár beállítása

Állítson be legalább egy munkaidőnaptárt, amely megjeleníti a működési idejének napjait és óráit. Ha több országban és régióban van jelen, akkor lehetséges, hogy minden területhez érdemes munkaidőnaptárt beállítania.

1. A **Szervezet felügyelete** oldalon válassza a **Naptárak** elemet.

2. Válassza az **Új** lehetőséget, és adja meg a naptár nevét és leírását.

3. A **Létrehozási beállítások** területen válassza ki a szervezet munkanapjait és munkaidőit. 
   - Munkaszünet vagy leállás hozzáadásához válassza a **Hozzáadás** gombot a **Szabadnapok és leállások** elem mellett.
   - Ha olyan időt szeretne hozzáadni, amely nem munkaidő, például ebédet vagy szünetet, akkor válassza a **Hozzáadás** gombot a **NEM MUNKAIDŐ** területen, és adja meg a nevet és az időtartományt.

4. A **Napok** beállításnál válassza a **Létrehozás** lehetőséget, amivel létrehozza a napokat a naptárban. Adja meg a naptár dátumtartományát, majd válassza a **Napok létrehozása** lehetőséget.

5. Munkaütemezések hozzáadásához a **Munkaütemezés** beállításnál válassza a **Hozzáadás** gombot, majd adja meg az egyes munkaütemezések idejét.

## <a name="configure-holidays-and-closures"></a>Szabadnapok és leállások konfigurálása

A munkaidőnaptárban külön is hozzáadhatja és módosíthatja a szabadnapokat és a leállásokat.

1. A **Szervezet felügyelete** oldalon válassza a **Szabadnapok és leállások** elemet.

2. Válassza az **Új** lehetőséget, és adja meg a szabadnap vagy leállás nevét és dátumát.

## <a name="configure-non-work-time"></a>Nem munkaidő konfigurálása

A munkaidőnaptárban külön is hozzáadhatja és módosíthatja a nem munkaidőnek számító időket.

1. A **Szervezet felügyelete** oldalon válassza a **Nem munkaidő** elemet.

2. Válassza az **Új** lehetőséget, és adja meg a nem munkaidőnek számító idő nevét és időtartományát.

Ha engedélyezte a szabadsággal és a távolléttel kapcsolatos munkaszünet-korrekciók előzetes funkcióját, akkor a Human Resources a szabadnapok és a leállások dátuma alapján határozza meg, hogy hány napot kell módosítani a naptárba bejegyzett alkalmazottaknál.

## <a name="see-also"></a>Lásd még

- [Szabadság és távollét áttekintése](hr-leave-and-absence-overview.md)
- [Szabadság- és távolléttípusok konfigurálása](hr-leave-and-absence-types.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]