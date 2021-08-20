---
title: Külső adatok használata pénzforgalmi előrejelzésekben (előzetes verzió)
description: Ez a témakör azokat a beállítási lépéseket ismerteti, amelyeket végre kell hajtania ahhoz, hogy külső adatokat lehessen bevinni vagy behozni a pénzforgalmi előrejelzésekbe.
author: rcarlson
ms.date: 07/16/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalSetup, LedgerJournalTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2020-06-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: ff2a454b422cc4decc15339e6b328d99df85ccbc66ba3928f6c9e9f21b7b51a7
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6768843"
---
# <a name="use-external-data-in-cash-flow-forecasts-preview"></a>Külső adatok használata pénzforgalmi előrejelzésekben (előzetes verzió)

[!include [banner](../includes/banner.md)]

A külső adatok bevihetők vagy importálhatók a pénzforgalmi előrejelzésekbe. Ez a témakör azokat a beállítási lépéseket ismerteti, amelyek a külső adatok használatára vonatkoznak, és amelyek lehetővé teszik a külső adatok pénzforgalmi előrejelzésbe való beírását.

## <a name="external-data-setup"></a>Külső adatbeállítás

A **Pénzforgalmi előrejelzés beállítása** lapon (**Készpénz- és bankkezelés \> Pénzforgalmi előrejelzés**) lévő **Külső forrás** oldalon adhatja meg azokat a beállításokat, amelyek támogatják a külső adatok használatát a pénzforgalmi előrejelzésekben.

Az számlálók beállításával kapcsolatos további információkat lásd: [Pénzforgalmi előrejelzés](../cash-bank-management/cash-flow-forecasting.md).

A pénzforgalmi előrejelzések külső adatainak megadásához használja az Open in Excel felhasználói felületet külső adatok beviteléhez és módosításához. Válassza ki a **Külső adatok** gombot, majd válassza a **Külső adatok hozzáadása** vagy a **Meglévő külső adatok szerkesztése** lehetőséget. A Microsoft Excel-fájl megnyitásakor a következő mezőkben adhatja meg a kívánt adatokat:

- **Bejegyzésazonosító**
- **Leírás** (nem kötelező)
- **Külső forrás neve** – A pénzügyi betekintések beállításakor megadott lista egyik értékének kiválasztása.
- **Jogi személy**
- **Dátum**
- **Összeg a tranzakció pénznemében.**
- **Pénznemkód**
- **Alapértelmezett dimenzió** (nem kötelező)
- **Dokumentum száma** (nem kötelező)
- **Számla száma** (nem kötelező)
- **Számla neve** (nem kötelező)

## <a name="importing-external-data-by-using-the-data-management-framework"></a>Külső adatok importálása az Adatkezelési keretrendszer használatával

A külső adatokat a pénzforgalmi előrejelzésekhez az **Adatkezelés** munkaterületen és a **Pénzforgalmi előrejelzés külső forrás bejegyzésével** ellátott entitáson keresztül importálhatók.

Ezenkívül ha a beállítási adatokat át kell vinni egyik környezetből a másikba, a következő entitások érhetők el a szükséges beállítási táblákban:

- Pénzforgalmi előrejelzés külső forrásának beállítása
- Pénzforgalmi előrejelzés külső forrásaként megadott jogi személy beállítása

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
