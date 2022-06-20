---
title: Érkezések és küldemények feladása az Intrastat számára
description: Ez a cikk az Intrastat érkezések és elküldések feladását mutatja be.
author: anasyash
ms.date: 8/23/2021
ms.topic: article
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: anasyash
ms.search.validFrom: ''
ms.openlocfilehash: aef20f0261e103be7fe231a7efb39751ab4d1151
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8862964"
---
# <a name="post-arrivals-and-dispatches-for-intrastat"></a>Érkezések és küldemények feladása az Intrastat számára

[!include [banner](../includes/banner.md)]

Ez a cikk az Intrastat érkezések és elküldések feladását mutatja be. A példa az **ITCO** jogi személyt használja.

## <a name="setup"></a>Beállítás

1. Importálja a következő elektronikus jelentéstételi (ER) konfigurációk legújabb verzióját:

    - Intrastat modell
    - Intrastat jelentés
    - Intrastat (IT)

    További részleteket a [Konfigurációs szolgáltatás globális adattárából ER konfigurációk letöltése](../../fin-ops-core/dev-itpro/analytics/er-download-configurations-global-repo.md) című részben talál.

2. A Microsoft Dynamics 365 Pénzügyben folyamatosként adja meg a következő számsorozatokat: **Szon\_ 397**, **A illetve\_ 16403**, **Var\_ 407** és **PUR\_ EU**.

    1. Menjen a **Szervezeti adminisztráció** > **Számsorozatok** > **Számsorozatok** pontra.
    2. Válassza ki a táblázatból a számsorozat kódok egyikét.
    3. A műveleti ablaktáblán válassza a **Szerkesztés** lehetőséget.
    4. Az **Általános** gyorslapon, a **Beállítás** szakaszban a **Folyamatos** opciót állítsa **Igenre**.
    5. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.

3. Raktárcím beállítása.

    1. Ugorjon a **Raktárkezelés** &gt; **Beállítás** &gt; **Raktár** &gt; **Raktárak** pontra.
    2. A listában válassza ki a **11-es** raktárat.
    3. A **Cím** gyorslapon válassza a **Hozzáadás** lehetőséget.
    4. Az **Új** **cím** párbeszédpanel **Név** **vagy** **Leírás** mezőjébe írja be a **Fő** szót.
    5. Az **Ország/régió** mezőben válassza az **ITA (Olaszország)** lehetőséget.
    6. A **Város** mezőben válassza az **Aprilia-t**.
    7. Válassza ki az **OK** lehetőséget.

4. Tranzakciós kódok beállítása.

    1. Ugorjon a következőre: **Adó** > **Beállítás** > **Külkereskedelem** > **Tranzakciókódok**.
    2. Válassza az **Új** lehetőséget és állítson be egy tranzakciós kódot a tulajdonátruházásokhoz.

        - A **Tranzakciókód** mezőbe adja meg a **1** értéket.
        - A **Név** mezőbe írja be a **Tulajdonátruházás** mezőt.

    3. Válassza az **Új** lehetőséget és állítson be egy tranzakciós kódot a visszatérítésekhez.

        - A **Tranzakció** **kód** mezőbe írjon be **2**-et.
        - A **Név** mezőbe írja be az **Áruvisszaküldés** értéket.

5.  Külkereskedelmi paraméterek beállítása.

    1. Ugorjon a következőre: **Adó** > **Beállítások** > **Külkereskedelem** > **Külkereskedelmi paraméterek**.
    2. Az **Intrastat** lapon az **Általános** gyorslapon a **Tranzakció** **kód** mezőben válassza a **1**-et.
    3. A **Jóváírási megjegyzés** mezőben válassza a **2**-et.
    4. Az **Értékesítési jelentési időszak** mezőben válassza a **hónapot**.
    5. A **Beszerzési jelentési időszak** mezőben válassza a **Hónapot**.
    6. Az **Elektronikus jelentéstétel** gyorslapon a **Fájlformátum-társítás** mezőben válassza az **Intrastat (IT)** lehetőséget.
    7. A **Jelentési formátum hozzárendelése** mezőben válassza az **Intrastat-jelentést**.
    8. Az **Árucsoport-hierarchia** gyorslapon a **Kategória-hierarchia** mezőben válassza az **Intrastat** lehetőséget.
    9. A **Statisztikai értékek** gyorslapon állítsa a **Statisztikai adatok nyomtatása és exportálása** opciót **Igenre**.
    10. Az **Ország/régió tulajdonságai** lapon ellenőrizze, hogy a következő sorok léteznek-e.

        | **Fél/ország/régió** | **Intrastat-kód** | **Pénznem** | **Ország/régió típusa** |
        |--------------------------|--------------------|--------------|-------------------------|
        | ITA                      | IT                 | EUR          | Belföldi                |
        | SMR                      | SM                 | EUR          | Speciális belföldi        |

    11. Az eszköztáron válassza az **Új** lehetőséget a következő sor létrehozásához.

        | **Fél/ország/régió** | **Intrastat-kód** | **Pénznem** | **Ország/régió típusa** |
        |--------------------------|--------------------|--------------|-------------------------|
        | DNK                      | DK                 | DKK          | EU                      |

6. Adómentességi számok beállítása.

    1. Menjen az **Adó** > **Beállítás** > **Értékesítési adó** > **Adómentes számok** pontra.
    2. A Műveletpanelen válassza az **Új** lehetőséget a következő sorok létrehozásához.

        | **Ország/régió** | **Adómentességi szám** | **Vállalat neve** |
        |--------------------|-----------------------|------------------|
        | DEU                | DE3456789012          | UE SZÁLLÍTÓ        |
        | DNK                | DK0987654321          | Ügyfél ER      |

7. Állítsa be a szállító címét.

    1. Nyissa meg a következőt: **Kötelezettségek** &gt; **Szállítók** &gt; **Minden szállító**.
    2. A rácson válassza ki az **UE Beszállító** elemet.
    3. A **Címek** gyorslapon válassza a **Hozzáadás** lehetőséget.
    4. Az **Új cím** párbeszédpanelen a **Név vagy leírás** mezőbe írja be a **Németország** szót.
    5. Az **Ország/régió** mezőben válassza a **DEU** lehetőséget.
    6. Válassza az **OK** lehetőséget az új cím létrehozásához.
    7. A **Számla és szállítás** gyorslapon, a **Forgalmi adó** szakaszban, az **Adómentes szám** mezőben jelölje be a **Mind**, majd válassza ki a **DE1234567890** lehetőséget.
    8. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.

8. Állítsa be az ügyfelek címeit.

    1. Menjen a **Követelések** > **Ügyfelek** > **Minden ügyfél** pontra.
    2. Válassza ki a rácson az **ITCO-000001-et**.
    3. A **Címek** gyorslapon válassza a **Szerkesztés** lehetőséget.
    4. Az **Új cím** párbeszédpanelen a **Név vagy leírás** mezőbe írja be a **San Marino** nevet.
    5. Az **Ország/régió** mezőben válassza a **SMR** lehetőséget.
    6. Válassza az **OK** lehetőséget az új cím létrehozásához.
    7. A **Számla és szállítás** gyorslapon, a **Számla** szakaszban, a **Számlaszám** mezőben válassza az **ITCO-000001-et**.
    8. A **Számsorozat csoport** mezőben válassza az **IT\_VENDOM** lehetőséget.
    9. A művelet panelen válassza a **Mentés** elemet, majd zárja be a lapot.
    10. A **Minden ügyfél** oldalon a rácson válassza ki az **ITCO-000002-t**.
    11. A **Címek** gyorslapon válassza a **Hozzáadás** lehetőséget.
    12. Az **Új cím** párbeszédpanelen a **Név vagy leírás** mezőbe írja be a **Dánia** szót.
    13. Az **Ország/régió** mezőben válassza a **DNK** lehetőséget.
    14. Válassza az **OK** lehetőséget az új cím létrehozásához.
    15. Az **Értékesítési demográfiák** gyorslapon a **Pénznem** mezőben válassza a **DKK-t**.
    16. A **Számla és szállítás** gyorslapon, a **Forgalmi adó** szakaszban, a **Forgalmi adó csoport** mezőben válassza az **IT\_PUREU** lehetőséget.
    17. Az **Adómentességi szám** mezőben válassza az **Összes**, majd a **DK0987654321** jelölőnégyzetet.
    18. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.

9. Állítsa be a kategóriahierarchiát.

    1. Menjen a **Termékinformációk kezelése** > **Beállítás** > **Kategóriák és attribútumok** > **Kategóriahierarchiák** pontra.
    2. Válassza ki az **Intrastat** lehetőséget a rácsban.
    3. A Művelet panelen kattintson az **Új kategória-csomópont** elemre.
    4. A **Név** mezőbe írja be a **Szerviz** szót.
    5. A **Kód** mezőbe írja be az **123456-ot**.
    6. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.

10. Termékek beállítása.

    1. Menjen a **Termékinformációk kezelése** > **Termékek** > **Kiadott termékek** pontra.
    2. Válassza ki a rácson a **ITEM**-et.
    3. A **Beszerzés** gyorslapon, az **Adminisztráció** szakaszban, a **Szállító** mezőben válassza ki az **ITCO-000001-et**.
    4. A **Külkereskedelem** gyorslapon az **Intrastat** szakaszban, az **Árucikk** mezőben válassza a **\[100 200 30\] Hangszóró** elemet.
    5. A **Származás** szakaszban az **Ország/régió** mezőben válassza a **DEU** beállítást.
    6. Az **Állam/tartomány** mezőben válassza a **BE-t**.
    7. A **Készlet kezelése** gyorslapon, a **Nettó mérések** szakaszban, a **Nettó súly** mezőbe írja be az **5** értéket.
    8. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.
    9. A **Felszabadított termékek** oldalon a rácson válassza ki a **Szolgáltatáselemet**.
    10. A **Külkereskedelem** gyorslapon az **Intrastat** szakaszban, az **Áru** mezőben válassza a **\[123456\] Szolgáltatás** lehetőséget.
    11. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.

11. Állítsa be a szállítási módokat.

    1. Menjen az **Adó** > **Beállítás** > **Külkereskedelem** > **Szállítási mód** pontra.
    2. A Műveletpanelen válassza az **Új** lehetőséget a következő szállítási módok létrehozásához.

        | **Átvitel** | **Leírás** |
        |---------------|-----------------|
        | 1             | Közút            |
        | 2             | Légi             |

12. Állítson be egy kiszállítási módot.

    1. Ugorjon a következőre: **Beszerzés és forrás** > **Beállítás** > **Forgalmazás** > **Szállítási módok**.
    2. A Műveleti ablaktáblán kattintson az **Új** elemre.
    3. A **Kiszállítási mód** mezőbe írja be az **1-es** értéket.
    4. A **Leírás** mezőbe írja be a **Teherautó** szót.
    5. A **Külkereskedelmi** gyorslapon a **Szállítás** mezőben válassza az **1 Közút** lehetőséget.
    6. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.

13. A szállítási feltételek meghatározása.

    1. Lépjen a **Fizetendő számlák** > **Beállítás** > **Szállítási feltételek** pontra.
    2. A listában válassza ki a **CFR-t**.
    3. Az **Általános** gyorslapon az **Intrastat kód** mezőbe írja be az **1** értéket.

## <a name="post-arrivals-for-intrastat"></a>Érkezések feladása az Intrastat számára

### <a name="purchase-goods-by-using-a-purchase-order"></a>Áruk beszerzése megrendeléssel

A példa ezen része azt mutatja be, hogyan használhat egy megrendelést az Európai Unió (EU) országaiból származó áruk (tételek) beszerzésére.

1. Menjen a **Fizetendő számlák** > **Beszerzési megbízások** > **Minden beszerzési megbízás** menüpontba.
2.  A Műveleti ablaktáblán kattintson az **Új** elemre.
3.  A **Megrendelés létrehozása** párbeszédpanelen a **Szállítói számla** mezőben válassza az **UE Szállítót**.
4.  Az **Adminisztráció** gyorslapon válassza ki **a** **Nyelv** mezőt.
5.  Válassza ki az **OK** lehetőséget.
6.  A **Fejléc** nézetben, a **Kül** **kereskedelmi** gyorslapon ellenőrizze, hogy a **Tranzakciókód** mező értéke **1**-e.
7.  Ellenőrizze, hogy a **Származási/célállomás megyéje** mezőben **RM** van-e beállítva.
8.  A **Kézbesítés** gyorslap **Kézbesítés** szakaszában a **Kézbesítési mód** mezőben válassza az **1.** lehetőséget.
9.  A **Szállítási feltételek** mezőben válassza a **CFR** lehetőséget.
10. A **Sorok** nézetben, a **Beszerzési rendelés sorai** gyorslapon a **Tételszám** mezőben válassza a **Tétel** lehetőséget.
11. A **Site** mezőben válasszon ki a **1** értéket.
12. A **Raktár** mezőben válassza ki az **11** értéket.
13. Írja be a **10** értéket a **Mennyiség** mezőbe.
14. Írjon be **100** értéket az **Egységár** mezőbe.
15. A **Beállítás** lapon, a **Forgalmi adó** szakaszban, a **Tétel forgalmi adó csoport** mezőben válassza a **22%EU** értéket.
16. A Műveletpanelen, a **Vásárlás** lapon, a **Műveletek** csoportban válassza a **Megerősítés** lehetőséget.
17. A Műveleti ablaktábla **Számla** lapján a **Létrehozás** csoportban válassza a **Számla** lehetőséget.
18. A Műveletpanelen válassza az **Alapértelmezettet**.
19. A **Sorok alapértelmezett mennyisége** mezőben válassza a **Megrendelt mennyiséget**, majd az **OK**-t.
20. A **Szállítói számla fejléc** gyorslap, a **Számla azonosítása** szakaszában a **Szám** mezőbe írja be a **0001-es** számot.
21. A **Számlák dátuma** szakasz **Számla dátuma** mezőben válassza a **7/9/2021** lehetőséget.
22. A Művelet ablaktáblán válassza a **Feladás** lehetőséget a számla könyveléséhez.

### <a name="purchase-services-by-using-a-vendor-invoice"></a>Szolgáltatások beszerzése szállítói számla használatával

A példa ezen része azt mutatja be, hogy hogyan lehet szállítói számlát használni uniós országokból származó szolgáltatások vásárlására.

1. Lépjen a **Fizetendő számlák** > **Számlák** > **Számlák naplója** menüpontba.
2. A Műveleti ablaktáblán kattintson az **Új** elemre.
3. A **Név** mezőben válassza a **VEND\_EUINV** lehetőséget.
4. A Műveleti ablaktáblán válassza a **Sorok** elemet.
5. A **Dátum** mezőbe írja be a **7/9/2021** dátumot.
6. A **Számlatípus** mezőben válassza a **Szállítót**.
7. A **Számla** mezőben válassza az **UE Szállító** lehetőséget.
8. A **Számla dátuma** mezőben válassza a **7/9/2021** lehetőséget.
9. A **Számla** mezőbe írja be az **ITA-0004** kódot.
10. A **Hitel** mezőbe írja be a **120000** számot.
11. Az **Offset számla** **típusa** mezőben válassza a **Főkönyvi könyvelést**.
12. Az **Offset számla** mezőben válassza a **110130** számot.
13. Az **Értékesítési adó csoportmezőben** válassza az **IT\_PUREU** lehetőséget.
14. A **Tétel forgalmi adó csoportmezőben** válassza a **22%EU** értéket.
15. A **Külkereskedelem** lapon kövesse az alábbi lépéseket:

    1. A **Tranzakció kódja** mezőben válassza az **1** értéket.
    2. A **Szállítás** mezőben válassza a **2 légi** lehetőséget.
    3. Az **Árumezőben** válassza a **\[123456\] Szolgáltatás** lehetőséget.
    4. Az **Ország/régió** mezőben válassza a **ITA** lehetőséget.
    5. Az **Állam/tartomány** mezőben válassza a **LAZ** lehetőséget.
    6. A **Származási/célállomás megyéje** mezőben válassza az **LT** lehetőséget.


16. A műveleti ablaktáblán válassza ki a **Feladás** elemet.
17. Intrastat-nyilatkozat létrehozása az érkezésekhez.

    1. Ugorjon a következőre: **Adó** > **Nyilatkozatok** > **Külkereskedelem** > **Intrastat**.
    2. A Műveletpanelen válassza az **Átvitel** lehetőséget.
    3. Az **Intrastat (Átvitel)** párbeszédpanelen állítsa a **Szállítói számla** opciót **Igenre**.
    4. Válassza az **OK** lehetőséget a tranzakciók átviteléhez, majd tekintse át az Intrastat naplót.

   ![Intrastat napló oldal, Áttekintés fül.](media/ita_intrastat_journal_vendor_invoice.png)

18. Tekintse át a beszerzési rendelés **Általános** lapját.

    ![Intrastat naplósor adatai a beszerzési rendeléshez](media/ita_intrastat_journal_purchase_order_line_details.png)

19. Tekintse át a szállítói számla **Általános** lapját.

    ![Intrastat naplósor adatai a szállítói számlához](media/ita_intrastat_journal_vendor_invoice_line_details.png)

20. Intrastat-jelentés készítése az érkezésekről.

    1. A Műveletpanelen válassza a **Kimenet** > **Jelentés** lehetőséget.
    2. Az **Intrastat jelentés** párbeszédpanelen a **Dátum** szakaszban, a **Dátumtól** mezőben válassza a **2021.1.7.** dátumot.
    3. A **Dátum** mezőben válassza a **7/31/2021** lehetőséget.
    4. Az **Exportálási beállítások** szakaszban állítsa a **Fájl létrehozása** és a **Jelentés létrehozása** beállításokat **Igen**-re.
    5. A **Fájlnév** mezőbe írja be az **Érkezési fájl** értéket.
    6. A **Jelentés fájlnév** mezőbe írja be az **Érkezési jelentés** értéket.
    7. Az **Irány** mezőben válassza az **Érkezések** lehetőséget.
    8. A **Hivatkozási szám** mezőbe írja be az **123456** számot.
    9. Válassza az **OK** gombot az Intrastat-jelentés és az Intrastat-fájl létrehozásához, majd tekintse át azokat.

    Az alábbi ábra egy példát mutat egy Intrastat-jelentésre.

    ![Intrastat érkezési jelentés.](media/ita_intrastat_arrivals_report.png)

    Az alábbi ábra egy Intrastat-fájl példáját mutatja.

    ![Intrastat érkezési fájl.](media/ita_intrastat_arrivals_file.png)

## <a name="post-dispatches-for-intrastat"></a>Küldések feladása az Intrastat számára

### <a name="sell-goods-by-using-a-sales-order"></a>Áruk értékesítése értékesítési megrendeléssel

A példa ezen része azt mutatja be, hogyan használhat egy értékesítési megbízást az Európai Unió (EU) országaiba történő árueladásra.

1. Ugorjon a következőre: **Követelések** > **Rendelések** > **Minden értékesítési rendelés**.
2. A Műveleti ablaktáblán kattintson az **Új** elemre.
3. Az **Értékesítési megbízás létrehozása** párbeszédpanelen a **Vevői számla** mezőben válassza az **ITCO-000002** lehetőséget.
4. Válassza ki az **OK** lehetőséget.
5. A **Fejléc** nézetben, a **Kézbesítés** gyorslapon, az **Egyéb szállítási információk** szakaszban, a **Kézbesítési mód** mezőben válassza az **1 tehergépkocsi** lehetőséget.
6. A **Szállítási feltételek** mezőben válassza a **CFR** lehetőséget.
7. A **Sorok** nézetben, az **Értékesítési megbízás sorai** gyorslapon a **Tételszám** mezőben válassza a **TÉTEL** lehetőséget.
8. Írja be a **50** értéket a **Mennyiség** mezőbe.
9. A **Site** mezőben válasszon ki a **1** értéket.
10. A **Raktár** mezőben válassza ki az **11** értéket.
11. Írjon be **250** értéket az **Egységár** mezőbe.
12. A **Sor részletek** gyorslapon, a **Beállítás** lapon, a **Értékesítési adó** szakaszban, a **Tétel áfacsoportja** mezőben válassza a **22%EU** értéket.
13. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.
14. A Műveletpanelen, a **Számla** lapon, a **Létrehozás** csoportban válassza a **Számla** lehetőséget a megrendeléshez tartozó számla létrehozásához.
15. A **Könyvelési számla** párbeszédpanelben a **Paraméterek** gyorslapon a **Paraméterek** szakaszban a **Mennyiség** mezőben válassza az **Összes** lehetőséget.
16. A **Beállítás** gyorslap a **Számla** **dátuma** mezőben válassza a **7/9/2021** lehetőséget.
17. Válassza ki az **OK** lehetőséget.
18. Tekintse át az Intrastat napló sorait.

    1. Ugorjon a következőre: **Adó** > **Nyilatkozatok** > **Külkereskedelem** > **Intrastat**.
    2. A Műveletpanelen válassza az **Átvitel** lehetőséget.
    3. Az **Intrastat (Átvitel)** párbeszédpanelen állítsa az **Ügyfélszámla** opciót **Igenre**.
    4. Válassza az **OK** lehetőséget a tranzakciók átviteléhez, és tekintse át az Intrastat naplót. A jóváírási tranzakció korrekcióként van megjelölve, és negatív számlaösszeggel rendelkezik.

        ![Intrastat napló oldal](media/ita_intrastat_journal_sales_order.png)

        ![Intrastat naplósor részletei az értékesítési rendeléshez](media/ita_intrastat_journal_sales_order_line_details.png)

### <a name="return-goods-by-using-a-credit-note"></a>Az áruk visszaküldése jóváírással

A példa ezen része azt mutatja be, hogyan használhat jóváírást az Európai Unió (EU) országaiból származó áruk (tételek) visszaküldéséhez.

1. Ugorjon a következőre: **Követelések** > **Rendelések** > **Minden értékesítési rendelés**.
2. A Műveleti ablaktáblán kattintson az **Új** elemre.
3. Az **Értékesítési megbízás létrehozása** párbeszédpanelen a **Vevői számla** mezőben válassza az **ITCO-000002** lehetőséget.
4. Válassza ki az **OK** lehetőséget.
5. A **Fejléc** nézetben, a **Kézbesítés** gyorslapon, az **Egyéb szállítási információk** szakaszban, a **Kézbesítési mód** mezőben válassza az **1 tehergépkocsi** lehetőséget.
6. A **Szállítási feltételek** mezőben válassza a **CFR** lehetőséget.
7. A **Külkereskedelmi** gyorsfájlok lapon a **Tranzakciók kódja** mezőben válassza a **2** értéket.
8. A **Sorok** lapon, az **Értékesítési megbízás sorai** gyorslapon a **Tételszám** mezőben válassza a **TÉTEL** lehetőséget.
9. A **Mennyiség** mezőbe írja be a **-10** értéket.
10. A **Site** mezőben válasszon ki a **1** értéket.
11. A **Raktár** mezőben válassza ki az **11** értéket.
12. Írjon be **250** értéket az **Egységár** mezőbe.
13. A **Sor részletek** gyorslapon, a **Beállítás** lapon, a **Értékesítési adó** szakaszban, a **Tétel áfacsoportja** mezőben válassza a **22%EU** értéket.
14. A **Visszaküldött rendelés** szakaszban a **Visszatérő tétel azonosítója** mezőben válassza ki a korábban létrehozott tételt.
15. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.
16. A Műveletpanelen, a **Számla** lapon, a **Létrehozás** csoportban válassza a **Számla** lehetőséget a megrendeléshez tartozó számla létrehozásához.
17. A **Paraméterek** gyorslapon a **Paraméterek** szakaszban a **Mennyiség** mezőben válassza az **Összes** lehetőséget.
18. A **Számla könyvelése** párbeszédpanelen, a **Beállítás** gyorslapon a **Számla** **dátuma** mezőben válassza a **2021.9.7.** lehetőséget.
19. A számla könyveléséhez válassza az **OK** lehetőséget.
20. Tekintse át az Intrastat napló sorait.

    1. Ugorjon a következőre: **Adó** > **Nyilatkozatok** > **Külkereskedelem** > **Intrastat**.
    2. A Műveletpanelen válassza az **Átvitel** lehetőséget.
    3. Az **Intrastat (Átvitel)** párbeszédpanelen állítsa az **Ügyfélszámla** opciót **Igenre**.
    4. Válassza az **OK** lehetőséget a tranzakciók átviteléhez, és tekintse át az Intrastat naplót. A jóváírási tranzakció korrekcióként van megjelölve, és negatív számlaösszeggel rendelkezik.

    ![Intrastat napló jóváírás](media/ita_intrastat_journal_credit_note.png)

    ![Intrastat naplósor adatai a jóváíráshoz](media/ita_intrastat_journal_credit_note_line_details.png)

### <a name="sell-goods-to-san-marino-by-using-a-sales-order"></a>Áruk értékesítése San Marinóba értékesítési megbízás segítségével

A példa ezen része azt mutatja be, hogyan használjon értékesítési megbízást áruk (tételek) San Marinóba történő beszerzésére.

1. Ugorjon a következőre: **Követelések** > **Rendelések** > **Minden értékesítési rendelés**.
2. A Műveleti ablaktáblán kattintson az **Új** elemre.
3. Az **Értékesítési megbízás létrehozása** párbeszédpanelen a **Vevői számla** mezőben válassza az **ITCO-000001-et**.
4. Válassza ki az **OK** lehetőséget.
5. A **Fejléc** nézetben, a **Kézbesítés** gyorslapon, az **Egyéb kézbesítési információk** szakaszban, a **Kézbesítési mód** mezőben válassza az **1** lehetőséget.
6. A **Szállítási feltételek** mezőben válassza a **CFR** lehetőséget.
7. A **Sorok** lapon, az **Értékesítési megbízás sorai** gyorslapon a **Tételszám** mezőben válassza a **TÉTEL** lehetőséget.
8. Írja be a **30** értéket a **Mennyiség** mezőbe.
9. A **Site** mezőben válasszon ki a **1** értéket.
10. A **Raktár** mezőben válassza ki az **11** értéket.
11. Írjon be **200** értéket az **Egységár** mezőbe.
12. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.
13. A Műveletpanelen, a **Számla** lapon, a **Létrehozás** csoportban válassza a **Számla** lehetőséget a megrendeléshez tartozó számla létrehozásához.
14. A **Paraméterek** gyorslapon a **Paraméterek** szakaszban a **Mennyiség** mezőben válassza az **Összes** lehetőséget.
15. A **Számla könyvelése** párbeszédpanelen, a **Beállítás** gyorslapon a **Számla** **dátuma** mezőben válassza a **2021.9.7.** lehetőséget.
16. A számla könyveléséhez válassza az **OK** lehetőséget.
17. Tekintse át az Intrastat napló sorait.

    1. Ugorjon a következőre: **Adó** > **Nyilatkozatok** > **Külkereskedelem** > **Intrastat**.
    2. A Műveletpanelen válassza az **Átvitel** lehetőséget.
    3. Az **Intrastat (Átvitel)** párbeszédpanelen állítsa az **Ügyfélszámla** opciót **Igenre**.
    4. Válassza az **OK** lehetőséget a tranzakciók átviteléhez, és tekintse át az Intrastat naplót.

   ![Intrastat napló San Marino számára](media/ita_intrastat_journal_sales_order_san_marino.png)

   ![Intrastat naplósorok részletei San Marino esetében](media/ita_intrastat_journal_sales_order_san_marino_line_details.png)

18. Intrastat nyilatkozat létrehozása a küldeményekhez.

    1. Ugorjon az **Adó** &gt; **Nyilatkozatok** &gt; **Külkereskedelem** &gt; **Intrastat** pontra.
    2. A műveleti ablaktáblán válassza a **Kimenet** &gt; **Jelentés** lehetőséget.
    3. Az **Intrastat jelentés** párbeszédpanelen a **Dátum** szakaszban, a **Dátumtól** mezőben válassza a **2021.1.7.** dátumot.
    4. A **Dátum** mezőben válassza a **7/31/2021** lehetőséget.
    5. Az **Exportálási beállítások** szakaszban állítsa a **Fájl létrehozása** és a **Jelentés létrehozása** beállításokat **Igen**-re.
    6. A **Fájlnév** mezőbe írja be a **Küldeményfájl** szót.
    7. A **Jelentés fájlnév** mezőbe írja be az **Küldési jelentés** értéket.
    8. Az **Irány** mezőben válassza a **Küldemények** lehetőséget.
    9. A **Hivatkozási szám** mezőbe írja be a **98754**-et.
    10. Válassza az **OK** lehetőséget az Intrastat-jelentés és az Intrastat-fájl létrehozásához.

        Az alábbi ábra egy példát mutat egy nyomtatott Intrastat-jelentésről.

        ![Intrastat jelentés](media/ita_intrastat_report_for_dispatches.png)

        A következő ábra egy nyomtatott Intrastat-fájl példáját mutatja.

        ![Intrastat fájl a küldeményekhez](media/ita_intrastat_file_for_dispatches.png)
