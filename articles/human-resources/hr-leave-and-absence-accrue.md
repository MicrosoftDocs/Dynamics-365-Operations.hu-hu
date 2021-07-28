---
title: Szabadság- és távolléti tervek halmozódása
description: Elhatárolhatja a szabadságot és távollétet a Dynamics 365 Human Resources alkalmazásban több alkalmazott vagy egy egyén esetében.
author: andreabichsel
ms.date: 05/04/2020
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: f15deae8a2b457548606616dd540f71a505f727a
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/06/2021
ms.locfileid: "6357095"
---
# <a name="accrue-leave-and-absence-plans"></a>Szabadság- és távolléti tervek halmozódása

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Elhatárolhatja a szabadságot és távollétet a Dynamics 365 Human Resources alkalmazásban több alkalmazott vagy egy egyén esetében.

## <a name="accrue-leave-and-absence-for-multiple-employees"></a>Több alkalmazott szabadságának és távollétének elhatárolása

1. A **Szabadság és távollét** oldalon válassza a **Hivatkozások** lapot.

2. A **Szabadság kezelése** alatt válassza a **Szabadság- és távolléti tervek elhatárolása** lehetőséget.

3. Megjelenik a **Szabadság- és távolléti tervek elhatárolása** párbeszédpanel. Az **Elhatárolás kezdete** részben válassza a **Mai dátum** vagy az **Egyéni dátum** lehetőséget, és adjon meg egy egyéni dátumot.

4. Ha minden vállalatnál szeretné futtatni az elhatárolást, válassza az **Összes vállalat** lehetőséget. Ha egyetlen szabadsági tervhez szeretné feldolgozni az elhatárolást, válassza a **Nem** lehetőséget az **Összes konstrukció** alatt, majd válasszon egy **Szabadságkonstrukciót**. Ha az összes vállalatot választja, akkor nem választhat ki egyéni szabadságtervet.

5. Ha a háttérben szeretné futtatni az elhatárolási folyamatot, válassza a **Futtatás a háttérben** parancsot, majd hajtsa végre a következő műveleteket:

    1. Információk megadása az elhatárolási folyamathoz.
    2. Ismétlődő feladat beállításához válassza az **Ismétlődés** lehetőséget, adja meg az ismétlődés adatait, majd kattintson az **OK** gombra.
    3. A munkafigyelmeztetések beállításához jelölje ki a **Figyelmeztetések** lehetőséget, válassza ki, hogy milyen figyelmeztetéseket akar kapni ezzel kapcsolatban, majd kattintson az **OK** gombra.
    4. Válassza ki az **OK** lehetőséget. Az elhatárolási folyamat a megadott paraméterekkel fog futni. 

## <a name="accrue-leave-and-absence-for-an-employee"></a>Egy alkalmazott szabadságának és távollétének elhatárolása

1. Az alkalmazott rekordján válassza a **Szabadság** elemet.

2. Válassza a **Szabadság- és távolléti tervek elhatárolása** lehetőséget.

3. Megjelenik a **Szabadság- és távolléti tervek elhatárolása** párbeszédpanel. Az **Elhatárolás kezdete** részben válassza a **Mai dátum** vagy az **Egyéni dátum** lehetőséget, és adjon meg egy egyéni dátumot.

4. Ha minden vállalatnál szeretné futtatni az elhatárolást, válassza az **Összes vállalat** lehetőséget. Ha egyetlen szabadsági tervhez szeretné feldolgozni az elhatárolást, válassza a **Nem** lehetőséget az **Összes konstrukció** alatt, majd válasszon egy **Szabadságkonstrukciót**. Ha az összes vállalatot választja, akkor nem választhat ki egyéni szabadságtervet.

5. Ha a háttérben szeretné futtatni az elhatárolási folyamatot, válassza a **Futtatás a háttérben** parancsot, majd hajtsa végre a következő műveleteket:

   1. Információk megadása az elhatárolási folyamathoz.

   2. Ismétlődő feladat beállításához jelölje be az **Ismétlődés** jelölőnégyzetet, adja meg az ismétlődési adatokat, majd kattintson az **OK** gombra.

   3. A munkafigyelmeztetések beállításához jelölje ki a **Figyelmeztetések** lehetőséget, válassza ki, hogy milyen figyelmeztetéseket akar kapni ezzel kapcsolatban, majd kattintson az **OK** gombra.

   4. Válassza ki az **OK** lehetőséget. Az elhatárolási folyamat a megadott paraméterekkel fog futni.

## <a name="delete-leave-and-absence-accruals-for-multiple-employees"></a>Több alkalmazott szabadság- és távollét-elhatárolásának törlése

Törli az adott tervhez és dátumtartományhoz tartozó elhatárolási rekordokat. Az elhatárolásnak aznapi vagy jövőbeli dátummal kell rendelkeznie.

1. A **Szabadság és távollét** oldalon válassza a **Hivatkozások** lapot.

2. A **Szabadság kezelése** alatt válassza a **Szabadság- és távolléti tervek elhatárolásának törlése** lehetőséget.

3. A **Szabadság- és távolléti tervek elhatárolásának törlése** párbeszédpanelen válassza ki a **Szabadságterv** lehetőséget.

4. Ha szükséges, válassza az **Egyenleg-helyesbítések törlése** lehetőséget.

5. Adja meg vagy válassza ki a **Szabadság elhatárolási dátumát**. Ennek a dátumnak ma vagy a jövőben kell lennie.

6. Válassza ki az **OK** lehetőséget. Az elhatárolási folyamat a megadott paraméterekkel töröl elhatárolásokat.

## <a name="delete-leave-and-absence-accruals-for-a-single-employee"></a>Egy alkalmazott szabadság- és távollét-elhatárolásának törlése

1. Az alkalmazott rekordján válassza a **Szabadság** elemet.

2. Válassz a **Szabadság- és távolléti tervek elhatárolásának törlése** lehetőséget.

3. A **Szabadság- és távolléti tervek elhatárolásának törlése** párbeszédpanelen válassza ki a **Szabadságterv** lehetőséget.

4. Ha szükséges, válassza az **Egyenleg-helyesbítések törlése** lehetőséget.

5. Adja meg vagy válassza ki a **Szabadság elhatárolási dátumát**. Ennek a dátumnak ma vagy a jövőben kell lennie.

6. Válassza ki az **OK** lehetőséget. Az elhatárolási folyamat a megadott paraméterekkel töröl elhatárolásokat.

## <a name="review-leave-accrual-and-deletion-processes"></a>A szabadságelhatárolási és -törlési folyamatok áttekintése

**Szabadságelhatárolás auditálása** megjelenít minden egyes alkalmat, amikor elhatárolást futtatott vagy törölt egy vagy az összes munkavállalóhoz. Az dátum és a műveletet végrehajtó személy is meg lesz jelenítve.

1. A **Szabadság és távollét** oldalon válassza a **Hivatkozások** lapot.

2. A **Szabadság kezelése** alatt válassza a **Szabadságelhatárolás auditálásának törlése** lehetőséget.

## <a name="leave-accrual-transaction-auditing"></a>Szabadságelhatárolási tranzakció auditálása

Ez a verziójú funkció segít a szabadságokat és a távolléteket kezelőknek áttekinteni a szabadság- és a távollétkönyvelési tranzakciókat, amelyek egy alkalmazott távolléti egyenlegével kapcsolatosak egy adott távolléttípusnál.

A tranzakció részleteinek megtekintése:

1. Az alkalmazott rekordján válassza a **Szabadság** elemet.

2. Válassza a **Szabadság megtekintése** lehetőséget, majd lépjen az **Egyenlegek** lapra.

Az adott szabadságtípushoz kapcsolódó könyvelési tranzakciók megtekintéséhez válassza ki a numerikus értéket az **Aktuális egyenleg** oszlopban.

Adott könyvelési összegek tranzakciós részleteinek megtekintéséhez válasszon ki egy könyvelési sort, nyissa meg a **Kapcsolódó információ** panelt a jobb oldalon, majd a **Tranzakció részletei** szakaszt. Megjelenik a Tranzakció részletei szakasz:

- Az alkalmazott távolléttípusára vonatkozó egyenleg módosításai
- A foglalkoztatás adott könyvelési időszakra vonatkozó részletei
- A könyvelési időszak és a díjak részletei
- A szabadságterv konfigurációin végrehajtott módosítások

![Szabadságelhatárolási tranzakció auditálásának megjelenítése.](media/hr-leave-and-absence-accrue-audit.png)

## <a name="see-also"></a>Lásd még

[Szabadság és távollét áttekintése](hr-leave-and-absence-overview.md)</br>
[Szabadság- és távolléti terv létrehozása](hr-leave-and-absence-plans.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
