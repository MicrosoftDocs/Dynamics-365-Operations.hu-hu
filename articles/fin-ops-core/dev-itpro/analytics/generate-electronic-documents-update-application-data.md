---
title: Elektronikus dokumentumok létrehozása létrehozása és alkalmazásadatok frissítése ER használatával.
description: Lehetőség van elektronikus jelentési (ER) formátumok tervezésére, amelyek kimenő elektronikus dokumentumok létrehozására használhatók az alkalmazásban. Olyan ER-formátumokat is készíthet, amelyek a bejövő elektronikus dokumentumokat elemzik, és ezeknek a dokumentumoknak a tartalmát használják az alkalmazásadatok frissítésére.
author: NickSelin
manager: AnnBe
ms.date: 11/01/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERSolutionTable, ERVendorTable, ERWorkspace
audience: Developer, IT Pro, Application user
ms.reviewer: kfend
ms.custom: 27621
ms.assetid: 018a11ae-854c-4f36-9358-8c39baca882d
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4b9e17d67c437d384ab941d28b8d5ce2b0e3738f
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/05/2020
ms.locfileid: "4688388"
---
# <a name="generate-electronic-documents-and-update-application-data-by-using-er"></a>Elektronikus dokumentumok létrehozása létrehozása és alkalmazásadatok frissítése ER használatával.

[!include [banner](../includes/banner.md)]

Lehetőség van elektronikus jelentési (ER) formátumok tervezésére, amelyek kimenő elektronikus dokumentumok létrehozására használhatók az alkalmazásban. Olyan ER-formátumokat is készíthet, amelyek a bejövő elektronikus dokumentumokat elemzik, és ezeknek a dokumentumoknak a tartalmát használják az alkalmazásadatok frissítésére.

Ezzel a funkcióval egyetlen ER-formátum használható a kimenő elektronikus dokumentumok létrehozására, majd az alkalmazásadatok frissítésére. Ez a funkció a következő forgatókönyvek esetében használható:

- Az alkalmazásadatoknak a későbbi folyamatokban való ismételt felhasználásának elkerülésére az alkalmazás adatait az elektronikus dokumentumok létrehozása után azonnal megjelölheti. A fizetési tranzakciókat például azonnal megjelölheti már feldolgozottként, amint bekerülnek a generált fizetési üzenetbe.
- Az ER-logika használatával létrehozott elektronikus dokumentumok feldolgozási részleteinek tárolására. Például egy ER-kifejezés használatával létrehozott egyedi fizetésiüzenet-azonosító. A kifejezés alapját az ER-párbeszédpanelen akkor megadott adatok adják, amikor az ER-formátumot dokumentumok létrehozásához futtatják.

Ezzel a funkcióval kapcsolatos további információért játssza le a Dokumentumok létrehozása alkalmazásadat-frissítéssel ER feladatútmutató-készletet (a 7.5.4.3 Informatikai szolgáltatások/megoldások összetevőinek beszerzése/kifejlesztése (10677) üzleti folyamat része), amelyek bemutatja az Intrastat jelentéskészítés és archiválás részleteit. A következő fájlok szükségesek a feladatútmutató egyes lépéseinek végrehajtásához. Töltse le és mentse ezeket a fájlokat a helyi számítógépre.

- [ER adatmodellkonfiguráció: Instrastat (modell)](https://go.microsoft.com/fwlink/?linkid=849038)
- [ER modell leképezésének konfigurációja: Intrastat (leképezés)](https://go.microsoft.com/fwlink/?linkid=849038)
- [ER formátumkonfiguráció: Intrastat (formátum)](https://go.microsoft.com/fwlink/?linkid=849038)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]