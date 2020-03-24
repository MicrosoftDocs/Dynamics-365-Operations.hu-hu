---
title: Videók feltöltése
description: Ez a témakör azt mutatja be, hogyan tölthet fel videókat a Microsoft Dynamics 365 Commerce webhelykészítőben.
author: psimolin
manager: annbe
ms.date: 03/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: 98cb4f9049509dd700cf38a5d176447f86e9c824
ms.sourcegitcommit: 567132f4e4f7a1d76dccf762068209a42c788b52
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/03/2020
ms.locfileid: "3097027"
---
# <a name="upload-videos"></a>Videók feltöltése

[!include [banner](includes/banner.md)]

Ez a témakör azt mutatja be, hogyan tölthet fel videókat a Microsoft Dynamics 365 Commerce webhelykészítőben.

## <a name="overview"></a>Áttekintés

A Commerce webhelykészítő médiatára segítségével videókat tölthet fel. Mindig a legnagyobb bitrátával és felbontással töltse fel a videót, mert a videót a program automatikusan átváltja különböző nézetablakok és töréspontok számára.

### <a name="video-information-specified-during-upload"></a>A feltöltéskor megadott videóinformáció

Videó feltöltésekor meg lehet adni a következő adatokat.

- **Cím, leírás, kulcsszavak**: a videó metaadatai.
- **Feliratok automatikus létrehozása**: meghatározza, hogy a rendszer automatikusan generálja-e a feliratokat a videóhoz.
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

[Kép fókuszpontok testreszabása](dam-custom-focal-point.md)
