---
title: A verzióelőzmények megtekintése az oldalak és a részletek visszaállításhoz
description: Ez a témakör ismerteti, hogyan lehet megtekinteni egy oldal vagy egy részlet verzióelőzményét, és visszaállni a Microsoft Dynamics 365 Commerce webhelyszerkesztő egy régebbi verziójára.
author: phinneyridge
ms.date: 06/21/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: niholman
ms.search.validFrom: 2017-06-20
ms.openlocfilehash: fa2ecdd9d9bc7e60b279d850573b5caa6df2c659
ms.sourcegitcommit: 9cfccb5c260ce56a3457f9ea12e80f54ea55a3b4
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/21/2022
ms.locfileid: "9183336"
---
# <a name="view-version-history-to-revert-pages-and-fragments"></a>A verzióelőzmények megtekintése az oldalak és a részletek visszaállításhoz

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

Ez a témakör ismerteti, hogyan lehet megtekinteni egy oldal vagy egy részlet verzióelőzményét, és visszaállni a Microsoft Dynamics 365 Commerce webhelyszerkesztő egy régebbi verziójára.

A Commerce Site Builder lehetővé teszi egy lap vagy a részletek verzióelőzményének megtekintését, és szükség esetén visszaáll a dokumentum egy adott korábbi verziójára. Miközben egy dokumentum meg van nyitva, a Verzióelőzmények párbeszédpanel megnyitásához a parancssori előzmények megjelenítése lehetőséget választhatja ki, **ahol** a **Verzió** lap felsorolja az összes verzió előzményeit, **és** menti az oldal vagy a részlet tevékenységeit. Ezt követően a listában kiválaszthatja a dokumentum egy korábbi verzióját, előnézetben megtekintheti, majd aktuális verzióként visszaállíthatja azt. A **párbeszédpanel** Tevékenység lapja a dokumentum teljes tevékenységi előzményeit sorolja fel, köztük az összes mentést, közzétételt és közzé nem tett eseményt.

> [!NOTE]
> A dokumentumok minden alkalommal új verziója jön létre, amikor a webhely szerzője módosítja a módosításokat, **majd a Dokumentum szerkesztésének** befejezése lehetőséget választja. 

Egy oldal vagy részlet verzióelőzményének megtekintéséhez és egy korábbi verzióhoz való visszatéréshez kövesse ezeket a lépéseket.

1. Nyissa meg a webhelyszerkesztőben azt az oldalt vagy részletet, amelyről meg szeretné tekinteni a verzióelőzményeket.
1. Válassza az Előzmények megjelenítése parancsot a **parancssorban**.

    ![Előzmények gomb megjelenítése.](./media/version-history-1.png)

1. A **Verzióelőzmények** **párbeszédpanel** Verzió lapján válassza ki a dokumentum egy korábbi verzióját. A jobb oldalon található tulajdonságablak a kiválasztott verzió miniatűr előnézetét, valamint a módosítókról és az adatokról tartalmaz információkat.

    ![Verzióelőzmény-lista megtekintése.](./media/version-history-2.png)

1. A dokumentum kijelölt verziójának teljes előnézeti képének megtekintéséhez válassza az Előnézet **lehetőséget**. Az előnézet bezárásához és a Verzióelőzmények **párbeszédpanelhez** való visszatéréshez válassza a Kilépés az előnézet **lehetőséget**.
1. A dokumentum egy korábbi verziójának visszaállításához jelölje **ki** azt a Verzió lap listájában, majd válassza a Visszaállítás **lehetőséget**. **Megjelenik egy \<version number\>** Visszaállítás verziójú üzenet, amely kéri a visszaállítási művelet megerősítését. 

    ![Visszaállítás gomb és megerősítő üzenetmező](./media/version-history-3.png)

1. A visszaállítási művelet úgy folytatható, hogy a Visszaállítás **lehetőséget választja**. A program frissíti a webhelyszerkesztőt, és megjeleníti az oldal vagy a részlet visszaállított verzióját.
1. A visszaállított verzió közzétételéhez válassza a Befejezés **szerkesztés**, majd a Közzététel **lehetőséget**.
