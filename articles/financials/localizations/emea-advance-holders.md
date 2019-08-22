---
title: Előlegre jogosultak
description: Előlegre jogosult funkcióiról szóló tudnivalók a Microsoft Dynamics 365 for Finance and Operations rendszerben.
author: LizaGolub
manager: AnnBe
ms.date: 08/23/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: HcmWorkerAdvHolderTableListPage_RU
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 262574
ms.search.region: Czech Republic, Estonia, Hungary, Latvia, Lithuania, Poland, Russia
ms.author: v-elgolu
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 587af5644cfcbb648157b2e3b42b387729c99ca5
ms.sourcegitcommit: 16bfa0fd08feec1647829630401ce62ce2ffa1a4
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/02/2019
ms.locfileid: "1852149"
---
# <a name="advance-holders"></a>Előlegre jogosultak

[!include [banner](../includes/banner.md)]

Előlegre jogosult funkcióiról szóló tudnivalók a Microsoft Dynamics 365 for Finance and Operations rendszerben.

*Előlegre jogosultnak* egy vállalat azon alkalmazottját nevezzük, aki egy a szervezet által biztosított költségösszegért felel. Előlegre jogosult csak vállalati dolgozó lehet. Beszerzéskor az előlegre jogosult jelenti a vállalatnak a foganatosított kiadásokat. A vállalat a költség összegét megtéríti az alkalmazottnak. A vállalat minden előlegre jogosult egyenlegét vezeti. Az Észtország, Lettország, Litvánia, Lengyelország, Cseh Köztársaság, Magyarország és Oroszország területén működő jogi személyek felhasználói a szervezet által biztosított költségösszegért felelős alkalmazottak által végzett műveletekre vonatkozó konkrét tranzakciókat kezelhetnek.

## <a name="set-up-an-advance-holder"></a>Előlegre jogosult beállítása
Ez a szakasz végigvezeti az előlegre jogosult beállításán. A jelen részben az alábbi sorrendben hajtsa végre a feladatokat:

> [!div class="checklist"]
> * 1. Előlegre jogosult csoportok létrehozása
> * 2. Alkalmazott feladási sablonjának beállítása
> * 3. Kötelezettségek paramétereinek beállítása
> * 4. Konkrét fizetési feltételek létrehozása az előlegre jogosult számára
> * 5. Konkrét fizetési feltételek létrehozása az előlegre jogosult számára
> * 6. Előlegre jogosult létrehozása


### <a name="advance-holder-groups"></a>Előlegre jogosult csoportok

Használja az **Előlegre jogosult csoportok** oldalt az előlegre jogosult csoport létrehozásához. Megadhatja a nevet, a leírást és az ellenszámlát az előlegre jogosult csoporthoz.
### <a name="employee-posting-profile"></a>Alkalmazott feladási sablonja

Az előlegre jogosult tranzakcióihoz sablon létrehozásához használja az **Alkalmazott feladási sablonjai** oldalt. Az alkalmazott feladási sablonjához a következő adatokat adhatja meg.

|      Mező      |                                            Leírás                                            |
|-----------------|---------------------------------------------------------------------------------------------------|
| Feladási profil |               Adja meg a feladási sablon azonosító kódját az előlegre jogosulthoz.               |
|   Leírás   |                         Adja meg a feladói sablon rövid leírását.                         |
|    Érvényes    | A feladási sablon beállításához használt csoportosítási szinthez a következő lehetőségek közül választhat: |

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

### <a name="create-an-advance-holder"></a>Előlegre jogosult létrehozása

Előlegre jogosult létrehozása előtt beállított dolgozókkal kell rendelkeznie. További tudnivalókért lásd: [Dolgozó adatainak megadása (Feladat-útmutató).](../../fin-and-ops/hr/tasks/enter-worker-information.md) 

1. Válassza a **Kötelezettségek** \> **Előlegre jogosultak** \> **Előlegre jogosultak** elemet.

    > [!NOTE]
    > Nem lehet hozzáadni vagy törölni alkalmazottakat az **Előlegre jogosultak** lapon. Az alkalmazottakat előbb fel kell venni az **Emberi erőforrások** modulban. Az **Alkalmazott feladási sablonjai** lapon beállíthatja az előlegre jogosultak egyenlegeinek feladására szolgáló alkalmazotti feladási profilt.

2. Jelöljön ki egy alkalmazottat, és kattintson a **Szerkesztés** gombra.
3. Az **Általános** gyorslapon állítsa az **Előlegre jogosult** lehetőséget **Igen** értékre, mert ezzel jelezheti, hogy az alkalmazott előlegre jogosult.
4. A **Csoport** mezőben válassza ki azt az előlegre jogosult csoportot, amelyhez az alkalmazott tartozik.
5. Az **Azonosító bizonylat** pontnál adja meg, egy azonosító dokumentum részletes adatait.
    - **Sorozat** – Adja meg a dokumentumsorozatot, amely az előlegre jogosult azonosítására szolgál.
    - **Szám** – Adja meg a dokumentum számát, amely az előlegre jogosult azonosítására szolgál.
    - **Kiadás dátuma** – Válassza ki vagy írja be a dokumentum kibocsátási dátumát.
    - **Kiállította:** – Adja meg az okmányt kiállító hatóság vagy személy részleteit.
6. Kattintson a **Mentés** lehetőségre, vagy zárja be az oldalt.

> [!NOTE]
> Ha az **Előlegre jogosultak rendezése** beállítás értéke **Igen** a **Kötelezettségek paraméterei** oldalon, akkor az előlegre jogosultak a rács tetején jelennek meg az **Előlegre jogosultak** lapon.


## <a name="advance-holder-inquiries-and-reports"></a>Előlegre jogosulttal kapcsolatos lekérdezések és jelentések

### <a name="advance-holder-transactions-inquiry"></a>Előlegre jogosult tranzakcióinak lekérdezése

Előlegre jogosult tranzakcióinak listájához kattintson a **Tranzakciók** gombra az **Előlegre jogosultak** oldalon. Az összes előlegre jogosult tranzakcióinak megtekintéséhez vagy előlegre jogosultak tranzakcióin alapuló konkrét lekérdezés létrehozásához kattintson a **Kötelezettségek** &gt; **Lekérdezések és jelentések** &gt; **Előlegre jogosultakkal kapcsolatos lekérdezések és jelentések** &gt; Tranzakciók elemre. Kattintson a **Bizonylat** elemre a **Bizonylattranzakciók** oldal megnyitásához.
### <a name="advance-holder-balance-inquiry"></a>Előlegjogosult egyenlegének lekérdezése

Előlegre jogosult egyenlegének megtekintéséhez használja az **Előlegre jogosultak** oldalt. Az összes előlegre jogosult egyenlegének megtekintéséhez vagy előlegre jogosultak számláin alapuló konkrét lekérdezés létrehozásához kattintson a **Kötelezettségek** &gt; **Lekérdezések és jelentések** &gt; **Előlegre jogosultakkal kapcsolatos lekérdezések és jelentések** &gt; **Egyenleg** elemre.
### <a name="advance-holder-balance-report"></a>Előlegre jogosult egyenlege – jelentés

Előlegre jogosultak egyenlegével kapcsolatos információk alapján készített jelentés megtekintéséhez vagy nyomtatásához kattintson a **Kötelezettségek** &gt; **Lekérdezések és jelentések** &gt; **Előlegre jogosultakkal kapcsolatos lekérdezések és jelentések** &gt; **Előlegre jogosult egyenlege – jelentés** elemre.
### <a name="advance-holder-transactions-report"></a>Előlegre jogosult tranzakciói – jelentés

Előlegre jogosultak tranzakcióival kapcsolatos jelentés megtekintéséhez vagy nyomtatásához kattintson a **Kötelezettségek** &gt; **Lekérdezések és jelentések** &gt; **Előlegre jogosultakkal kapcsolatos lekérdezések és jelentések** &gt; **Előlegre jogosult tranzakciói – jelentés** elemre.

## <a name="advance-holder-transactions"></a>Előlegre jogosult tranzakciói

Információk az előlegre jogosult tranzakcióival kapcsolatban a Microsoft Dynamics 365 for Finance and Operations rendszerben.

Ezen előlegre jogosult dolgozók számára tranzakciókat előlegrejogosult-fiókok segítségével lehet feladni. A minden előlegre jogosultnál megadott dolgozói azonosító használható az előlegre jogosultak összes tranzakciójának nyomon követésére. Ez a szám számlaszámként hívható le az előlegre jogosultak tranzakcióihoz a **Főkönyvi naplók** és **Előlegre jogosult tranzakciói** oldalakon.

### <a name="create-and-post-a-purchase-order-with-advance-holder-details"></a>Beszerzési rendelés létrehozása és feladása az előlegre jogosultak részletes adataival
A beszerzési rendelésekkel kapcsolatos általános tudnivalókért lásd: [Beszerzési rendelések áttekintése](../../supply-chain/procurement/purchase-order-overview.md). Előlegjogosulti adatokat tartalmazó szállítói számla létrehozása és feladása esetén az előlegre jogosult egyenlegei alkalmazotti egyenlegszámlára kerülnek feladásra a szállítói egyenlegszámla helyett. Előlegre jogosult részleteinek beszerzési rendeléshez történő hozzáadásához tegye a következőket:

-   Az **Ár és engedmény** szakasz **Fizetési feltételek** mezőjében válassza ki a fizetési feltételeket. <!---For more information about **Terms of payment**, see [Define vendor payment terms](../accounts-payable/tasks/define-vendor-payment-terms.md).--> Olyan fizetési feltételt válasszon ki, amelynél a **Kezdő előlegre jogosult** lehetőség ki van választva a **Fizetési feltételek** oldalon. Előlegre jogosultak számára fizetési feltételek beállításával kapcsolatos további tudnivalókért lásd: [Előlegre jogosultak](emea-advance-holders.md).
-   Az **Ár és engedmény** gyorslap **Előlegre jogosult** mezőjében válassza ki az előlegre jogosultat a beszerzési rendeléshez.

A beszerzési rendelés feladási folyamata két szállítói tranzakciót hoz létre ellentétes összegekkel és egy előlegrejogosult-tranzakcióval. Előlegjogosulti adatok nélkül csak egy szállítói tranzakció jön létre.

### <a name="settle-advance-holder-balances-via-a-bank"></a>Előlegre jogosultak egyenlegeinek banki kiegyenlítése
Előlegre jogosultak egyenlegeinek banki kiegyenlítésekor az előlegre jogosultak egyenlegeit lezáró naplóbejegyzések a főkönyvben jönnek létre. A naplóhoz tartozó kódot és a bankot a **Kötelezettségek paraméterei** oldal **Előlegre jogosultak** szakaszában állíthatja be. További információ: [Előlegre jogosultak](emea-advance-holders.md). Előlegre jogosultak egyenlegének banki lezárásához nyissa meg a **Kötelezettségek** &gt; **Előlegre jogosultak** &gt; **Előlegre jogosultak** elemet. Kattintson az **Egyenleg** gombra a műveleti ablaktáblában, majd kattintson a **Zárás bankon keresztül** elemre. Adja meg az alábbi adatokat a **Zárás bankon keresztül** oldalon.

| Mező                    | Leírás |
|------------------------------|-------------------|
| **Fizetés dátuma**          | Adja meg a fizetés feladásának dátumát.|
| **Átutalandó összeg** | Adja meg a zárás közbeni egyenleget. Az **Egyenleg** képernyő **Összeg** mezőjében jelzett összeg alapértelmezés szerint látható. |
| **Automatikus**                | Jelölje be az **Automatikus** jelölőnégyzetet a **Kötelezettségek paraméterei** oldalon előre beállított napló létrehozásához és feladásához.|

### <a name="settle-advance-holder-balances-via-cash"></a>Előlegre jogosultak egyenlegeinek készpénzes kiegyenlítése
Előlegre jogosultak egyenlegeinek készpénzes kiegyenlítésekor az előlegre jogosultak egyenlegeit lezáró naplóbejegyzések egy bizonylatnaplóban jönnek létre. A naplóhoz tartozó kódot és a készpénzt a **Kötelezettségek paraméterei** oldal **Előlegre jogosultak** lapján állíthatja be. További információ: [Előlegre jogosultak](emea-advance-holders.md). Előlegre jogosultak egyenlegének készpénzes lezárásához nyissa meg a **Kötelezettségek** &gt; **Előlegre jogosultak** &gt; **Előlegre jogosultak** elemet. Kattintson az **Egyenleg** gombra a műveleti ablaktáblában, majd kattintson a **Zárás készpénzen keresztül** elemre. Adja meg az alábbi adatokat a **Zárás készpénzen keresztül** oldalon.

| Mező                    | Leírás
|------------------------------|-----------------|
| **Fizetés dátuma**          | Adja meg a fizetés feladásának dátumát.|
| **Átutalandó összeg** | Adja meg a zárás közbeni egyenleget. Az **Egyenleg** képernyő **Összeg** mezőjében jelzett összeg alapértelmezés szerint látható. |
| **Automatikus**                | Jelölje be az **Automatikus** jelölőnégyzetet a **Kötelezettségek paraméterei** oldalon előre beállított napló automatikus létrehozásához és feladásához.     |

A bizonylatnapló feldolgozása után, amennyiben az **Átutalandó összeg** mezőben lévő összeg negatív volt, az egyenlegek lezárásakor az előlegre jogosultakhoz kifizetési pénztárbizonylat jön létre. Amennyiben az **Átutalandó összeg** mezőben lévő összeg pozitív volt, bevételezési pénztárbizonylat jön létre.

## <a name="additional-resources"></a>További erőforrások

- [Előleg alkalmazotthoz (Kelet-Európa)](tasks/advance-payment-employee.md)
- [Előlegre jogosultak Oroszország esetén](rus-advance-holders.md)



