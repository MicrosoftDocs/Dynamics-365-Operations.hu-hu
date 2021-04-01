---
title: Szállítási ütemezés létrehozása
description: Ez az eljárás bemutatja, hogyan hozhatja létre az értékesítési rendelések kiszállítási ütemezését.
author: omulvad
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable, SalesDeliverySchedule, SalesEditLines,  SrsReportViewerForm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8ddbc59a35b5e6d466a495885e992a00f42f9994
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5250906"
---
# <a name="create-delivery-schedule"></a>Szállítási ütemezés létrehozása

[!include [banner](../../includes/banner.md)]

Ez az eljárás bemutatja, hogyan hozhatja létre az értékesítési rendelések kiszállítási ütemezését. A szállítási ütemezés akkor használatos, ha egy rendeléshez tartozó mennyiséget több részletben kell szállítani, vagy ilyen árajánlat szükséges. Ezt a folyamatot az USMF bemutatócéggel vagy saját adataival is futtathatja.


## <a name="create-delivery-schedule"></a>Szállítási ütemezés létrehozása
1. Ugrás az összes értékesítési rendelésre.
2. Kattintson az Új lehetőségre.
3. A Vevőszámla mezőben adjon meg vagy válasszon ki egy értéket.
4. Kattintson az OK gombra.
5. Az Elemszám mezőben adjon meg, vagy válasszon ki egy értéket.
6. A Mennyiség mezőben adjon meg egy 1-nél nagyobb számot.
7. Kattintson az Értékesítésirendelés-sor lehetőségre.
8. Kattintson a Szállítási ütemezés elemre.
    * A Szállítási ütemezés lap az a hely, ahol megadhatja a szállítmányok számát, amely mennyiséggel a rendelési sor szállításra kerül a vevőnek.    
    * Alapértelmezés szerint a rendszer bemásolja a teljes mennyiséget és az egyéb részleteket az eredeti eladási sorból az első szállítási ütemezés sorába. Ebben a példában két szállítmányhoz ütemezést hozunk létre, a második szállítmány dátumát egy héttel eltolva az első szállítmányétól.  
9. A Mennyiség mezőben adjon meg egy számot, amely a teljes mennyiség része.
10. Kattintson az Új elemre.
11. Ezután a Mennyiség mezőben adja meg a visszamaradó mennyiséget.
12. A kért szállítási dátum mezőben adjon meg egy olyan dátumot, amelyik egy héttel korábbi az első szállítási dátumnál.
    * A két lehetőség a Költségek átalakítás gyorslapon meghatározza, hogy hogyan oszoljanak el a költségek a szállítási ütemezés sorok között, miután hozzárendelte őket az eredeti rendelési sorhoz. Ha a Bruttó összeg másolását választja ugyanaz a költségösszeg kerül másolásra minden sorba. A Felosztás szállítmánysorokra lehetőség egyenlően osztja el a költségeket a szállítmánysorok között.  
    * Csak rögzített költségek oszthatók, míg a változó költségek változatlanul a sorokba kerülnek.  
13. Vigye el a kurzort a második szállítási sortól az oldal frissítéséhez.
    * Nyomon követheti a teljes mennyiséget, ami a szállítási ütemezés soraihoz van rendelve ha megtekinti az Összes és Maradvány mezőket. Ha a maradvány mennyisége nulla, akkor a teljes mennyiség az eredeti sorból az ütemezéshez lett rendelve.   
14. Kattintson az OK gombra.
    * A szállítási ütemezés most a rendeléssorokba lett másolva.   
    * Az eredeti rendelési sorra hivatkozó Kereskedelmi sor egy több szállítással rendelkező Rendeléssorhoz lett konvertálva. Egy külön ikon jelzi, ami fejlécként szolgál a szállítási sorokhoz.  
    * A szállítási sorokként hivatkozott két új sor egy szállítási ütemezést képez. A rendelés szembeni ezen sorok és nem az eredeti sor szerint kerül feldolgozásra. Ha a dokumentumokat, például visszaigazolási leveleket, szállítóleveleket, kitárolási leveleket vagy számlákat nyomtat csak a szállítási sorok láthatóak.   
    * A szállítási sorok különböző szállítási dátumokkal, mennyiségekkel, szállítási módokkal és tárolási dimenziókkal rendelkezhetnek, például webhely és raktár. Ugyanakkor a termékdimenzióknak mindig egyezniük kell a kereskedelmi sorral, amit nem lehet változtatni.  
15. A Mennyiség mezőben adjon meg a jelenleginél nagyobb számot.
16. Válassza ki a kereskedelmi sort a mennyiség-újraszámítás hatásának megtekintéséhez.
17. A Művelet panelen kattintson a Kitárolás és csomagolás elemre.
18. Kattintson A szállítólevél feladása lehetőségre.
19. Bontsa ki a Paraméterek szakaszt.
20. A Mennyiség mezőben válassza a „Mind” lehetőséget.
    * Vegye figyelembe, hogy a szállítólevél a két szállítási ütemezési sorba és a nem az eredeti rendelési sorba fog létrejönni.  
21. Válassza az Igen lehetőséget az Szállítólevél nyomtatása mezőben.
22. Kattintson az OK gombra.
23. Kattintson az Igen gombra.
24. Zárja be a lapot.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]