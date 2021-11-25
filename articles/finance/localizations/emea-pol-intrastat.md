---
title: Lengyelország – Intrastat
description: Ez a témakör a lengyelországi Intrastat-jelentéskészítéssel kapcsolatban tartalmaz tájékoztatást.
author: andosip
ms.date: 11/09/2021
ms.topic: article
audience: Application User
ms.reviewer: kfender
ms.search.region: Global
ms.author: v-aosipov
ms.search.validFrom: ''
ms.openlocfilehash: 9564892f768adb8f48208fe10b31c7c6392a4567
ms.sourcegitcommit: f4823a97c856e9a9b4ae14116a43c87f9482dd90
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/09/2021
ms.locfileid: "7779907"
---
# <a name="polish-intrastat"></a>Lengyelország – Intrastat

[!include[banner](../includes/banner.md)]

Az **Intrastat** oldalon információkat generálhat és jelenthet az Európai Unió országaival folytatott kereskedelemről. A lengyel Intrastat nyilatkozat a jelentéskészítéshez szükséges árukereskedelemről tartalmaz információkat.

A következő mezők a lengyel Intrastat nyilatkozatban szerepelnek. Minden mező az érkezéseken és a kiszállításokon szerepel, kivéve a **RodzajTransportu (a szállítási mód) és** a NyelvjPochodzenia (származási ország vagy régió), amely nem szerepel az elküldésekben, valamint az **·** **IdKontrahenta** (a vevő külföldi áfaszáma), amely nem szerepel az érkeztetéseken.

| Mezőnév | Leírás |
|-------------------------|-------------------------|
| Deklaracja adatok | A dokumentum létrehozási dátuma. |
| Miesiac | A bevallás hivatkozási hónapja. |
| Rok | A bevallás hivatkozási éve. |
| Szám | A nyilatkozat száma a hivatkozási időszakban. |
| Wersja | A bevallás verziószáma |
| NrWlasny | A nyilatkozat azonosítója. A program automatikusan generálja az értéket. |
| Typ | A jelentés iránya.</br><li>Az érkezések esetén a program a "P" címkét nyomtatja ki.</li><li>Elküldésekhez a program a "W" címkét nyomtatja.</li> |
| Rodzaj | A bevallás típusa Ez az érték jelzi, hogy a jelentés eredeti bevallás vagy javítás. |
| UC | Az az egységkód, amelybe az Intrastat nyilatkozat címzettje kerül. Az érték a Külkereskedelmi paraméterek lap Ügynök lapjának Áfa szakaszában található Adószám **·** **·** **·** **mezőben van** megadva. |
| Nazwa | A vállalat neve. |
| Miejscoowsc, UlnumerNumer,Ponumertowy | A jogi személy teljes címe. |
| Nip | A lengyel adóazonosító szám (áfa [ÁFA] azonosítója). |
| Regon | A lengyel statisztikai azonosító (vállalatszám). |
| AlmaznaWartoscFakala | A számlaértékek összege. |
| NaplóznaWartoscStatystyalana | A statisztikai értékek összege. |
| TatnaLiczbaPo éscdzsi | Áruk áruinak száma összesen. |
| PozId | Az adott áru egymást követő száma. |
| OpisTowru | Az árucikk kereskedelmi neve. |
| VanjPochodzeniaWysíróki | A megfelelő országának vagy régiójának ISO-kódja (International Organization for Standardization– ISO-kód). |
| WarunkiDostawy | A szállítási feltételek Intrastat-kódja. |
| RodzajTransakcdzs | A tranzakció jellegére utaló kód. A lengyel vállalatok kétjegyű tranzakciókódokat használnak. |
| Leszűkk van a 2015-2019 | A Kombinált Nomenclature szerinti nyolcjegyű vámtarifakód. |
| RodzajTransportu | A szállítási mód Intrastat-kódja. |
| VanjPochodzenia | Annak az országnak vagy területnek az ISO-kódja, ahol az árucikkeket termelték vagy gyártották. |
| MrinNetto | A nettó tömeg teljes kilogrammban. |
| IloscUzupelniajacaJm | A kiegészítő mértékegységben szereplő mennyiség egész számmal. |
| SkarttoscFakalay | Az egy cikk által fedezett összes tranzakció számlázási értéke. |
| TattoscStatystyalana | A statisztikai érték. |
| Isztenniajacy: NazwiskoIuláció, Telefon, Faks, E-mail | A nyilatkozatot beküldő személy vezeték- és telefonszáma, faxszáma és e-mail címe. |
| IdKontrahenta | A vevő külföldi áfaszáma EU-tagországban. |


## <a name="set-up-intrastat"></a>Intrastat beállítása

Importálja a globális tárházból a következő elektronikusjelentés-konfigurációk legújabb verzióját:

   - Intrastat modell
   - Intrastat jelentés
   - Intrastat (PL)

További információért lásd: [ER-konfigurációk letöltése a Konfigurációs szolgáltatás globális tárolójából](../../fin-ops-core/dev-itpro/analytics/er-download-configurations-global-repo.md).

## <a name="set-up-a-vat-id-and-an-enterprise-number-for-your-company"></a>Állítsa be a vállalat áfaazonosítóját és vállalatszámát.

### <a name="create-registration-types-for-company-codes"></a>Regisztrációs típusok létrehozása vállalati kódokhoz

Két regisztrációs típust kell létrehozni a vállalati kódokhoz: egyet az áfaazonosítóhoz (NIP-kód), egyet a vállalatszámhoz (Regon-kód).

1. Ugrás a **Szervezetfelügyelet** > **globális címjegyzék** > **regisztrálási** > **típusainak regisztrálási** típusaihoz.
2. A munkaablakban az Új gombra kattintva hozzon létre egy regisztrációs **·** típust az áfaazonosítóhoz.
3. A Regisztrációtípus részletei párbeszédpanel Név mezőjébe írja **·** be az új **·** regisztrációtípus nevét. Megadhatja például az **NIP-t.**
4. Az **Ország/régió** mezőben válassza a **POL** lehetőséget.
5. Válassza a **Létrehozása** lehetőséget.
6. A munkaablakban válassza az **Új** lehetőséget, ha regisztrációs típust hoz létre a vállalatszámhoz.
7. A Regisztrációtípus részletei párbeszédpanel Név mezőjébe írja **·** be az új **·** regisztrációtípus nevét. Adja meg például a **Regon adhatja** meg.
8. Az **Ország/régió** mezőben válassza a **POL** lehetőséget.
9. Válassza a **Létrehozása** lehetőséget.

### <a name="match-the-registration-types-with-registration-categories"></a>A regisztrációtípusok egyeztetése a regisztrációs kategóriákkal

1. Ugrás a **Szervezetfelügyelet** > **globális címjegyzék** > **regisztrálási** > **típusainak regisztrálási kategóriáihoz.**
2. A műveletpanel Új beállításának használatával hozzon létre kapcsolatot minden létrehozott regisztrációs típus **és egy regisztrációs kategória** között.

    - Az áfaazonosító (NIP-kód) regisztrációs típusának **·** kiválasztása.
    - A vállalatszám (Regon-kód) regisztrációtípusa esetén válassza ki a VÁLLALATI **azonosító (COID)** regisztrációs kategóriát.

### <a name="set-up-a-vat-id-and-an-enterprise-number-for-your-company"></a>Állítsa be a vállalat áfaazonosítóját és vállalatszámát.

1. Nyissa meg a következőt: **Szervezetek adminisztrációja** > **Szervezetek** > **Jogi személyek**.
2. A rácson válassza ki a vállalatot.
3. A munkaablakban válassza ki **a Regisztrációs adatok** lehetőséget.
4. Válassza a Hozzáadás lehetőséget a Regisztrációs **·** azonosító **gyorsgombra.**
5. A Regisztráció típusa mezőben válassza ki a korábban létrehozott **·** regisztrációtípusok valamelyikét.
6. Adja meg a vállalat áfaazonosítóját (NIP-kód) vagy vállalatszámát (Regon-kód), az előző lépésben kiválasztott regisztrációs típustól függően.
7. Ismételje meg a 4–6. lépést a korábban létrehozott többi regisztrációtípussal.

## <a name="set-up-a-company-address"></a>Vállalati cím beállítása

1. Nyissa meg a következőt: **Szervezetek adminisztrációja** > **Szervezetek** > **Jogi személyek**.
2. A rácson válassza ki a vállalatot.
3. A Címek **lapon válassza a Szerkesztés** **·** lehetőséget.
4. A Cím szerkesztése párbeszédpanel Irányítószám mezőjében válassza ki a vállalat **·** **·** irányítószámát.
5. Az Utca **·** mezőben adja meg a címét.
6. A Város **·** mezőben válassza ki a települést.

## <a name="set-up-foreign-trade-parameters"></a>Külkereskedelmi paraméterek beállítása

1. Ugrás az **Adóbeállítás** > **·** > **külkereskedelmi paramétereihez**
2. Az Intrastat lap Elektronikus jelentés gyorslap Fájlformátum-hozzárendelés mezőjében válassza az **·** **·** **·** **Intrastat (PL)** lehetőséget.
3. A **Jelentésformátum-hozzárendelés** mezőben válassza az **Intrastat jelentés** lehetőséget.
4. Az **Árucikk-kódok hierarchiája** gyorslapon a **Kategóriahierarchia** mezőben válassza az **Intrastat** lehetőséget.
5. A **Tranzakciókód** mezőben válassza ki a vagyonátruházáshoz létrehozott tranzakciókódot. Ezt a kódot olyan tranzakciókra használja, amelyek tényleges vagy tervezett tulajdonátruházást eredményeznek (pénzügyi vagy egyéb) ellenszolgáltatás ellenében. Javításra is használható. A lengyelországi vállalatok kétjegyű tranzakciókódokat használnak.
6. A **Jóváírási megjegyzés** mezőben válassza ki az áruk visszaküldésének tranzakciós kódját.
7. Az **Ország/régió tulajdonságai** lapon az **Ország/régió** mezőben sorolja fel azokat az országokat vagy régiókat, amelyekkel a vállalata üzleti kapcsolatban áll. Az Európai Unióba országonként válassza ki az EU-t az Ország/terület típus mezőben, hogy az ország megjelenjen az **·** **·** Intrastat-jelentésben. Lengyelország esetében válassza a **Belföldi** lehetőséget az **Ország/terület típus** mezőben.
8. Az Ügynök lap Áfa szakaszÁnak Ügynök gyorslapján adja meg a **·** **·** **·** **·** **4200000 számot az** Adószám mezőben, hogy milyen egységkódra vonatkozik az Intrastat nyilatkozat.
9. Adja meg a nyilatkozatot küldő személy nevét, telefonszámát, faxszámát és e-mail címét a Kapcsolattartó **·** lapon.
10. Az **XML-fájlszám-hivatkozás Számsorozatkód mezőjében a Számsorozatok lapon adjon meg egy nem folytonos számsorozatot, amely legfeljebb** **kilenc karaktert** **·** tartalmazhat. Ez a mező az Intrastat jelentés Deklarációazonosító mezőjének automatikus **·** előállítására használható.

## <a name="set-up-product-parameters-for-the-intrastat-declaration"></a>Termékparaméterek beállítása az Intrastat nyilatkozathoz

1. Ugorjon a következőre: **Termékinformáció-kezelés** > **Termékek** > **Felszabadított termékek**.
2. A rácsban válasszon egy terméket.
3. A **Külkereskedelmi** gyorslapon az **Intrastat** szakaszban az **Áru** mezőben válassza ki az árukódot. Az intrastat jelentés Vámtarifó leírása mezőjébe a program be fogja nyomtatni az **·** árucikk nevét.
4. Az Eredet terület Ország/terület mezőjében válassza ki a termék származási **·** **·** országát vagy régióját.
5. A **Készlet kezelése** gyorslapon a **Nettó súly** mezőben adja meg a termék súlyát kilogrammban.

## <a name="set-up-compression-of-intrastat"></a>Intrastat tömörítésének beállítása

-   Válassza az **Adó** > **Beállítások** > **Külkereskedelem** > **Intrastat tömörítése** menüpontot, és válassza ki azokat a mezőket, amelyeket össze kell hasonlítani az Intrastat-adatok összesítése során. Lengyel Intrastathoz válassza a következő mezőket:

    - Árucikk
    - Tranzakció kódja
    - Származási ország/régió
    - Átvitel
    - Szállítási feltételek
    - Feladó országa/régiója
    - Ország/régió
    - Korrekció
    - Adómentességi szám
    - Irány
    - Számla

## <a name="set-up-the-transport-method-and-delivery-terms"></a>Szállítási mód és szállítási feltételek beállítása

1.  Szállítási kódok beállítása.

    1. Menjen az **Adó** > **Beállítás** > **Külkereskedelem** > **Szállítási mód** pontra.
    2. A Műveleti ablaktáblán kattintson az **Új** elemre.
    3. A **Szállítás** mezőbe írjon be egy egyedi kódot. A lengyel vállalatok egy számjegyű szállítási kódokat használnak.

2.  Intrastat-kódok szállítási módjának beállítása.

    1. Ugrás **a Beszerzés és forrás beállításai** > **– Szállítási** > **feltételek** > **·** gombra.
    2. A rácson válasszon ki egy szállítási feltételkészletet.
    3. Az Általános **·** gyorssablon **Intrastat-kód mezőjébe írja be** az egyedi kódot.

## <a name="intrastat-transfer"></a>Intrastat-átvitel

Az **Intrastat** oldalon a műveleti panelen az **Átvitel** gombra kattintva automatikusan át lehet vinni az közösségen belüli kereskedelemre vonatkozó adatokat az értékesítési rendelésekből, a szabadszöveges számlákból, a beszerzési rendelésekből, a szállítói számlákból, a szállítói termékbevételezésekből, a projektszámlákból és az átátviteli rendelésekből. Csak azok a dokumentumok kerülnek átvitelre, amelyek rendeltetési vagy kiszállítmányi országként egy EU-országban vannak.

A tranzakciók manuálisan is beírhatók, ha a **·** munkaablakban az Új lehetőséget választják.

### <a name="generate-an-intrastat-report"></a>Intrastat jelentés készítése

1. Ugorjon a következőre: **Adó** > **Nyilatkozatok** > **Külkereskedelem** > **Intrastat**.
2. A műveleti ablaktáblán válassza a **Kimenet** &gt; **Jelentés** lehetőséget.
3. Az **Intrastat jelentés** párbeszédpanelen a következő mezőket állítsa be.

    | Mező | Leírás |
    |-------------------------|-------------------------|
    | Kezdő dátum | Válassza ki a jelentés kezdő dátumát. |
    | Fájl létrehozása | A beállítás Igen **·** beállítással .xml fájlt generálhat az Intrastat-jelentéshez. |
    | Fájlnév | Az .xml fájl nevének beírásakor. |
    | Jelentés létrehozása | Állítsa ezt az opciót **Igenre**, ha .xlsx fájlt szeretne generálni az Intrastat jelentéshez. |
    | Jelentésfájl neve | Adja meg az .xlsx fájl nevét. |
    | Irány | Válassza a **Beérkezések** lehetőséget a közösségen belüli beérkezésekkel kapcsolatos jelentésekhez.</br>A közösségen belüli kiküldésekről szóló jelentéshez válassza a **Kiküldések** lehetőséget. |
    | Bevallás azonosítója | A dokumentumazonosító generálása automatikusan történik, és frissíthető. |
    | Nyilatkozat típusa | Eredeti **·** bevallás bevallásának kiválasztása.</br>Nyilatkozatkorrekció kiválasztása – egy korrekciós nyilatkozat helyettesítése, amely egy meglévő, korábban benyújtott eredeti vagy javítási nyilatkozat **·** teljes helyettesítésére szolgál. |
    | Bizonylat készítésének helye (város) | Adja meg az Intrastat nyilatkozat **Miejscosc mezőjébe nyomtatandó** értéket. |
    | Bizonylat készítésének dátuma | Adja meg az Intrastat nyilatkozat **Deklaracja Adatok mezőjében nyomtatandó** értéket. |
    | Dokumentum száma | Adja meg az Intrastat nyilatkozat Szám mezőjében nyomtatandó **·** értéket. |
    | Dokumentum verziója | Adja meg az Intrastat nyilatkozat Wersja mezőjében nyomtatandó **·** értéket. |

4. Válassza az **OK** lehetőséget, és tekintse át a generált jelentéseket.

## <a name="example"></a>Példa

Ebben a példában a DEMF jogi személy használatával lehet az Intrastathoz érkezések és **·** elküldések feladását bemutatja.

### <a name="preliminary-setup"></a>Előzetes beállítás

Importálja a következő ER-konfigurációk legújabb verzióját:

   - Intrastat modell
   - Intrastat jelentés
   - Intrastat (PL)

### <a name="set-up-a-company-address"></a>Vállalati cím beállítása

1. Lépjen a **Szervezet adminisztráció** > **Globális címjegyzék** > **Címek** > **Címbeállítás** menüpontra.
2. A Város **lapon válassza az Új** **·** lehetőséget.
3. Az **Ország/régió** mezőben válassza a **POL** lehetőséget.
4. A Város **·** mezőben adja meg **a 2012 2005 000 000**
5. Az **Irányítószám lapon** válassza az Új **·** lehetőséget.
6. Az **Ország/régió** mezőben válassza a **POL** lehetőséget.
7. A Város **·** mezőben válassza a **Kijelölés** lehetőséget.
8. Az Irányítószám mezőbe írja be **·** a **00-844számot.**
9. Lépjen a **Szervezeti adminisztráció** > **Szervezet** > **Jogi személyek** menüpontba, és válassza ki a **DEMF** jogi személyt.
10. A **Címek** gyorslapon válassza a **Szerkesztés** lehetőséget.
11. Az **Ország/régió** mezőben válassza a **POL** lehetőséget.
12. Az **Irányítószám** mezőben válassza a **31-111-es lehetőséget**.
13. Az Utca mezőbe írja be **·** a **Statystytipna 22/1 mezőt**.
14. A Város **·** mezőben válassza a **Kijelölés** lehetőséget.
15. Válassza ki az **OK** lehetőséget.

## <a name="set-up-a-vat-id-and-an-enterprise-number-code-for-your-company"></a>Állítsa be a vállalat áfaazonosítóját és vállalatszámát.

### <a name="create-registration-types-for-company-codes"></a>Regisztrációs típusok létrehozása vállalati kódokhoz

1. Ugrás a **Szervezetfelügyelet** > **globális címjegyzék** > **regisztrálási** > **típusainak regisztrálási** típusaihoz.
2. A műveletpanel Új beállításával hozzon létre egy regisztrációs **·** típust az áfaazonosítóhoz (NIP-kód).
3. A Regisztrációs típus részletei párbeszédpanel Név mezőjébe írja be a **·** **·** **NIP** adatokat.
4. Az **Ország/régió** mezőben válassza a **POL** lehetőséget.
5. Válassza a **Létrehozása** lehetőséget.
6. A munkaablakban válassza az Új lehetőséget, ha regisztrációs típust hoz létre a vállalatszámhoz **·** (Regonkód).
7. A Regisztrációs típus részletei párbeszédpanel Név mezőjébe írja be a **·** **·** **Regon** adatokat.
8. Az **Ország/régió** mezőben válassza a **POL** lehetőséget.
9. Válassza a **Létrehozása** lehetőséget.

### <a name="match-the-registration-types-with-registration-categories"></a>A regisztrációtípusok egyeztetése a regisztrációs kategóriákkal

1. Ugrás a **Szervezetfelügyelet** > **globális címjegyzék** > **regisztrálási** > **típusainak regisztrálási kategóriáihoz.**
2. A műveletpanel Új beállításának használatával hozzon létre kapcsolatot minden létrehozott regisztrációs típus **és egy regisztrációs kategória** között.

    - Az **adószámok** regisztrációtípusa esetén válassza ki az **áfaazonosító** regisztrációjának kategóriáját.
    - A **Regon** regisztrációtípushoz válassza ki a **Vállalatazonosító (COID)** regisztrációs kategóriát.

### <a name="set-up-a-vat-id-and-an-enterprise-number-for-your-company"></a>Állítsa be a vállalat áfaazonosítóját és vállalatszámát.

1. Nyissa meg a következőt: **Szervezetek adminisztrációja** > **Szervezetek** > **Jogi személyek**.
2. Válassza ki a rácson a **DEMF**-et.
3. A munkaablakban válassza ki **a Regisztrációs adatok** lehetőséget.
4. Válassza a Hozzáadás lehetőséget a Regisztrációs **·** azonosító **gyorsgombra.**
5. A Regisztráció **típusa** mezőben válassza a **NIP** lehetőséget.
6. A Regisztrációs szám mezőbe írja be **a** **·** 1234567890.
7. Válassza a **Hozzáadás** lehetőséget.
8. A Regisztráció **típusa** mezőben válassza a **Regon** lehetőséget.
9. A Regisztrációs szám mezőbe írja be a **·** **·** 12345678901234.

### <a name="set-up-a-number-sequence-code"></a>Számsorozatkód beállítása

1. Menjen a **Szervezeti adminisztráció** > **Számsorozatok** > **Számsorozatok** pontra.
2. A Műveletpanel Számsorozat lapján, az Új csoport csoportban **·** válassza a **·** **Számsorozat** lehetőséget.
3. Adja meg az XML-fájlt az Azonosító gyorstábla **·** **Számsorozatkód** **\_** mezőjében.
4. Jelölje be a Vállalat gombra a Hatókör paraméterei **·** gyorsmezőBen a Hatókör **·** **·** mezőben.
5. A Vállalat **·** mezőben válassza a **DEMF** et.
6. Adja meg **a** 4-et a Szegmensek gyorsgombra vonatkozó Alfanumerikus szegmens Hossz **·** **·** **·** mezőjében.
7. A Beállítás szakasz Általános gyorsgombgombján állítsa a Nem **·** **·** **·** gombra a Folytonos **·** beállítást.
8. A Legnagyobb mező Szám kiosztás szakaszában adja meg **·** a **·** **9999-es** számot.

### <a name="set-up-foreign-trade-parameters"></a>Külkereskedelmi paraméterek beállítása

1. Ugorjon a következőre: **Adó** > **Beállítások** > **Külkereskedelem** > **Külkereskedelmi paraméterek**.
2. Az **Intrastat** lapon az **Általános** gyorslapon a **Tranzakció** **kód** mezőben válassza a **11**-et.
3. Az Elektronikus jelentés gyorsjelentések gyorsjelentésének Fájlformátum-hozzárendelés mezőjében válassza **·** az **·** **Intrastat (PL)** lehetőséget.
4. A **Jelentésformátum hozzárendelése** mezőben válassza az **Intrastat-jelentés** lehetőséget.
5. Az **Árucikk-kódok hierarchiája gyorssablonban ellenőrizze, hogy a** **Kategóriahierarchia mező** beállítása **·** Intrastat.
6. Az **Ország/régió tulajdonságai** lapon válassza az **Új** lehetőséget.
7. A **Fél országa/régiója** mezőben válassza az **POL** értéket. Ezután az **Ország/régió típus** mezőjében válassza a Belföldi **·** lehetőséget.
8. A **Fél országa/régiója** mezőben válassza az **DEU** értéket. Ezt követően az **Ország/régió típus** mezőjében válassza az **EU** lehetőséget.
9. Adja meg az Ügynök lap Áfa területének **·** **·** **·** **·** **4200000** mezőjében az Ügynök gyorslapon.
10. Adja meg a Kapcsolattartó **·** lap Név **·** mezőjében a **ManishLcra** mezőt.
11. A **Telefon mezőben adja meg** a **·** 425-555-5068.
12. A **Faxszám mezőbe írja be** a **·** 425-555-5049.
13. Az **E-mail mezőben adja meg** a **·** manishc@contoso.com.
14. Válassza ki az XML-fájlt a Számsorozatok lap Xml-fájlhivatkozás Számsorozatkód **·** **·** **·** **\_** mezőjében.

### <a name="set-up-product-information"></a>Termékinformációk beállítása

1. Ugrás a **Termékinformáció-kezelési** > **Termékek kiadott** > **·** **·** termékeihez.
2. Válassza ki a rácson a **D0001**-et.
3. A **Külkereskedelem** gyorslapon az **Intrastat** szakaszban, az **Árucikk** mezőben válassza a **100 200 30** kódot.
4. A **Készletkezelés** gyorslapon a **Súlymérések** szakaszban a **Nettó súly** mezőbe írja be a **2** értéket.
5. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.
6. Válassza ki a rácson a **D0003**-et.
7. A **Külkereskedelem** gyorslapon az **Intrastat** szakaszban, az **Árucikk** mezőben válassza a **100 200 30** kódot.
8. A **Származás** szakaszban az **Ország/régió** mezőben válassza a **DEU** beállítást.
9. A **Készletkezelés** gyorslapon a **Súlymérések** szakaszban a **Nettó súly** mezőbe írja be a **5** értéket.
10. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.

### <a name="change-the-site-address"></a>A webhely címének módosítása

1. Menjen a **Raktárkezelés** > **Beállítás** > **Raktár** > **Oldalak** pontra.
2. Válassza ki a **1** értéket a rácsban.
3. A **Címek** gyorslapon válassza a **Szerkesztés** lehetőséget.
4. A **Cím szerkesztése** párbeszédpanelen az **Ország/régió** mezőben válassza ki a **POL** lehetőséget.
5. Válassza ki az **OK** lehetőséget.

### <a name="set-up-a-transport-method"></a>Szállítási mód beállítása

1. Hozzon létre egy szállítási módot.

    1. Menjen az **Adó** > **Beállítás** > **Külkereskedelem** > **Szállítási mód** pontra.
    2. A Műveleti ablaktáblán kattintson az **Új** elemre.
    3. A **Szállítás mezőbe** írja be a **3-ast.**
    4. A Leírás **·** mezőben adja meg **a Fuvarozás** mezőt.

2. Az új szállítási mód hozzárendelése szállítási módhoz. Ezzel a módszerrel lehet beállítani a szállítási módhoz a megfelelő szállítási mód kiválasztásakor használt alapértelmezett értékeket.

    1. Ugorjon a következőre: **Beszerzés és forrás** > **Beállítás** > **Forgalmazás** > **Szállítási módok**.
    2. Válassza ki a **10** értéket a rácsban.
    3. A **Külkereskedelem** gyorslapon a **Szállítás** mezőben válassza a **3** értéket.

3. A vevő alapértelmezett szállítási módjának kiválasztása.

    1. Menjen a **Követelések** > **Ügyfelek** > **Minden ügyfél** pontra.
    2. A rácsban válassza a **DE-016** et.
    3. Válassza a **·** **10-et a Számlázási és kézbesítési gyorsgombra a Szállítási mód** **·** mezőben.

4. A szállító alapértelmezett szállítási módjának kiválasztása.

    1. Ugrás **a Kötelezettségek** > **szállítóihoz –** > **Minden** szállító.
    2. A rácsban válassza a **DE-001** et.
    3. Válassza a **·** **10-et a Számlázási és kézbesítési gyorsgombra a Szállítási mód** **·** mezőben.

### <a name="set-up-codes-for-terms-of-delivery"></a>Szállítási feltételek kódjainak beállítása

1. Intrastat-kód beállítása a szállítási feltételekhez.

    1. Ugrás **a Beszerzés és forrás beállításai** > **– Szállítási** > **feltételek** > **·** gombra.
    2. Válassza ki a rácson a **CIF**-et.
    3. Az Általános gyorssablon Intrastat kód mezőjébe írja be a **·** **·** **CIF** kódot.

2. A vevőre vonatkozó alapértelmezett szállítási feltételek kiválasztása.

    1. Menjen a **Követelések** > **Ügyfelek** > **Minden ügyfél** pontra.
    2. A rácsban válassza a **DE-016** et.
    3. Válassza a CIF gombra a Szállítási feltételek mező Számla és szállítás **·** **·** gyorsétét **·** gombra.

3. Válassza ki a szállító alapértelmezett szállítási feltételeit.

    1. Ugrás **a Kötelezettségek** > **szállítóihoz –** > **Minden** szállító.
    2. A rácsban válassza a **DE-001** et.
    3. Válassza a CIF gombra a Szállítási feltételek mező Számla és szállítás **·** **·** gyorsétét **·** gombra.

### <a name="verify-an-eu-customers-tax-exempt-number-code"></a>Eu-vevő adószámának ellenőrzése

1. Menjen a **Követelések** > **Ügyfelek** > **Minden ügyfél** pontra.
2. A rácsban válassza a **DE-016** et.
3. Ellenőrizze a Számla és szállítás gyorsétét az Áfa szakaszban, hogy az Adószám mező beállítása **·** **·** **·** **DE9012.**

### <a name="create-a-sales-order-with-an-eu-customer"></a>Értékesítési megbízás létrehozása egy EU-s ügyféllel

1. Ugorjon a következőre: **Követelések** > **Rendelések** > **Minden értékesítési rendelés**.
2. A Műveleti ablaktáblán kattintson az **Új** elemre.
3. Az **Értékesítési megbízás létrehozása** párbeszédpanelen, a **Vevő** gyorslapon, a **Vevő** szakaszban, az **Vevői számla** mezőben válassza a **DE-016** lehetőséget.
4. Az **Általános** gyorslapon, a **Tárolási dimenziók** szakaszban, a **Telephely** mezőben válassza az **1** értéket.
5. A **Raktár** mezőben válassza ki az **11** értéket.
6. A Cím lapon ellenőrizze, hogy a Cím mezőben a **·** **·** **Tebulgasse 12, Kiel, 24103, DEU beállítás van-e meg, mivel a vevő** Németországból van.
7. Válassza ki az **OK** lehetőséget.
8. A Szállítás gyorslap Fejléc lapján ellenőrizze, hogy a Szállítási feltételek mező beállítása CIF, a Szállítási mód mezőben **·** **pedig** **·** **·** **·** **10.**
9. A **Sorok** lapon, az **Értékesítési megbízás sorai** gyorslapon a **Tételszám** mezőben válassza a **D0001-et**. Ezután a **Mennyiség** mezőbe írjon be **8**-et.
10. A Külkereskedelem lap Sor részletei gyorslapján ellenőrizze, hogy a Tranzakciókód mező beállítása **·** **·** **·** **11,** **·** **·** **·** **·** az Árucikk mező beállítása 100 200 30, az Származási ország/terület mező beállítása POL.
11. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.
12. A Műveleti ablaktábla **Számla** lapján a **Létrehozás** csoportban válassza a **Számla** lehetőséget.
13. A **Számlafeladás** párbeszédpanel **Paraméterek** gyorslapján, a **Paraméter** szakaszban a **Mennyiség** mezőben válassza az **Összes** lehetőséget.
14. Válassza a **·** **·** **2021. október 10. 18-át** (2021. október 18. ).
15. A számla könyveléséhez válassza az **OK** lehetőséget.

### <a name="transfer-the-transaction-to-the-intrastat-journal-and-review-the-result"></a>A tranzakció átvezetése az Intrastat naplóba, és az eredmény áttekintése

1. Ugorjon a következőre: **Adó** > **Nyilatkozatok** > **Külkereskedelem** > **Intrastat**.
2. A Műveletpanelen válassza az **Átvitel** lehetőséget.
3. Az **Intrastat (Átvitel)** párbeszédpanel **Paraméterek** szakaszában állítsa a **Vevői számla** beállítást **Igen** beállításra.
4. Válassza ki a **Szűrő** elemet.
5. Az Intrastat-szűrő párbeszédpanel Tartomány lapján jelölje ki az első sort, és ellenőrizze, hogy a Mező mező beállítása **·** **·** **·** **·** Dátum.
6. A **Kritériumok** mezőben válassza ki az aktuális dátumot.
7. Válassza az **OK** gombot az **Intrastat-szűrő** párbeszédpanel bezárásához.
8. Válassza az **OK** gombot az **Intrastat (Átvitel)** párbeszédpanel bezárásához, és tekintse meg az eredményt. A sor a korábban létrehozott értékesítési rendelést jelöli.

    ![Az Intrastat-lapon az értékesítési rendelést jelképező sor](media/intrastat_pl_1.png)

9. Válassza ki a tranzakciós sort, majd válassza az **Általános** lapot a további részletek megtekintéséhez.

    ![Értékesítési rendelés részletei az Intrastat oldal Általános lapján](media/intrastat_pl_2.png)

10. A Műveletpanelen válassza a **Kimenet** > **Jelentés** lehetőséget.
11. Az **Intrastat jelentés párbeszédpanelEn, a Paraméterek gyorspanel Dátum szakaszában, a Dátum mezőben válassza ki az aktuális hónap első** **·** **·** **·** napját.
12. Az **Exportálási** **lehetőségek** szakaszban állítsa a **Fájl létrehozása** opciót **Igen**-re. Ezután a **Fájlnév** mezőbe írja be a kívánt nevet.
13. Állítsa a **Jelentés készítése** opciót **Igenre**. Ezután a **Jelentésfájl neve** mezőbe írja be a kívánt nevet.
14. Az **Irány** mezőben válassza a **Küldemények** lehetőséget.
15. A **Fájlformátum-leképezés szakaszban ellenőrizze, hogy a** Nyilatkozat típusa mező beállítása **·** **Deklaráció.**
16. A **Bizonylatok városának létrehozása** mezőben adja meg **a Írnikow** mezőt.
17. A Dokumentum létrehozásának dátuma mezőben válassza **·** a **19. 10-et** (2021. október 19.).
18. A Bizonylat **no** mezőjébe írja be a **11-et.**
19. A **Dokumentumverzió** mezőben adja meg a **22-es** et.
20. Válassza az OK gombra, és tekintse át a jelentést a létrehozott **·** XML-formátumban. A következő táblázat a példajelentésben szereplő értékeket mutatja.

    <table>
    <tbody>
    <tr>
    <td>
    <p><strong>Mezőnév</strong></p>
    </td>
    <td>
    <p><strong>Mező leírása</strong></p>
    </td>
    <td>
    <p><strong>Érték</strong></p>
    </td>
    </tr>
    <tr>
    <td colspan="3">
    <p><strong>A dokumentummal kapcsolatos információk</strong></p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Deklaracja adatok</p>
    </td>
    <td>
    <p>A dokumentum létrehozási dátuma.</p>
    </td>
    <td>
    <p>2021-10-19</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Vegyes</p>
    </td>
    <td>
    <p>Az a város, ahol a dokumentumot létrehozták.</p>
    </td>
    <td>
    <p>Krakkó</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>TatnaLiczbaPo éscdzsi</p>
    </td>
    <td>
    <p>A cikkek száma összesen.</p>
    </td>
    <td>
    <p>1</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>NaplóznaWartoscStatystyalana</p>
    </td>
    <td>
    <p>A statisztikai összérték.</p>
    </td>
    <td>
    <p>2632</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>AlmaznaWartoscFakala</p>
    </td>
    <td>
    <p>A teljes számlaérték.</p>
    </td>
    <td>
    <p>2632</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>UC</p>
    </td>
    <td>
    <p>Az egység kódja.</p>
    </td>
    <td>
    <p>420000</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Rodzaj</p>
    </td>
    <td>
    <p>A bevallás típusa</p>
    </td>
    <td>
    <p>T</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Wersja</p>
    </td>
    <td>
    <p>A dokumentum verziója.</p>
    </td>
    <td>
    <p>22</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Szám</p>
    </td>
    <td>
    <p>A dokumentum száma.</p>
    </td>
    <td>
    <p>11</p>
    </td>
    </tr>
    <tr>
    <td width="191">
    <p>Miesiac</p>
    </td>
    <td width="330">
    <p>A hivatkozási hónap.</p>
    </td>
    <td>
    <p>10</p>
    </td>
    </tr>
    <tr>
    <td width="191">
    <p>Rok</p>
    </td>
    <td width="330">
    <p>A hivatkozási év.</p>
    </td>
    <td>
    <p>2021</p>
    </td>
    </tr>
    <tr>
    <td width="191">
    <p>Typ</p>
    </td>
    <td width="330">
    <p>A jelentés iránya.</p>
    </td>
    <td>
    <p>S</p>
    </td>
    </tr>
    <tr>
    <td width="191">
    <p>NrWlasny</p>
    </td>
    <td width="330">
    <p>A nyilatkozat azonosítója.</p>
    </td>
    <td>
    <p>21ISTDEMF-0001</p>
    </td>
    </tr>
    <tr>
    <td colspan="3">
    <p><strong>Vállalat adatai</strong></p>
    </td>
    </tr>
    <tr>
    <td width="191">
    <p>Vegyes</p>
    </td>
    <td width="330">
    <p>Az a város, ahol a vállalat található.</p>
    </td>
    <td>
    <p>Varsó</p>
    </td>
    </tr>
    <tr>
    <td width="191">
    <p>Regon</p>
    </td>
    <td width="330">
    <p>A vállalat Regon-kódja.</p>
    </td>
    <td>
    <p>12345678901234</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Nip</p>
    </td>
    <td>
    <p>A vállalat NIP-kódja.</p>
    </td>
    <td>
    <p>1234567890</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Spoowtowy</p>
    </td>
    <td>
    <p>A vállalat irányítószáma.</p>
    </td>
    <td>
    <p>31-111</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Ulnumerikus szám</p>
    </td>
    <td>
    <p>Az az utca, ahol a vállalat található.</p>
    </td>
    <td>
    <p>Statisztika, 22/1</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Nazwa</p>
    </td>
    <td>
    <p>A vállalat neve.</p>
    </td>
    <td>
    <p>Contoso Szórakozási rendszer – Németország</p>
    </td>
    </tr>
    <tr>
    <td colspan="3">
    <p><strong>A jóra vonatkozó információk</strong></p>
    </td>
    </tr>
    <tr>
    <td>
    <p>TattoscStatystyalana</p>
    </td>
    <td>
    <p>A statisztikai érték.</p>
    </td>
    <td>
    <p>2632</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>SkarttoscFakalay</p>
    </td>
    <td>
    <p>A számla értéke.</p>
    </td>
    <td>
    <p>2632</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>MrinNetto</p>
    </td>
    <td>
    <p>A nettó tömeg.</p>
    </td>
    <td>
    <p>16</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>IdKontrahenta</p>
    </td>
    <td>
    <p>A vevő áfaszáma.</p>
    </td>
    <td>
    <p>DE9012</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Leszűkk van a 2015-2019</p>
    </td>
    <td>
    <p>Az árucikk-kód.</p>
    </td>
    <td>
    <p>10020030</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>RodzajTransakcdzs</p>
    </td>
    <td>
    <p>A tranzakció kódja.</p>
    </td>
    <td>
    <p>11</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>WarunkiDostawy</p>
    </td>
    <td>
    <p>A szállítási mód feltételei.</p>
    </td>
    <td>
    <p>CIF</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>VanjPochodzeniaWysíróki</p>
    </td>
    <td>
    <p>A kiszállítás/cél országának vagy régiójának kódja.</p>
    </td>
    <td>
    <p>DE</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>OpisTowru</p>
    </td>
    <td>
    <p>Az árucikk leírása.</p>
    </td>
    <td>
    <p>Hardver</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>PozId</p>
    </td>
    <td>
    <p>A cikkszám.</p>
    </td>
    <td>
    <p>1</p>
    </td>
    </tr>
    <tr>
    <td colspan="3">
    <p><strong>Kapcsolattartó adatai</strong></p>
    </td>
    </tr>
    <tr>
    <td>
    <p>E-mail</p>
    </td>
    <td>
    <p>A beküldő e-mail címe.</p>
    </td>
    <td>
    <p>manishc@contoso.com</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Faks</p>
    </td>
    <td>
    <p>A beküldő faxszáma.</p>
    </td>
    <td>
    <p>425-555-5049</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Telefon</p>
    </td>
    <td>
    <p>A beküldő telefonszáma.</p>
    </td>
    <td>
    <p>425-555-5068</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>NazwiskoIarc</p>
    </td>
    <td>
    <p>A beküldő neve.</p>
    </td>
    <td>
    <p>Manish Mártra</p>
    </td>
    </tr>
    </tbody>
    </table>

21. Tekintse át a generált Excel formátumú jelentést.

    ![Intrastat-jelentés az elküldésekről](media/intrastat_pl_3.png)

### <a name="create-a-purchase-order"></a>Beszerzési rendelés létrehozása

1. Menjen a **Fizetendő számlák** > **Beszerzési megbízások** > **Minden beszerzési megbízás** menüpontba.
2. A Műveleti ablaktáblán kattintson az **Új** elemre.
3. A **Megrendelés létrehozása** párbeszédpanelen a **Szállítói számla** mezőben válassza a **DE-001-et**.
4. A Hely **·** mezőben válassza az **1 et.**
5. A Raktár **·** mezőben válassza a **11-et.**
6. Válassza ki az **OK** lehetőséget.
7. A Szállítás gyorslap Fejléc lapján ellenőrizze, hogy a Szállítás módja mező **·** **·** **·** **10-e,** **·** **·** és a Szállítási feltételek mezőben a CIF beállítás van-e meg.
8. A **Sorok** lapon, a **Beszerzési rendelés sorai** gyorslapon a **Tételszám** mezőben válassza a **D0003-et**. Ezután a **Mennyiség** mezőbe írjon be **6**-et.
9. A Külkereskedelem lap Sor részletei gyorslapján ellenőrizze, hogy a tranzakciókód 11-re van-e állítva, a Szállítás **·** **·** **·** **·** **·** **mezőben a 3-as,** **·** **·** **·** **·** az Árucikk mezőben a 100 200 30, az Származási ország/terület mezőben a DEU beállítás van meg.
10. A Műveletpanelen, a **Vásárlás** lapon, a **Műveletek** csoportban válassza a **Megerősítés** lehetőséget.
11. A Műveleti ablaktábla **Számla** lapján a **Létrehozás** csoportban válassza a **Számla** lehetőséget.
12. Válassza a műveletpanel Alapértelmezett beállítását, majd a Sorok alapértelmezett mennyisége mezőjében válassza **a** Megrendelt mennyiség **·** **beállítást**. Majd kattintson az **OK** lehetőségre.
13. Írja be **a** **·** **·** **00010** számot a Szállítói számla fejlécének gyorskódja mezőbe a Számlaazonosító szakasz Szám mezőjébe.
14. A **Számladátum** szakasz **Számladátum** mezőjében válassza ki az aktuális dátumot. Ez a dátum lesz használva az Intrastat-átvitelhez.
15. A Bizonylat dátumának fogadása mezőben válassza **·** a **2021. február 18-át** (2021. október 18.).
16. A Művelet ablaktáblán válassza a **Feladás** lehetőséget a számla könyveléséhez.

### <a name="create-an-intrastat-declaration-for-arrivals"></a>Intrastat-nyilatkozat létrehozása az érkezésekhez

1. Ugorjon a következőre: **Adó** > **Nyilatkozatok** > **Külkereskedelem** > **Intrastat**.
2. A Műveletpanelen válassza az **Átvitel** lehetőséget.
3. Az **Intrastat (Átvitel)** párbeszédpanelen állítsa a **Szállítói számla** opciót **Igenre**.
4. Válassza az **OK** lehetőséget a tranzakciók átviteléhez, majd tekintse át az Intrastat naplót.

    ![A beszerzési rendelést képviselő sor az Intrastat oldalon](media/intrastat_pl_4.png)

5. Tekintse át az általános **lapon található információkat a beszerzési** rendeléshez.

    ![Beszerzési rendelés részletei az Intrastat lap Általános lapján](media/intrastat_pl_5.png)

6. A Műveletpanelen válassza a **Kimenet** > **Jelentés** lehetőséget.
7. Az **Intrastat jelentés párbeszédpanelEn, a Paraméterek gyorspanel Dátum szakaszában, a Dátum mezőben válassza ki az aktuális hónap első** **·** **·** **·** napját.
8. Az **Exportálási** **lehetőségek** szakaszban állítsa a **Fájl létrehozása** opciót **Igen**-re. Ezután a **Fájlnév** mezőbe írja be a kívánt nevet.
9. Állítsa a **Jelentés készítése** opciót **Igenre**. Ezután a **Jelentésfájl neve** mezőbe írja be a kívánt nevet.
10. Az **Irány** mezőben válassza az **Érkezések** lehetőséget.
11. A **Fájlformátum-leképezés szakaszban ellenőrizze, hogy a** Nyilatkozat típusa mező beállítása **·** **Deklaráció.**
12. A **Bizonylatok városának létrehozása** mezőben adja meg **a Írnikow** mezőt.
13. A Dokumentum létrehozásának dátuma mezőben válassza **·** a **19. 10-et** (2021. október 19.).
14. A Bizonylat **no** mezőjébe írja be a **11-et.**
15. A **Dokumentumverzió** mezőben adja meg a **22-es** et.
16. Válassza az OK gombra, és tekintse át a jelentést a létrehozott **·** XML-formátumban. A következő táblázat a példajelentésben szereplő értékeket mutatja.

    <table>
    <tbody>
    <tr>
    <td>
    <p><strong>Mezőnév</strong></p>
    </td>
    <td>
    <p><strong>Mező leírása</strong></p>
    </td>
    <td>
    <p><strong>Érték</strong></p>
    </td>
    </tr>
    <tr>
    <td colspan="3">
    <p style="text-align: center;"><strong>A dokumentummal kapcsolatos információk</strong></p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Deklaracja adatok</p>
    </td>
    <td>
    <p>A dokumentum létrehozási dátuma.</p>
    </td>
    <td>
    <p>2021-10-19</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Vegyes</p>
    </td>
    <td>
    <p>Az a város, ahol a dokumentumot létrehozták.</p>
    </td>
    <td>
    <p>Krakkó</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>TatnaLiczbaPo éscdzsi</p>
    </td>
    <td>
    <p>A cikkek száma összesen.</p>
    </td>
    <td>
    <p>1</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>NaplóznaWartoscStatystyalana</p>
    </td>
    <td>
    <p>A statisztikai összérték.</p>
    </td>
    <td>
    <p>965</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>AlmaznaWartoscFakala</p>
    </td>
    <td>
    <p>A teljes számlaérték.</p>
    </td>
    <td>
    <p>965</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>UC</p>
    </td>
    <td>
    <p>Az egység kódja.</p>
    </td>
    <td>
    <p>420000</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Rodzaj</p>
    </td>
    <td>
    <p>A bevallás típusa</p>
    </td>
    <td>
    <p>T</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Wersja</p>
    </td>
    <td>
    <p>A dokumentum verziója.</p>
    </td>
    <td>
    <p>22</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Szám</p>
    </td>
    <td>
    <p>A dokumentum száma.</p>
    </td>
    <td>
    <p>11</p>
    </td>
    </tr>
    <tr>
    <td width="191">
    <p>Miesiac</p>
    </td>
    <td width="332">
    <p>A hivatkozási hónap.</p>
    </td>
    <td>
    <p>10</p>
    </td>
    </tr>
    <tr>
    <td width="191">
    <p>Rok</p>
    </td>
    <td width="332">
    <p>A hivatkozási év.</p>
    </td>
    <td>
    <p>2021</p>
    </td>
    </tr>
    <tr>
    <td width="191">
    <p>Typ</p>
    </td>
    <td width="332">
    <p>A jelentés iránya.</p>
    </td>
    <td>
    <p>P</p>
    </td>
    </tr>
    <tr>
    <td width="191">
    <p>NrWlasny</p>
    </td>
    <td width="332">
    <p>A nyilatkozat azonosítója.</p>
    </td>
    <td>
    <p>21ISTDEMF-0002</p>
    </td>
    </tr>
    <tr>
    <td colspan="3">
    <p style="text-align: center;"><strong>Vállalat adatai</strong></p>
    </td>
    </tr>
    <tr>
    <td width="191">
    <p>Vegyes</p>
    </td>
    <td width="332">
    <p>Az a város, ahol a vállalat található.</p>
    </td>
    <td>
    <p>Varsó</p>
    </td>
    </tr>
    <tr>
    <td width="191">
    <p>Regon</p>
    </td>
    <td width="332">
    <p>A vállalat Regon-kódja.</p>
    </td>
    <td>
    <p>12345678901234</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Nip</p>
    </td>
    <td>
    <p>A vállalat NIP-kódja.</p>
    </td>
    <td>
    <p>1234567890</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Spoowtowy</p>
    </td>
    <td>
    <p>A vállalat irányítószáma.</p>
    </td>
    <td>
    <p>31-111</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Ulnumerikus szám</p>
    </td>
    <td>
    <p>Az az utca, ahol a vállalat található.</p>
    </td>
    <td>
    <p>Statisztika, 22/1</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Nazwa</p>
    </td>
    <td>
    <p>A vállalat neve.</p>
    </td>
    <td>
    <p>Contoso Szórakozási rendszer – Németország</p>
    </td>
    </tr>
    <tr>
    <td colspan="3">
    <p style="text-align: center;"><strong>A jóra vonatkozó információk</strong></p>
    </td>
    </tr>
    <tr>
    <td>
    <p>TattoscStatystyalana</p>
    </td>
    <td>
    <p>A statisztikai érték.</p>
    </td>
    <td>
    <p>965</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>SkarttoscFakalay</p>
    </td>
    <td>
    <p>A számla értéke.</p>
    </td>
    <td>
    <p>965</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>MrinNetto</p>
    </td>
    <td>
    <p>A nettó tömeg.</p>
    </td>
    <td>
    <p>30</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>VanjPochodzenia</p>
    </td>
    <td>
    <p>A származási ország vagy régió kódja.</p>
    </td>
    <td>
    <p>DE</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>RodzajTransportu</p>
    </td>
    <td>
    <p>A szállítási mód kódja.</p>
    </td>
    <td>
    <p>3</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Leszűkk van a 2015-2019</p>
    </td>
    <td>
    <p>Az árucikk-kód.</p>
    </td>
    <td>
    <p>10020030</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>RodzajTransakcdzs</p>
    </td>
    <td>
    <p>A tranzakció kódja.</p>
    </td>
    <td>
    <p>11</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>WarunkiDostawy</p>
    </td>
    <td>
    <p>A szállítási mód feltételei.</p>
    </td>
    <td>
    <p>CIF</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>VanjPochodzeniaWysíróki</p>
    </td>
    <td>
    <p>A kiszállítás/cél országának vagy régiójának kódja.</p>
    </td>
    <td>
    <p>DE</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>OpisTowru</p>
    </td>
    <td>
    <p>Az árucikk leírása.</p>
    </td>
    <td>
    <p>Hardver</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>PozId</p>
    </td>
    <td>
    <p>A cikkszám.</p>
    </td>
    <td>
    <p>1</p>
    </td>
    </tr>
    <tr>
    <td colspan="3">
    <p style="text-align: center;"><strong>Kapcsolattartó adatai</strong></p>
    </td>
    </tr>
    <tr>
    <td>
    <p>E-mail</p>
    </td>
    <td>
    <p>A beküldő e-mail címe.</p>
    </td>
    <td>
    <p>manishc@contoso.com</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Faks</p>
    </td>
    <td>
    <p>A beküldő faxszáma.</p>
    </td>
    <td>
    <p>425-555-5049</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>Telefon</p>
    </td>
    <td>
    <p>A beküldő telefonszáma.</p>
    </td>
    <td>
    <p>425-555-5068</p>
    </td>
    </tr>
    <tr>
    <td>
    <p>NazwiskoIarc</p>
    </td>
    <td>
    <p>A beküldő neve.</p>
    </td>
    <td>
    <p>Manish Mártra</p>
    </td>
    </tr>
    </tbody>
    </table>

17. Tekintse át a generált Excel formátumú jelentést.

    ![Intrastat-jelentés az érkezésekről](media/intrastat_pl_6.png)
