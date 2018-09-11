--- 
title: "Bankhitelek beállítása és az akkreditívhez tartozó profilok feladása"
description: "Ez az eljárás bemutatja a banki hitel létrehozásán és az akkreditív feladásához szükséges profil közzétételén."
author: kweekley
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BankParameters, DefaultDashboard, BankDocumentSetup, BankDocumentPosting
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: 43422627f8529768ab9377c04568da531d6565c6
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="set-up-bank-facilities-and-posting-profiles-for-letter-of-credit"></a>Bankhitelek beállítása és az akkreditívhez tartozó profilok feladása

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ez az eljárás bemutatja a banki hitel létrehozásán és az akkreditív feladásához szükséges profil közzétételén. 

Ezek az eljárások az „USMF” bemutatócéget használják.






## <a name="general-ledger-parameter"></a>Főkönyvi paraméter
1. Ugorjon a Készpénz- és bankkezelés > Beállítás > Készpénz- és bankkezelési paraméterek pontra.
2. Bontsa ki a A banki bizonylat szakaszt.
3. Jelölje be az Importakkreditív engedélyezése lehetőséget.
4. Jelölje be az Exportakkreditív engedélyezése lehetőséget.
5. Kattintson a Mentés gombra.
6. Zárja be a lapot.

## <a name="create-bank-facility"></a>Banki hitel létrehozása
1. Ugorjon a Készpénz- és bankkezelés > Beállítás > Banki hitelek pontra.
2. Kattintson az Új lehetőségre.
3. A Hitelcsoport mezőben adja meg a banki hitelcsoportot.
4. A Leírás mezőbe írja be a banki hitelcsoport leírását.
5. Kattintson a Mentés gombra.
6. Kattintson a Hitelek lapra.
7. Kattintson az Új lehetőségre.
8. Írja be a cikk egyedi nevét a Hiteltípus mezőbe.
9. A Leírás mezőben adjon meg egy értéket.
10. A Hitelcsoport mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
11. A kívánt rekord megkeresése és kijelölése a listán
12. A listában kattintson a kijelölt sorban lévő hivatkozásra.
13. A Hitel természete mezőben válassza ki a hiteltípushoz tartozó természetet.
14. Kattintson a Mentés gombra.
15. Zárja be a lapot.

## <a name="bank-posting-profile"></a>Banki feladási profil
1. Ugorjon a Készpénz- és bankkezelés > Beállítás > Banki dokumentumok közzétele profil pontra.
2. Kattintson az Új lehetőségre.
3. A Fiók/Csoport száma mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
4. A kívánt rekord megkeresése és kijelölése a listán
5. A listában kattintson a kijelölt sorban lévő hivatkozásra.
6. Válassza ki a rendezéshez a fő számlát.
    * Ezt a számlát kell használni a pénzforgalmi előrejelzés kiszámításakor.  
7. A Díjfiók mezőben válassza ki a számlát a költségtranzakciókhoz.
8. Az Értékpapír-hitelszámla mezőben válassza ki a számlát az értékpapír-tranzakciókhoz.
    * Ez a számla lesz megterhelve a nyitó különbözet feladásakor, és ezen a számlán jelenik meg a jóváírás a kifizetés feladásakor.  
9. Kattintson a Mentés gombra.


