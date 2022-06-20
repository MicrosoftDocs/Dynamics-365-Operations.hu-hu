---
title: Alvállalkozásba adás
description: Ez a cikk segít az alvállalkozói tevékenységeknek a gyártásban való felépítésében Dynamics 365 Supply Chain Management.
author: johanhoffmann
ms.date: 09/28/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2018-09-30
ms.dyn365.ops.version: ''
ms.openlocfilehash: ef8f30e934ece4a148c6f5259d74f8f67799999d
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8854177"
---
# <a name="subcontracting"></a>Alvállalkozásba adás

[!include [banner](../includes/banner.md)]

Ez a cikk segítséget segít a Microsoft gyártási alvállalkozásba adásának felépítésében Dynamics 365 Supply Chain Management. A cikk első része az adatok beállítását írja le. A második rész végigvezeti Önt a forgatókönyv lépésein.

## <a name="target-audience"></a>Célközönség

Ebben a cikkben meg lehet ismerkedni az alvállalkozói szerződések beállításával a gyártás területén. A HQUS jogi személynél lévő adatokat fogja használni az alvállalkozásba adás tevékenységfolyamatának alapvető beállításához. A HQUS jogi személynél lévő bemutató adatok olyan beállítási paramétereket is tartalmaznak, amik az útmutató lépéseinek támogatására vannak állítva. Annak ellenére, hogy az útmutató a kulcsfontosságú gyenge pontokat és a kihívásokat a különböző szerepkörök számára vizsgálja, a rendszergazda is elvégezheti.

## <a name="demo-scenario"></a>Bemutató eset

A HQUS jogi személy felső kategóriás hangszórókat gyárt. A gyártási folyamat során a hangszórók az alábbi három műveleten esnek át.

- **Előzetes összeállítás** – a hangszórókabinetet összeállítják. A kabinet anyagát a művelet megkezdése előtt kiválasztják a nyersanyagraktárban.
- **Bevonás** – Miután a hangszórókabinetet összeállították, bevonatot kell készíteni rá. Ezt a műveletet egy szállító hajtja végre (alvállalkozó). Az előzetesen összeállított hangszórókabinetet két anyaggal együtt elszállítják a bevonás alvállalkozóhoz.
- **Elsimítás** – Az előzetesen összeállított hangszórókabinet, miután az alvállalkozó bevonatot készített hozzá, visszakerül a HQUS jogi személyhez, és a hangszóró végső összeállítása elkezdődhet.

A következő ábrán a három művelet és az általuk igényelt anyagok láthatóak.

![Az előzetes összeállítás, bevonás, elsimítás műveletek és az általuk felhasználandó anyagok.](./media/subcontract01_operations-materials.png)

## <a name="setup"></a>Beállítás

Az útmutató elkezdése előtt be kell állítania az adatokat.

### <a name="set-up-the-finished-product"></a>Elkészült termék beállítása

Ez az eljárás végigvezeti Önt a kiadott D8100 termék, a "Bevont kabinet" beállításán.

1. Válassza ki a **Termékinformációk kezelése \> Termékek \> Kiadott termékek** opciót a **Kiadott termék részletei** oldal megnyitásához.
2. A gyors szűrő mezőjébe írja be a **D8100** kódot a meglévő kiadott termék megtalálásához.

    ![A D8100 kiadott termék szűrése a kiadott termék részletei oldalon.](./media/subcontract02_filtering-released-products.png)

3. A műveleti ablakon, a **Mérnök** lapon válassza ki az **Útvonal** opciót az **Útvonal** oldal megnyitásához.

    Az **Útvonal** oldal megjeleníti a kiadott D8100 termék nyolc útvonalverzióját. A nyolc útvonalverzió négy-négy útvonalra van osztva az 1-es hely és az 5-ös hely között. A 000400 útvonal a költségszámításhoz használható, a 00041 útvonal a bevonási művelethez mint belső művelet használható, és a 00042 útvonal a bevonási művelethez mint külső művelet használható.

    ![Nyolc útvonalverzió az útvonal oldalon.](./media/subcontract03_route-page.png)

4. A felső ablakban, a **verziók** rácsban, jelölje be a **00042** útvonalverziót az **5-ös** helyhez.
5. Az alsó ablakban ,az **áttekintés** fülön, jelölje be a **20-as** (**Cbnt CtSc**) műveletet a rácsban.

    ![A 20-as művelet kiválasztva az 5-ös hely 00042 útvonalverzióhoz.](./media/subcontract04_route-version-operation.png)

6. Válassza ki az **Általános** fület.

    Figyelje meg, hogy az **útvonaltípus** mező értéke **szállító**. Ez az érték jelzi, hogy a 20-as (Cbnt CtSc) művelet egy alvállalkozói művelet.

    ![Az útvonaltípus mező értéke szállító az általános fülön.](./media/subcontract05_general-tab.png)

7. Válassza ki az **Erőforrás-követelmények** fület.

    A képességek használatba kerülnek majd egy alkalmazható erőforrás megkeresésére a termelési ütemezés közben. A 20-as művelet (Cbnt CtSc) esetében figyelje meg, hogy olyan erőforrásra van szükség, amelynek két képessége van, a **bevonás** és a **bevont kabinetek**.

    ![Bevonás és bevont kabinetek képességek az erőforrás-követelményeknek fülön.](./media/subcontract06_resource-requirements-tab.png)

8. Válassza ki az **Alkalmazható erőforrások** opciót az **Alkalmazható erőforrások** párbeszédpanel megnyitásához.

    Három erőforrás található, amely megfelel a művelethez tartozó erőforrás-követelményeknek. Figyelje meg, a 8851 és 8852 erőforrások **szállító** típusúak.

    ![Három kívánt erőforrás a megfelelő erőforrások párbeszédpanelen.](./media/subcontract07_applicable-resources-dialog.png)

9. Válassza ki az **OK** opciót az **Alkalmazható erőforrások** párbeszédpanel bezárásához és az **Útvonal** oldalra való visszatéréshez.
10. Zárja be az **Útvonal** oldalt a **Kiadott termék részletei** oldalra való visszatéréshez.

    ![Megjelent termék részletei oldal.](./media/subcontract08_released-product-details-page.png)

11. A műveleti ablakon, a **Mérnök** lapon válassza ki az **Anyajegyzék verziók** opciót az **Anyajegyzék verziók** oldal megnyitásához.

    Az **Anyagjegyzék-verziók** oldal megjeleníti a négy anyagjegyzéket (BOM), amik a kiadott D8100 termékhez tartoznak. A 000400 anyajegyzék a költségszámításhoz és a tervezéshez használható, a 00041 anyajegyzék a házon belüli bevonási művelethez használható, és a 00042, valamint a 000043 anyajegyzék az alvállalkozói bevonási művelethez használható.

    Figyelje meg, hogy az S8050 cikk egy **Szolgáltatás** elemtípusú termék. Ez a cikk az alvállalkozói munkát jelöli.

    ![A négy anyagjegyzék-verzió az anyagjegyzék-verziók oldalon.](./media/subcontract09_bom-versions-page.png)

12. Az **Anyagjegyzéksorok** gyorslapon válassza a **Szerkesztés** opciót az **Anyagjegyzéksor szerkesztése** párbeszédpanel megnyitásához.

    Amikor egy termelési rendelés létrehozásra és becslésre kerül a kiadott D8100 termékről, az auotomatikusan generál egy beszerzési rendelést az S8050 cikkről. Ez a beszerzési rendelés a termelési rendeléshez lesz kapcsolva. A beszerzési rendelések automatikus létrehozásához a **Sortípus** mezőt **Szállító** értékre kell állítani, és ki kell választani az alvállalkozó szállítói számláját. Ebben az esetben a szállítói számla USA-801.

    Figyelje meg, hogy az anyajegyzéksor a műveleti számon (ebben az esetben az 20) keresztül kapcsolódik a bevonás művelethez.

    ![anyajegyzéksor párbeszédpanel szerkesztése.](./media/subcontract10_edit-bom-line-dialog.png)

### <a name="create-a-password-for-warehouse-workers"></a>Jelszó létrehozása a raktári dolgozóknak

Meg kell adni egy jelszót a kéziszámítógépet használó raktári dolgozóknak.

1. Válassza ki a **Raktárkezelés \> Beállítás \> Dolgozó** opciót a **Munkafelhasználók** oldal megnyitásához.
2. A **Felhasználók** gyorslapon válassza ki az **51-es** felhasználó sorát.

    ![Munkafelhasználók oldal.](./media/subcontract11_work-users-page.png)

3. Válassza ki az **Új jelszó létrehozása** opciót.
4. A **Jelszó** és a **Jelszó megerősítése** mezőkben adja meg az **1** értéket.
5. Válassza ki a **Jelszó beállítása** opciót.

## <a name="step-by-step-walkthrough"></a>Útmutató lépésről lépésre

**Eset és háttér**

Egy 10 darabos termelési rendelés jön létre a D8100, "Bevont kabinet" termékre. A kabinetek bevonása egy alvállalkozói művelet, amit az US-801 szállító, a Perfect Coating Solutions végez. A termelési rendelés három műveletből áll. Az első művelet esetében a kabinet előzetes összeállításra kerül házon belül. Az előzetes összeállításhoz szükséges anyagok elérhetővé válnak kiválasztásra a nyersanyag raktárban. Az előzetes összeállítás befejezése után az előzetesen összeállított kabinetet a Perfect Coating Solutions-höz küldik két nyersanyaggal együtt, amelyek szükségesek a bevonás művelethez. Amikor a bevont kabinet visszaérkezik a szállítótól, akkor az átesik egy végső házon belüli összeállításon, mielőtt befejezettként jelentik.

1. Válassza ki a **Gyártásvezérlés \> Termelési rendelések \> Minden termelési rendelés** opciót a **Minden termelési rendelés** oldal megnyitásához.
2. A műveleti ablakon válassza ki az **Új termelési rendelés** opciót a **Termelési rendelés létrehozása** párbeszédpanel megnyitásához.

    ![Termelési rendelés létrehozása párbeszédpanel.](./media/subcontract12_create-production-order-dialog.png)

3. A **Cikkszám** mezőben válassza ki a **D8100** cikkszámot.
4. A cikkszám kiválasztása után eltűnnek a készletdimenzió-mezők. A **Szín** mezőben válassza ki a **Chrome** opciót.

    Megjelenik egy üzenetpanel, amely rákérdez, hogy az anyagjegyzék és az útvonal aktív verzióit be kell-e szúrni.

    ![Üzenetpanel.](./media/subcontract13_message-box.png)

5. Válassza ki az **Igen** lehetőséget. 

    A **Termelési rendelés létrehozása** párbeszédpanelen a D8100 termék anyagjegyzékének és útvonalának aktív verziói automatikusan kiválasztódnak az **Anyagjegyzékszám** és az **Útvonalszám** mezőkben. Ebben az esetben a **000040** anyajegyzék és a **000040** útvonal vannak kiválasztva.
    
    > [!NOTE]
    > Az anyagjegyzék és az útvonal esetében is a 000040 verzió használatos a költségszámításhoz és a tervezéshez.

6. A **Site** mezőben válasszon ki a **5** értéket.
7. A **Raktár** mezőben válassza ki az **51** értéket.
8. Az **Anyagjegyzékszám** és az **Útvonalszám** mezők értékét változtassa az automatikusan kiválasztottról a **000042** értékre.

    > [!NOTE]
    > Az anyagjegyzék és az útvonal esetében is a 000042 verzió használatos a kabinetbevonás US-801 szállítóhoz való alvállalkozásba adásához.

    ![A termelési rendelés létrehozása párbeszédpanelen beállított értékek.](./media/subcontract14_create-production-order-dialog-set.png)

9. Válassza ki a **Létrehozás** opciót a termelési rendelés létrehozásához, és térjen vissza a **Minden termelési rendelés** oldalra.

    ![Új termelési rendelés a minden termelési rendelés oldalon.](./media/subcontract15_new-production-order.png)

10. A műveleti ablakon, a **Termelési rendelés** lapon válassza ki a **Becslés** opciót a **Becslés** párbeszédpanel megnyitásához.

    ![Becslés párbeszédpanel.](./media/subcontract16_estimate-dialog.png)

11. Válassza ki az **OK** opciót a becslés megerősítéséhez, és térjen vissza a **Minden termelési rendelés** oldalra.

    > [!NOTE]
    > A termelési rendelés becslésekor létrejön az USA-801 szállító számára egy beszerzési rendelés, amely az S8050 szolgáltatási tételről szól.

12. A műveleti panelen, a **Termelési rendelés** lapon válassza az **Anyagjegyzék** elemet az **Anyagjegyzék** lap megnyitásához, amelyen megtekintheti az anyagjegyzéksorokat a termelési rendeléshez.

    Figyelje meg az S8050 szolgáltatási tételnél, hogy van egy hivatkozás a beszerzési rendelésre, amely akkor generálódott, amikor a termelési rendelést megbecsülték.

    ![Termelési rendelések anyagjegyzéksorai az Anyagjegyzék lapon.](./media/subcontract17_production-order-bom-lines.png)

13. Zárja be az **Anyagjegyzék** lapot a **Minden termelési rendelés** lapra való visszatéréshez.
14. A mműveleti ablaktábla **Ütemezés** lapján válassza ki a **Munkák ütemezése** opciót a **Feladatütemezés** párbeszédpanel megnyitásához.
15. Adja meg az alábbi értékeket:

    - Az **Ütemezés iránya** mezőben válassza ki a **Holnaptól továbbítás** lehetőséget.
    - Állítsa a **Véges kapacitás** lehetőséget **Igen** értékre.

    ![Feladatütemezés párbeszédpanel.](./media/subcontract18_job-scheduling-dialog.png)

16. Válassza ki az **OK** opciót az **Feladatütemezés** párbeszédpanel bezárásához és a **Minden termelési rendelés** oldalra való visszatéréshez.
17. A műveleti ablaktáblán, az **Ütemezés** lapon válassza a **Gantt** elemet a **Gantt-diagram – erőforrás nézet** lap megnyitásához.

    A Gantt-diagram vizuálisan jeleníti meg a termelési feladatok erőforrás-ütemezését. Figyelje meg, hogy a Külső bevonás művelete három feladatból áll: egy feldolgozási feladatból, egy szállítási feladatból és egy várakozási idő típusú feladatból.

    ![Gantt-diagram a Gantt-diagramon – Erőforrás nézet lap.](./media/subcontract19_gantt-chart.png)

18. Zárja be a **Gantt-diagram – Erőforrás nézet** lapot a **Minden termelési rendelés** lapra való visszatéréshez.
19. A műveleti ablakon, a **Termelési rendelés** lapon válassza ki a **Kiadás** opciót a **Kiadás** párbeszédpanel megnyitásához.

    ![Kiadás párbeszédpanel.](./media/subcontract20_release-dialog.png)

20. Kattintson az **OK** gombra a **Kiadás** párbeszédpanel bezárásához.
21. Válassza ki a **Gyártásvezérlés \> Időszakos feladatok \> Kiadás raktárba \> Darabjegyzék és receptúrasorok automatikus kiadása** lehetőséget a **Darabjegyzék és receptúrasorok automatikus kiadása** párbeszédpanel megnyitásához.

    ![Darabjegyzék és receptúrasorok automatikus kiadása párbeszédpanel.](./media/subcontract21_auto-release-bom-formula-lines-dialog.png)

22. Válassza az **OK** lehetőséget az Anyagjegyzék és receptúrasorok automatikus kiadása feladat futtatásához.

    Ez a feladat felszabadítja a nyersanyagok raktárba való kitárolásának munkáját.

23. Válassza ki a **Gyártásvezérlés \> Termelési rendelések \> Minden termelési rendelés** opciót a **Minden termelési rendelés** oldal megnyitásához.
24. A gyorsszűrés mező segítségével válassza ki azt a termelési rendelést, amelyen dolgozik.
25. A műveleti ablaktáblán, a **Raktár** lapon válassza ki a **Munka részletes adatai** opciót a **Munka** oldal megnyitásához.

    Figyelje meg, hogy a lap kétféle munkát jelenít meg a nyersanyag kitárolásához. Az első munka az M8100 és M8101 anyagokra vonatkozik. Ezeket az anyagokat a 10-es művelet használja fel. A másodi munka az M8202 és M8250 anyagokra vonatkozik. Ezek az anyagok a 20-as művelet során kerülnek felhasználásra, amely egy alvállalkozói művelet.

    ![A Munka lap kétféle munkát jelenít meg a nyersanyag kitárolásához.](./media/subcontract22_work-page.png)

26. Indítsa el a Raktárkezelés mobilalkalmazást a 10-es művelet raktári munkájának feldolgozásához.

    <!-- TBD – screen shots for processing pick work for the materials. -->

27. Válassza ki a **Gyártásvezérlés \> Termelési rendelések \> Minden termelési rendelés** opciót a **Minden termelési rendelés** oldal megnyitásához.
28. A gyorsszűrés mező segítségével válassza ki azt a termelési rendelést, amelyen dolgozik.
29. A műveleti ablakon, a **Termelési rendelés** lapon válassza ki az **Indítás** opciót az **Indítás** párbeszédpanel megnyitásához.
30. Az **Általános** lapon adja meg a következő értékeket:

    - A **Kezdő műveletszám** mezőben válassza a **10** értéket.
    - A **Záró műveletszám** mezőben válassza a **10** értéket.

    ![Az Általános lapon beállított értékek 1.](./media/subcontract23_start-dialog.png)

31. Válassza ki az **OK** opciót az **Indítás** párbeszédpanel bezárásához és a **Minden termelési rendelés** oldalra való visszatéréshez.

    Vegye figyelembe, hogy a termelési rendelés állapota ekkor **Elindítva**. A 10-es művelet anyagait a kitárolási lista naplójának automatikus feladása használja el. A 10-es művelet időfelhasználásának elszámolása egy útvonalkártya-napló automatikus feladásával történik.

32. Indítsa el a Raktárkezelés mobilalkalmazást a 20-es művelet raktári munkájának feldolgozásához.

    <!-- TBD – screen shots for processing pick work for the materials. -->

33. A műveleti ablakon, a **Termelési rendelés** lapon válassza ki az **Indítás** opciót az **Indítás** párbeszédpanel megnyitásához.
34. Az **Általános** lapon adja meg a következő értékeket:

    - A **Kezdő műveletszám** mezőben válassza a **20** értéket.
    - A **Záró műveletszám** mezőben válassza a **20** értéket.
    - Írja be a **10** értéket a **Mennyiség** mezőbe.
    - Válassza a **Nem** lehetőséget a **Kitárolási lista feladása most** mezőben.

    ![Az Általános lapon beállított értékek 2.](./media/subcontract24_general-tab.png)

35. Válassza ki az **OK** opciót az **Indítás** párbeszédpanel bezárásához és a **Minden termelési rendelés** oldalra való visszatéréshez.

    Létrejön egy kitárolási lista a külső bevonás műveletének anyagaihoz és a szolgáltatási tételhez. A szolgáltatási tétel az alvállalkozói művelet költségét jelenti.

36. A műveleti ablaktáblán, a **Nézet** lapon válassza a **Kitárolási lista** elemet a **Kitárolási lista** lap megnyitásához.
37. Válassza ki azt a kitárolási listát, amely nincs feladva, majd válassza ki a napló számát a naplósorok megtekintéséhez.

    ![Naplósorok a Kitárolási lista lapon.](./media/subcontract25_picking-list.png)

38. A Műveleti ablaktáblán válassza a **Nyomtatás**\>**Kitárolási lista jelentése** pontot a **Kitárolási lista jelentése** párbeszédpanel megnyitásához.
39. Állítsa a **Szállítólevél-elrendezés használata** opciót **Igen** értékre.

    ![Kitárolási lista jelentésének párbeszédpanele.](./media/subcontract26_picking-list-report-dialog.png)

40. Válassza az **OK** lehetőséget egy **Kitárolási lista** jelentés készítéséhez.

    Ebben az esetben a szállítói szállítólevél nyomtatása a termelési kitárolási lista naplójából történik. A szállítólevél meghatározza azokat az anyagokat, amelyek a külső bevonást elvégző szállítóhoz elszállítottak.

    ![Kitárolási lista jelentése.](./media/subcontract27_picking-list-report.png)

41. Zárja be a **Kitárolási lista** jelentést, ha vissza szeretne térni a **Kitárolási lista** oldalra.
42. A műveleti ablaktáblán kattintson a **Feladás** gombra a **Napló feladása** párbeszédpanel megnyitásához.

    ![Napló feladása párbeszédpanel.](./media/subcontract28_post-journal-dialog.png)

43. Kattintson az **OK** gombra a **Napló feladása** párbeszédpanel bezárásához.
44. Nyissa meg a beszerzési rendelést.

    ![Beszerzési rendelés lap.](./media/subcontract29_purchase-order-page.png)

45. A **Beszerzés** lap műveleti ablaktáblájában kattintson a **Megerősítés** pontra.
46. Kattintson a **Feladás** gombra a **Napló feladása** párbeszédpanel megnyitásához.
47. Válassza ki az **OK** opciót a **Napló feladása** párbeszédpanel bezárásához és a **Beszerzési rendelés** oldalra való visszatéréshez.
48. Módosítsa az egységárat **33** értékről **40** értékre.

    ![Módosult az egységár a Beszerzési rendelés lapon.](./media/subcontract30_unit-price.png)

49. Erősítse meg újra a beszerzési rendelést.
50. Termékbevételezés.

    ![Termékbevételezés feladásának párbeszédpanele.](./media/subcontract31_posting-product-receipt-dialog.png)

51. Beszerzési számla.
52. Egyeztetési állapot frissítése.

    ![Szállítói számla lapja.](./media/subcontract32_vendor-invoice-page.png)

53. Készként jelentés.

    ![Jlentés készként párbeszédpanel.](./media/subcontract33_report-as-finished-dialog.png)

54. Vége.

    ![Vége párbeszédpanel.](./media/subcontract34_end-dialog.png)

55. Költség összehasonlítása.

    ![Költség-összehasonlítás diagramjai.](./media/subcontract35_cost-comparison-charts.png)

Hiányzó beállítás az adatoknál.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]