---
title: A Lifecycle Services (LCS) szolgáltatás eltávolított vagy elavult funkciói
description: Ez a témakör azokat a funkciókat ismerteti, amelyek el lettek távolítva a Microsoft Dynamics Lifecycle Services (LCS) szolgáltatásból, vagy az eltávolításuk be van tervezve.
author: AngelMarshall
manager: AnnBe
ms.date: 06/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: tsmarsha
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 6b49a6f26b4c2fa895fe0e49f716ce423c3c0057
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/09/2021
ms.locfileid: "5559085"
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