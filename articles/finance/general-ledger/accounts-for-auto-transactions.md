---
title: Számlák automatikus tranzakciókhoz
description: Ez a témakör bemutatja, Microsoft Dynamics hogy hogyan használhatók az automatikus tranzakciók számlái a 365-ös feladás során, és példákkal szolgál az automatikus tranzakciók kulcsszámláira.
author: rachel-profitt
ms.date: 12/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerSystemAccounts
audience: Application User
ms.reviewer: twheeloc
ms.custom: ''
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2022-01-03
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 275c74d673d1ba2468e23c5fa443c9272d13a184
ms.sourcegitcommit: 5d1772bdeb21a9bec6dc49e64550aaf34127a4e2
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/10/2022
ms.locfileid: "8735260"
---
# <a name="accounts-for-automatic-transactions"></a>Számlák automatikus tranzakciókhoz

Az **automatikus tranzakciók számlái** lap (**&gt;&gt;** Főkönyvi feladás beállítása számlák automatikus tranzakciókhoz) lap a rendszer minden egyes feladási típusához használt alapértelmezett fő számla meghatározására használható. Bár a legtöbb feladási típus konfigurálható egy modulspecifikus vagy funkcióspecifikus lapon, **néhány feladási típus csak az automatikus tranzakciók számlái oldalon konfigurálható**.

Például megadhatja **a** **·** **vevői** egyenleg feladására használt fő számlát, amely a Vevői feladási profil lapon az Összegzés mezőben található, és mindegyik vevői profilhoz más-más fő számlát használhat. Így részletesebben szabályozhatja a feladásokat. A hibaszámlát azonban csak **az automatikus tranzakciók számlája lapon adhatja** meg.

Amikor új jogi személyben nyitja **meg** az automatikus tranzakciókhoz a Számlák automatikus tranzakcióhoz lapot, a számlák listája üres lesz. Az oldalon konfigurálni **kívánt leggyakoribb feladási típusokat az Alapértelmezett típusok létrehozása gomb használatával lehet** hozzáadni. Ezután minden sorhoz kiválaszthatja a **fő számlát a Fő számla mezőben**. **Ha** egy feladási típusnál üresen hagyja a Fő számla mezőt, és nem konfigurált fő számlát egy modulspecifikus vagy funkcióspecifikus lapon, akkor egy hibaüzenet jelenik meg a feladási típust használó tranzakció feladása során. Az üzenet általában a következő: "Nem található a \[\] feladási típus számlája".

## <a name="default-posting-types"></a>Alapértelmezett feladási típusok

Az alábbi táblázat példákat mutat be **az alapértelmezett feladási típusokra, amelyek akkor hozhatók létre, ha az Alapértelmezett típusok létrehozása** az Automatikus **tranzakciók** számlái lapon be van jelölve. Fő mintaszámlákat és leírásokat mutat. A "Tartozik/Követel" A <a0/<a0/<a2/1>oszlop jelzi, hogy a tranzakció általában tartozik vagy követel tételeket ad fel. Bizonyos esetekben a tranzakció tartozást vagy jóváírást is feladhat. Az "Elszámolószámla" oszlop jelzi, hogy a feladás elszámolószámla-e. Ha a feladás elszámolószámla típusú, a számlára feladott összeg egy későbbi tranzakció feladása esetén automatikusan sztornírozásra kerül.

| Feladás típusa | Példa a fő számlára | Példa a fő számlanévre | Számla típusa | Tartozik/követel? | Elszámolási számla | Leírás |
|--------------|----------------------|---------------------------|--------------|---------------|------------------|-------------|
| Fillérkülönbözet a jelentés pénznemében | 618160 | Vegyes költség | Költség | Mindkettő | Nem | Ezt a feladási típust használja a rendszer, ha fillérkülönbség lép fel, amikor egy idegen pénznemben történő tranzakcióösszeget a jelentési pénznemre átváltanak. |
| Fillérkülönbözet a könyvelési pénznemben | 618160 | Vegyes költség | Költség | Mindkettő | Nem | Ezt a feladási típust használja a rendszer, ha fillérkülönbség lép fel, amikor egy idegen pénznemben könyvelt tranzakció összegét a könyvelési pénznemre fordítják. |
| Hibaszámla | 999999 | Hibaszámla | Költség | Mindkettő | Nem | Ezt a feladási típust használja a rendszer, ha hiba történik a rendszerben. A számlát minden időszakban ellenőrizni kell, és az esetleges hibákat meg kell oldani. |
| Év végi eredmény | 300160 | Visszatartott eredmény | Saját tőke | Mindkettő | Nem | Ez a feladási **típus** akkor használatos, amikor az év végi zárási folyamat futtatásakor az eredmény típusú számlák egyenlegét áthelyezik az év végi eredményhez kiválasztott fő számlára. |
| Vevő készpénzfizetési engedménye | Nem alkalmazható | Nem alkalmazható | Nem alkalmazható | Nem alkalmazható | Nem | Nem használja a Számlák **automatikus** tranzakciókhoz lapon megadott feladási típust. A Kinnlevőségek között a készpénzfizetési engedmények konfigurálásakor fő számlát kell megadni.|
| Szállító készpénzfizetési engedménye | Nem alkalmazható | Nem alkalmazható | Nem alkalmazható | Nem alkalmazható | Nem | Nem használja a Számlák **automatikus** tranzakciókhoz lapon megadott feladási típust. A Kötelezettségek között beállítja a készpénzfizetési engedményeket, és meg kell adni egy fő számlát. |

## <a name="additional-posting-types"></a>További feladási típusok

Az alábbi táblázat példákat mutat be a további feladási típusokra, ezeket konfigurálni kell, ha a kapcsolódó funkciók használatát tervezi. Ilyen feladási típusok esetén egy másik modulban nem érhető el feladásiprofil-konfiguráció. A "Tartozik/Követel" A <a0/<a0/<a2/1>oszlop jelzi, hogy a tranzakció általában tartozik vagy követel tételeket ad fel. Bizonyos esetekben a tranzakció tartozást vagy jóváírást is feladhat. Az "Elszámolószámla" oszlop jelzi, hogy a feladás elszámolószámla-e. Ha a feladás elszámolószámla típusú, a számlára feladott összeg egy későbbi tranzakció feladása esetén automatikusan sztornírozásra kerül.

| Feladás típusa | Példa a fő számlára | Példa a fő számlanévre | Számla típusa | Tartozik/követel? | Elszámolási számla | Leírás |
|--------------|----------------------|---------------------------|--------------|---------------|------------------|-------------|
| Egyenlegszámla a konszolidációs különbözethez | 801200 | Nyereség és veszteség - átértékelés | Költség | Mindkettő | Nem | Ezt a feladási típust devizaátértékelést magábanó konszolidáció végrehajtásakor használja a rendszer, és filléres különbözetek fordulhatnak elő az átértékelés során. |
| Eredménykimutatás a konszolidációs különbségekhez | 801200 | Nyereség és veszteség - átértékelés | Költség | Mindkettő | Nem | Ezt a feladási típust devizaátértékelést magábanó konszolidáció végrehajtásakor használja a rendszer, és filléres különbözetek fordulhatnak elő az átértékelés során. |
| Egységközi – tartozás | 133500 | Egységközi kinnlevőségek | Eszközök | Terhelés | Nem | Ezt a feladási típust használja a rendszer, amikor a **Főkönyv** lapon egy kiegyenlítő dimenziót választ ki, és a dimenzió nem egyenlege egy feladott tranzakcióban. |
| Egységközi - jóváírás | 233500 | Egységközi kötelezettség | Kötelezettség | Jóváírás | Nem | Ezt a feladási típust használja a rendszer, amikor a **Főkönyv** lapon egy kiegyenlítő dimenziót választ ki, és a dimenzió nem egyenlege egy feladott tranzakcióban. |
