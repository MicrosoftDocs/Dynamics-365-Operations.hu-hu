---
title: Szabadság- és távolléti tervek halmozódása
description: Elhatárolhatja a szabadságot és távollétet a Dynamics 365 Human Resources alkalmazásban több alkalmazott vagy egy egyén esetében.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
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
ms.openlocfilehash: ba60fc2e5b17ec32aa6ad7eb104e8ae55ddee3bb
ms.sourcegitcommit: f38302b9430f2ab3efe91d0a7beff946bc610e8f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/28/2020
ms.locfileid: "3092338"
---
# <a name="accrue-leave-and-absence-plans"></a>Szabadság- és távolléti tervek halmozódása

Elhatárolhatja a szabadságot és távollétet a Dynamics 365 Human Resources alkalmazásban több alkalmazott vagy egy egyén esetében.

## <a name="accrue-leave-and-absence-for-multiple-employees"></a>Több alkalmazott szabadságának és távollétének elhatárolása

1. A **Szabadság és távollét** oldalon válassza a **Hivatkozások** lapot.

2. A **Szabadság kezelése** alatt válassza a **Szabadság- és távolléti tervek elhatárolása** lehetőséget.

3. A **Szabadság- és távolléti tervek elhatárolása** párbeszédpanelen az **Elhatárolás kezdete** részben válassza ki a **Mai dátum** vagy az **Egyéni dátum** lehetőséget, és adjon meg egy egyéni dátumot.

4. Ha a háttérben szeretné futtatni az elhatárolási folyamatot, válassza a **Futtatás a háttérben** parancsot, majd hajtsa végre a következő műveleteket:

   1. Információk megadása az elhatárolási folyamathoz.

   2. Ismétlődő feladat beállításához jelölje be az **Ismétlődés** jelölőnégyzetet, adja meg az ismétlődési adatokat, majd kattintson az **OK** gombra.

   3. A munkafigyelmeztetések beállításához jelölje ki a **Figyelmeztetések** lehetőséget, válassza ki, hogy milyen figyelmeztetéseket akar kapni ezzel kapcsolatban, majd kattintson az **OK** gombra.

   4. Válassza ki az **OK** lehetőséget. Az elhatárolási folyamat a megadott paraméterekkel fog futni.

## <a name="accrue-leave-and-absence-for-an-employee"></a>Egy alkalmazott szabadságának és távollétének elhatárolása

1. Az alkalmazott rekordján válassza a **Szabadság** elemet.

2. Válassza a **Szabadság- és távolléti tervek elhatárolása** lehetőséget.

3. A **Szabadság- és távolléti tervek elhatárolása** párbeszédpanelen az **Elhatárolás kezdete** részben válassza ki a **Mai dátum** vagy az **Egyéni dátum** lehetőséget, és adjon meg egy egyéni dátumot.

4. Ha a háttérben szeretné futtatni az elhatárolási folyamatot, válassza a **Futtatás a háttérben** parancsot, majd hajtsa végre a következő műveleteket:

   1. Információk megadása az elhatárolási folyamathoz.

   2. Ismétlődő feladat beállításához jelölje be az **Ismétlődés** jelölőnégyzetet, adja meg az ismétlődési adatokat, majd kattintson az **OK** gombra.

   3. A munkafigyelmeztetések beállításához jelölje ki a **Figyelmeztetések** lehetőséget, válassza ki, hogy milyen figyelmeztetéseket akar kapni ezzel kapcsolatban, majd kattintson az **OK** gombra.

   4. Válassza ki az **OK** lehetőséget. Az elhatárolási folyamat a megadott paraméterekkel fog futni.

## <a name="preview-features-for-leave-and-absence"></a>Előnézeti funkciók a Szabadság és távollét pontban

[!include [banner](includes/preview-feature-leave-absence.md)]

A következő előzetes verziós funkciókat engedélyezheti a Szabadság és távollét esetében:

- **Szabadság- és távolléti tervek elhatárolásának törlése**. Törli az adott tervhez és dátumtartományhoz tartozó elhatárolási rekordokat. Az elhatárolásnak aznapi vagy jövőbeli dátummal kell rendelkeznie.

- **Szabadságelhatárolás auditálása**. Minden alkalommal megjelenik, amikor valaki egy elhatárolást futtat vagy töröl egy vagy az összes alkalmazott esetében, és megjeleníti a dátumot és a művelet végrehajtóját is.

## <a name="see-also"></a>Lásd még

- [Szabadság és távollét áttekintése](hr-leave-and-absence-overview.md)
- [Szabadság- és távolléti terv létrehozása](hr-leave-and-absence-plans.md)