---
title: Külső adatok használata pénzforgalmi előrejelzésekben (előzetes verzió)
description: Ez a témakör azokat a beállítási lépéseket ismerteti, amelyeket végre kell hajtania ahhoz, hogy külső adatokat lehessen bevinni vagy behozni a pénzforgalmi előrejelzésekbe.
author: rcarlson
ms.date: 05/01/2020
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
ms.openlocfilehash: ddfc0670a5fca24d996e9ab605e267f9f3f26f19
ms.sourcegitcommit: 7d0cfb359a4abc7392ddb3f0b3e9539c40b7204d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/14/2021
ms.locfileid: "5897888"
---
# <a name="use-external-data-in-cash-flow-forecasts-preview"></a>Külső adatok használata pénzforgalmi előrejelzésekben (előzetes verzió)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

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

#### <a name="privacy-notice"></a>Adatvédelmi nyilatkozat
Az előzetes verziók (1) kevesebb adatvédelmi és biztonsági intézkedést alkalmazhatnak, mint a Dynamics 365 Finance and Operations szolgáltatás (2) és nem vonatkozik a szolgáltatásiszint-szerződés (SLA) ehhez a szolgáltatáshoz, (3) nem használhatók olyan személyes adatok vagy más adatok feldolgozásához, melyekhez törvényi vagy jogszabályi megfelelési követelmények tartoznak, és (4) korlátozott támogatás tartozik hozzá.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]