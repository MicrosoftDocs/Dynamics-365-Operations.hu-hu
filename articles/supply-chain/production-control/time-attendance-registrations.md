---
title: Munkaidő és jelenlét rögzítésének áttekintése
description: A munkaidő-nyilvántartási dolgozók különböző típusú időregisztrációkat adhatnak meg, például érkezéskori blokkolás, távozáskori blokkolás, közvetett tevékenységeket regisztrálhatnak és távolléteket regisztrálhatnak. Ez a témakör regisztrációkat ír le, azok számítását, jóváhagyását, valamint a munkafolyamat használatát annak érdekében, hogy szerkezetet és automatikus jóváhagyást adjon az időnyilvántartások jóváhagyásának folyamatához.
author: ShylaThompson
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmWorker, JmgCalcApprovePickDialog, JmgGroupApprove, JmgGroupCalc, JmgGroupSigningTable, JmgRegistration, JmgTimeCalcParmeters, WorkflowTableListPageRnr, JmgRegistrationSetup, JmgStampTrans, JmgStampJournalTrans
audience: Application User
ms.reviewer: kamaybac
ms.custom: 53351
ms.assetid: 885b0cdf-53d7-4cb4-92fe-da1b9e32b39f
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 66c02a2d15b4be4c1c2849f9547da10717fd10b7
ms.sourcegitcommit: 0cc89dd42c1924ca0ec735c6566bc56b39cc5f7d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/26/2021
ms.locfileid: "6102698"
---
# <a name="time-and-attendance-registration-overview"></a>Munkaidő és jelenlét rögzítésének áttekintése

[!include [banner](../includes/banner.md)]

A munkaidő-nyilvántartási dolgozók különböző típusú időregisztrációkat adhatnak meg, például érkezéskori blokkolás, távozáskori blokkolás, közvetett tevékenységeket regisztrálhatnak és távolléteket regisztrálhatnak. Ez a témakör regisztrációkat ír le, azok számítását, jóváhagyását, valamint a munkafolyamat használatát annak érdekében, hogy szerkezetet és automatikus jóváhagyást adjon az időnyilvántartások jóváhagyásának folyamatához.

## <a name="registrations"></a>Regisztrációk

A Munkaidő és jelenlét lehetőséget használó vállalatoknál a dolgozóknak regisztrálni kell a munkában töltött időt, illetve a jelenlétet. Egyes vállalatoknál a dolgozóknak blokkolniuk kell megérkezéskor és távozáskor. Más cégeknél a dolgozóknak elképzelhetően a ténylegesen az általuk elvégzett feladatokra fordított időt kell regisztrálniuk, beleértve a szüneteket is. A Munkaidő és jelenlét funkció lehetséges felhasználói a következők:

- Olyan dolgozók, akiknek például napi, heti vagy kétheti rendszerességgel regisztrálniuk kell a munkaidejüket és jelenlétüket.
- Olyan munkafelügyelők, vezetők és bérszámfejtési tisztviselők, akik kiszámítják, jóváhagyják vagy további feldolgozásra továbbküldik a dolgozók által regisztrált adatokat.

| **Megjegyzés**                                                                                                                                                                                                                                                    |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Ha a Munkaidő és jelenlét funkciót a Gyártásvégrehajtással együtt futtatja, úgy rögzítésre, illetve mindkét modul bérszámfejtési számításaihoz felhasználásra kerül minden, a projektek, projekttevékenységek, közvetett tevékenységek, távolléti kódok, túlóra, illetve rugalmas munkaidő kapcsán regisztrált adat. |

## <a name="time-registrations-workers"></a> Munkaidő-nyilvántartási dolgozók

A munkaidő és távollét regisztrálásának lehetővé tétele érdekében az érintett dolgozókat az adott vállalat munkaidő-nyilvántartási dolgozóiként kell beállítania.

A beállítást követően a dolgozók részére többféle regisztráció is engedélyezett.

- Blokkolás munkába érkezéskor, illetve távozáskor.
- Idő- és cikkfelhasználás termelési feladatok során.
- Az üzemben egy adott gép használati ideje, amennyiben a gép erőforrásként van megjelölve.

| **Megjegyzés**                                                                                                                                                                                                                      |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| A dolgozó automatikusan hozzárendelhető az üzem egy adott gépe kapcsán végzett időpont-regisztrációkhoz, amennyiben a dolgozó azt állítja be a termelési feladat megkezdésekor, hogy segédként dolgozik az adott gépen. |

- Időpont regisztráció projektek és projekttevékenységek kapcsán.
- Projektdíjak és cikkfelhasználás regisztrálása a megfelelő projektdíjnaplók és projektcikknaplók felhasználásával.
- Tervezett távollét.
- Késedelmes munkakezdéshez, illetve a tervezettnél korábbi távozáshoz kapcsolódó távollét.
- Manuálisan regisztrált, vagy a rendszer által automatikusan kiszámított munkaszünetek.
- Olyan, a dolgozó által esetlegesen végzett közvetett tevékenységek, amelyek nem termelési tevékenységek. Ilyen tevékenység lehet például a megbeszélés vagy a munkaterület megtisztítására.
- Túlóra, amely a tervezetten felüli órák, rugalmas munkaidő vagy túlóra formájában regisztrálható.

## <a name="adding-clock-out-registrations"></a>Távozáskori blokkolások hozzáadása

Amennyiben a dolgozó távozáskor elfelejt blokkolni a munkanap végén, a hiányzó regisztráció egy kötegelt feladat futtatásával adható hozzá. A rendszer a dolgozó hozzárendelt profilja alapján összehasonlítása a érkezéskori és távozáskori blokkolás időt, és automatikusan beilleszti a hiányzó távozáskori blokkolási regisztrációt, a profil záró időpontjának megfelelően. Az érkezéskori, illetve távozáskori regisztrációk megléte egyaránt elengedhetetlen fontosságú az időjegyzékek későbbi, a bérszámfejtéshez történő továbbítást megelőző kiszámításához és jóváhagyásához.

## <a name="calculating-registrations"></a>A regisztrációk kiszámítása

Amikor a munkaidő-nyilvántartási dolgozó hozzá van rendelve egy számítási csoporthoz, amely jellemzően egy adott csapathoz, műszakhoz vagy munkacsoporthoz kapcsolódik. Jellemzően a csapat vezetője vagy felügyelője ellenőrzi a dolgozók regisztrációit, így szintén ő felel az adott számítási csoportokra vonatkozó számítások napi rendszerességgel történő futtatásáért. A számítás részeként a csapat vezetője vagy felügyelője képes:

- Kijavítani a hibás regisztrációkat. Megváltoztatni például a kapcsolókódokat, illetve módosítani a termelési feladatokra vonatkozó visszajelzéseket.
- Hozzáadni a hiányzó regisztrációkat. Például távozáskori blokkolási regisztrációkat, illetve távolléti tranzakciókat hozni létre.
- Törölni a hibás regisztrációkat.

Mivel, a regisztrációk kiszámításához a regisztrált időnek meg kell egyeznie a dolgozó időprofiljával, Önnek felül kell írnia minden olyan dolgozó munkaidő profilját, aki az általában jellemzőtől eltérő munkaidő profil szerint dolgozik. Abban az esetben, ha a dolgozói profil nappali műszakot tartalmaz, és a dolgozó túlóradíj nélküli éjszakai műszakot vállalt, a csapat vezetőjének vagy felügyelőjének felül kell írnia az alapértelmezett dolgozói munkaidő profilt, annak érdekében, hogy a munkaidő kiszámítása a szokásos éjszakai bér, és ne a túlóradíj alapján történjen. A számítás akkor is hibát jelez, ha hiányzik valamilyen távolléti regisztráció. Ezt is pótolni szükséges a számítás végrehajtásához.

## <a name="approving-registrations"></a>A regisztrációk jóváhagyása

A számítási csoporthoz hasonlóan jóváhagyási csoportot is hozzá kell rendelnie minden munkaidő-nyilvántartási munkavállalóhoz. Az ilyen csoport jellemzően egy konkrét csapat, műszak vagy munkacsoport lesz. A helyesen, azaz a hiba nélkül végigfutó számítás eredményeképp kiszámított, időregisztrációkat jóvá kell hagynia, és csak ezt követően hozhatók létre a bérszámfejtő rendszerbe megküldésre kerülő fizetési tételek. Jellemzően a bérszámfejtő hagyja jóvá a regisztrációkat, a jóváhagyást megelőzően pedig az alábbi tevékenységeket tudja végrehajtani:

- Egyes dolgozókra vonatkozó fizetési megállapodások felülbírálása
- Prémiumok manuális hozzáadása.
- További információk megadása a távolléti regisztrációkkal kapcsolatban.

| **Megjegyzés**                                                                                                                                                                             |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Ha egyes dolgozók számára túlórát számol el, a túlórát fel lehet osztani a nap egyes feladatai között. Erre akkor van szükség, ha a feladat költségének kiszámítása a dolgozói fizetés alapján történik. |

## <a name="approving-registrations-using-workflow"></a> Regisztrációk jóváhagyása munkafolyamat segítségével

Be tud állítani olyan munkafolyamat-jóváhagyási folyamatot, ami automatikusan jóváhagyja az olyan regisztrációkat, amelyek megfelelnek a munkafolyamat-szabályoknak, és így csak az eltérések manuális kezelése szükséges. A munkafolyamat-jóváhagyás aktiválása esetén a csapatvezető vagy felügyelő küldi el a kiszámított regisztrációkat jóváhagyásra. A munkafolyamatra vonatkozó folyamat létrehozza a megfelelő jóváhagyásokat és feladatokat, majd azokat a munkafolyamat által azonosított megfelelő felhasználókhoz és szerepkörökhöz rendeli hozzá. A munkaidőre és jelenlétre két munkafolyamat-jóváhagyás vonatkozik.

| Munkafolyamat                                  | Cél                                                                                                   | Nyilvántartás típusa                                                                                                                                                                                                                                     |
|-------------------------------------------|-----------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Munkaidő és jelenléti napok száma összesen            | A munkafolyamat például a napi munkaórák várható száma alapján ellenőrzi a regisztrációkat. |                                                                                                                                                                                                                                                       |
| Munkaidő és jelenlét napló regisztráció. | A munkafolyamat ellenőrzi a regisztráció dátumának minden egyes regisztrációtípusát.                           | Munkaidő és jelenlét • Blokkolás érkezéskor • Blokkolás távozáskor • Távollét • Szünet • Kapcsolókód • Projekt • Projekttevékenység • Közvetett tevékenység - Termelési feladatok • Várakozás előtte • Beállítás • Folyamat • Átfedés • Szállítás • Várakozás utána • Támogatás kezdete • Támogatás befejezése |

## <a name="transferring-approved-registrations"></a>Jóváhagyott regisztrációk áthelyezése

A regisztrációk jóváhagyása után azokat át tudja helyezni az ismétlődő bérlistafeladatba. Az áthelyezett regisztráció olyan tevékenységhez vagy feladathoz kerül feladásra, mint például egy termelési rendelés vagy egy projekt. A rendszer minden egyes dolgozó kapcsán a regisztrációk alapján hozza létre a bérlista-tranzakciókat.  

## <a name="reversing-transferred-registrations"></a>Áthelyezett regisztrációk sztornírozása

A tranzakciók sztornírozása – azaz azok visszaállítása – addig lehetséges, amíg le nem futtatja a bérlista-időszak fizetések áthelyezését. Azaz, amíg a bérlistaadatokat át nem helyezi egy külső fájlba. Sztornírozás esetén valamennyi regisztráció visszavonásra kerül, és a meghatározott termelési rendelésekbe és projektekbe feladott valamennyi tranzakcióhoz ellentranzakció készül, így a program semlegesíti a tranzakciókat.

| **Megjegyzés**                                                 |
|----------------------------------------------------------|
| A külső fájl importálható egy bérszámfejtő rendszerbe . |

## <a name="registrations-in-electronic-timecards"></a>Regisztrációk elektronikus munkaidőlapon

Az olyan munkaköri feladatot, például valamilyen termelési feladatot végző dolgozók esetén, ahol nem szükséges az azonnali visszajelzés, előnyös lehet az elektronikus munkaidőlap használata. Az elektronikus munkaidőlap lehetővé teszi a regisztrációk rugalmas, az Ön üzletmenete szempontjából a legalkalmasabb időpontban bármikor, naponta vagy hetente, vagy a dolgozó, az irodába történő visszatérését követő rögzítését. Úgy tud elektronikus munkaidőlapot használni az ilyen dolgozók esetén, ha beállítja a Munkaidőlap használata lehetőséget az adott dolgozó részletes adatai között. Az elektronikus munkaidőlapok az alábbiak regisztrálását teszik lehetővé a dolgozó részére:

- Dátum
- Nyilvántartás típusa
- Feladathivatkozás, például projekt, közvetett tevékenység vagy termelési rendelés
- Feladat azonosítása
- Időfelhasználás
- Projektdíjak
- Projektcikkek

[!INCLUDE[footer-include](../../includes/footer-banner.md)]