---
title: "Minőségi rendelések beállítása"
description: "Ez az eljárás bemutatja, hogy hogyan engedélyezheti a minőségkezelési folyamatot, ha a bejövő készletet, a beérkezés regisztrációja után azonnal ellenőrizni szükséges."
author: perlynne
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 73981313fc662094ee4f8bb15a88271e16d41193
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="set-up-quality-orders"></a>Minőségi rendelések beállítása

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ez az eljárás bemutatja, hogy hogyan engedélyezheti a minőségkezelési folyamatot, ha a bejövő készletet, a beérkezés regisztrációja után azonnal ellenőrizni szükséges. Ezt az eljárást jellemzően egy minőségbiztosítási vezető végzi. A folyamat részét képezi a minőségi csoport létrehozása, a mintavétellel érintett cikkek, valamint a minőségi csoportban szereplő cikkeken végzendő tesztek csoportosítását szolgáló tesztcsoport meghatározása. Ezt az útmutatót lefuttathatja az USMF bemutatócégen.


## <a name="enable-quality-management"></a>Minőségkezelés engedélyezése
1. Ugrás a Készletkezelés > Beállítás > Készlet- és raktárkezelési paraméterek lehetőségre.
2. Kattintson a Minőségkezelés lapra.
3. Állítsa a Minőségkezelés használata beállítást Igen értékre.
4. Kattintson a Jelentés-beállítás elemre.
    * Az USMF-ben, a minőségkezelési jelentések beállításai előre definiálva vannak. Ha ez nem történt meg, adjon hozzá új sorokat a különböző típusú jelentés típusokhoz, majd válassza ki az egyes jelentésekhez használandó dokumentum típust.  
5. Zárja be a lapot.
6. Zárja be a lapot.

## <a name="create-a-test"></a>Teszt létrehozása
1. Ugorjon a következőhöz: Készletkezelés > Beállítás > Minőség-ellenőrzés > Készlet.
2. Kattintson az Új lehetőségre.
3. Írjon be egy értéket a Teszt mezőbe.
4. A Leírás mezőben adjon meg egy értéket.
5. Az „Opció” kiválasztása a Típus mezőben.
    * Ebben a példában kiválasztjuk az „Opciók” lehetőséget, ami lehetővé teszi a teszteredmények, előre megadott értékek alapján történő társítását.  
6. Kattintson a Mentés gombra.
7. Zárja be a lapot.

## <a name="create-test-variables-to-define-the-way-test-results-are-recorded"></a>Tesztváltozók létrehozása a teszteredmények rögzítési módjának meghatározása érdekében
1. Ugorjon a következőhöz: Készletkezelés > Beállítás > Minőség-ellenőrzés > Tesztváltozók.
2. Kattintson az Új lehetőségre.
3. Írjon be egy értéket a Változó mezőbe.
4. A Leírás mezőben adjon meg egy értéket.
5. Kattintson a Mentés gombra.
6. Kattintson az Eredmények elemre.
7. Kattintson az Új lehetőségre.
8. Írjon be egy értéket az Eredmény mezőbe.
9. A Leírás mezőben adjon meg egy értéket.
10. Az Eredményállapot mezőben válassza a „Megfelelt” értéket.
11. Kattintson a Mentés gombra.
12. Kattintson az Új lehetőségre.
13. Írjon be egy értéket az Eredmény mezőbe.
14. A Leírás mezőben adjon meg egy értéket.
15. Kattintson a Mentés gombra.
16. Zárja be a lapot.
17. Zárja be a lapot.

## <a name="set-up-item-sampling"></a>Cikk-mintavétel beállítása
1. Ugorjon a következőhöz: Készletkezelés > Beállítás > Minőség-ellenőrzés > Cikk-mintavétel.
2. Kattintson az Új lehetőségre.
3. Írjon be egy értéket a Cikk-mintavétel mezőbe.
4. A Leírás mezőben adjon meg egy értéket.
5. Adjon meg egy számot az Érték mezőben.
    * Ez az értéket a szomszédos mezőben kiválasztott Megadott mennyiségre vonatkozik.  
6. Bontsa ki vagy csukja össze a Folyamat szakaszt.
7. Jelölje be a Teljes zárolás jelölőnégyzetet, vagy törölje belőle a jelet.
    * Ha kiválasztja ezt a lehetőséget, úgy sikertelen teszt esetén blokkolva lesz a teljes adat vagy rendelési sor mennyiség. Ha nem választja ki a lehetőséget, úgy csak a minőségi rendelésben szereplő cikkek kerülnek blokkolásra.  
8. Kattintson a Mentés gombra.
9. Zárja be a lapot.

## <a name="create-a-quality-group"></a>Minőségi csoport létrehozása
1. Ugorjon a következőhöz: Készletkezelés > Beállítás > Minőség-ellenőrzés > Minőségi csoportok.
2. Kattintson az Új lehetőségre.
3. Írjon be egy értéket a Minőségi csoport mezőbe.
    * Használjon leíró jellegű nevet, ami segít beazonosítani, hogy a csoport milyen jellegű cikkeket tartalmaz (mintavételi feltételek).  
4. A Leírás mezőben adjon meg egy értéket.
5. Kattintson a Mentés gombra.
6. Kattintson a Cikkek hozzáadása pontra.
7. Válassza ki a Cikkszám sort
    * Ebben a példában a szűrést a cikkszám alapján futtatjuk.  
8. Érték beírása a Feltétel mezőbe.
    * A T betűvel kezdődő cikkszámok szűréséhez például gépelje be azt, hogy T*.  
9. Kattintson az OK gombra.
10. Kattintson az OK gombra.
11. Cikkminőségi csoportok megtekintése.
12. Zárja be a lapot.
13. Zárja be a lapot.

## <a name="create-a-test-group"></a>Tesztcsoport létrehozása
1. Ugorjon a következőhöz: Készletkezelés > Beállítás > Minőség-ellenőrzés > Tesztcsoportok.
2. Kattintson az Új lehetőségre.
3. Írjon be egy értéket a Tesztcsoport mezőbe.
    * Olyan nevet adjon a Tesztcsoportnak, amely utal arra, hogy milyen jellegű teszteket futtat, és azt milyen minőségi csoporttal kell társítani. Ha például azt olyan minőségi csoporttal kívánja használni, ami a „T”-vel kezdődő cikkeket választja ki, úgy nevezze a csoportot például „T-cikk tesztek”-nek.  
4. A Leírás mezőben adjon meg egy értéket.
5. A Cikk-mintavétel mezőben válassza a korábban létrehozott cikk-mintavétel sort.
6. Keresse meg és jelölje ki a kívánt rekordot a listán.
7. Kattintson a Hozzáadás gombra.
8. Adjon meg egy számot a Sorozatszám mezőben.
9. A Teszt mezőben válassza ki az előbbiekben létrehozott tesztet.
10. A kívánt rekord megkeresése és kijelölése a listán
11. Kattintson a Teszt lapra.
12. A Változók mezőben válassza ki az előbbiekben létrehozott változót.
13. A kívánt rekord megkeresése és kijelölése a listán
14. Az Alapértelmezett eredmény mezőben kattintson a legördülő gombra a keresőlista megnyitásához.
15. A listában kattintson a kijelölt sorban lévő hivatkozásra.
16. Kattintson a Mentés gombra.
17. Zárja be a lapot.

## <a name="define-when-quality-orders-will-be-created"></a>Határozza meg, hogy mikor történjen a minőségi rendelések létrehozása
1. Ugorjon a következőhöz: Készletkezelés > Beállítás > Minőség-ellenőrzés > Minőségi társítások.
2. Kattintson az Új lehetőségre.
3. Válasszon egy lehetőséget a Hivatkozástípus mezőben.
4. Válassza a „Csoport” lehetőséget a Cikk mezőben:
    * Ebben a példában a „Csoport”-ot " választjuk ki és a korábban létrehozott minőségi csoportot fogjuk felhasználni. Használhatja a „Táblázat” beállítást is, ha manuálisan kívánja megadni a cikkeket, vagy válassza a „Mind” lehetőséget az összes cikk, a minőségi csoporthoz történő hozzáadásához.  
5. A Cikk mezőben válassza ki az előbbiekben létrehozott minőségi csoportot.
    * A Cikk mezőben rendelkezésre álló lehetőségek köre attól függ, hogy mit állított be a Cikk-kód mezőben.  
6. Keresse meg és jelölje ki a kívánt rekordot a listán.
7. Bontsa ki vagy csukja össze a Folyamat szakaszt.
8. Válasszon egy lehetőséget az Eseménytípus mezőben.
    * Ez az esemény aktiválja a tesztet. A rendelkezésre álló lehetőségek köre attól függ, hogy milyen eljárást választott ki a Hivatkozástípus mezőben  
9. Válasszon egy lehetőséget a Végrehajtás mezőben.
10. Bontsa ki vagy csukja össze a Minőségi rendelési folyamat szakaszt.
11. Az Eseményzárolás mezőben kattintson a legördülő gombra a keresőlista megnyitásához.
    * Ez a mező azon eljárások jegyzékét tartalmazza, melyeket zárolni lehet, amikor a minőségi rendelés még nyitva van. A lehetőségek köre attól függ, hogy mit választott ki az Eseménytípus mezőben.  
12. A listában kattintson a kijelölt sorban lévő hivatkozásra.
    * Ez a korábban kiválasztott értékek függvénye. Jelölje be, ha a következő folyamatokat zárolni kell, amikor nyitott minőségi rendelések kapcsolódnak egy forrásbizonylat-sorhoz.  
13. Bontsa ki vagy csukja össze a Specifikációk szakaszt.
14. A Tesztcsoport mezőben válassza ki az előbbiekben létrehozott tesztcsoportot.
15. A kívánt rekord megkeresése és kijelölése a listán
16. Kattintson a Mentés gombra.
17. Zárja be a lapot.

