---
title: Pillanatképek áttekintése (előzetes verzió)
description: Ez a témakör a pillanatképek funkciót ismerteti, amely lehetővé teszi a pénzforgalmi előrejelzés mentését elemzés vagy későbbi tényleges adatok összehasonlítása érdekében. Amikor pénzforgalmi előrejelzést hoz létre, az előrejelzést „pillanatképként” mentheti. Ezután a pillanatképek segítségével szerkesztheti az előrejelzésben szereplő fiókokat, vagy összehasonlíthatja a pillanatképen szereplő előrejelzést a tényleges adatokkal.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 05/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-05-19
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: f0d0bdde8b69148c72b8c645e040f0e596ecba92
ms.sourcegitcommit: deb711c92251ed48cdf20ea514d03461c26a2262
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/25/2020
ms.locfileid: "4645625"
---
# <a name="snapshots-overview-preview"></a>Pillanatképek áttekintése (előzetes verzió)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

A pillanatképek lehetővé teszik a szervezetek számára, hogy egy adott időpontban szerkesszék és mentsék a készpénzes pozíciójukra és a készpénz-előrejelzéseikre vonatkozó információkat. Összehasonlíthatja a pillanatképet a tényleges pénzügyi adatokkal, megvizsgálhatja az eltérést, és ezt az információt felhasználhatja a pénzforgalmi előrejelzések időbeli javítására. Pontosabban a pillanatképeket a következő módokon lehet használni:

- Készpénzpozíció és -előrejelzések nyomon követése idővel.
- Az adatok szűrésével megjelenítheti azokat a jogi személyeket, akikhez a pillanatkép létrejött.
- A rendszer által előállított készpénzpozíció és -előrejelzés szerkesztése.
- A mi lenne, ha elemzés elvégzése a pénzforgalom optimista, pesszimista és legvalószínűbb nézeteinek megfontolására.
- A tényleges pénzügyi teljesítmény összevetése a pillanatfelvételen mentett előrejelzéssel.

A pillanatképek létrehozásához válassza a **Pénzforgalmi előrejelzés** munkaterület **Készpénzpozíció** fülén vagy **Készpénzelőrejelzés** fülén válassza az **Új pillanatkép** lehetőséget. Miután létrehozta a pillanatképet, szerkesztheti és mentheti a benne szereplő be- és kiáramlásokat. Minden mentett pillanatkép elérhető a **Pillanatképek** fülön. Pillanatkép megnyitásához válassza ki a pillanatkép nevét.

A pillanatképek pénzbe- és kiáramlásai bármikor szerkeszthetők. Ha egy beáramló összeg vagy egy kiáramló összeg szerkesztve van, akkor a frissített összeg az eredeti egyenleget elkészítő likviditási számlákkal arányos. Amikor befejezte a pillanatképek módosítását, válassza a **Mentés** elemet a módosítások mentéséhez.

Ha több pillanatképet szeretne összehasonlítani, válassza a **Pillanatképek összehasonlítása** elemet. Egyszerre két pillanatképet lehet összehasonlítani. Válassza ki az összehasonlítani kívánt két pillanatképeket, majd kattintson az **OK** gombra. A **Pillanatképek összehasonlítása** lap a kiválasztott pillanatfelvételek összehasonlítását jeleníti meg. A lap felső részén található diagram bemutatja a pénzbeáramlások, a pénzkiáramlások és a banki egyenlegek összehasonlítását a két pillanatfelvétel közötti átfedésben lévő időszakok között. Az alsó részen látható rács a likviditási összegekhez tartozó két előrejelzés részletes összehasonlítását tartalmazza. Az **Eltérés** oszlopa egy adott időszak egyenlegeinek különbségét mutatja.

Ha egy olyan előrejelzéssel szeretné összehasonlítani a tényleges pénzügyi eredményt, amelyet pillanatfelvételként mentettek, válassza az **Összehasonlítás a tényleges adatokkal** elemet. A **Pillanatképek összehasonlítás** lap a tényleges összegek és az előrejelzés összehasonlítását jeleníti meg. A lap felső részén található diagram bemutatja a pénzbeáramlások, a pénzkiáramlások és a banki egyenlegek összehasonlítását a két pillanatfelvétel közötti átfedésben lévő időszakok között. Az alsó részen látható rács a likviditási összegekhez tartozó időszakonkénti tényleges egyenlegek és az előrejelzett egyenleg. Az **Eltérés** oszlopa egy adott időszak tényleges egyenleg és az előrejelzett egyenleg különbségét mutatja.

#### <a name="privacy-notice"></a>Adatvédelmi nyilatkozat
Az előzetes verziók (1) kevesebb adatvédelmi és biztonsági intézkedést alkalmazhatnak, mint a Dynamics 365 Finance and Operations szolgáltatás (2) és nem vonatkozik a szolgáltatásiszint-szerződés (SLA) ehhez a szolgáltatáshoz, (3) nem használhatók olyan személyes adatok vagy más adatok feldolgozásához, melyekhez törvényi vagy jogszabályi megfelelési követelmények tartoznak, és (4) korlátozott támogatás tartozik hozzá.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]