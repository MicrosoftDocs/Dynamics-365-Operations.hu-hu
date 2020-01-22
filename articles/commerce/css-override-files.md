---
title: A CSS felülíró fájljainak használata
description: Ez a témakör ismerteti, hogy miért, mikor és hogyan kell használni az egymásba ágyazott stíluslapok (CSS) felülíró fájljait a Microsoft Dynamics 365 Commerce alkalmazásban.
author: phinneyridge
manager: annbe
ms.date: 12/12/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.search.region: Global
ms.search.industry: ''
ms.author: niholman
ms.search.validFrom: 2019-12-12
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: b5a50fc0c9060117cdddc0875446afc2edc12a11
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/20/2019
ms.locfileid: "2915439"
---
# <a name="work-with-css-override-files"></a>A CSS felülíró fájljainak használata

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Ez a témakör ismerteti, hogy miért, mikor és hogyan kell használni az egymásba ágyazott stíluslapok (CSS) felülíró fájljait a Microsoft Dynamics 365 Commerce alkalmazásban.

## <a name="overview"></a>Áttekintés

Az állandó webhelystílusokat általában a webhely témáján keresztül kell kezelni. A témák biztosítják az alapvető CSS- és stílusbeállításokat a webhely minden oldala esetén. A témák az Dynamics 365 Commerce online szoftverfejlesztői készlet (SDK) segítségével hozhatók létre, és a webhelyekre a Microsoft Dynamics Lifecycle Services (LCS) szolgáltatáson keresztül vannak telepítve. Az SDK téma-hibakeresés képességei és modulinterfész-konfigurációi segítenek a webhely fejlesztőinek testreszabható és összetartó webhelytervcsomagok létrehozásában. Ha ezeket a tervezési csomagokat egy webhelyre telepítik, a webhelykészítők a tartalom webhelyfejlesztés helyett a tartalom létrehozására, szerkesztésére és közzétételére összpontosíthatnak.

Tekintettel egy téma szokásos életciklusára, a függőség a fejlesztőktől, hogy elvégezzék a stílusváltoztatásokat SDK- és LCS-telepítési folyamaton keresztül, bizonyos esetekben akadályozó tényező lehet. A webhely prototípusai és gyorsjavításai nehézkesnek tűnhetnek, ha az SDK nincs konfigurálva, vagy nincs ideje megvárni az LCS telepítését.

Ezekben az esetekben a CSS felülbírálási fájljai segíthetnek. A Commerce szerzői eszközeiben a hitelesített felhasználók feltölthetnek egy CSS fájlt, megtekinthetik az előnézetét, majd aktiválhatják a webhely témájának felülbírálásához. Az e feletti SDK- vagy az LCS-telepítésre nincs szükség. A CSS felülírási fájlban megadott felülírások lehetnek olyan kicsik, mint egy szövegstílus módosítása vagy olyan széles körűek, mint a teljes márka átalakítása.

A CSS felülíró fájlok használata előtt vegye figyelembe a következő korlátozásokat:

- Egyszerre csak CSS felülíró fájl lehet aktív a webhelyen. Ezért az összes aktív felülírásnak fájlnak egyetlen felülíró fájlban kell lennie.
- Bár megtekintheti a felülírásokat a Commerce szerzői eszközeiben, nincs dedikált hibakereső funkció, amely segít azonosítani a felülírási hibákat. Más szavakkal, ha CSS felülírási fájlokat használ, akkor nem ugyanazzal a eszközkészlettel rendelkezik, mint amit az SDK a modul- és a szerzői érvényesítéshez biztosít.

Mindazonáltal a CSS felülbíráló fájlok segítségével gyorsan elkészítheti egy terv prototípusát vagy végrehajthat egy gyorsjavítást a teljes téma frissítésének kifejlesztése és telepítése előtt.

## <a name="create-a-css-override-file"></a>CSS felülíró fájl létrehozása

CSS felülírási fájl létrehozásához használhat bármilyen integrált fejlesztőkörnyezetet (IDE), szövegszerkesztőt vagy forráskód-szerkesztőt. A szokásos megközelítés szerint a böngészőben szabványos webes hibakeresőjének segítségével azonosíthatja a stílusválasztókat, tulajdonságokat és értékeket a meglévő webhelyen. A legtöbb böngésző lehetővé teszik az értékek módosítását és a hibakeresőben való előnézetét. Miután azonosította a kívánt változtatásokat, mentheti azokat a saját CSS fájljába.

## <a name="upload-a-css-override-file"></a>CSS felülírási fájl feltöltése

Ha fel szeretne tölteni egy CSS fájlt a webhelyére a Commerce alkalmazásban, kövesse az alábbi lépéseket.

1. A szerkesztési eszközökben nyissa meg a webhelyét.
1. A bal oldali navigációs ablakban válassza ki a **Terv** lehetőséget.

    > [!NOTE]
    > A használt Commerce szerkesztési eszközök verziószámától függően előfordulhat, hogy ki kell bontania a **Beállítások** lehetőséget a navigációs ablaktáblán, mielőtt kiválasztaná a **Terv** lehetőséget.

1. A fő tervezőablak tetején jelölje ki a **CSS felülírás** lapot, ha még nincs bejelölve.
1. A **Rendelkezésre álló CSS felülírások** alatt válassza a **CSS fájl feltöltése** lehetőséget. Megjelenik egy fájlkezelő ablak.
1. A fájlkezelő programban tallózással keresse meg és válassza ki a CSS fájlt, majd kattintson a **Megnyitás** lehetőségre. A feltöltött CSS fájl most már a **Rendelkezésre álló CSS felülírások** alatt jelenik meg.

## <a name="preview-a-css-override-file"></a>CSS felülírási fájl előnézetének megtekintése

A CSS felülírási fájl előzetes megtekintéséhez kövesse az alábbi lépéseket, mielőtt aktiválná az éles webhelyén.

1. A bal oldali navigációs ablaktáblán válassza ki a **Terv** elemet, majd a **CSS felülírása** lapon, a **Rendelkezésre álló CSS felülírások** alatt keresse meg az előzetesként megtekinteni kívánt CSS-t.
1. A CSS fájlnév mellett válassza ki a **Webhely előnézete** lehetőséget.
1. A **Válasszon egy URL-t** párbeszédpanelen válassza ki annak a webhelynek az URL-címét, amelyre alkalmazni szeretné a felülírást, majd kattintson az **OK**gombra.
1. Ha a kiválasztott URL-címnek több változata van, válassza ki a kívánt változatot a megjelenő **Előnézet változatai** párbeszédpanelen.

Egy új böngésző fül vagy ablak nyílik meg, ahol érvényesítheti a stílusfelülírásokat a webhelyen. Az URL-címet megoszthatja más hitelesített Commerce-felhasználókkal véleményezés és visszajelzés céljából.

## <a name="activate-a-css-override-file-on-your-live-site"></a>A CSS felülírási fájl aktiválása az élő webhelyen

Miután megtekintette és jóváhagyta a CSS felülbíráló fájlt, aktiválhatja azt az éles webhelyen.

> [!NOTE]
> Egyszerre csak egy CSS felülíró fájl lehet aktív a webhelyen. Ha aktivál egy új felülírási fájlt, az előző felülírási fájl inaktiválódik. Ezért győződjön meg arról, hogy minden szükséges felülírás megtalálható egyetlen CSS felülírási fájlban.

Egy CSS felülírási fájl aktiválásához kövesse az alábbi lépéseket.

1. A bal oldali navigációs ablaktáblán válassza ki a **Terv** elemet, majd a **CSS felülírása** lapon, a **Rendelkezésre álló CSS felülírások** alatt keresse meg az előzetesként megtekinteni kívánt CSS-t.
1. A CSS fájlnév alatt válassza ki az **Aktiválás** lehetőséget. A felülíró fájl azonnal aktívvá válik az éles webhelyen.

## <a name="deactivate-a-css-override-file-on-your-live-site"></a>A CSS felülírási fájl deaktiválása az élő webhelyen

A webhelyén lévő CSS felülíró fájlok inaktiválásához kövesse az alábbi lépéseket.

1. A bal oldali navigációs ablaktáblán válassza ki a **Terv** elemet, majd a **CSS felülírása** lapon, a **Rendelkezésre álló CSS felülírások** alatt keresse meg az inaktiválni kívánt CSS-t.
1. A CSS fájlnév alatt válassza ki az **Inaktiválás** lehetőséget. A felülíró fájl azonnal inaktívvá válik az éles webhelyen.

> [!TIP]
> Az CSS felülíró fájlok további beállításainak eléréséhez jelölje ki a három pontot (**...**) a CSS fájl neve mellett. A **Letöltés**, **Átnevezés** és **Csere** beállítások hasznosak a meglévő CSS felülíró fájlok gyors módosításnál.

## <a name="additional-resources"></a>További erőforrások

[Embléma hozzáadása](add-logo.md)

[Webhely témájának kiválasztása](select-site-theme.md)

[Kedvencek ikon hozzáadása](add-favicon.md)

[Üdvözlő üzenet hozzáadása](add-welcome-message.md)

[Szerzői jogi értesítés hozzáadása](add-copyright-notice.md)

[Nyelvek hozzáadása a webhelyhez](add-languages-to-site.md)

[Parancsfájl hozzáadása a webhely oldalaihoz a telemetria támogatásához](add-telemetry.md)
