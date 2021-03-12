---
title: A webhely keresőmotor-optimalizálási (SEO) szempontjai
description: Ez a témakör a keresőmotor-optimalizálással (SEO) kapcsolatosan megfontolandó témákat tárgyalja webhelyével kapcsolatosan a fejlesztéstől a termelésig.
author: psimolin
manager: annbe
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 639d6fa74954b5f74560c7e51523ab2b4d2b7f62
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4989352"
---
# <a name="search-engine-optimization-seo-considerations-for-your-site"></a>A webhely keresőmotor-optimalizálási (SEO) szempontjai


[!include [banner](includes/banner.md)]

Ez a témakör a keresőmotor-optimalizálással (SEO) kapcsolatosan megfontolandó témákat tárgyalja webhelyével kapcsolatosan a fejlesztéstől a termelésig.

## <a name="a-site-that-is-under-development"></a>Fejlesztés alatt álló webhely

A webhely fejlesztése alatt a webhely minden oldalának **NOINDEX** és **NOFOLLOW** címkékkel kell rendelkeznie, így a keresőmotorok nem indexelik a lapokat, és nem tárolják a webhely fejlesztői verzióit a gyorsítótárban. Ehhez a konfigurációhoz hozzá kell adnia az alapértelmezett metacímkék modult a webhely sablonjához. Az alapértelmezett metacímkék tulajdonságai ezután elérhetővé válnak a lapszerkesztő SEO-tulajdonságok szakaszában. Ezeket a tulajdonságokat a metacímkék kezelésére használhatja.

## <a name="soft-launch-of-a-site"></a>A webhely próbaindítása

A „próbaindítás” során egy webhely csak korlátozott közönség vagy piac számára érhető el, mielőtt megtörténne a teljes indítás. Ha csinál egy próbaindítást of weboldalán akkor érdemes a **NOINDEX** metacímkéket a helyükön hagyni. Ily módon garantálhatja, hogy a próbaindítás továbbra is korlátozott a korlátozott közönségre korlátozódik, amelyet el kíván érni.

## <a name="a-site-that-is-in-production"></a>A termelésben részt vevő webhely

Amikor egy webhely termelésben van, győződjön meg arról, hogy az összes webhelylapot helyesen címkézték meg. A Microsoft Dynamics 365 Commerce az oldalon megadott információkat használja az oldal SEO-adatainak generálásához. A következő modulok nyújtják ezt a funkciót: kategória-oldal összegzése, lista oldal összegzése és a termékoldal összegzése.

A keresőmotor indexelésének optimalizálása érdekében a renderelési keretrendszer a Dynamics 365 Commerce programban konfigurált SEO-tulajdonságokat és a modulban megadott adatokat is használja. A termelésben lévő hely esetén győződjön meg arról, hogy a robots.txt fájl lehetővé teszi az egész webhely indexelését, és a közzétett oldaltérkép-dokumentumra mutató hivatkozásokat tartalmaz. Be kell kapcsolni a oldaltérkép-generálás funkciókat a **Webhelybeállítások \> Engedélyezett webhelytérképek** helyen.

### <a name="page-seo-settings-for-internal-preview-limited-audiences-and-all-audiences"></a>Oldal SEO beállításai a belső előnézethez, korlátozott közönséghez és teljes közönséghez

Mivel a Dynamics 365 Commerce támogatja a „valós megjelenítésű” (WYSIWYG), a hitelesített előnézeteket a vizuális oldalkészítőben, a szerkesztők úgy készíthetik el az oldal tartalmát, hogy nem kell azon aggódniuk, hogy az információk láthatóvá válnak az oldal látogatóinak. Ha egy lapot közzé kell tenni, de a kitettséget korlátozni kell, akkor a **NOINDEX** metacímkével kell ellátni, hogy a keresőmotorok ne indexeljék. Ezután, amikor a lap készen áll a teljes közönségre, minden alapvető SEO metaadatnak jelen kell lennie, hogy maximalizálni lehessen a keresőmotor-indexelés hatékonyságát. Ezenkívül a **NOLIMIT** metacímkét el kell távolítani.

## <a name="additional-resources"></a>További erőforrások

[Az e-kereskedelem felhasználóinak és szerepköreinek kezelése](manage-ecommerce-users-roles.md)

[Parancsfájl hozzáadása a webhely oldalaihoz a telemetria támogatásához](add-telemetry.md)

[Tartalomra vonatkozó biztonsági házirend (CSP) kezelése](manage-csp.md)
