---
title: A webhellyel kapcsolatos keresőmotor-optimalizálási (SEO) szempontok
description: Ez a cikk a webhely keresőprogram szerinti optimalizálási szempontokat tartalmaz a fejlesztéstől a termelés fejlesztésére.
author: psimolin
ms.date: 05/25/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgri
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.openlocfilehash: 6747df3c56fb05248210f78ebf2176a56ce78329
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8896901"
---
# <a name="search-engine-optimization-seo-considerations-for-your-site"></a>A webhellyel kapcsolatos keresőmotor-optimalizálási (SEO) szempontok


[!include [banner](includes/banner.md)]

Ez a cikk a webhely keresőprogram szerinti optimalizálási szempontokat tartalmaz a fejlesztéstől a termelés fejlesztésére.

## <a name="a-site-that-is-under-development"></a>Fejlesztés alatt álló webhely

Annak érdekében, hogy a keresőmotorok ne indexelnek fejlesztés alatt található webhelyet, **minden webhelyoldalon noindex** **és nofollow** metacímkének kell lennie. A helyes gyakorlat az, ha a MetaTags [modul alapján egy részletet hoznak létre, amely a következő metacímke-bejegyzést tartalmazza, és gondoskodik arról, hogy a részlet hozzá legyen adva a](metatags-module.md) webhelyen használt sablonok HTML \<head\> szakaszhoz.

```html
<meta name="robots" content="noindex,nofollow" /> 
```

## <a name="soft-launch-of-a-site"></a>A webhely próbaindítása

A „próbaindítás” során egy webhely csak korlátozott közönség vagy piac számára érhető el, mielőtt megtörténne a teljes indítás. Ha a webhelyet csak úgy indítja el, **érdemes megfontolni a noindex** metacímkék helyét. Ily módon garantálhatja, hogy a próbaindítás továbbra is korlátozott a korlátozott közönségre korlátozódik, amelyet el kíván érni.

## <a name="a-site-that-is-in-production"></a>A termelésben részt vevő webhely

Amikor egy webhely termelésben van, győződjön meg arról, hogy az összes webhelylapot helyesen címkézték meg. A Microsoft Dynamics 365 Commerce az oldalon megadott információkat használja az oldal SEO-adatainak generálásához. A következő modulok nyújtják ezt a funkciót: kategória-oldal összegzése, lista oldal összegzése és a termékoldal összegzése.

A keresőmotor indexelésének optimalizálása érdekében a renderelési keretrendszer a Dynamics 365 Commerce programban konfigurált SEO-tulajdonságokat és a modulban megadott adatokat is használja. A termelésben lévő hely esetén győződjön meg arról, hogy a robots.txt fájl lehetővé teszi az egész webhely indexelését, és a közzétett oldaltérkép-dokumentumra mutató hivatkozásokat tartalmaz. Be kell kapcsolni a oldaltérkép-generálás funkciókat a **Webhelybeállítások \> Engedélyezett webhelytérképek** helyen.

### <a name="page-seo-settings-for-internal-preview-limited-audiences-and-all-audiences"></a>Oldal SEO beállításai a belső előnézethez, korlátozott közönséghez és teljes közönséghez

Mivel a Dynamics 365 Commerce támogatja a „valós megjelenítésű” (WYSIWYG), a hitelesített előnézeteket a vizuális oldalkészítőben, a szerkesztők úgy készíthetik el az oldal tartalmát, hogy nem kell azon aggódniuk, hogy az információk láthatóvá válnak az oldal látogatóinak. Ha egy oldalt közzé kell tenni, de az adott lapnak korlátozottnak kell lennie, **akkor a noindex** metacímkének kell lennie, hogy ne indexelje a keresőmotorok. Ezután, amikor a lap készen áll a teljes közönségre, minden alapvető SEO metaadatnak jelen kell lennie, hogy maximalizálni lehessen a keresőmotor-indexelés hatékonyságát. Ezenkívül a nolimit **metacímkét** is el kell távolítani.

## <a name="additional-resources"></a>További erőforrások

[Az e-kereskedelem felhasználóinak és szerepköreinek kezelése](manage-ecommerce-users-roles.md)

[Parancsfájl hozzáadása a webhely oldalaihoz a telemetria támogatásához](add-telemetry.md)

[Tartalomra vonatkozó biztonsági házirend (CSP) kezelése](manage-csp.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
