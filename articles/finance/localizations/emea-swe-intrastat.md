---
title: Svéd Intrastat
description: Ez a téma a svédországi Intrastat jelentéssel kapcsolatos információkat tartalmazza.
author: andosip
ms.date: 8/24/2021
ms.topic: article
audience: Application User
ms.reviewer: kfender
ms.search.region: Global
ms.author: v-aosipov
ms.search.validFrom: ''
ms.openlocfilehash: 404fb8dff1519aefb2f4af25eb95dfa6fce75b7c
ms.sourcegitcommit: 259ba130450d8a6d93a65685c22c7eb411982c92
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/24/2021
ms.locfileid: "7417082"
---
# <a name="swedish-intrastat"></a>Svéd Intrastat

[!include[banner](../includes/banner.md)]

Az **Intrastat** oldalon információkat generálhat és jelenthet az Európai Unió országaival folytatott kereskedelemről. A svéd Intrastat-nyilatkozat tartalmazza az áruforgalomra vonatkozó információkat a jelentéstételhez.

A svéd Intrastat-nyilatkozat a következő mezőket tartalmazza:

   - Partnerország ISO-kódja
   - Tranzakció kódja
   - Vámtarifakód
   - Másodlagos egység
   - Betűvastagság
   - Számlaösszeg

## <a name="set-up-intrastat"></a>Intrastat beállítása

Importálja a következő elektronikus jelentéstételi (ER) konfigurációk legújabb verzióját:

   - Intrastat modell
   - Intrastat jelentés
   - Intrastat (SE)

További információért lásd: [ER-konfigurációk letöltése a Konfigurációs szolgáltatás globális tárolójából](../../fin-ops-core/dev-itpro/analytics/er-download-configurations-global-repo.md).

## <a name="set-up-foreign-trade-parameters"></a>Külkereskedelmi paraméterek beállítása

1. A Microsoft Dynamics 365 Finance oldalon az **Adó** > **Beállítás** > **Külkereskedelmi paraméterek** menüpontra lépjen.
2. Az **Intrastat** lapon az **Elektronikus jelentéstétel** gyorslapon a **Fájlformátum leképezése** mezőben válassza az **Intrastat (SE)** lehetőséget.
3. A **Jelentésformátum-hozzárendelés** mezőben válassza az **Intrastat jelentés** lehetőséget.
4. Az **Árucikk-kódok hierarchiája** gyorslapon a **Kategóriahierarchia** mezőben válassza az **Intrastat** lehetőséget.
5. A **Tranzakciókód** mezőben válassza ki a vagyonátruházáshoz létrehozott tranzakciókódot. Ezt a kódot olyan tranzakciókra használja, amelyek tényleges vagy tervezett tulajdonátruházást eredményeznek (pénzügyi vagy egyéb) ellenszolgáltatás ellenében. Javításra is használható. A svédországi vállalatok egyjegyű tranzakciós kódokat használnak.
6. A **Jóváírási megjegyzés** mezőben válassza ki az áruk visszaküldésének tranzakciós kódját. Ezt a kódot az eredetileg a tranzakció kódja alatt rögzített áruk visszaküldésére használja a tranzakciót követően. A svédországi vállalatok egyjegyű tranzakciós kódokat használnak.
7. Az **Ország/régió tulajdonságai** lapon az **Ország/régió** mezőben sorolja fel azokat az országokat vagy régiókat, amelyekkel a vállalata üzleti kapcsolatban áll. Minden olyan ország esetében, amely az EU része, az **Ország/régió típusa** mezőben válassza az **EU-t**, hogy az ország megjelenjen az Intrastat-jelentésben.

## <a name="set-up-the-product-parameters-for-the-intrastat-declaration"></a>Az Intrastat-nyilatkozat termékparamétereinek beállítása

1. Ugorjon a következőre: **Termékinformáció-kezelés** > **Termékek** > **Felszabadított termékek**.
2. A rácsban válasszon egy terméket.
3. A **Külkereskedelmi** gyorslapon az **Intrastat** szakaszban az **Áru** mezőben válassza ki az árukódot.
4. A **Készlet kezelése** gyorslapon a **Nettó súly** mezőben adja meg a termék súlyát kilogrammban.
5. Válassza az **Adó** > **Beállítások** > **Külkereskedelem** > **Intrastat tömörítése** menüpontot, és válassza ki azokat a mezőket, amelyeket össze kell hasonlítani az Intrastat-adatok összesítése során. A svéd Intrastat esetében válassza ki a következő mezőket:

    - Árucikk
    - Tranzakció kódja
    - Irány
    - Ország/régió
    - Korrekció
    - Számla

## <a name="intrastat-transfer"></a>Intrastat-átvitel

Az **Intrastat** oldalon a műveleti panelen az **Átvitel** gombra kattintva automatikusan át lehet vinni az közösségen belüli kereskedelemre vonatkozó adatokat az értékesítési rendelésekből, a szabadszöveges számlákból, a beszerzési rendelésekből, a szállítói számlákból, a szállítói termékbevételezésekből, a projektszámlákból és az átátviteli rendelésekből. Csak azok a dokumentumok kerülnek átvitelre, amelyek célországa vagy -régiója (kiküldésekhez) vagy feladója (beérkezésekhez) egy EU-s ország.

Másik lehetőségként manuálisan is beírhatja a tranzakciókat az **Új** gombra kattintva a Műveletei panelen.

### <a name="generate-an-intrastat-report"></a>Intrastat jelentés készítése

1. Ugorjon a következőre: **Adó** > **Nyilatkozatok** > **Külkereskedelem** > **Intrastat**.
2. A Műveletpanelen válassza a **Kimenet** > **Jelentés** lehetőséget.
3. Az **Intrastat jelentés** párbeszédpanelen a következő mezőket állítsa be.

    | Mező            | Leírás                                                                                                                         |
    |------------------|-------------------------------------------------------------------------------------------------------------------------------------|
    | Kezdő dátum        | Válassza ki a jelentés kezdő dátumát.                                                                                               |
    | Záró dátum          | Válassza ki a jelentés befejező dátumát.                                                                                                 |
    | Fájl létrehozása    | Állítsa ezt az opciót **Igenre**, ha .txt fájlt szeretne generálni az Intrastat jelentéshez.                                                       |
    | Fájlnév        | Adja meg a .txt fájl nevét.                                                                                                    |
    | Jelentés létrehozása  | Állítsa ezt az opciót **Igenre**, ha .xlsx fájlt szeretne generálni az Intrastat jelentéshez.                                                     |
    | Jelentésfájl neve | Adja meg az .xlsx fájl nevét.                                                                                                   |
    | Irány        | Válassza a **Beérkezések** lehetőséget a közösségen belüli beérkezésekkel kapcsolatos jelentésekhez. A közösségen belüli kiküldésekről szóló jelentéshez válassza a **Kiküldések** lehetőséget. |

4. Válassza az **OK** lehetőséget, és tekintse át a generált jelentéseket.

## <a name="example"></a>Példa

Ez a példa azt mutatja be, hogyan kell az Intrastat érkezéseket és elküldéseket feladni. A **DEMF** jogi személyt használja.

### <a name="preliminary-setup"></a>Előzetes beállítás

1. Lépjen a **Szervezeti adminisztráció** > **Szervezet** > **Jogi személyek** menüpontba, és válassza ki a **DEMF** jogi személyt.
2. A **Címek** gyorslapon válassza a **Szerkesztés** lehetőséget, majd az **Ország/régió** mezőben válassza a **SWE (Svédország**) lehetőséget.
3. Importálja a következő ER-konfigurációk legújabb verzióját:

    - Intrastat modell
    - Intrastat jelentés
    - Intrastat (SE)

### <a name="create-transaction-codes"></a>Tranzakciós kódok létrehozása

1. Ugorjon a következőre: **Adó** > **Beállítás** > **Külkereskedelem** > **Tranzakciókódok**.
2. A Műveleti ablaktáblán kattintson az **Új** elemre.
3. A **Tranzakció** **kód** mezőbe írjon be **1**-et.
4. A **Név** mezőbe írja be a **Normál tranzakciókat**.
5. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.

### <a name="set-up-foreign-trade-parameters"></a>Külkereskedelmi paraméterek beállítása

1. Ugorjon a következőre: **Adó** > **Beállítások** > **Külkereskedelem** > **Külkereskedelmi paraméterek**.
2. Az **Intrastat** lapon az **Általános** gyorslapon a **Tranzakció** **kód** mezőben válassza a **1**-et.
3. Az **Elektronikus jelentéstétel** gyorslapon a **Fájlformátum-társítás** mezőben válassza az **Intrastat (SE)** lehetőséget.
4. A **Jelentésformátum hozzárendelése** mezőben válassza az **Intrastat-jelentés** lehetőséget.
5. Az **Vámtrafiakód-hierarchia** gyorslapon a **Kategória hierarchia** mezőben győződjön meg arról, hogy az **Intrastat** van kiválasztva.
6. Az **Ország/régió tulajdonságai** lapon válassza az **Új** lehetőséget.
7. A **Fél országa/régiója** mezőben válassza az **SWE** értéket.
8. Az **Ország/régió típusa** mezőben válassza a **Belföldet**.
9. A **Részes fél országa/régiója** mezőben válassza a **DEU**, majd az **Ország/régió típusa** mezőben az **EU** lehetőséget.

### <a name="set-up-product-information"></a>Termékinformációk beállítása

1. Menjen a **Termékinformációk kezelése** > **Termékek** > **Kiadott termékek** pontra.
2. Válassza ki a rácson a **D0001**-et.
3. A **Külkereskedelem** gyorslapon az **Intrastat** szakaszban, az **Árucikk** mezőben válassza a **100 200 30** kódot.
4. A **Készletkezelés** gyorslapon a **Súlymérések** szakaszban a **Nettó súly** mezőbe írja be a **5** értéket.
5. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.

### <a name="change-the-site-address"></a>A webhely címének módosítása

1. Menjen a **Raktárkezelés** > **Beállítás** > **Raktár** > **Oldalak** pontra.
2. Válassza ki a **1** értéket a rácsban.
3. A **Címek** gyorslapon válassza a **Szerkesztés** lehetőséget.
4. A **Cím szerkesztése** párbeszédpanelen az **Ország/régió** mezőben válassza ki a **SWE** lehetőséget.
5. Válassza ki az **OK** lehetőséget.

### <a name="create-a-sales-order-with-an-eu-customer"></a>Értékesítési megbízás létrehozása egy EU-s ügyféllel

1. Ugorjon a következőre: **Követelések** > **Rendelések** > **Minden értékesítési rendelés**.
2. A Műveleti ablaktáblán kattintson az **Új** elemre.
3. Az **Értékesítési megbízás létrehozása** párbeszédpanelen, a **Vevő** gyorslapon, a **Vevő** szakaszban, az **Vevői számla** mezőben válassza a **DE-015** lehetőséget.
4. Az **Általános** gyorslapon, a **Tárolási dimenziók** szakaszban, a **Telephely** mezőben válassza az **1** értéket.
5. A **Raktár** mezőben válassza ki az **11** értéket.
6. Válassza ki az **OK** lehetőséget.
7. A **Sorok** lapon, az **Értékesítési megbízás sorai** gyorslapon a **Tételszám** mezőben válassza a **D0001-et**. Ezután a **Mennyiség** mezőbe írjon be **10**-et.
8. A **Soradatok** gyorslapon, a **Külkereskedelem** fülön győződjön meg arról, hogy a **Tranzakciós kód** és **Árucikk** mezők automatikusan be vannak állítva.
9. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.
10. A Műveletpanelen, a **Számla** lapon, a **Létrehozás** szakaszban válassza a **Számla** lehetőséget.
11. A **Számlafeladás** párbeszédpanel **Paraméterek** gyorslapján, a **Paraméter** szakaszban a **Mennyiség** mezőben válassza az **Összes** lehetőséget.
12. A számla könyveléséhez válassza az **OK** lehetőséget.

### <a name="transfer-the-transaction-to-the-intrastat-journal-and-review-the-result"></a>A tranzakció átvezetése az Intrastat naplóba, és az eredmény áttekintése

1. Ugorjon a következőre: **Adó** > **Nyilatkozatok** > **Külkereskedelem** > **Intrastat**.
2. A Műveletpanelen válassza az **Átvitel** lehetőséget.
3. Az **Intrastat (Átvitel)** párbeszédpanel **Paraméterek** szakaszában állítsa a **Vevői számla** beállítást **Igen** beállításra.
4. Válassza ki a **Szűrő** elemet.
5. Az **Intrastat szűrő** párbeszédpanelen a **Tartomány** lapon jelölje ki az első sort, és győződjön meg arról, hogy a **Mező** mezőben a **Dátum** érték van beállítva.
6. A **Kritériumok** mezőben válassza ki az aktuális dátumot.
7. Válassza az **OK** gombot az **Intrastat-szűrő** párbeszédpanel bezárásához.
8. Válassza az **OK** gombot az **Intrastat (Átvitel)** párbeszédpanel bezárásához, és tekintse meg az eredményt. A sor a korábban létrehozott értékesítési rendelést jelöli.

    ![Intrastat naplósorok értékesítési rendeléshez](media/swe_intrastat_journal_sales_order.png)

9. Válassza ki a tranzakciós sort, majd válassza az **Általános** lapot a további részletek megtekintéséhez.

    ![Intrastat naplósor részletei az értékesítési rendeléshez](media/swe_intrastat_journal_sales_order_line_details.png)

10. A Műveletpanelen válassza a **Kimenet** > **Jelentés** lehetőséget.
11. Az **Intrastat jelentés** párbeszédpanelen, a **Paraméterek** gyorslapona a **Dátum** szakaszban válassza ki a létrehozott értékesítési rendelés hónapját.
12. Az **Exportálási** **lehetőségek** szakaszban állítsa a **Fájl létrehozása** opciót **Igen**-re. Ezután a **Fájlnév** mezőbe írja be a kívánt nevet.
13. Állítsa a **Jelentés készítése** opciót **Igenre**. Ezután a **Jelentésfájl neve** mezőbe írja be a kívánt nevet.
14. Az **Irány** mezőben válassza a **Küldemények** lehetőséget.
15. Válassza az **OK** gombot, és tekintse át a generált .txt formátumú jelentést. A következő táblázat a példajelentésben szereplő értékeket mutatja.

    | Partnerország ISO-kódja | Tranzakció kódja | Vámtarifakód | Másodlagos egység | Betűvastagság | Számlaösszeg |
    |--------------------------|------------------|----------------|-----------------|--------|----------------|
    | IT                       | 1                | 10020030       | 0               | 50     | 3290           |

16. Tekintse át a generált Excel formátumú jelentést.

    ![Intrastat jelentés](media/swe_intrastat_report_for_dispatches.png)

### <a name="create-a-purchase-order"></a>Beszerzési rendelés létrehozása

1. Menjen a **Fizetendő számlák** > **Beszerzési megbízások** > **Minden beszerzési megbízás** menüpontba.
2. A Műveleti ablaktáblán kattintson az **Új** elemre.
3. A **Megrendelés létrehozása** párbeszédpanelen a **Szállítói számla** mezőben válassza a **DE-001-et**.
4. Válassza ki az **OK** lehetőséget.
5. A **Fejléc** lap **Kül** **kereskedelmi** gyorslapon ellenőrizze, hogy a **Tranzakciókód** mezőben **1** van-e beállítva.
6. A **Sorok** lapon, a **Beszerzési rendelés sorai** gyorslapon a **Tételszám** mezőben válassza a **D0001-et**. Ezután a **Mennyiség** mezőbe írjon be **6**-et.
7. A Műveletpanelen, a **Vásárlás** lapon, a **Műveletek** csoportban válassza a **Megerősítés** lehetőséget.
8. A Műveleti ablaktábla **Számla** lapján a **Létrehozás** csoportban válassza a **Számla** lehetőséget.
9. A Műveletpanelen válassza az **Alapértelmezettet**. A **Sorok alapértelmezett mennyisége** mezőben válassza a **Megrendelt mennyiséget**. Majd kattintson az **OK** lehetőségre.
10. A **Szállítói számla fejléc** gyorslap, a **Számla azonosítása** szakaszában a **Szám** mezőbe írja be a **0001-es** számot.
11. A Művelet ablaktáblán válassza a **Feladás** lehetőséget a számla könyveléséhez.

### <a name="create-an-intrastat-declaration-for-arrivals"></a>Intrastat-nyilatkozat létrehozása az érkezésekhez

1. Ugorjon a következőre: **Adó** > **Nyilatkozatok** > **Külkereskedelem** > **Intrastat**.
2. A Műveletpanelen válassza az **Átvitel** lehetőséget.
3. Az **Intrastat (Átvitel)** párbeszédpanelen állítsa a **Szállítói számla** opciót **Igenre**.
4. Válassza az **OK** lehetőséget a tranzakciók átviteléhez, és tekintse át az Intrastat naplót.

    ![Intrastat napló beszerzési rendeléshez](media/swe_intrastat_journal_purchase_order.png)

5. Tekintse át a beszerzési rendelés **Általános** lapját.

    ![Intrastat naplósor adatai a beszerzési rendeléshez](media/swe_intrastat_journal_purchase_order_line_details.png)

6. A Műveletpanelen válassza a **Kimenet** > **Jelentés** lehetőséget.
7. Az **Intrastat jelentés** párbeszédpanelen, a **Paraméterek** gyorslapona a **Dátum** szakaszban válassza ki a létrehozott értékesítési rendelés hónapját.
8. Az **Exportálási** **lehetőségek** szakaszban állítsa a **Fájl létrehozása** opciót **Igen**-re. Ezután a **Fájlnév** mezőbe írja be a kívánt nevet.
9. Állítsa a **Jelentés készítése** opciót **Igenre**. Ezután a **Jelentésfájl neve** mezőbe írja be a kívánt nevet.
10. Az **Irány** mezőben válassza az **Érkezések** lehetőséget.
11. Válassza az **OK** gombot, és tekintse át a generált .txt formátumú jelentést. A következő táblázat a példajelentésben szereplő értékeket mutatja.

    | Partnerország ISO-kódja | Tranzakció kódja | Vámtarifakód | Másodlagos egység | Betűvastagság | Számlaösszeg |
    |--------------------------|------------------|----------------|-----------------|--------|----------------|
    | IT                       | 1                | 10020030       | 0               | 30     | 1714           |

12. Tekintse át a generált Excel formátumú jelentést.

    ![Intrastat érkezési jelentés](media/swe_intrastat_arrivals_report.png)
