---
title: Költségváltozások szimulálása, a tervezett költségek költségszámítási verziójának alkalmazásával
description: Ez a cikk azt mutatja be, hogy hogyan szimulálhatja a költségmódosítások hatásait egy termék kiszámított költségein egy külön költségszámítási verzió alkalmazásával a tervezett költségekre vonatkozóan.
author: AndersGirke
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CostingVersion
audience: Application User
ms.reviewer: kamaybac
ms.custom: 78183
ms.assetid: 1e41953f-cdb9-4598-b776-46e49383a773
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e288a5f00e43901ba1bf6ec50f460be4b62ea2db73adbaf0f9204c988e812f58
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6781561"
---
# <a name="simulate-cost-changes-by-using-a-costing-version-for-planned-costs"></a>Költségváltozások szimulálása, a tervezett költségek költségszámítási verziójának alkalmazásával

[!include [banner](../includes/banner.md)]

Ez a cikk azt mutatja be, hogy hogyan szimulálhatja a költségmódosítások hatásait egy termék kiszámított költségein egy külön költségszámítási verzió alkalmazásával a tervezett költségekre vonatkozóan.

Szimulálhatja a költségmódosítások hatásait egy termék kiszámított költségein egy külön költségszámítási verzió alkalmazásával a tervezett költségekre vonatkozóan. Használja ezt a külön költségszámítási verziót az olyan függő költségrekordok bevitelére, amelyek növekményes költségváltozásokat tükröznek, illetve a termékekre ható költségek kiszámítására. Mivel az aktív költségek tartalékelvét használják az anyagjegyzék-számításokban (BOM), csak a növekményes költségváltozókat kell megadni.

## <a name="guidelines-for-defining-the-simulation-costing-version"></a>A szimulált költségszámítási verzió meghatározására vonatkozó irányelvek
Alkalmazza az alábbi útmutatásokat a szimulációra vonatkozó költségszámítási verzió meghatározásakor.

-   **Tervezett költségek** költségszámítási típusának hozzárendelése.
-   Rendeljen hozzá egy felismerhető azonosítót a költségszámítási verzióhoz, mint például **Szimuláció**.
-   Győződjön meg róla, hogy a tartalomban szerepelnek költségrekordok.
-   Engedélyezze a költségrekordok bevitelét. Ne tiltsa le a függő költségek bevitelét.
-   Engedélyezze a költségrekordok bevitelét minden hely esetében. Ha meghatároz egy helyet, azzal korlátozza a költségrekordok bevitelét arra a helyre.
-   Akadályozza meg a függő költségek aktiválását. Csak a függő költségeket kell megadni a költségrekordok vonatkozóan a a szimulációs költségszámítási verzióban.
-   Ne adjon meg "kezdő" dátumot. Egy számítási dátum lesz beírva minden egyes anyagjegyzékhez, amely a szimulációs költségszámítási verziót használja.
-   Határozza meg a **Jelenleg aktív** tartalékelvét. A tartalékelv lehetővé teszi szimulációs célból a növekvő költségváltozások megadását, de az aktuális aktív költségeket az összes többi költségrekord forrásaként alkalmazza. Feltételezzük, hogy az aktuális aktív költségek léteznek az összes többi költségrekordra vonatkozóan.
-   Határozza meg a **Verzió önköltségi ára** önköltségiár-modelljét, de ne korlátozza a számításokat. Például a szimulációk alkalmazhatják az **Anyagjegyzék-számítási csoport** önköltségiár-modelljét a beszerzett cikkek költség-hozzájárulás adatainak forrásmegjelölésére.
-   Határozzon meg egy **Többszintű** alábontási módot, de ne korlátozza a számításokat. A szimulációk másik alábontási módokat is használhatnak.

## <a name="costing-versions"></a>Költségszámítási verziók
A következő esetek azt mutatják be, hogy hogyan alkalmazzák a szimulációs költségszámítási verziót a költségváltozások kihatásának szimulációjára. Egy szimulált költségváltozás megadása előtt törölje a függő költségrekordokat a szimulációs költségszámítási verzióban, hogy egy tiszta indulási pontot képezzen. Használja a **Cikk ára** képernyőt azon függő költségrekordok megtekintéséhez és törléséhez, amelyek cikkárakhoz és költségkategória-árakhoz tartoznak.

-   Szimulálja egy alapanyag költségváltozását. Például a költségváltozás lehet, hogy a várható növekedést vagy csökkenést tükrözi a kritikus alapanyagok költségében. Használja a **Cikk ára** képernyőt egy függő költségrekord megadására a szimulációs költségszámítási verzióban a különböző költség meghatározásához egy beszerzett cikkre vonatkozóan.
-   Szimulálja egy költségkategória költségváltozását. Például a költségváltozás várható növekedést vagy csökkenést tükrözhet a műhelyek munkadíjaiban vagy óradíjaiban az üzemi erőforrásokra vonatkozóan. Használja a **Költségkategória ára** képernyőt egy függő költségrekord megadására a szimulációs költségszámítási verzióban az eltérő költség meghatározására egy költségkategóriára vonatkozóan.
-   Szimulálja a költségváltozását egy közvetett költségszámítási képletben. Például a költségváltozás növekedést vagy csökkenést tükrözhet a gyártási többletköltségben. Használja a **Költségszámítási táblázat beállítása** képernyőt egy függő költségrekord megadására a szimulációs költségszámítási verzióban, és a változás ellenőrzésére és mentésére egy közvetett költségszámítási képletben szereplő eltérés meghatározásához.

A szimulált költségváltozások megadása után számítsa ki a költségváltozások által érintett termékek költségeit. Használja az **Számítás** képernyőt a szimulációs költségszámítási verzióhoz, és azonosítsa be a termékek azon csoportját, amelyekre kihatással lesznek a költségváltozások. Az anyagjegyzék-számítások csak akkor vonatkoznak minden termékre, ha kiválasztja a konkrét cikkeket. Másik megoldásként alkalmazhatja az anyagjegyzék-számítás lehetőséget azokra a frissítésekre, ahol azok használtban vannak. Tekintse meg a cikk költségrekordjait a szimulációs költségszámítási verzióban, hogy megvizsgálja hogyan hatottak a megadott termékek költségeire a szimulált költségváltozások. Használja a **Cikkár** lapot és a **Cikk-költség kiszámítása** lapot a költségek megtekintéséhez és elemzéséhez.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]