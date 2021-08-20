---
title: TDS számítás a szabadszöveges számla oldalon található számlákhoz
description: Ez a témakör ismerteti, hogyan kell kiszámítani a forrásnál levont adót (TDS) a számlákon a Szabadszöveges számla oldalon.
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
ms.openlocfilehash: c543876c48eca55eaaa6fd67585ec357dfea276ffbf8abad3c28c6f4cf29f782
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6750364"
---
# <a name="tds-calculation-on-invoices-from-the-free-text-invoice-page"></a>TDS számítás a szabadszöveges számla oldalon található számlákhoz

[!include [banner](../includes/banner.md)]

Ez a témakör ismerteti, hogyan kell kiszámítani a forrásnál levont adót (TDS) a számlákon a **Szabadszöveges számla** oldalon.

1. Ugorjon a következőre: **Kinnlévőségek \> Számlák \> Kizárólag szabadszöveges számlák**.

    [![Szabadszöveges számla oldal.](./media/apac-ind-TDS-57-1.png)](./media/apac-ind-TDS-57-1.png)

2. Válassza az **Új** lehetőséget, hozzon létre egy szabadszöveges számlát, majd adja meg a szükséges adatokat.
3. Válassza ki a **Számla** lapot. Az **Adóelőlegcsoport** szakaszban az **Értékelő jellege** mező mutatja meg az ügyfél Értékelő jellege kategóriáját.
4. A **TDS-csoport** mezőben tekintse át vagy módosítsa a vevő számára meghatározott alapértelmezett TDS-csoportot.

    > [!NOTE]
    > Amikr értéket választ a **TDS-csoport** mezőben, nem érhető el a **TCS-csoport** mező. A TDS kiszámítása csak akkor történik meg, ha az **Adóelőleg számítása** opció az **Összes szállító** lapon az ügyfél esetében **Igen** értékre van állítva.

5. Az **Adózási információk** lapon, a **Céginformációk** részben, a **Név** mezőben kiválaszthatja a vállalat számára beállított alternatív címhez tartozó cégnevet.

    Az **Adóelőleg** részben az **Adószámlaszám (TAN)** mező a kiválasztott vállalat adószámlaszámát (TAN) mutatja.

6. Hozzon létre számlasorokat a **Számlasorok** lapon, és adja meg a szükséges adatokat.

    Az **Adóelőlegcsoport** szakaszban az **Adószámlaszám (TAN)** mező a TAN- t, a **TDS-csoport** mező pedig a TDS-csoportot mutatja.

7. Az **Ideiglenes adóelőleg-tranzakciók** lap megnyitásához válassza az **Adóelőleg** lehetőséget. Az oldal felső részén a következő mezők találhatók:

    - **Adóelőleg összege összesen** – A TDS-csoport tranzakciójáért kiszámított teljes TDS.
    - **Érték** – A tranzakcióhoz a TDS kiszámításához használt teljes százalék. A teljes százalék a TDS-csoporthoz csatolt és TDS-adókódokra meghatározott képleten alapul.
    - **Korrigált forrásadó összege összesen** – A TDS csoport összes adókódjának teljes korrigált TDS-összege.
    - **TDS** – A bejelölt jelölőnégyzet azt jelzi, hogy egy TDS-csoport csatolva van a tranzakcióhoz.

    Az **Áttekintés**, **Általános** és **Kiigazítás** lapján található mezők a TDS-csoporthoz csatolt egyes TDS-adókódok számított TDS-összegét és kiigazított TDS-összegadatait jelenítik meg.

8. Válassza a **Küszöb** lehetőséget a **Küszöb** lap megnyitásához, ahol áttekintheti az adott TDS-adókódhoz csatolt TDS-adóösszetevőre meghatározott küszöbértéket.
9. Válassza a **Képlettervező** lehetőséget a **Képlettervező** oldal megnyitásához, ahol áttekintheti az adott TDS-adókódhoz definiált képletet.
10. Szabadszöveges számla feladása. A szabadszöveges számlához kiszámított TDS-összeg a TDS-csoport minden egyes TDS-adókódjára meghatározott követelésszámlára kerül. A TDS-adókódok fizetendő számláit vagy kinnlévőségszámláit az **Adóelőleg-kódok** oldalon határozzák meg.
11. Az **Adóelőleg-tranzakciók** lap megnyitásához válassza a **Feladott adóelőleg** lehetőséget. Az **Érték** mező megjeleníti A tranzakcióhoz a TDS kiszámításához használt teljes százalékot.

    Az **Áttekintés**, **Általános** és **Összeg** fülek mezői a számlasorokon kiszámított TDS-összegeket mutatják.

12. Tekintse át a TDS-csoporthoz csatolt minden egyes TDS-adókód TDS-számítási adatait.
