---
title: Juttatásra való jogosultsági szabályok és irányelvek meghatározása
description: Ez a cikk bemutatja, hogyan hozhat létre juttatásra való jogosultsági szabályokat és irányelveket, majd miként rendelhet hozzá szabályokat a juttatásokhoz.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysPolicySourceDocumentRuleType, SysPolicyListPage, SysPolicy, HcmBenefitEligibilityPolicy, HcmBenefit, BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Human Resources
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Version 7.0.0, Human Resources
ms.openlocfilehash: f46437fef342ab1a4e368063d8b74205ca8e8c05
ms.sourcegitcommit: ba340f836e472f13f263dec46a49847c788fca44
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/04/2020
ms.locfileid: "3430877"
---
# <a name="define-benefit-eligibility-rules-and-policies"></a>Juttatásra való jogosultsági szabályok és irányelvek meghatározása

Ez a cikk bemutatja, hogyan hozhat létre juttatásra való jogosultsági szabályokat és irányelveket, majd miként rendelhet hozzá szabályokat a juttatásokhoz.  

A bemutató adatsor típusa, melyet a vállalat használt az útmutató készítéséhez, az USMF.


## <a name="create-benefit-eligibility-policy-rule-type"></a>Juttatásra való jogosultsági irányelvszabály-típus létrehozása
1. Ugorjon az Emberi erőforrások > Juttatások > Jogosultság > Juttatásra való jogosultsági irányelvszabály-típusok lehetőségre.
2. Kattintson az Új lehetőségre.
3. Írjon be egy értéket a Szabály neve mezőbe.
4. A Leírás mezőben adjon meg egy értéket.
5. A Lekérdezés neve mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
6. A listában kattintson a kijelölt sorban lévő hivatkozásra.
7. Kattintson a Mentés gombra.
8. Zárja be a lapot.

## <a name="benefit-eligibility-policy"></a>Juttatásra való jogosultsági irányelv
1. Ugorjon az Emberi erőforrások > Juttatások > Jogosultság > Juttatásra való jogosultsági irányelvszabályok lehetőségre.
2. Válasszon ki egy meglévő juttatási irányelvet.
3. A listában kattintson a kijelölt sorban lévő hivatkozásra.
4. Bontsa ki az Irányelv szervezetei részt.  Itt felveheti és eltávolíthatja a szervezeteket, amelyeket meg kíván említeni az irányelvben.
5. Csukja be vagy bontsa ki az Irányelvszabályok szakaszt.
6. A listában keresse ki a korábban létrehozott irányelvszabályt.
7. Kattintson az Irányelvszabályra.
8. Az Érvényesség dátuma mezőben adja meg a dátumot, amikor érvénybe kívánja léptetni az irányelvet.
    * Az érvényesség kezdő és záró dátumának beállítása lehetővé teszi az irányelvszabályok későbbi módosítását, és így nincs szükség visszatérni az irányelvhez, ha szeretné érvényesíteni ezeket a változtatásokat.  
9. 
    * Például, ha szeretné, hogy a szabály csak az Értékesítési vezetőkre vonatkozzon, akkor létrehozhatja az alábbi Where feltételt: Ahol a beosztás leírása megegyezik az Értékesítési vezető értékkel.  A Where kimutatást És vagy Vagy művelettel szorozhatja össze a szabályban.  
10. Kattintson az OK gombra.
11. Zárja be a lapot.
12. Zárja be a lapot.

## <a name="assign-rule-to-benefit"></a>Szabály hozzárendelése juttatáshoz
1. Ugorjon az Emberi erőforrások > Juttatások > Juttatások pontra.
2. Keresse meg és jelölje ki a kívánt rekordot a listán.
3. A listában kattintson a kijelölt sorban lévő hivatkozásra.
4. Bontsa ki vagy zárja be az Alkalmazhatósági szabályok szakaszt.
5. Kattintson a Szerkesztés lehetőségre.
6. Az Alkalmazhatóság mezőben válassza ki a Szabályalapú lehetőséget a listáról.
7. A Szabálytípus mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
8. A listában keresse meg és válassza ki a korábban létrehozott szabályt.
9. A listában kattintson a kijelölt sorban lévő hivatkozásra.
10. Kattintson a Mentés gombra.
11. Zárja be az űrlapot.

