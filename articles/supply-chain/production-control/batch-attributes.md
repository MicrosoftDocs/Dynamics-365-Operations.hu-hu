---
title: Kötegattribútumok
description: Ez a cikk a kötegattribútumokkal kapcsolatban tartalmaz információkat. A kötegattribútumok a nyersanyagok és a késztermékek jellemzői, amelyek készletkötegeket alkotnak. A cikk bemutatja továbbá a kötegattribútumok társítását, és hogy a kötegek lefoglalásánál hogyan kereshet rájuk.
author: johanhoffmann
ms.date: 11/03/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: PdsBatchAttrib, PdsBatchAttribAssociate, PdsBatchAttribByAttribGroup, PdsBatchAttribByItem, PdsBatchAttribByitemCustomer, PdsBatchAttribGroup, WHSBatchAttribReserve
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19271
ms.assetid: 41de0250-4a96-412e-a412-aa06615b6b1d
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e5f5a03df63cf4fa90b5e9e67082a0d60eef9afc
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8899382"
---
# <a name="batch-attributes"></a>Kötegattribútumok

[!include [banner](../includes/banner.md)]

Ez a cikk a kötegattribútumokkal kapcsolatban tartalmaz információkat. A kötegattribútumok a nyersanyagok és a késztermékek jellemzői, amelyek készletkötegeket alkotnak. A cikk bemutatja továbbá a kötegattribútumok társítását, és hogy a kötegek lefoglalásánál hogyan kereshet rájuk.

A kötegattribútumok a nyersanyagok és a késztermékek jellemzői, amelyek készletkötegeket alkotnak. A kötegattribútumok különbözhetnek olyan tényezők tekintetében, mint a környezeti tényezők, a köteg előállításához használt nyersanyagok minősége, vagy a késztermék eredménye. A használt szám és kötegattribútumok-típusok is jelentősen eltérhetnek iparáganként. Az alábbiakban két példák, illusztrálja, hogy hogyan kell használni a kötegattribútumokat:

-   A sajt iparágban a tej, amely a sajt előállításához használt nyersanyagok közé tartozik, különböző jellemzőkkel bír, mint pl. zsírtartalom és százalékos súly. A tejből előállított sajt más attribútumokkal rendelkezhet, például a nedvesség és a kor.
-   Az acéliparban a létrehozott vas olyan attribútumokkal rendelkezhet, mint a magnéziumtartalom, ezüsttartalom, és cinktartalom százalékos aránya.

Az attribútumok számának és típusainak jobb kezelése érdekében használhatja a kötegattribútum-csoportokat. Ezzel a módszerrel nem kell külön-külön hozzáadnia az egyes attribútumokat.

## <a name="assign-batch-attributes"></a>Kötegattribútumok hozzárendelése
Kötegattribútumokat hozzárendelhet az egyes termékekhez, amelyeket készletkötegekben tartanak, vagy hozzárendelheti őket meghatározott vevőkhöz kapcsolódó termékekhez. Mielőtt hozzárendel egy kötegattribútumot a vevő szintjén, a termék szintjén kell hozzárendelnie. A terméknek kell rendelkeznie egy kötegdimenzió-készlettel, amely az **Aktív** lehetőségre van állítva a nyomonkövetési dimenziócsoportban. Használja a termékspecifikus lapot, ha kötegattribútum-csoportot akar hozzárendelni az egyes termékekhez. Ha az attribútum meghatározott vevőhöz tartozó termékre jellemző, akkor a vevőre jellemző lapot kell használni. Attribútum hozzáadásakor egy termékhez megadhat egyéb paramétereket is. Íme néhány példa:

-   Egy attribútum maximális és minimális értékei az **Egész** vagy **Rész** típusban.
-   Az attribútum tűréshatárának műveletei az **Egész** vagy **Tört** típusban. Ha az attribútum értéke a minimális és maximális tartományon kívül esik, a művelet lehet figyelmeztetés vagy hibaüzenet.
-   Az attribútum célértéke. Ez az érték az attribútum optimális értéke, és minden attribútumtípusra vonatkozik.

Hozzáférhet a kiválasztott termékek lapjaihoz, ha a **Felszabadított termékek** oldalon kiválasztja a Termékinformációk kezelése lehetőséget. Miután hozzárendelte kötegattribútumokat egy termékhez, akkor hozzáadhat adott értékeket az attribútumokhoz a **Készletköteg-attribútumok** oldalon.

## <a name="reserve-batches"></a>Kötegek foglalása
Rákereshet kötegattribútumokra amikor egy vásárlói rendelés kielégítéséhez kötegfoglalásokat végez egy értékesítési rendeléshez, de egy termelési rendeléshez való kötegkitárolás és -foglalás esetén is megteheti ezt. A keresés segítségével keresse meg a készletköteget, amely tartalmazza a terméket, amely rendelkezik a kívánt kötegattribútummal. A köteg- vagy kötegek megtalálása után lefoglalhatja a terméket a származó készlet-tranzakciósorba.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]