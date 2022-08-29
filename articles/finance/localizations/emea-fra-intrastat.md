---
title: Francia Intrastat
description: Ez a cikk a franciaországi Intrastat nyilatkozatról tartalmaz információkat.
author: AdamTrukawka
ms.date: 07/09/2021
ms.topic: article
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: atrukawk
ms.search.validFrom: ''
ms.openlocfilehash: 83af3cf304772085c5a6f0943ab5196fcc0208c9
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9287017"
---
# <a name="french-intrastat"></a>Francia Intrastat

[!include[banner](../includes/banner.md)]

A francia vállalatoknak, amelyekre az áfaregisztráltak, és amelyek más Európai Unió országaival folytatott kereskedelemben részt vesznek nyilatkozniuk kell a Franciaországba érkező és az onnan távozó áruk és szolgáltatások cseréjéről. The Declaration d'exchanges de biens (Árukereskedelmi nyilatkozat vagy DEB) az EU értékesítési lista és az Intrastat jelentés kombinációja. Ezt a jelentést havonta kell benyújtani az áruk közösségen belüli értékesítései kapcsán.

A DEB jelentés kétféle elektronikus szöveges fájlformátumban generálható: SAISUNIC 330 vagy INTRACOM formátumban.

Az alábbi táblázat bemutatja a francia Intrastat nyilatkozat mezőit a SAISUNIC 330 formátumban. A táblázat a mező jelentési szintjét is mutatja. A mező lehet **4** (egyszerűsített), **1** (teljes) vagy mindkettő.

| **Mező**                   | **Jelentésszint** |
|-----------------------------|------------------|
| Hivatkozási időszak         | 4, 1              | 
| Bevallás száma       | 4, 1              |
| Sor száma                 | 4, 1              |
| Ország ISO-kódja (FR)       | 4, 1              | 
| Kiegészítő kód          | 4, 1              | 
| Siren-szám                | 4, 1              | 
| Az ügyfél áfakódja        | 4, 1              | 
| Iránykód              | 4, 1              |
| Tranzakció típusa            | 4, 1              | 
| Kötelezettség szintje            | 4, 1              |
| Vámtarifakód              | 1                | 
| Nemzeti NGP                | 1                | 
| Megye (Részleg)         | 1                |
| A tranzakció jellege       | 1                | 
| Származási ország      | 1                | 
| Származási ország – importálások | 1                | 
| Végső cél – Exportálások | 1                | 
| Számlaérték               | 4, 1              | 
| Statisztikai érték           | 1                |
| Nettó tömeg                  | 1                | 
| Kiegészítő egységek            | 1                |
| Szállítási kód              | 1                | 

Az alábbi táblázat bemutatja a francia Intrastat nyilatkozat mezőit az INTRACOM formátumban.
A táblázat a mező jelentési szintjét is mutatja. A mező lehet **4** (egyszerűsített), **1** (teljes) vagy mindkettő.

| **Mező**                   | **Jelentésszint**   | 
|-----------------------------|--------------------|
| Kód                        | 4, 1               | 
| Bevallás száma       | 4, 1               |
| Sor száma              | 4, 1               | 
| Siren                       | 4, 1               |
| Megye (Részleg)         | 1                  |          
| Szállítási kód              | 1                  |          
| Származási ország           | 1                  |            
| A tranzakció jellege       | 1                  |             
| Számlaérték               | 4, 1               |             
| Szállítási módok           | 1                  |           
| Tranzakció típusa            | 4, 1               |            
| Kötelezettség szintje            | 4, 1               |           
| Vámtarifakód              | 1                  |            
| Nemzeti NGP                | 1                  |            
| Nettó tömeg                  | 1                  |            
| Statisztikai érték           | 1                  |            
| Kiegészítő egységek            | 1                  |            
| Származási ország – importálások | 1                  |            
| Végső cél – Exportálások | 1                  |            
| Az ügyfél áfakódja        | 4, 1               |            
| Kiegészítő kód          | 4, 1               |           
| Hivatkozási időszak         | 4, 1               |         

### <a name="set-up-intrastat"></a>Intrastat beállítása

1.  A [Microsoft Dynamics Lifecycle Services (LCS)](https://lcs.dynamics.com/Logon/Index) szolgáltatásban, a Közös eszközök könyvtárából töltse le a legfrissebb verzióit a következő Elektronikus jelentéskészítési (ER) konfigurációkat az Intrastat nyilatkozathoz:

    - Intrastat modell
    - Intrastat jelentés
    - Intrastat INTRACOM (FR)
    - Intrastat SAISUNIC (FR)

    További tudnivalókért lásd: [Az elektronikus jelentési beállítások letöltése a Lifecycle Services rendszerből](../../fin-ops-core/dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md).

2.  A Dynamics 365 Pénzügy programban **kattintson** > **az Adóbeállítás** >  **– Külkereskedelmi** > **paraméterek** gombra, és hajtsa végre a következő lépéseket:

    1. Az **Intrastat** lapon az **Elektronikus jelentések** gyorslapon **Fájlformátum-hozzárendelés** mezőben válassza az **Intrastat INTRACOM (FR)** vagy az **Intrastat SAISUNIC (FR)** lehetőséget.
    2. A **Jelentésformátum-hozzárendelés** mezőben válassza az **Intrastat jelentés** lehetőséget.
    3. Az **Árucikk-kódok hierarchiája** gyorslapon a **Kategóriahierarchia** mezőben válassza az **Intrastat** lehetőséget.
    4. Az **Általános** gyorslap **Tranzakciókód** mezőjében válassza ki az áruk átvitelére használt kódot.
    5. A **Jóváírás** mezőben válassza ki az áruk visszaküldésére használt kódot.
    6. Az **Exportálási kötelezettség szintje** mezőbe írja be az exportjelentés részletességi szintjét. A kiválasztott szint hatással van a jelentésben megjelenő sorokra. A további tudnivalókat lásd a cikk elején található táblákban.

3. Menjen a **Szervezetfelügyelet** > **Szervezetek** > **Jogi személyek** részbe, válassza ki a vállalatot, majd hajtsa végre a következő lépéseket:

    1. A **Regisztrációs számok** gyorslapon a **NAF kód** mezőbe írja be a NAF-kódot. A további tudnivalókat lásd: [FR-00003 NAF-kódok és Siret-számok](tasks/fr-00003-naf-codes-siret-numbers.md).
    2. Az **Külkereskedelem és logisztika** gyorslap **Intrastat** szakaszában állítsa be az **Áfamentességi szám exportálása** és **Áfamentességi szám importálása** mezőket.
    3. Az **Adó regisztráció** gyorslapon, az **Adószám** mezőben adja meg a vállalata adószámát.

4. A vevők NAF-kódjainak és adószámának megadásához menjen a **Kinnlevőségek** > **Vevők** > **Minden vevő** részbe, és hajtsa végre a következő lépéseket:

    1. Válasszon vevőt.
    2. A **Számlázás és szállítás** gyorslapon, az **Áfa** szakaszban az **Adómentességi szám** mezőben adja meg az ügyfél adómentességi számát.
    3. Az **Értékesítés demográfia** gyorslapon a **Francia Siret** mezőben adja meg a vállalat Siret-számát.
    4. A **NAF kód** mezőben adja meg a vállalat NAF kódját.
    5. Ismételje meg ezeket a lépéseket a többi vevővel.

5. A szállítók NAF-kódjainak és adószámának megadásához menjen a **Kötelezettségek** > **Szállítók** > **Minden szállító** részbe, és hajtsa végre a következő lépéseket:

    1. Válasszon ki egy szállítót.
    2. A **Számlázás és szállítás** gyorslapon, az **Áfa** szakaszban az **Adómentességi szám** mezőben adja meg a szállító adómentességi számát.
    3. A **Beszerzési demográfia** gyorslapon a **Francia Siret** mezőben adja meg a vállalat Siret-számát.
    4. A **NAF kód** mezőben adja meg a vállalat NAF kódját.
    5. Ismételje meg ezeket a lépéseket a többi szállítóval.

6. Válassza az **Adó** > **Beállítások** > **Külkereskedelem** > **Intrastat tömörítése** menüpontot, és válassza ki azokat a mezőket, amelyeket össze kell hasonlítani az Intrastat-adatok összesítése során. Francia Intrastat esetében válassza a **Statisztikai eljárás**, **Származási állam**, **Származási ország/régió**, **Szállítási feltételek**, **Szállítás**, **Javítás**, **Ország/régió**, **Származási/cél megye**, **Irány**, a **Feladó országa/régiója**, **Feladó állama**, **Állam**, **Tranzakciókód** és az **Árucikk** lehetőségeket.

7. Menjen a **Raktárkezelés** > **Beállítás** > **Raktár** > **Raktárak** menübe, válasszon ki egy raktárat, majd hajtsa végre a következő lépéseket:

    1. Válassza a **Címek** gyorslapon a **Hozzáadás** vagy **Szerkesztés** lehetőséget.
    2. A párbeszédpanel **Város** mezőjében válassza ki a raktár városát. A DEB jelentéshez a város állama lesz használva megyének.

### <a name="ngp-codes"></a>NGP-kódok

A DEB jelentésben a termékek kódolása a következő elemekből áll:

  - Az Európai Unió tarifa- és statisztikai nómenklatúráját képviselő nyolcjegyű CN8-kód.
  - Ha van, akkor az egyjegyű Nomenclature Générale des Produits (NGP) nemzeti cikk-kód.

2021-ben az NGP csak háromféle terméktípusra vonatkozik:

  - Néhány termék, ami tehénből, birkából és kecskéből készül
  - Katonai eszközök
  - Francia borok

 Az NGP-kódokat be kell állítani, és hozzá kell rendelni a kapcsolódó termékekhez. A program ezután automatikusan beállít egy **NGP** mezőt az **Intrastat napló** oldalon.

#### <a name="set-up-an-ngp-code"></a>Állítson be egy NGP-kódot

1. Ugorjon az **Adó** > **Beállítás** > **Külkereskedelem** > **NGP kódok** pontra.
2. Jelölje be a műveleti ablakban az **Új** lehetőséget egy NGP-kód létrehozásához.
3. Az **NGP** mezőben adjon meg egy egyjegyű kódot.
4. A **Leírás** mezőbe írja be a kód leírását.

#### <a name="assign-an-ngp-code-to-a-product"></a>NGP kód hozzárendelése egy termékhez

1. Ugorjon a következőre: **Termékinformáció-kezelés** > **Termékek** > **Felszabadított termékek**.
2. A rácsban válasszon egy terméket.
3. Válassza ki a megfelelő NGP-kódot a **Külkereskedelem** gyorslap **Intrastat** szakaszában, az **NGP** mezőben.

## <a name="intrastat-journal"></a>Intrastat-napló

Az Eu-országokkal folytatott külkereskedelmi tranzakciók kezeléséhez menjen az **Adó** > **Bevallások** > **Külföldi** **kereskedelem** > **Intrastat** menübe. A további tudnivalókat lásd: [Intrastat áttekintése](emea-intrastat.md).

Az **NGP** oszlop Franciaországhoz specifikus. Megjeleníti az NGP kódot a termékhez. Ha az NGP nem alkalmazható egy termékre, **0** (nulla) jelenik meg. Az NGP-kód módosítható. Válassza ki a tranzakciót, majd az **Általános** lapon, a **Kódok** szakaszban, az **NGP** mezőben válassza ki a szükséges NGP-kódot.

### <a name="intrastat-transfer"></a>Intrastat-átvitel

Az **Intrastat** oldalon a műveleti panelen az **Átvitel** gombra kattintva automatikusan át lehet vinni az közösségen belüli kereskedelemre vonatkozó adatokat az értékesítési rendelésekből, a szabadszöveges számlákból, a beszerzési rendelésekből, a szállítói számlákból, a szállítói termékbevételezésekből, a projektszámlákból és az átátviteli rendelésekből. Csak azok a dokumentumok kerülnek átvitelre, amelyek célországa vagy -régiója (kiküldésekhez) vagy feladója (beérkezésekhez) egy EU-s ország.

Mivel a DEB jelentés az EU értékesítési lista és az Intrastat jelentés kombinációja, *háromszögügylet* tranzakciókat is tartalmaz, amelyekben az egyik EU országból (A fél) egy másik EU-országba (C fél) szállítják, és egy francia jogi személy (B fél) van a háromszögügylet központjában.

### <a name="generate-a-deb-intrastat-report"></a>DEB (Intrastat) jelentés készítése

1. Ugorjon a következőre: **Adó** > **Nyilatkozatok** > **Külkereskedelem** > **Intrastat**.
2. A Műveletpanelen válassza a **Kimenet** > **Jelentés** lehetőséget.
3. Az **Intrastat jelentés** párbeszédpanelen a következő mezőket állítsa be.

    | Mező            | Leírás                                                                                                                         |
    |------------------|-------------------------------------------------------------------------------------------------------------------------------------|
    | Kezdő dátum        | Válassza ki a jelentés kezdő dátumát.                                                                                               |
    | Záró dátum          | Válassza ki a jelentés befejező dátumát.                                                                                                 |
    | Fájl létrehozása    | Egy .txt fájl generálásához állítsa ezt a beállítást **Igen** értékre.                                                                                 |
    | Fájlnév        | Adja meg az Intrastat-jelentés .txt fájljának nevét.                                                                          |
    | Jelentés létrehozása  | Egy .xml fájl generálásához állítsa ezt a beállítást **Igen** értékre.                                                                                |
    | Jelentésfájl neve | Adja meg a szükséges nevet.                                                                                                            |
    | Csak helyesbítések | Az **Igen** értékre állítása esetén csak a helyesbítéseket jelenti. Állítsa **Nem** állapotra a normál tranzakciók és helyesbítések jelentéséhez.         |
    | Irány        | Válassza a **Beérkezések** lehetőséget a közösségen belüli beérkezésekkel kapcsolatos jelentésekhez. A közösségen belüli kiküldésekről szóló jelentéshez válassza a **Kiküldések** lehetőséget. |

## <a name="example"></a>Példa

A következő példa bemutatja, hogyan lehet beállítani a francia Intrastat-jelentést és létrehozni a DEB jelentést. A **DEMF** jogi személyt használja.

1. A [Microsoft Dynamics Lifecycle Services (LCS)](https://lcs.dynamics.com/Logon/Index) szolgáltatásban, a Közös eszközök könyvtárából töltse le a legfrissebb verzióit a következő Elektronikus jelentéskészítési (ER) konfigurációkat az Intrastat nyilatkozat formátumához:

    - Intrastat modell
    - Intrastat jelentés
    - Intrastat INTRACOM (FR)

2. A Pénzügyben állítson be egy tranzakciókódot:

    1. Ugorjon a következőre: **Adó** > **Beállítás** > **Külkereskedelem** > **Tranzakciókódok**.
    2. A Műveleti ablaktáblán kattintson az **Új** elemre.
    3. A **Tranzakciókód** mezőbe adja meg a **11** értéket.
    4. A **Név** mezőbe írja be a következőt: **Beszerzés vagy értékesítés**.
    5. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.

3.  Állítson be egy termékhierarchiát:

    1. Menjen a **Termékinformációk kezelése** > **Beállítás** > **Kategóriák és attribútumok** > **Kategóriahierarchiák** pontra.
    2. Válassza ki az **Intrastat** lehetőséget a rácsban. A Műveleti ablaktáblán a **Kategóriahierarchia** lapon a **Karbantartás** csoportban válassza a **Szerkesztés** lehetőséget.
    3. A Művelet panelen kattintson az **Új kategória-csomópont** elemre.
    4. A **Név** mezőbe írja be a következőt: **Autres Libournais**.
    5. A **Kód** mezőbe adja meg a **2204 21 42** értéket
    6. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.

4. Menjen az **Adó** > **Beállítás** > **Külkereskedelem** > **Külkereskedelmi paraméterek** menübe és kövesse az alábbi lépéseket.

    1. Az **Intrastat** lapon az **Általános** gyorslapon **Tranzakciókód** mezőben válassza a **11** kódot.
    2. Az **Elektronikus jelentés** gyorslap **Fájlformátum-hozzárendelés** mezőjében válassza az **Intrastat INTRACOM (FR)** lehetőséget.
    3. A **Jelentésformátum-hozzárendelés** mezőben válassza az **Intrastat jelentés** lehetőséget.
    4. Az **Árucikk-kódok hierarchiája** gyorslapon a **Kategóriahierarchia** mezőben válassza az **Intrastat** lehetőséget.

5. Állítson be egy NGP-kódot:

    1. Ugorjon az **Adó** > **Beállítás** > **Külkereskedelem** > **NGP kódok** pontra.
    2. A Műveleti ablaktáblán kattintson az **Új** elemre.
    3. Az **NGP** mezőben adja meg a **8** értéket.
    4. A **Leírás neve** mezőben adja meg az **NGP 8** értéket.
    5. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.

6. NGP kód hozzárendelése egy termékhez:

    1. Ugorjon a következőre: **Termékinformáció-kezelés** > **Termékek** > **Felszabadított termékek**.
    2. Válassza ki a **0001** értéket a rácsban.
    3. Az **Külkereskedelem** gyorslap **NGP** mezőjében válassza ki a **8** értéket.
    4. Az **Árucikk mezőben** válassza a **2204 21 42** értéket.
    5. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.

7. Hozzon létre egy értékesítési rendelést, amely tartalmazza az új terméket:

    1. Ugorjon a következőre: **Követelések** > **Rendelések** > **Minden értékesítési rendelés**.
    2. A Műveleti ablaktáblán kattintson az **Új** elemre.
    3. Az **Értékesítési** **rendelés** **létrehozása** párbeszédpanelen, a **Vevő**  szakaszban a **Vevői** **számla** mezőben válassza ki a **100001** értéket.
    4. A **Cím** szakaszban a **Szállítási cím** mezőben válassza a pluszjelet (**+**) egy cím létrehozásához.
    5. Az **Új cím** párbeszédpanelbe a **Leírás neve** mezőbe írja be a **Németország** értéket.
    6. Az **Ország/régió** mezőben válassza a **DEU** lehetőséget.
    7. Válassza ki az **OK** lehetőséget.
    8. Az **Értékesítési rendelés létrehozása** párbeszédpanelen válassz az **OK** lehetőséget.
    9. Az **Értékesítésirendelés** **sorok** gyorslap **Cikkszám** mezőjében válassza a **0001** elemet.
    10. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.
    11. A Műveleti ablaktábla **Számla** lapján a **Létrehozás** csoportban válassza a **Számla** lehetőséget.
    12. A **Számlafeladás** párbeszédpanel **Paraméterek** gyorslapján, a **Paraméter** szakaszban a **Mennyiség** mezőben válassza az **Összes** lehetőséget. Ezután válassza az **OK** lehetőséget a számla feladásához.

8.  DEB jelentés létrehozása:

    1. Ugorjon az **Adó** > **Nyilatkozatok** > **Külkereskedelem** > **Intrastat** pontra:
    2. A Műveleti ablaktáblán. válassza az **Átvitel** elemet.
    3. Az **Intrastat (Átvitel)** párbeszédpanel **Paraméterek** szakaszában állítsa a **Vevői számla** beállítást **Igen** beállításra. Majd kattintson az **OK** lehetőségre.
    4. Tranzakciók rendezése a **Dátum** mező szerint. A legfelső tranzakció az eredménytranzakció. Az **NGP** mező beállítása automatikus.
    5. A műveleti ablaktáblán válassza a **Kimenet** &gt; **Jelentés** lehetőséget.
    6. Az **Intrastat jelentés** párbeszédpanelen, a **Paraméterek** gyorslapona a **Dátum** szakaszban válassza ki a létrehozott értékesítési rendelés hónapját.
    7. Az **Exportálási beállítások** szakaszban állítsa **Igen** értékre a **Fájl létrehozása** beállítást.
    8. A **Fájlnév** mezőben adja meg a szükséges nevet.
    9. Kattintson az **OK** gombra, és tekintse át a létrehozott jelentést.

