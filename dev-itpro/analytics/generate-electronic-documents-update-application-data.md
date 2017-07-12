---
title: "Elektronikus dokumentumok és alkalmazásadatok frissítése az Elektronikus jelentéskészítő eszköz használatával"
description: "Lehetőség van elektronikus jelentési (ER) formátumok tervezésére, amelyek kimenő elektronikus dokumentumok létrehozására használhatók a Finance and Operations alkalmazásban. Olyan ER-formátumokat is készíthet, amelyek a bejövő elektronikus dokumentumokat elemzik, és ezeknek a dokumentumoknak a tartalmát használják az alkalmazásadatok frissítésére."
author: kfend
manager: AnnBe
ms.date: 05/11/2017
ms.topic: article
ms.prod: 
ms.service: Lifecycle Services
ms.technology: 
ms.search.form: ERSolutionTable, ERVendorTable, ERWorkspace
audience: Developer, IT Pro
ms.reviewer: annbe
ms.search.scope: AX 7.2, Operations
ms.custom: 27621
ms.assetid: 018a11ae-854c-4f36-9358-8c39baca882d
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d37d20b26d8ae755a6c5a688afd1ad0541d1f693
ms.openlocfilehash: 7e4e0acb374fe091c0e099355204116345c62997
ms.contentlocale: hu-hu
ms.lasthandoff: 06/13/2017

---


Lehetőség van elektronikus jelentési (ER) formátumok tervezésére, amelyek kimenő elektronikus dokumentumok létrehozására használhatók a Finance and Operations alkalmazásban. Olyan ER-formátumokat is készíthet, amelyek a bejövő elektronikus dokumentumokat elemzik, és ezeknek a dokumentumoknak a tartalmát használják az alkalmazásadatok frissítésére. 

Ezzel a funkcióval egyetlen ER-formátum használható a kimenő elektronikus dokumentumok létrehozására, majd az alkalmazásadatok frissítésére. Ez a funkció a következő forgatókönyvek esetében használható:

- Az alkalmazásadatoknak a későbbi folyamatokban való ismételt felhasználásának elkerülésére az alkalmazás adatait az elektronikus dokumentumok létrehozása után azonnal megjelölheti. A fizetési tranzakciókat például azonnal megjelölheti már feldolgozottként, amint bekerülnek a generált fizetési üzenetbe.
- Az ER-logika használatával létrehozott elektronikus dokumentumok feldolgozási részleteinek tárolására. Például egy ER-kifejezés használatával létrehozott egyedi fizetésiüzenet-azonosító. A kifejezés alapját az ER-párbeszédpanelen akkor megadott adatok adják, amikor az ER-formátumot dokumentumok létrehozásához futtatják.

Ezzel a funkcióval kapcsolatos további információért játssza le a Dokumentumok létrehozása alkalmazásadat-frissítéssel ER feladatútmutató-készletet (a 7.5.4.3 Informatikai szolgáltatások/megoldások összetevőinek beszerzése/kifejlesztése (10677) üzleti folyamat része), amelyek bemutatja az Intrastat jelentéskészítés és archiválás részleteit. A következő fájlok szükségesek a feladatútmutató egyes lépéseinek végrehajtásához. Töltse le és mentse ezeket a fájlokat a helyi számítógépre.

- [ER adatmodellkonfiguráció: Instrastat (modell)](https://go.microsoft.com/fwlink/?linkid=849038)
- [ER modell leképezésének konfigurációja: Intrastat (leképezés)](https://go.microsoft.com/fwlink/?linkid=849038)
- [ER formátumkonfiguráció: Intrastat (formátum)](https://go.microsoft.com/fwlink/?linkid=849038)

