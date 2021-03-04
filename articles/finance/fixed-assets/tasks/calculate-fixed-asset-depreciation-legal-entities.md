---
title: Tárgyi eszköz értékcsökkenésének kiszámítása jogi személyek között
description: Tárgyi eszköz értékcsökkenése egyetlen lépésben futtatható jogi személyek között.
author: saraschi2
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetParameters, AssetProposalDepreciation, DefaultDashboard, LedgerJournalTable
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 074a1b80584050302920a95c20fb547523a4866c
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4443835"
---
# <a name="calculate-fixed-asset-depreciation-across-legal-entities"></a>Tárgyi eszköz értékcsökkenésének kiszámítása jogi személyek között

[!include [banner](../../includes/banner.md)]

Tárgyi eszköz értékcsökkenése egyetlen lépésben futtatható jogi személyek között. Ez a témakör bemutatja, hogy hogyan állíthatja be és futtathatja több jogi személynél a folyamatot. Ez a könyvelői szerepkört és a bemutató adatokat használja a USMF jogi személyhez.


## <a name="set-up-cross-company-depreciation-run-journals"></a>Vállalatközi vállalati értékcsökkenés-futtatási naplók beállítása
1. Ugorjon a Tárgyi eszközök > Beállítás > Tárgyi eszköz paraméterek pontra.
2. Bontsa ki a tárgyieszköz-javaslatok szakaszt.
3. Kattintson a Hozzáadás gombra.
4. A Feladási réget mezőben adjon meg vagy válasszon ki egy értéket.
5. A Napló neve mezőben adjon meg vagy válasszon ki egy értéket.
    * Ismételje meg a napló beállítását a tárgyi eszköz paraméterei lapon az egyes jogi személyekhez.  

## <a name="depreciation-run"></a>Értékcsökkenés futtatása
1. Ugorjon a Tárgyi eszközök > Naplóbejegyzések > Értékcsökkenési javaslat létrehozása pontra.
2. A Feladási réget mezőben adjon meg vagy válasszon ki egy értéket.
    * A napló neve alapértelmezésben a tárgyi eszköz paramétereiből jön. Itt módosítható az aktuális jogi személyhez.  
3. Adja meg a dátumot a „Záró dátum” mezőben.
    * Válassza ki az értékcsökkenés futtatásába felvenni kívánt jogi személyeket.  
    * A listában csak a tárgyieszköz-javaslatokhoz a tárgyi eszköz paraméterei lapon beállított naplókkal rendelkező jogi személyek fognak megjelenni.  
4. Válassza ki az Igen lehetőséget a Naplók feladása mezőben.
    * A szűrőmezőkbe beletartozik az összes tárgyi eszköz, a csoportok és a könyvek az értékcsökkenési futtatáshoz kiválasztott a jogi személyekhez.  
    * A kötegelt feldolgozási beállítás alapértelmezés szerint engedélyezve van. Ha ez a beállítás engedélyezve van, az értékcsökkenési napló létrehozása és feladása a háttérben fog futni.  
5. Kattintson a Napló létrehozása lehetőségre.
6. Ugorjon a Tárgyi eszközök > Naplóbejegyzések > Tárgyi eszközök naplója pontra.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]