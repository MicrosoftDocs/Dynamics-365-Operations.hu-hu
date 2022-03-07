---
title: Tanúsítványszámok és -dátumok frissítése TDS-tranzakciókhoz
description: Ez a témakör elmagyarázza, hogyan lehet frissíteni a visszaigényelhető tanúsítványszámokat és dátumokat frissíteni, amelyek a szállítói, ügyfél- és könyvelési számlákhoz lettek rögzítve a Forrásnál levont adóhoz (TDS).
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
ms.openlocfilehash: a698a8ccc781167060400068dc4011d318b5fe53
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/06/2021
ms.locfileid: "6360215"
---
# <a name="update-certificate-numbers-and-dates-for-tds-transactions"></a>Tanúsítványszámok és -dátumok frissítése TDS-tranzakciókhoz

[!include [banner](../includes/banner.md)]

Ez a témakör elmagyarázza, hogyan lehet frissíteni a visszaigényelhető tanúsítványszámokat és dátumokat frissíteni, amelyek a szállítói, ügyfél- és könyvelési számlákhoz lettek rögzítve a Forrásnál levont adóhoz (TDS). A TDS-tranzakciók tanúsítványait a **Visszatéríthető tanúsítványok** lapon lehet megtekinteni. A tanúsítványokat a **Tanúsítványok frissítése** lapon frissítheti.

Kövesse az alábbi lépéseket a TDS-tanúsítványok számának és dátumának frissítéséhez.

1. Lépjen ide: **Adó \> Bevallások \> Adóelőleg \> Tanúsítvány frissítése**.

    [![Tanúsítvány frissítése oldal.](./media/apac-ind-TDS-45.png)](./media/apac-ind-TDS-45.png)

2. A **Tanúsítvány frissítése** lapon, az **Adótípus** mezőben a **Kijelölés** szakaszában válassza ki a **TDS** lehetőséget.
3. A **Tanúsítvány** száma mezőben válassza ki a vevő vagy a szállító TDS-tanúsítványának számát.

    > [!NOTE]
    > A **Tanúsítvány száma** mező csak azokat a TDS-tanúsítványszámokat sorolja fel, amelyek esetében a **Visszaállítható tanúsítványok** lapon törölve van a jelölés a **Lezárt** jelölőnégyzetből.

    A **Tanúsítvány dátuma** mező jeleníti meg a tanúsítvány dátumát. A **Számlatípus** mező mutatja annak a számlának a típusát, amelyhez a TDS-tanúsítvány száma érkezett, a **Név** mezőben pedig a számla neve látható.

5. Az **Kezdő dátum** és a **Záró dátum** mezőkben, válassza ki a az időszak kezdő és záró dátumát, amelyhez meg szeretné jeleníteni a TDS-tranzakciókat.
6. Az **Adatok megjelenítése** lehetőséget választva megtekintheti a kijelölt időszakban könyvelt TDS-tranzakciókat.

    Az **Áttekintés** lapon a felső ablaktábla rácsa a szállítóhoz vagy vevőhöz a megadott időszakban feladott minden egyes TDS-tranzakcióval kapcsolatban a következő adatokat mutatja:

    - **Bizonylat** – A TDS-tranzakció bizonylatszámának megjelenítése.
    - **Dátum** – A kiválasztott TDS-tranzakció dátuma.
    - **Összeg** – Az a számlaösszeg, amelyen a TDS kiszámításra került.
    - **Adóösszeg** – A tranzakcióhoz kiszámított TDS-adóösszeg.

7. A felső rácsból konkrét TDS-tranzakciók áthelyezéséhez az alsó rácsba, jelölje ki a tranzakciókat, majd válassza a **Belefoglalás** lehetőséget. Másik lehetőségként válassza az **Összes belefoglalása** lehetőséget az összes TDS-tranzakciót áthelyezéséhez a felső rácsból az alsó rácsba.

    Ha konkrét TDS-tranzakciókat vagy minden TDS-tranzakciót át szeretne áthelyezni az alsó rácsból a felső rácsba, használja a **Kihagyás** vagy az **Összes kihagyása** lehetőséget.

8. A **Frissítés** lehetőséget választva frissítheti az alsó rácsban a TDS-tranzakciók **Tanúsítványszám** és **Tanúsítvány dátuma** mezőit.
10. Menjen az **Adó \> Közvetett adók \> Adóelőleg \> Visszaállítható tanúsítvány** menübe és a **Lekérdezés** lehetőséget választva megtekintheti azokat a frissített tranzakciósorokat, amelyek az új tanúsítványszámokat tartalmazzák a **Tanúsítványtranzakciók** oldalon.

    [![Tanúsítványtranzakciók oldal.](./media/apac-ind-TDS-46.png)](./media/apac-ind-TDS-46.png)
