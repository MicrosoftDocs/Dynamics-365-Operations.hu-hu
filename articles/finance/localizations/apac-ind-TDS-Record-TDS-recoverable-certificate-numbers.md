---
title: TDS visszatéríthető tanúsítvány számának rögzítése
description: Ez a cikk bemutatja, hogy hogyan lehet a Vissza állítható tanúsítványok lapon rögzíteni az adott szállítóhoz, vevőhöz vagy főkönyvhöz beérkezett adó levont adó tanúsítványszámait és dátumait.
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
ms.openlocfilehash: 513412e292167795fad9d80b68e6e5e14dbd13c5
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8853256"
---
# <a name="record-tds-recoverable-certificate-numbers"></a>TDS visszatéríthető tanúsítvány számának rögzítése

[!include [banner](../includes/banner.md)]

Ez a cikk **bemutatja**, hogy hogyan lehet a Vissza állítható tanúsítványok lapon rögzíteni az adott szállítóhoz, vevőhöz vagy főkönyvhöz beérkezett adó levont adó tanúsítványszámait és dátumait. Az ezen az oldalon a TDS-tranzakcióknál rögzített TDS-bizonylatszámok és dátumok frissítéséhez használja a **Tanúsítvány frissítése** lapot (**Főkönyv \> Időszakos \> Adóelőleg \> Tanúsítvány frissítése**). Miután befejezte a TDS-tanúsítványszámok frissítését, zárja be azokat.

Kövesse az alábbi lépéseket a TDS-tanúsítványok számának és dátumának rögzítéséhez.

1. Ugorjon az **Adó \> Közvetett adó \> Adóelőleg \> Visszatéríthető tanúsítvány** elemre.

    [![Visszatéríthető tanúsítványok lap.](./media/apac-ind-TDS-49.png)](./media/apac-ind-TDS-49.png) 

2. A **Visszatéríthető tanúsítványok** lapon az **Adó típusa** mezőben válassza a **TDS** lehetőséget.
3. Válassza az **Új** lehetőséget egy rekord létrehozásához.
4. A **Tanúsítvány száma** mezőben adja meg a TDS-tanúsítvány számát.
5. A **Számlatípus** mezőben válassza ki azt a számlatípust, amelyhez a TDS-tanúsítvány érkezik: **Szállító**, **Vevő** vagy **Főkönyv**.
6. A **Számla** mezőben válassza ki a szállító, a vevő vagy a főkönyv számlaszámát a kiválasztott számlatípustól függően. A **Név** mező a szállító, a vevő vagy a főkönyv számlanevét mutatja.
7. A **Tanusítvány összege** mezőbe írja be a TDS-tanúsítvány összegét.
8. A **Dátum** mezőben adja meg a tanúsítvány számának tanúsítványidejét.
9. Válassza a **Lekérdezések** lehetőséget a **Tanúsítványtranzakciók** oldal megnyitásához, ahol megtekintheti azokat a TDS-tranzakciókat, amelyekhez a TDS-tanúsítvány száma és dátuma frissül. Ez az információ frissíthető a **Tanúsítvány frissítése** oldalon (**Adó \> Bevallások \> Adóelőleg \> Tanúsítvány frissítése**).

    A **Tanúsítvány frissítése** lapon az egyes TDS-tranzakciókra vonatkozó következő információk találhatók:

    - **Dátum** – A kiválasztott TDS-tranzakció feladási dátuma.
    - **Bizonylat** – A TDS-tranzakció bizonylatszámának megjelenítése.
    - **Forrás** – A modul, amelyben a TDS-tranzakció létrejött.
    - **Számla** – Az a szállítói, vevői vagy főkönyvi számlaszám, amelyhez a TDS-tranzakció készült.
    - **Név** – Az a szállítói, vevői vagy főkönyvi számlanév, amelyhez a TDS-tranzakció készült.
    - **Összeg** – Az a számlaösszeg, amelyen a TDS kiszámításra került.
    - **Adóösszeg** – A tranzakcióhoz kiszámított TDS-adóösszeg.
    - **Tanúsítvány dátuma** – A TDS-tranzakcióhoz frissített TDS-tanúsítvány dátuma.
    - **Tanúsítvány száma** – A TDS-tranzakcióhoz frissített TDS-tanúsítvány száma.

10. A **Visszatéríthető tanúsítványok** lapon jelölje be a **Lezárt** jelölőnégyzetet a TDS-tanúsítványszám bezárásához, miután befejezte a TDS-tranzakciók frissítését a **Tanúsítvány frissítése** lapon.

    Ha ki szeretné választani az oldal összes rekordjának **Lezárt** jelölőnégyzetét, válassza az **Összes jelölése** lehetőséget.

    > [!NOTE]
    > A **Lezárt** jelölőnégyzet által kiválasztott TDS-tanúsítványszámok nem érhetők el a **Tanúsítvány frissítése** lapon.
