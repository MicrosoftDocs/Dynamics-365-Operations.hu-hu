---
title: Minőségi rendelések beállítása
description: Ez az eljárás bemutatja, hogy hogyan engedélyezheti a minőségkezelési folyamatot, ha a bejövő készletet, a beérkezés regisztrációja után azonnal ellenőrizni szükséges.
author: perlynne
manager: tfehr
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventParameters, InventTestReportSetup, InventTestTable, DefaultDashboard, InventTestVariable, InventTestVariableOutcome, InventItemSampling, InventTestQualityGroup, InventTestItemQualityGroupAdd, SysQueryForm, InventTestItemQualityGroup, InventTestGroup, InventTestAssociationTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4577b8b189403b3d71eb634e159d51d2fa53ce12
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4429773"
---
# <a name="set-up-quality-orders"></a>Minőségi rendelések beállítása

[!include [banner](../../includes/banner.md)]

Ez az eljárás bemutatja, hogy hogyan engedélyezheti a minőségkezelési folyamatot, ha a bejövő készletet, a beérkezés regisztrációja után azonnal ellenőrizni szükséges. Ezt az eljárást jellemzően egy minőségbiztosítási vezető végzi. A folyamat részét képezi a minőségi csoport létrehozása, a mintavétellel érintett cikkek, valamint a minőségi csoportban szereplő cikkeken végzendő tesztek csoportosítását szolgáló tesztcsoport meghatározása. Ezt az útmutatót lefuttathatja az USMF bemutatócégen.


## <a name="enable-quality-management"></a>Minőségkezelés engedélyezése
1. Ugrás a **Navigációs ablaktábla > Modulok > Készletkezelés > Beállítás > Készlet- és raktárkezelési paraméterekre**.
2. Kattintson a **Minőségkezelés** lapra.
3. Állítsa a **Minőségkezelés használata beállítást** „Igen” értékre.
4. Kattintson a **Jelentésbeállítás** elemre. Az USMF-ben, a minőségkezelési jelentések beállításai előre definiálva vannak. Ha ez nem történt meg, adjon hozzá új sorokat a különböző típusú jelentés típusokhoz, majd válassza ki az egyes jelentésekhez használandó dokumentum típust.  
5. Zárja be a lapot.
6. Zárja be a lapot.

## <a name="create-a-test"></a>Teszt létrehozása
1. Ugorjon a **Készletkezelés > Beállítás > Minőség-ellenőrzés > Készlet** elemre.
2. Kattintson az **Új** elemre.
3. Adjon meg egy értéket a **Teszt** mezőben.
4. Írjon egy értéket a **Leírás** mezőbe.
5. A **Típus** mezőben válassza ki a „Lehetőség” elemet. Ebben a példában kiválasztjuk az „Opciók” lehetőséget, ami lehetővé teszi a teszteredmények, előre megadott értékek alapján történő társítását.  
6. Kattintson a **Mentés** gombra.
7. Zárja be a lapot.

## <a name="create-test-variables-to-define-the-way-test-results-are-recorded"></a>Tesztváltozók létrehozása a teszteredmények rögzítési módjának meghatározása érdekében
1. Ugorjon a **Készletkezelés > Beállítás > Minőség-ellenőrzés > Tesztváltozók** elemre.
2. Kattintson az **Új** elemre.
3. Adjon meg egy értéket a **Változó** mezőben.
4. Írjon egy értéket a **Leírás** mezőbe.
5. Kattintson a **Mentés** gombra.
6. Kattintson az **Eredmények** elemre.
7. Kattintson az **Új** elemre.
8. Adjon meg egy értéket az **Eredmény** mezőben.
9. Írjon egy értéket a **Leírás** mezőbe.
10. Az **Eredményállapot** mezőben válassza ki a „Megfelelt” értéket.
11. Kattintson a **Mentés** gombra.
12. Kattintson az **Új** elemre.
13. Adjon meg egy értéket az **Eredmény** mezőben.
14. Írjon egy értéket a **Leírás** mezőbe.
15. Kattintson a **Mentés** gombra.
16. Zárja be a lapot.
17. Zárja be a lapot.

## <a name="set-up-item-sampling"></a>Cikk-mintavétel beállítása
1. Ugorjon a **Készletkezelés > Beállítás > Minőség-ellenőrzés > Cikk-mintavétel** elemre.
2. Kattintson az **Új** elemre.
3. Adjon meg egy értéket a **Cikk-mintavétel** mezőben.
4. Írjon egy értéket a **Leírás** mezőbe.
5. Adjon meg egy számot az **Érték** mezőben. Ez az értéket a szomszédos mezőben kiválasztott Megadott mennyiségre vonatkozik.  
6. Bontsa ki vagy csukja össze a **Folyamat** szakaszt.
7. Jelölje be a **Teljes zárolás** jelölőnégyzetet, vagy törölje belőle a jelet. Ha kiválasztja ezt a lehetőséget, úgy sikertelen teszt esetén blokkolva lesz a teljes adat vagy rendelési sor mennyiség. Ha nem választja ki a lehetőséget, úgy csak a minőségi rendelésben szereplő cikkek kerülnek blokkolásra.  
8. Kattintson a **Mentés** gombra.
9. Zárja be a lapot.

> [!NOTE]
> A *Raktári folyamatok minőségkezelése* funkció további cikkmintavételi képességeket ad hozzá. Bevezeti a *Cikkmintaétel hatókörének* fogalmát, és lehetővé teszi egy teljes azonosítótábla meghatározását mennyiségi specifikációnak. Ha engedélyezte ezt a funkciót, a részleteket [Raktári folyamatok minőségkezelése](../quality-management-for-warehouses-processes.md) szakaszban találja.

## <a name="create-a-quality-group"></a>Minőségi csoport létrehozása
1. Ugorjon a **Készletkezelés > Beállítás > Minőség-ellenőrzés > Minőségi csoportok** elemre.
2. Kattintson az **Új** elemre.
3. Adjon meg egy értéket a **Minőségi csoport** mezőben. Használjon leíró jellegű nevet, ami segít beazonosítani, hogy a csoport milyen jellegű cikkeket tartalmaz (mintavételi feltételek).  
4. Írjon egy értéket a **Leírás** mezőbe.
5. Kattintson a **Mentés** gombra.
6. Kattintson a **Cikkek hozzáadása** pontra.
7. Válassza ki a **Cikkszám** sort. Ebben a példában a szűrést a cikkszám alapján futtatjuk.  
8. Adjon meg egy értéket a **Feltétel** mezőben. A T betűvel kezdődő cikkszámok szűréséhez például gépelje be azt, hogy T*.  
9. Kattintson az **OK** gombra.
10. Kattintson az **OK** gombra.
11. Kattintson a **Cikkminőségi csoportok megtekintése** elemre.
12. Zárja be a lapot.
13. Zárja be a lapot.

## <a name="create-a-test-group"></a>Tesztcsoport létrehozása
1. Ugorjon a **Készletkezelés > Beállítás > Minőség-ellenőrzés > Tesztcsoportok** elemre.
2. Kattintson az **Új** elemre.
3. Adjon meg egy értéket a **Tesztcsoport** mezőben. Olyan nevet adjon a **Tesztcsoportnak**, amely utal arra, hogy milyen jellegű teszteket futtat, és azt milyen minőségi csoporttal kell társítani. Ha például azt olyan minőségi csoporttal kívánja használni, ami a „T”-vel kezdődő cikkeket választja ki, úgy nevezze a csoportot például „T-cikk tesztek”-nek.  
4. Írjon egy értéket a **Leírás** mezőbe.
5. A **Cikk-mintavétel** mezőben válassza a korábban létrehozott cikk-mintavétel sort.
6. Keresse meg és jelölje ki a kívánt rekordot a listán.
7. Kattintson a **Hozzáadás** parancsra.
8. Adjon meg egy számot a **Sorozatszám** mezőben.
9. A **Teszt** mezőben válassza ki az előbbiekben létrehozott tesztet.
10. A kívánt rekord megkeresése és kijelölése a listán
11. Kattintson a **Teszt** lapra.
12. A **Változók** mezőben válassza ki az előbbiekben létrehozott változót.
13. A kívánt rekord megkeresése és kijelölése a listán
14. Az **Alapértelmezett eredmény** mezőben kattintson a legördülő gombra a keresőlista megnyitásához.
15. A listában kattintson a kijelölt sorban lévő hivatkozásra.
16. Kattintson a **Mentés** gombra.
17. Zárja be a lapot.

## <a name="define-when-quality-orders-will-be-created"></a>Határozza meg, hogy mikor történjen a minőségi rendelések létrehozása
1. Ugorjon a **Készletkezelés > Beállítás > Minőség-ellenőrzés > Minőségi társítások** elemre.
2. Kattintson az **Új** elemre.
3. Válasszon egy lehetőséget a **Hivatkozástípus** mezőben.
4. Válassza ki a „Csoport” lehetőséget a **Cikk kódja** mezőben. Ebben a példában a „Csoport”-ot " választjuk ki és a korábban létrehozott minőségi csoportot fogjuk felhasználni. Használhatja a „Táblázat” beállítást is, ha manuálisan kívánja megadni a cikkeket, vagy válassza a „Mind” lehetőséget az összes cikk, a minőségi csoporthoz történő hozzáadásához.  
5. A **Cikk** mezőben válassza ki az előbbiekben létrehozott minőségi csoportot. A Cikk mezőben rendelkezésre álló lehetőségek köre attól függ, hogy mit állított be a Cikk-kód mezőben.  
6. Keresse meg és jelölje ki a kívánt rekordot a listán.
7. Bontsa ki vagy csukja össze a Folyamat szakaszt.
8. Válasszon egy lehetőséget az **Eseménytípus** mezőben. Ez az esemény aktiválja a tesztet. A rendelkezésre álló lehetőségek köre attól függ, hogy milyen eljárást választott ki a Hivatkozástípus mezőben  
9. Válasszon egy lehetőséget a **Végrehajtás**  mezőben.
10. Bontsa ki vagy csukja össze a **Minőségi rendelési folyamat** szakaszt.
11. Az **Eseményzárolás** mezőben kattintson a legördülő gombra a keresőlista megnyitásához. Ez a mező azon eljárások jegyzékét tartalmazza, melyeket zárolni lehet, amikor a minőségi rendelés még nyitva van. A lehetőségek köre attól függ, hogy mit választott ki az Eseménytípus mezőben.  
12. A listában kattintson a kijelölt sorban lévő hivatkozásra. Ez a korábban kiválasztott értékek függvénye. Jelölje be, ha a következő folyamatokat zárolni kell, amikor nyitott minőségi rendelések kapcsolódnak egy forrásbizonylat-sorhoz.  
13. Bontsa ki vagy csukja össze a **Specifikációk** szakaszt.
14. A **Tesztcsoport** mezőben válassza ki az előbbiekben létrehozott tesztcsoportot.
15. Keresse meg és jelölje ki a kívánt rekordot a listán.
16. Kattintson a **Mentés** gombra.
17. Zárja be a lapot.

> [!NOTE]
> A *Raktári folyamatok minőségkezelése* funkció további lehetőségeket biztosít minőségi társítások beállításához. Hozzáad egy új feltételt (**Vonatkozó raktártípus**) és egy új beállítást (**Minőségfeldolgozási házirend**). Ha engedélyezte ezt a funkciót, a részleteket [Raktári folyamatok minőségkezelése](../quality-management-for-warehouses-processes.md) szakaszban találja.