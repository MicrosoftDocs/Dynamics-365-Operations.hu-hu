---
title: Féléves értékcsökkenési szabály módszertana
description: Ez a témakör azt a módszert írja le, amellyel a tárgyi eszközök értékcsökkenését a féléves szabály alkalmazásával számítják ki, amely a tárgyi eszköz első és utolsó évében hat hónap értékcsökkenést számít ki.
author: moaamer
ms.date: 08/17/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: kfend
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2019-08-17
ms.dyn365.ops.version: 10.0.12
ms.openlocfilehash: fac20f7a31eca7922ed079f9554437f28448620d
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8879595"
---
# <a name="half-year-depreciation-convention-methodology"></a>Féléves értékcsökkenési szabály módszertana

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Ez a témakör azt a módszert írja le, amely a tárgyi eszközök értékcsökkenésének a féléves szabály alapján való kiszámítására használatos. A Féléves szabály egy eszköz első és utolsó évében kiszámítja az értékcsökkenést hat hónapra. Az értékcsökkenési szabályokkal kapcsolatos további tudnivalókért lásd: [Értékcsökkenési módszerek és szabályok](Fixed-asset-depreciation-conventions.md). 

Amikor a hathónapos értékcsökkenési szabályt használja, a rendszer a beszerzés évét vagy az eszköz üzembe helyezésének évét használja, majd az adott évtől számított öt éves értékcsökkenést számítja ki, majd hat hónapot hozzáad. Ennek a folyamatnak a szemléltetéséhez képzeljen el egy olyan eszközt, amelyet a 50 000 dollárért vettek 2020 augusztusában. Azt is feltételezi, hogy az eszköznek ötéves élettartama van.

Az üzemelés első éve 2020 decemberében kezdődik ami azt jelenti, hogy az eszköz ötéves élettartamának vége 2024 december. A féléves értékcsökkenési szabály hat hónapot ad hozzá az eszköz élettartamához, ami azt jelenti, hogy a hasznos élettartam 2025 júniusában fog befejeződni. 

> Évenkénti értékcsökkenés 50000/5 = 10 000 havi értékcsökkenés 10000/12 = 833,33 <br>
> Első évi értékcsökkenés 10000/2 = 5 000 és az azt követő havi értékcsökkenés 5000/9 = 555,56

   [![Féléves értékcsökkenési szabály értékcsökkenési ütemezése.](./media/half-yr-dprectn-cnvntn.png)](./media/half-yr-dprectn-cnvntn.png)

A féléves konvencióval hozzáadott meghosszabbított értékcsökkenési időszakok pontosabban osztják fel az értékcsökkenést. A hat hónapos szabály egyenletesebben képviseli az értékcsökkenést, ami az eredménykimutatásban történő jelentéshez hasznos.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
