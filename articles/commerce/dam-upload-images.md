---
title: Képek feltöltése
description: Ez a témakör azt mutatja be, hogyan tölthet fel képeket a Microsoft Dynamics 365 Commerce webhelykészítőben.
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
ms.openlocfilehash: f562d3376fde6a24e6a1e1a3f7f4192cf290ae90
ms.sourcegitcommit: 597476103bb695e3cbe6d9ffcd7a466400346636
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/20/2020
ms.locfileid: "4594284"
---
# <a name="upload-images"></a>Képek feltöltése

[!include [banner](includes/banner.md)]

Ez a témakör azt mutatja be, hogyan tölthet fel képeket a Microsoft Dynamics 365 Commerce webhelykészítőben.

## <a name="overview"></a>Áttekintés

A Commerce webhelykészítő médiatára segítségével képeket tölthet fel, egyesével vagy tömegesen mappákkal. Mindig a legnagyobb felbontással és minőséggel töltse fel a képet, mert a képátméretező összetevő automatikusan optimalizálja a képet különböző nézetablakok és töréspontok számára.

### <a name="image-information-specified-during-upload"></a>A feltöltéskor megadott képinformáció

Kép feltöltésekor meg lehet adni a következő adatokat.

- **Cím, helyettesítő szöveg, leírás, kulcsszavak**: a kép vagy a képek metaadatai. A cím és a helyettesítő szöveg kötelező értékek.
- **Kategóriaválasztás**:
    - **Nincs**: az e-kereskedelmi leírás képéhez vagy képekhez használatos.
    - **Termék, kategória, vevő, alkalmazott, katalógus**: Dynamics 365 Commerce omnicsatornás képhez vagy képekhez használatos.
- **Eszközök közzététele feltöltés után**: Ha ez a jelölőnégyzet be van jelölve, akkor a képet vagy a képeket a feltöltés után azonnal közzéteszi a program.

> [!NOTE]
> A kiválasztott kategóriába tartozó képeszközöket is automatikusan címkézik a kategóriával, hogy egy adott kategóriába tartozó eszközök keresésekor támogassa a keresést.

### <a name="naming-conventions-for-omni-channel-images"></a>Az omnicsatornás képek elnevezési konvenciói 

Ha a médiatárat állította be az omnicsatornás képek háttereként, akkor képkategóriákkal jelezheti, melyik kategóriához tartozik a feltöltött kép. A követendő elnevezési szabállyal biztosítható, hogy a képeket más csatornák megfelelően kérik le, pl. pénztár (POS).

Az alapértelmezett elnevezési konvenció a kategória alapján változik:
- Katalóguskép: "**/Catalogs/\{LanguageId\}/\{CatalogName\}.jpg**"
- Kategóriaképek: "**/Categories/\{CategoryName\}.png**"
- Vevői képek: "**/Customers/\{CustomerNumber\}.jpg**"
- Alkalmazotti képek: "**/Workers/\{WorkerNumber\}.jpg**"
- Termékképek: "**/Products/\{ProductNumber\}_000_001.png**"
    - A 001 a kép sorszáma, amely lehet 001, 002, 003, 004 vagy 005
- Termékváltozat-képek: "**/Products/\{ProductNumber\}\_\{Size\}\_\{Color\}\_\{Style\}\_000_001.png**"

## <a name="upload-an-image"></a>Kép feltöltése

Ha képet szeretne feltölteni a webhelykészítőbe, hajtsa végre az alábbi lépéseket.

1. A bal oldali navigációs ablakban válassza ki a **Médiatár** lehetőséget.
1. A parancssávon válassza a **Feltöltés \> Médiaelemek feltöltése**.
1. A fájlkezelő ablakban navigáljon a lapra, és válasszon ki egy vagy több képfájlt, majd válassza a **Megnyitás** lehetőséget.
1. A **médiaelem feltöltése** párbeszédpanelen írja be a szükséges címet és a helyettesítő szöveget.
1. Írja be a választható leírást és kulcsszavakat, és ha szükséges, válasszon ki egy kategóriát. 
1. Ha azonnal közzétenné a képeket a feltöltés után, jelölje be a **Médiatartalom közzététele a feltöltés után** jelölőnégyzetet.
1. Válassza ki az **OK** lehetőséget.

## <a name="upload-a-folder-of-images"></a>Képek mappa feltöltése

Ha tömegesen szeretne feltölteni egy képmappát a webhelykészítőbe, hajtsa végre az alábbi lépéseket.

1. A bal oldali navigációs ablakban válassza ki a **Médiatár** lehetőséget.
1. A parancssávon válassza a **Feltöltés \> Mappa feltöltése**.
1. A fájlkezelő ablakban navigáljon a feltöltendő mappára, és válasszon ki, majd válassza a **Megnyitás** lehetőséget.
1. A **médiatartalom feltöltése** párbeszédpanelen írja be a választható kulcsszavakat, és ha szükséges, válasszon ki egy kategóriát. 
1. Ha azonnal közzétenné a mappaképeket a feltöltés után, jelölje be a **Médiatartalom közzététele a feltöltés után** jelölőnégyzetet.
1. Válassza ki az **OK** lehetőséget.

## <a name="additional-resources"></a>További erőforrások

[Digitális eszközkezelés – áttekintés](dam-overview.md)

[Videó feltöltése](dam-upload-video.md)

[Fájlok feltöltése](dam-upload-files.md)

[Képek körülvágása](dam-crop-images.md)

[Képfókuszpontok testreszabása](dam-custom-focal-point.md)

[Statikus fájlok feltöltése és kiszolgálása](upload-serve-static-files.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]