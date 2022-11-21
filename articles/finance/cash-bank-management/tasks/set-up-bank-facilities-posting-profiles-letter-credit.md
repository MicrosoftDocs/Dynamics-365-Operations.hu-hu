---
title: Bankhitelek beállítása és az akkreditívhez tartozó profilok feladása
description: Ez az eljárás bemutatja a banki hitel létrehozásán és az akkreditív feladásához szükséges profil közzétételén.
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
ms.openlocfilehash: 7fe5b2ba43c4fcb4855c742bdb6f8209ebd92d68
ms.sourcegitcommit: cf6b764824bd1cf2c0dde6d37ddd0a7abab87ff0
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/16/2022
ms.locfileid: "9779462"
---
# <a name="set-up-bank-facilities-and-posting-profiles-for-letter-of-credit"></a>Bankhitelek beállítása és az akkreditívhez tartozó profilok feladása

[!include [banner](../../includes/banner.md)]

Ez az eljárás bemutatja a banki hitel létrehozásán és az akkreditív feladásához szükséges profil közzétételén. 

Ezek az eljárások az „USMF” bemutatócéget használják.


## <a name="general-ledger-parameter"></a>Főkönyvi paraméter
1. A Készpénz- **és bankkezelés > beállítása > készpénz- és bankkezelési paraméterekhez**.
2. Bontsa ki **a Banki bizonylat szakaszt**.
3. Válassza az **Importakkreditó engedélyezése** lehetőséget.
4. Válassza az **Exportakkreditó engedélyezése** lehetőséget.
5. Kattintson a **Mentés** gombra.
6. Zárja be a lapot.

## <a name="create-bank-facility"></a>Banki hitel létrehozása
1. Váltsa át **a Készpénz- és bankkezelés > és > Bank hitellehetőségeihez**.
2. Kattintson az **Új** elemre.
3. A Hitelcsoport **mezőben** adja meg a banki hitelcsoport nevét.
4. A Leírás **mezőbe** írja be a banki hitelcsoport leírását.
5. Kattintson a **Mentés** gombra.
6. Kattintson a Hiteltípusok **fülre**.
7. Kattintson az **Új** elemre.
8. A Hitel **típusa mezőbe** írjon be egy egyedi kódot.
9. Írjon egy értéket a **Leírás** mezőbe.
10. A Hitelcsoport **mezőben** kattintson a legördülő gombra a keresés megnyitásához.
11. A kívánt rekord megkeresése és kijelölése a listán
12. A listában kattintson a kijelölt sorban lévő hivatkozásra.
13. A Hitel **jellege mezőben** adja meg a banki hitel jellegét.
14. Kattintson a **Mentés** gombra.
15. Zárja be a lapot.

## <a name="bank-posting-profile"></a>Banki feladási profil
1. Menjen a Készpénz- **és bankkezelés > beállítása > banki bizonylatok feladási profiljához**.
2. Kattintson az **Új** elemre.
3. A Számla **/csoport száma mezőben** kattintson a legördülő gombra a keresés megnyitásához.
4. A kívánt rekord megkeresése és kijelölése a listán
5. A listában kattintson a kijelölt sorban lévő hivatkozásra.
6. Válassza ki a rendezéshez a fő számlát.
    * Ezt a számlát kell használni a pénzforgalmi előrejelzés kiszámításakor.  
7. A Költségszámla **mezőben** válassza ki a költségtranzakciók számláját.
8. A Különbözeti **számla mezőben** válassza ki az árréstranzakciók számláját.
    * Ez a számla lesz megterhelve a nyitó különbözet feladásakor, és ezen a számlán jelenik meg a jóváírás a kifizetés feladásakor.  
9. Kattintson a **Mentés** gombra.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
