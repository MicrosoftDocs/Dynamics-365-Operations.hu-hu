---
title: Pénztár Kelet Európához és Oroszországhoz
description: Ez a témakör ismerteti a házipénztár funkciót, amellyel a felhasználók az Észtország, Litvánia, a Cseh Köztársaság, Magyarország, Lettország, Lengyelország és Oroszország készpénzműveleteit tükrözhetik a rendszerben.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RCashBalance, RCashCountStatementForm, RCashPosting, RCashRemainLimit, RCashReportJour_PL, RCashTable, RCashTableBalance, RCashTableCredLimit, RCashTableLastRevaluation, RCashTableTransactions, RCashTrans
audience: Application User
ms.reviewer: kfend
ms.custom: 268504
ms.search.region: Czech Republic, Estonia, Hungary, Latvia, Lithuania, Poland, Russia
ms.author: kfend
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: d6eaeb48184d30450a9da68b4f8419b1f3c77f6f
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5231500"
---
# <a name="petty-cash-for-eastern-europe-and-russia"></a>Pénztár Kelet Európához és Oroszországhoz

[!include [banner](../includes/banner.md)]

Ez a témakör ismerteti a házipénztár funkciót, amellyel a felhasználók az Észtország, Litvánia, a Cseh Köztársaság, Magyarország, Lettország, Lengyelország és Oroszország készpénzműveleteit tükrözhetik a rendszerben.

A házipénztár funkciói készpénzműveletek, -bevételek és -kiadások automatizálására, elsődleges dokumentumok létrehozására és a kapcsolódó jelentések nyomtatására használhatók. A házipénztár funkcióval az alábbi műveletek végezhetők:

-   A rendelkezésre álló készpénzes eszközök bevételének és kiadásának rögzítése.
-   Gyakori készpénzes űrlapok generálása: bevételezési pénztárbizonylatok, készpénzkifizetési bizonylatok és pénztárbizonylat-regisztrálási naplók.
-   A vevői, szállítói stb. műveletek esetében engedélyezett legnagyobb készpénzösszeg ellenőrzése.
-   Különböző pénznemekben végzett készpénzműveletek tükrözése a rendszerben.
-   Külföldi pénznemben végrejhatott készpénzösszeg-műveletek átváltása az alapértelmezett pénznemre a könyvelés számára készült jelentésekhez.
-   **Pénztárkönyvi** és pénztári jelentés létrehozása.

## <a name="prerequisites"></a>Előfeltételek
A házipénztár funkció használatához előbb a következő, előfeltételt jelentő feladatokat kell elvégezni:

-   Készpénzszámlák beállítása.
-   Készpénzfeladási profilok beállítása.
-   Számsorozatok beállítása pénztárbizonylatok számozásához.
-   Alapértelmezett értékek és paraméterek beállítása készpénz és bank kezeléséhez.
-   Készpénzkezelési naplónevek beállítása a főkönyvben.

### <a name="set-up-cash-accounts"></a>Készpénzszámlák beállítása

Készpénz beállításához nyissa meg a **Készpénz- és bankkezelés** &gt; **Bankszámlák** &gt; **Készpénzszámlák** elemet, és adja meg a következő adatokat.

| Mező                 | Leírás                                                                                                          |
|-----------------------|----------------------------------------------------------------------------------------------------------------------|
| Készpénz                  | Adja meg a készpénzszámla (készpénz) azonosító kódját.                                                                    |
| Név                  | Adja meg a készpénzszámla leírását.                                                                             |
| Pénznem              | Állítsa be az alapértelmezett pénznemkódot a készpénztranzakciókhoz.                                                              |
| Számsorozatcsoport | Ha a pénztárbizonylatok számozása kötelezően különbözik paraméterek között megadott számozástól, adjon meg egy kódot. |
| Több pénznem       | Jelölje be ezt a jelölőnégyzetet, és engedélyezze a pénznemeket, amelyek különböznek a könyvelés alapértelmezett pénznemétől.                     |
| Negatív készpénz         | Jelölje be ezt a jelölőnégyzetet, és engedélyezze a negatív készpénzegyenlegeket bármely pénznemben.                                               |

Készpénzszámla készpénzegyenlege ellenőrzési szabályainak beállításához válassza ki a készpénzszámlát, majd a műveletpanel **Készpénzszámla** lapján az **Egyenleg korlátja** csoportban kattintson az **Egyenleg korlátja** elemre. Adja meg a következő adatokat.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Mező</th>
<th>Leírás</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Pénznemtípus</td>
<td>Válassza ki a pénznem típusát:
<ul>
<li><strong>Könyvelési pénznem</strong> – használja a vállalat alapvető pénznemkódját.</li>
<li><strong>Beállított valuta</strong> – használjon a vállalat alapvető pénznemkódjától eltérő pénznemkódot.</li>
</ul></td>
</tr>
<tr class="even">
<td>Pénznem</td>
<td>Ha a <strong>Beállított valuta</strong> lehetőséget választotta a <strong>Pénznemtípus</strong> mezőben, válasszon pénznemkódot. Ez a mező nem áll rendelkezésre, ha a <strong>Könyvelési pénznem</strong> lehetőséget választotta a <strong>Pénznemtípus</strong> mezőben.</td>
</tr>
<tr class="odd">
<td>Egyenleg-határérték típusa</td>
<td>Válasszon a következő elérhető értékek közül:
<ul>
<li><strong>Maximális</strong> – a készpénzegyenleg nem haladhatja meg a készpénzszámlához tartozó <strong>Egyenleg korlátja</strong> összegét (felső határ).</li>
<li><strong>Minimális</strong> – a készpénzegyenleg nem süllyedhet a készpénzszámlához tartozó <strong>Egyenleg korlátja</strong> összege alá (alsó határ).</li>
</ul></td>
</tr>
<tr class="even">
<td>Egyenlegkorlát ellenőrzése</td>
<td>Válassza ki, mi történik a készpénzbefizetési bizonylatok jóváhagyási eljárása során, ha a készpénzszámla <strong>Egyenleg korlátja</strong> összegét átlépik:
<ul>
<li><strong>Elfogadás</strong> – A határérték túlléphető.</li>
<li><strong>Figyelmeztetés</strong> – a határérték átléphető, de a felhasználó figyelmeztető üzenetet kap. A készpénzbizonylat megerősítésre vagy jóváhagyásra kerül.</li>
<li><strong>Hiba</strong> – A határérték nem léphető túl. A felhasználó hibaüzenetet kap, és a készpénzbizonylat nem kerül megerősítésre vagy jóváhagyásra.</li>
</ul>
A készpénzbizonylatok jóváhagyási folyamatával kapcsolatos további tudnivalókért lásd a &quot;Készpénztranzakciók jóváhagyása és feladása&quot; részt a témakör későbbi részében.</td>
</tr>
<tr class="odd">
<td>Egyenleg korlátja</td>
<td>Adja meg a készpénzszámla egyenlegének határértékét. Az összegnek a megadott pénznemben kell lennie.</td>
</tr>
</tbody>
</table>

### <a name="set-up-cash-posting-profiles"></a>Készpénzfeladási profilok beállítása

A készpénzfeladási profilok határozzák meg a főkönyvi feladásokat. Készpénzfeladási profil beállításához lépjen a **Készpénz-** **és bankkezelés** &gt; **Beállítás** &gt; **Készpénzfeladási sablonok** pontra, és válasszon vagy hozzon létre feladási profilt. Adja meg a következő adatokat.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Mező</th>
<th>Leírás</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Érvényes</td>
<td>Válassza ki, hogy a feladási profil egy adott készpénzszámlára vagy minden készpénzszámlára vonatkozik-e:
<ul>
<li><strong>Táblázat</strong> – ha létezik feladási profilsor a készpénzes számlához, a úgy ez a sor kerül felhasználásra a készpénztranzakciók feladásánál.</li>
<li><strong>Mind</strong> – nincs feladási profilsor a készpénzszámlához.</li>
</ul></td>
</tr>
<tr class="even">
<td>Készpénz</td>
<td>Ha a <strong>Tábla</strong> lehetőséget választotta az <strong>Érvényes</strong> mezőben, akkor adja meg a készpénzszámlát. A mező üresen marad, ha a <strong>Mind</strong> elemet választotta az <strong>Érvényes</strong> mezőben.</td>
</tr>
<tr class="odd">
<td>Főkönyvi számla</td>
<td>Adja meg a készpénzszámla összegző számlájaként használni kívánt főkönyvi számla számát.</td>
</tr>
</tbody>
</table>

### <a name="set-up-number-sequences-for-cash-documents"></a>Készpénzbizonylatok számsorozatainak beállítása

Készpénzbizonylatok számsorozatainak beállításához lépjen a **Készpénz- és bankkezelés** &gt; **Beállítás** &gt; **Készpénz- és bankkezelési paraméterek** elemre. A **Számsorozat** lapon adja meg a számsorozat-kódokat a **Bevételezési pénztárbizonylatok**, **Készpénz-kifizetési bizonylatok**, **Készpénzkorrekciós bizonylatok** és **Árfolyam-korrekció** bizonylatok, valamint a **Készpénzjelentés száma** számára.

### <a name="set-up-default-values-for-cash-and-bank-management-parameters"></a>Alapértelmezett értékek és paraméterek beállítása készpénz és bank kezeléséhez

Alapértelmezett értékek és paraméterek beállításához készpénz és bank kezeléséhez a házipénztár funkcióban lépjen a **Készpénz- és bankkezelés** &gt; **Beállítás** &gt; **Készpénz- és bankkezelési paraméterek** elemre. A **Készpénz** lapon adja meg a következő adatokat.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Mező</th>
<th>Leírás</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Készpénz</td>
<td>Válassza ki a naplókhoz használandó alapértelmezett készpénzszámlát.</td>
</tr>
<tr class="even">
<td>Készpénzfeladás</td>
<td>Adja meg az alapértelmezett feladási profilt, amelyet a rendszer akkor használ, ha más feladási profil nincs megadva.</td>
</tr>
<tr class="odd">
<td>Felhasznált bizonylat ellenőrzése</td>
<td>Válassza ki, mi történik, ha a készpénzbizonylat számának ellenőrzése során ismétlődő számok találhatók:
<ul>
<li>Ismétlődések tiltása</li>
<li>Ismétlődések tiltása a pénzügyi éven belül</li>
<li>Ismétlődések elfogadása</li>
<li>Figyelmeztetés ismétlődés esetén</li>
</ul></td>
</tr>
<tr class="even">
<td>Műveletek korlátjának ellenőrzése</td>
<td>Adja meg, mi történik az ellenoldali feleket érintő műveletek határértékének túllépése esetén:
<ul>
<li><strong>Elfogadás</strong> – A határérték túlléphető.</li>
<li><strong>Figyelmeztetés</strong> – a határérték átléphető, de a felhasználó figyelmeztető üzenetet kap. A művelet fel van adva.</li>
<li><strong>Hiba</strong> – A határérték nem léphető túl. A felhasználó hibaüzenetet kap, és a művelet feladása nem történik meg.</li>
</ul></td>
</tr>
<tr class="odd">
<td>Ellenőrzési mód</td>
<td>Válassza ki a műveletek határértékének túllépését felügyelő ellenőrzési módot:
<ul>
<li><strong>Művelet</strong> – ellenőrzés tranzakciónként</li>
<li><strong>Megállapodás</strong> – ellenőrzés olyan tranzakciónként, amelyhez megadott szerződés tartozik egy ellenoldali féllel.</li>
</ul></td>
</tr>
<tr class="even">
<td>Műveletek korlátja</td>
<td>Adja meg az ellenoldali felekkel rendelkező műveletekhez tartozó maximális készpénzösszeget.</td>
</tr>
<tr class="odd">
<td>Feladás korábbi dátummal</td>
<td>Jelölje be ezt a jelölőnégyzetet, hogy engedélyezze a legutóbbi készpénztranzakció dátuma előtti készpénztranzakciók feladását.</td>
</tr>
<tr class="even">
<td>Dimenziók</td>
<td>Adja meg a dimenziókat a <strong>Részleg kódja</strong>, <strong>Analitikai kód</strong> és <strong>Cél kódja</strong> mezőkben. A készpénzbizonylatok nyomtatása űrlap tükrözni fogja ezt az információt.</td>
</tr>
<tr class="odd">
<td>Jóváhagyási állapot használata</td>
<td>Jelölje be ezt a jelölőnégyzetet, ha egy további állapotot (<strong>Visszaigazolva</strong>) kíván alkalmazni készpénzbizonylatok jóváhagyási folyamata során. (További információkért lásd a &quot;Készpénztranzakciók jóváhagyása és feladása&quot; szakaszt.)</td>
</tr>
</tbody>
</table>

### <a name="set-up-cash-journal-names-in-general-ledger"></a>Készpénzkezelési naplónevek beállítása a főkönyvben

Készpénztranzakciók feladására napló létrehozásához lépjen a **Főkönyv** &gt; **Napló beállítása** &gt; **Naplónevek** elemre, és hozzon létre egy új rekordot. A **Naplótípus** mezőben válassza ki a **Készpénz** lehetőséget. Adja meg az egyéb szükséges alapértelmezett naplóparamétereket.

## <a name="daily-cash-operations-via-a-slip-journal"></a>Napi készpénzműveletek Bizonylatnapló révén
Készpénzbizonylat létrehozásához Bizonylatnapló révén lépjen a **Készpénz- és bankkezelés** &gt; **Készpénztranzakciók** &gt; **Bizonylatnapló** elemre, és hozzon létre egy új naplót. A Művelet panelen kattintson a **Sorok** elemre. Adjon hozzá új sort, és írja be a következő adatokat.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Mező</th>
<th>Leírás</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Dátum</td>
<td>Adja meg a tranzakció dátumát.</td>
</tr>
<tr class="even">
<td>Könyvelési számla</td>
<td>Válassza ki a készpénzes számlát. Alapértelmezés szerint a készpénzes számlák a Készpénz- és bankkezelési paraméterek között vannak megadva.</td>
</tr>
<tr class="odd">
<td>Leírás</td>
<td>Adjon meg magyarázó szöveget a tranzakcióhoz.</td>
</tr>
<tr class="even">
<td>Tartozik Követel</td>
<td>Adja meg a készpénzbizonylat összegét a következő mezők egyikében:
<ul>
<li><strong>Tartozik</strong> – a mező használatával készpénzbevételek és a bevételezési pénztárbizonylatok rögzíthetők.</li>
<li><strong>Követel</strong> – a mező használatával készpénzkiadások és a készpénz-kifizetési bizonylatok rögzíthetők.</li>
</ul></td>
</tr>
<tr class="odd">
<td>Ellenszámla típusa Ellenszámla</td>
<td>Válasszon ellenszámlatípust és ellenszámlaszámot.</td>
</tr>
<tr class="even">
<td>Pénznem</td>
<td>Válassza ki a tranzakció pénznemkódját.</td>
</tr>
<tr class="odd">
<td>Bizonylat </td>
<td>Ezt a mezőt a rendszer automatikusan kitölti a napló beállítása alapján.</td>
</tr>
<tr class="even">
<td>Rendelés száma</td>
<td>Ha nincs más számsorozat beállítva a készpénzszámlához, ez a mező automatikusan ki van töltve a paraméterekben megadott számsorozat alapján. Igény szerint ebben a mezőben rendelési szám manuális bevitele lehetséges. A készpénzbizonylatok számozási következetlenségeinek megelőzése érdekében a következő felügyelet kerül alkamazásra: olyan készpénzbizonylat száma, amelynél a művelet dátuma korábbi, nem lehet nagyobb, mint a későbbi műveleti dátumú készpénzbizonylatok száma. Ha nem igényli ezt a felügyeletet, jelölje be a <strong>Feladás korábbi dátummal</strong> jelölőnégyzetet a Készpénz- és bankkezelési paraméterek között.</td>
</tr>
<tr class="odd">
<td>Jóváhagyási állapot</td>
<td>Az első tranzakció állapota <strong>Nincs</strong>. A tranzakció állapotának beállításával kapcsolatos tudnivalókért lásd a &quot;Készpénztranzakciók jóváhagyása és feladása&quot; szakaszt.</td>
</tr>
<tr class="even">
<td>Dokumentumtípus </td>
<td>Ezt a mezőt a <strong>Készpénzutalvány</strong> lapon a rendszer automatikusan kitölti a készpénzbizonylathoz megadott összeg alapján:
<ul>
<li><strong>Bevételezési pénztárbizonylat</strong> – ez az érték kerül használatra, ha a készpénzszámla <strong>Tartozik</strong> mezőjében adott meg összeget.</li>
<li><strong>Készpénz-kifizetési bizonylat</strong> – ez az érték kerül használatra, ha a készpénzszámla <strong>Követel</strong> mezőjében adott meg összeget.</li>
<li><strong>Korrekció</strong> – negatív összeget adott meg a készpénzszámla <strong>Tartozik</strong> vagy a <strong>Követel</strong> mezőjében.</li>
</ul></td>
</tr>
<tr class="odd">
<td>Áfacsoport</td>
<td>Adjon meg egy áfacsoportot a művelet adóinak kiszámítására.</td>
</tr>
<tr class="even">
<td>Cikkáfacsoport</td>
<td>Adjon meg egy cikkáfacsoportot a művelet adóinak kiszámítására.</td>
</tr>
<tr class="odd">
<td>Jogcím</td>
<td>A <strong>Készpénzutalvány</strong> lapon adja meg a tranzakció tárgyának leírását. Ez a szöveg nyomtatásnál rákerül a pénztárbizonylat formanyomtatványára.</td>
</tr>
<tr class="even">
<td>Dokumentum dátuma</td>
<td>Adja meg a tranzakció okát adó elsődleges dokumentum (például előzetes jelentés, számla vagy rendelés) leírását, számát és dátumát.</td>
</tr>
<tr class="odd">
<td>Képviselő típusa</td>
<td>Ez a mező a következő értékeket veheti fel:
<ul>
<li><strong>Dolgozó</strong> – a <strong>Képviselő</strong> keresés alkalmazottak listáját tartalmazza, ha az <strong>Ellenszámla</strong> mező értéke <strong>Főkönyv</strong> vagy <strong>Bank</strong>, illetve az ellenoldali fél kapcsolattartóinak listáját, ha az <strong>Ellenszámla</strong> mező értéke <strong>Vevő</strong> vagy <strong>Szállító</strong>. Képviselők beállításához lépjen az <strong>Alap</strong> &gt; <strong>Beállítás</strong> &gt; <strong>Kapcsolattartók</strong> &gt; <strong>Kapcsolattartó</strong> elemre.</li>
<li><strong>Egyéb</strong> – a <strong>Képviselő</strong> keresés más ügyfelek listáját tartalmazza. A <strong>Vevők</strong> vagy <strong>Szállítók</strong> táblában nem szereplő jogosultak beállításához lépjen a <strong>Főkönyv</strong> &gt; <strong>Jogosultak</strong> elemre. Ez a típus csak Lettországban érhető el. (A <strong>CSELatvia</strong> konfigurációs kulcsnak engedélyezve kell lennie.)</li>
<li><strong>Szállító</strong> – a <strong>Képviselő</strong> keresés szállítók listáját tartalmazza. Szállítók beállításához lépjen a <strong>Kötelezettségek</strong> &gt; <strong>Szállítók</strong> elemre.</li>
<li><strong>Vevő</strong> – a <strong>Képviselő</strong> keresés vevők listáját tartalmazza. Vevők beállításához lépjen a <strong>Kinnlevőségek</strong> &gt; <strong>Vevők</strong> elemre.</li>
</ul></td>
</tr>
<tr class="even">
<td>Jellegzetes</td>
<td>Válasszon ki egy a <strong>Képviselő típusa</strong> mezőben megadott típusú képviselőt.</td>
</tr>
<tr class="odd">
<td>A személy neve</td>
<td>Ezt a mezőt a rendszer automatikusan kitölti az <strong>Ellenszámla</strong> és a <strong>Képviselő</strong> mezők alapján. A pénztárbizonylatok nyomtatása űrlap tükrözni fogja ezt az információt.</td>
</tr>
<tr class="even">
<td>Személyi igazolvány</td>
<td>Ezt a mezőt a rendszer automatikusan kitölti a kapcsolattartó (képviselő) személyazonosító igazolványának adatai alapján. Ha az <strong>Ellenszámla típusa</strong> mező értéke <strong>Előleg jogosultja</strong> és az <strong>Ellenszámla</strong> mező értéke egy alkalmazotti szám, készpénzbe- és kifizetések végezhetők az alkalmazott részére vagy részéről. Ebben az esetben a <strong>Személyi igazolvány</strong> mező ki van töltve automatikusan az <strong>Alkalmazott</strong> táblában szereplő személyiigazolvány-adatok alapján (<strong>Személyzeti számvitel</strong> &gt; <strong>Alkalmazott tábla</strong>).</td>
</tr>
<tr class="odd">
<td>Cél</td>
<td>A <strong>Cél</strong> táblában adjon meg egy vagy több rendeltetésihely-kódot a tranzakció összegéhez. Válasszon ki egy rendeltetési kódot a <strong>Cél</strong> mezőben, és írja be a magyarázatot a <strong>Tranzakció szövege</strong> mezőben. Az <strong>Összeg</strong> mezőben adjon meg egy összeget a tranzakció pénznemében. A <strong>Százalék</strong> mező százalékos formában a célösszeg és a tranzakció teljes összegének arányát mutatja.</td>
</tr>
<tr class="even">
<td>Maradvány</td>
<td>A fennmaradó, kiszámított összeg. Fontos megjegyezni, hogy a teljes tranzakció összegét rendeltetésihely-kódokhoz kell rendelni.</td>
</tr>
<tr class="odd">
<td>Hivatalnokok</td>
<td>A <strong>Hivatalnokok</strong> lapon adja a felelős személyek nevét és beosztását: igazgató, vezető könyvelő és pénztáros. A <strong>Pozíció</strong> értékeit a hivatalnokok beállítása határozza meg a <strong>Hivatalnokok</strong> oldal <strong>Általános</strong> és <strong>Főkönyv</strong> lapjain (<strong>Alap</strong> &gt; <strong>Beállítás</strong> &gt; <strong>Kapcsolattartók</strong> &gt; <strong>Hivatalnokok</strong>).</td>
</tr>
<tr class="even">
<td>Előleg</td>
<td>Jelölje be ezt a jelölőnégyzetet, ha a tranzakció előleg.</td>
</tr>
<tr class="odd">
<td>Feladási profil</td>
<td>Adja meg a készpénzszámla feladási profilját. Alapértelmezés szerint a rendszer a Készpénz- és bankkezelési paraméterek között megadott feladási profilt használja.</td>
</tr>
<tr class="even">
<td>Ellenszámla feladási sablonja</td>
<td>Adja meg a kiválasztott ellenszámla feladási profilját.</td>
</tr>
<tr class="odd">
<td>Teljes összeg</td>
<td>A <strong>Teljes összeg</strong> mezőcsoportban a lap alján a <strong>Visszatérítés</strong> a mező mutatja a végösszeget, amely az aktuális naplóban megadott összes Bevételezési pénztárbizonylat alapján kerül kiszámításra, a <strong>Kifiz</strong> mező pedig az összes Bevételezési pénztárbizonylat végösszegét mutatja.</td>
</tr>
</tbody>
</table>

A naplóbejegyzések ellenőrzéséhez a műveletpanelen kattintson az **Ellenőrzés** elemre.

## <a name="daily-cash-operations-via-a-general-journal"></a>Napi készpénzműveletek Általános napló révén
Készpénztranzakció Általános naplón keresztüli létrehozásához lépjen a **Főkönyv** &gt; **Naplóbejegyzések** &gt; **Általános naplók** elemre, és hozzon létre egy új naplót. A Művelet panelen kattintson a **Sorok** elemre. Adjon hozzá új sort, és írja be a következő adatokat.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Mező</th>
<th>Leírás</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Dátum</td>
<td>Adja meg a tranzakció dátumát.</td>
</tr>
<tr class="even">
<td>Számla típusa</td>
<td>Válassza a <strong>Pénztár</strong> elemet.</td>
</tr>
<tr class="odd">
<td>Könyvelési számla</td>
<td>Válassza ki a készpénzszámla számát.</td>
</tr>
<tr class="even">
<td>Tranzakció szövege</td>
<td>Adjon meg magyarázó szöveget a tranzakcióhoz.</td>
</tr>
<tr class="odd">
<td>Tartozik Követel</td>
<td>Adja meg a készpénzbizonylat összegét a következő mezők egyikében:
<ul>
<li><strong>Tartozik</strong> – a mező használatával készpénzbevételek és a bevételezési pénztárbizonylatok rögzíthetők.</li>
<li><strong>Követel</strong> – a mező használatával készpénzkiadások és a készpénz-kifizetési bizonylatok rögzíthetők.</li>
</ul></td>
</tr>
<tr class="even">
<td>Ellenszámla típusa Ellenszámla</td>
<td>Válasszon ellenszámlatípust és ellenszámlaszámot.</td>
</tr>
<tr class="odd">
<td>Pénznem</td>
<td>Válassza ki a tranzakció pénznemkódját.</td>
</tr>
</tbody>
</table>

A **Számla** lapon adhatja meg a kijelölt számlához és ellenszámlához a feladási profilokat. Ha a regisztrált tranzakció egy előleg, jelölje be az **Előleg** jelölőnégyzetet a **Fizetés** lapon. A **Képviselő** mezőcsoportban töltse ki a mezőket a bizonylatnaplósorokban megadottaknak megfelelően; ezek nyomtatásnál bekerülnek a **Készpénz** jelentésbe. A naplóbejegyzések ellenőrzéséhez a műveletpanelen kattintson az **Ellenőrzés** elemre.

## <a name="cash-transaction-approval-and-posting"></a>Készpénztranzakciók jóváhagyása és feladása
Készpénztranzakciók esetén a következő állapotok alkalmazhatók: **Nincs**, **Visszaigazolva**, **Jóváhagyva** és **Elutasítva**. A **Készpénz- és bankkezelés** &gt; **Beállítás** &gt; **Készpénz- és bankkezelési paraméterek** **Készpénz** lapjának **Jóváhagyás** gyorslapján szereplő **Jóváhagyási állapot használata** paraméter lehetővé teszi két további állapot aktiválását: **Visszaigazolva** és **Elutasítva**. Megerősítés akkor alkalmazható, ha a készpénzbizonylatok kiadására kerül sor, és a készpénzbefizetések vagy -kifizetések két alkalmazott: könyvelő és pénztáros között oszlanak meg. Az **Állapot visszaállítása** funkció az aktuális tranzakció állapotától függően változik. A **Jóváhagyva** állapotból **Visszaigazolva**, a **Visszaigazolva** állapotból pedig **Nincs** lesz. A pénztárnaplótételek szerkesztése csak akkor lehetséges, ha az állapot **Nincs**. A készpénzes tranzakciókat akkor lehet elutasítani, ha a tranzakció állapota **Visszaigazolva**. Az elutasított készpénzbizonylatok szerepelnek a **Pénztárbizonylatok regisztrációs naplója** jelentésben, de nem jelennek meg a **Pénztárkönyv** jelentésben. Tranzakció megerősítéséhez válassza ki a megfelelő bizonylatnaplósort, és kattintson a **Dokumentumok jóváhagyása** &gt; **Megerősítés** elemre. Létrejön egy rendelésszám a megadott számsorozat alapján. A tranzakció állapota **Visszaigazolva** értékre változik, és a naplósor többé nem szerkeszthető. A készpénzes számla egyenlege változatlan marad. Készpénzbizonylat elutasításához kattintson a **Dokumentumok jóváhagyása** &gt; **Elutasítás** elemre. Ez a beállítás csak azon dokumentumoknál érhető el, amelyek állapota **Visszaigazolva**. Tranzakció jóváhagyásához válassza ki a megfelelő bizonylatnaplósort, és kattintson a **Dokumentumok jóváhagyása** &gt; **Jóváhagyás** elemre. A **Jóváhagyva** állapot azt jelzi, hogy a pénzalapok beérkezése vagy elküldése megtörtént. A készpénzegyenleg módosul. A készpénztranzakciót fel lehet adni. **Jóváhagyva** állapot törléséhez és az állapot **Nincs** értékű alaphelyzetbe állításához kattintson a **Dokumentumok jóváhagyása** &gt; **Állapot visszaállítása** elemre. Csak jóváhagyott készpénztranzakciók adhatók fel. Napló feladásához kattintson a **Feladás** &gt; **Feladás** elemre.

## <a name="print-a-cash-order"></a>Készpénzutalvány nyomtatása
Készpénzutalvány nyomtatásához válasszon bizonylatnaplósort, majd a műveletek panelen kattintson a **Nyomtatása** &gt; **Készpénzutalvány-jelentés** elemre. Létrejön egy nyomtatási űrlap bevételezési pénztárbizonylathoz vagy készpénzkifizetési bizonylathoz, attól függően, hogy az összeg a **Tartozik** vagy a **Követel** mezőben szerepel-e a a kijelölt sornál:

-   Ha az összeg a **Tartozik** mezőben szerepel: bevételezési pénztárbizonylat jön létre
-   Ha az összeg a **Követel** mezőben szerepel: készpénzkifizetési bizonylat jön létre

Azok a bizonylatnaplósorok nyomtathatók, amelyek állapota **Visszaigazolva**, **Jóváhagyva** vagy **Elutasítva**. A készpénzbefizetési utalványok a **Készpénz- és bankkezelés** &gt; **Lekérdezések és jelentések** &gt; **Készpénzutalvány** menüpontban is kinyomtathatók.

## <a name="periodic-tasks"></a>Időszakos feladatok
A következő feladatok a **Készpénz- és bankkezelés** &gt; **Időszakos feladatok** pontban hajthatók végre.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Időszakos feladat</th>
<th>Leírás</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Egyenlegkorlát ellenőrzése</td>
<td>Ellenőrizze a kiválasztott készpénzszámla megadott napi egyenlegét, és jelenítse meg az eredményt egy információs üzenetben. Az egyenleg kiszámításánál csak a jóváhagyott tranzakciók számítanak. A <strong>Bérlista számára</strong> megjelöléssel ellátott tranzakciók nem számítanak bele az egyenlegbe.</td>
</tr>
<tr class="even">
<td>Készpénzegyenleg újraszámítása</td>
<td>E feladat segítségével győződjön meg arról, hogy a készpénzes számlákhoz tartozó főkönyvi egyenlegek és a készpénzegyenleg egyeznek.</td>
</tr>
<tr class="odd">
<td>Készpénzjelentés létrehozása (csak Lengyelország)</td>
<td><strong>Készpénzes</strong> jelentés létrehozása. A <strong>Készpénz</strong> jelentés száma a <strong>Jelentés számához</strong> beállított számsorozat alapján jön létre. A feladat párbeszédablakának <strong>Záró dátum</strong> mezőjében adja meg az utolsó dátumot, amelyhez a készpénztranzakciókat figyelembe kell venni a <strong>Készpénz</strong> jelentéshez. Használja a <strong>Szűrő</strong> funkciót a <strong>Belefoglalandó rekordok</strong> lapon, és adjon meg további feltételeket a készpénzes tranzakciók körének korlátozására. Ezek a kritériumok lehetnek készpénzes számlaszámok és pénznemkódok. A <strong>Létrehozó</strong> mezőben jelölje ki a felhasználót, aki felelős a jelentés létrehozásáért. A létrejött <strong>Készpénz</strong> jelentés megtekintéséhez használja a <strong>Készpénzjelentések</strong> gombot a <strong>Készpénzszámlák</strong> lapon.</td>
</tr>
<tr class="even">
<td>Készpénz - árfolyamkorrekció FIFO és LIFO (csak Lengyelország)</td>
<td>Kiszámítja az árfolyam-korrekciót a lengyel szabványoknak megfelelően. Használja a <strong>Szűrő</strong> funkciót a <strong>Belefoglalandó rekordok</strong> lapon, és adja meg a készpénzszámlát, amelyen a feladat le fog futni. Az összes nyitott időszak árfolyam-korrekciós különbözetének teljes újraszámításához jelölje be az <strong>Újraszámítás</strong> jelölőnégyzetet. Az árfolyam-korrekció kiszámítása a következőképpen történik az elsőként be, elsőként ki (FIFO) és az utolsóként be, elsőként ki (LIFO) módszerek alkalmazásánál:
<ul>
<li><strong>FIFO módszer</strong> – a rendszer keres egy kiadási tranzakciót, amelynek a tranzakciódátuma korábbi (kisebb rendelési számú), és rendezi egy olyan bevételezési tranzakcióval, amelynek korábbi a tranzakciódátuma (kisebb rendelési számú).</li>
<li><strong>LIFO módszer</strong> – a rendszer keres egy kiadási tranzakciót, amelynek a tranzakciódátuma későbbi (nagyobb rendelési számú), és rendezi egy olyan bevételezési tranzakcióval, amelynek későbbi a tranzakciódátuma (nagyobb rendelési számú).</li>
</ul>
A kiegyenlített összeg tükröződik a <strong>Kiegyenlített összeg pénzneme</strong> mezőben a <strong>Készpénztranzakció</strong> lapon. Árfolyam-korrekciós különbözet esetén az összeg megjelenik az <strong>Árfolyam-korrekció összege</strong> mezőben, és létrejön egy <strong>Árfolyamkülönbség</strong> bizonylattípusú tranzakció a <strong>Készpénztranzakció</strong> táblában. A nyereség/veszteség tranzakciók főkönyvi számlái a <strong>Pénznem</strong> táblában vannak beállítva (<strong>Árfolyam pénzügyi nyeresége</strong> és <strong>Árfolyam pénzügyi vesztesége</strong>).</td>
</tr>
<tr class="odd">
<td>Devizaátértékelés – készpénz</td>
<td>Ha a műveletek külföldi pénznemben vannak megadva, használja ezt a feladatot annak érdekében, hogy megfelelő egyenleg álljon rendelkezésre az alapértelmezett pénznemben a jelentési napon. Használja a <strong>Szűrő</strong> funkciót a <strong>Belefoglalandó rekordok</strong> lapon, és adja meg a készpénzszámlát, amelyen a feladat le fog futni. A feladat párbeszédpanelén használja a <strong>Kezdő pénznem</strong> és a <strong>Célpénznem</strong> mezőkbenet a tranzakció pénznemeinek megadásához. A rendszer összehasonlítja a konvertált pénznemben az összeget az alapértelmezett pénznemben megadott összeggel az adott napi átváltási árfolyam használatával. A két összeg közötti különbség (a korábbi árfolyam-korrekció nélkül) a számított árfolyam-korrekció. Ez a feladat <strong>Árfolyam-korrekció</strong> típusú, jóváhagyott készpénztranzakciót hoz létre. A főkönyvi tranzakció a készpénzes főkönyvi számla és a <strong>Nem realizált nyereség</strong> vagy <strong>Nem realizált veszteség</strong> formájában a <strong>Pénznem</strong> táblában megadott főkönyvi számla segítségével jön létre.</td>
</tr>
</tbody>
</table>

## <a name="inquiries-and-reports"></a>Lekérdezések és jelentések

| Lekérdezés vagy jelentés                             | Leírás                                                                                                                                                                                                                     |
|-----------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Készpénztranzakciók nézete                        | Bizonylatnaplósornál használja a **Lekérdezések** gombot a műveletpanelen a főkönyvi tranzakciók, a készpénzegyenleg és más információk megtekintéséhez.                                                                                  |
| Készpénztranzakció                              | Készpénzes tranzakciók megtekintéséhez lépjen a **Készpénz- és bankkezelés** &gt; **Lekérdezések és jelentések** &gt; **Készpénztranzakciók** elemre. Használja a **Szűrő** funkciót, és adjon meg további feltételeket a készpénzes tranzakciók körének korlátozására. |
| Regisztrálási napló (Észtország, Oroszország) | A **Készpénz- és bankkezelés** &gt; **Lekérdezések és jelentések** &gt; **Regisztrálási napló** pontban elérhető jelentés tükrözi az összes kiadott a bevételezési és készpénz-kifizetési bizonylatot.                                   |
| Pénztárkönyv (Lettország, Litvánia, Oroszország)     | A **Készpénz- és bankkezelés** &gt; **Lekérdezések és jelentések** &gt; **Pénztárkönyvi jelentés** a tényleges készpénzmozgásokat tükrözi (bevételek és kiadások).                                                            |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]