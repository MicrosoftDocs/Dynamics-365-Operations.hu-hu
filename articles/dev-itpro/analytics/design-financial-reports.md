---
title: Pénzügyi jelentések megtekintése és tervezése
description: Ebben a cikkben gyakorlatokat talál, amelyek bemutatják a pénzügyi jelentések megtekintését és létrehozását a Microsoft Dynamics 365 for Finance and Operations rendszerben.
author: jcart1106
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: FinancialReportingSetup
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 10814
ms.assetid: cd5f6483-c09b-4c2d-9336-d22eb6ab6e4f
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 94933ed28ad3a5f4f5e0f45bdd2f6131550a213c
ms.sourcegitcommit: 16bfa0fd08feec1647829630401ce62ce2ffa1a4
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/02/2019
ms.locfileid: "1848317"
---
# <a name="view-and-design-financial-reports"></a>Pénzügyi jelentések megtekintése és tervezése

[!include [banner](../includes/banner.md)]

Ebben a cikkben gyakorlatokat talál, amelyek bemutatják a pénzügyi jelentések megtekintését és létrehozását a Microsoft Dynamics 365 for Finance and Operations rendszerben. A pénzügyi jelentések egyrészt a Microsoft Dynamics 365 for Finance and Operations rendszeren belüli megtekintésből, másrészt az egy kattintással használható jelentéstervezőből állnak, amellyel pénzügyi jelentéseket hozhat létre és szerkeszthet.

## <a name="exercise-1-generate-and-explore-a-default-financial-report"></a>1. Gyakorlat: Alapértelmezett pénzügyi jelentés létrehozása és böngészése

Ebben a gyakorlatban meglévő alapértelmezett jelentést fog létrehozni és böngészni. Ez a jelentés minden számlát tartalmaz, és tartalmazza a számlák tulajdonságait (attribútumok) a számlákra is. Belemegy majd a tranzakció részleteibe, dimenzió szűrőket alkalmaz, és módosítja a jelentésben szereplő pénznemet. Ajánlott először frissítése a pénzügyi jelentések dimenziók megjelenítési sorrendjét. Ez lehetővé teszi, hogy kiválassza, hogyan jelenjenek meg a dimenziók, nem csak a pénzügyi jelentések megtekintése és tervezése során.

1. Ugrás a **Pénzügyi dimenzió konfigurációja alkalmazások integrálásához** alatt a **Számlatükör dimenziói** pontra a Főkönyvben.
2. Mozgassa a dimenziókat a következő sorrend eléréséhez:

    1. Fő számla
    2. Üzleti egység
    3. Költséghely
    4. Osztály

    > [!NOTE]
    > A többi dimenzió maradhat a jelenlegi sorrendjükben.

3. Mentse el a dimenzió konfigurációját. Ezután létrehozunk egy jelentést és böngésszük a jelentésben szereplő adatokat.
4. Ugrás a **Pénzügyi jelentések** pontra a **Lekérdezések és jelentések** rész alatt a Főkönyvben.
5. Válassza ki a **Főkönyvi adatok – Alapértelmezett** jelentés sorát.
6. Válassza ki a **Szerkesztés** opciót.

    > [!NOTE]
    > A program kérni fogja az egykattintásos jelentés tervező letöltését és a bejelentkezést. A hitelesítő adatok használatával jelentkezzen be.

7. Módosítsa az alapévet 2012-re és válassza a **Létrehozás** opciót. Amikor jelentés kerül létrehozásra a jelentés tervezőből, a böngészőben új lapon fog megnyílni. Böngészheti a jelentést az új böngésző lapon, vagy átválthat az eredeti böngésző lapra és megnyithatja a jelentést onnan a **Pénzügyi jelentések** listából történő kiválasztással.
8. A megnyitott jelentésben válassza ki az egyik összeget a jelentéssel kapcsolatos számla adatainak kirészletezéséhez.
9. A számla részleteinek elérése után válasszon egy számlát adatokkal és a **Leásás a jelentés tranzakciós szintjéig** opciót. A jelentés tranzakció szintjén láthatja azon tulajdonságokat (attribútumokat), amelyek szerepelnek ezen jelentés tervezésében. A tranzakciótól és a számlától függően az attribútumok egy része vagy az összes megjeleníthető.
10. Zárja be a jelentés tranzakciós szintjét.
11. Válassza ki ugyanazon vagy egy másik számlát és a **Bizonylati tranzakciók megnyitása** opciót. A bizonylat tranzakciók a kiválasztott számlára vonatkozó időszak, év és a számla + dimenzió kombináció szerint kerül szűrésre. A bizonylati tranzakciókból böngészhet a tranzakcióval kapcsolatos egyéb adatokat.
12. Zárja be a bizonylati tranzakciókat. Egy pénzügyi jelentésen belül megtekintheti az adatokat egy eltérő időszakra és évre, vagy különböző attribútumokat és dimenziókat alkalmazva. Ez a **Jelentés beállítások** használatával hajtható végre.
13. Válassza ki a **Jelentés beállítások** opciót.
14. Válassza ki a **Dimenzió szűrő hozzáadása** opciót és válassza az **Üzleti egység** lehetőséget.
15. Írja be a 001 értéket a mezőbe, majd kattintson az **OK** gombra. A jelentés most már kizárólag a 001 Üzleti egység adatait jeleníti meg. Ez egy testreszabott nézete a jelentésnek, és mások számára nem megtekinthető.
16. Zárja be a szűrt jelentést. A pénzügyi jelentések bármilyen pénznemben megjeleníthetők, amelyet hozzáadtak a Finance and Operations rendszerhez.
17. Válassza ki a **Pénznem** opciót, majd válassza az **EUR** lehetőséget. A jelentés most euróban jelenik meg. Most bármilyen, a jelentéstervben szereplő pénznemszimbólumok vagy pénznemkódok az alkalmazott pénznemben jelennek meg. Ha egy pénznemre nincs megadva pénznemszimbólum, a pénznem szimbóluma nem jelenik meg.
18. Zárja be a **Főkönyvi adatok** jelentést.
19. Zárja be a **Jelentéstervező** ablakot.

## <a name="exercise-2-add-additional-account-properties-to-a-report-design"></a>2. Gyakorlat: További számla tulajdonságok hozzáadása jelentéstervhez
Ebben a gyakorlatban meglévő alapértelmezett jelentést fog módosítani. Frissíteni fogja a sordefiníciót az összes számla felvételéhez és frissíteni fogja a oszlopdefiníciót, hogy tartalmazza a számla tulajdonságokat. Ha befejeződtek a frissítések, előállítja majd az újonnan létrehozott jelentést és böngészi a jelentést. A Pénzügyi jelentések listától indulunk.

1. Ugrás a **Pénzügyi jelentések** pontra a Lekérdezések és jelentések rész alatt a Főkönyvben.
2. Válassza ki a **Összegző főkönyvi kivonat – Alapértelmezett** jelentés sorát.
3. Válassza ki a **Szerkesztés** opciót. Az **Összegző főkönyvi kivonat – Alapértelmezett** a jelentéstervezőben nyílik meg.
4. Válassza a **Fájl** menüpontot, majd a **Mentés másként** opciót és adja a jelentésnek a Részletes főkönyvi kivonat attribútumokkal nevet.

    > [!NOTE]
    > Bármikor, ha új jelentés kerül létrehozásra a jelentéstervezőben, a pénzügyi jelentések lista frissítésre kerül a Finance and Operations rendszerben.

5. A jelentésdefinícióból válassza ki a sordefiníció ikont a **Főkönyvi kivonat – Alapértelmezett sordefiníció** megnyitásához.
6. Mentse a sordefiníciót **Részletes főkönyvi kivonat attribútumokkal** néven.
7. A kurzort az 50. sorra helyezve válassza a **Szerkesztés** opciót, majd a **Sorok beszúrása dimenziókból** lehetőséget. A Sorok beszúrása dimenziókból segítségével kiválaszthatja, milyen dimenziókat szeretne a sordefiníciójában. Ebben a gyakorlatban létrehozzuk a sordefiníciót a Fő számla használatával.
8. Győződjön meg róla, hogy a **Fő számla** tartalmaz minden és-jelet, majd kattintson az **OK** gombra. A sordefiníció most tartalmazza az USMF jogi személy minden fő számláját.
9. Görgessen le az 11110 sorhoz és törölje az 11110 sort.
10. Az 11080 sorban válassza ki az **--- (Összegek aláhúzása)** opciót.
11. Az 11140 sor B oszlopába írja be a következőt: **Valamennyi számla összege**.
12. A C oszlopban válassza ki a **TOT** lehetőséget a legördülő listából.
13. A D oszlopba írja be a következőt: **50:11080**.
14. Jelentésdefiníció **Mentése**. A sordefiníció most tartalmazza az összes számlát, valamint egy összegező sort az összes számla összeadásához. Ezt követően frissítjük az oszlopdefiníciót a további számla attribútumok felvételéhez.
15. A **Részletes főkönyvi kivonat attribútumokkal** jelentésdefinícióból válassza ki az oszlopdefiníció ikont az **Összegző főkönyvi kivonat – Alapértelmezett** megnyitásához.
16. Mentse az oszlopdefiníciót **Részletes főkönyvi kivonat attribútumokkal** néven. Az oszlopdefiníció pénzügyi adatok oszlopokat, egy leírás oszlopot és számítás oszlopokat tartalmaz. Attribútum oszlopokat fogunk hozzáadni az oszlopdefinícióhoz, hogy további részleteket biztosítsanak a számlákról.
17. A következő attribútumok kerülnek hozzáadásra az oszlopdefinícióhoz:

    - Napló száma
    - Napló leírása
    - Tranzakció dátuma
    - Létrehozta
    - Legutóbb módosította:

18. Az I oszlopban válassza ki az **ATTR** oszloptípust. Ezután válassza ki a **Napló száma** lehetőséget az attribútum kategóriaként.
19. Folytassa az oszlopok hozzáadását a fennmaradó attribútumoknak.
20. A **2. fejléc** sorban, adjon hozzá leírásokat minden egyes hozzáadott új oszlopra.
21. Mentse az oszlopdefiníciót. Most, hogy a sordefiníció és oszlopdefiníció frissítésre kerültek, hozzá kell adnunk őket a jelentésdefinícióhoz.
22. A **Részletes főkönyvi kivonat attribútumokkal** jelentésdefinícióból válassza a Részletes főkönyvi kivonat attribútumokkal lehetőséget mind a sordefinícióra, mind az oszlopdefinícióra.
23. Módosítsa az alapévet a következőre: **2012**.
24. **Mentse** a jelentésdefiníciót és válassza a **Létrehozás** lehetőséget. A jelentés létrehozásának és megnyitásának befejeződése után böngészheti a jelentést, ahogyan az előző gyakorlatban tette. Részletezzen ki különböző számlákat annak megtekintésére, hogy hogyan jelennek meg a további attribútumok.
25. Zárja be a **Részletes főkönyvi kivonat attribútumokkal** jelentést.
26. Zárja be a **Jelentéstervező** ablakot.

## <a name="exercise-3-create-a-multidimensional-report-using-a-reporting-tree"></a>3. Gyakorlat: Többdimenziós jelentés létrehozása jelentési fa segítségével
Ebben a gyakorlatban meglévő alapértelmezett jelentést fog módosítani. Jelentési fát fog létrehozni és hozzáadni jelentésdefinícióhoz egy Költséghely/Felosztásos bevételkimutatás előállításához. Ha befejeződtek a frissítések, létrehozza a Költséghely/Felosztásos bevételkimutatást és böngészi a jelentést a jelentési fa segítségével. A Pénzügyi jelentések listától indulunk.

1. Ugrás a **Pénzügyi jelentések** pontra a Lekérdezések és jelentések rész alatt a Főkönyvben.
2. Válassza ki a **Bevételkimutatás – Alapértelmezett** jelentés sorát.
3. Válassza ki a **Szerkesztés** opciót. A **Bevételkimutatás – Alapértelmezett** a jelentéstervezőben nyílik meg.
4. A **Fájl** menüben mutasson az **Új** elemre, majd kattintson a **Jelentési fa definíciója** gombra.
5. Válassza a **Szerkesztés** menü **Jelentési egységek beszúrása dimenziókból** parancsát.
6. Törölje a jelet a jelölőnégyzetből az összes dimenzióra, kivéve a **Költséghely** dimenzió esetén.
7. Kattintson a **Forrásként használt dimenzió** mezőre a Költséghely dimenzióhoz, adja meg a **007** értéket, majd nyomja le a Tab billentyűt. A **Célként használt dimenzió** mezőbe írja be a **018** értéket.
8. **Mentse** az eredményül kapott fát **Költséghelyek részleg szerint** néven. Most, hogy a jelentési fa létrehozásra került, módosítani fogja a jelentési fát úgy, hogy tartalmazzon három új összesítő egységet; Marketing, Műveletek és Kiskereskedelem.
9. Az **Ablak** menüben kattintson a **Költséghelyek részleg szerint** elemre. (Ha be lett zárva a jelentési fa, válassza ki a navigációs ablakban a Jelentési fa definíciók elemből.)
10. Kattintson a kettes egységszámra, majd a **Kereskedelmi börze** elemre, és kattintson a **Jelentési egység beszúrása** ikonra.
11. Kattintson duplán az entitás oszlopra az üres sorban, és válassza az **USMF** elemet.
12. A B és C oszlopokba írja a következőt: **Marketing**.
13. Kattintson az ötös egységszámra, majd a **Szolgáltatási műveletek** elemre, és kattintson a jobb gombbal. Válassza a **Jelentési egység beszúrása** opciót.
14. Ismételje meg a 11. lépést.
15. A B és C oszlopokba írja a következőt: **Műveletek**.
16. Kattintson a tizenkettes egységszámra, majd az **Outlet** elemre, és kattintson a jobb gombbal. Válassza a **Jelentési egység beszúrása** opciót.
17. Ismételje meg a 11. lépést.
18. A B és C oszlopokba írja a következőt: **Kiskereskedelem**. A Marketing, Műveletek és Kiskereskedelem egységek az aktuális összesítő egységekkel azonos szinten jelennek meg. Az új egységek kerülnek rendezésre ezután. A jelentési egységek a jobb gombos lehetőségekkel kerülnek rendezésre; előléptetéssel és visszaléptetéssel, vagy húzással.
19. Ellenőrizze, hogy a hármas egység, a **Kereskedelmi börzék** aktív, és kattintson a jobb gombbal.
20. Válassza ki a **Jelentési egység hátrasorolása** opciót. Figyelje meg, hogy az egység ettől kezdve a **Marketing** gyermekeként jelenik meg.
21. Kattintson a négyes egységre, a **Marketingkampány** elemre, és kattintson a jobb gombbal.
22. Válassza ki a **Jelentési egység hátrasorolása** opciót.
23. Kattintson a **Szolgáltatási műveletek** elemre a grafikus kijelzőn. Nyomja meg és tartsa lenyomva az egér bal oldali gombját amíg felhúzza az egységet a **Műveletek** elemhez. Engedje fel a bal egérgombot az egységnek a Műveletek összesítőjébe való beleejtéséhez. Ismételje meg a **Termelés, Minőség-ellenőrzés, Beszerzés és Felügyelet** elemre.
24. Tegye az **Outlet**, **Szuper**, **Bevásárlóközpont**, és **Online** elemeket a **Kiskereskedelem** gyermekévé a hátrasorolásukkal vagy azok húzásával.
25. Mentse az eredményül kapott átszervezést. Most, hogy a jelentési fa létrehozásra és rendezésre került, hozzáadható a jelentésdefinícióhoz.
26. Az **Ablak** menüben válassza a **Bevételkimutatás – Alapértelmezett** elemet a jelentésdefiníció megnyitásához.
27. Kattintson a **Fa típus** legördítő nyílra, és válassza a **Jelentési fa** lehetőséget.
28. Kattintson a Fa legördítő nyílra, majd válasza a **Költséghelyek részleg szerint** lehetőséget.
29. Módosítsa az alapévet a **2012** értékre, **mentse** a módosításokat és **hozza létre** a jelentést. A jelentés létrehozásának és megnyitásának befejeződése után böngészhet a jelentésben.
30. Válassza ki a **Jelentési fa** legördülő listáját a jelentési egységek megtekintéséhez. Másik lehetőségként kirészletezheti a jelentés egy sorát a jelentési fa összes egységének összes egyenlegének megtekintéséhez.
31. Zárja be a **Bevételkimutatás – alapértelmezett** ablakot.
32. Zárja be a **Jelentéstervező** ablakot.

## <a name="exercise-4-create-a-consolidated-report-using-an-organization-hierarchy"></a>4 gyakorlat: A szervezeti hierarchia használata konszolidált jelentés létrehozása
Ebben a gyakorlatban meglévő alapértelmezett jelentést fog módosítani. Fel szeretné venni a szervezeti hierarchia mutatni a konszolidált eredménykimutatás és mérleg jelentés meghatározása. Ha befejeződtek a frissítések, létrehozza a konszolidált bevételkimutatást és böngészi a jelentést a jelentési fa segítségével. A Pénzügyi jelentések listától indulunk.

1. Ugrás a **Pénzügyi jelentések** pontra a Lekérdezések és jelentések rész alatt a Főkönyvben.
2. Válassza ki a sort a nevű jelentés **Mérleg és eredménykimutatás egymás mellé – alapértelmezett**
3. Válassza ki a **Szerkesztés** opciót. Válassza ki a sort a nevű jelentés **Mérleg és eredménykimutatás egymás mellé – alapértelmezett**.
4. Válassza a **Fájl** &gt; **Mentés másként** elemet, és adja a jelentésnek a **Mérleg és bevétel-kimutatás egymás mellett** nevet.
5. Módosítsa az alapévet a következőre: 2012.
6. Kattintson a **Szervezeti hiearchiák** legördítő nyílra, és válassza a Jelentési fa lehetőséget.
7. Kattintson a **Contoso Holdings** legördítő nyílra, és válassza a Jelentési fa lehetőséget.
8. A változtatások mentése és a varázsló bezárása. Ha szükséges, az összes jelentés egység kiválasztása A jelentés létrehozásának és megnyitásának befejeződése után böngészhet a jelentésben.
9. Válassza ki a **Jelentés beállítások** opciót.
10. Válassza ki a **Dimenzió szűrő hozzáadása** opciót és válassza a **Részleg** lehetőséget.
11. Írja be a **022** értéket a mezőbe, majd kattintson az **OK** gombra.
12. Zárja be a szűrt jelentést.
13. Válassza ki a **Jelentési fa** legördülő listáját a jelentési egységek megtekintéséhez. Másik lehetőségként kirészletezheti a jelentés egy sorát a jelentési fa összes egységének összes egyenlegének megtekintéséhez.
14. Zárja be a **Mérleg és bevétel-kimutatás egymás mellett**.
15. Zárja be a **Jelentéstervező** ablakot.

## <a name="exercise-5-create-a-sidebyside-departmental-report"></a>5. gyakorlat: Egymás melletti részlegjelentés létrehozása
A következő gyakorlatban fog létrehozni új jelentés. A jelentés akkor egymás mellett megyei eredménykimutatásban. Használni egy korábbi sordefiníciót fog, de új jelentésdefiníciót és új oszlopdefiníció használó dimenzió szűrők létrehozása. A Pénzügyi jelentések listától indulunk.

1. Ugrás a **Pénzügyi jelentések** pontra a Lekérdezések és jelentések rész alatt a Főkönyvben.
2. **Új** kiválasztása. Nyissa meg a jelentés üres definíciója jelentéstervező nyílik meg. Az első feladat az oszlopdefiníció létrehozni.
3. Hozzon létre egy új oszlopdefiníció kattintva **Fájl**, majd **Új**, majd **Oszlopdefiníció**.
4. Az **A oszlopban** válassza ki az **DESC** oszloptípust.
5. Az **B oszlopban** válassza ki az **FD** oszloptípust.
6. Kattintson duplán a **a Dimenziószűrő** mező.
7. A **Dimenzió** ablakban dupla kattintás a **Részleg** oszlopban.
8. Jelölje be a párbeszédpanelt egyén vagy egy tartomány csoport a **három pont** tartozó a **származó** mező Részlegek listájának megjelenítése.
9. Válassza ki a részleg **022**, **Értékesítés és Marketing** , majd **OK** pontokat.
10. Ismételje meg az 5 – 8 lépéseket a 23-25. részlegek esetén.
11. A **Fejléc 2** FD oszlopfejlécében soránál, akkor írja be a következő osztály leírása:

    - B oszlop – Értékesítési és marketing
    - Oszlop C – Műveletek
    - D oszlop – Pénzügy
    - E oszlop – IT

12. Mentse a oszlopdefiníció egymás részlegek. Egy meglévő sordefinícióba használata ajánlott, mivel a jelentésdefiníció most módosítható kell használni az újonnan létrehozott oszlopdefiníció és a meglévő sordefinícióba.
13. Az **Ablak** menüben válassza az **Új jelentés meghatározása** elemet a jelentésdefiníció megnyitásához.
14. Válassza ki **Eredménykimutatás – alapértelmezett** a sordefiníció, és **Egymás mellett részlegek** , az oszlop megadása.
15. Mentse a jelentést **Egymás melletti részleg eredménykimutatásban**.
16. Módosítsa az alapévet a következőre: **2012**.
17. Módosítsa a részletezési szint a **Pénzügyi, Számla és Tranzakció**.
18. **Mentés** a módosításokat, és **készítése**. A jelentés létrehozásának és megnyitásának befejeződése után böngészhet a jelentésben.

## <a name="additional-resources"></a>További erőforrások
[Pénzügyi jelentéskészítés](../../financials/general-ledger/financial-reporting-getting-started.md)

[Pénzügyi jelentések megtekintése](../../financials/general-ledger/view-financial-reports.md)

[Dynamics Pénzügyi jelentések blog](http://blogs.msdn.com/b/dynamics_financial_reporting/)
