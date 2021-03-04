---
title: Okkódok készletszámláláshoz
description: Ez a témakör ismerteti az okkódok beállítását számlálási feladatokhoz.
author: Mirzaab
manager: tfehr
ms.date: 03/15/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventCountingReasonCodePolicy, InventCountingReasonCode
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 1705903
ms.assetid: 427e01b3-4968-4cff-9b85-1717530f72e4
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: 1025dd00db2e8b87e3c76e3047a7cf470a2d6641
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4429313"
---
# <a name="reason-codes-for-inventory-counting"></a>Okkódok készletszámláláshoz

[!include [banner](../includes/banner.md)]

Az okkódok segítségével elemezheti a számlálási folyamat eredményeit és a folyamat során felmerülő esetleges eltéréseket. Megadhatja a számlálás okait, például hogy eltört a raklap vagy a készletmintákon alapuló készletkiigazítás történt.

## <a name="recommendation"></a>Ajánlás

Mielőtt beállítaná a rendszert, javasoljuk, hogy dolgozzon ki egy stratégiát az okokkódok kezeléséhez. Próbáljon például válaszolni a következő kérdésekre:

- Legyenek az okkódok kötelezők a raktárak számára?
- Legyenek az okkódok kötelezők vagy választhatók egyes cikkeknél?
- Hány okkódra van szükség?
- Hogyan használják a vonalkód-szkennerek felhasználói az okkódokat? Legyenek az okkódok előválasztottak, kötelezőek vagy nem szerkeszthetők?
- A raktári dolgozók különböző kódviselkedést igényelnek a mobil leolvasóknál? Ha a válasz igen, akkor több menüpontot hozhat létre, és hozzárendelheti azokat különböző emberekhez.

## <a name="where-reason-codes-apply"></a>Hol érvényesek az okkódok

Többféle okkód-szabályzatot hozhat létre, és minden okkód-szabályzatban két számlálási okkód szabályzatot adhat meg. A számlálási okkód szabályzatok használhatók a raktár vagy a cikkek szintjén.

## <a name="set-up-reason-code-policies"></a>Okkód-szabályzatok létrehozása

1. Válassza a **Készletkezelés** \> **Beállítás** \> **Készlet** \> **Leltározási okkód irányelvei** elemet, és hozzon létre egy új okkód-irányelvet.
2. A **Leltározási okkód típusa** mezőben a következők közül választhat **Kötelező** vagy **Választható** – ezzel adhatja meg, hogy az okkód kiválasztása kötelező vagy választható legyen-e a következő leltárnaplók egyikében:

    - Ciklikus leltározás (mobileszköz)
    - Eseti leltározás (mobileszköz)
    - Küszöbérték-leltározás (mobileszköz)
    - Igazítás be (mobileszköz)
    - Igazítás ki (mobileszköz)
    - Leltárnapló (funkciógazdag ügyfél)

Az egyes raktárakhoz és termékekhez is létrehozhat okkódokat. A termékek okkódjainak beállítása figyelmen kívül hagyhatja a raktárak beállítását.

## <a name="mandatory-reason-codes"></a>Kötelező okkódok

Ha a **Kötelező** paraméter meg van adva a raktárak vagy cikkek okkódjainak konfigurációjában, a leltárnapló nem fejezhető be és zárható le, amíg okkód nincs megadva.

### <a name="set-up-reason-codes-for-warehouses"></a>Okkódok beállítása raktárakhoz

1. Válassza a **Készletgazdálkodás** \> **Beállítás** \> **Készlet részletezése** \> **Raktárak** lehetőséget.
2. A **Raktár** lapon a **Leltározási okkód irányelve** mezőben válassza ki az egyiket a következő lehetőségek közül:

    - **Üres** – A cikkhez beállított paraméter használatos annak megállapítása, hogy a leltározási naplók kötelezőek-e a termékhez.
    - **Kötelező** – a raktárban a leltárnaplóknál minden esetben szükség van okkódra.
    - **Választható** – a raktárban a leltárnaplóknál nincs minden esetben szükség okkódra.

### <a name="set-up-reason-codes-for-products"></a>Okkódok beállítása termékekhez

1. Válassza a **Termékinformációk kezelése** \> **Termékek** \> **Kiadott termékek** lehetőséget.
2. A **Termék** lapon válassza a **Leltározási okkód irányelve** elemet, majd válassza ki az egyiket a következő lehetőségek közül:

    - **Üres** – A raktárhoz beállított paraméter használatos annak megállapítása, hogy a leltározási naplók kötelezőek-e a termékhez.
    - **Kötelező** – a terméknél a leltárnaplóknál minden esetben szükség van okkódra. Ez a beállítás felülbírálja a raktár szintjén érvényes okkód-beállításokat.
    - **Választható** – a terméknél a leltárnaplóknál nincs minden esetben szükség okkódra. Ez a beállítás felülbírálja a raktár szintjén érvényes okkód-beállításokat.

### <a name="use-reason-codes-in-counting-journals"></a>Okkódok használata leltárnaplókban

A leltárnaplóban az alábbi típusú leltározásokhoz adhat hozzá okkódokat:

- Ciklikus leltározás
- Eseti leltározás
- Küszöbérték-leltározás
- Igazítás be
- Igazítás ki

Az okkódok a **Leltárnapló** leltárnaplóknál a napló soraiba kerülnek hozzáadásra.

1. Válassza a **Készletgazdálkodás** \> **Naplóbejegyzések** \> **Cikkleltár** \> **Leltár** elemet.
2. A leltárnapló sorainak részletei között a **Leltározási okkód** mezőben válasszon egy beállítást.

### <a name="view-the-counting-history-as-its-recorded-by-reason-codes"></a>A leltározási előzmények megtekintése a bejegyzett okkódok alapján

- Válassza a **Készletkezelés** \> **Lekérdezések és jelentések** \> **Leltározási előzmények** elemet, majd a a **Leltározási okkód** mezőben tekintse meg az okkódok formájában rögzített leltározási előzményeket.

### <a name="use-a-reason-code-for-a-quantity-adjustment"></a>Okkód használata mennyiség módosításához

1. Az **Aktuális készlet** oldalon válassza a **Mennyiség módosítása** elemet. Többféleképpen megnyithatja az **Aktuális készlet** lapot. Például válassza a **Készletkezelés** \> **Lekérdezések és jelentések** \> **Aktuális készlet** elemet.
2. Válassza a **Mennyiség módosítása** elemet, majd a **Leltározási okkód** mezőben válasszon egy okkódot.

### <a name="configure-reason-codes-for-mobile-device-menu-items"></a>Okkódok konfigurálása mobileszköz menüelemeihez

Bármilyen típusú leltár okkódjait beállíthatja mobileszköz menüelemeihez. A mobileszköz-menüpont konfigurációja a következő információkat tartalmazza:

- Azt, hogy az okkód megjelenik-e a mobileszközön dolgozó számára leltározás közben.
- Az alapértelmezett okkódot, amely megjelenik a mobileszköz menüpontjában.
- Azt, hogy a felhasználó szerkesztheti-e az okkódot.

### <a name="set-up-reason-codes-on-a-mobile-device"></a>Mobileszköz okkódjainak beállítása

1. Válassza a **Raktárkezelés** \> **Beállítás** \> **Mobileszköz** \> **Mobileszköz menüpontjai** pontot.
2. A **ciklikus leltár** lapon válassza a **Ciklikus leltározás** lehetőséget.
3. Az **Alapértelmezett leltározási okkód** mezőben állítsa be az alapértelmezett okkódot, amelyet rögzíteni kell a leltár készítésekor a mobileszköz-menüpont használatával.
4. A **Leltározási okkód megjelenítése** mezőben válassza a **Sor** elemet, amelyben az okkód megjelenik az egyes különbözetet rögzítése után. Másik lehetőségként válassza az **Elrejtés** elemet, ha az okkódot nem kell megjeleníteni.
5. Állítsa a **Leltározási okkód szerkesztése** lehetőséget vagy **Igen** vagy **Nem** értékre. Ha ez a beállítás **Igen**, a dolgozó szerkesztheti az okkódot, amikor a leltár során megjelenik a mobileszközön.

> [!NOTE]
> A **Ciklikus leltározás** gomb engedélyezhető bármely mobileszköz-menüpontban, ahol leltározás végezhető. Példa: menüelemek eseti leltározáshoz, felhasználó által irányított munkához és a rendszer által irányított munkához.

## <a name="cycle-count-approvals"></a>Ciklikus leltári jóváhagyások

A leltár jóváhagyása előtt a felhasználó módosíthatja a leltárhoz társított okkódot. A leltár jóváhagyásakor az okkód bekerül a leltárnapló soraiba.

### <a name="modify-cycle-count-approvals"></a>Ciklikus leltári jóváhagyások módosítása

1. Válassza a **Raktárkezelés** \> **Ciklikus leltározás** \> **Ciklikus leltározási munka ellenőrzése függőben** lehetőséget.
2. Válassza a **Ciklikus leltározás** elemet, majd az **Okkód** mezőben válasszon egy új okkódot.

### <a name="modify-the-mobile-device-menu-item-for-adjustment-in-and-adjustment-out"></a>A mobileszköz-menüpont módosítása igazítás be és igazítás ki folyamathoz

1. Válassza a **Raktárkezelés** \> **Beállítás** \> **Mobileszköz** \> **Mobileszköz menüpontjai** elemet, majd válassza ki a **Igazítás be és ki** lehetőséget.
2. A **Meglévő munka használata** lehetőséget állítsa **Nem** értékre.
3. A **Munka-létrehozási folyamat** mezőben válassza az **Igazítás be** lehetőséget.

A következő mezők hozzáadódnak a mobileszköz menüelemeihez, amikor az **Igazítás be** vagy **Igazítás ki** van kiválasztva a munka-létrehozási folyamat során:

- Alapértelmezett leltározási okkód
- Leltározási okkód megjelenítése
- Leltározási okkód szerkesztése


[!INCLUDE[footer-include](../../includes/footer-banner.md)]