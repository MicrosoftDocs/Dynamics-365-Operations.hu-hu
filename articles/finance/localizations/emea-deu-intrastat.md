---
title: Német Intrastat
description: Ez a témakör a németországi Intrastat-jelentéskészítéssel kapcsolatban tartalmaz tájékoztatást.
author: andosip
ms.date: 08/2/2021
ms.topic: article
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: v-aosipov
ms.search.validFrom: ''
ms.openlocfilehash: e1dbf0997417f9f1ad313e6a7b3c2c9cfae41efc6b1cfda60a5500ae0af94709
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6759843"
---
# <a name="german-intrastat"></a>Német Intrastat

Az **Intrastat** oldalon információkat generálhat és jelenthet az Európai Unió országaival folytatott kereskedelemről. A német Intrastat nyilatkozat tartalmazza a jelentéskészítéshez szükséges árukereskedelmi adatokat.

Az alábbi táblázat a német Intrastat-nyilatkozatban szereplő mezőket mutatja be.

| Mezők | Elküldések | Érkezések |
|-------------------------|-------------------------|-------------------------|
| Referencia-időszak | X | X |
| Irány kódja | X | X |
| Az Intrastat-nyilatkozat pénzneme</br>**Megjegyzés:** Ez a pénznem a <em>könyvelési pénznem</em>. | X | X |
| Árucikk-kód | X | X |
| Árucikk neve | X | X |
| Kiegészítő mértékegység kódja | X | X |
| A feladó/rendeltetési hely szerinti tagállam | X | X |
| Nettó tömeg | X | X |
| Kiegészítő mértékegységben kifejezett mennyiség | X | X |
| Származási ország |  | X |
| Számlaösszeg | X |  |
| Statisztikai érték | X | X |
| Tranzakciók jellege | X | X |
| Szállítás módja | X | X |
| Régiókód</br>**Megjegyzés:**</br><ul></br><li>Ha a származási ország vagy régió Németország, és a számla feladásokról szól, a származási állam Intrastat-kódja jelenik meg.</li></br><li>Ha a származási ország vagy régió nem Németország, és a számla feladásokról szól, a **99**-es kód jelenik meg.</li></br><li>Ha a számla az érkezések számlája, akkor az állam Intrastat-kódja jelenik meg.</li></br></ul> | X | X |
| Kikötő/repülőtér/belvízi kikötő kódja | X | X |
| Szállítási feltételek | X | X |


## <a name="set-up-intrastat"></a>Intrastat beállítása

1. A vállalat kódjainak beállítása.

    1. Nyissa meg a következőt: **Szervezetek adminisztrációja** > **Szervezetek** > **Jogi személyek**.
    2. A **Külkereskedelem és logisztika** gyorslapon az **Azonosítás** szakaszban, a **DVR** mezőben adja meg az adatcsere egyezmény azonosítóját. Ez az azonosító szerepel majd a jelentésben.
    3. Az **Áfamentességi szám exportáláshoz** mezőben adja meg a vállalat exportálásra használt áfaszámát.
    4. Az **Áfamentességi szám importáláshoz** mezőben adja meg a vállalat importálásra használt áfaszámát.
    5. Az **Intrastat-kód** mezőbe írja be a jogi személyhez rendelt Intrastat-kódot.
    6. Az **Adó regisztráció** gyorslapon, az **Adószám** mezőben adja meg a vállalata adószámát.

    > [!NOTE]
    > Ha Intrastat-jelentést készít a kapcsolt vállalkozások számára, az **Adónyilvántartási szám** mezőben adja meg az anyavállalat adónyilvántartási számát.

2. A [Microsoft Dynamics Lifecycle Services (LCS)](https://lcs.dynamics.com/Logon/Index) portálon, a Közös eszközök tárának menüpontjában töltse le a következő Elektronikus jelentés (ER) konfigurációk legújabb verzióit az Intrastat-nyilatkozathoz.

    - Intrastat modell
    - Intrastat jelentés
    - INSTAT XML
    - INSTAT XML (DE)

3. Külkereskedelmi paraméterek beállítása:

    1. A Dynamics 365 Finance alkalmazásban menjen az **Adó** > **Beállítás** > **Külkereskedelmi paraméterek** menüponthoz.
    2. Az **Intrastat** lapon az **Elektronikus jelentéskészítés** gyorslapon a **Fájlformátum leképezés** mezőben válassza az **Intrastat XML (DE)** lehetőséget.
    3. A **Jelentésformátum-hozzárendelés** mezőben válassza az **Intrastat jelentés** lehetőséget.
    4. Az **Árucikk-kódok hierarchiája** gyorslapon a **Kategóriahierarchia** mezőben válassza az **Intrastat** lehetőséget.
    5. A **Tranzakciókód** mezőben válassza ki a vagyonátruházáshoz létrehozott tranzakciókódot. Ezt a kódot olyan tranzakciókra kell használni, amelyek tényleges vagy tervezett vagyonátruházást eredményeznek (pénzügyi vagy egyéb) ellenszolgáltatás ellenében. Javításra is használható.
    6. A **Jóváírási megjegyzés** mezőben válassza ki az áruk visszaküldésének tranzakciós kódját. Ezt a kódot az eredetileg a tranzakció kódja alatt rögzített áruk visszaküldésére használja a tranzakciót követően.
    7. A **Hatóság** mezőben válassza ki az Intrastatáhatóságot.
    8. Válassza az **Adó** > **Közvetett adók** > **Értékesítési adó** > **Értékesítési adóhatóságok** menüpontot, és adja meg az előző lépésben kiválasztott Intrastat-hatósághoz a következő adatokat:

       - Hatóság azonosítója
       - Cím
       - Kapcsolattartó adatai

    9. Az **Ország/régió tulajdonságai** lapon az **Ország/régió** mezőben sorolja fel azokat az országokat vagy régiókat, amelyekkel a vállalata üzleti kapcsolatban áll. Minden egyes ország vagy régió esetében az **Ország/régió típusa** mezőben válassza az **EU** lehetőséget, hogy az ország vagy régió megjelenjen az Intrastat-jelentésben.

4. Regionális kódok beállítása.

    1. Lépjen a **Szervezet adminisztráció** > **Globális címjegyzék** > **Címek** > **Címbeállítás** menüpontra.
    2. Az **Állam/tartomány** lapon az **Ország/régió** mezőben válassza a **DEU** lehetőséget, majd válassza a **Szűrő alkalmazása** lehetőséget.
    3. A rácsban válassza ki az államot. Ezután az **Intrastat-kód** mezőbe írja be az egyedi Intrastat-kódot.

5. A termék származási címének beállítása.

    1. Ugorjon a következőre: **Termékinformáció-kezelés** > **Termékek** > **Felszabadított termékek**.
    2. A rácsban válassza ki a terméket.
    3. A **Külkereskedelem** gyorlapon az **Intrastat** szakaszban a **Származási ország** mezőben válassza ki a **DEU** lehetőséget.

6. Válassza az **Adó** > **Beállítások** > **Külkereskedelem** > **Intrastat tömörítése** menüpontot, és válassza ki azokat a mezőket, amelyeket össze kell hasonlítani az Intrastat-adatok összesítése során. A német Intrastat esetében válassza ki a következő mezőket:

    - Árucikk
    - Ország/régió
    - Korrekció
    - Irány
    - Szállítási feltételek
    - Számla
    - Származási ország/régió
    - Kikötő
    - Feladó országa/régiója
    - Feladó állama
    - Statisztikai eljárás
    - Tranzakció kódja
    - Átvitel
    - Adómentességi szám

### <a name="intrastat-transfer"></a>Intrastat-átvitel

Az **Intrastat** lapon a Műveletpanelen válassza az **Átvitel** lehetőséget, hogy automatikusan átvegye a Közösségen belüli kereskedelemre vonatkozó információkat az értékesítési rendelésekből, a szabadszöveges számlákból, a beszerzési rendelésekből, a szállítói számlákból, a szállítói termékbevételekből **,** a projekt számlákból és az átutalási megbízásokból. Csak azok a dokumentumok kerülnek átvitelre, amelyek célországa vagy -régiója (kiküldésekhez) vagy feladója (beérkezésekhez) egy EU-s ország.

Másik lehetőségként manuálisan is beírhatja a tranzakciókat az **Új** gombra kattintva a Műveletei panelen.

### <a name="generate-an-intrastat-report"></a>Intrastat jelentés készítése

1. Ugorjon a következőre: **Adó** > **Nyilatkozatok** > **Külkereskedelem** > **Intrastat**.
2. A Műveletpanelen válassza a **Kimenet** > **Jelentés** lehetőséget.
3. Az **Intrastat jelentés** párbeszédpanelen a következő mezőket állítsa be.

    | Mező | Leírás |
    |-------------------------|-------------------------|
    | Kezdő dátum | Válassza ki a jelentés kezdő dátumát. |
    | Záró dátum | Válassza ki a jelentés befejező dátumát. |
    | Fájl létrehozása | Egy .xml fájl generálásához állítsa ezt a beállítást **Igen** értékre. |
    | Fájlnév | Ezt a mezőt hagyja üresen. A fájl neve automatikusan generálódik, és az **&lt;envelopeId&gt;** XML-címke értékéből és az **.xml** kiterjesztésű fájlnévből áll.</br>Az **&lt;envelopeId&gt;** érték a következő elemek összekapcsolása, ebben a sorrendben:</br><ol type="1"></br><li>Az **&lt;interchangeAgreementId&gt;** címke értéke</li></br><li>Kötőjel (-)</li></br><li>A **&lt;referencePeriod in YYYYMM&gt;** címke értéke</li></br><li>Kötőjel (-)</li></br><li>Az **&lt;Envelope/DateTime/date in YYYYMMDD&gt;** címke értéke</li></br><li>Kötőjel (-)</li></br><li>Az **&lt;Envelope/DateTime/time in hhmm&gt;** címke értéke</li></br></ol> |
    | Irány | <ul></br><li>A Közösségen belüli érkezések jelentéséhez válassza az **Érkezések** lehetőséget.</li></br><li>A Közösségen belüli feladásokról szóló jelentéshez válassza a **Feladások** lehetőséget.</li></br><li>Válassza a **Mindkettő** lehetőséget, ha mind az érkezésekről, mind a feladásokról jelentést szeretne készíteni.</li></br></ul> |
    | Adóregisztrációs szám | Adja meg a feladó azonosító kódjának létrehozásához használandó nyilvántartási számot, ha a szám eltér a jogi személy adóregisztrációs számától. |


## <a name="example"></a>Példa

Ez a példa azt mutatja be, hogyan kell az Intrastat érkezéseket és elküldéseket feladni. A **DEMF** jogi személyt használja.

1. Az [LCS](https://lcs.dynamics.com/Logon/Index)-ben a Közös eszközök tárában töltse le a következő ER-konfigurációk legújabb verzióit az Intrastat nyilatkozatformátumhoz:

    - Intrastat modell
    - Intrastat jelentés
    - Intrastat XML
    - Intrastat XML (DE)

2. Tranzakciós kódok létrehozása.

    1. Ugorjon a következőre: **Adó** > **Beállítás** > **Külkereskedelem** > **Tranzakciókódok**.
    2. A Műveleti ablaktáblán kattintson az **Új** elemre.
    3. A **Tranzakció** **kód** mezőbe írjon be **21**-et.
    4. A **Név** mezőbe írja be az **Áruvisszaküldés** értéket.
    5. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.

3. Állítsa be a hatósági azonosítószámot.

    1. Ugorjon a következőre: **Adó** > **Közvetett adók** > **Értékesítési adó** > **Adóhatóságok**.
    2. A listában válassza ki a **TA** értéket.
    3. A **Hatóság azonosító** mezőbe írjon be **123**-at.

4. Regionális kódok beállítása.

    1. Lépjen a **Szervezet adminisztráció** > **Globális címjegyzék** > **Címek** > **Címbeállítás** menüpontra.
    2. Az **Állam/tartomány** lapon az **Ország/régió** mezőben válassza a **DEU** lehetőséget, majd válassza a **Szűrő alkalmazása** lehetőséget.
    3. A rácsban válassza a **BE** lehetőséget, majd az **Intrastat-kód** mezőbe írjon be **11**-et.
    4. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.

5. Külkereskedelmi paraméterek beállítása.

    1. Ugorjon a következőre: **Adó** > **Beállítások** > **Külkereskedelem** > **Külkereskedelmi paraméterek**.
    2. Az **Intrastat** lapon az **Általános** gyorslapon a **Tranzakció** **kód** mezőben válassza a **11**-et.
    3. A **Jóváírási megjegyzés** mezőben válassza a **21**-et.
    4. A **Hatóság** mezőben válassza a **TA** értéket.
    5. Az **Elektronikus jelentéskészítés** gyorslapon a **Fájlformátum-társítás** mezőben válassza az **INSTAT XML (DE)** lehetőséget.
    6. A **Jelentésformátum hozzárendelése** mezőben válassza az **Intrastat-jelentés** lehetőséget.
    7. Az **Vámtrafiakód-hierarchia** gyorslapon a **Kategória hierarchia** mezőben győződjön meg arról, hogy az **Intrastat** van kiválasztva.
    8. Az **Ország/régió tulajdonságai** lapon válassza az **Új** lehetőséget.
    9. A **Fél országa/régiója** mezőben válassza az **FRA** értéket.
    10. Az **Ország/régió típusa** mezőben válassza ki az **EU** lehetőséget.

6. Egy termékhez árucikk-kódot rendelhet, és beállíthatja a termék eredetét. Az **Vámtarifakód**, a **Származási ország/régió** és a **Származási állam** mezők ezután automatikusan be lesznek állítva az értékesítési és beszerzési rendeléseken, amikor kiválasztja a terméket.

    1. Ugorjon a következőre: **Termékinformáció-kezelés** > **Termékek** > **Felszabadított termékek**.
    2. Válassza ki a rácson a **D0001**-et.
    3. A **Külkereskedelem** gyorslapon az **Intrastat** szakaszban, az **Árucikk** mezőben válassza a **920 20 34** kódot.
    4. A **Származás** szakaszban az **Ország/régió** mezőben válassza a **DEU** beállítást.
    5. A **Készletkezelés** gyorslapon a **Súlymérések** szakaszban a **Nettó súly** mezőbe írja be a **12** értéket.
    6. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.

7. Szállítás hozzárendelése egy szállítási módhoz. A szállítási kód automatikusan be lesz állítva a rendeléseken, amikor kiválasztja a szállítási módot.

    1. Ugorjon a következőre: **Beszerzés és forrás** > **Beállítás** > **Forgalmazás** > **Szállítási módok**.
    2. A listában válassza ki a **10** értéket.
    3. A **Külkereskedelem** gyorslapon a **Szállítás** mezőben válassza a **01** értéket.

8. Értékesítési rendelés létrehozása EU-s vevővel.

    1. Ugorjon a következőre: **Követelések** > **Rendelések** > **Minden értékesítési rendelés**.
    2. A Műveleti ablaktáblán kattintson az **Új** elemre.
    3. Az **Értékesítési megbízás létrehozása** párbeszédpanelen, a **Vevő** gyorslapon, a **Vevő** szakaszban, az **Vevői számla** mezőben válassza a **DE-012** lehetőséget.
    4. Az **Általános** gyorslapon, a **Tárolási dimenziók** szakaszban, a **Telephely** mezőben válassza az **1** értéket.
    5. A **Raktár** mezőben válassza ki az **11** értéket.
    6. Válassza ki az **OK** lehetőséget.
    7. A **Fejléc** lap **Külkereskedelem** gyorslapján a **Kikötő** mezőben válassza az **53** értéket.
    8. A **Statisztikai eljárás** mezőben válassza a **31710** kódot.
    9.  A **Sorok** lapon, az **Értékesítési rendelés** **sorai** gyorslapon a **Tételszám** mezőben válassza a **D0001** lehetőséget. Ezután a **Mennyiség** mezőbe írjon be **10**-et.
    10. A **Sor részletei** gyorslapon a **Külkereskedelem lapon** győződjön meg arról, hogy automatikusan be van állítva a **Tranzakciókód**, a **Szállítás**, az **Árucikk** és a **Származási ország/régió** mező.
    11. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.
    12. A Műveletpanelen, a **Számla** lapon, a **Létrehozás** szakaszban válassza a **Számla** lehetőséget.
    13. A **Számlafeladás** párbeszédpanel **Paraméterek** gyorslapján, a **Paraméter** szakaszban a **Mennyiség** mezőben válassza az **Összes** lehetőséget.
    14. A számla könyveléséhez válassza az **OK** lehetőséget.

9.  Vigye át a tranzakciót az Intrastat naplóba, és tekintse át az eredményt.

    1. Ugorjon a következőre: **Adó** > **Nyilatkozatok** > **Külkereskedelem** > **Intrastat**.
    2. A Műveletpanelen válassza az **Átvitel** lehetőséget.
    3. Az **Intrastat (Átvitel)** párbeszédpanel **Paraméterek** szakaszában állítsa a **Vevői számla** beállítást **Igen** beállításra.
    4. Válassza ki a **Szűrő** elemet.
    5. Az **Intrastat szűrő** párbeszédpanelen a **Tartomány** lapon jelölje ki az első sort, és győződjön meg arról, hogy a **Mező** mezőben a **Dátum** érték van beállítva.
    6. A **Kritériumok** mezőben válassza ki az aktuális dátumot.
    7. Válassza az **OK** gombot az **Intrastat-szűrő** párbeszédpanel bezárásához.
    8. Válassza az **OK** gombot az **Intrastat (Átvitel)** párbeszédpanel bezárásához, és tekintse meg az eredményt. A sor a korábban létrehozott értékesítési rendelést jelöli.

        ![Az Intrastat-lapon az értékesítési rendelést jelképező sor](media/intrastat_deu_1.png)

10. Válassza ki a tranzakciós sort, majd válassza az **Általános** lapot a további részletek megtekintéséhez.

    ![Értékesítési rendelés részletei az Intrastat oldal Általános lapján](media/intrastat_deu_2.png)

11. Jóváírás létrehozása egy értékesítési rendelés segítségével.

    1. Ugorjon a következőre: **Követelések** > **Rendelések** > **Minden értékesítési rendelés**.
    2. A Műveleti ablaktáblán kattintson az **Új** elemre.
    3. Az **Értékesítési megbízás létrehozása** párbeszédpanelen, a **Vevő** gyorslapon, a **Vevő** szakaszban, az **Vevői számla** mezőben válassza a **DE-012** lehetőséget.
    4. Az **Általános** gyorslapon, a **Tárolási dimenziók** szakaszban, a **Telephely** mezőben válassza az **1** értéket.
    5. A **Raktár** mezőben válassza ki az **11** értéket.
    6. A **Fejléc** lap **Külkereskedelem** gyorslapján a **Kikötő** mezőben válassza az **53** értéket.
    7. A **Statisztikai eljárás** mezőben válassza a **31710** kódot.
    8. A **Sorok** lapon, az **Értékesítési rendelés** **sorai** gyorslapon a **Tételszám** mezőben válassza a **D0001** lehetőséget. Ezután a **Mennyiség** mezőbe írja be a **-2** értéket.
    9. A **Sor részletei** gyorslapon a **Külkereskedelem lapon** a **Tranzakció kód** mezőben válassza ki a **21**-et.
    10. Győződjön meg róla, hogy a **Szállítás**, az **Áru** és a **Származási ország/régió** mezők automatikusan be vannak állítva.
    11. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.
    12. A Műveletpanelen, a **Számla** lapon, a **Létrehozás** szakaszban válassza a **Számla** lehetőséget.
    13. A **Számlafeladás** párbeszédpanel **Paraméterek** gyorslapján, a **Paraméter** szakaszban a **Mennyiség** mezőben válassza az **Összes** lehetőséget.
    14. A számla könyveléséhez válassza az **OK** lehetőséget.

12. Vigye át a tranzakciót az Intrastat naplóba, és tekintse át az eredményt.

    1. Ugorjon a következőre: **Adó** > **Nyilatkozatok** > **Külkereskedelem** > **Intrastat**.
    2. A Műveletpanelen válassza az **Átvitel** lehetőséget.
    3. Az **Intrastat (Átvitel)** párbeszédpanel **Paraméterek** szakaszában állítsa a **Vevői számla** beállítást **Igen** beállításra.
    4. Válassza az **OK** gombot az **Intrastat (Átvitel)** párbeszédpanel bezárásához, és tekintse meg az eredményt. Új sor került beillesztésre, amelyben az **Irány** mező az **Érkezések** értékre van beállítva.            
        Ez a sor az áruk fizikai visszaküldését jelenti.

        ![Az Intrastat lapon a tényleges visszáruk sora](media/intrastat_deu_3.png)

13. Válassza ki a tranzakciós sort, majd válassza az **Általános** lapot a további részletek megtekintéséhez.

    ![Az áruk tényleges visszaküldésének részletei az Intrastat oldal Általános lapján](media/intrastat_deu_4.png)

14. Javítás létrehozása egy értékesítési megbízás segítségével:

    1. Ugorjon a következőre: **Követelések** > **Rendelések** > **Minden értékesítési rendelés**.
    2. A Műveleti ablaktáblán kattintson az **Új** elemre.
    3. Az **Értékesítési megbízás létrehozása** párbeszédpanelen, a **Vevő** gyorslapon, a **Vevő** szakaszban, az **Vevői számla** mezőben válassza a **DE-012** lehetőséget.
    4. Az **Általános** gyorslapon, a **Tárolási dimenziók** szakaszban, a **Telephely** mezőben válassza az **1** értéket.
    5. A **Raktár** mezőben válassza ki az **11** értéket.
    6. A **Fejléc** lap **Külkereskedelem** gyorslapján a **Kikötő** mezőben válassza az **53** értéket.
    7. A **Statisztikai eljárás** mezőben válassza a **31710** kódot.
    8. A **Sorok** lapon, az **Értékesítési rendelés** **sorai** gyorslapon a **Tételszám** mezőben válassza a **D0001** lehetőséget. Ezután a **Mennyiség** mezőbe írja be a **-3** értéket.
    9. A **Sor részletei** gyorslapon a **Külkereskedelem** lapon a **Tranzakció kód** mezőben válassza ki a **11** értéket.
    10. Győződjön meg róla, hogy a **Szállítás**, az **Áru** és a **Származási ország/régió** mezők automatikusan be vannak állítva.
    11. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.
    12. Győződjön meg arról, hogy a **Tranzakció kód** mezőben a 11 érték van beállítva.
    13. A Műveletpanelen, a **Számla** lapon, a **Létrehozás** szakaszban válassza a **Számla** lehetőséget.
    14. A **Számlafeladás** párbeszédpanel **Paraméterek** gyorslapján, a **Paraméter** szakaszban a **Mennyiség** mezőben válassza az **Összes** lehetőséget.
    15. A számla könyveléséhez válassza az **OK** lehetőséget.

15. Vigye át a tranzakciót az Intrastat naplóba, és tekintse át az eredményt:

    1. Ugorjon a következőre: **Adó** > **Nyilatkozatok** > **Külkereskedelem** > **Intrastat**.
    2. A Műveletpanelen válassza az **Átvitel** lehetőséget.
    3. Az **Intrastat (Átvitel)** párbeszédpanel **Paraméterek** szakaszában állítsa a **Vevői számla** beállítást **Igen** beállításra.
    4. Válassza az **OK** gombot az **Intrastat (Átvitel)** párbeszédpanel bezárásához, és tekintse meg az eredményt. Egy új sor került beillesztésre, ahol a **Javítás** oszlopban egy pipa jelenik meg.

        ![Az Intrastat oldalon található javítási sor](media/intrastat_deu_5.png)

16. Válassza ki a tranzakciós sort, majd válassza az **Általános** lapot a további részletek megtekintéséhez.

    ![A javítás részletei az Intrastat oldal Általános lapján](media/intrastat_deu_6.png)

17. A Műveletpanelen válassza a **Kimenet** > **Jelentés** lehetőséget.
18. Az **Intrastat jelentés** párbeszédpanelen, a **Paraméterek** gyorslapona a **Dátum** szakaszban válassza ki a létrehozott értékesítési rendelés hónapját.
19. Az **Exportálási** **lehetőségek** szakaszban állítsa a **Fájl létrehozása** opciót **Igen**-re.
20. A **Fájlnév** mezőben adja meg a szükséges nevet.
21. Válassza az **OK** gombot, és tekintse meg a létrehozott jelentést. A következő táblázat a példajelentésben szereplő értékeket mutatja.

    | **Név**                  | **Értékesítési számla**  |   **Korrekció**   | **Jóváírás** |
    |---------------------------|--------------------|--------------------|-----------------|
    | declarationId             | 2021-07-D          | 2021-07-A          |                 |
    | referencePeriod           | 2021-07            | 2021-07            |                 |
    | PSIId                     | 11203/118/12345000 | 11203/118/12345000 |                 |
    | functionCode              | O                  | O                  |                 |
    | flowCode                  | T                  | A                  |                 |
    | CurrencyCode              | EUR                | EUR                |                 |
    | itemNumber                | 0000362            | 0000362            | 0000361         |
    | CN8Code                   | 9202034            | 9202034            | 9202034         |
    | goodsDescription          | Speaker            | Speaker            | Speaker         |
    | MSConsDestCode            | FR                 | FR                 | FR              |
    | countryOfOriginCode       | \-                 | \-                 | DE              |
    | netMass                   | 120                | -36                | 24              |
    | invoicedAmount            | 3290               | -987               | \-              |
    | StatisticalValue          | 3290               | -987               | 658             |
    | natureOfTransactionACode  | 1                  | 1                  | 2               |
    | natureOfTransactionBCode  | 1                  | 1                  | 1               |
    | modeOfTransportCode       | 01                 | 01                 | 01              |
    | regionCode                | 11                 | 11                 | 11              |
    | portAirportInlandportCode | 53                 | 53                 | 53              |

