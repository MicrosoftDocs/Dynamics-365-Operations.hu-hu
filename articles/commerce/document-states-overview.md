---
title: Állapotok és életciklus-dokumentálás
description: Ez a témakör a Microsoft Dynamics 365 Commerce oldalelemeinek különböző dokumentumállapotait mutatja be.
author: phinneyridge
manager: annbe
ms.date: 10/31/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: ''
ms.author: niholman
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: a34d10edbf84ac1814afdc7107727aea68a303e0
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/06/2019
ms.locfileid: "2770435"
---
# <a name="document-states-and-lifecycle"></a>Állapotok és életciklus-dokumentálás

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Ez a témakör a Microsoft Dynamics 365 Commerce oldalelemeinek különböző dokumentumállapotait mutatja be.

## <a name="document-state-descriptions"></a>Dokumentumállapotok leírásai

Az [Oldalelemek](page-elements-overview.md) témakör a tartalomkezelő rendszerben (CMS) található, különböző típusú dokumentumokat sorolja fel. Ezek a dokumentumtípusok a szerkesztési eszközben számos állapotot felvehetnek. A dokumentumállapotok segítenek az adatütközések elkerülésében és a verziókövetés betartatásában. Meghatározzák, hogy kik módosíthatják a dokumentumokat, mikor módosíthatók a dokumentumok, és a változtatások mikor lesznek mások által is megtekinthetők.

A következő táblázat bemutatja a Commerce oldalelemeinek lehetséges dokumentumállapotait.

| Dokumentum állapota | Leírás |
|---|---|
| Lefoglalva | Ha Ön kivesz egy CMS-elemet, akkor azt más hitelesített rendszerfelhasználók nem szerkeszthetik. Az elemen Ön által végzett módosításokat csak Ön láthatja. |
| Bejelentkezve | Ha egy CMS-elemet beadnak, akkor az összes többi hitelesített rendszerfelhasználó láthatja az összes módosítást, valamint ezek a felhasználók ki is vehetik ezeket az elemeket, és szerkeszthetik őket. Az egyes beadások az elemek előzményeiben létrehoznak egy dokumentumverzió-rekordot. |
| Közzétéve | Egy CMS-elem közzétételekor a rendszer feltolja az Ön éles webhelyére, és így az interneten a nem hitelesített külső felhasználók számára is felfedezhetővé válik. A cikkeket csak akkor lehet közzétenni, ha beadták őket. |
| Mentve | A kivett CMS-elemek módosításait a program a CMS-be mentheti, mielőtt a elemet beadták vagy közzétették. Ezek a mentett változtatások nem láthatók a többi hitelesített rendszerfelhasználó számára mindaddig, amíg be nem adták az elemet. Ezek addig nem láthatók a külső felhasználók számára, amíg nem teszik közzé. |
| Elvetett kivétel | Amikor egy kivett CMS-elemet ekvetnek, az összes mentett módosítás törlődik, és az elemet a rendszer visszaállítja arra a verzióra, amelyet legutóbb adtak be. |

## <a name="additional-resources"></a>További erőforrások

[A tartalom hozzáadásának módjai](add-manage-content.md)

[Oldal modellszószedete](page-elements-overview.md)

[Modulok használata](work-with-modules.md)

[Töredékek használata](work-with-fragments.md)

[Sablonok és elrendezések áttekintése](templates-layouts-overview.md)

[Webhely-navigáció testreszabása](customize-site-navigation.md)
