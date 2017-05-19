---
title: "Előlegre jogosultak"
description: "Tudjon meg többet a Microsoft Dynamics 365 for Operations előlegre jogosulti funkciójáról."
author: ShylaThompson
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 262574
ms.assetid: 87924785-6032-4125-8279-5b1a758f4d80
ms.search.region: Czech Republic, Estonia, Hungary, Latvia, Lithuania, Poland, Russia
ms.author: v-elgolu
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: 0f34bfed64507944cadf5b02e3c7222f17803f92
ms.contentlocale: hu-hu
ms.lasthandoff: 04/25/2017


---

# <a name="advance-holders"></a>Előlegre jogosultak

[!include[banner](../includes/banner.md)]


Tudjon meg többet a Microsoft Dynamics 365 for Operations előlegre jogosulti funkciójáról.

*Előlegre jogosultnak* egy vállalat azon alkalmazottját nevezzük, aki egy a szervezet által biztosított költségösszegért felel. Előlegre jogosult csak vállalati dolgozó lehet. Beszerzéskor az előlegre jogosult jelenti a vállalatnak a foganatosított kiadásokat. A vállalat a költség összegét megtéríti az alkalmazottnak. A vállalat minden előlegre jogosult egyenlegét vezeti. Az Észtország, Lettország, Litvánia, Lengyelország, Cseh Köztársaság, Magyarország és Oroszország területén működő jogi személyek felhasználói a szervezet által biztosított költségösszegért felelős alkalmazottak által végzett műveletekre vonatkozó konkrét tranzakciókat kezelhetnek.

## <a name="set-up-an-advance-holder"></a>Előlegre jogosult beállítása
Előlegre jogosult beállításához a következő feladatokat kell sorrendben elvégezni.
1.  Előlegre jogosult csoportok létrehozása.
2.  Alkalmazott feladási sablonjának beállítása.
3.  Kötelezettségek paramétereinek beállítása.
4.  Konkrét fizetési feltételek létrehozása az előlegre jogosult számára.
5.  Előlegre jogosult létrehozása.

### <a name="advance-holder-groups"></a>Előlegre jogosult csoportok

Használja az **Előlegre jogosult csoportok** oldalt az előlegre jogosult csoport létrehozásához. Megadhatja a nevet, a leírást és az ellenszámlát az előlegre jogosult csoporthoz.
### <a name="employee-posting-profile"></a>Alkalmazott feladási sablonja

Az előlegre jogosult tranzakcióihoz sablon létrehozásához használja az **Alkalmazott feladási sablonjai** oldalt. Az alkalmazott feladási sablonjához a következő adatokat adhatja meg.
|Mező |Leírás|
|------|-----------|
|Feladási profil|Adja meg a feladási sablon azonosító kódját az előlegre jogosulthoz.|
|Leírás|Adja meg a feladói sablon rövid leírását.|
|Érvényes|A feladási sablon beállításához használt csoportosítási szinthez a következő lehetőségek közül választhat: 
**Tábla** – ezt a beállítást használhatja a feladási sablon egy előlegjogosult számára történő beállításához. Az előleg jogosultjának kódját meg kell adni a Hivatkozás mezőben.
**Csoport** – ezt a beállítást használhatja a feladási sablon előlegjogosultak csoportja számára történő beállításához. Az csoport kódját meg kell adni a Hivatkozás mezőben.
**Mind** – ezt a beállítást használhatja a feladási sablon az összes előlegjogosult számára történő beállításához.| |Hivatkozás|Válassza ki az előlegjogosult kódját, ha az Érvényes mezőben a Tábla lehetőség van kiválasztva, illetve válassza ki az előlegjogosulti csoportot, ha az Érvényes mezőben a Csoport lehetőség van kiválasztva.| |Összegzett számla|Válassza ki a tranzakciók feladására szolgáló összegzett számlát.|



### <a name="account-payable-parameters"></a>Kötelezettségek paraméterei

Az előlegre jogosult tranzakcióinak tükrözéséhez be kell állítania a következőket a **Kötelezettségek paraméterei** lapon az **Előlegre jogosultak** szakaszban.
|                                                |                   |
|------------------------------------------------|-------------------|
|  **Mező**                                     | **Leírás**                                                                                                                                                                  |
| **Feladási profil**                            | Válassza ki az alapértelmezett sablont az előlegre jogosultak tranzakcióinak elvégzéséhez.                                                                                                         |
| **Előlegre jogosultak rendezése**                     | Ha ki van jelölve, az előlegre jogosultak a lista elején jelennek meg az **Előlegre jogosultak** oldalon.                                                                     |
| **Kibocsátás nyitott egyenleg esetén**                 | Ha ki van jelölve, engedélyezve lesz a készpénzelőleg kiadása azon előlegre jogosult számára, aki nyitott pozitív egyenleggel rendelkezik.                                                                      |
| **Egyenleg zárása készpénz-mezőcsoporttal: Név** | Válassza ki a pénztárbizonylat naplókódját. Ez a naplókód használatos készpénz-kifizetési bizonylatok és bevételezési pénztárbizonylatok létrehozásához az előlegre jogosult egyenlegének készpénzes lezárásakor. |
| **Készpénz**                                       | Válassza ki a készpénzszámlát az előlegre jogosult egyenlegének lezárásához használt bizonylatok meghatározásárához.                                                                 |
| **Egyenleg zárása bankmezőcsoporttal: Név** | Válassza ki az egyenlegek banki lezárásához használt tranzakciók naplókódját.                                                                                                   |
| **Számla típusa**                               | Válassza ki az egyenlegek banki lezárásához használt bankot.                                                                                                        |
| **Fő számla**                               | Válassza ki az egyenlegek banki lezárásához használt bankszámlakódot.                                                                                           |

### <a name="terms-of-payment-for-advance-holder"></a>Előlegre jogosultra érvényes fizetési feltételek

Beszerzési rendelés előlegre jogosulton keresztül történő megfelelő rögzítéséhez és feladásához olyan fizetési feltételeket kell használnia, amelyeknél a **Kezdő előlegre jogosult** beállítás értéke **Igaz**.
### <a name="create-an-advance-holder-creation"></a>Előlegre jogosult létrehozása

Előlegre jogosult létrehozása előtt beállított dolgozókkal kell rendelkeznie. További tudnivalókért lásd: [Dolgozó adatainak megadása (Feladat-útmutató).](http://ax.help.dynamics.com/en/wiki/enter-worker-information/) Használja az **Előlegre jogosultak** oldalt a dolgozó előlegre jogosultként történő beállításához. Válassza ki a dolgozót, akit előlegre jogosultként kíván használni, kattintson a **Szerkesztés** elemre, majd állítsa az **Előlegre jogosult** lehetőséget **Igaz** értékre. A következő mezőket szintén ki kell töltenie.
|                |                                                                                             |
|----------------|---------------------------------------------------------------------------------------------|
| **Mező**      | **Leírás**                                                                             |
| **Csoport**      | Válasszon ki előlegre jogosult csoportot.                                                             |
| **Sorozatok**     | Adja meg a dokumentumsorozatot, amely az előlegre jogosult azonosítására szolgál. |
| **Szám**     | Adja meg a dokumentum számát, amely az előlegre jogosult azonosítására szolgál. |
| **Kiadás dátuma** | Válassza ki vagy írja be a dokumentum kibocsátási dátumát.                                                    |
| **Kiállította:**  | Adja meg az okmányt kiállító hatóság vagy személy részleteit.                       |

## <a name="advance-holder-inquiries-and-reports"></a>Előlegre jogosulttal kapcsolatos lekérdezések és jelentések
### <a name="advance-holder-transactions-inquiry"></a>Előlegre jogosult tranzakcióinak lekérdezése

Előlegre jogosult tranzakcióinak listájához kattintson a **Tranzakciók** gombra az **Előlegre jogosultak** oldalon. Az összes előlegre jogosult tranzakcióinak megtekintéséhez vagy előlegre jogosultak tranzakcióin alapuló konkrét lekérdezés létrehozásához kattintson a **Kötelezettségek** &gt; **Lekérdezések és jelentések** &gt; **Előlegre jogosultakkal kapcsolatos lekérdezések és jelentések** &gt; Tranzakciók elemre. Kattintson a **Bizonylat** elemre a **Bizonylattranzakciók** oldal megnyitásához.
### <a name="advance-holder-balance-inquiry"></a>Előlegjogosult egyenlegének lekérdezése

Előlegre jogosult egyenlegének megtekintéséhez használja az **Előlegre jogosultak** oldalt. Az összes előlegre jogosult egyenlegének megtekintéséhez vagy előlegre jogosultak számláin alapuló konkrét lekérdezés létrehozásához kattintson a **Kötelezettségek** &gt; **Lekérdezések és jelentések** &gt; **Előlegre jogosultakkal kapcsolatos lekérdezések és jelentések** &gt; **Egyenleg** elemre.
### <a name="advance-holder-balance-report"></a>Előlegre jogosult egyenlege – jelentés

Előlegre jogosultak egyenlegével kapcsolatos információk alapján készített jelentés megtekintéséhez vagy nyomtatásához kattintson a **Kötelezettségek** &gt; **Lekérdezések és jelentések** &gt; **Előlegre jogosultakkal kapcsolatos lekérdezések és jelentések** &gt; **Előlegre jogosult egyenlege – jelentés** elemre.
### <a name="advance-holder-transactions-report"></a>Előlegre jogosult tranzakciói – jelentés

Előlegre jogosultak tranzakcióival kapcsolatos jelentés megtekintéséhez vagy nyomtatásához kattintson a **Kötelezettségek** &gt; **Lekérdezések és jelentések** &gt; **Előlegre jogosultakkal kapcsolatos lekérdezések és jelentések** &gt; **Előlegre jogosult tranzakciói – jelentés** elemre.



<a name="see-also"></a>Lásd még
--------

[Előlegre jogosult tranzakciói](emea-advance-holders-transactions.md)




