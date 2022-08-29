---
title: Állapotok és életciklus dokumentálása
description: Ez a cikk a lapelemek különböző dokumentum-államát tartalmazza Microsoft Dynamics 365 Commerce.
author: phinneyridge
ms.date: 10/09/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: niholman
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.custom: intro-internal
ms.search.industry: ''
ms.search.form: ''
ms.openlocfilehash: 350b3236eec6ad6520025bf44b22f12366f1e266
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9269916"
---
# <a name="document-states-and-lifecycle"></a>Állapotok és életciklus dokumentálása

[!include [banner](includes/banner.md)]

Ez a cikk a lapelemek különböző dokumentum-államát tartalmazza Microsoft Dynamics 365 Commerce.

## <a name="document-state-descriptions"></a>Dokumentumállapotok leírásai

A [lap elemeinek](page-elements-overview.md) cikke a tartalomkezelő rendszer (CMS) különféle dokumentumtípusait sorolja fel. Ezek a dokumentumtípusok a szerkesztési eszközben számos állapotot felvehetnek. A dokumentumállapotok segítenek az adatütközések elkerülésében és a verziókövetés betartatásában. Meghatározzák, hogy kik módosíthatják a dokumentumokat, mikor módosíthatók a dokumentumok, és a változtatások mikor lesznek mások által is megtekinthetők.

A következő táblázat bemutatja a Commerce oldalelemeinek lehetséges dokumentumállapotait.

| Dokumentum állapota      | Webhelykészítő művelet        | Leírás                                                  |
| ------------------- | -------------------------- | ------------------------------------------------------------ |
| Felelősnél         | Válassza ki a **Szerkesztés** opciót.           | Ön kivette a vonatkozó dokumentumot. Amikor egy dokumentum ebben az állapotban van, nem módosíthatja a többi hitelesített rendszerfelhasználó, és a dokumentumban elvégzett módosítások csak az Ön számára láthatók. |
| Mentve               | Válassza a **Mentés** lehetőséget.           | A kivett dokumentum módosításait az adatbázisba menti a program, de a dokumentum még nincs beküldve vagy közzétéve. A mentett változtatások nem láthatók a többi hitelesített rendszerfelhasználó számára mindaddig a szerző ki nem választja a **Szerkesztés befejezése** lehetőséget. Ezek addig nem láthatók a külső felhasználók számára, amíg nem teszik közzé. |
| Elvetett kivétel | Válassza a **Módosítások elvetése** parancsot.  | A kivett dokumentum minden módosítását elveti, és a rendszer visszaállítja az utolsó beküldött verzióra. |
| Bejelentkezve          | Válassza a **Szerkesztés befejezése** lehetőséget. | A szerkesztett dokumentum be van küldve. Minden változtatás látható a többi hitelesített rendszerfelhasználó számára is, és ezek a felhasználók is módosíthatják a dokumentumot. Az egyes beadások az elemek előzményeiben létrehoznak egy dokumentumverzió-rekordot. |
| Közzétéve           | Válassza a **Közzététel** lehetőséget.        | A program közzéteszi a dokumentumot, és a változtatások át lesznek küldve az élő webhelyre, és külső felhasználók számára is láthatóvá válnak. A cikkek csak akkor tehetők közzé, ha először be lettek küldve **Szerkesztés befejezése** lehetőség kiválasztásával. |

## <a name="additional-resources"></a>További erőforrások

[A tartalom hozzáadásának módjai](add-manage-content.md)

[Oldal modellszószedete](page-elements-overview.md)

[A közzétételi csoportokkal végzett munka](publish-groups.md)

[Csatornaközi megosztás engedélyezése és használata](cross-channel-sharing.md)

[Modulok használata](work-with-modules.md)

[Töredékek használata](work-with-fragments.md)

[Sablonok és elrendezések áttekintése](templates-layouts-overview.md)

[Webhely-navigáció testreszabása](customize-site-navigation.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
