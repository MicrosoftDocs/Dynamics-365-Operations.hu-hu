---
title: Beszerzésirendelés-sor adateltérásai
description: A beszerzési rendelés sorai adateltéreket vagy adatsérüléseket is látnak.
author: SmithaNataraj
ms.date: 12/07/2021
ms.topic: troubleshooting
ms.search.form: PurchLineManualCorrection, PurchTable, PurchLine, InventTrans
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-12-07
ms.dyn365.ops.version: 10.0.24
ms.openlocfilehash: ee2cb9a07c8a00a92c71e3e99d8ec20aa27fb20e
ms.sourcegitcommit: b9799a58d6ec221df86788bc37c4fbd28b435e89
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/08/2022
ms.locfileid: "8100781"
---
# <a name="purchase-order-line-data-discrepancies"></a>Beszerzésirendelés-sor adateltérásai

## <a name="symptoms"></a>Tünetek

Amikor megvizsgálja egy beszerzési rendelés sorait, a következő problémákat veszi észre:

- Adateltérás vagy sérülés van a beszerzési rendelési sorok fennmaradó részében (szállítás vagy számla).
- Sérülés van egy beszerzésirendelés-sorban vagy fejlécállapotban.
- Beszerzési rendelésről nem lehet számlát kiszámlázni, mert például a következő hibaüzenetek közül kap egyet:

    - "Leállítva (hiba): A tranzakció már fel lett adva."
    - "A mennyiség nem számlázható, mert nincs elegendő Bevételezés állapotú készlettranzakció."
    - "Nincs elegendő "Beszerzett" állapotú készlettranzakció a cikkmennyiséghez %0%1."

- Beszerzési rendelést nem véglegesíthet vagy nem zárhat le, például a következő problémák valamelyike miatt:

    - A **Véglegesíteni** gomb nem érhető el.
    - Visszaigazolt és bevételt állapotban álló beszerzési rendelés esetén nem érvénytelenheti a beszerzésirendelés-sor megrendelt mennyiségét.

## <a name="cause"></a>Ok

Ezeket a problémákat általában adatsérülés, illetve egy vagy több beszerzésirendelés-sor fennmaradó mennyiségének eltérése okozza.

## <a name="resolution"></a>Megoldás

Ezeket a problémákat általában a megfelelő beszerzésirendelés-sorok beszerzési állapotának, szállítási maradványának és/vagy számla-maradványának frissítésével lehet kijavítani, az alábbi eljárás szerint.

1. Ugrás a Beszerzés **és forrás időszakos feladatok \>\> – Helyes beszerzésirendelés-sorok \> manuális tisztítása**.
1. A Beszerzési **rendelés mezőben** keresse meg és válassza ki azt a beszerzési rendelést, amely problémát okoz.
1. A Beszerzési **rendelés sorai szakaszban** válasszon ki egy sort, amelyben eltérést talált.
1. A Készlettranzakciók **szakaszban** vizsgálja meg a megjelenő adatokat. Ha a beszerzési rendelési sorok és a készlettranzakciók között ellentmondást lát, a következő parancsok közül választhat a munkaablakban, attól függően, hogy hol látja az inkonzisztenciát:

    - **Fennmaradó szállításának újraszámítása \>** – automatikusan frissíti a beszerzési rendelés sorát és a fejléc állapotát. Ez a funkció csak a raktárkészletbe adott beszerzésirendelés-soroknál működik (azok a sorok, amelyekben a cikk raktárott cikk). A nem készleten lévő cikkek és a "catch weight" cikkek jelenleg nem támogatottak.
    - **Számla-maradvány \> újraszámítása** – a beszerzési rendelési sorok és a fejlécek állapotának automatikus frissítése. Ez a funkció csak a raktárkészletbe adott beszerzésirendelés-soroknál működik (azok a sorok, amelyekben a cikk raktárott cikk). A nem készleten lévő cikkek és a "catch weight" cikkek jelenleg nem támogatottak.
    - **Az újraszámítás állapota \>** – a kiválasztott sor állapotának újraszámítása. A számítás a meglévő logikán alapul. Ennek megfelelően a beszerzési rendelés fejlécének állapota szükség szerint frissül az új beszerzésirendelés-sor állapota alapján.

1. Ha továbbra is inkonzisztenciát lát a fennmaradó mennyiségekben, a következő mezők segítségével szükség esetén közvetlenül szerkesztheti őket:

    - Fennmaradó szállítása
    - Fennmaradó készlet szállítása
    - Számlahátralék
    - Készletkezelés számlahátraléka
