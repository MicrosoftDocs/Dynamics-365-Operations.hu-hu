---
title: Vonalkódok beolvasása a Warehouse Management mobilalkalmazás kamerája segítségével
description: Ez a cikk bemutatja, hogyan lehet beállítani a Raktárkezelés mobilalkalmazást a vonalkódok beolvasására egy mobileszköz kamerájával.
author: Mirzaab
ms.date: 01/03/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSMobileAppField
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2017-01-03
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: 8459ea6912328fa589b92f1731551f56df89c11b
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8862337"
---
# <a name="scan-bar-codes-using-a-camera-in-the-warehouse-management-mobile-app"></a>Vonalkódok beolvasása a Warehouse Management mobilalkalmazás kamerája segítségével

[!include [banner](../includes/banner.md)]

Ez a cikk bemutatja, hogyan lehet beállítani a Raktárkezelés mobilalkalmazást a vonalkódok beolvasására egy mobileszköz kamerájával.

## <a name="setup"></a>Beállítás

A Raktárkezelés mobilalkalmazás Megjelenítési beállítások szakaszában kiválaszthatja, hogy a kamerát szeretné-e használni a vonalkódok beolvasására. Ha engedélyezi a **Kamera használata beolvasásra** lehetőséget, akkor használhatja a kamerát mindegyik olyan beviteli mezőn, amelynél az előnyben részesített beviteli mód a **Beolvasás**.

Annak irányításához, hogy egy beviteli mező beolvasható legyen-e, **A raktári alkalmazáson belüli mezőnevek** lapján állítsa a **Preferált beviteli mód** beállítást **Beolvasás** értékre. Ha ez a beállítás van kijelölve, egy kamera használható beolvasásra a Raktárkezelés mobilalkalmazásban. ovábbi információ: [A Raktárkezelés mobilalkalmazás mezőinek konfigurálása](configure-app-field-names-priorities-warehouse.md).

## <a name="supported-bar-code-formats"></a>Támogatott vonalkódformátumok

A leggyakoribb vonalkódformátumok támogatottak, beleértve a következőket: Code 128, Code 39, Code 93, EAN-8, EAN-13, UPC-E, UPC-A és QR-kódok.

## <a name="navigation"></a>Navigáció

A kamera lap minden olyan oldalnál elindul, ahol a beviteli mezőnél a **Preferált beviteli mód** értéke a *Beolvasás*, amikor a Kamera oldalon a következő lehetőségek közül választhat:

- Válassza a Vissza gombot a **Feladatok és részletes adatok** oldalára való visszatéréshez.
- Válassza a ceruza ikont a **Feladatok és részletes adatok** oldalán, hogy arra a lapra juthasson, ahol az értéket manuálisan adhatja meg.
- Válassza ki a kamerát a **Feladatok és részletes adatok** oldalán a Kamera lapra való visszatéréshez.

Ha a kamera lapján a Kamera gombot választják, akkor az kiszürkítve jelenik meg, amikor megpróbál azonosítani egy vonalkódot. Ha a vonalkód azonosítása nem történik meg 5 másodpercen belül, akkor a folyamat időkorlátja lejár, és a Kamera gomb ismét elérhető lesz. Ezután ismét megpróbálja beolvasni a vonalkódot.

Amikor a kamerával egy vonalkódra céloz, tartsa a vonalkódot egy vonalban a keretekkel a legjobb eredmény elérése érdekében. Amikor megtörténik egy vonalkód sikeres beolvasása, megtörténik a folyamat feldolgozása, és Ön a következő lépéshez jut. Ha a következő lépés egy másik beviteli mezőt tartalmaz, és a preferált beviteli mód a Beolvasás, akkor újraindul a kamera lapja. Ha a következő lépésként nem egy beolvasási mező jelenik meg, akkor nem indul el a kamera lap.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]