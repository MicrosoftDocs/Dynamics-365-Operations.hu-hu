---
title: Vonalkódok beolvasása a raktári alkalmazás kamerája segítségével
description: Ez a témakör bemutatja, hogy miként állítható be a raktári alkalmazása arra, hogy vonalkódokat olvasson be egy mobileszköz kamerájának használatához.
author: MarkusFogelberg
manager: tfehr
ms.date: 01/03/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSMobileAppField
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 269384
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2017-01-03
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: fd4818ab936e1c93000793da756c97df6d05b2a9
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4429311"
---
# <a name="scan-bar-codes-using-a-camera-in-the-warehouse-app"></a>Vonalkódok beolvasása a raktári alkalmazás kamerája segítségével

[!include [banner](../includes/banner.md)]

Ez a témakör bemutatja, hogy miként állítható be a raktári alkalmazása arra, hogy vonalkódokat olvasson be egy mobileszköz kamerájának használatához. 

## <a name="prerequisites"></a>Előfeltételek
A funkció használatához a raktári alkalmazás 1.2.0.0-s verziójának kell telepítve lennie, és eszközén lennie kell kamerának. Ha megnyitja az alkalmazást a frissítést követően, akkor a rendszer felajánlja az engedélyezést az alkalmazás számára a kamera használatára. Ha az eszközön nincs kamera, akkor nem jelenik meg a felajánlás, és akkor nem tud kamerát használni a beolvasásra. 

## <a name="setup"></a>Beállítás
A raktári alkalmazás Megjelenítési beállítások szakaszában kiválaszthatja, hogy a kamerát szeretné-e használni a vonalkódok beolvasására. Ha engedélyezi a **Kamera használata beolvasásra** lehetőséget, akkor használhatja a kamerát mindegyik olyan beviteli mezőn, amelynél az előnyben részesített beviteli mód a **Beolvasás**. 

Annak irányításához, hogy egy beviteli mező beolvasható legyen-e, **A raktári alkalmazáson belüli mezőnevek** lapján állítsa a **Preferált beviteli mód** beállítást **Beolvasás** értékre. Ha ez a beállítás van kijelölve, egy kamera használható beolvasásra a raktári alkalmazásban. Ha információt szeretne arról, hogy miként konfigurálhatók az alkalmazásmezőnevek a Raktárkezelésnél, lásd a következőt: [A raktári alkalmazás alkalmazás-mezőneveinek konfigurálása](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/warehousing/configure-app-field-names-priorities-warehouse).

## <a name="supported-bar-code-formats"></a>Támogatott vonalkódformátumok
A leggyakoribb vonalkódformátumok támogatottak, beleértve a következőket: Code 128, Code 39, Code 93, EAN-8, EAN-13, UPC-E, UPC-A és QR-kódok. 

## <a name="navigation"></a>Navigáció
A kamera lap minden olyan oldalnál elindul, ahol a beviteli mezőnél a preferált beviteli mód a Beolvasás, amikor a Kamera oldalon a következő lehetőségek közül választhat:
- Kattintson a Vissza gombra a Feladatok és részletes adatok oldalára való visszatéréshez. 
- Kattintson a ceruza ikonra a Feladatok és részletes adatok oldalán, hogy arra a lapra juthasson, ahol az értéket manuálisan adhatja meg.
- Kattintson a kamerára a Feladatok és részletes adatok oldalán a Kamera lapra való visszatéréshez. 

| Feladatok és részletes adatok oldala | Kamera lap | 
| :---------------------: | :--------------------: |
| ![Kamerabeolvasás példafeladat részletek oldala](./media/camera-scanning-example-task-detail-page50.png)          | ![Kamerabeolvasás példafeladat kisebb oldala](./media/camera-scanning-example-camera-page50.png)          |

Ha a kamera lapján a Kamera gombra kattint, akkor az kiszürkítve jelenik meg, amikor megpróbál azonosítani egy vonalkódot. Ha a vonalkód azonosítása nem történik meg 5 másodpercen belül, akkor a folyamat időkorlátja lejár, és a Kamera gomb ismét elérhető lesz. Ezután ismét megpróbálja beolvasni a vonalkódot.

Amikor a kamerával egy vonalkódra céloz, tartsa a vonalkódot egy vonalban a keretekkel a legjobb eredmény elérése érdekében. Amikor megtörténik egy vonalkód sikeres beolvasása, megtörténik a folyamat feldolgozása, és Ön a következő lépéshez jut. Ha a következő lépés egy másik beviteli mezőt tartalmaz, és a preferált beviteli mód a Beolvasás, akkor újraindul a kamera lapja. Ha a következő lépésként nem egy beolvasási mező jelenik meg, akkor nem indul el a kamera lap.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]