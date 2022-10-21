---
title: Igényvezérelt anyagigény-tervezés (DDMRP) – áttekintés
description: Ez a cikk az igényalapú anyagigény-tervezésről (DDMRP) nyújt tájékoztatást, amely az igények és igények továbbtervezésán alapul.
author: t-benebo
ms.date: 06/30/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2022-06-30
ms.dyn365.ops.version: 10.0.28
ms.openlocfilehash: 31b45fdb92cf8a590ff77104f0c8015fb4d329d5
ms.sourcegitcommit: 3e04f7e4bc0c29c936dc177d5fa11761a58e9a02
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/18/2022
ms.locfileid: "9689488"
---
# <a name="demand-driven-material-requirements-planning-ddmrp-overview"></a>Igényvezérelt anyagigény-tervezés (DDMRP) – áttekintés

[!include [banner](../../includes/banner.md)]
[!INCLUDE [preview-banner](../../includes/preview-banner.md)]
<!-- KFM: Preview until further notice -->

A vállalatok éveken át anyagigény-tervezést (MRP) használnak a termék gyártásához szükséges anyagok és összetevők számításához. Azonban az ellátási lánc megváltozott. Az alkatrészeknek hosszabb az átfutási időük, mert a túlról származó adatforrások. Emiatt sok vállalatnál jelentették, hogy készlettúllépést vagy készlettúllépést tapasztalt, mivel nem tudja, hogy mennyi készlet van készleten. A piaci ingadozások is nagyobbak (időnként nem pontos előrejelzés), és a vevők rövid átfutási idő alatt leigénylik a termékeket. Ebből következően az ellátási láncból hiányok vannak az egész világon belül. Ezenkívül az MRP-eszközök gyakran több ezresnyi műveletet adnak a tervezőnek. Ezért nehéz tudni, hogy mire kell fókuszálni. Gyakran az a megoldás, hogy a problémák nagy része az igényvezérelt anyagigény-tervezésre (DDMRP) vált.

A DDMRP egy olyan tervezési módszertan, amely az ellátás és az igény felfokozásán alapul. Ezt a le- és lecsatolást a pontelemek beállításával lehet elérni. Ezeknél a cikkeknél a pufferek karbantartása gondoskodik arról, hogy a megfelelő készletmennyiséget megtartsa a rendszer. A készlet és az igények összecsatolása segít megakadályozni a "pozitív hatóképességet", mivel a láncon nincs átmenve a variability. (Az *ingadozás* azt jelenti, hogy a kiskereskedelmi szintű igények kis ingadozásai növekvő ingadozásokat okozhatnak a nagykereskedelem, a terjesztő, a gyártó és a nyersanyag-szállítói szinteken.) Az egyes pufferek a rész átlagos használatát fedezik, és igény szerint módosíthatók.

A DDMRP értékes tervezési módszertannak bizonyul a változó környezetekben, ahol a vevők tűréshatára rövidebb a halmozott átfutási időknél.

## <a name="the-five-components-of-ddmrp"></a>A DDMRP öt összetevője

A DDMRP öt egymást követő összetevővel (lépéssel) rendelkezik. Az első három összetevő alapvetően meghatározza egy igényvezérelt anyagkövetelmény-tervezési modell kezdeti és konfigurációs konfigurációját. Az utolsó két összetevő a módszertan napi működését határozza meg.

1. **[Stratégiai készlet pozicionzása](ddmrp-inventory-positioning.md)** – az ellátásilánc-hálózatban a felcsatolási pontok azonosítása. Az időfeltöltési pontok az ellátási lánc meghatározott pontjai, ahol egy készletpuffert lehet berakodni, és figyelni és fel lehet tölteni.
2. **[Pufferprofilok és](ddmrp-buffer-profile-and-levels.md)** szintek – minden egyes felállási pontnál azonosítsa a pufferméreteket (minimális mennyiség, maximális mennyiség és újrarendelési pont) és az újrarendelési mennyiséget.
3. **[Dinamikus pufferhelyesbítások](ddmrp-buffer-profile-and-levels.md#dynamic-adjustments)** – a pufferszintek beállítása különböző üzemi paraméterek vagy tervezett jövőbeli események alapján.
4. **[Igényvezérelt tervezés](ddmrp-planning.md)** – igény szerint generálja az ellátási rendeléseket. Ezek közé tartoznak a gyártási rendelések, a beszerzési rendelések és a készletátviteli rendelések.
5. **[Kifejezetten veszélyes és látható végrehajtás](ddmrp-visual-and-collaborative-execution.md)** – az ellátási rendelések futtatása a megjelenítés segítségével.

A DDMRP-t jellemzően olyan gyártók használják, amelyek többszintű anyagjegyzéket tartalmaznak. Ugyanakkor elosztásra és kiskereskedelmi hálózatokra is alkalmazható.

## <a name="ddmrp-in-dynamics-365-supply-chain-management"></a>DDMRP be Dynamics 365 Supply Chain Management

A DDMRP a Microsoft Dynamics 365 Supply Chain Management része, ezért nem igényel további licencdíjakat. Az Ellátásilánc-kezelés modul DDMRP-funkciói hozzá vannak adva a meglévő alaptervezési **modulhoz**. Ehhez azonban a Tervezési optimalizálási bővítményt kell használni. 

A DDMRP integrálva van az Ellátásilánc-kezelés meglévő tervezési beállításaival, és a beállításokkal együtt használatos arra, hogy a vállalat megfelelő tervezési konfigurációját megossa. Ezt egy olyan új fedezeti kód vezérli, amely teljesen különbözik az időszaktól, a minimumtól, a követelménytől stb. Ez nem egy új modul, és nem cseréli le a meglévő tervezési funkciókat. Ugyanakkor további funkciókat is biztosít a használathoz.
