---
title: ER Számláláshoz és összegzéshez használt formátum konfigurálása (1. rész – Formátum létrehozása)
description: Ez a témakör azt ismerteti, hogyan kell konfigurálni az Elektronikus jelentéskészítési formátumokat a már létrehozott szövegkimenet adatai alapján. (1. rész)
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERVendorPart, ERSolutionRepositoryTable, ERSolutionRepositoryCreateDropDialog, ERSolutionImport,  ERSolutionTable
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7a3639b5ac28f8a571642e983906d658dabf05b1
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/30/2021
ms.locfileid: "5093022"
---
# <a name="er-configure-format-to-do-counting-and-summing-part-1---create-format"></a>ER Számláláshoz és összegzéshez használt formátum konfigurálása (1. rész – Formátum létrehozása)

[!include [banner](../../includes/banner.md)]

Az alábbi útmutató azt ismerteti, hogy a rendszergazda vagy elektronikus jelentésfejlesztői szerepkörhöz hozzárendelt felhasználó hogyan konfigurálhat egy elektronikus jelentési (ER) formátumot számlálás és összegzés céljára a már létrehozott szöveges kimeneti adatok alapján. Ezeket a lépéseket bármely vállalatban végrehajthatja.

Hajtsa végre az alábbi lépéseket: először hajtsa végre a „Konfigurációszolgáltató létrehozása és aktívként történő megjelölése” eljárás lépéseit.

Az eljárás egy olyan szolgáltatáshoz tartozik, amely a Dynamics 365 for Operations 1611-es verziójában jelent meg.


## <a name="get-access-to-the-list-of-configurations-provided-by-microsoft"></a>Hozzáférés a Microsoft által biztosított konfigurációk listájához
1. Ugorjon a Szervezeti adminisztráció > Munkaterületek > Elektronikus jelentés pontra.
    * Győződjön meg róla, hogy a „Litware, Inc.” szolgáltató elérhető és aktívként megjelölt legyen.  
2. Válassza ki a Litware, Inc. lehetőséget szolgáltatót.
3. Kattintson a Tárházak gombra.
    * Ha már létezik egy „Üzemi erőforrások” típusú tár, hagyja ki az aktuális altevékenység többi lépését.  
4. A Hozzáadása gombra kattintva nyissa meg a legördülő párbeszédpanelt.
5. A Konfiguráció tárházának típusa mezőbe írja be az „Üzemi erőforrások” szöveget.
6. Kattintson a Tárház létrehozása lehetőségre.
7. Kattintson az OK gombra.

## <a name="get-the-intrastat-configurations-provided-by-microsoft"></a>A Microsoft által biztosított Intrastat konfigurációk beszerzése
1. Kattintson a Megnyitás gombra.
2. A fastruktúrában jelölje ki a következőt: „Intrastat modell\Intrastat (DE)”.
3. Kattintson az Importálás gombra.
    * Kattintson az Importálás gombra a kijelölt konfiguráció 1.1-es verziójának esetében.  
4. Kattintson az Igen gombra.
5. Zárja be a lapot.
6. Zárja be a lapot.
7. Kattintson a Jelentéskészítés konfigurációi lehetőségre.
8. A fastruktúrában bontsa ki az „Instrastat modell” elemet.
9. A fastruktúrában jelölje ki a következőt: „Intrastat modell\Intrastat (DE)”.

