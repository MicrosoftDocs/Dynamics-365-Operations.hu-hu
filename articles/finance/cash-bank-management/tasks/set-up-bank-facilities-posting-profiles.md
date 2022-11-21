---
title: Bankhitelek beállítása és a garancialevélhez tartozó profilok feladása
description: Ez a feladat banki hitelt hoz létre, és feladási profilt, amely a garancialevél feldolgozásához szükséges.
author: kweekley
ms.date: 11/15/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: BankParameters, DefaultDashboard, BankDocumentSetup, BankDocumentPosting
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1bfdef0cd535f47bb1df9fb7494043d3dd519c5b
ms.sourcegitcommit: cf6b764824bd1cf2c0dde6d37ddd0a7abab87ff0
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/16/2022
ms.locfileid: "9779880"
---
# <a name="set-up-bank-facilities-and-posting-profiles-for-letters-of-guarantee"></a>Bankhitelek beállítása és a garancialevélhez tartozó profilok feladása

[!include [banner](../../includes/banner.md)]

Ez a feladat banki hitelt hoz létre, és feladási profilt, amely a garancialevél feldolgozásához szükséges.



Ez a feladat az USMF bemutatócéget használja. 




## <a name="general-ledger-parameter"></a>Főkönyvi paraméter
1. A Készpénz- **és bankkezelés > beállítása > készpénz- és bankkezelési paraméterekhez**.
2. Bontsa ki **a Banki bizonylat szakaszt**.
3. Válassza a Garancialevél **engedélyezése** lehetőséget.
4. A Tranzakciónapló **mezőben** kattintson a legördülő gombra a keresés megnyitásához.
5. A kívánt rekord megkeresése és kijelölése a listán
6. A listában kattintson a kijelölt sorban lévő hivatkozásra.
7. Kattintson a Számsorozatok **fülre**.
    * Adja meg a számsorozat kódját a Garancialevél számához és a Garancialevél tranzakciós hivatkozásához  
8. Kattintson a **Mentés** gombra.
9. Zárja be a lapot.

## <a name="create-bank-facility"></a>Banki hitel létrehozása
1. Váltsa át **a Készpénz- és bankkezelés > és > Bank hitellehetőségeihez**.
2. Kattintson az **Új** elemre.
3. A Hitelcsoport **mezőben** adja meg a garancialevél-tranzakció banki hitelcsoportjának nevét.
4. Írjon egy értéket a **Leírás** mezőbe.
5. Kattintson a **Mentés** gombra.
6. Kattintson a Hiteltípusok **fülre**.
7. Kattintson az **Új** elemre.
8. A Hitel **típusa mezőben** adja meg a banki hitelmegállapodáshoz kapcsolódó banki hiteltípus nevét.
9. Írjon egy értéket a **Leírás** mezőbe.
10. A Hitelcsoport **mezőben** kattintson a legördülő gombra a keresés megnyitásához.
11. Keresse meg és jelölje ki a kívánt rekordot a listán.
12. A listában kattintson a kijelölt sorban lévő hivatkozásra.
13. Válasszon egy beállítást a Hitel jellege mezőben.
14. Kattintson a **Mentés** gombra.
15. Zárja be a lapot.

## <a name="bank-posting-profile"></a>Banki feladási profil
1. Menjen a Készpénz- **és bankkezelés > beállítása > banki bizonylatok feladási profiljához**.
2. Kattintson az **Új** elemre.
3. A Számla **/csoport száma mezőben** kattintson a legördülő gombra a keresés megnyitásához.
4. A kívánt rekord megkeresése és kijelölése a listán
5. A listában kattintson a kijelölt sorban lévő hivatkozásra.
6. A Számla **kiegyenlítése mezőben** válassza ki a kiegyenlítés fő számláját.
7. A Költségszámla **mezőben** válassza ki a költségtranzakciók számláját.
8. A Különbözeti **számla mezőben** válassza ki a különbözeti tranzakció számláját.
9. A Felszámolási **számla mezőben** válassza ki a garancialevél-tranzakció felszámolási számláját. 
10. Kattintson a **Mentés** gombra.
11. Zárja be a lapot.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
