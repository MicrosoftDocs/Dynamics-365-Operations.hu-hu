---
title: Féléves értékcsökkenési szabály módszertana
description: Ez a témakör azt mutatja be, hogy a tárgyi eszközökhöz milyen módszerrel számítják ki az értékcsökkenést a féléves szabály alapján, amely az eszköz első és utolsó évében a szolgáltatásban számított hat hónapos értékcsökkenést számítja ki.
author: moaamer
ms.date: 08/17/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2019-08-17
ms.dyn365.ops.version: 10.0.12
ms.openlocfilehash: 9a8dd3d8c6b92be9f22573f463aa96b13d9e3418
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/06/2021
ms.locfileid: "6355532"
---
# <a name="half-year-depreciation-convention-methodology"></a>Féléves értékcsökkenési szabály módszertana

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Ez a témakör azt mutatja be, hogy milyen módszer van alkalmazva a tárgyi eszközökhöz az értékcsökkenés kiszámítására a féléves szabályok használatával. A Féléves szabály egy eszköz első és utolsó évében kiszámítja az értékcsökkenést hat hónapra. Az értékcsökkenési szabályokkal kapcsolatos további tudnivalókért lásd: [Értékcsökkenési módszerek és szabályok](Fixed-asset-depreciation-conventions.md). 

Amikor a hathónapos értékcsökkenési szabályt használja, a rendszer a beszerzés évét vagy az eszköz üzembe helyezésének évét használja, majd az adott évtől számított öt éves értékcsökkenést számítja ki, majd hat hónapot hozzáad. Ennek a folyamatnak a szemléltetéséhez képzeljen el egy olyan eszközt, amelyet a 50 000 dollárért vettek 2020 augusztusában. Azt is feltételezi, hogy az eszköznek ötéves élettartama van.

Az üzemelés első éve 2020 decemberében kezdődik ami azt jelenti, hogy az eszköz ötéves élettartamának vége 2024 december. A féléves értékcsökkenési szabály hat hónapot ad hozzá az eszköz élettartamához, ami azt jelenti, hogy a hasznos élettartam 2025 júniusában fog befejeződni. 

> Évenkénti értékcsökkenés 50000/5 = 10 000 havi értékcsökkenés 10000/12 = 833,33 <br>
> Első évi értékcsökkenés 10000/2 = 5 000 és az azt követő havi értékcsökkenés 5000/9 = 555,56

   [![Féléves értékcsökkenési szabály értékcsökkenési ütemezése.](./media/half-yr-dprectn-cnvntn.png)](./media/half-yr-dprectn-cnvntn.png)

A féléves konvencióval hozzáadott meghosszabbított értékcsökkenési időszakok pontosabban osztják fel az értékcsökkenést. A hat hónapos szabály egyenletesebben képviseli az értékcsökkenést, ami az eredménykimutatásban történő jelentéshez hasznos.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]