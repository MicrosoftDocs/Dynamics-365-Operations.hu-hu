---
title: ER Dokumentumkezelési fájlok használata formátumkimenetekben (1. rész – Adatmodell előkészítése)
description: Ez a témakör azt ismerteti, hogyan kell konfigurálni egy elektronikus jelentési (ER) formátumot az ER kimenet dokumentumkezelési fájljainak (mellékletei) használatára. (1. rész)
author: kfend
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.search.form:
- ERWorkspace, ERVendorPart, ERSolutionRepositoryTable, ERSolutionRepositoryCreateDropDialog, ERSolutionImport
- ERSolutionTable, ERSolutionCreateDropDialog
ms.openlocfilehash: f407555eca4c4bd08d09047e9d8f8512cb99d254
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9291024"
---
# <a name="er-use-document-management-files-in-format-outputs-part-1---prepare-data-model"></a>ER Dokumentumkezelési fájlok használata formátumkimenetekben (1. rész – Adatmodell előkészítése)

[!include [banner](../../includes/banner.md)]

A következő lépések leírják, hogy egy rendszergazda vagy elektronikus jelentések fejlesztője szerepkörrel rendelkező felhasználó miként konfigurálhat egy új Elektronikus jelentés (ER) formátumot a dokumentumkezelési fájlok (mellékletek) használatához az ER-kimenetben. Ezeket a lépéseket bármely vállalatban végrehajthatja.

Hajtsa végre az alábbi lépéseket: először hajtsa végre a „Konfigurációszolgáltató létrehozása és aktívként történő megjelölése” eljárás lépéseit.

Az eljárás egy olyan szolgáltatáshoz tartozik, amely a Dynamics 365 for Operations 1611-es verziójában jelent meg.


## <a name="get-access-to-the-list-of-configurations-provided-by-microsoft"></a>Hozzáférés a Microsoft által biztosított konfigurációk listájához
1. Ugorjon a Szervezeti adminisztráció > Munkaterületek > Elektronikus jelentés pontra.

    Győződjön meg róla, hogy a Litware, Inc. szolgáltató elérhető és aktívként megjelölt legyen.  

2. Válassza ki a Litware, Inc. szolgáltatót.
3. Kattintson a Tárházak gombra.

    Ha már létezik egy „Üzemi erőforrások” típusú tár, hagyja ki az aktuális altevékenység többi lépését.  

4. A Hozzáadása gombra kattintva nyissa meg a legördülő párbeszédpanelt.
5. A Konfiguráció tárházának típusa mezőbe írja be az „Üzemi erőforrások” szöveget.
6. Kattintson a Tárház létrehozása lehetőségre.
7. Kattintson az OK gombra.

## <a name="get-the-customer-invoice-model-configurations-provided-by-microsoft"></a>A Microsoft által biztosított vevői számlamodell konfigurációk beszerzése
1. Kattintson a Szűrők megjelenítése pontra.
2. Alkalmazza az alábbi szűrőket: Adja meg az „Üzemi erőforrások” szűrőértéket a „Név” mezőben a „kezdete” szűrőoperátor használatával; Adja meg az "" szűrőértéket a „Leírás” mezőben a „kezdete” szűrőoperátor használatával
3. Kattintson a Szűrők megjelenítése pontra.
4. Kattintson a Megnyitás gombra.
5. A fastruktúrában válassza ki a „Vevői számlamodell” lehetőséget.

    Válassza ki a „Vevői számlamodell modellkonfigurációt” az importáláshoz.  

6. Kattintson az Importálás gombra.

    Kattintson az Importálás gombra a kijelölt konfiguráció 1-es verziójának esetében.  

7. Kattintson az Igen gombra.
8. Zárja be a lapot.
9. Zárja be a lapot.
10. Kattintson a Jelentéskészítés konfigurációi lehetőségre.
11. A fastruktúrában válassza ki a „Vevői számlamodell” lehetőséget.

## <a name="create-the-derived-model-to-support-access-to-the-document-management-files"></a>Hozza létre a származtatott modellt a Dokumentumkezelés fájlok elérésének támogatásához.
A vevői számlamodellhez saját konfigurációt fog létrehozni, a Microsoft által biztosított konfiguráció alapján. A konfiguráció használatával fogja megvalósítani a hozzáférést a dokumentumkezelési fájlokhoz, illetve elérhetővé tenni őket az elektronikus dokumentumok számára, amelyeket a modell alapján hoz létre.  
1. A Konfiguráció létrehozása gombra kattintva megnyithatja a legördülő párbeszédablakot.
2. Az Új mezőbe írja be a következőt: „Származtatás innen: Vevői számlamodell, Microsoft”.
3. A Név mezőbe írja be a „Vevői számlamodell (egyéni)” szöveget.
4. Kattintson a Konfiguráció létrehozása lehetőségre.



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
