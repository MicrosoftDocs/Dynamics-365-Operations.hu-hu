---
title: Külső adatok a pénzforgalmi előrejelzésekben
description: Ez a témakör azokat a beállítási lépéseket ismerteti, amelyeket el kell végrehajtani annak érdekében, hogy a pénzforgalmi előrejelzésekbe külső adatokat lehet beírni vagy importálni.
author: rcarlson
ms.date: 12/21/2021
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
ms.openlocfilehash: 66b097b2936e61c619d45ad103440eddbb983feb
ms.sourcegitcommit: c8dc60bb760553f166409c2e06dd2377f601c006
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/23/2021
ms.locfileid: "7945791"
---
# <a name="external-data-in-cash-flow-forecasts"></a>Külső adatok a pénzforgalmi előrejelzésekben

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

A külső adatok bevihetők vagy importálhatók a pénzforgalmi előrejelzésekbe. Ez a témakör azokat a beállítási lépéseket ismerteti, amelyek a külső adatok használatára vonatkoznak, és amelyek lehetővé teszik a külső adatok pénzforgalmi előrejelzésbe való beírását.

## <a name="external-data-setup"></a>Külső adatbeállítás

A Pénzforgalom előrejelzése beállítási lapjának Külső forrás lapja ( Készpénz- és bankkezelés pénzforgalmi előrejelzés - Pénzforgalmi előrejelzés beállítása) használatával adja meg a külső adatok pénzforgalmi előrejelzésekben való használatát **támogató** **·** **\>\>** beállításokat.

A külső adatok bevihetők vagy importálhatók a pénzforgalmi előrejelzésekbe. A külső adatok bevitele vagy importálása előtt be kell állítani a külső adatforrásokat. A Külső **forrás lapon állítsa be a külső pénzforgalmi** kategóriákat. A kategória lehet kimenő **vagy** **bejövő**. **Feladási** típusként a likviditást kell kiválasztani. A Jogi személyek beállításai rácsban válassza ki a jogi személyeket és a megfelelő fő számlákat, amelyekre a külső pénzforgalmi **kategóriák** vonatkoznak.

A pénzforgalmi előrejelzések beállításának további tudnivalókat lásd: [Pénzforgalmi](../cash-bank-management/cash-flow-forecasting.md) előrejelzés.

## <a name="enter-external-data"></a>Külső adatok beírása

A pénzforgalmi előrejelzések külső adatainak módosítására az Excelben való megnyitás tapasztalat **használható**. Jelölje ki a Külső adatok gomb a Pénzforgalmi előrejelzés beállítása lapon, majd válassza a Külső adatok hozzáadása vagy a Meglévő külső adatok **szerkesztése** **·** **·** **lehetőséget**. A Microsoft Excel-fájl megnyitásakor a következő mezőkben adhatja meg a kívánt adatokat:

- **Bejegyzésazonosító** (egyedi)
- **Leírás** (nem kötelező)
- **Külső forrás neve – válasszon ki egyet a Pénzügyi információk beállításakor meghatározott** listából.
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
