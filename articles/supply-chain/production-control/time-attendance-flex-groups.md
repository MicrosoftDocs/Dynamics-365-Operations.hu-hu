---
title: Rugalmasidő-csoportok
description: Ez a témakör azt mutatja be, hogyan használhatók a rugalmasidő-csoportok a munkaidő és jelenlétben.
author: johanhoffmann
manager: AnnBe
ms.date: 03/15/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: JmgFlexGroup
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 1705903
ms.assetid: 427e01b3-4968-4cff-9b85-1717530f72e4
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: aae00f3605a6598a34e58fad3e06e687476dd859
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2019
ms.locfileid: "361199"
---
# <a name="flex-groups"></a>Rugalmasidő-csoportok

[!include[banner](../includes/banner.md)]

A rugalmas munkaidő lehetővé teszik a vállalatok számára a túlórakifizetések minimalizálását azzal, hogy extra szabadidőt adnak a dolgozóknak azokban az időszakokban, amikor a terhelés alacsony. Ez a funkció jelentőséggel bír például az olyan szegmensekben, ahol a terhelés szezonálisan változik.

Rugalmasidő-csoportok segítségével a következő szabályokat és elveket állíthatja be a dolgozó rugalmas munkaidejére:

- Rugalmasidő-rendeletekre vonatkozó szabályok
- A dolgozó rugalmasidő-egyenlege számításának elve

## <a name="set-up-flexible-working-hours-in-flex-groups"></a>Rugalmas munkaidőre rugalmasidő-csoportok beállítása

- Válassza a **Munkaidő és jelenlét** \> **Beállítás** \> **Csoportok** \> **Rugalmasidő-csoportok** elemet rugalmas órák beállításához a rugalmasidő-csoportokhoz.

## <a name="associate-workers-with-flex-groups"></a>Dolgozók rugalmasidő-csoportokhoz társítása

- Válassza a **Munkaidő és jelenlét** \> **Beállítás** \> **Időnyilvántartás - dolgozók** elemet.

## <a name="rules-for-flex-regulations"></a>Rugalmasidő-rendeletekre vonatkozó szabályok

Szabályokon keresztül lehet rugalmas szabályozásokkal meghatározni a rugalmasidő-korlátokat, vagy rugalmasidő-fiókban engedélyezett dolgozói órák minimális és maximális számát. A rugalmasidő-korlát a rugalmasidő-csoporton állítható be. Ha a rugalmasidő-korlátot túllépik, módosítható a dolgozó rugalmasidő-egyenlege és fizetése.

A dolgozó engedélyezett rugalmasidő-minimumának túllépése esetén (vagyis ha a rugalmasidő-számla órák száma nem éri el a megadott minimumot) ezeket a metódusokat alkalmazhatja a dolgozó rugalmasidő-egyenlegének beállítására rugalmasidő-szabályokkal:

- A dolgozó rugalmasidő-számlája módosítható a megengedett minimumra, de nincs levonás a dolgozó fizetéséből az órák után, amelyekkel a rugalmasidő-számla nem éri el a megengedett minimális óraszámot.
- A dolgozó fizetéséből levonhatnak az órák után, amelyekkel a rugalmasidő-számla nem éri el a megengedett minimális óraszámot. Ez a levonás egy bizonyos kifizetési típusú fizetési tételek létrehozásával történik, amelyeknek pozitív vagy negatív fizetési egységeik vannak.

A dolgozó engedélyezett rugalmasidő-maximumának túllépése esetén ezeket a metódusokat alkalmazhatja a dolgozó rugalmasidő-egyenlegének beállítására rugalmasidő-szabályokkal

- A dolgozó rugalmasidő-számlája visszaállítható a megengedett maximumra, de nincs kompenzáció a dolgozó számára az órák után, amelyekkel a rugalmasidő-számla meghaladta a megengedett maximális óraszámot.
- A dolgozó megengedett maximum fölött ledolgozott óraszáma kifizetéssé konvertálható. Az átalakítás egy bizonyos kifizetési típusú fizetési tételek létrehozásával történik

A rugalmasidő-egyenleg a következő esetekben módosítható:

- Ha egy fizetési fájl, amely a bérlistaadatokon alapul, exportálva van a **Fizetés átutalása** feladattal. A bérlistaadatok akkor jönnek létre, amikor a dolgozó regisztrációját átviszik a **Jóváhagyás** oldalról.
- A **Rugalmasidő-egyenleg beállítása** feladat feldolgozásakor.

> [!NOTE]
> A rugalmasidő-szabályok alkalmazása nem történik meg a napi jóváhagyás és a dolgozói regisztrációk átvitele során a **Jóváhagyás** oldalon.

## <a name="principle-for-calculating-a-workers-flex-balance"></a>A dolgozó rugalmasidő-egyenlege számításának elve

A dolgozó rugalmasidő-egyenlege számításának elve a rugalmasidő-csoport szerint van beállítva. Válassza a **Munkaidő és jelenlét** \> **Beállítás** \> **Csoportok** \> **Rugalmasidő-csoportok** elemet. 

A következő két elv használható:

- **Idő** – A dolgozó rugalmas óráinak számítása csak az adott napon regisztrált dolgozói idő alapján. A dolgozó napi regisztrációinak kiszámítása során az adott napra vonatkozó rugalmasidő-többlet és rugalmasidő-hiány órák számát a dolgozó időprofiljában megadott rugalmasidő-többlet és rugalmasidő-hiány zónák alapján számítja ki a rendszer.
- **Kifizetés típusai** – A dolgozó rugalmas óráinak számítási alapját a rugalmasidő-többlet és rugalmasidő-hiány fizetéstípusok bére adja, amelyek a dolgozó fizetési megállapodásában vannak meghatározva. A fizetési megállapodás társítva van a munkaidő-nyilvántartásos dolgozóhoz. Előfordulhat, hogy használni kívánja a fizetéstípusokat a rugalmasidő-számlák kezelésére, ha például szeretné növelni a dolgozó rugalmasidő-számláját egy adott tényezővel egy vagy több rugalmasidő-zónában.

### <a name="scenario-1-adjusting-a-workers-pay-and-flex-account-because-the-allowed-flex-minimum-is-exceeded"></a>1. eset: A dolgozó kifizetésének rugalmasidő-számlájának beállítása, mivel túllépte az engedélyezett rugalmasidő-minimumot

A rugalmas munkaidőben dolgozó munkavállaló negatív rugalmasidő-számlával rendelkezik.

- **Rugalmasidő-számla:** -4

A dolgozó társítva van egy rugalmasidő-csoporthoz, amely a következő konfigurációval rendelkezik:

- **Rugalmas idő minimuma:** -0,5
- **Fizetéstípus minimuma:** 1302
- **Fizetéstípus tényezője:** -1,00

Ahogy a dolgozó rugalmasidő-számlája és az engedélyezett rugalmasidő-minimum különbsége jelzi, a dolgozó túllépte az engedélyezett rugalmasidő-minimumot 3,5 órával.

Amikor a bérszámfejtő átviszi a dolgozó fizetési adatait az **Átvitel kifizetésbe** vagy a **Rugalmasidő-korrekció** feladat futtatásával, a következő helyesbítések történnek:

- A dolgozó rugalmasidő-számlája 3,5 órával módosul. Ezért a rugalmasidő-egyenleg-4,0 órával válik kiigazítottá, hogy a dolgozó engedélyezett rugalmas idő minimuma, -0,5 óra legyen.
- 1302 fizetéstípusú fizetési tétel jön létre. A fizetési tételhez -3.5 óra fizetési egység tartozik, a program ezt levonja a dolgozó fizetéséből. Ebben az esetben a fizetési egység negatív szám, mert a 3.5 óra pozitív korrekciót megszorozzák a rugalmasidő-csoportban definiált-1.0 negatív kifizetési típus tényezővel. A fizetési tétel a kifizetési fájl a **Átvitel kifizetésbe** feladat által létrehozott része lesz.

### <a name="scenario-2-adjusting-a-workers-pay-and-flex-account-because-the-allowed-flex-maximum-is-exceeded"></a>2. eset: A dolgozó kifizetésének rugalmasidő-számlájának beállítása, mivel túllépte az engedélyezett rugalmasidő-maximumot

A rugalmas munkaidőben dolgozó munkavállaló pozitív rugalmasidő-számlával rendelkezik.

- **Rugalmasidő-számla:** 6

A dolgozó társítva van egy rugalmasidő-csoporthoz, amely a következő konfigurációval rendelkezik:

- **Rugalmas idő maximuma:** 2,0
- **Fizetéstípus minimuma:** 1302
- **Fizetéstípus tényezője:** -1,0

Ahogy a dolgozó rugalmasidő-számlája és az engedélyezett rugalmasidő-maximum különbsége jelzi, a dolgozó túllépte az engedélyezett rugalmasidő-maximumot 4,0 órával.

Amikor a bérszámfejtő átviszi a dolgozó fizetési adatait az **Átvitel kifizetésbe** vagy a **Rugalmasidő-korrekció** feladat futtatásával, a következő helyesbítések történnek:

- A dolgozó rugalmasidő-számlája -4,0 órával módosul. Ezért a rugalmasidő-egyenleg6,0 órával válik kiigazítottá, hogy a dolgozó engedélyezett rugalmas idő maximuma 2,0 óra legyen.
- 1302 fizetéstípusú fizetési tétel jön létre. A fizetési tételhez 4.0 óra fizetési egység tartozik, a program ezt hozzáadja a dolgozó fizetéséhez. Ebben az esetben a fizetési egység pozitív szám, mert a 4.0 óra negatív korrekciót megszorozzák a rugalmasidő-csoportban definiált-1.0 negatív kifizetési típus tényezővel. A fizetési tétel a kifizetési fájl a **Átvitel kifizetésbe** feladat által létrehozott része lesz.

### <a name="scenario-3-managing-a-workers-flex-balance-based-on-pay-types"></a>3. eset: Egy dolgozó rugalmasidő-egyenlegének kezelése fizetéstípusok alapján

Ahogy korábban már szó volt róla, a rugalmasidő-számlák kezelhetők a dolgozó időprofiljában megadott rugalmasidő-többlet és rugalmasidő-hiány zónákban regisztrált idő alapján, vagy a dolgozó fizetési megállapodásban meghatározott fizetéstípusok alapján. A fizetési típusok használata esetén a dolgozó rugalmasidő-számlája azokkal a fizetési tételekkel lesz kiigazítva, amelyek akkor jönnek létre, amikor a dolgozó regisztrációit elküldik a **Jóváhagyás** lapról. Előfordulhat, hogy használni kívánja a fizetéstípusokat a rugalmasidő-számlák kezelésére, ha például szeretné növelni a dolgozó rugalmasidő-számláját egy adott tényezővel egy vagy több rugalmasidő-zónában.

Az eset a következő rugalmasidő-profilt használja, amely egy munkanapot képvisel.

| Profil típusa  | Eleje    | Vége      |
|---------------|----------|----------|
| Rugalmasidő-többlet         | 12:00 DE | 08:00 DE |
| Érkezéskori blokkolás      | 08:00 DE | 08:00 DE |
| Rugalmasidő-hiány         | 08:00 DE | 09:00 DE |
| Szokásos idő | 09:00 DE | 11:30 DE |
| Fizetett szünet    | 11:30 DE | 12:00 DU |
| Rugalmasidő-hiány         | 12:00 DU | 04:00 DU |
| Távozáskori blokkolás     | 04:00 DU | 04:00 DU |
| Rugalmasidő-többlet         | 04:00 DU | 12:00 DE |

Ebben az esetben a dolgozó rugalmasidő-egyenlegét fizetéstípusok alapján szeretné kezelni. Ezért meg kell adni a **Fizetéstípusokon alapuló** lehetőség **Igen** beállítását a dolgozó rugalmasidő-csoportjára.

A rugalmas órák elszámolásához meg kell adnia egy új kifizetési típust is. Ebben az esetben a fizetéstípus neve **FlexCnt**.

| Kifizetés típusa | Leírás  |
|----------|--------------|
| FlexCnt  | Rugalmasidő-számláló |

Ezután kövesse az alábbi lépéseket, amelyekkel beállít egy kifizetési típust, és új típusú sorokat ad hozzá a fizetési profilhoz.

1. Válassza a **Munkaidő és jelenlét** \> **Beállítás** \> **Csoportok** \> **Rugalmasidő-csoportok** elemet, majd az **Új** lehetőséget.
2. A **Rugalmasidő-többlet** és a **Rugalmasidő-hiány** mezőben adja meg az új fizetéstípust: **FlexCnt**.
3. Válassza ki **Munkaidő és jelenlét** \> **Beállítás** \> **Kifizetési megállapodások** elemet, majd válassza ki a **Szerződéssorok** elemet.
4. A **hétfő** esetében, a **Rugalmasidő-többlet** profiltípusra, írja be a következő három sort.

    | Kifizetés típusa | Leírás  | Kezdő időpont | Záró időpont  | Minimum | Maximum | Szorzó |
    |----------|--------------|-----------|----------|---------|---------|--------|
    | FlexCnt  | Rugalmasidő-számláló | 12:00 DE  | 06:00 DU | 00:00   | 00:00   | 1.00   |
    | FlexCnt  | Rugalmasidő-számláló | 06:00 DU  | 12:00 DE | 00:00   | 02,00   | 1.50   |
    | FlexCnt  | Rugalmasidő-számláló | 06:00 DU  | 12:00 DE | 02,00   | 06,00   | 2.00   |

    > [!NOTE]
    > Minden sor másik időintervallumra van használatban, és eltérő tényezővel rendelkezik. Az időintervallumban ledolgozott dolgozói rugalmas órákat megszorozzák az adott sor tényezőjével. Például a 18:00 és 20:00 között ledolgozott órákat 1,50-del szorozzák be. A tényező itt van megadva: **Tényező** mező az **Általános** lapján a **Fizetési megállapodás sorai** oldalnak.

A dolgozó a napra vonatkozóan felviszi az alábbi regisztrációkat.

| Naplóregisztráció típusa | Eleje    | Vége      |
|---------------------------|----------|----------|
| Érkezéskori blokkolás                  | 07:00 DE | 07:00 DE |
| Termelési feladat            | 07:00 DE | 09:00 DU |
| Távozáskori blokkolás                 | 09:00 DU | 09:00 DU |

A kifizetendő összeg számítása a **Jóváhagyás** lapon történik, a dolgozó regisztrációja alapján. A regisztráció kiszámítása után megtekintheti az eredményt az **idők** lapon. Ebben az esetben az Önt érdeklő mezők a következők.

| Rugalmasidő-többlet | Rugalmasidő-hiány | Idő  | Fizetett idő |
|--------|--------|-------|----------|
| 6,00   | 0,00   | 13,50 | 08,00    |

Rugalmasidő-többlet összege hat óra, és a számítás az időprofil rugalmasidő-zónáin alapul. Ez az összeg egy óra rugalmasidő-többletből áll összes 07:00 óra és 08:00 óra között, és 5 óra rugalmasidő-többletből 16:00 és 21:00 óra között.

A regisztrációk átvitelekor megfigyelheti, hogy a rugalmasidő-többlet összege módosult 6,0 óráról 8.0 órára.

| Rugalmasidő-többlet | Rugalmasidő-hiány | Idő  | Fizetett idő |
|--------|--------|-------|----------|
| 8,00   | 0,00   | 13,50 | 08,00    |

Ez a módosítás az átvitel után történik, mert a rugalmas órák számítása a fizetéstípusokon alapul az idő helyett. A következő táblázat a nyolc óra kiszámításának módját mutatja.

| Kezdőérték     | Végérték       | Idő | Szorzó    | Rugalmasidő-számla |
|----------|----------|------|-----------|--------------|
| 07:00 DE | 08:00 DE | 1    | 1         | 1            |
| 04:00 DU | 06:00 DU | 2    | 1         | 2            |
| 06:00 DU | 08:00 DU | 2    | 1.5       | 3            |
| 08:00 DU | 09:00 DU | 1    | 2         | 2            |
|          |          |      | **Összesen** | **8**        |
