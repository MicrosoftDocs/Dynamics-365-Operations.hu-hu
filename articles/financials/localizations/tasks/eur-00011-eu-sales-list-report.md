--- 
title: "EU értékesítési lista jelentés készítése"
description: "Ezzel az eljárás végigvezeti az EU értékesítési lista jelentésének létrehozásán."
author: EvgenyPopovMBS
manager: AnnBe
ms.date: 03/02/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: epopov
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: 820c18eaa8d94b67c9d246c818ea13f3bdceeb39
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="generate-an-eu-sales-list-report"></a>EU értékesítési lista jelentés készítése

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ezzel az eljárás végigvezeti az EU értékesítési lista jelentésének létrehozásán. Ez magában foglalja a Közösségen belüli kereskedelmi tranzakciók átvitelét az EU értékesítési listára és a jelentés futtatását. Az eljárással egy bemutatásra szánt közösségen belüli kereskedelmi tranzakciót is létrehozhat. További tájékoztatásért az EU értékesítési lista jelentéséről, a kötelező előfeltételeket is beleértve, lásd a Dynamics 365 for Finance and Operations súgóját.

Ez az eljárás minden európai országra/régióra vonatkozik. Az eljárás a DEMF bemutatócég adataival lett létrehozva, így a példa ország/régió Németország lett. Az eljárás EU-s ország/régió példájaként Portugáliát is használja. Ez az eljárás végrehajtása előtt be kell állítania az EU értékesítési lista jelentését.

Ez az eljárás könyvelőknek szól.


## <a name="create-an-intra-community-sales-transaction-for-demo-purposes"></a>Bemutatás céljából egy Közösségen belüli értékesítési tranzakció létrehozása
1. Ugorjon a Kinnlevőségek > Rendelések > Minden értékesítési rendelés elemre.
2. Kattintson az Új lehetőségre.
3. A Vevői számla mezőbe írja be a „PRT-001” szöveget.
4. Kattintson az OK gombra.
5. A Cikkszám mezőbe írja be az „D0001” értéket.
6. Bontsa ki a Soradatok szakaszt.
7. Kattintson a Beállítások fülre.
8. A Cikkértékesítési adócsoport mezőbe írja be hogy „FULL”.
9. Kattintson az Új sor hozzáadására.
10. A Cikkszám mezőbe írja be az „D0003” értéket.
11. A Cikkértékesítési adócsoport mezőbe írja be hogy „RED”.
12. Kattintson a Mentés gombra.
13. A Művelet panelen kattintson a Számla lehetőségre.
14. Kattintson a Számla lehetőségre.
15. Bontsa ki a Paraméterek szakaszt.
16. A Mennyiség mezőben válassza a „Mind” lehetőséget.
17. Bontsa ki a Beállítások szakaszt.
18. A Számla kelte mezőben állítsa „01/11/2016” értékűre a dátumot.
19. Kattintson az OK gombra.
20. Kattintson az OK gombra.

## <a name="transfer-intra-community-trade-transactions-to-the-eu-sales-list"></a>Közösségen belüli kereskedelmi tranzakciók átvitele EU értékesítési listára
1. Ugorjon az Adó > Nyilatkozatok > Külkereskedelmi > EU értékesítési lista menüpontba.
2. Kattintson az Áthelyezés elemre.
3. Válassza az Igen beállítást a Cikk mezőben a cikktranzakciók átviteléhez.
4. Válassza az Igen beállítást a Szolgáltatás mezőben a szolgáltatástranzakciói átviteléhez.
    * Megadhat további szűrőket a Közösségen belüli kereskedelmi tranzakciók átviteléhez.  
5. Kattintson az Áthelyezés elemre.
    * Győződjön meg róla, hogy a Közösségen belüli értékesítési tranzakció sikeresen átkerül az EU értékesítési listára.  

## <a name="generate-the-eu-sales-list-report"></a>EU értékesítési lista jelentés készítése
1. Kattintson a Jelentéskészítés elemre.
2. A Jelentéskészítési időszak mezőben válassza a „Havi” lehetőséget.
3. A Kezdő dátum mezőben állítsa „01/01/2016” értékűre a dátumot.
4. Válassza az Igen lehetőséget a Fájl létrehozása mezőben.
5. Válassza az Igen lehetőséget a Jelentés létrehozása mezőben.
6. A Fájlnév mezőbe írja be, hogy „EUSalesList”.
7. A Jelentésnév mezőbe írja be, hogy „EUSalesList”.
8. A EU értékesítési lista regisztrációs azonosítója mezőbe írja be, hogy „123”.
    * Ez a mező csak Németországban érhető el.  
    * Megadhat további szűrőket a Közösségen belüli kereskedelmi tranzakciók jelentésbe foglalásához.  
9. Kattintson az OK gombra.
    * Győződjön meg róla, hogy előugró ablakok jelennek meg, amelyek megerősítik, hogy a fájl és az ellenőrző jelentés letöltése folyamatban van.  

## <a name="mark-eu-sales-list-lines-as-reported"></a>EU értékesítési lista sorainak megjelölése Jelentettként
1. Kattintson a Megjelölés elemre.
2. Kattintson a Megjelölés jelentettként elemre.
3. A listából válassza Számla keltezése mezőhöz tartozó sort.
4. A Feltétel mezőbe írja be, hogy „01/01/2016..01/31/2016”.
5. A listából válassza Jelentés állapota mezőhöz tartozó sort.
6. A Feltételek mezőben válasszon ki a „Belefoglalva” értéket.
    * Megadhat további szűrőket a Közösségen belüli kereskedelmi tranzakciók Jelentettként megjelöléséhez.  
7. Kattintson az OK gombra.
8. A Kiválasztása mezőben válassza a „Jelentve” lehetőséget.

## <a name="mark-eu-sales-list-lines-as-closed"></a>EU értékesítési lista sorainak megjelölése Lezártként
1. Kattintson a Megjelölés elemre.
2. Kattintson a Megjelölés lezártként elemre.
3. A listában jelölje meg a Számla keltezése mezőhöz tartozó sort.
4. A Feltétel mezőbe írja be, hogy „01/01/2016..01/31/2016”.
5. A listában jelölje meg a Jelentés állapota mezőhöz tartozó sort.
6. A Feltételek mezőben válassza ki a „Jelentve” értéket.
    * Megadhat további szűrőket a Közösségen belüli kereskedelmi tranzakciók Lezártként megjelöléséhez.  
7. Kattintson az OK gombra.
8. A Kiválasztása mezőben válassza a „Lezárt” lehetőséget.


