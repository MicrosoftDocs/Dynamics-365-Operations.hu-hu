---
title: Konfigurációk tervezése alkalmazásadatokkal rendelkező dokumentumok létrehozásához
description: Ez a témakör egy elektronikus dokumentumot létrehozó elektronikus jelentéskészítési (ER) konfigurációk megtervezését mutatja be. (1. rész – Konfigurációk importálása).
author: NickSelin
ms.date: 06/19/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9d3f528d48f345ec4b5cc2a46d7740cb6d0a36cd
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5751082"
---
# <a name="design-configurations-to-generate-documents-that-have-application-data"></a>Konfigurációk tervezése alkalmazásadatokkal rendelkező dokumentumok létrehozásához

[!include [banner](../../includes/banner.md)]

Az eljárás lépéseinek elvégzéséhez először hajtsa végre az „ER – Dokumentumok létrehozása alkalmazásadat-frissítéssel (1. rész: Konfigurációk importálása)” eljárást.



Az eljárás lépései az elektronikus dokumentumot létrehozó elektronikus jelentési (ER) konfigurációk megtervezését mutatják be. Ebben az eljárásban futtatjuk az importált ER-formátumkonfigurációkat a Litware, Inc. mintavállalatra vonatkozóan, elektronikus dokumentumok létrehozása érdekében.



Ez az eljárás a rendszergazda vagy az elektronikus jelentések fejlesztője szerepkör rendelkező felhasználók számára készült. A lépések a DEMF-adathalmazzal hajthatók végre. 



Mielőtt hozzálátna, módosítsa a DEMF vállalat országfüggő környezetét DEU (Németország) beállításról BEL (Belgium) beállításra. Kattintson a Szervezet felügyelete > Szervezetek > Jogi személyek lehetőségre az országkód frissítéséhez a DEMF jogi személy elsődleges címében. Indítsa újra az alkalmazást.


## <a name="run-imported-er-format"></a>Importált ER-formátum futtatása
1. Nyissa meg a következőt: Szervezeti adminisztráció > Elektronikus jelentés > Konfigurációk.
2. A fastruktúrában bontsa ki az „Instrastat (model)” elemet.
3. A fastruktúrában jelölje ki a következőt: „Intrastat (model)\Intrastat (format)”.
4. Kattintson a Futtatás elemre.
    * Az Intrastat-jelentés elkészítéséhez futtassa az ER-formátumkonfiguráció piszkozatverzióját.  
5. Az Fájlnév megadása mezőbe írja be a következőt: 'intrastat.xml'.
    * Adja meg a fájl nevét.  
6. Kattintson az OK gombra.
    * Tekintse át a létrehozott XML-fájlt.  
7. Zárja be a lapot.
8. Ugorjon az Adó > Nyilatkozatok > Külkereskedelem > Intrastat pontra.
    * Nyissa meg ezt az űrlapot azon Intrastat-tranzakciók megtekintéséhez, amelyek szerepelnek a létrehozott elektronikus dokumentumban.  
9. Kattintson az Intrastat archívum elemre.
    * Mivel a végrehajtott ER-formátum nem tartalmazza az alkalmazásadatok módosításának semmilyen beállítását, a rendszer nem archiválta a kitöltött Intrastat-jelentés részleteit.  
10. Zárja be a lapot.
11. Zárja be a lapot.



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]