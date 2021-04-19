---
title: Kisegítő funkciók és lehetőségek
description: Ez a témakör a Microsoft Dynamics 365 Commerce különböző verzióiban rendelkezésre álló kisegítő lehetőségekről és segédprogramokról nyújt tájékoztatást.
author: BrianShook
ms.date: 04/14/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 13f035a080eb41b4a69cc31b7275d87a5836c686
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5796318"
---
# <a name="accessibility-features-and-capabilities"></a>Kisegítő funkciók és lehetőségek

[!include [banner](includes/banner.md)]

Ez a témakör a Microsoft Dynamics 365 Commerce különböző verzióiban rendelkezésre álló kisegítő lehetőségekről és segédprogramokról nyújt tájékoztatást.

A kisegítő lehetőségek és képességek funkcionális eszközöket biztosítanak a felhasználók számára, hogy hozzáférjenek és végrehajthassanak műveleteket a céljaik elérése érdekében. A felhasználók ezen széles köre segítőeszközöket igényel hallás, látás, mozgékonyság vagy idegrendszeri problémák leküzdése érdekében.

A Dynamics 365 Commerce különböző funkcióival úgy építheti fel a webhelyét, hogy az magában foglalja a kisegítő funkciókat. A webhely tervezésekor vegye figyelembe a kisegítő lehetőségek azon területeit, amelyeket a [Microsoft kisegítő lehetőségek központja](https://www.microsoft.com/accessibility) említ. 

Ez a témakör a kisegítő lehetőségek további területeit ismerteti, amelyeket a Dynamics 365 Commerce használata során figyelembe kell vennie.

## <a name="image-alt-text"></a>Képek alternatív szövege

A Dynamics 365 Commerce egy beépített digitális eszközkezelő rendszerrel követi a webhelyén használt kép- és videóeszközöket. A képfeliratok, a leírások és az alternatív szöveg hozzáadhatók a kép kijelölt vagy feltöltött kép tulajdonságpanelén.

## <a name="video-accessibility"></a>Videós kisegítő lehetőségek

A Dynamics 365 Commerce digitáliseszköz-kezelő rendszer számos kisegítő szolgáltatást támogat a videótartalom számára. A következő tábla felsorol néhány példát.

| Videófunkció               | Leírás |
|-----------------------------|-------------|
| Kódolt feliratok (CC)      | A siket vagy csökkent hallóképességű felhasználók számára segítséget nyújthat a videó hang- és hangleíró elemeihez megjeleníthető szöveg |
| Feliratok                   | Feliratfájlok, amelyek az adott környezet elemeinek vagy a képernyőn megjelenő párbeszéd szövegét mutatják |
| Hangátiratok           | A kimondott szavak szöveges átirata, amely a videóeszköz hangjából kerül előállításra |
| Hangos leírás           | Egy nem elsődleges hangcsatorna, amely a képernyőn megjelenő tartalmat vagy környezetet írja le |
| Minimális korkapu            | Egy attribútum, amely tárolni tudja azt a minimális életkort, amelyet a megtekintőnek el kell érnie egy videó megtekintéséhez (csak metaadatok) |

### <a name="configure-video-accessibility-elements"></a>A videó kisegítő lehetőségeinek konfigurálása

A Commerce alkalmazásban, a webhelye **Médiatár** részében feltölthet videóeszközöket, amelyek külön fájlokkal rendelkeznek a feliratozáshoz, a hagyományos hanghoz és a leíró hanghoz. A kódolt feliratok automatikusan is generálhatók a videóeszköz feltöltésekor.

#### <a name="generate-or-upload-closed-caption-files-during-video-asset-upload"></a>A kódolt feliratok létrehozása vagy feltöltése videóeszköz feltöltése során

Ha azt szeretné, hogy a videó feltöltésekor a program automatikusan létrehozza a kódolt felirat fájlját, kövesse ezt a lépést.

- Az **Eszközfeltöltés** párbeszédpanelen jelölje be a **Kódolt feliratok automatikus generálása** lehetőséget. Ha kódoltfelirat-fájlt generál, a kódoltfelirat-fájl fájlválasztója nem lesz elérhető a párbeszédpanelen.

Ha a videó feltöltésekor manuálisan szeretné feltölteni a kódolt felirat fájlját, kövesse ezt a lépést.

- Az **Eszközfeltöltés** párbeszédpanelen törölje a **Kódolt feliratok automatikus generálása** kijelölését.

Ha a videóhoz hagyományos hangot vagy leíró hangfájlokat szeretne feltölteni, használja az **Eszközfeltöltés** párbeszédpanel fájlválasztóját.

> [!NOTE]
> A kódolt felirat, a hagyományos hang és a leíró hangeszközök a videóeszköz feltöltése után is hozzáadhatók. Lépjen az **Médiatár** menüpontba, válassza ki a videóeszközt, és a kivételhez válassza a **Szerkesztés** parancsot. Ezután a videóeszköz tulajdonságok panelén töltse fel a további eszközöket.

#### <a name="edit-cc-and-audio-transcript-files"></a>CC és hangátirat fájlok szerkesztése

A CC és a hangátirat fájlokat közvetlenül a szerkesztőeszközből lehet szerkeszteni. A szerkesztés során a videólejátszás elérhető.

A CC és a hangátirat fájljainak szerkesztéséhez hajtsa végre az alábbi lépéseket.

1. Nyissa meg a **Médiatár** elemet, és válassza ki a videoeszköz fájlnevét. Megjelenik a kódolt felirat és az átirata tartalomszerkesztője.
1. Válassza ki a **Szerkesztés** opciót.
1. Szerkessze a kódolt felirat vagy az átirat szövegét.
1. Ha végzett, válassza a **Mentés** lehetőséget, majd válassza **Szerkesztés befejezése** lehetőséget.
1. Ha készen áll a közzétételre, válassza a **Közzététel** lehetőséget.

#### <a name="set-the-minimum-age-attribute"></a>A minimális életkor attribútum beállítása

A **Minimális életkor** metaadat-attribútumot a videóeszközökhöz lehet társítani.

A videóeszköz **Minimális életkor** attribútumának beállításához kövesse az alábbi lépéseket.

1. Nyissa meg az **Médiatár** elemet, és jelölje ki a videóeszközt.
1. Válassza ki a **Szerkesztés** opciót.
1. A videóeszköz tulajdonságpanelén állítsa be a **Minimális életkor** attribútumot.

> [!NOTE]
> A tulajdonságpanel csak a metaadat-attribútum értékének beállítására és tárolására használatos. Testreszabott modulokat kell létrehozni, hogy használja ezt az attribútumot a lejátszás szabályozásához.

## <a name="additional-resources"></a>További erőforrások

[Űrlapok, termékek és vezérlők hozzáférhetősége](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/user-interface/enable-accessibility)

[Microsoft kisegítő lehetőségek központja](https://www.microsoft.com/accessibility)

[Dynamics 365 kisegítő lehetőségek központja](https://docs.microsoft.com/dynamics365/get-started/accessibility/index)

[Megfelelőség áttekintése](compliance-overview.md)

[Cookie-k megfelelősége](cookie-compliance.md)

[Adatvédelmi irányelv oldalának hozzáadása](add-privacy-page.md)

[Nyomon követett tartalmi változásokhoz társított felhasználói azonosítók kicserélése](replace-IDs-tracked-changes.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
