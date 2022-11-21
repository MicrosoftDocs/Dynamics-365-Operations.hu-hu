---
title: Dolgozókhoz való hozzáférés korlátozása jogi személy szerint
description: Ez a cikk bemutatja a dolgozók jogi személyek szerint való hozzáférésének beállítását.
author: twheeloc
ms.date: 11/28/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmSharedParameters, HcmPersonnelManagementWorkspace
audience: Application User
ms.custom: 51891
ms.assetid: c7d8f58c-d78a-4035-abbf-2b0ce16109fe
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: fadd2c34d31bbd259255596c06a8e7517f7a774b
ms.sourcegitcommit: cf6b764824bd1cf2c0dde6d37ddd0a7abab87ff0
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/16/2022
ms.locfileid: "9780299"
---
# <a name="restrict-access-to-workers-by-legal-entity"></a>Dolgozókhoz való hozzáférés korlátozása jogi személy szerint

Ez a cikk bemutatja a dolgozók jogi személyek szerint való hozzáférésének beállítását.

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Az alkalmazottak jogi személyeknél alkalmazásban állnak. Íme néhány példa:

- Az UsSI jogi személynél alkalmazásban áll.
- Az UsMF jogi személy alkalmazásban áll.
- A GlSI és az USMF jogi személyek alkalmazásban áll.

A felhasználónak a vállalatnál betöltött szerepétől függően szükséges lehet a hozzáférése az összes alkalmazotthoz az összes jogi személynél. Arra is lehetőség van, hogy egy felhasználó korlátozva legyen, hogy csak a jogi személy alkalmazottait tudja megtekinteni. Annak beállítására, hogy egy felhasználó mely alkalmazottakat tekintse meg, **jelölje** be a Dolgozói adatokhoz való hozzáférés korlátozása paramétert az **Emberi erőforrások megosztott paraméterei lapon**.

Egy felhasználó például hozzáfér a **Dolgozó** laphoz, és csak az USMF jogi személyhez fér hozzá. Ebben az esetben a felhasználó a következő információkat megtekintheti az előző listában található alkalmazottakról:

- Ha nincs engedélyezve a dolgozói adatokhoz való hozzáférést korlátozó funkció, akkor a felhasználó megtekintheti a Dolgozó, a Engedélyezve és a Melláni adatokat.
- Ha ez a funkció engedélyezve van, akkor a felhasználó csak datálhat és megtekinthet adatokat, mivel ők is az USMF jogi személy alkalmazottja.

A megjelenő adatok a használt alkalmazástól függően eltérőek.

## <a name="dynamics-365-human-resources-stand-alone"></a>Dynamics 365 Human Resources Önálló

Ha engedélyezve van a dolgozói adatokhoz való hozzáférés korlátozására vonatkozó funkció, a korlátozott felhasználó üres értéket lát néhány olyan listában, amely a dolgozó nevét tartalmazza.

Például egy olyan felhasználó, aki csak az USMF jogi személyhez fér hozzá, a következő viselkedést tapasztalja:

- Az Aktív **beosztások** listán **a** Dolgozó oszlop üresen marad Azon a beosztáson, mert a felhasználónak nincs hozzáférése az USSI jogi személy alkalmazottaihoz.
- Ha a felhasználó a dolgozó nevében ás le, egy üres **Dolgozó** lap jelenik meg.

## <a name="dynamics-365-human-resources-on-finance-infrastructure"></a>Dynamics 365 Human Resources a pénzügyi infrastruktúrán

Ha engedélyezve van a dolgozói adatokhoz való hozzáférés korlátozására vonatkozó funkció, a korlátozott felhasználó bizonyos listákon láthatja a dolgozó nevét.

Például egy olyan felhasználó, aki csak az USMF jogi személyhez fér hozzá, a következő viselkedést tapasztalja:

- Az Aktív **beosztások listán** a Dolgozó **oszlopban** megjelenik a Munkatárs neve. Ha a felhasználó a dolgozó neve felett dolgozik, csak a név és a beosztás jelenik meg.
- Ha a felhasználó a dolgozó nevében ás le, egy üres **Dolgozó** lap jelenik meg.

> [!TIP]
> Ha a Dynamics 365 Emberi erőforrások a pénzügyi infrastruktúrában van használatban, és azt szeretné, hogy a korlátozott felhasználók üres értékeket tekintsenek meg a dolgozónevekhez, **·** **hozzáadhatja** a "Dolgozók biztonsági engedélyének korlátozása" jogosultságot a Biztonsági konfigurációs lapon szereplő felhasználói szerepkörökhöz.

Miután engedélyezi a funkciót, további lépéseket kell végrehajtania ahhoz, hogy beállítsa az engedélyeket minden olyan felhasználóhoz, akinek nézetét korlátozni kell.

1. Jelöljön ki egy felhasználót a **Felhasználók** lapon.
2. Szerepkör kiválasztása a felhasználó számára. Elérhetővé válik a **Szervezetek hozzárendelése** beállítás.
3. Válassza ki a **Szervezetek hozzárendelése** lehetőséget.
4. Válassza ki az új lapon a **Megadja a hozzáférést adott szervezetekhez egyenként**, majd válassza ki azokat a szervezeteket, amelyekhez a felhasználónak hozzáférést kell tudnia.
5. Ismételje meg a 2–4. lépést a felhasználó összes többi szerepkörével, beleértve a rendszer felhasználói szerepkörét is.

> [!NOTE]
> A jogi személyeknek, akikhez hozzáférése van, meg kell egyezniük a felhasználó összes szerepköre között.
