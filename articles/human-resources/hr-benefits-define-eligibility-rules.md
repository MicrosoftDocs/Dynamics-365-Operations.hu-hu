---
title: Juttatásra való jogosultsági szabályok és irányelvek meghatározása
description: Ez a témakör elmagyarázza, hogyan hozhat létre jogosultsági szabályokat és házirendeket, majd hogyan rendelheti a szabályokat a juttatásokhoz.
author: twheeloc
ms.date: 08/23/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SysPolicySourceDocumentRuleType, SysPolicyListPage, SysPolicy, HcmBenefitEligibilityPolicy, HcmBenefit, BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Version 7.0.0, Human Resources
ms.openlocfilehash: 4781a00ae63bb2d27df0610a1886cc43e52798f9
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8861189"
---
# <a name="define-benefit-eligibility-rules-and-policies"></a>Juttatásra való jogosultsági szabályok és irányelvek meghatározása


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Ez a cikk bemutatja, hogy hogyan lehet létrehozni a juttatásra való jogosultsági szabályokat és irányelveket, majd szabályokat hozzárendelni a juttatásokhoz.  

## <a name="create-benefit-eligibility-policy-rule-type"></a>Juttatásra való jogosultsági irányelvszabály-típus létrehozása

1. Ugorjon az **Emberi erőforrások > Juttatások > Jogosultság > Juttatásra való jogosultsági irányelvszabály-típusok** lehetőségre.
2. Válassza az **Új** lehetőséget.
3. A **Szabály neve** mezőben adjon meg egy értéket.
4. A **Leírás** mezőben adjon meg egy értéket.
5. A **Lekérdezés neve** mezőben kattintson a legördülő nyílra a keresőlista megnyitásához.
6. A listában válassza ki a kiválasztott sorból a hivatkozást.
7. Válassza a **Mentés** lehetőséget.
8. Zárja be a lapot.

## <a name="benefit-eligibility-policy"></a>Juttatásra való jogosultsági irányelv

1. Ugorjon az **Emberi erőforrások > Juttatások > Jogosultság > Juttatásra való jogosultsági irányelvszabályok** lehetőségre.
2. Válasszon ki egy meglévő juttatási irányelvet.
3. A listában válassza ki a kiválasztott sorból a hivatkozást.
4. Bontsa ki az **Irányelv szervezetei** részt. Felveheti és eltávolíthatja a szervezeteket, amelyeket meg kíván említeni az irányelvben.
5. Csukja be vagy bontsa ki az **Irányelvszabályok** szakaszt.
6. A listában keresse ki a korábban létrehozott irányelvszabályt.
7. Válassza ki az **Irányelvszabály létrehozása** lehetőséget.
8. Az **Érvényesség dátuma** mezőben adja meg a dátumot, amikor érvénybe kívánja léptetni az irányelvet.
    * Az érvényesség kezdő és záró dátumának beállítása lehetővé teszi az irányelvszabályok későbbi módosítását, és így nem kell visszatérnie az irányelvhez, ha szeretné érvényesíteni ezeket a változtatásokat.  
9. Ha szükséges, adjon hozzá egy Where feltételt a **Feltétel hozzáadása** mezőhöz.
    * Például, ha szeretné, hogy a szabály csak az Értékesítési vezetőkre vonatkozzon, akkor létrehozhatja az alábbi Where feltételt: Ahol a beosztás leírása megegyezik az Értékesítési vezető értékkel. Több Where kimutatást adhat össze a szabályban.  
10. Válassza ki az **OK** lehetőséget.
11. Zárja be a lapot.

## <a name="assign-rule-to-benefit"></a>Szabály hozzárendelése juttatáshoz

1. Ugorjon az **Emberi erőforrások > Juttatások > Juttatások** pontra.
2. Keresse meg és jelölje ki a kívánt rekordot a listán.
3. A listában válassza ki a kiválasztott sorból a hivatkozást.
4. Bontsa ki vagy zárja be az **Alkalmazhatósági szabályok** szakaszt.
5. Válassza ki a **Szerkesztés** opciót.
6. Az **Alkalmazhatóság** mezőben válassza ki a szabályt.
7. A **Szabálytípus** mezőben keresse meg és válassza ki a korábban létrehozott szabályt.
9. A listában válassza ki a kiválasztott sorból a hivatkozást.
10. Válassza a **Mentés** lehetőséget.
11. Zárja be az űrlapot.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
