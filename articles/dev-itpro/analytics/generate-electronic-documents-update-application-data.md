---
title: "Elektronikus dokumentumok és alkalmazásadatok frissítése az Elektronikus jelentéskészítő eszköz használatával"
description: "Lehetőség van elektronikus jelentési (ER) formátumok tervezésére, amelyek kimenő elektronikus dokumentumok létrehozására használhatók a Finance and Operations alkalmazásban. Olyan ER-formátumokat is készíthet, amelyek a bejövő elektronikus dokumentumokat elemzik, és ezeknek a dokumentumoknak a tartalmát használják az alkalmazásadatok frissítésére."
author: NickSelin
manager: AnnBe
ms.date: 11/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
ms.search.form: ERSolutionTable, ERVendorTable, ERWorkspace
audience: Developer, IT Pro, Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 27621
ms.assetid: 018a11ae-854c-4f36-9358-8c39baca882d
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 7378c1d205b9a9cd61044dc33fc52ff75c6b94b7
ms.contentlocale: hu-hu
ms.lasthandoff: 11/03/2017

---

# <a name="generate-electronic-documents-and-update-application-data-using-the-electronic-reporting-tool"></a>Elektronikus dokumentumok és alkalmazásadatok frissítése az Elektronikus jelentéskészítő eszköz használatával

[!include[banner](../includes/banner.md)]

Lehetőség van elektronikus jelentési (ER) formátumok tervezésére, amelyek kimenő elektronikus dokumentumok létrehozására használhatók a Finance and Operations alkalmazásban. Olyan ER-formátumokat is készíthet, amelyek a bejövő elektronikus dokumentumokat elemzik, és ezeknek a dokumentumoknak a tartalmát használják az alkalmazásadatok frissítésére. 

Ezzel a funkcióval egyetlen ER-formátum használható a kimenő elektronikus dokumentumok létrehozására, majd az alkalmazásadatok frissítésére. Ez a funkció a következő forgatókönyvek esetében használható:

- Az alkalmazásadatoknak a későbbi folyamatokban való ismételt felhasználásának elkerülésére az alkalmazás adatait az elektronikus dokumentumok létrehozása után azonnal megjelölheti. A fizetési tranzakciókat például azonnal megjelölheti már feldolgozottként, amint bekerülnek a generált fizetési üzenetbe.
- Az ER-logika használatával létrehozott elektronikus dokumentumok feldolgozási részleteinek tárolására. Például egy ER-kifejezés használatával létrehozott egyedi fizetésiüzenet-azonosító. A kifejezés alapját az ER-párbeszédpanelen akkor megadott adatok adják, amikor az ER-formátumot dokumentumok létrehozásához futtatják.

Ezzel a funkcióval kapcsolatos további információért játssza le a Dokumentumok létrehozása alkalmazásadat-frissítéssel ER feladatútmutató-készletet (a 7.5.4.3 Informatikai szolgáltatások/megoldások összetevőinek beszerzése/kifejlesztése (10677) üzleti folyamat része), amelyek bemutatja az Intrastat jelentéskészítés és archiválás részleteit. A következő fájlok szükségesek a feladatútmutató egyes lépéseinek végrehajtásához. Töltse le és mentse ezeket a fájlokat a helyi számítógépre.

- [ER adatmodellkonfiguráció: Instrastat (modell)](https://go.microsoft.com/fwlink/?linkid=849038)
- [ER modell leképezésének konfigurációja: Intrastat (leképezés)](https://go.microsoft.com/fwlink/?linkid=849038)
- [ER formátumkonfiguráció: Intrastat (formátum)](https://go.microsoft.com/fwlink/?linkid=849038)

