---
title: Munkaidőnaptár létrehozása
description: A Dynamics 365 Human Resources alkalmazásban munkaidőnaptárt, szabadnapokat és munkaidőket definiálhat.
author: andreabichsel
manager: tfehr
ms.date: 04/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: ccf7901ebbea655b7f795a48944c6f03f9cf210a
ms.sourcegitcommit: 18e626c49ccfdb12c1484b985e3a275e51f61320
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/04/2021
ms.locfileid: "5115102"
---
# <a name="create-a-working-time-calendar"></a>Munkaidőnaptár létrehozása

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