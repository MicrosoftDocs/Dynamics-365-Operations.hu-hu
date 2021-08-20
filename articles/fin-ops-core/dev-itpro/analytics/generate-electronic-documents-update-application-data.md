---
title: Elektronikus dokumentumok létrehozása létrehozása és alkalmazásadatok frissítése ER használatával.
description: Lehetőség van elektronikus jelentési (ER) formátumok tervezésére, amelyek kimenő elektronikus dokumentumok létrehozására használhatók az alkalmazásban.
author: NickSelin
ms.date: 04/23/2021
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: f5f78f3b36a1aebfb263d64ccf2293097eb9af6e6de1ab49de39b18e1c318950
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6765808"
---
# <a name="generate-electronic-documents-and-update-application-data-by-using-er"></a>Elektronikus dokumentumok generálása és alkalmazásadatok frissítése ER használatával

[!include [banner](../includes/banner.md)]

Lehetőség van elektronikus jelentési (ER) formátumok tervezésére, amelyek kimenő elektronikus dokumentumok létrehozására használhatók az alkalmazásban. Olyan ER-formátumokat is készíthet, amelyek a bejövő elektronikus dokumentumokat elemzik, és ezeknek a dokumentumoknak a tartalmát használják az alkalmazásadatok frissítésére.

Ezzel a funkcióval egyetlen ER-formátum használható a kimenő elektronikus dokumentumok létrehozására, majd az alkalmazásadatok frissítésére. Ez a funkció a következő forgatókönyvek esetében használható:

- Az alkalmazásadatoknak a későbbi folyamatokban való ismételt felhasználásának elkerülésére az alkalmazás adatait az elektronikus dokumentumok létrehozása után azonnal megjelölheti. A fizetési tranzakciókat például azonnal megjelölheti már feldolgozottként, amint bekerülnek a generált fizetési üzenetbe.
- Az ER-logika használatával létrehozott elektronikus dokumentumok feldolgozási részleteinek tárolására. Például egy ER-kifejezés használatával létrehozott egyedi fizetésiüzenet-azonosító. A kifejezés alapját az ER-párbeszédpanelen akkor megadott adatok adják, amikor az ER-formátumot dokumentumok létrehozásához futtatják.

Ezzel a funkcióval kapcsolatos további információért játssza le a Dokumentumok létrehozása alkalmazásadat-frissítéssel ER feladatútmutató-készletet (a 7.5.4.3 Informatikai szolgáltatások/megoldások összetevőinek beszerzése/kifejlesztése (10677) üzleti folyamat része), amelyek bemutatja az Intrastat jelentéskészítés és archiválás részleteit. A következő fájlok szükségesek a feladatútmutató egyes lépéseinek végrehajtásához. Töltse le és mentse ezeket a fájlokat a helyi számítógépre.

- [ER adatmodellkonfiguráció: Instrastat (modell)](https://download.microsoft.com/download/9/c/e/9ceeacbe-c13e-422e-96f2-594c4a6b45b7/Intrastatmodel.xml)
- [ER modell leképezésének konfigurációja: Intrastat (leképezés)](https://download.microsoft.com/download/2/1/d/21ddaaeb-64c5-4408-a35f-1ccb922d40a4/Intrastatmapping.xml)
- [ER formátumkonfiguráció: Intrastat (formátum)](https://download.microsoft.com/download/8/b/b/8bbb8891-e88d-4739-b92a-2d1d2fffcb79/Intrastatformat.xml)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
