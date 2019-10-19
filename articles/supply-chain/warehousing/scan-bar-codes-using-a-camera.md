---
title: Vonalkódok beolvasása a Dynamics 365 Supply Chain Management – Raktározás alkalmazás kamerája segítségével
description: Ez a témakör bemutatja, hogy miként állítható be a Dynamics 365 Supply Chain Management – Raktárkezelés alkalmazása arra, hogy vonalkódokat olvasson be egy mobileszköz kamerájának használatához.
author: MarkusFogelberg
manager: AnnBe
ms.date: 01/03/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSMobileAppField
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 269384
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2017-01-03
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: 8062a981f792bcfed2713d3cb6a42f414394f6a4
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/30/2019
ms.locfileid: "2251460"
---
# <a name="scan-bar-codes-using-a-camera-in-dynamics-365-supply-chain-management---warehousing-app"></a>Vonalkódok beolvasása a Dynamics 365 Supply Chain Management – Raktározás alkalmazás kamerája segítségével

[!include [banner](../includes/banner.md)]

Ez a témakör bemutatja, hogy miként állítható be a Dynamics 365 Supply Chain Management – Raktárkezelés alkalmazása arra, hogy vonalkódokat olvasson be egy mobileszköz kamerájának használatához. 

## <a name="prerequisites"></a>Előfeltételek
A funkció használatához a Raktárkezelés alkalmazás 1.2.0.0-s verziójának kell telepítve lennie, és eszközén lennie kell kamerának. Ha megnyitja az alkalmazást a frissítést követően, akkor a rendszer felajánlja az engedélyezést az alkalmazás számára a kamera használatára. Ha az eszközön nincs kamera, akkor nem jelenik meg a felajánlás, és akkor nem tud kamerát használni a beolvasásra. 

## <a name="setup"></a>Beállítás
A Raktárkezelés alkalmazás Megjelenítési beállítások szakaszában kiválaszthatja, hogy a kamerát szeretné-e használni a vonalkódok beolvasására. Ha engedélyezi a **Kamera használata beolvasásra** lehetőséget, akkor használhatja a kamerát mindegyik olyan beviteli mezőn, amelynél az előnyben részesített beviteli mód a **Beolvasás**. 

Annak irányításához, hogy egy beviteli mező beolvasható legyen-e, **A raktári alkalmazáson belüli mezőnevek** lapján állítsa a **Preferált beviteli mód** beállítást **Beolvasás** értékre. Ha ez a beállítás van kijelölve, egy kamera használható beolvasásra a Raktárkezelés alkalmazásban. Ha információt szeretne arról, hogy miként konfigurálhatók az alkalmazásmezőnevek a Raktárkezelésnél, lásd a következőt: [A Warehousing alkalmazás alkalmazás-mezőneveinek konfigurálása](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/warehousing/configure-app-field-names-priorities-warehouse).

## <a name="supported-bar-code-formats"></a>Támogatott vonalkódformátumok
A leggyakoribb vonalkódformátumok támogatottak, beleértve a következőket: Code 128, Code 39, Code 93, EAN-8, EAN-13, UPC-E, UPC-A és QR-kódok. 

## <a name="navigation"></a>Navigáció
A kamera lap minden olyan oldalnál elindul, ahol a beviteli mezőnél a preferált beviteli mód a Beolvasás, amikor a Kamera oldalon a következő lehetőségek közül választhat:
- Kattintson a Vissza gombra a Feladatok és részletes adatok oldalára való visszatéréshez. 
- Kattintson a ceruza ikonra a Feladatok és részletes adatok oldalán, hogy arra a lapra juthasson, ahol az értéket manuálisan adhatja meg.
- Kattintson a kamerára a Feladatok és részletes adatok oldalán a Kamera lapra való visszatéréshez. 

| Feladatok és részletes adatok oldala | Kamera lap | 
| :---------------------: | :--------------------: |
| ![camera-scanning-example-task-detail-page](./media/camera-scanning-example-task-detail-page50.png)          | ![camera-scanning-example-camera-page-smaller](./media/camera-scanning-example-camera-page50.png)          |

Ha a kamera lapján a Kamera gombra kattint, akkor az kiszürkítve jelenik meg, amikor megpróbál azonosítani egy vonalkódot. Ha a vonalkód azonosítása nem történik meg 5 másodpercen belül, akkor a folyamat időkorlátja lejár, és a Kamera gomb ismét elérhető lesz. Ezután ismét megpróbálja beolvasni a vonalkódot.

Amikor a kamerával egy vonalkódra céloz, tartsa a vonalkódot egy vonalban a keretekkel a legjobb eredmény elérése érdekében. Amikor megtörténik egy vonalkód sikeres beolvasása, megtörténik a folyamat feldolgozása, és Ön a következő lépéshez jut. Ha a következő lépés egy másik beviteli mezőt tartalmaz, és a preferált beviteli mód a Beolvasás, akkor újraindul a kamera lapja. Ha a következő lépésként nem egy beolvasási mező jelenik meg, akkor nem indul el a kamera lap.

