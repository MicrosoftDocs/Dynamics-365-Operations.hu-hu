---
title: TDS-kifizetések elszámolása TDS-hatósági szállítóknak és TDS-challan generálása
description: Ez a témakör elmagyarázza, hogyan kell rendezni a Forrásnál levont adó (TDS) kifizetését hatóság szállítóinak.
author: kailiang
ms.date: 03/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: 19f41020c6e1db8b08c7f69a58d33852c730931447803e2e1e970b1c293b6acd
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6779398"
---
# <a name="settle-tds-payments-to-tds-authority-vendors-and-generate-tds-challan"></a>TDS-kifizetések elszámolása TDS-hatósági szállítóknak és TDS-challan generálása

[!include [banner](../includes/banner.md)]

Ez a témakör elmagyarázza, hogyan kell rendezni a Forrásnál levont adó (TDS) kifizetését hatóság szállítóinak.

1. Ugorjon a **Kötelezettségek \> Fizetések \> Szállítói kifizetés naplója** lehetőségre.

    [![Szállítói kifizetési napló oldal.](./media/apac-ind-TDS-51.png)](./media/apac-ind-TDS-51.png)

2. A **Szállító kifizetési naplója** oldalán válassza az **Új** lehetőséget egy naplósor létrehozásához.
3. A **Számla** mezőben válassza ki azt a TDS hatósági szolgáltatót, amelyhez a TDS-kifizetéseket rendezni szeretné.
4. Válassza az **Kiegyenlítési tranzakciók** lehetőséget a **Kiegyenlítési tranzakciók** lap megnyitásához, ahol megtekintheti a TDS hatósági szállítójának kiegyenlített TDS-tranzakcióit.

    Az elszámolási időszakra vonatkozó kiegyenlített TDS-tranzakciók a következőképpen jelennek meg:

    - Azokat a TDS-tranzakciókat, amelyekben az értékelőkategória jellege **Vállalat**, egy tranzakciós sorként kell jelennek meg.
    - Azok a TDS-tranzakciók, amelyeknél az értékelő kategória jellege **HUF**, **Cég**, **Magánszemély**, **AOP**, **BOI**, **Önkormányzat** vagy **Egyéb**, egy tranzakciós sorként jelennek meg.
    - Az **Összeg** mező a TDS hatósági szállítónak fizetendő teljes TDS-összeget mutatja.

5. Válassza az **Adóelőleg tranzakciók** lehetőséget az elszámolási rekordhoz tartozó különböző TDS-tranzakciók megtekintéséhez. Ezen az oldalon megtekintheti az elszámolási időszak elszámolási folyamatában szereplő egyes TDS-tranzakciók felosztását.
6. Az **Áttekintés** lapon jelölje be a **Megjelölés** jelölőnégyzetet TDS-tranzakciókhoz a TDS hatósági szállítónak történő kiegyenlítéshez.

    Az **Áttekintés** lapon az egyes nyitott TDS-tranzakciókra vonatkozó következő információk találhatók:

    - **Dátum** – A TDS-tranzakció dátuma.
    - **Bizonylat** – A bizonylatszám.
    - **Forrás** – A modul, amelyben a TDS-tranzakció közzé lett téve.
    - **Szállító/Vevő** – Az a szállítói vagy vevői számlaszám, amelyről a TDS levonásra kerül.
    - **A levont fél/fél neve** – Annak a szállítónak vagy vevőnek a neve, akitől a TDS levonásra kerül.
    - **Értékelő jellege** – Az értékelő kategória jellege, amelyhez a levont fél tartozik.
    - **Összeg** – Az a számlaösszeg, amelyen a TDS kiszámításra került.
    - **Adóösszeg** – A tranzakcióhoz kiszámított TDS-összeg.

    > [!NOTE]
    > Törölje a jelet a **Jelölés** jelölőnégyzetből azokhoz a TDS-tranzakciókhoz, amelyeket nem kell a TDS-hatóság szállító felé kiegyenlíteni.

    Az **Általános** lapon a **PAN** mező a levont fél állandó számlaszámát (PAN) mutatja. A **Dátum** mező a TDS-számítás dátumát, az **Érték** mező pedig a TDS-számításhoz használt teljes százalékot mutatja.

7. Válassza a **Bizonylat** lehetőséget a TDS-tranzakció bizonylatrekordjainak megtekintéséhez.
8. Zárja be a lapot.
10. Válassza az **Adóelőleg-összetevők** lehetőséget az **Adóelőleg-összetevők** lap megnyitásához, ahol megtekintheti a TDS-t, ami ki lett számítva TSD-adóösszetevőnként az adott TDS-adókódhoz.

    Az **Áttekintés** lapon az **Adóösszetevő** mező a tranzakcióhoz használt TDS-adóösszetevőt mutatja. Az **Összeg** mező a TDS-adóösszetevőre számított TDS-összeget mutatja az alappénznemben. Az **Összesített összeg** mező az összes kiegyenlített tranzakció TDS-adóösszetevőjére kiszámított teljes TDS-összeget mutatja.

    Az **Összeg** lapon az **Alapértelmezett pénznem** szakaszban a TDS-adóösszetevőre számított TDS-összeg látható az alapértelmezett pénznemben. A **Másodlagos pénznem** szakasz a másodlagos pénznemben mutatja az összeget.

11. Zárja be az **Adóelőleg-összetevők** lapot.
12. A **Nyitott tranzakció szerkesztése** lapon, az **Összeg** mezőben figyelje meg, hogy az elszámolási időszakra vonatkozó TDS hatósági szállítójának kiegyenlítendő összeg frissült.
13. A különböző TDS-elszámolási időszakok TDS-tranzakcióinak a TDS-hatósági szállítója számára jelölje be a **Jelölés** jelölőnégyzetet a tranzakciókhoz.
14. Zárja be a **Nyitott tranzakció szerkesztése** lapot.

    > [!NOTE]
    > Ha csak néhány tranzakció van kiválasztva kiegyenlítéshez az **Adóelőleg-tranzakciók** oldalon, a kiválasztott tranzakciók teljes TDS-összege frissítve lesz a **Korrekció** mezőben a **Nyitott tranzakciók szerkesztése** oldalon. A helyesbítési összeg a **Napló bizonylat** oldalon található napló sorban frissül, és a **Nyitott tranzakció szerkesztése** lap bezárul.

    A **Naplóbizonylat** oldalán a **Terhelés** mező a TDS hatósági szállítónak fizetendő teljes összeget mutatja.

15. Adja meg az ellenszámla adatait.

    > [!NOTE]
    > Ha a TDS-tranzakciók Adószámla száma (TAN) eltérő, a naplósorok TAN-onként jönnek létre a **Naplóbizonylat** oldalon.

16. A **Kifizetési illeték** lapon, a **Díjazonosító** mezőben válasszon ki egy díjazonosítót, amelynek típusa **Kamat** vagy **Egyéb** a fizetési díj felszámításához a a késedelmes fizetésekhez, amelyek a TDS hatósági szállító felé történtek.

    Az **Adózási információk** lapon, a **Céginformációk** részben a **Név** mező a cég nevét mutatja. Az **Adóelőleg** szakaszban az **Adószámlaszám (TAN)** mező a tranzakciósorhoz csatolt TAN-t mutatja.

17. Ellenőrizze és adja fel a naplót.
18. Válassza az **Adóelőleg \> Challan-adatok** lehetőséget a tranzakció challan-adatainak megadásához.

    A **Bizonylat** mező A TDS-tranzakció bizonylatszámát jeleníti meg.
    
19. Jelölje be a **TDS letétbe helyezett könyvbejegyzés** jelölőnégyzetet, ha a TDS-összeg könyvbejegyzéssel van letétbe helyezve.
20. A **Challan-szám** mezőben adja meg azt a challan-számot, amelyet a fizetéshez használ a TDS-hatósági szállítónak.
21. Adja meg a challan-dátumot a **Dátum** mezőben.
22. A **Bank neve** mezőben válassza ki annak a banknak a nevét, amelybe a TDS hatósági szállítójának fizetendő TDS-összeget letétbe kell helyezni. Ez a mező felsorolja az összes bankszámlát, amelyet a TDS hatósági szállítóhoz állítottak be a **Kötelezettségek \> Összes szállító \> Beállítás \> Bankszámlák** helyen.
23. A **BSR-kód** mezőben adja meg a bank statisztikai alapvisszatérési (BSR) kódját.
24. Zárja be a lapot.

### <a name="example"></a>Példa

A 2009. 01. 04-i időszakot a **Bérleti díj** TDS komponenscsoport számára az időszakos TDS elszámolási folyamat segítségével rendezik. A 141 625,00 teljes TDS-összege a TDS-elszámolási időszakra a TDS szállítói hatósági számlájára kerül. Ezt az összeget a TDS-hatóság szállítójának **Nyitott tranzakciók szerkesztése** lapjának **Összeg** mezőjében tekintheti meg.

Ha az **Adóelőleg-tranzakciók** lehetőséget választja az adott időszakra kiegyenlített különböző TDS-tranzakciók megtekintéséhez, a következő információk jelennek meg.

| TDS összege |
|------------|
| 16,995.00  |
| 22,660.00  |
| 28,325.00  |
| 16,995.00  |
| 28,325.00  |
| 16,995.00  |
| 11,330.00  |

Az adott TDS-összeghez kiválaszthatja az **Adóelőleg-összetevők** lehetőséget az Adóelőleg-összetevők lap megnyitásához, ahol megtekintheti a TDS-t, ami ki lett számítva TSD-adóösszetevőnként az adott TDS-adókódhoz. Ebben a példában válassza az **Adóelőleg-összetevők** lehetőséget a 16 995,00 TDS-összeghez. Megjelenik a tranzakció komponensenként kiszámított adóösszege.

| Adóösszetevő | Összeg    | Halmozott összeg |
|---------------|-----------|--------------------|
| TDS           | 1,5000.00 | 125,000.00         |
| Pótdíj     | 1,500.00  | 12,500.00          |
| PE-Cess       | 330.00    | 2,750.00           |
| SHE Cess      | 165.00    | 1,375.00           |

Ha csak az **Adóelőleg-tranzakciók** oldalon az elszámoláshoz 16 995,00, 22 660,00, és 28 325,00 TDS-összegeket választotta ki, az elszámolás teljes összege **67 980,00** összeggel jelenik meg a **Nyitott tranzakciók szerkesztése** lap **Korrekció** mezőjében. Ha ez a tranzakció kiegyenlítésre van ki jelölve, és a **Nyitott tranzakciók szerkesztése** lap lezárul, a **67 980,00** összeg megjelenik a **Napló bizonylat** oldalon a **Terhelés** mezőben.

Most már tegye a naplót, és generálja a TDS-challant.

### <a name="adjustment-of-advance-payments-that-are-made-to-tds-authority-vendors"></a>A TDS-hatóság szállítóinak teljesített előlegek kiigazítása

A TDS-hatóság szállítójának nyújtott előleg tényleges kifizetéshez való igazításához lépjen a **Kötelezettségek \> Szállítók \> Összes szállító \> Tranzakció szerkesztése** mezőbe. Ha a ténylegesen végrehajtott kifizetés meghaladja az előleget, két challan-szám jön létre a tranzakcióhoz. A TDS-lekérdezésen azonban csak az első challan-szám szerepel.
