---
title: Állapotok és életciklus-dokumentálás
description: Ez a témakör a Microsoft Dynamics 365 Commerce oldalelemeinek különböző dokumentumállapotait mutatja be.
author: phinneyridge
manager: annbe
ms.date: 10/09/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: niholman
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 7c30932800beda13ac8fe6b0386fe29efe93f79c
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4982616"
---
# <a name="document-states-and-lifecycle"></a>Állapotok és életciklus-dokumentálás

[!include [banner](includes/banner.md)]

Ez a témakör a Microsoft Dynamics 365 Commerce oldalelemeinek különböző dokumentumállapotait mutatja be.

## <a name="document-state-descriptions"></a>Dokumentumállapotok leírásai

Az [Oldalelemek](page-elements-overview.md) témakör a tartalomkezelő rendszerben (CMS) található, különböző típusú dokumentumokat sorolja fel. Ezek a dokumentumtípusok a szerkesztési eszközben számos állapotot felvehetnek. A dokumentumállapotok segítenek az adatütközések elkerülésében és a verziókövetés betartatásában. Meghatározzák, hogy kik módosíthatják a dokumentumokat, mikor módosíthatók a dokumentumok, és a változtatások mikor lesznek mások által is megtekinthetők.

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