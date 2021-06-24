---
title: Videók feltöltése
description: Ez a témakör azt mutatja be, hogyan tölthet fel videókat a Microsoft Dynamics 365 Commerce webhelykészítőben.
author: psimolin
ms.date: 06/09/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: e3579b54c58898b79c84406480a3b58f541c4621
ms.sourcegitcommit: 257437a57e146496a49782bc8aad179c92fbf6e8
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/11/2021
ms.locfileid: "6224538"
---
# <a name="upload-videos"></a>Videók feltöltése

[!include [banner](includes/banner.md)]

Ez a témakör azt mutatja be, hogyan tölthet fel videókat a Microsoft Dynamics 365 Commerce webhelykészítőben.

A Commerce webhelykészítő médiatára segítségével videókat tölthet fel. Mindig a legnagyobb bitrátával és felbontással töltse fel a videót, mert a videót a program automatikusan átváltja különböző nézetablakok és töréspontok számára.

### <a name="video-information-specified-during-upload"></a>A feltöltéskor megadott videóinformáció

Videó feltöltésekor meg lehet adni a következő adatokat.

- **Cím, leírás, kulcsszavak**: a videó metaadatai.
- **Feliratok automatikus létrehozása**: meghatározza, hogy a rendszer automatikusan generálja-e a feliratokat a videóhoz (csak az angol nyelv támogatott). 
- **Felirat**: meghatározza a használandó feliratokat.
- **Normál hang**: meghatározza a normál hangsáv használatát.
- **Miniatűr**: meghatározza a videoklip mintaképét. Ha nincs megadva, a rendszer automatikusan létrehozza.
- **Leíró hang**: meghatározza a leíró hangsáv használatát.

## <a name="upload-a-video"></a>Videó feltöltése

Ha videót szeretne feltölteni a webhelykészítőbe, hajtsa végre az alábbi lépéseket.

1. A bal oldali navigációs ablakban válassza ki a **Médiatár** lehetőséget.
1. A parancssávon válassza a **Feltöltés \> Médiaelemek feltöltése**.
1. A fájlkezelő ablakban navigáljon a lapra, és válasszon ki egy vagy több videofájlot, majd válassza a **Megnyitás** lehetőséget.
1. A **médiaelem feltöltése** párbeszédpanelen írja be a szükséges címet és a helyettesítő szöveget.
1. Írja be a választható leírást és kulcsszavakat, és ha szükséges, válasszon ki egy kategóriát. 
1. Ha azonnal közzétenné a képeket a feltöltés után, jelölje be a **Médiatartalom közzététele a feltöltés után** jelölőnégyzetet
1. Válassza ki az **OK** lehetőséget.

Ha egyszerre több típusú eszközt (például képeket és videókat) tölt fel, akkor a **Médiaelem feltöltése** párbeszédpanelen csak a kulcsszavakat lehet megadni, hogy a fájlok közzététele a feltöltés után azonnal történjen-e, és hogy a feliratok automatikusan megjelenjenek-e a videofájlok esetében. Minden eszköz ugyanazokat a kulcsszavakkal fog rendelkezni.

## <a name="additional-resources"></a>További erőforrások

[Digitális eszközkezelés – áttekintés](dam-overview.md)

[Képek feltöltése](dam-upload-images.md)

[Fájlok feltöltése](dam-upload-files.md)

[Képek körülvágása](dam-crop-images.md)

[Képfókuszpontok testreszabása](dam-custom-focal-point.md)

[Statikus fájlok feltöltése és kiszolgálása](upload-serve-static-files.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
