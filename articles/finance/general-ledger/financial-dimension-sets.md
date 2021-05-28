---
title: Pénzügyi dimenziókészletek
description: Ez a témakör a pénzügyi dimenziókészleteket írja le, és a használatuk optimalizálásához nyújt tippeket.
author: yukonpeegs
ms.date: 03/23/2021
ms.topic: article
ems.prod: ''
ms.technology: ''
ms.search.form: DimensionFocus, LedgerTrialBalanceListPage
audience: Application User
ms.reviewer: roschlom
ms.custom: 25871
ms.search.region: Global
ms.author: epegors
ms.search.validFrom: 2021-03-23
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: ba11be028ebeea140df93e2a07dbb463402e3ef0
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/11/2021
ms.locfileid: "6021828"
---
# <a name="financial-dimension-sets"></a>Pénzügyi dimenziókészletek

[!include [banner](../includes/banner.md)]

Ez a témakör a pénzügyi dimenziókészleteket írja le, és a használatuk optimalizálásához nyújt tippeket.

A dimenziókészlet a pénzügyi dimenziók rendezett listája, amely a főkönyvi adatok felhasználó által definiált módon való összesítéséhez használható. A dimenziókészletek elsődleges használata a főkönyvi kivonat meghatározása.

Az egyetlen normál dimenziókészlet az a dimenziókészlet, amely csak a fő számlát tartalmazza.

A **Pénzügyi dimenziókészletek** lap a pénzügyi dimenziókészletek létrehozására és kezelésére használható.

## <a name="dimension-set-balances"></a>Dimenziókészlet-egyenlegek

A dimenziókészleteknek egyenlege lehet a pénzügyi dimenziók alapján. Az egyenlegek a főkönyvben léteznek, és a dimenziókészlet-definíción alapulnak. Az egyenlegek a főkönyvi adatokból vannak összegezve, ami javítja a beolvasási teljesítményüket (például főkönyvi kivonat létrehozása során).

## <a name="create-balances"></a>Egyenlegek létrehozása

Az **Egyenlegek létrehozása** gombbal inicializálhatja egy olyan dimenziókészlet egyenlegét, amely jelenleg nem rendelkezik egyenlegekkel.

> [!NOTE]
> Javasoljuk, hogy korlátozza az egyenleggel rendelkezik dimenziókészletek számát, mivel az egyenlegek frissítése minden főkönyvi feladási tevékenységet befolyásol.

## <a name="update-balances"></a>Egyenlegek módosítása

Az **Egyenlegek frissítése** gombra kattintva a legutóbbi főkönyvi feladási tevékenységet is beleveheti az egyenlegekbe. Az egyenlegfrissítések világos műveletek. Csak a legutóbbi frissítés óta történt főkönyvi feladási tevékenységet kell feldolgozniuk.

> [!NOTE]
> A főkönyvi kivonatok megjelenítése frissítést kényszerít ki annak a biztosítására, hogy a megjelenített egyenlegek aktuálisak legyenek. Fontolja meg egy ismétlődő kötegelt feladat használatát, hogy gyorsan frissüljenek a leggyakrabban használt dimenziókészletek. Ezzel a módszerrel minimálisra csökkentheti a főkönyvi kivonat felhasználók várakozási idejét.

## <a name="rebuild-balances"></a>Egyenlegek újbóli létrehozása

Az **Egyenlegek újbóli létrehozása** gomb használatával az egyenlegeket a nulláról hozza újra létre. Ily módon gondoskodhatja arról, hogy azok megegyeznek a főkönyvi adatokkal. Az egyenlegek újraépítése rengeteg számítás igényel, és általában nem szükséges.

> [!NOTE]
> Ha olyan forgatókönyve van, amely rendszeresen megköveteli az egyenlegek újraépítését, akkor forduljon az ügyfélszolgálathoz. Az ügyféltámogatás segítségével meghatározható, hogy az egyenlegek miért nem egyeznek meg a főkönyvi adatokkal.

## <a name="clear-balances"></a>Egyenlegek rendezése

Az **Egyenlegek törlése** gombbal eltávolíthatja az egyenlegeket, és leállíthatja a további frissítéseket. A dimenziókészlet már nem lesz hatással a főkönyvi feladási tevékenységekre.

További információért lásd: [Pénzügyi dimenziók](financial-dimensions.md).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
