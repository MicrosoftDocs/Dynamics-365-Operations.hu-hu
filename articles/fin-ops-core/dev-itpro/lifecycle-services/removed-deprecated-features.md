---
title: A Lifecycle Services (LCS) szolgáltatás eltávolított vagy elavult funkciói
description: Ez a témakör azokat a funkciókat ismerteti, amelyek el lettek távolítva a Microsoft Dynamics Lifecycle Services (LCS) szolgáltatásból, vagy az eltávolításuk be van tervezve.
author: AngelMarshall
manager: AnnBe
ms.date: 06/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: tsmarsha
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: abf7a1a0a75ac3098efeeab3df65481999b69acc
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/05/2020
ms.locfileid: "4687878"
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
<td>Elavult: A BPM folyamatábra összetevője várhatóan 2020-ban eltávolításra kerül. A következők funkciók nem lesznek elérhetők:
<ul>
<li>Minden folyamatábra csak olvasható, és nem érhető el szerkesztésre. A folyamatábra-tevékenységekhez társított alakzattulajdonságok sem lesznek elérhetők. Ezek a folyamatábrák tartalmazzák továbbá az alapértelmezett folyamatábrákat, amelyek automatikusan létrejönnek és a testreszabott folyamatábrákat, amelyeket az alapértelmezett folyamatábrák alapján módosítottak.</li>
<li>A folyamat lépései csak olvashatók, és nem érhető el szerkesztésre.</li>     
<li>Az örökölt illeszkedés-/hiányelemzés nem lesz elérhető. Ezért a program automatikusan nem hozhat létre vagy bocsájthat rendelkezésre exportáláshoz hiánylistát.
<p><strong>Megjegyzés:</strong> Ez a funkció korábban már elavult és helyébe a Microsoft Azure DevOps integrációk léptek.</p>
</li>
<li>A folyamatábra verzióelőzményei nem lesznek elérhetők.</li>
</ul>
</td>
</tr>
</tbody>
</table>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]