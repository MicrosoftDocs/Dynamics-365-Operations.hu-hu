---
title: Dokumentumok és bizonylatok időrendi számozása
description: Ez a témakör bemutatja, hogyan állíthatja be és használhatja az időrendi számozást az alkalmazandó dokumentumok és a kapcsolódó bizonylatok esetében.
author: ikond
ms.date: 02/01/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: NumberSequenceGroup
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 401195
ms.search.region: Global
ms.author: ilyako
ms.search.validFrom: 2021-03-15
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: ced09fb4be49dbfd10dac9f9ece86372d38e854460c7ca6cd72922c64ac7cce4
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6724135"
---
# <a name="numbering-documents-and-vouchers-chronologically"></a>Dokumentumok és bizonylatok időrendi számozása

[!include [banner](../includes/banner.md)]


Egyes országokban kötelező a dokumentumok és a kapcsolódó bizonylatok időrendi számozása. Az időszakoknak támogatniuk kell az időrendet. Minden korábbi időszakhoz tartozó számnak kisebbnek kell lennie a későbbi időszakokhoz tartozó számoknál. Ennek a követelménynek megfelelően időrendi számozási funkciókat hajtottunk végre. Ez a témakör bemutatja, hogyan konfigurálhatja és használhatja az időrendi számozást az alkalmazandó dokumentumok és a kapcsolódó bizonylatok esetében.

## <a name="prerequisites"></a>Előfeltételek

A Funkciókezelés munkaterületen kapcsolja be az **Időrendi számozás** funkciót. További tájékoztatás: [Funkciókezelés – áttekintés](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

## <a name="configure-chronological-numbering"></a>Időrendi számozás konfigurálása

Az időrendi számozás a következő dokumentumokat érinti.

**Kinnlevőségek**
- Vevői számla
- Vevői számlabizonylat
- Értékesítési jóváírás
- Értékesítési jóváírás-bizonylat
- Szabadszöveges számla
- Szabadszövegű számlabizonylat
- Szabadszövegű jóváírás
- Szabadszövegű jóváírás-bizonylat
- Szállítólevél
- Szállítólevél bizonylata
- Szállítólevél korrekciós bizonylata
- Kamatlevél bizonylata
- Fizetési felszólítás bizonylata

**Kötelezettségek**
- Számlabizonylat
- Jóváírás bizonylata
- Termékbevételezési bizonylat

**Projektvezetés**
- Számla
- Számlabizonylat
- Jóváírás
- Jóváírás bizonylata 

### <a name="define-number-sequences"></a>Számsorozatok meghatározása

Számsorozatok meghatározásához lépjen a **Szervezeti adminisztráció** > **Számsorozatok** > **Számsorozatok** lehetőségre. Annyi számsorozatot adhat meg, amennyi csak szükséges a szükséges dokumentumok érintett periódusainak lefedéséhez. 

Minden számsorozathoz adjon meg egy vállalatot. A számsorozatok szegmenseit úgy kell meghatározni, hogy az időszakok időrendi sorrendben jelenjenek meg. A szegmensnevek tartalmazhatnak például egy speciális előtagot, amely az adott időszakot azonosítja.

![Számsorozat beállítása.](media/chrono-num-sequence.jpg)

### <a name="configure-number-sequence-groups"></a>Számsorozatcsoportok konfigurálása

A számsorozatcsoportok konfigurálához kattintson a **Kinnlevőségek** > **Beállítás** > **Kinnlévőségek paraméterei** gombra. A **Számsorozatok** lapon definiálja az érintett időszakok fedezésére szükséges számsorozatcsoportokat. 

Mindegyik csoportnál a **Hivatkozás** szakaszban válassza ki a támogatott dokumentumhivatkozások valamelyikét, és a **Számsorozatkód** mezőben hivatkozzon egy, a kapcsolódó időszakhoz korábban létrehozott számsorozatra.

![Sorozatszámcsoport beállítása.](media/chrono-num-sequence-group.jpg)

Ehhez hasonlóan állítsa be a számsorozatcsoportokat a **Kötelezettségek** és a **Projektvezetés és könyvelés** modulban is.

### <a name="configure-number-sequence-groups-chronology"></a>Számsorozatcsoportok konfigurálásának időrendje

A számsorozatcsoportok időrendi konfigurációját a **Szervezeti adminisztráció** > **Számsorozatok** > **Időrendi számsorozatcsoportok** pontban állítsa be. Határozza meg a számsorozatcsoportok alkalmazhatósági feltételeit.

![Időrendi számok beállítása.](media/chrono-num-sequence-group-period.jpg)

| Mező            | Leírás                                                                                                                                                                                                                                                                                                                                                                                   |
|---------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Érvénybe lépés  | A számsorozatcsoport alkalmazhatóságának kezdő dátuma. |
| Lejárat      | A számsorozatcsoport alkalmazhatóságának záró dátuma. Ha nem alkalmaz záró dátumot, válassza a **Soha** lehetőséget. |
| Számsorozatcsoport | Az a számsorozatcsoport, amelyet a bizonylatszámok előállításához használ az adott időszakban. |
| Eredeti számsorozatcsoport | A rendszer ezt a számsorozatcsoport-kódot használja az olyan esetek további szűrésére, amikor a dokumentumokhoz már hozzá van rendelve egy konkrét *állandó* számsorozatcsoport. Az üres érték konkrét értéknek számít. Ha figyelmen kívül kell hagynia egy előzetes hozzárendelt csoportot, használja az **Alapértelmezett** lehetőséget ehhez a beállításhoz. |
| Alapértelmezett | Ha be van kapcsolva, a rendszer figyelmen kívül hagyja az előzetes hozzárendelt dokumentumszám-sorozatcsoportot, és csak az időszakok kezdő és záró dátumát használja az alkalmazhatósági elemzéshez. Ha ki van kapcsolva, a rendszer a kijelöléshez a **Hatályos** + **Lejárat** + **Eredeti számsorozatcsoport** teljes kombinációját használja. |

## <a name="document-posting"></a>Dokumentum feladása
Dokumentum feladásakor a program a dokumentum feladási dátuma alapján hozzárendeli a megfelelő számsorozatcsoportot a dokumentumhoz, majd az észlelt számsorozaton alapuló dokumentumszám előállítására használja. A rendszer üzenetet küld a számsorozatcsoport hozzárendelésével kapcsolatban.

![Bizonylat száma.](media/chrono-num-sequence-fti.jpg)

> [!NOTE]
> Egyes országokban már létezik a dokumentumszámozáshoz meghatározott logika. Ebben az esetben az országspecifikus logika felülbírálja az **Időrendi számozás** funkciót.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
