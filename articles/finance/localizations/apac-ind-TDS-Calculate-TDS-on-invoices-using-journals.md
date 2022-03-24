---
title: TDS kiszámítása számlákon naplók segítségével
description: Ez a témakör felsorolja a forrásnál levont adó (TDS) kiszámításának lépéseit a naplókon.
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 5e7654a4e593ab5328077deb571d6e2220fd1385
ms.sourcegitcommit: 6dc2b877cf8ea9185a07964ec05c5ddb7a78471b
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/12/2022
ms.locfileid: "8407611"
---
# <a name="calculate-tds-on-invoices-using-journals"></a>TDS kiszámítása számlákon naplók segítségével

[!include [banner](../includes/banner.md)]

Ez a témakör felsorolja a forrásnál levont adó (TDS) kiszámításának lépéseit a naplókon.

Kezdje az **Általános naplók** oldal megnyitásával (**Főkönyv > Naplóbejegyzések > Általános naplók**).

[![Általános naplók.](./media/apac-ind-TDS-57.png)](./media/apac-ind-TDS-57.png)

1. Hozzon létre naplósorokat a táblázatban felsorolt naplóformák segítségével. Válassza ki a számlatípust és az eltolás számlatípust, és adja meg a tranzakció összegét. 

   > [!NOTE]
   > A **Számlajóváhagyás naplója** lapon válassza az **Utalványok keresése** lehetőséget, és válassza ki a TDS kiszámításához szükséges számlákat. Tekintse meg a **Számlaregisztrátság** vagy az **Bizonylatok keresése** lapon létrehozott számlákat.  

2. A **Napló bizonylat** oldal **Általános** lapján tekintse meg vagy módosítsa a szállítóra vagy vevőre meghatározott alapértelmezett TDS-csoportot a **TDS-csoport** mezőben. A naplósorokra számított TDS-összeg a **TDS-csoport** mezőben felsorolt TDS-adókódokhoz meghatározott képleten alapul. 

   > [!NOTE]
   > Az **Adóelőleg-csoport** mező és a **TCS-csoport** mező nem lesz elérhető, ha a **TDS-csoport** mezőben egy TDS-csoportot választ. Az **Adóelőleg csoport** mező csak az **Általános napló** oldalon érhető el. A TDS kiszámítása csak akkor történik meg, ha az **Összes szállító** vagy az **Összes vevő** lapokon a szállító vagy vevő számára ki van jelölve az **Adóelőleg kiszámítása** jelölőnégyzet.   

3. Válassza ki az **Adózási információk** fület. Szükség esetén válassza ki ebben a mezőben a cégnévhez beállított cég alternatív címeit. A cégnevet a **Céginformáció** mezőcsoport alatt található **Név** mezőben tekintheti meg. 

4. Tekintse meg az eladó vagy vevő értékelő kategóriájának jellegét az **Adóelőleg-mezőcsoport** alá tartozó **Értékelő jellege** mezőben. Az **Adószámlaszám** (**TAN**) mezőben tekintse meg a kiválasztott cégnév TAN-ját.  

5. Az **Ideiglenes adóelőleg-tranzakciók** lap megnyitásához válassza az **Adóelőleg** lehetőséget az **Adóelőleg** menüben. A következő mezők az **Ideiglenes adóelőleg-tranzakciók** oldal felső ablaktábláján jelennek meg.

   - Az **Adóelőleg összege összesen** – A TDS-csoport tranzakciójáért kiszámított teljes TDS.

   - **Érték** – A tranzakció-TDS kiszámításához használt teljes százalék. A teljes százalék a TDS-csoporthoz csatolt TDS-adókódokra meghatározott képleten alapul.

   - **Korrigált forrásadó összege összesen** – A TDS csoport összes adókódjának teljes korrigált TDS-összege.

   - **TDS** – Ha be van jelölve, egy TDS-csoport csatlakozik a tranzakcióhoz.

  Az **Ideiglenes forrásadó-tranzakciók** oldal **Áttekintése**, **Általános** és **Helyesbítése** lapján található mezők a TDS-csoporthoz csatolt egyes TDS-adókódok számított TDS-összegét és kiigazított TDS-összegadatait jelenítik meg.

6. A **Küszöbérték** lap megnyitásához válassza a **Küszöbérték** lehetőséget. Ezen az oldalon tekintse meg az adott TDS-adókódhoz csatolt TDS-adóösszetevőre meghatározott küszöbértéket és kivételi küszöbértéket.

   A **Receptúratervező** lap megnyitásához válassza a **Receptúratervező** űrlapot. Tekintse meg ezen az oldalon az adott TDS-adókódhoz definiált receptúrát. Zárja be a **Képlettervező** és az **Ideiglenes adóelőleg-tranzakciók** oldalakat, hogy visszatérjen a **Napló bizonylat** oldalára.

8. Adja meg az egyéb szükséges adatokat. Ellenőrizze és adja fel a naplót. A beszerzési számlákon kiszámított TDS-összeg a fizetendő számlára kerül. Az értékesítési számlákon kiszámított TDS-összeg a TDS-csoport minden egyes TDS-adókódjára meghatározott követelésszámlára kerül. A TDS-adókódok fizetendő számláit vagy követelésszámláit az **Adóelőleg-kódok** oldalon határozzák meg.

9. Az **Adóelőleg-tranzakciók** lap megnyitásához válassza a **Feladott adóelőleg** lehetőséget. Az **Érték** mezőben megjelenik a tranzakció-TDS kiszámításához használt teljes százalék.

   Az Adóelőleg-tranzakciók oldal **Áttekintés**, **Általános** és **Összeg** lapján található mezők a TDS-csoporthoz csatolt egyes TDS-adókódok számított TDS-összegét és kiigazított TDS-összegadatait jelenítik meg.
