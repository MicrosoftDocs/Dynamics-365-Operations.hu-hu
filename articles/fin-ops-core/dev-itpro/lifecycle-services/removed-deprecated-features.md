---
title: A Lifecycle Services (LCS) szolgáltatás eltávolított vagy elavult funkciói
description: Ez a témakör azokat a funkciókat ismerteti, amelyek el lettek távolítva a Microsoft Dynamics Lifecycle Services (LCS) szolgáltatásból, vagy az eltávolításuk be van tervezve.
author: sericks007
manager: AnnBe
ms.date: 12/02/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: c792d06e9b0aa42919de924bdcc9118358779b72
ms.sourcegitcommit: 75bbcff474cfb8d2f282be2b9d2d7984d1505fa3
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/03/2019
ms.locfileid: "2885455"
---
# <a name="removed-or-deprecated-features-in-lifecycle-services-lcs"></a>A Lifecycle Services (LCS) szolgáltatás eltávolított vagy elavult funkciói

[!include[banner](../includes/banner.md)]

Ez a témakör azokat a funkciókat ismerteti, amelyek el lettek távolítva vagy elavultak a Microsoft Dynamics Lifecycle Services (LCS) szolgáltatásban.

- Az *eltávolított* szolgáltatások már nem érhetők el a szolgáltatásban.
- Az *elavult* szolgáltatás már nincs aktív fejlesztés alatt, és egy jövőbeli frissítésben eltávolíthatjuk.

Ez a lista segít figyelembe venni az elavult és eltávolított szolgáltatásokat a saját tervezése elősegítésére.

## <a name="october-2019-announcements"></a>2019. októberi bejelentések

### <a name="flowchart-diagrams-in-business-process-modeler"></a>Az üzletifolyamat-modellező folyamatábrái

<table>
<tbody>
<tr>
<td><strong>Elavulás/eltávolítás oka</strong></td>
<td>Elavulttá fog válni a folyamatábra-diagramok összetevője az Üzletifolyamat-modellezőben (BPM), mert az örökölt kialakítás alacsony kihasználtságot eredményezett.</td>
</tr>
<tr>
<td><strong>Felváltotta másik szolgáltatás?</strong></td>
<td>Nem</td>
</tr>
<tr>
<td><strong>Érintett területek</strong></td>
<td>Üzletifolyamat-modellező</td>
</tr>
<tr>
<td><strong>Állapot</strong></td>
<td>Elavult: A BPM folyamatábra összetevője várhatóan 2020 februárjának elején eltávolításra kerül. A következők funkciók eltávolításra kerülnek:
<ul>
<li>A meglévő folyamatábrák nem lesznek érhetők megtekintésre vagy szerkesztésre. A folyamatábra-tevékenységekkel társított alakzattulajdonságok sem nem lesznek elérhetők, mert a teljes <strong>Folyamatábra</strong> lap eltávolításra kerül. Ezek a folyamatábrák tartalmazzák továbbá az alapértelmezett folyamatábrákat, amelyek automatikusan létrejönnek és a testreszabott folyamatábrákat, amelyeket az alapértelmezett folyamatábrák alapján módosítottak.</li>
<li>Az örökölt illeszkedés-/hiányelemzés nem lesz elérhető. Ezért a program automatikusan nem hozhat létre vagy bocsájthat rendelkezésre exportáláshoz hiánylistát.
<p><strong>Megjegyzés:</strong> Ez a funkció korábban már elavult és helyébe a Microsoft Azure DevOps integrációk léptek.</p>
</li>
<li>A folyamatábra verzióelőzményei nem lesznek elérhetők.</li>
</ul>
</td>
</tr>
</tbody>
</table>
