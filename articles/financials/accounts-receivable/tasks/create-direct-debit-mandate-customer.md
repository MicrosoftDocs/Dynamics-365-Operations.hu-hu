--- 
title: "Beszedési megbízási felhatalmazás létrehozása vevő részére"
description: "Ez az útmutató bemutatja, hogyan hozhat létre beszedési megbízási felhatalmazást, és hogyan használhatja azt számlához."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 10/23/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: d01c7c19925a3c7064ab3f845b92b610b162066c
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-direct-debit-mandate-for-a-customer"></a>Beszedési megbízási felhatalmazás létrehozása vevő részére

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

Ez az útmutató bemutatja, hogyan hozhat létre beszedési megbízási felhatalmazást, és hogyan használhatja azt számlához.


## <a name="create-a-bank-account"></a>Bankszámla létrehozása
1. Ugorjon a Kinnlevőségek > Vevők > Minden vevő pontra.
2. Válassza ki például az US-001-et.
3. A Művelet panelen kattintson a Vevő elemre.
4. Kattintson a Bankszámlák lehetőségre.
5. Kattintson az Új lehetőségre.
6. A Bankszámla mezőben adjon meg egy értéket.
7. Írjon be egy értéket a Név mezőbe.
8. Az IBAN mezőben adjon meg egy értéket.
9. Érték beírása a Pénznem mezőbe.
10. Kattintson a Mentés gombra.
11. Zárja be a lapot.
12. Menjen a Készpénz és bankkezelés > Bankszámlák > Bankszámlák menüpontra.
13. Keresse meg és jelölje ki a kívánt rekordot a listán.
14. A listában kattintson a kijelölt sorban lévő hivatkozásra.
15. Kattintson a Szerkesztés lehetőségre.
16. Bontsa ki a További azonosítás szakaszt.
17. Írjon egy értéket a Beszedési megbízási azonosító mezőbe.
18. Az IBAN mezőben adjon meg egy értéket.
19. Zárja be a lapot.
20. Zárja be a lapot.

## <a name="define-the-electronic-payment-method"></a>Elektronikus fizetési mód meghatározása
1. Ugorjon a Kinnlevőségek > Fizetési beállítás > Fizetési mód pontra.
2. Kattintson az Új lehetőségre.
3. Írjon be egy értéket a Fizetési mód mezőbe.
4. A Leírás mezőben adjon meg egy értéket.
5. A beszedési megbízási felhatalmazás fizetési módjában elektronikus fizetést kell beállítani.
6. Válassza az Igen lehetőséget a Felhatalmazás szükséges mezőben.
7. Zárja be a lapot.

## <a name="add-a-direct-debit-mandate-to-a-customer"></a>Beszedési megbízási rendelet hozzáadása a vevőhöz.
1. Ugorjon a Kinnlevőségek > Vevők > Minden vevő pontra.
2. Válassza ki például az US-001-et.
3. Kattintson a Szerkesztés lehetőségre.
4. Bontsa ki a Fizetés alapértelmezései szakaszt.
5. A Fizetési mód mezőben adjon meg vagy válasszon ki egy értéket.
6. Bontsa ki a Fizetés alapértelmezései szakaszt.
7. Bontsa ki a beszedési megbízási felhatalmazások szakaszt.
8. Kattintson a Hozzáadás gombra.
9. A Bankszámlák mezőben adjon meg vagy válasszon ki egy értéket.
10. A Hitelező bank mezőben adjon meg vagy válasszon ki egy értéket.
11. Adja meg, hogy várhatóan hány fizetést tervez feldolgozni ehhez a felhatalmazáshoz.
12. Kattintson az OK gombra.
13. Kattintson a Nyomtatás parancsra.
14. Kattintson a Felhatalmazás jelentése pontra.
15. Zárja be a lapot.
16. Kattintson a Szerkesztés lehetőségre.
17. Adja meg a dátumot az Aláírás dátuma mezőben.
18. Kattintson az Igen gombra.
19. Adja meg a felhatalmazás aláírásának helyét.
20. Kattintson az OK gombra.
21. Zárja be a lapot.

## <a name="create-a-free-text-invoice-with-mandate"></a>Szabadszöveges számla létrehozása felhatalmazással
1. Ugorjon a Kinnlévőségek > Számlák > Kizárólag szabadszöveges számlák pontra.
2. Kattintson az Új lehetőségre.
3. Válassza ki a vevőt, akihez hozzáadta a felhatalmazást.
4. A Beszedési megbízási felhatalmazás azonosítója mezőben adjon meg, vagy válasszon ki egy értéket.


