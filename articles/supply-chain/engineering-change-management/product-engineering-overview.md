---
title: Tervezési változáskezelés áttekintése
description: Ez a témakör áttekintést nyújt a tervezési változáskezeléssel kapcsolatban, amely segítséget nyújt a termék verziószámozásának tervezéséhez és kezeléséhez, valamint a termékéletciklusok és mérnöki változásainak kezeléséhez.
author: t-benebo
manager: tfehr
ms.date: 11/11/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-09-28
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: f1aa04b472eaef7ed398f08a05d46bac2d589561
ms.sourcegitcommit: 9f32389715b226c11e74c53547527e0a8b51e300
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/12/2020
ms.locfileid: "4514350"
---
# <a name="engineering-change-management-overview"></a>Tervezési változáskezelés áttekintése

[!include [banner](../includes/banner.md)]

## <a name="feature-summary"></a>Funkció összegzése

A mai gyártóknak szükségük van hatékony termék-adatmenedzsmentre, verziószabályozásra és tervezési változáskezelésre, hogy sikeresek legyenek a folyamatosan csökkenő termékéletciklusok, a megnövekedő minőségi és megbízhatósági követelmények, valamint a növekedő termékbiztonsági fókusz világában.

A mérnöki változtatáskezelés struktúrát és fegyelmet hoz a termékadat-menedzsment folyamatba, és a termékek így szabályozott módon határozhatók meg, adhatók ki és felügyelhetők, amelyet munkafolyamatok támogatnak. A termékverziók és a mérnöki változáskezelés segítségével dokumentálhatja a mérnöki változásokat, értékelheti a határukat és alkalmazhatja őket a termék teljes életciklusa során.

A tervezési változáskezelés segítséget nyújt a termék verziószámozásának tervezéséhez és kezeléséhez, valamint a termékéletciklusok és mérnöki változásainak kezeléséhez. Itt van egy lista a fő funkciókról:

- Termék verziószámozása
- Továbbfejlesztett termékkiadási funkció, amely lehetővé teszi a termék alapadatainak karbantartását egy jogi személyben (a tervezési vállalatban), és közzéteheti a teljesen konfigurált kiadott terméket más jogi személyekbe
- Annak ellenőrzésére vonatkozó szabályok, hogy a kötelező adatokat megadták-e a termékverzió aktiválása előtt (készenléti ellenőrzések)
- Továbbfejlesztett termékéletciklus-kezelés a kiadott termék meghatározott üzleti folyamatokban való alkalmazásának részletes szabályozásával
- Tervezési változási kérelmek, amelyeket munkafolyamatok támogatnak
- Tervezési változási rendelések, amelyeket munkafolyamatok támogatnak

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4HE6B]

Az előző videó ([Módosításkezelési képességek a Dynamics 365 Supply Chain Management rendszerben](https://youtu.be/N313FqvRuBc)) szerepel a [Finance and Operations lejátszási listában](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) a YouTube-on.

## <a name="turn-on-engineering-change-management-for-your-system"></a>A rendszer műszaki módosításkezelésének bekapcsolása

Először kapcsolja be a mérnöki módosításkezelést az alábbi lépések végrehajtásával.

1. Lépjen a [Funkciókezelés](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) lehetőségre.
1. Keressen frissítéseket.
1. Kapcsolja be a **Mérnöki módosításkezelés** szolgáltatást.

Ezután kapcsolja be a **Mérnöki módosításkezelés** konfigurációs kulcsot az alábbi lépések végrehajtásával.

1. Állítsa a rendszert karbantartási módba a [Karbantartási mód](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md) alatt leírtak szerint.
1. Lépjen a **Rendszerfelügyelet \> Beállítás \> Licenckonfiguráció** elemre.
1. Bontsa ki a **Kereskedelmi** csomópontot, és jelölje be a **Mérnöki módosításkezelés** jelölőnégyzetet.
1. Kapcsolja ki a karbantartási módot a [Karbantartási mód](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md) alatt leírtak szerint.