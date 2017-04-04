---
title: "Előlegre jogosultak"
description: "Tudnivalók az előleg jogosultja funkciói Microsoft Dynamics 365 műveletekhez."
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
translationtype: Human Translation
ms.sourcegitcommit: f707d45290682e79ee439ba0d504852429defa90
ms.openlocfilehash: 8cfe98e3859778e4fdc61f22b437cb1b4d004549
ms.lasthandoff: 03/31/2017


---

# <a name="advance-holders"></a>Előlegre jogosultak

Tudnivalók az előleg jogosultja funkciói Microsoft Dynamics 365 műveletekhez.

Egy *az előleg jogosultja* a vállalatnál, aki felelős a szervezet által biztosított költség összeget az alkalmazott. Csak a vállalat dolgozói előlegre jogosult lehet. Amikor megtörténik a beszerzési, előlegre jogosult jelenti a vállalat kapcsolatban végzett a kiadások. A vállalat abban az esetben téríti az alkalmazott számára a kiadás összege. A vállalat az egyes előlegre jogosult egyenlege szabályozza. A jogi személyek, Észtország, Lettország, Litvánia, Lengyelország, Cseh Köztársaság, Magyarország és Oroszország a felhasználók kísérő a vállalat alkalmazottai, akik a kiadás összege, a szervezet által biztosított elszámoltathatók legyenek a műveletek adott tranzakciók is tükrözik.

## <a name="set-up-an-advance-holder"></a>Előlegre jogosult beállítása
Előlegre jogosult beállításához a következő feladatokat sorrendben kell elvégezni.
1.  Előlegre jogosult csoportok létrehozása.
2.  Az alkalmazott könyvelési profil beállítása.
3.  Kifizetendő számla paramétereinek beállítása.
4.  Hozzon létre egy adott előleg jogosultja fizetési feltételei.
5.  Előlegre jogosult létrehozása.

### <a name="advance-holder-groups"></a>Előlegre jogosult csoportok

Használja a **előlegre jogosult csoportok** oldalra előlegre jogosult csoport létrehozása. Megadhatja a nevet, a leírást és az Ellenszámla előlegre jogosult csoport.
### <a name="employee-posting-profile"></a>Alkalmazott feladási sablonja

Használja a **alkalmazott feladási profilok** profil létrehozása az előlegre jogosult tranzakcióinak lapra. Az alkalmazott feladási profil a következő adatokat is megadhat.
|Mező |Leírás|
|------|-----------|
|Feladási profil|A könyvelési profil azonosító kód megadása az előlegre jogosult.|
|Leírás|A feladási profil rövid leírásának megadása.|
|Érvényes|A feladási profil beállítása a csoportosítási szint a következő lehetőségek közül választhat: 
**Táblázat** – ezt a beállítást használják a feladási profilnak egy előlegjogosult beállítása. Az előleg jogosultjának kódja mezőjében meg kell adnia.
**Csoport** – ezt a beállítást használják a feladási profil beállítása előlegre jogosultak egy csoportja számára. A kódot a hivatkozás mezőben meg kell adnia.
**Minden** – ezt a beállítást használják a feladási profil beállítása minden előlegre jogosultak. |}] | Hivatkozás |}] Az előleg jogosultjának kódja válassza, ha a tábla beállítás van megadva, az érvényes mezőben, vagy jelölje ki a előlegre jogosult csoport, ha a csoport van kiválasztva a mező érvényes. |}] | Az összegző számla |}] A könyvelési tranzakciók összegző számlája. |}]



### <a name="account-payable-parameters"></a>Fiók kötelezettségek paraméterei

Előlegre jogosult tranzakcióinak megfelelően be kell állítania a következő a **figyelembe a Kötelezettségek paraméterei** a lap a **előlegre jogosultak** szakasz.
|                                                |                   |
|------------------------------------------------|-------------------|
|  **Field**                                     | **Description**                                                                                                                                                                  |
| **Posting profile**                            | Válassza ki az alapértelmezett profil előlegre jogosultak tranzakciói befejezéséhez.                                                                                                         |
| **Advance holder sorting**                     | Ha kijelölve, előlegre jogosultak a lista elején jelennek meg a **előlegre jogosultak** lap.                                                                     |
| **Issue when balance is open**                 | Ha kijelölve, a probléma, akik nyitott pozitív egyenlege előlegre jogosult a készpénzelőleg lehetővé kell tenni.                                                                      |
| **Egyenleg kiegyenlítése készpénz mezőcsoport: név** | A készpénzfizetési bizonylat napló kódjának kiválasztása. Ez a napló kód létrehozásához használatos bevételezési pénztárbizonylatok és a készpénz-kifizetési bizonylatok előlegre jogosult egyenlegek készpénz keresztül bezárásakor. |
| **Cash**                                       | Válassza ki a készpénzszámla meghatározására a bizonylatokhoz használt záró egyenlegének az előlegre jogosult.                                                                 |
| **Via bankcsoport mező záró egyenleg: név** | Zárja be a Bank egyenlegek tranzakciók naplóba kódjának kiválasztása.                                                                                                   |
| **Account type**                               | Válassza ki a bank Bank előlegre jogosult az egyenlegek lezárása.                                                                                                        |
| **Main account**                               | Zárja be az egyenlegek a Bank előlegre jogosult a bankszámla kódjának kiválasztása                                                                                           |

### <a name="terms-of-payment-for-advance-holder"></a>Előlegre jogosult fizetési feltételei

Helyes regisztrálása és előlegre jogosult – beszerzési rendelés feladása, használjon egy a beállított fizetési feltételek a **az előlegre jogosulttól** beállítás **igaz**.
### <a name="create-an-advance-holder-creation"></a>Hozzon létre egy előleg jogosultja létrehozása

Előlegre jogosult létrehozása előtt be kell állítania a munkavállalók. További tudnivalókért lásd: [a munkavállalók tájékoztatása (feladat guide) adja meg.](http://ax.help.dynamics.com/en/wiki/enter-worker-information/) Használja a **előlegre jogosultak** mint előlegre jogosult a munkavállaló beállítása lapon. Válassza ki a munkavállaló előlegre jogosult használni, kattintson a **szerkesztése**, majd állítsa be a **előlegre jogosult** be **igaz**. A következő mezőket is ki kell töltenie.
|                |                                                                                             |
|----------------|---------------------------------------------------------------------------------------------|
| **Field**      | **Description**                                                                             |
| **Group**      | Előlegre jogosult csoport kiválasztása.                                                             |
| **Series**     | Adja meg a dokumentumot, amelynek segítségével azonosítani az előlegre jogosult sorozata. |
| **Number**     | Adja meg, amelynek segítségével azonosítani az előleg jogosultja a bizonylat számát. |
| **Issue date** | Válassza ki vagy írja be a dokumentum kibocsátási dátuma.                                                    |
| **Issued by**  | Adja meg a személy, aki az okmányt kiállító hatóság vagy a részleteket.                       |

## <a name="advance-holder-inquiries-and-reports"></a>Előlegre jogosult lekérdezésekben és jelentésekben
### <a name="advance-holder-transactions-inquiry"></a>Előleg jogosultja tranzakciók lekérdezése

Előlegre jogosult tranzakcióinak listáját, kattintson a **tranzakciók** gombja a **előlegre jogosultak** oldalon. Előlegre jogosultak, vagy egy különleges előlegre jogosultak tranzakciókon alapuló vizsgálatot létrehozásához kattintson az összes tranzakciók megtekintéséhez **kötelezettségek**&gt;**lekérdezések és jelentések**&gt;**előlegre jogosultak lekérdezések és jelentések**&gt; tranzakciók. Kattintson a **bizonylat** megnyitni a **Bizonylattranzakciók** oldalon.
### <a name="advance-holder-balance-inquiry"></a>Előleg jogosultja egyenleg lekérdezése

Megtekintéséhez használja az előlegre jogosult egyenlege a **előlegre jogosultak** oldalon. Előlegre jogosultak vagy előlegre jogosultak számlák alapján egy adott lekérdezés létrehozásához kattintson az összes egyenleg megtekintéséhez **kötelezettségek**&gt;**lekérdezések és jelentések**&gt;**előlegre jogosultak lekérdezések és jelentések**&gt;**mérleg.**
### <a name="advance-holder-balance-report"></a>Előlegre jogosult egyenlege – jelentés

Megtekintése és előlegre jogosult egyenlege kapcsolatos információk alapján jelentést nyomtasson, kattintson a **kötelezettségek**&gt;**lekérdezések és jelentések**&gt;**előlegre jogosultak lekérdezések és jelentések**&gt;**jogosultjának egyenlege előlegjelentés**.
### <a name="advance-holder-transactions-report"></a>Előlegre jogosult tranzakciói – jelentés

Megtekintése és előlegre jogosultak tranzakciókon alapuló jelentést nyomtasson, kattintson a **kötelezettségek**&gt;**lekérdezések és jelentések**&gt;**előlegre jogosultak lekérdezések és jelentések**&gt;**előleg jogosultja tranzakciókról szóló jelentés**.



<a name="see-also"></a>Lásd még
--------

[Advance holder transactions](emea-advance-holders-transactions.md)


