---
title: Kifizetések és kötelezvények TDS-számítása
description: Ez a témakör hivatkozási adatokat tartalmaz a forrásnál levont adó (TDS) számításának különböző fizetési tranzakcióiról.
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: 28afd04b1c341985f7ac15e05aba7a9039a59d869dd5bc60b4163d2ba1ae4ec0
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6750340"
---
# <a name="tds-calculation-on-payments-and-promissory-notes"></a>Kifizetések és kötelezvények TDS-számítása

[!include [banner](../includes/banner.md)]

Ez a témakör hivatkozási adatokat tartalmaz a forrásnál levont adó (TDS) számításának különböző fizetési tranzakcióiról.

| Sorozatszám | Tranzakció típusa | Tranzakció összege | Oldalszám és elérési út | Számla típusa és ellenszámla típusa |
|---------------|------------------|--------------------|--------------------|--------------------------------------|
| 1             | Előlegfizetés / Fizetés számlával szemben (TDS-kötelezettség) | Terhelés vagy jóváírás | <ul><li>Általános napló (**Főkönyv \> Naplóbejegyzések \> Általános naplók**)</li><li>Számlanapló (**Kötelezettségek \> Számlák \> Számlanapló**)</li><li>Számlanapló (**Kötelezettségek \> Kifizetés \> Szállítói kifizetési napló**)</li></ul> | Szállító (Dr.), bank (Cr.) |
| 2             | Előlegfizetés / Fizetés számla ellenében (Vevőtől származó beszerzés – TDS-kötelezettség) | Terhelés vagy jóváírás | <ul><li>Általános napló (**Főkönyv \> Naplóbejegyzések \> Általános naplók**)</li><li>Számlanapló (**Kötelezettségek \> Számlák \> Számlanapló**)</li><li>Számlanapló (**Kötelezettségek \> Kifizetés \> Szállítói kifizetési napló**)</li></ul> | Ügyfél (Dr.), bank (Cr.) |
| 3             | Kötelezvények | Tartozik | Kötelezvénykiállítási napló (**Kötelezettségek \> Kifizetések \> Kötelezvények \> Kötelezvénykiállítási napló**) | Szállító (Dr.), Főkönyv (Cr.) |
| 4             | Vegyes bevétel (TDS-kinnlevőségek) | Terhelés vagy jóváírás | Általános napló (**Főkönyv \> Naplóbejegyzések \> Általános naplók**) | Bank (Dr.), Főkönyv (Cr.) |
| 5             | Egyéb költségek (TDS-kötelezettségek) | Terhelés vagy jóváírás | Általános napló (**Főkönyv \> Naplóbejegyzések \> Általános naplók**) | Bank (Dr.), Főkönyv (Cr.) |

A következő lépések szerint számítsa ki a kifizetésekre és kötelezvényekre vonatkozó TDS-t.

1. A naplólapokon hozzon létre naplósorokat. Válassza ki a számla típusát és az ellenszámla típusát.
2. Válassza ki a **Funkciók \> Kiegyenlítés** lehetőséget a **Nyitott tranzakciók szerkesztése** oldal megnyitásához. Ezután válassza ki azt a konkrét számlát, amelyet ki kell egyenlíteni. Ha a TDS már számlaszinten lett kiszámítva, az **Összeg eredete** mező mutatja azt az alapösszeget, amely alapján a TDS kiszámítása történik. A **TDS-összeg** mező jeleníti meg a tranzakcióhoz kiszámított TDS-összeget. Az **Összeg** mezőben a nettó kifizetés összege látható (ez a kifizetés összege a TDS levonása után).

    > [!NOTE]
    > Számla ellenében történő kifizetés esetén a következő feltételek érvényesek:
    >
    > - Ha a kifizetési összeg és a számlaösszeg megegyezik, akkor a program nem számít TDS-összeget, ha a számla szintjén már kiszámították.
    > - Ha a számlaösszeg a TDS összegének levonása után több, mint a kifizetés összege, akkor nem lesz kiszámítva a TDS.
    > - Ha a TDS összegének levonása után a számlaösszeg kevesebb, mint a kifizetés összege, akkor a TDS számítása a számlaösszeget meghaladó összeg alapján történik.

3. A **Napló bizonylat** oldalon az **Áttekintés** lapon tekintse meg vagy módosítsa a szállítóra vagy vevőre meghatározott alapértelmezett TDS-csoportot a **TDS-csoportok** mezőben. A naplósorokra számított TDS a TDS-csoportban felsorolt TDS-adókódokhoz meghatározott képleten alapul.

    > [!NOTE]
    > A TDS kiszámítása csak akkor történik meg, ha az **Adóelőleg számítása** opció a **Szállítók** lapon a szállító esetében **Igen** értékre van állítva.

4. Az **Adózási információk** lapon, a **Céginformációk** részben, a **Név** mezőben kiválaszthatja a vállalat számára beállított alternatív címekhez tartozó cégnevet.

    Az **Adóelőleg-mezőcsoport** alá tartozó **Értékelő jellege** mező megjeleníti az értékelő kategória jellegét a szállítóhoz vagy ügyfélhez. Az **Adószámlaszám (TAN)** mező a kiválasztott vállalat adószámlaszámát (TAN) mutatja.

5. Az **Ideiglenes adóelőleg-tranzakciók** lap megnyitásához válassza az **Adóelőleg gomb \> adóelőleg** lehetőséget. Az oldal felső részén a következő mezők találhatók:

    - **Adóelőleg összege összesen** – A TDS-csoport tranzakciójáért kiszámított teljes TDS.
    - **Érték** – A tranzakcióhoz a TDS kiszámításához használt teljes százalék. A teljes százalék a TDS-csoporthoz csatolt és TDS-adókódokra meghatározott képleten alapul.
    - **Korrigált forrásadó összege összesen** – A TDS csoport összes adókódjának teljes korrigált TDS-összege.
    - **TDS** – A bejelölt jelölőnégyzet azt jelzi, hogy egy TDS-csoport csatolva van a tranzakcióhoz.

    Az **Áttekintés**, **Általános** és **Kiigazítás** lapján található mezők a TDS-csoporthoz csatolt egyes TDS-adókódok számított TDS-összegét és kiigazított TDS-összegadatait jelenítik meg.

6. Válassza a **Küszöb** lehetőséget a **Küszöb** lap megnyitásához, ahol áttekintheti az adott TDS-adókódhoz csatolt TDS-adóösszetevőre meghatározott küszöbértéket.
7. Válassza a **Képlettervező** lehetőséget a **Képlettervező** oldal megnyitásához, ahol áttekintheti az adott TDS-adókódhoz definiált képletet.
8. Zárja be a **Képlettervező** és az **Ideiglenes adóelőleg-tranzakciók** oldalakat, hogy visszatérjen a **Napló bizonylat** oldalára.
9. Ellenőrizze és adja fel a naplót. A kiszámított TDS-összeg a TDS-csoport minden egyes TDS-adókódjára meghatározott kötelezettségszámlára kerül. A TDS-adókódok fizetendő számláit vagy kinnlévőségszámláit az **Adóelőleg-kódok** oldalon határozzák meg.
10. Az **Adóelőleg-tranzakciók** lap megnyitásához válassza a **Feladott adóelőleg** lehetőséget. Az **Érték** mező megjeleníti A tranzakcióhoz a TDS kiszámításához használt teljes százalékot.

    Az **Áttekintés**, **Általános** és **Összeg** fülek mezői a tranzakcióhoz csatolt TDS-csoporthoz kiszámított TDS-összegeket mutatják.

11. Tekintse át a TDS-csoporthoz csatolt minden egyes TDS-adókód TDS-számítási adatait.

## <a name="generate-payments"></a>Kifizetések létrehozása

Kifizetések generálásához kövesse az alábbi lépéseket.

1. Tegye a következők egyikét:

    - Ugorjon a **Kötelezettségek \> Fizetések \> Szállítói kifizetés naplója** lehetőségre.
    - Válassza a **Kinnlevőségek \> Kifizetések \> Kifizetési napló** lehetőséget.
    - Ugorjon a **Kötelezettségek \> Kifizetések \> Kötelezvények \> Kötelezvénykiállítási napló** lehetőségre.
    - Ugrás ide: **Kinnlevőségek \> Kifizetések \> Váltó \> Váltónapló kiállítása**.
    - Ugrás ide: **Kinnlevőségek \> Kifizetések \> Váltó \> Váltónapló újbóli kiállítása**.

2. **Sorok** kiválasztása.
3. Válassza a **Funkciók \> Kifizetések generálása** lehetőséget.
