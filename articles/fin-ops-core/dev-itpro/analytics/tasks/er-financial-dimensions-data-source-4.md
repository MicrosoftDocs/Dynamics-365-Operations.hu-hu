---
title: ER Pénzügyi dimenziók használata adatforrásként (4. rész – A jelentés futtatása)
description: Ez a témakör azt ismerteti, hogyan kell konfigurálni egy elektronikus jelentési (ER) modellt, hogy a pénzügyi dimenziókat használja az ER-jelentések adatforrásaként. (4. rész)
author: kfend
ms.date: 05/27/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.search.form: ERSolutionTable, SysQueryForm
ms.openlocfilehash: d0fca8b1a6139b71782af05531d9494c968ef9f5
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9290754"
---
# <a name="er-use-financial-dimensions-as-a-data-source-part-4---run-the-report"></a>ER Pénzügyi dimenziók használata adatforrásként (4. rész – A jelentés futtatása)

[!include [banner](../../includes/banner.md)]

A következő lépések leírják, hogy egy rendszergazda vagy az elektronikus jelentések fejlesztője szerepkörhöz hozzárendelt felhasználó miként konfigurálhat egy elektronikusjelentés-modellt (ER-modell) a pénzügyi dimenzió használatához az ER-jelentések adatforrásaként. Ezeket a lépéseket a DEMF vállalatban hajthatja végre.

A lépések végrehajtásához először hajtsa végre az „ER Pénzügyi dimenziók használata adatforrásként (3. rész: A jelentés megtervezése)” eljárás lépéseit. Emellett az alapértelmezett dokumentumtípusokat is meg kell adni az Elektronikus jelentési paraméterek lapon. Az alapértelmezett dokumentumtípusok beállítása bármely ER-konfiguráció letöltésekor és importálásakor is megtörténik. 


## <a name="run-report"></a>Futtassa a jelentést
1. Nyissa meg a következőt: Szervezeti adminisztráció > Elektronikus jelentés > Konfigurációk.
2. A fastruktúrában bontsa ki a következőt: „Pénzügyi dimenziók mintamodell”.
3. A fastruktúrában válassza ki a következőt: „Pénzügyi dimenziók mintamodell\Főkönyvi naplójelentés”.
4. Kattintson a Futtatásra.
![ER-konfigurációk oldal.](../media/er-financial-dimensions-guides-run1.png)
5. A Dimenzió mezőben adjon meg vagy válasszon ki egy értéket.
    * Az aktuális vállalat összes dimenziójának kijelöléséhez írja be a következőt: BusinessUnit;CostCenter;Department;ItemGroup;MainAccount;Project  
![Az elektronikus jelentés paraméterei kiúszó elem, Dimenzió neve legördülő lista.](../media/er-financial-dimensions-guides-run2.png)
6. Bontsa ki a Szerepeltetni kívánt rekordok szakaszt.
7. Kattintson a Szűrő parancsra.
8. Jelölje ki a főkönyvi napló táblájának a sorát, és a Napló kötegszáma mezőt.
9. A Feltétel mezőbe írja be a „00057” értéket.
10. Kattintson az OK gombra.
11. Kattintson az OK gombra.
![Az elektronikus jelentés paraméterei kiúszó elem, Belefoglalni kívánt jelentések szakasz.](../media/er-financial-dimensions-guides-run3.png)
    * Tekintse át a létrehozott kimenetet. A kiválasztott köteg minden tranzakciójához a megfelelő dimenziók pénzügyi dimenziói jelennek meg. Futtassa a jelentést, és válasszon ki különböző dimenziókat annak a megtekintéséhez, hogy a jelentés nem függ a kiválasztott dimenziók, vagy a példányhoz konfigurált dimenziók számától.  
![Az ER-konfigurációk által generált kimenet.](../media/er-financial-dimensions-guides-run4.png)


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
