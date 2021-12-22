---
title: Képek feltöltése
description: Ez a témakör azt mutatja be, hogyan tölthet fel képeket a Microsoft Dynamics 365 Commerce webhelykészítőben.
author: psimolin
ms.date: 12/03/2021
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
ms.openlocfilehash: 3b99aeff7eafd788c19204e22dbfc61f45b25408
ms.sourcegitcommit: 5f5a8b1790076904f5fda567925089472868cc5a
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/03/2021
ms.locfileid: "7891522"
---
# <a name="upload-images"></a>Képek feltöltése

[!include [banner](includes/banner.md)]

Ez a témakör azt mutatja be, hogyan tölthet fel képeket a Microsoft Dynamics 365 Commerce webhelykészítőben.

A Commerce webhelykészítő médiatára segítségével képeket tölthet fel, egyesével vagy tömegesen mappákkal. Mindig a legnagyobb felbontással és minőséggel töltse fel a képet, mert a képátméretező összetevő automatikusan optimalizálja a képet különböző nézetablakok és töréspontok számára.

### <a name="image-information-specified-during-upload"></a>A feltöltéskor megadott képinformáció

Kép feltöltésekor meg lehet adni a következő adatokat.

- **Cím, helyettesítő szöveg, leírás, kulcsszavak**: a kép vagy a képek metaadatai. A cím és a helyettesítő szöveg kötelező értékek.
- **Kategóriaválasztás**:
    - **Nincs**: az e-kereskedelmi leírás képéhez vagy képekhez használatos.
    - **Termék, kategória, vevő, alkalmazott, katalógus**: Dynamics 365 Commerce omnicsatornás képhez vagy képekhez használatos.
- **Eszközök közzététele feltöltés után**: Ha ez a jelölőnégyzet be van jelölve, akkor a képet vagy a képeket a feltöltés után azonnal közzéteszi a program.

> [!NOTE]
> - A kiválasztott kategóriába tartozó képeszközöket is automatikusan címkézik a kategóriával, hogy egy adott kategóriába tartozó eszközök keresésekor támogassa a keresést.
> - A termék részletező lapjai dinamikusan generálják az Alt Text szöveget a terméknév használatával, így a termékkép Helyettesítő szövegének módosítása nem fogja befolyásolni **a** megjelenített **képet**.

### <a name="naming-conventions-for-omni-channel-images"></a>Az omnicsatornás képek elnevezési konvenciói 

Ha a médiatárat állította be az omnicsatornás képek háttereként, akkor képkategóriákkal jelezheti, melyik kategóriához tartozik a feltöltött kép. A követendő elnevezési szabállyal biztosítható, hogy a képeket más csatornák megfelelően kérik le, pl. pénztár (POS).

Az alapértelmezett elnevezési konvenció a kategória alapján változik:
- Katalóguskép: "**/Catalogs/\{LanguageId\}/\{CatalogName\}.jpg**"
- Kategóriaképek: "**/Categories/\{CategoryName\}.png**"
- Vevői képek: "**/Customers/\{CustomerNumber\}.jpg**"
- Alkalmazotti képek: "**/Workers/\{WorkerNumber\}.jpg**"
- A termékképek neve legyen **"/Products/\{ProductNumber\}\_000_001.png"**
    - A 001 a kép sorszáma, amely lehet 001, 002, 003, 004 vagy 005
- Termékváltozat-képek: „**/Products/\{ProductNumber\} \^ \{Style\} \^ \{Size\} \^ \{Color\} \^\_000_001.png**”
    - Például: 93039 \^ &nbsp;\^ 2 \^ Black \^\_000_001.png
- A konfigurációs dimenzióval rendelkező termékváltozatok képeit a „**/Products/\{ProductNumber\} \^ \{Configuration\}\_000_001.png**” névvel kell ellátni.
    - Például: 93039 \^ LB8017_000_001.png

> [!NOTE]
> A termékváltozat képeinél, ha a dimenzió értéke üres, a fájlnévben a pontok között két szóköznek kell lennie.

A fenti példák az alapértelmezett konfigurációt használják. Az elválasztó karakter és a méretek konfigurálhatók, és a pontos elnevezések telepítésenként eltérőek lehetnek. A szükséges pontos elnevezési konvenció azonosításának egyik módszere, hogy a böngésző fejlesztői konzolján keresztül megvizsgálja a termékváltozat képkérelmeit, miközben a termék méreteit megváltoztatja az áruház termékadatlapján (PDP).

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
