---
title: Tervezés negatív tényleges készleten lévő mennyiségekkel
description: Ez a témakör azt mutatja be, hogy hogyan kezeli a program a negatív aktuális készletet a tervezés optimalizálása során.
author: ChristianRytt
ms.date: 07/22/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2020-02-18
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: 97688e09aae9706dd85e7965aa08c7ea873a44d81391c39406e2e6367660e0d0
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6758544"
---
# <a name="planning-with-negative-on-hand-quantities"></a>Tervezés negatív tényleges készleten lévő mennyiségekkel

[!include [banner](../../includes/banner.md)]

Ha a rendszer negatív összesített tényleges mennyiséget mutat, akkor a tervezési motor a mennyiséget 0 (nulla) értékkel kezeli a túlszállítás elkerülésére. Ez a funkció működése:

1. A tervezés optimalizálása funkció összesíti az aktuális készleten lévő mennyiségeket a fedezeti dimenziók legalacsonyabb szintjén. (Ha például a *hely* nem fedezeti dimenzió, akkor a tervezés optimalizálása a *raktár* szintjén összesíti az aktuális készleten lévő mennyiségeket.)
1. Ha negatív a fedezeti dimenziók legalacsonyabb szintjén levő összesített aktuális mennyiség, a rendszer azt feltételezi, hogy az aktuális készlet mennyisége valóban 0 (nulla).

> [!IMPORTANT]
> A tervezési rendszer csak akkor lehet pontos, mint a bemeneti adat. Ha a bemeneti adatok pontatlanok, akkor a negatív tényleges készlet rekordok azt jelzik, hogy a Microsoft Dynamics 365 Supply Chain Management szolgáltatásban lévő készlet adatai nincsenek harmóniában a valós világgal. Ezért a tervezés eredménye hibás lesz. A pontos tervezési eredmény érdekében minimalizálni kell azokat a rekordokat, amelyek negatív aktuális mennyiséget jelenítenek meg.

## <a name="example-1"></a>1. példa

A 13. raktár konfigurálása a következő módon történik:

- **Fedezeti kód:** Min./Max.
- **Minimum:** 15 darab (db)
- **Maximum:** 25 db.

A fedezeti dimenziók legalacsonyabb szintje a *raktár*, és a következő aktuális mennyiségeket rögzíti a rendszer a *hely* szintjén:

- **1. telephely, 13. raktár, 1. hely:** 20 db.
- **1. telephely, 13. raktár, 2. hely:** &minus;8 db.

Ennek megfelelően a 13. raktár összesített tényleges mennyisége 12 db. (= 20 db. &minus; 8 db.).

Ebben az esetben a tervezési motor az összesített 12 darabos aktuális készletet használja a 13. raktárhoz.

Az eredmény 13 darabból álló tervezett rendelés. (= 25 db. &minus; 12 db.) a 13. raktár újratöltése 12 darabról 25 darabra.

## <a name="example-2"></a>2. példa

A 13. raktár konfigurálása a következő módon történik:

- **Fedezeti kód:** Min./Max.
- **Minimum:** 15 db.
- **Maximum:** 25 db.

A fedezeti dimenziók legalacsonyabb szintje a *raktár*, és a következő aktuális mennyiségeket rögzíti a rendszer a *hely* szintjén:

- **1. telephely, 13. raktár, 1. hely:** 4 db.
- **1. telephely, 13. raktár, 2. hely:** &minus;8 db.

Ennek megfelelően a 13. raktár összesített tényleges mennyisége &minus;4 db. (= 4 db. &minus; 8 db.). Azaz kevesebb, mint 0 (nulla).

Ebben az esetben a tervezési motor feltételezi, hogy a 13. raktár aktuális készlete 0 db. &minus;4 db helyett.

Az eredmény 25 darabból álló tervezett rendelés. (= 25 db. &minus; 0 db.) a 13. raktár újratöltése 0 darabról 25 darabra.

## <a name="planning-when-there-is-a-reservation-against-negative-on-hand-inventory"></a>Tervezés negatív aktuális készletre vonatkozó foglalás esetén

Ha úgy módosítja a készletet, hogy közben tényleges foglalások vannak, olyan helyzet alakulhat, amikor egy rendelés ténylegesen le lesz foglalva a negatív készletből. Ebben az esetben fizikai foglalás létezik, ezért a Tervezési optimalizálás azt feltételezi, hogy az aktuális készlet támogatja azt, még akkor is, ha az aktuális készlet bevételezése még nincs regisztrálva a rendszerben. Ebből következően azt feltételezi, hogy a feltöltés nem szükséges, és nem hoz létre tervezett rendelést a rendelés mennyiségének feltöltéséhez.

Az alábbi forgatókönyv ezt a példát ábrázolja.

### <a name="example"></a>Példa

A rendszer a következő módon van konfigurálva:

- Az *FG* termék létezik és *10* db van belőle. aktuális készleten.
- A termékkonfiguráció lehetővé teszi a tényleges negatív készletet.
- *10* db. mennyiségre van egy értékesítési rendelés Az *FG* termékből.
- Az értékesítési rendelés mennyisége ténylegesen le van foglalva a meglévő aktuális készlettel szemben.

Ezután módosítja az *FG* termék mennyiségét úgy, hogy az aktuális készlet 0 (nulla) legyen. Mivel az aktuális termékkészlet nulla, az értékesítési rendelés mennyisége most negatív készlettel szemben lesz lefoglalva. Ha azonban most futtatja az alaptervezést, nem jön létre tervezett rendelés az értékesítési rendelés ellátásához, mivel a Tervezési optimalizálás feltételezi, hogy a tényleges foglaláshoz szükséges aktuális készlet létezik.

## <a name="related-resources"></a>Kapcsolódó erőforrások

- [Tervezési optimalizálás áttekintése](planning-optimization-overview.md)
- [A Tervezési optimalizálás kezdő lépései](get-started.md)
- [A tervezésoptimalizálása illeszkedési elemzése](planning-optimization-fit-analysis.md)
- [Tervelőzmények és tervezési naplók megtekintése](plan-history-logs.md)
- [Tervezési feladat érvénytelenítése](cancel-planning-job.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
