---
title: Tárgyi eszközök kezelési munkaterülete
description: Ez a cikk a tárgyieszköz-kezelés munkaterületével kapcsolatban tartalmaz tájékoztatást. A munkaterület a rendszerben megadott tárgyi eszközökhöz kapcsolódó információkat jelenít meg. Összesítés és analitika nézet tartalmaz.
author: moaamer
ms.date: 01/12/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetWorkspace
audience: Application User
ms.reviewer: kfend
ms.assetid: ''
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: 95b45a91cd201a6d3a4817c315053e98a7693e05
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8894055"
---
# <a name="fixed-asset-management-workspace"></a>Tárgyi eszközök kezelési munkaterülete

[!include [banner](../includes/banner.md)]

A **Tárgyi eszközök kezelése** munkaterület a rendszerben megadott tárgyi eszközökhöz kapcsolódó információkat jelenít meg. A munkaterület összesítés és analitika nézet tartalmaz. A **Saját munka** lap megjeleníti az összegző lapokat, a tárgyi eszköz részleteit, és a kapcsolódó információkat az aktuális vállalat tárgyi eszközeire nézve. Emellett közvetlenül a munkaterületen is hozzáadható az analitika a Power BI analitika szakaszához. Az **Analitika – összes vállalat** lap a Microsoft Power BI képességeit használja az összes vállalat tárgyi eszközeihez kapcsolódó vizualizációk megjelenítéséhez.

## <a name="my-work"></a>Saját munka

### <a name="summary"></a>Összegzés

Az **Összefoglaló** szakasz csempéi áttekintést nyújtanak a tárgyi eszközökről. Az információk közé tartoznak a következők mérőszámai: még be nem szerzett tárgyi eszközök, a folyó évben beszerzett tárgyi eszközök és a folyó évben kivezetett eszközök. Az **Összefoglaló** szakasz lehetővé teszi a **Tárgyi eszköz** listalap, a kötegelt értékcsökkenési javaslat és a tárgyieszköz-napló gyors elérését.

### <a name="find-fixed-assets"></a>Tárgyi eszközök keresése

A **Tárgyi eszközök keresése** szakasz az eszközök gyors megkeresését teszi lehetővé a tárgyi eszköz száma, a csoport, a név, a hely vagy a felelős személy megadásával. A keresési feltételeknek megfelelő összes eszköz meg fog jelenni a listában.

A listából a következő lapokat tekintheti meg:

 - A tárgyi eszköz **Részletek** lap
 - A tárgyi eszközhöz társított összes könyv **Könyvek** lapja
 - **Tárgyieszköz-értékelések** lap

### <a name="valuations"></a>Értékelések

A **Tárgyieszköz-értékelések** lap segítségével egy oldalon tekinthetők meg a tárgyi eszközzel kapcsolatos legfontosabb információk, valamint a tárgyi eszközhöz társított minden könyv adatait. Az **Egyenlegek** lehetőség a lap bal felső részén a tárgyi eszközhöz társított minden egyes könyv értékelését jeleníti meg. Az értékekből lefúrhat, és megtekintheti az összesített értéket alkotó részletezett tranzakciókat. A **Profil** lehetőség a lap bal felső részén a tárgyi eszközhöz társított minden egyes könyv értékcsökkenési ütemezését jeleníti meg.

A **Tárgyieszköz-értékelések** laphoz hozzáférhet a **Tárgyi eszközök kezelése** munkaterületről vagy a **Tárgyi eszköz** listaoldalról.

### <a name="related-information"></a>Kapcsolódó információ

Közvetlenül navigálhat az **Áfakönyv-beállítások** lapra, a **Tárgyi eszközök tranzakcióinak lekérdezése** lapra, valamint számos jelentéshez, a munkaterület **Kapcsolódó információk** szakaszában található hivatkozások segítségével.

### <a name="analytics--all-companies"></a>Elemzés – az összes vállalat

Az **Analitika** lap fontos mérőszámokat jelenít meg a rendszerben megtalálható összes jogi személynél levő tárgyi eszközökről. Az ezen lapon való hozzáférést a Tárgyieszköz-elemzés megtekintése az összes vállalat esetében biztonsági jogosultságok vezérlik.

Az alábbi táblázat mutatja be az egyes jelentésoldalakon rendelkezésre álló megjelenítéseket.

| Jelentéslap            | Megjelenítés        |
|------------------------|----------------------|
| Tárgyieszköz-értékelések | Teljes nettó könyv szerinti érték |
| Tárgyieszköz-értékelések | Nettó könyv szerinti érték tárgyieszközcsoportonként |
| Tárgyieszköz-értékelések | Beszerzési értékek |
| Tárgyieszköz-értékelések | Kivezetési értékek |
| Tárgyieszköz-értékelések | Tárgyi eszköz részletei |
| Értékelési leképezések        | Teljes nettó könyv szerinti érték |
| Értékelési leképezések        | Tárgyi eszközök helye |
| Értékelési leképezések        | Tárgyi eszköz részletei |

Ha analitikákat is meg szeretne jeleníteni az adatokkal, akkor először frissítenie kell az AssetTransactionMeasure összesítő mértéket az **Entitástár** lapon.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
