---
title: "A kelet-európai pénztár"
description: "Ez a témakör ismerteti a pénztár funkciót, amellyel a felhasználók az Észtország, Litvánia, Cseh Köztársaság, Magyarország, Lettország, Lengyelország és Oroszország Készpénzműveletek tükrözik a rendszerben."
author: ShylaThompson
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: RCashBalance, RCashCountStatementForm, RCashPosting, RCashRemainLimit, RCashReportJour_PL, RCashTable, RCashTableBalance, RCashTableCredLimit, RCashTableLastRevaluation, RCashTableTransactions, RCashTrans
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 268504
ms.assetid: ff2ea7b0-8de2-48c5-8f9f-5d95d9924925
ms.search.region: Czech Republic, Estonia, Hungary, Latvia, Lithuania, Poland, Russia
ms.author: v-elgolu
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
translationtype: Human Translation
ms.sourcegitcommit: 6bb98cc72c2ec0c1551412dd39d5bea3ce10e2cd
ms.openlocfilehash: e843abff91f74ff8c2c577f499fa829821fc56ee
ms.lasthandoff: 03/31/2017


---

# <a name="petty-cash-for-eastern-europe"></a>A kelet-európai pénztár

Ez a témakör ismerteti a pénztár funkciót, amellyel a felhasználók az Észtország, Litvánia, Cseh Köztársaság, Magyarország, Lettország, Lengyelország és Oroszország Készpénzműveletek tükrözik a rendszerben.

A pénztár funkcióival automatizálására műveletek, bevételek és kiadások készpénz, elsődleges dokumentumok létrehozását és a kapcsolódó jelentések nyomtatása. A pénztár a szolgáltatás lehetővé teszi az alábbi műveletek végezhetők:

-   A számla és a rendelkezésre álló készpénzből eszközök kiadásait.
-   Tipikus befizetési űrlapok készítése: készpénz befizetési bizonylatok, a készpénz-kifizetési bizonylatok és egy a pénztárbizonylatok regisztrációs naplója.
-   Ellenőrzés a legnagyobb készpénz összeg engedélyezett műveletek esetében, melyek a vevők, szállítók és így tovább.
-   Készpénzműveletek különböző pénznemekben tükrözik a rendszerben.
-   Készpénzműveletek összegeket át a könyvelési jelentések számára az alapértelmezett pénznemre, külföldi pénznemben.
-   Készítése a **a pénztárkönyv** jelentés és a pénztári jelentés.

## <a name="prerequisites"></a>Előfeltételek
A pénztár funkció használata előtt meg kell adnia a következő előfeltételek:

-   Pénztári számlák beállítása.
-   Készpénzfeladási profilok beállítása.
-   Készpénz-befizetési bizonylat számozásához használt számsorozatok beállítása.
-   Alapértelmezett értékek beállítása a készpénz és banki paraméterek.
-   Készpénz-befizetési naplónevek beállítása általában főkönyvi.

### <a name="set-up-cash-accounts"></a>Pénztári számlák beállítása

Nyissa meg a készpénz, a **készpénz-és banki**&gt;**bankszámlák**&gt;**készpénz számlák**, és adja meg a következő adatokat.

| Mező                 | Leírás                                                                                                          |
|-----------------------|----------------------------------------------------------------------------------------------------------------------|
| Készpénz                  | Adja meg a készpénzszámla (készpénz) azonosítására szolgáló kódot.                                                                    |
| Név                  | A készpénzszámla leírásának megadása.                                                                             |
| Pénznem              | Válassza ki az alapértelmezett pénznemkódot a készpénztranzakciókhoz.                                                              |
| Számsorozatcsoport | Ha a pénztárbizonylatok számozás különbözik, számozás van megadva a paraméterek, adjon meg egy kódot. |
| Több pénznem       | Jelölje be ezt a jelölőnégyzetet, engedélyezi a pénznemeket, amelyek különböznek az alapértelmezett pénznemben kell könyvelni.                     |
| Negatív készpénz         | Jelölje be ezt a jelölőnégyzetet a negatív készpénz egyenlegek lehetővé bármely pénznemben.                                               |

Készpénzegyenleg beállítása ellenőrzési szabályainak a készpénzszámla kiválasztása a készpénzszámla és ezután a műveletpanel a a **Pénztá** lapon, az a **egyenleg-határérték** csoport, kattintson a **egyenleg-határérték**. Adja meg a következő adatokat.

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
<td>Jelölje be a pénznem típusát:
<ul>
<li><strong>Pénznem</strong> – a vállalat alapvető pénznemkód.</li>
<li><strong>Megadott pénznem</strong> –, amely a vállalat alapvető pénznemkód eltér a pénznemkód.</li>
</ul></td>
</tr>
<tr class="even">
<td>Pénznem</td>
<td>Ha a kiválasztott <strong>jelzett pénznemben</strong> a a <strong>pénznem típusú</strong> mezőben, válassza ki azt a pénznemkódot. Ez a mező nem áll rendelkezésre, ha a kiválasztott <strong>pénznem</strong> a a <strong>pénznem típusú</strong> mezőben.</td>
</tr>
<tr class="odd">
<td>Egyenleg-határérték típusa</td>
<td>A rendelkezésre álló értékek közül választhat:
<ul>
<li><strong>Maximális</strong> – egyenleget nem szabadna haladja meg a <strong>egyenleg-határérték</strong> összege a készpénzszámlához (felső határ).</li>
<li><strong>Minimális</strong> – egyenleget nem szabadna go alatt a <strong>egyenleg-határérték</strong> összege a készpénzszámlához (kötött lent).</li>
</ul></td>
</tr>
<tr class="even">
<td>Egyenlegkorlát ellenőrzése</td>
<td>Válassza ki, mi történik a készpénz-befizetési bizonylatok jóváhagyási eljárás során, ha a <strong>egyenleg-határérték</strong> a készpénzszámla túllépik az összeg:
<ul>
<li><strong>Fogadja el</strong> – a határérték túllépése is.</li>
<li><strong>Figyelmeztetés</strong> – a határérték túllépése is, de a felhasználó figyelmeztető üzenetet kap. A Készpénzdokumentum megerősítette vagy jóváhagyta.</li>
<li><strong>Hiba</strong> – nem lépheti túl a határértéket. A felhasználó hibaüzenetet kap, és a készpénz-befizetési bizonylat nem megerősítette vagy jóváhagyta.</li>
</ul>
A készpénz-befizetési bizonylatok jóváhagyási folyamat kapcsolatos további tudnivalókért lásd a &quot;tranzakció jóváhagyási és feladási pénzbeli&quot; rész a témakör későbbi részében található.</td>
</tr>
<tr class="odd">
<td>Egyenleg korlátja</td>
<td>A Készpénz-számlaegyenleg korlát megadása. Az összeg a megadott pénznemben kell lennie.</td>
</tr>
</tbody>
</table>

### <a name="set-up-cash-posting-profiles"></a>Feladási profilok beállítása

Készpénzfeladási profilok a főkönyvi feladások határozza meg. Feladási profil készpénzes beállításához nyissa meg **készpénz****és a bank kezelése**&gt;**telepítő**&gt;**készpénz feladási profilok**, és válassza ki vagy hozza létre a feladási profilt. Adja meg a következő adatokat.

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
<td>Válassza ki, hogy a feladási profil egy adott készpénzszámla vagy minden készpénzszámlák vonatkozik:
<ul>
<li><strong>Táblázat</strong> – ha készpénzes számlát a feladási profil sort, a sor készpénz-tranzakció feladása szolgál.</li>
<li><strong>Minden</strong> – nem a készpénzszámla feladási profil sorban szerepel.</li>
</ul></td>
</tr>
<tr class="even">
<td>Készpénz</td>
<td>Ha a kiválasztott <strong>tábla</strong> a a <strong>érvényes</strong> mezőben, akkor adja meg a készpénzes számlát. Ez a mező üresen marad, ha a kiválasztott <strong>minden</strong> a a <strong>érvényes</strong> mezőben.</td>
</tr>
<tr class="odd">
<td>Főkönyvi számla</td>
<td>Adja meg a főkönyvi készpénzszámla használja az összegző számla számát.</td>
</tr>
</tbody>
</table>

### <a name="set-up-number-sequences-for-cash-documents"></a>Készpénz-befizetési bizonylatok számsorozatainak beállítása

Készpénz-befizetési bizonylatok számsorozatainak beállítása, látogasson el **készpénz-és banki**&gt;**a telepítő**&gt;**banki paraméterek**. A a **számsorozat** fülre, adja meg a számsorozat-kódok a **készpénz-befizetési bizonylatok**, **készpénz-kifizetési pénztárbizonylatok**, **Készpénzkorrekciós bizonylat**, és **árfolyam-korrekció** dokumentumokat, és a **készpénz-befizetési bizonylat száma**.

### <a name="set-up-default-values-for-cash-and-bank-management-parameters"></a>Alapértelmezett értékek beállítása a készpénz és banki kezelési paraméterek

Alapértelmezett értékek beállítása a készpénz és a bank a pénztár funkció paramétereinek kezelése, Ugrás **banki kezelési**&gt;**a telepítő**&gt;**banki paraméterek**. A a **készpénz** fülre, adja meg a következő adatokat.

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
<td>Válassza ki az alapértelmezett készpénzszámla naplók.</td>
</tr>
<tr class="even">
<td>Készpénzfeladás</td>
<td>Adja meg a feladási profilt, amely akkor használatos, ha más feladási profil nincs megadva alapértelmezett készpénz.</td>
</tr>
<tr class="odd">
<td>Felhasznált bizonylat ellenőrzése</td>
<td>Válassza ki, mi történik, ha a készpénz-befizetési bizonylat száma, az ellenőrzés során talált ismétlődő számokat:
<ul>
<li>Ismétlődések tiltása</li>
<li>Ismétlődések pénzügyi évben</li>
<li>Ismétlődések elfogadása</li>
<li>Figyelmeztetés ismétlődés esetén</li>
</ul></td>
</tr>
<tr class="even">
<td>Műveletek korlátjának ellenőrzése</td>
<td>Adja meg, mi történik ellenoldali felek műveletek esetében a határérték túllépése esetén:
<ul>
<li><strong>Fogadja el</strong> – a határérték túllépése is.</li>
<li><strong>Figyelmeztetés</strong> – a határérték túllépése is, de a felhasználó figyelmeztető üzenetet kap. A művelet fel van adva.</li>
<li><strong>Hiba</strong> – nem lépheti túl a határértéket. A felhasználó hibaüzenetet kap, és a művelet nem könyveli.</li>
</ul></td>
</tr>
<tr class="odd">
<td>Ellenőrzési mód</td>
<td>Az ellenőrzési túllépte maximális összegek műveletekhez használt érvényesítési módszer kiválasztása:
<ul>
<li><strong>A művelet</strong> – érvényesítésben tranzakciónként</li>
<li><strong>Megállapodás</strong> – ellenőrzés egy megadott szerződést egy ellenoldali féllel tranzakciónként történik.</li>
</ul></td>
</tr>
<tr class="even">
<td>Műveletek korlátja</td>
<td>Adja meg a maximális összeget, készpénzben ellenoldali felek műveletek esetében engedélyezett.</td>
</tr>
<tr class="odd">
<td>Feladás korábbi dátummal</td>
<td>Jelölje be ezt a jelölőnégyzetet ahhoz, hogy a készpénzes tranzakciók könyvelését, a készpénztranzakció utolsó napját megelőzően.</td>
</tr>
<tr class="even">
<td>Dimenziók</td>
<td>Adja meg a dimenziók a <strong>Költséghely kód</strong>, <strong>analitikai kód</strong>, és <strong>kód rendeltetésű</strong> mezők. Készpénz-befizetési bizonylatok nyomtatása űrlap ezt az információt fogja tükrözni.</td>
</tr>
<tr class="odd">
<td>Jóváhagyási állapot használata</td>
<td>Jelölje be a jelölőnégyzetet, egy további állapot használandó <strong>megerősítve</strong>, a készpénz-befizetési bizonylatok jóváhagyási eljárás során. (További információért lásd: a &quot;tranzakció jóváhagyási és feladási készpénz&quot; szakaszt.)</td>
</tr>
</tbody>
</table>

### <a name="set-up-cash-journal-names-in-general-ledger"></a>Készpénz-befizetési naplónevek beállítása általában főkönyvi

Készpénz-befizetési tranzakciók feladási napló létrehozása, látogasson el **főkönyvi**&gt;**napló beállítása**&gt;**Naplónevek**, és hozzon létre egy új rekordot. A a **típus** mezőben, adja meg **készpénz**. Más alapértelmezett napló paraméterek meghatározása, mint szükséges.

## <a name="daily-cash-operations-via-a-slip-journal"></a>Napi Készpénzműveletek naplója egy keresztül
A Készpénzdokumentum keresztül egy napló létrehozásához, lépjen **készpénz-és banki**&gt;**tranzakciók készpénz**&gt;**naplója**, és hozzon létre egy új naplót. Kattintson a műveletpanel a **vonalak**. Új sor hozzáadásához, és írja be a következő adatokat.

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
<td>A készpénzszámla kiválasztása. Alapértelmezés szerint egy készpénzes számlát a banki kezelési paraméterek van megadva.</td>
</tr>
<tr class="odd">
<td>Leírás</td>
<td>Magyarázó szöveg megadása a tranzakcióhoz.</td>
</tr>
<tr class="even">
<td>Tartozik-követel</td>
<td>Készpénz-befizetési bizonylat összege meg a következő mezők egyikén:
<ul>
<li><strong>Tartozik</strong> – a mező használatával pénzbevételek és a bevételezési pénztárbizonylat regisztrálni.</li>
<li><strong>Hitel</strong> – ezt a mezőt használja a pénztári kiadások és a készpénz-kifizetési bizonylat regisztrálása.</li>
</ul></td>
</tr>
<tr class="odd">
<td>Ellenszámla Ellenszámla típusa</td>
<td>Az Ellenszámla típusa és eltolás számlaszámának kiválasztása.</td>
</tr>
<tr class="even">
<td>Pénznem</td>
<td>Válassza ki a tranzakció pénznemének kódját.</td>
</tr>
<tr class="odd">
<td>Bizonylat </td>
<td>Ezt a mezőt automatikusan kitölti, a napló beállítása alapján.</td>
</tr>
<tr class="even">
<td>Rendelés száma</td>
<td>Ha nincs más számsorozatot a készpénzszámla, ez a mező ki van töltve automatikusan, a paraméterekben megadott számsorozat alapján. Ez a mező egy rendelési szám manuális bevitele, van szüksége. A készpénz-befizetési bizonylat számozása inconsistence megelőzése érdekében a következő vezérlőre alkalmazandó:, amely a művelet dátuma korábbi, mint a készpénzbizonylat száma nem lehet nagyobb, mint egy későbbi dátumú művelet Készpénzbizonylat száma. Ha a vezérlő nem szükséges, jelölje be a <strong>feladás dátuma korábbi</strong> a banki kezelési paraméterek jelölőnégyzetet.</td>
</tr>
<tr class="odd">
<td>Jóváhagyási állapot</td>
<td>Az első tranzakció állapota <strong>nincs</strong>. A tranzakció állapota beállításával kapcsolatos tudnivalókért tanulmányozza a &quot;tranzakció jóváhagyási és feladási pénzbeli&quot; szakasz.</td>
</tr>
<tr class="even">
<td>Dokumentumtípus </td>
<td>Ez a mező a <strong>pénztárbizonylat</strong> lap automatikusan kitölti, a készpénz-befizetési bizonylat megadott mennyisége alapján:
<ul>
<li><strong>Készpénz-befizetési pénztárbizonylatokból</strong> – ezt az értéket használja, ha az összeget adott meg a <strong>tartozik</strong> a készpénzszámla mezőt.</li>
<li><strong>Készpénz-kifizetési bizonylat</strong> – ezt az értéket használja, ha az összeget adott meg a <strong>hitel</strong> mezőt a készpénzszámla</li>
<li><strong>Korrekciós</strong> – beírt negatív összeg a <strong>tartozik</strong> mező vagy a <strong>hitel</strong> a készpénzszámla mezőt.</li>
</ul></td>
</tr>
<tr class="odd">
<td>Áfacsoport</td>
<td>Adjon meg egy áfacsoportot kiszámítására a műveletet.</td>
</tr>
<tr class="even">
<td>Cikkáfacsoport</td>
<td>Adjon meg egy cikk áfacsoportja a művelet kiszámítására.</td>
</tr>
<tr class="odd">
<td>Jogcím</td>
<td>A a <strong>pénztárbizonylat</strong> fülre, adja meg a tranzakció tárgy leírását. Ez a szöveg a pénztárbizonylat formanyomtatvány nyomtatja.</td>
</tr>
<tr class="even">
<td>Dokumentum dátuma</td>
<td>Adja meg a leírás, számát és dátumát az elsődleges dokumentum, amely a tranzakció (például előzetes jelentések, számla vagy rendelés) oka.</td>
</tr>
<tr class="odd">
<td>Képviselő típusa</td>
<td>Ez a mező a következő értékeket veheti fel:
<ul>
<li><strong>Dolgozó</strong> – a <strong>képviselő</strong> keresési alkalmazottak listáját tartalmazza, ha a <strong>ellenszámla</strong> mező értéke <strong>főkönyvi</strong> vagy <strong>Bank</strong>, vagy egy kapcsolattartó személyek, ha az ellenoldali fél listáját a <strong>ellenszámla</strong> mező értéke <strong>vevő</strong> vagy <strong>szállító</strong>. Képviselői beállításához nyissa meg <strong>alapvető</strong>&gt;<strong>a telepítő</strong>&gt;<strong>kapcsolatok</strong>&gt;<strong>kapcsolattartó személy</strong>.</li>
<li><strong>Egyéb</strong> – a <strong>képviselő</strong> keresési más ügyfelek listáját tartalmazza. Állíthatja be a vevőknek, akik nem jelennek meg a <strong>vevők</strong> vagy <strong>szállítók</strong> táblát, keresse fel <strong>főkönyvi</strong>&gt;<strong>vevők</strong>. Ez a típus csak Lettország esetében érhető el. (A <strong>CSELatvia</strong> engedélyezni kell a konfigurációs kulcsot.)</li>
<li><strong>Szállítói</strong> – a <strong>képviselő</strong> keresési szállítók listáját tartalmazza. Szállítók beállítása Ugrás <strong>kötelezettségek</strong>&gt;<strong>szállítók</strong>.</li>
<li><strong>Vevő</strong> – a <strong>képviselő</strong> keresési vevők listáját tartalmazza. Vevők beállítása Ugrás <strong>követelések</strong>&gt;<strong>vevők</strong>.</li>
</ul></td>
</tr>
<tr class="even">
<td>Jellegzetes</td>
<td>Jelölje ki a megadott típusú képviselője a <strong>képviselő típusa</strong> mezőben.</td>
</tr>
<tr class="odd">
<td>A személy neve</td>
<td>Ezt a mezőt automatikusan kitölti, alapján a <strong>ellenszámla</strong> és <strong>képviselő</strong> mezők. A Nyomtatás képernyő pénztárbizonylatok ezt az információt fogja tükrözni.</td>
</tr>
<tr class="even">
<td>Személyi igazolvány</td>
<td>Ezt a mezőt automatikusan kitölti, a kapcsolattartó (képviselője) a személyazonosító igazolvány adatai alapján. Ha a <strong>Ellenszámla típusa</strong> mező értéke <strong>előlegre jogosult</strong>, és a <strong>ellenszámla</strong> mező értéke az alkalmazott számát, a készpénz-befizetési utalványok vagy kiadásai teheti ki, illetve az alkalmazott. Ebben az esetben a <strong>személyazonossági igazolvány száma:</strong> mező ki van töltve automatikusan az igazolvány származó adatok segítségével a <strong>alkalmazott</strong> táblázat (<strong>alkalmazott számviteli</strong>&gt;<strong>alkalmazott tábla</strong>).</td>
</tr>
<tr class="odd">
<td>Cél</td>
<td>A a <strong>célra</strong> table, egy vagy több rendeltetési hely-kódokat a tranzakció összegének meghatározása. Válasszon ki egy rendeltetési kódot a <strong>célra</strong> mezőben, és írja be a magyarázatot a <strong>tranzakció szövege</strong> mezőben. A a <strong>összeg</strong> mezőjébe írja be az összeget a tranzakció pénznemében. A <strong>%</strong> mező azt mutatja, a tranzakció teljes összegét összeg cél aránya százalékban.</td>
</tr>
<tr class="even">
<td>Maradvány</td>
<td>Számított fennmaradó összeg. Fontos megjegyezni, hogy a teljes tranzakció összege rendeltetési hely-kódokat kell rendelni.</td>
</tr>
<tr class="odd">
<td>Hivatalnokok</td>
<td>A a <strong>tisztviselői</strong> fülre, adja meg a neveket és címeket felelős személyek: igazgató, vezető könyvelő és pénztáros. A <strong>helyzet</strong> értékek határozzák meg a telepítő tisztviselők által a <strong>általános</strong> és <strong>főkönyvi</strong> lapján a <strong>tisztviselők</strong> lap (<strong>alapvető</strong>&gt;<strong>telepítő</strong>&gt;<strong>kapcsolattartók</strong>&gt;<strong>tisztviselők</strong>).</td>
</tr>
<tr class="even">
<td>Előleg</td>
<td>Jelölje be ezt a jelölőnégyzetet, ha a tranzakció egy előleg.</td>
</tr>
<tr class="odd">
<td>Feladási profil</td>
<td>A készpénzszámla adja meg a feladási profilhoz. Alapértelmezés szerint a banki paraméterek megadott feladási profilt használja.</td>
</tr>
<tr class="even">
<td>Ellenszámla feladási sablonja</td>
<td>A feladási profil megadása a kijelölt ellenszámla.</td>
</tr>
<tr class="odd">
<td>Teljes összeg</td>
<td>A a <strong>teljes összege</strong> mezőcsoportban a lap alján a <strong>Reimb</strong> a mező mutatja az összes vonatkozó összes készpénz bevételezési bizonylatok, amelyek szerepelnek az aktuális napló számított és a <strong>Disb</strong> a mező mutatja az összes a készpénz-kifizetési bizonylatok.</td>
</tr>
</tbody>
</table>

A műveletpanel a naplóbejegyzések ellenőrzéséhez kattintson az **ellenőrzi a**.

## <a name="daily-cash-operations-via-a-general-journal"></a>Napi Készpénzműveletek főkönyvi naplón keresztül
A készpénztranzakció keresztül a főkönyvi napló létrehozásához, lépjen **főkönyvi**&gt;**naplóbejegyzések**&gt;**főkönyvi naplók**, és hozzon létre egy új naplót. Kattintson a műveletpanel a **vonalak**. Új sor hozzáadásához, és írja be a következő adatokat.

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
<td>Válassza ki <strong>pénztár</strong>.</td>
</tr>
<tr class="odd">
<td>Könyvelési számla</td>
<td>A pénztárbizonylat számlaszámának kiválasztása.</td>
</tr>
<tr class="even">
<td>Tranzakció szövege</td>
<td>Magyarázó szöveg megadása a tranzakcióhoz.</td>
</tr>
<tr class="odd">
<td>Tartozik-követel</td>
<td>Készpénz-befizetési bizonylat összege meg a következő mezők egyikén:
<ul>
<li><strong>Tartozik</strong> – a mező használatával pénzbevételek és a bevételezési pénztárbizonylat regisztrálni.</li>
<li><strong>Hitel</strong> – ezt a mezőt használja a pénztári kiadások és a készpénz-kifizetési bizonylat regisztrálása.</li>
</ul></td>
</tr>
<tr class="even">
<td>Ellenszámla Ellenszámla típusa</td>
<td>Az Ellenszámla típusa és eltolás számlaszámának kiválasztása.</td>
</tr>
<tr class="odd">
<td>Pénznem</td>
<td>Válassza ki a tranzakció pénznemének kódját.</td>
</tr>
</tbody>
</table>

A a **számla** lapon adhatja meg a feladási profilok a kijelölt számla és ellenszámla. Ha a regisztrált tranzakció egy előleg, jelölje be a **előleg** jelölőnégyzetet az **fizetési** fülre. A a **képviselő** mezőcsoportban, töltse ki a mezőket, ahogy a Slip naplósorok nyomtatása a **készpénz** jelentés. A műveletpanel a naplóbejegyzések ellenőrzéséhez kattintson az **ellenőrzi a**.

## <a name="cash-transaction-approval-and-posting"></a>Készpénzes tranzakció jóváhagyása és feladása
Készpénz-befizetési tranzakciók esetén a következő állapotok alkalmazható: **nincs**, **megerősített**, **jóváhagyott**, és **elutasított**. A **jóváhagyási állapot használata** paraméter a **jóváhagyási** gyorslapján a **készpénz** a lap **banki kezelési**&gt;**telepítő**&gt;**banki paraméterek** lehetővé teszi két további állapotok aktiválása: **megerősítve** és **elutasított**. Megerősítés akkor alkalmazható, ha a készpénz okmányt adnak ki, és a készpénz-befizetési utalványok vagy kiadásai az alkalmazottak két közösen: könyvelő és pénztáros. A **állapot alaphelyzetbe állítása** függvény az aktuális tranzakció állapota változik. **Jóváhagyott** válik **megerősítve**, és **megerősítve** válik **nincs**. Készpénz-befizetési napló bejegyzéseinek szerkeszthető állapot esetén csak **sem**. A készpénzes tranzakciók lehet elutasítani, csak akkor, ha a tranzakció állapota **megerősítve**. Elutasította a készpénz-befizetési bizonylatok szerepelnek a **pénztárbizonylatok regisztrációs naplója** jelentés, de nem követhető nyomon a **pénztárkönyv** jelentés. Erősítse meg a tranzakciót, jelölje be a megfelelő Slip naplósorban, és kattintson **dokumentumok jóváhagyási**&gt;**megerősítése**. Egy rendelésszámot jön létre, a megadott számsorozat alapján. A tranzakció állapota változott **megerősítve**, és nem lehet szerkeszteni a naplósorban. A készpénzes számla egyenlege változatlan marad. Készpénz-befizetési bizonylatok elutasítását, kattintson a **dokumentumok jóváhagyási**&gt;**elutasítása**. Ez a beállítás csak a dokumentumok érhető el **megerősítve** állapotát. Egy tranzakció jóváhagyása, válassza ki a megfelelő Slip naplósorban, és kattintson a **dokumentumok jóváhagyási**&gt;**jóváhagyás**. A **jóváhagyott** állapot azt jelzi, hogy a pénzalapok kapott vagy feljegyzi. A készpénzegyenleg módosul. A készpénztranzakció lehet feladni. Megszakítja egy **jóváhagyott** állapot és az állapot alaphelyzetbe állítása **nincs**, kattintson a **dokumentumok jóváhagyási**&gt;**állapot alaphelyzetbe állítása**. Csak a jóváhagyott készpénzes tranzakciók könyvelhetők. Napló könyvelése, kattintson a **feladása**&gt;**feladása**.

## <a name="print-a-cash-order"></a>A készpénz-befizetési utalvány nyomtatása
A készpénz-befizetési utalvány nyomtatása, válassza ki a napló sorának és, majd kattintson a műveletek ablaktábla **nyomtatása**&gt;**készpénzutalvány-jelentés**. A rendszer létrehoz egy bevételezési pénztárbizonylat vagy a készpénz-kifizetési bizonylat, attól függően, hogy az összeg bekerül a nyomtatási űrlapot a **tartozik** mező a vagy **hitel** a kijelölt sor mező:

-   Ha az összeg a **tartozik** mező: készpénz-befizetési pénztárbizonylatokból
-   Ha az összeg a **hitel** mező: készpénz-kifizetési bizonylat

SLIP naplósorra, amelyen **megerősítve**, **jóváhagyott**, vagy **elutasított** állapotát is kinyomtathatók. Kinyomtathatja a pénztárbizonylatok rendelés, **készpénz-és banki**&gt;**Inquires és a jelentések**&gt;**pénztárbizonylat**.

## <a name="periodic-tasks"></a>Időszakos feladatok
A következő feladatok hajthatók végre **készpénz-és banki**&gt;**időszakos feladatok**.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Ismétlődő feladat</th>
<th>Leírás</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Egyenlegkorlát ellenőrzése</td>
<td>Ellenőrizze az egyenleget a kiválasztott készpénzszámla a megadott napon, és az eredmény megjelenítése az információs üzenet. Csak a jóváhagyott tranzakciók egyenleg kiszámításánál is számít. Megjelölt tranzakciók <strong>Bérlista</strong> nem tekinthető.</td>
</tr>
<tr class="even">
<td>Készpénzegyenleg újraszámítása</td>
<td>Ez a feladat segítségével győződjön meg arról, hogy a készpénzes számlákhoz tartozó főkönyvi egyenlegek fér el az egyenleget.</td>
</tr>
<tr class="odd">
<td>Készpénzjelentés létrehozása (a csak Lengyelország)</td>
<td>Hozzon létre egy <strong>készpénz</strong> jelentés. A <strong>készpénz</strong> jelentés száma a beállított számsorozat alapján jön létre <strong>bizonylat száma</strong>. A párbeszédablakban mezőbe a feladat, a <strong>dátum</strong>, mely készpénz tranzakciók kell figyelembe venni az utolsó dátumát adja meg a <strong>készpénz</strong> jelentés. Használja a <strong>szűrő</strong> működik a a <strong>bejegyzéseket</strong> fülre, és adja meg a további feltételeket a készpénzes tranzakciók választékát korlátozni. Ezek a kritériumok lehetnek készpénz számlaszámok és pénznemkódok. A a <strong>létre</strong> mezőben, jelölje ki a felhasználót, aki felelős a jelentés létrehozásához. Megtekintése a <strong>készpénz</strong> jelentés készül, amely használja a <strong>készpénz jelentések</strong> gombja a <strong>készpénz számlák</strong> lap.</td>
</tr>
<tr class="even">
<td>Készpénz - beállítása FIFO Exchange és a LIFO (a csak Lengyelország)</td>
<td>Számítsuk ki az árfolyam-korrekció / lengyel szabványoknak. Használja a <strong>szűrő</strong> működik a a <strong>bejegyzéseket</strong> fülre, és adja meg a feladat futtatásához a készpénzszámla. Válassza ki a <strong>újraszámítása</strong> jelölőnégyzetet az összes nyitott időszak árfolyam-korrekció különbözet teljes változtatáshoz. Íme, az árfolyam-korrekció kiszámításának amikor először ki (FIFO), az első és utolsó be, első ki (LIFO) módszereket alkalmaznak:
<ul>
<li><strong>FIFO módszer</strong> – a rendszer keres egy kiadási tranzakció egy korábbi tranzakció dátuma (kisebb rendelési szám) és rendezi azt a bevételezési tranzakciót, amelynek egy korábbi tranzakció dátuma (kisebb rendelési szám).</li>
<li><strong>LIFO módszer</strong> – a rendszer keres egy kiadási tranzakció egy későbbi tranzakció dátuma (nagyobb rendelési szám) és rendezi azt a bevételezési tranzakciót, amelynek egy későbbi tranzakció dátuma (nagyobb rendelési szám).</li>
</ul>
A kiegyenlített összeg tükröződik a <strong>pénznemben kiegyenlített</strong> mezőjében a <strong>tranzakció készpénzfizetési</strong> lap. Helyesbítés árfolyam-különbözet esetén az összeg megjelenik a <strong>Árfolyambeállítás összege</strong> mezőben, és a tranzakciót a <strong>Árfolyamkülönbség</strong> Bizonylattípus jön létre a <strong>tranzakció készpénzfizetési</strong> táblában. Nyereség/veszteség tranzakciók főkönyvi számláit is meg vannak a <strong>pénznem</strong> táblázat (<strong>pénzügyi árfolyamnyereség</strong> és <strong>pénzügyi árfolyamveszteség</strong>).</td>
</tr>
<tr class="odd">
<td>Devizaátértékelés – készpénz</td>
<td>Használja ezt a feladatot a jelentési dátum, amikor a műveletek külföldi pénznemben megadott rendelkezik egy megfelelő egyensúlyt az alapértelmezett pénznemben. Használja a <strong>szűrő</strong> működik a a <strong>bejegyzéseket</strong> fülre, és adja meg a feladat futtatásához a készpénzszámla. Ezen a párbeszédpanelen a feladat, a <strong>a pénznem</strong> és <strong>a pénznem</strong> mezőkben adja meg a tranzakció pénznemek. A rendszer összehasonlítja az összeg a pénznem árfolyam használatával a kijelölt napon az összeg az alapértelmezett pénznemben lett konvertálva. (A korábbi árfolyam-korrekció nélkül) a két összeg közötti különbség a számított árfolyam-korrekció. Ezt a feladatot hoz létre, a jóváhagyott készpénztranzakció a <strong>árfolyam-korrekció</strong> típusa. A főkönyvi tranzakció jön létre a készpénz és a megadott főkönyvi számla a főkönyvi számla segítségével <strong>nem realizált nyereség</strong> vagy <strong>nem realizált veszteség</strong> a a <strong>pénznem</strong> táblában.</td>
</tr>
</tbody>
</table>

## <a name="inquiries-and-reports"></a>Lekérdezések és jelentések
| Lekérdezés vagy jelentés                             | Leírás                                                                                                                                                                                                                     |
|-----------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| A készpénzes tranzakciók megtekintése                        | Slip naplósorban használja a **vizsgálatok** gombra a műveletpanelen főkönyvi tranzakciók megtekintése, egyenleget és más információk.                                                                                  |
| Készpénztranzakció                              | Keresse fel **készpénz-és banki**&gt;**lekérdezések és jelentések**&gt;**tranzakciók készpénz** a készpénzes tranzakciók megtekintése. Használja a **szűrő** függvény adja meg a további feltételeket a készpénzes tranzakciók választékát korlátozni. |
| (Észtország, Oroszország) a regisztrációs naplója | A jelentés a **készpénz-és banki**&gt;**lekérdezések és jelentések**&gt;**regisztrációs naplója** tükrözi a bevételezési és a készpénz-kifizetési bizonylatok kiadott.                                   |
| Pénztárkönyv (a Lettország, Litvánia, Oroszország)     | A jelentés a **készpénz-és banki**&gt;**lekérdezések és jelentések**&gt;**pénztári jelentés könyv** tükrözi a tényleges készpénz alap mozgások (bevételek és kiadások).                                                            |




