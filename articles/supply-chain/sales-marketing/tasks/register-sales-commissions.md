---
title: Értékesítési jutalékok regisztrálása
description: Ez a témakör az értékesítési jutalékok számításának és regisztrálásának módját mutatja be.
author: omulvad
manager: tfehr
ms.date: 08/06/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable, SalesEditLines,  CustInvoiceJournal, CommissionTrans, LedgerTransVoucher, CustClassificationGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 83cea952f4883d49621a9f7d16440927a8eddb98
ms.sourcegitcommit: 54da65a7da0efd4f0d9760c5b14ff785b28751c4
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/22/2020
ms.locfileid: "3830561"
---
# <a name="register-sales-commissions"></a>Értékesítési jutalékok regisztrálása

[!include [banner](../../includes/banner.md)]

Ez a témakör az értékesítési jutalékok számításának és regisztrálásának módját mutatja be. Ezt a folyamatot az USMF bemutatócéggel vagy saját adataival is futtathatja. Mielőtt elindítaná az útmutatót, az „Értékesítési jutalékok szabályainak beállítása” című segédlet futtatásával győződjön meg, hogy rendelkezik az összes szükséges jutalékszámítási beállítással.

Jegyezze fel a jutalékfolyamathoz kiválasztott vevő és cikkszámokat, majd használja ezeket ebben az útmutatóban a megfelelő helyen értékesítési rendelés létrehozásához.


## <a name="invoice-a-sales-order-that-qualifies-a-salesperson-for-a-commission"></a>Számlázzon egy értékesítési rendelést, amely lehetővé teszi egy értékesítőnek a jutalékot
1. A navigációs ablakban ugorjon a **Modulok > Értékesítés és marketing > Értékesítési rendelések > Minden értékesítési rendelés** pontra.
2. Válassza az **Új** lehetőséget.
3. A **Vevői számla** mező legördülő listájából válassza ki a kívánt rekordot.
4. Válassza ki az **OK** lehetőséget.
5. A műveleti ablaktáblán válassza ki a **Beállítások** elemet.
6. Válassza ki a **Nézetváltás** lehetőséget.
7. Válassza ki a **Fejlécnézet** elemet.
8. Bontsa ki a **Beállítások** szakaszt.

    - Az **Értékesítési csoport** mező értéke a csoportot jellemzi egy vagy több hozzárendelt értékesítővel. Az a csoport tagjai kapják jutalékokat a rendelés számlázásakor, előre megadott szorzók és elosztás szerint.   
    - Az érték a vevőkártyáról másolódik, de megváltoztatható.  
    - Az Értékesítési csoport is az értékesítési rendelés sorba másolódik. Meg lehet változtatni, így az eltérő lehet a fejlécben és/vagy a sorok között megadottól.  
    - A **Jutalékcsoport** mezőjének értéke azt a csoportot jelöli, amelyet egy vagy több vevő jutalékénak követése céljából hozott létre.   
    - Az érték a vevőkártyáról másolódik, de megváltoztatható.   

9. A műveleti ablaktáblán válassza ki a **Beállítások** elemet.
10. Válassza ki a **Nézetváltás** lehetőséget.
11. Válassza ki a **Sorokat megjelenítő nézet** elemre.
12. A **Cikkszám** mező legördülő listájában válassza ki a jutalékokhoz beállított elemet. 
13. Adjon meg egy számot a **Mennyiség** mezőben. Jegyezze fel a sor Nettó összegét. Az értékesítési bevétel összegét jelöli, amely ebben a példában a jutalékszámítás alapja.  
14. Válassza a **Mentés** lehetőséget.
15. A műveleti ablaktáblán válassza ki a **Számla** elemet.
16. Válassza ki a **Számla** lehetőséget.
17. Bontsa ki a **Paraméterek** szakaszt.
18. A **Mennyiség** mezőben válassza a **Mind** lehetőséget.
19. Válassza ki az **Igen** lehetőséget a **Feladás** mezőben.
20. Válassza ki az **OK** lehetőséget, majd ismét az **OK** lehetőséget a következő ablaktáblán. A tranzakció feladása körülbelül egy percet vesz igénybe. Engedélyezze a folyamat befejezését és ne zárja be az ablakot.  

## <a name="review-the-registered-sales-commissions"></a>A regisztrált értékesítési jutalékok áttekintése
1. A műveleti ablaktáblán válassza ki a **Számla**, majd ismét a **Számla** elemet.
2. A műveleti ablaktáblán válassza ki a **Számla**, majd a **Jutaléktranzakciók** elemet.

    - Az **Áttekintés** lap megjeleníti a számlázott értékesítési megrendeléshez társított értékesítőknek kifizethető jutalék összegeit jelölő sorokat. Most ellenőrizze a részleteket.  
    - Ha az „Értékesítési jutalékok szabályainak beállítása” útmutatót használta a **Jutalék értékesítési csoportja** beállításához, két ember kapja az értékesítési jutalékokat, és a jutalék egyenlően oszlik el közöttük.  
    - Ebben a példában a jutalék teljes összege az értékesítési bevétel (a rendelési sor nettó összege) százalékában számolt.  
3. Zárja be a lapot.
4. Válassza ki a **Bizonylat** lehetőséget. Ellenőrizheti a bizonylat tranzakciókat az előre megadott jutalék költséghez és jutalék fizethető számlához feladott jutalék összegekhez.  

