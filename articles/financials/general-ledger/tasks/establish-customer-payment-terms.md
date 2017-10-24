--- 
title: "Vevői kifizetések feltételeinek kialakítása"
description: "Ez az eljárás a készpénzfizetési engedményt és az esedékességi dátumot állítja be."
author: aprilolson
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 4e0e43962bea3ff1c3adafa73da4ce3862963a51
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="establish-customer-payment-terms"></a>Vevői kifizetések feltételeinek kialakítása

[!include[task guide banner](../../includes/task-guide-banner.md)]

Ez az eljárás a készpénzfizetési engedményt és az esedékességi dátumot állítja be. Ez az útmutató-feladat az USMF bemutatócéget használja.

1. Ugorjon a Kinnlevőségek > Fizetési beállítás > Fizetési napok pontra.
    * A fizetési feltételek beállítását a Kötelezettségek és a Kinnlevőségek közösen használják. Ha azt megadja ebben a modulban, úgy az a többi modulban is elérhető lesz. Ebben a feladat-útmutatóban beállítom a Kinnlevőségekre vonatkozó fizetési feltételeket.  
2. Kattintson az Új lehetőségre.
    * Hozzon létre fizetési napot, amennyiben a fizetési feltételei a hét (hétfő, kedd stb.) vagy a hónap egy adott napját (5-e, 10-e stb.) írják elő.  
3. A fizetési nap mezőben szereplő fizetési naphoz adjon meg egy Fizetési nap mező azonosítót.
4. Adja meg a fizetési nap leírását a Leírás mezőben.
5. A hét/hónap mezőben válassza a Hét vagy a Hónap lehetőséget.
    * Válassza ki a Hét lehetőséget, ha a hét egy adott napját szeretné megadni, például a hétfőt. Válassza ki a Hónap lehetőséget, ha a hónap egy adott napját szeretné megadni, például a 10-ét. Ehhez a példához válassza a Hónap lehetőséget.  
6. Adjon meg egy dátumot A hónap napja mezőben.
    * A dátumot szám formájában kell megadni, azaz például „10” és nem „10.”  
7. Kattintson a Mentés gombra.
8. Zárja be a lapot.
9. Ugorjon a Kinnlevőségek > Fizetési beállítás > Fizetési feltételek pontra.
10. Kattintson az Új lehetőségre.
    * A fizetési feltételek segítségével tudja meghatározni az esedékességi dátum számítását. A készpénzfizetési engedmény dátuma egy külön lapon kerül beállításra.  
11. A Fizetési feltételek mezőben adjon meg egy Fizetési feltételek mező azonosítót.
12. Adjon meg egy leírást a Leírás mezőben.
13. Válassza ki a fizetési módot, például: Utánvét, Nettó, Jelenlegi hónap stb.
    * A Fizetési mód segítségével tudja meghatározni az esedékességi dátum kiszámításának kezdetét.  A rendszer például a Nettó értéket használja, ha az esedékességi dátum minden esetben a számladátumot követő, meghatározott számú nap vagy hónap. Amennyiben a fizetés a számla ellenében esedékes, úgy használhatja az Utánvét lehetőséget, hogy a rendszer ne számoljon esedékességet. Ehhez a feladat-útmutatóhoz válassza a Jelenlegi hónap lehetőséget.  
14. Válasszon egy Fizetési napot, ha a számításban szerepel a hét egy adott napja vagy egy adott dátum.
    * Az Ön fizetési feltételei függvényében adja meg a kívánt Hónapok vagy Napok számát. Vagy használhatja a fizetési módhoz hozzáadandó Fizetési ütemezés vagy Fizetési nap lehetőséget. Amennyiben az esedékességi dátum minden esetben a következő hónap 10-e, úgy válassza ki a 10-ét, mint Fizetési napot.  
15. Kattintson a Mentés gombra.
16. Zárja be a lapot.
17. Ugorjon a Kinnlevőségek > Kifizetés beállítása > Készpénzfizetési engedmények pontra.
18. Kattintson az Új lehetőségre.
    * Ez az oldal a készpénzfizetési engedmény dátumának kiszámítására használható.  
19. A Készpénzfizetési engedmény mezőben adjon meg egy Készpénzfizetési engedmény mező azonosítót.
20. Adjon meg egy leírást a Leírás mezőben.
21. Többszintű készpénzfizetési engedmény esetén válassza ki az új készpénzfizetési engedmény után releváns Következő engedmény kódját.
22. Adja meg a készpénzfizetési engedmény dátumához használandó napok számát.
    * Ha a Nettó irányelv lehetőséget választotta, a napok száma hozzáadódik a számla dátumához, és így kerül kiszámításra a készpénzfizetési engedmény dátuma.  
23. Adja meg a készpénzfizetési engedmény százalékát.
24. Adja meg a fő számlát, amelyhez a vevői számlákon feladásra kerül a készpénzfizetési engedmény.
25. Válasszon egy lehetőséget a Kedvezmény ellenszámlák mezőben.
    * Ha a „Számlák a számlasorokban” beállítást választja, úgy a készpénzfizetési engedmény a szállítói számlasorok ugyanazon eszköz/költség főszámlájára kerül feladásra. A „Fő számla használata szállítói számlákhoz” lehetőség használata esetén a készpénzfizetési engedmény feladása a „Fő számla szállítói számlákhoz” elemnél megjelölt fő számlára történik. Ehhez a példához válassza a „Fő számla használata szállítói számlákhoz” lehetőséget.  
26. Adja meg a fő számlát, amelyhez a szállítói számlákon feladásra kerül a készpénzfizetési engedmény.
27. Kattintson a Mentés gombra.


