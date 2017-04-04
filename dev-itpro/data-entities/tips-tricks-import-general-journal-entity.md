---
title: "Gyakorlati tanácsok a bizonylatok segítségével az általános napló entitás importálása"
description: "Ez a témakör tippek az adatok importálása a főkönyvi napló segítségével az általános napló entitás."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 94363
ms.assetid: 0b8149b5-32c5-4518-9ebd-09c9fd7f4cfc
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 4d6cf88788dcc5e982e509137aa444a020137a5e
ms.openlocfilehash: 81a52acd1d9baa12fcfe9d848441901894fa5682
ms.lasthandoff: 03/31/2017


---

# <a name="best-practices-for-importing-vouchers-using-the-general-journal-entity"></a>Gyakorlati tanácsok a bizonylatok segítségével az általános napló entitás importálása

Ez a témakör tippek az adatok importálása a főkönyvi napló segítségével az általános napló entitás.  

A főkönyvi napló entitás segítségével importálhatja a bizonylatok, amelyek egy számlaként vagy ellenszámlaként számlatípus, **főkönyvi, vevői, szállítói vagy banki**. A bizonylat mindkét sorba kell beírni **fiók** mező és a **ellenszámla** vagy egy többsoros mező bizonylat, ha csak a **fiók** mezővel (és a **ellenszámla** minden sorban üresen marad). A főkönyvi napló entitás nem támogatja minden számlatípust. Ehelyett más entitások léteznek olyan esetekre, amikor különböző kombinációjú számlatípusokra van szükség. Például a projekttranzakció importálásához használja a projekt költség napló entitás. Egyes entitások támogatására szolgálnak egyes konkrét eseteket, ami azt jelenti, hogy további mezőket lehet másikat entitások szervek ilyen esetekben azonban nem használható.

## <a name="setup"></a>Beállítás
Segítségével az általános napló entitás importálása előtt ellenőrizze a következő telepítési:

-   **Számsorozat beállítása a kijelölt naplószámra vonatkozóan** - alapértelmezés szerint az általános napló a napló kötegelt szám által használt entitás segítségével határozza meg a főkönyvi paraméterek számsorozat importálásakor. Ha a napló kötegszámának számsorozatát **Manuálisra** állítja, akkor nem lesz alapértelmezett szám alkalmazva. Ez a beállítás nincs támogatva.
-   **Pénzügyi dimenzió konfigurációs** -minden szervezetnek kell meghatároznia a pénzügyi dimenziók sorrendje entitások használata, ha tranzakciókat szeretne importálni. A sorrend van definiálva a **főkönyvi integráció dimensions** formátum, **főkönyvi**&gt;**számlatükör**&gt;**dimenziók**&gt;**pénzügyi dimenzió konfigurációja alkalmazásokat integráló**&gt;**adatok entitások kiválasztása**. A főkönyvi számla importált szegmenseinek ugyan abban a sorrendben kell maradniuk. Ellenkező esetben hiba fog fellépni az importálás során.

## <a name="general-journal-entity-setup"></a>Általános napló entitás beállítása
Adatok kezelése két beállítása befolyásolja, hogyan kell alkalmazni az alapértelmezett napló száma vagy bizonylat száma:

-   **Set-alapú feldolgozás** (az adatokat az entitás)
-   **Automatikusan generált** (a mező-hozzárendelést)

A következő szakaszok bemutatják ezeknek a beállításoknak a hatásait, valamint meg is magyarázza, hogy hogyan lesznek generálva a naplók kötegszámai, valamint a bizonylatszámok.

### <a name="journal-batch-number"></a>Napló kötegszáma

-   A **Halmazalapú feldolgozás** beállítás az Általános napló entitásnál nincs semmilyen hatással a napló kötegszámainak a generálására.
-   Ha a **Napló kötegszáma** mező **Automatikusan generált** értékű, egy új napló kötegszám lesz létrehozva minden importált sorhoz. Ez a működés nem ajánlott. Az **Automatikusan generált** beállítás a projekt importálásánál, a **Leképzés megtekintése** menüben, a **Részletek leképezése** lapon található.
-   Ha a **Napló kötegszáma** mező nem **Automatikusan generált** értékű, a napló kötegszáma az alábbiak szerint lesz létrehozva:
    -   Ha az importált fájlban definiált naplószámra megegyezik egy létező, feladatlan napi napló Microsoft Dynamics 365 műveletekhez, minden egyező naplószámra sorokat a meglévő napló importálják. A sorok soha nem kerülnek importálásra a feladott napló kötegszámába. Ehelyett új szám jön létre.
    -   Ha az importált fájlban definiált naplószámra nem egyezik meg egy létező, feladatlan napi napló Dynamics 365 műveletekhez, azonos naplószámra rendelkező összes sor alatt egy új naplóba vannak csoportosítva. Például minden sor, aminek a napló kötegszáma 1, importálva lesz egy új naplóban, majd minden sor, aminek a napló kötegszáma 2, importálva lesz egy másik új naplóba. A napló kötegszáma az új, a Főkönyv paramétereknél megadott számsorozat segítségével lett létrehozva.

### <a name="voucher-number"></a>Bizonylatszám

-   Amikor a **Halmazalapú feldolgozás** beállítást használja az Általános napló entitásnál, a bizonylatszámot meg kell adnia az importált fájlban. Az Általános napló minden tranzakciójához hozzá lesz rendelve az a bizonylatszám, ami az importált fájlban lett megadva, még akkor is, ha a számla nincs kiegyenlítve. Ha set-alapú feldolgozás használni kívánt, de is szeretné használni a megadott számsorozat bizonylatszámok Dynamics 365 műveletekhez, kapott egy gyorsjavítás kiadásának február 2016. A gyorsjavítás száma 3170316, valamint letölthető a Lifestyle Services (LCS) rendszerből. További információkért lásd: [Gyorsjavítások letöltése a Lifecycle Services rendszerből](..\migration-upgrade\download-hotfix-lcs.md).
    -   Ahhoz, hogy ezt a funkciót, a behozatal Dynamics 365 műveletek esetében használt naplónév megadása **feladáskor foglalási szám** a **Igen**.
    -   A bizonylatszámot továbbra is meg kell határozni az importált fájlban. Ez a szám azonban átmeneti, és felülírja a Dynamics 365 műveletek bizonylat számát a napló feladásakor. Meg kell győződnie arról, hogy a napló sorai megfelelően vannak csoportosítva az ideiglenes bizonylatszám alapján. Például a könyvelés során három sor találhatók, amelyek egy ideiglenes bizonylatszám, 1. A következő szám a számsorozat felülírja az összes három sor ideiglenes bizonylatszám. Ha ez a 3 sor nem kiegyenlített tétel, a bizonylat nem lesz elküldve. Ezután, ha olyan sor lesz felfedezve, aminek az ideiglenes bizonylatszáma 2, akkor ez a szám felül lesz írva a soron következő számmal, és így tovább.

<!-- -->

-   Ha nem használja a **készlet alapú feldolgozás** állítja, meg nem kell adnia a bizonylatszámot, az importált fájlban. A bizonylatszámok importálás során lesznek létrehozva, a napló nevének beállítása alapján (**Csak egy bizonylat**, **Egyenleggel kapcsolatos**, és így tovább). Például, ha a napló nevének meghatározása **Egyenleggel kapcsolatos**, akkor az első sor egy új bizonylatszámot kap. A rendszer ezután megvizsgálja a sort, hogy a tartozás egyenlő-e a jóváírásokkal. Ha létezik ellenszámla a sorhoz, a következő importált sor úgy bizonylatszámot kap. Ha nem létezik ellenszámla, a rendszer megvizsgálja minden újonnan importált sornál, hogy a tartozás egyenlő-e a jóváírásokkal.
-   Ha a **Bizonylatszám** mező értéke **Automatikusan generált**, az importálás nem fog sikerülni. Az **Automatikusan generált** beállítás a **Bizonylatszám** mezőhöz nem támogatott.

Alapértelmezés szerint az Általános napló entitás halmazalapú feldolgozást használ. Miután értékelte az üzleti követelményeket a szervezete számára, megváltoztathatja a **Halmazalapú feldolgozás** beállítást az **Adatentitások** lehetőségre kattintva az **Adatok kezelése** munkaterületen. A halmazalapú feldolgozás a importálási folyamat sebességét hivatott növelni. Ha nem használja a halmazalapú feldolgozást, az Általános napló entitás importálása lassabb lesz.


