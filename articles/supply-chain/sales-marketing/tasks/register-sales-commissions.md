---
title: Értékesítési jutalékok regisztrálása
description: Ez az eljárás bemutatja az értékesítési jutalék számítását és regisztrálását.
author: omulvad
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable, SalesEditLines,  CustInvoiceJournal, CommissionTrans, LedgerTransVoucher
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2c39b2fcf521106dfb58466bc45a316c0b506345
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2019
ms.locfileid: "355150"
---
# <a name="register-sales-commissions"></a>Értékesítési jutalékok regisztrálása

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ez az eljárás bemutatja az értékesítési jutalék számítását és regisztrálását. Ezt a folyamatot az USMF bemutatócéggel vagy saját adataival is futtathatja. Mielőtt elindítaná az útmutatót, az „Értékesítési jutalékok szabályainak beállítása” című segédlet futtatásával győződjön meg, hogy rendelkezik az összes szükséges jutalékszámítási beállítással.

Jegyezze fel a jutalékfolyamathoz kiválasztott vevő és cikkszámokat, majd használja ezeket ebben az útmutatóban a megfelelő helyen értékesítési rendelés létrehozásához.


## <a name="invoice-a-sales-order-that-qualifies-a-salesperson-for-a-commission"></a>Számlázzon egy értékesítési rendelést, amely lehetővé teszi egy értékesítőnek a jutalékot
1. Lépjen az Értékesítés és marketing > Értékesítési rendelések > Minden értékesítési rendelés menüpontba.
2. Kattintson az Új lehetőségre.
3. A Vevői számla mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
4. Keresse meg és jelölje ki a kívánt rekordot a listán.
5. A listában kattintson a kijelölt sorban lévő hivatkozásra.
6. Kattintson az OK gombra.
7. A Művelet ablaktáblában kattintson a Beállítások elemre.
8. Kattintson a Nézetváltás elemre.
9. Kattintson a Fejlécnézet gombra.
10. Bontsa ki a Beállítások szakaszt.
    * Az értékesítési csoport mező értéke a csoportot jellemzi, egy, vagy több hozzárendelt üzletkötővel. Az a csoport tagjai kapják jutalékokat a rendelés számlázásakor, előre megadott szorzók és elosztás szerint.   Az érték a vevőkártyáról másolódik, de megváltoztatható.  Az Értékesítési csoport is az értékesítési rendelés sorba másolódik. Meg lehet változtatni, így az eltérő lehet a fejlécben és/vagy a sorok között megadottól.  
    * A Jutalék csoport mezőjének értéke jelöli a csoportot, amelynek a célja egy vagy több vevő jutalékénak követése.   Az érték a vevőkártyáról másolódik, de megváltoztatható.   
11. A Művelet ablaktáblában kattintson a Beállítások elemre.
12. Kattintson a Nézetváltás elemre.
13. Kattintson a Sor nézetre.
14. A Cikkszám mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
15. A listában válassza ki a cikket, amelyet a jutalékokhoz állított be. 
16. Adjon meg egy számot a Mennyiség mezőben.
    * Jegyezze fel a sor Nettó összegét. Az értékesítési bevétel összegét jelöli, amely ebben a példában a jutalékszámítás alapja.  
17. Kattintson a Mentés gombra.
18. A Művelet panelen kattintson a Számla lehetőségre.
19. Kattintson a Számla lehetőségre.
20. Bontsa ki a Paraméterek szakaszt.
21. A Mennyiség mezőben válassza a „Mind” lehetőséget.
22. Válassza ki az Igen lehetőséget a Feladás mezőben.
23. Kattintson az OK gombra.
24. Kattintson az OK gombra.
    * A tranzakció feladása körülbelül egy percet vesz igénybe. Engedélyezze a folyamat befejezését és ne zárja be az ablakot.  

## <a name="review-the-registered-sales-commissions"></a>A regisztrált értékesítési jutalékok áttekintése
1. A Művelet panelen kattintson a Számla lehetőségre.
2. Kattintson a Számla lehetőségre.
3. A Művelet panelen kattintson a Számla lehetőségre.
4. Kattintson a Jutaléktranzakciókra.
    * Az Áttekintés lap a számlázott értékesítési megrendeléshez társított üzletkötőknek kifizethető jutalék összegeket jelölő sorokat mutat. Most ellenőrizze a részleteket.     
    * Ha az „Értékesítési jutalékok szabályainak beállítása” útmutatót használta a Jutalék értékesítési csoport beállításához, két ember kapja az értékesítési jutalékokat, és a jutalék egyenlően oszlik el közöttük.  
    * Ebben a példában a jutalék teljes összege az értékesítési bevétel (a rendelési sor nettó összege) százalékában számolt.   
5. Zárja be a lapot.
6. Kattintson a Bizonylat elemre.
    * Ellenőrizheti a bizonylat tranzakciókat az előre megadott jutalék költséghez és jutalék fizethető számlához feladott jutalék összegekhez.  

