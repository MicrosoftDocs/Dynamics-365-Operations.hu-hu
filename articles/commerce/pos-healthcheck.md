---
title: Állapotellenőrzés pénztárperifériákhoz és -szolgáltatásokhoz
description: Ez a cikk áttekintést nyújt a pénztári állapotellenőrzési műveletről.
author: BrianShook
ms.date: 03/06/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: 141393
ms.assetid: e23e944c-15de-459d-bcc5-ea03615ebf4c
ms.search.region: Global
ms.search.industry: Retail
ms.author: brshoo
ms.search.validFrom: 2019-03-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 44fd4b6246d3d7947527416c2b8b447bd64f179f
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8863321"
---
# <a name="health-check-for-pos-peripherals-and-services"></a>Állapotellenőrzés pénztárperifériákhoz és -szolgáltatásokhoz

[!include [banner](includes/banner.md)]

Ez a témakör a pénztár állapotellenőrzési műveletét írja le.

## <a name="overview"></a>Áttekintés

A kiskereskedelmi üzletek összetett környezetek lehetnek, ahol számos alkalmazást és eszközt használnak. A műveletek növekedésével nehéz lehet biztosítani, hogy a műveletek mindig simán fussanak, például az olyan perifériákkal kapcsolatos függőségek miatt, amelyek elromolhatnak vagy véletlenül kihúzódhatnak. Az eszközökhöz és szolgáltatásokhoz kapcsolódó hibaelhárítás a nagyobb kereskedők számára drága lehet, és ugyanilyen bosszantó a kisebb szervezeteknél.

A Microsoft Dynamics 365 Commerce 10.0.10 és újabb verziói egy olyan állapotellenőrző művelettel is rendelkeznek, amely segít részben elkerülni ezeket a költségeket és frusztrációkat. Ez a művelet módszert biztosít az eszközök normál üzemen kívüli tesztelésére közvetlenül a pénztárból. Ezért a kiskereskedők számára segítséget jelenthet a problémák felderítésében azok kialakulása előtt.

## <a name="key-terms"></a>Kulcsfogalmak

| Időszak | Leírás |
|---|---|
| Perifériák | Minden olyan eszköz, amelyet a pénztári alkalmazás használ az üzlet tranzakcióinak és egyéb műveleteinek megkönnyítésére. Ilyenek például a pénztárgépfiókok, a vonalkód-olvasók és a fizetőterminálok. |
| Szolgáltatás | Ebben a cikkben a szolgáltatás kiegészítő alkalmazás, amely a tranzakciók és a napi műveletek elvégzésétől függ. Ilyenek például az adó-és a szállítási számításokat segítő alkalmazások. |

## <a name="health-check-operation"></a>Állapotfelmérés művelet

Az állapotfelmérés művelet a Commerce Headquarters **POS-műveletek** lapjának 717-es művelete. Ez a módszer akkor használható, ha a pénztár nem fiókos módban van. A hardverállomásnak azonban aktívnak kell lennie.

Alapértelmezés szerint az állapotfelmérési ellenőrzések csak azokat az eszközöket vizsgálják át, amelyek konfigurálva vannak annak a hardverállomásnak a profiljában, amely jelenleg aktív a kasszához. Ha egy kassza több hardvereszközt használ a nap folyamán, akkor az összesre vonatkozó állapotellenőrzéshez egyszerre egy hardverállomáshoz kell kapcsolódnia. Nincs üzletszintű állapotellenőrzés. Előfordulhat azonban, hogy az ilyen típusú ellenőrzés elvégezhető a Commerce Server bővíthetőségével.

### <a name="out-of-box-health-checks"></a>„Gyári” állapotellenőrzések

| Típus | Kapcsolat | Részletek |
|---|---|---|
| Nyomtató | OPOS | Ez a teszt a POS (OPOS) funkciókhoz kapcsolódó alapvető objektum csatolásokat és beágyazásokat ellenőrzi. Íme néhány példa:<ul><li>Megnyitás **Open** &gt; **ClaimDevice** &gt; **DeviceEnabled=True**</li><li>Bezárás: **DeviceEnabled=False** &gt; **ReleaseDevice** &gt; **Close**</li></ul> |
| Sor megjelenítése | OPOS | Ez az ellenőrzés a OPOS alapvető funkcióit vizsgálja. Íme néhány példa:<ul><li>Megnyitás **Open** &gt; **ClaimDevice** &gt; **DeviceEnabled=True**</li><li>Bezárás: **DeviceEnabled=False** &gt; **ReleaseDevice** &gt; **Close**</li></ul> |
| Két kijelző | Windows | Ez az ellenőrzés biztosítja, hogy az operációs rendszer egy másik Windows-kijelzőt észlel-e. | 
| MSR | OPOS | Ez az ellenőrzés a OPOS alapvető funkcióit vizsgálja. Íme néhány példa:<ul><li>Megnyitás **Open** &gt; **ClaimDevice** &gt; **DeviceEnabled=True**</li><li>Bezárás: **DeviceEnabled=False** &gt; **ReleaseDevice** &gt; **Close**</li></ul> |
| Fiók | OPOS | Ez az ellenőrzés a OPOS alapvető funkcióit vizsgálja. Íme néhány példa:<ul><li>Megnyitás **Open** &gt; **ClaimDevice** &gt; **DeviceEnabled=True**</li><li>Bezárás: **DeviceEnabled=False** &gt; **ReleaseDevice** &gt; **Close**</li></ul> | 
| Leolvasó | OPOS | Ez az ellenőrzés a OPOS alapvető funkcióit vizsgálja. Íme néhány példa:<ul><li>Megnyitás **Open** &gt; **ClaimDevice** &gt; **DeviceEnabled=True**</li><li>Bezárás: **DeviceEnabled=False** &gt; **ReleaseDevice** &gt; **Close**</li></ul> | 
| Mérleg | OPOS | Ez az ellenőrzés a OPOS alapvető funkcióit vizsgálja. Íme néhány példa:<ul><li>Megnyitás **Open** &gt; **ClaimDevice** &gt; **DeviceEnabled=True**</li><li>Bezárás: **DeviceEnabled=False** &gt; **ReleaseDevice** &gt; **Close**</li></ul> |
| PIN-billentyűzet | OPOS | Ez az ellenőrzés a OPOS alapvető funkcióit vizsgálja. Íme néhány példa:<ul><li>Megnyitás **Open** &gt; **ClaimDevice** &gt; **DeviceEnabled=True**</li><li>Bezárás: **DeviceEnabled=False** &gt; **ReleaseDevice** &gt; **Close**</li></ul> |
| Fizetési terminál | Fizetések SDK | Ez az ellenőrzés a Fizetési SDK által nyújtott alapvető fizetőterminál-funkciókat ellenőrzi. <ul><li>Zárolás</li><li>BeginTransaction</li><li>EndTransaction</li><li>ReleaseDevice</li><li>Zárás</li></ul> |

### <a name="using-the-health-check-operation-in-the-pos"></a>Az állapotfelmérés művelet használata a pénztárban

Amikor az állapotellenőrzés műveletet kezdeményezik a pénztárban a jobb oldali ablaktábla felsorolja a konfigurált eszközöket, és megjeleníti az egyes eszközök állapotát. Egyetlen eszköz állapotának ellenőrzéséhez válassza ki az eszközt, majd válassza a **Kijelölt ellenőrzése** elemet. Az összes eszközhöz tartozó állapotfelmérés végrehajtásához válassza az **Összestesztelése** lehetőséget. Az **Összes tesztelése** funkció az összes eszközt teszteli egyszerre, és frissíti az összes eszköz állapotát az **Állapot** oszlopban.

Az **Utolsó ellenőrzés** oszlop azt jeleníti meg, hogy az egyes eszközök esetében mikor történt meg utoljára az állapotfelmérés.

Ha egy eszközhöz tartozó állapotfelmérés sikeres (azaz ha nem fordul elő hiba), az eszköz állapota **OK** lesz. Ha nem sikerül az állapotellenőrzés, akkor az állapot azt jelzi, hogy hiba történt. Ebben az esetben a jobb oldali ablaktábla a hibával kapcsolatos részleteket jelenít meg, vagy utasítja a felhasználót, hogy forduljon a rendszergazdához.

Néhány eszköz – például az OPOS-billentyűzár – nem rendelkezik gyári állapotellenőrző tesztekkel. Ha egy használt eszköz esetében nem észlelhető egy állapotfelmérés-teszt, akkor az állapot **Nem támogatott** lesz.

### <a name="extending-health-checks"></a>Az állapotellenőrzések kiterjesztése

A gyári állapotfelmérő tesztek úgy vannak beállítva, hogy a jellemző hibákhoz felhasználóbarát üzeneteket jelenítsenek meg. Azonban ez nem minden esetre terjed ki. A bővíthetőség révén a kereskedők felhasználóbarát üzeneteket rendelhetnek a környezetükre jellemző hibákhoz.

Egyéni állapotfelmérő ellenőrzések is létrehozhatók olyan eszközök tesztelésére, amelyek gyárilag nem támogatottak, illetve olyan szolgáltatások tesztelésére, amelyekre a pénztár támaszkodik.

## <a name="related-articles"></a>Kapcsolódó cikkek

[A Modern POS (MPOS) eseményindítói és nyomtatása](dev-itpro/pos-trigger-printing.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]