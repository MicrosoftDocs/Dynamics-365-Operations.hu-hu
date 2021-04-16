---
title: Generált XML-fájlok felosztása méret és tartalommennyiség alapján
description: Ez a témakör arról tartalmaz tájékoztatást, hogy a fájl mérete és tartalomelem mennyisége alapján hogy lehet felosztani a létrehozott fájlokat.
author: NickSelin
ms.date: 05/25/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2018-04-01
ms.dyn365.ops.version: Release 8.0
ms.openlocfilehash: f39cb93f4ba2d41b145ed7cfa52da287ccac3df5
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5743557"
---
# <a name="split-generated-xml-files-based-on-file-size-and-content-quantity"></a>Generált XML-fájlok felosztása méret és tartalommennyiség alapján

[!include[banner](../includes/banner.md)]

Elektronikus jelentési (ER) formátumokat tervezhet kimenő dokumentumok XML-formátumú előállításához. Előfordul, hogy ezek a dokumentumok csak akkor fogadhatók el, ha megfelelnek speciális feltételeknek, például a fájl maximális mérete, vagy az egyes XML-csomópontok maximális száma. ER formátumok tervezhetők olyan elektronikus dokumentumok létrehozásához, amelyek megfelelnek az ilyen dokumentumokat kapók által megadott követelményeknek.

- A FÁJL formátuma elemhez meg lehet adni a fájl mérete korlátozását ER kifejezésként. Ha az ER-jelentés létrehozásakor a megadott korlátot túllépik, az ER befejezi az aktuális fájl létrehozását, és folytatja a következő fájl létrehozásával.
- Bármely XML-ELEM formátumhoz meg lehet adni az elemek száma korlátozását ER kifejezésként. Ha az ER-jelentés futtatásakor a létrehozás alatt levő fájlban az XML-csomópontok száma túllépi a megadott korlátot, az ER befejezi az aktuális fájl létrehozását, és folytatja a következő fájl létrehozásával.
- Bármely XML-SZEKVENCIA elemhez meg lehet adni a gyermek elemek száma korlátozását ER kifejezésként. Ha az ER-jelentés futtatásakor a létrehozott fájlban a formátum elem beágyazott XML-csomópontjainak száma túllépi a megadott korlátot, az ER befejezi az aktuális fájl létrehozását, és folytatja a következő fájl létrehozásával.
- Bármely XML-ELEM formátum elemet megjelölheti nem megtörőként. Ezzel a módszerrel egyetlen generált fájlban tárolhatja a formátum elem alatt létrehozott XML-csomópont beágyazott elemeit.

Az XML-ELEM és az XML-SZÁMSOROZAT formátum-elemek használata mellett az XML-csomópontok hozzáadásához a létrehozott fájlhoz, a nyers XML-formátum elemet is használhatja. Azonban a nyers XML-formátum elem használatával hozzáadott csomópontokat a rendszer nem veszi figyelembe az elemek számának számításakor, az elemek számára vonatkozó korlátozások kiértékelésekor.

Ha fájlcélokat állította be a FÁJL formátum elemhez, amely úgy van beállítva, hogy a létrehozott kimenetet ossza fel, valahányszor a megadott határértékeket eléri, minden létrehozott kimeneti elem külön fájlként lesz elküldve a beállított fájlcélra. Egyedi név adásához a fájloknak, amelyek a kimeneti felosztásával jönnek létre, konfigurálnia kell a FÁJL formátum elemhez egy ER kifejezést. Ha egy SZÁMSOROZAT típusú ER-adatforrást ad hozzá, a számsorozat minden felosztott kimenetnél növekszik.

Az ezzel a funkcióval kapcsolatos további tudnivalókért játssza le az **ER XML-fájlok felosztása méret és tartalommennyiség alapján** feladatútmutatót, amely része az **7.5.4.3 Informatikai szolgáltatások/megoldások összetevőinek beszerzése/kifejlesztése (10677)** üzleti folyamatnak, és letölthető innen: [Microsoft letöltőközpont](https://go.microsoft.com/fwlink/?linkid=874684). Ez a feladatútmutató végigvezeti egy ER formátum konfigurálásán az létrehozott fájlok felosztásához méret és tartalommennyiség alapján. A feladatútmutató befejezéséhez töltse le a következő fájlokat:

- [ER modellkonfiguráció - XmlFilesSplittingModel.xml](https://go.microsoft.com/fwlink/?linkid=874111)
- [ER-formátumkonfiguráció - XmlFilesSplittingFormat.xml](https://go.microsoft.com/fwlink/?linkid=874111)

## <a name="additional-resources"></a>További erőforrások
[Elektronikus jelentéskészítés (ER) céljai](electronic-reporting-destinations.md)

[Képletszerkesztő elektronikus jelentésekhez (ER)](general-electronic-reporting-formula-designer.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]