---
title: TDS-számlák kiszámítása a beszerzési rendelési űrlap és az értékesítési rendelési űrlap segítségével
description: Ez a cikk felsorolja a különböző típusú számlák levont adója (TDS) kiszámításának lépéseit.
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: 72883741ee7eed6b0296736c80dd648c882ae53e
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8853285"
---
# <a name="calculate-tds-invoices-using-purchase-order-form-and-sales-order-form"></a>TDS-számlák kiszámítása a beszerzési rendelési űrlap és az értékesítési rendelési űrlap segítségével

[!include [banner](../includes/banner.md)]

Ez a cikk a **Beszerzési rendelés,** **·** **·** **a Beszerzési napló, a Keretrendelés és az Értékesítési rendelés lap használatával sorolja fel a különböző típusú számlák levont adója kiszámításának lépéseit.**

1. Hozzon létre egy beszerzési rendelést, beszerzési naplót, beszerzési keretrendelést vagy értékesítési rendelést a felsorolt oldalon. Adja meg a szükséges adatokat.

2. Válassza a **Beállítás** fület a szállító vagy vevő értékelőjének természetének megtekintéséhez. Ezek az információk az **Adóelőleg-csoport** mezőcsoport alatti **Értékelők jellege** mezőben felsoroltak.

3. A **TDS-csoport** mezőben tekintse meg vagy módosítsa a szállító vagy vevő számára meghatározott alapértelmezett TDS-csoportot.

   > [!NOTE]
   > A **TCS-csoportmező** nem érhető el, ha a TDS-csoportmezőben kiválaszt egy **TDS-csoportot**. A TDS kiszámítása csak akkor történik meg, ha az **Összes szállító** vagy az **Összes vevő** lapon a szállító vagy vevő számára ki van jelölve az **Adóelőleg kiszámítása** jelölőnégyzet.  

4. Hozzon létre cikksorokat a **Sorok** lapon, és adja meg a szükséges adatokat.

5. Válassza a **Beállítás** lapot (vonalszint) a fejlécszinten definiált TDS-csoport megtekintéséhez vagy módosításához. A TDS-csoport a **TDS-csoport** mezőben jelenik meg, amely az **Adóelőleg-csoport** mezőcsoportja alatt található.

6. Válassza ki az **Adózási információk** fület, és válassza ki az ebben a mezőben megjelenő cégnévhez beállított alternatív címeket. A cégnév a **Céginformáció** mezőcsoport alatt található **Név** mezőben jelenik meg. 

   A kiválasztott cégnév TAN-ja az **Adószámlaszám** (**TAN**) mezőben jelenik meg az **Adóelőleg** mezőcsoport alatt. 

7. Az **Ideiglenes adóelőleg-tranzakciók** lap megnyitásához válassza az **Adóelőleg** lehetőséget. Tekintse meg a következő mezőket az **Ideiglenes adóelőleg-tranzakciók** oldal felső ablaktábláján.

   - **Adóelőleg** **összege** **összesen** – A TDS-csoport tranzakciójáért kiszámított teljes TDS.

   - **Érték** – A tranzakció-TDS kiszámításához használt teljes százalék. A teljes százalék a TDS-csoporthoz csatolt TDS-adókódokra meghatározott képleten alapul.

   - **Korrigált forrásadó összege összesen** – A TDS csoport összes adókódjának teljes korrigált TDS-összege.

   - **TDS** – Ha be van jelölve, egy TDS-csoport csatlakozik a tranzakcióhoz.

Az **Ideiglenes forrásadó-tranzakciók** oldal **Áttekintése**, **Általános** és **Helyesbítése** lapján található mezők a TDS-csoporthoz csatolt egyes TDS-adókódok számított TDS-összegét és kiigazított TDS-összegadatait jelenítik meg.

8. A **Küszöbérték** lap megnyitásához válassza a **Küszöbérték** lehetőséget. Ezen az oldalon tekintse meg az adott TDS-adókódhoz csatolt TDS-adóösszetevőre meghatározott küszöbértéket.

9. A **Receptúratervező** lap megnyitásához válassza a **Receptúratervező** lehetőséget. Tekintse meg ezen az oldalon az adott TDS-adókódhoz definiált képletet. 

10. Számla feladása. A beszerzési számlákon kiszámított TDS-összeg a fizetendő számlára kerül, és az értékesítési számlákon kiszámított TDS-összeg a TDS-csoport minden egyes TDS-adókódjához meghatározott követelésszámlára kerül. A TDS-adókódok fizetendő számláit vagy követelésszámláit az **Adóelőleg-kódok** oldalon határozzák meg.

11. Válassza a **Lekérdezés** gombot **> Számla > Aadóelőleg-bizonylatok** gombot az **Adóelőleg-tranzakciók** oldal megnyitásához. Az **Érték** mezőben megtekintheti a tranzakció-TDS kiszámításához használt teljes százalékot.

Az **Adóelőleg-tranzakciók** oldalon az **Áttekintés**, **Általános** és az **Összeg** fülön található mezők a tranzakcióra számított TDS adatait jelenítik meg. Tekintse meg a TDS-csoporthoz csatolt minden egyes TDS-adókód TDS-számítási adatait.
