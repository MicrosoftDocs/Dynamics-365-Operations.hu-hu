---
title: Tervezési változáskezelés áttekintése
description: Ez a témakör áttekintést nyújt a tervezési változáskezeléssel kapcsolatban, amely segítséget nyújt a termék verziószámozásának tervezéséhez és kezeléséhez, valamint a termékéletciklusok és mérnöki változásainak kezeléséhez.
author: t-benebo
ms.date: 11/11/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: intro-internal
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-09-28
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: 8f2d577d9e48ced9d4c516a66e4f53671417875cbfb51bd6bdc2cb0938d83c01
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6714956"
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

## <a name="turn-on-the-engineering-change-management-and-version-dimension-features-for-your-system"></a>Kapcsolja be a tervezési változáskezelést és a verziódimenziókat a rendszerén

A tervezési változáskezelés használata előtt engedélyeznie kell a *Tervezési változáskezelés* szolgáltatást és annak konfigurációs kulcsát. Ha a tranzakciókban nyomon szeretné követni a termékek verziódimenzióját is (opcionális), akkor engedélyeznie kell a *Termékverzió dimenzió* szolgáltatást és annak konfigurációs kulcsát is.

Először kapcsolja be a funkciókat a következő lépések végrehajtásával.

1. Ugorjon a [Funkciókezelés](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) munkaterületre.
1. Keressen frissítéseket.
1. Kapcsolja be a *Mérnöki módosításkezelés* szolgáltatást.
1. Ha használni szeretné, kapcsolja be a *Termékdimenzió verziója* nevű szolgáltatást is.

Ezután kapcsolja be a konfigurációs kulcsokat a következő lépések végrehajtásával.

1. Állítsa a rendszert karbantartási módba a [Karbantartási mód](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md) alatt leírtak szerint.
1. Lépjen a **Rendszerfelügyelet \> Beállítás \> Licenckonfiguráció** elemre.
1. Bontsa ki a **Kereskedelem** csomópontot,
1. A fő funkció konfigurációs kulcsának engedélyezéséhez jelölje be a **Mérnöki változások kezelése** jelölőnégyzetet.
1. Bontsa ki a **Tervezési változáskezelés** csomópontot, és szükség szerint jelölje be a következő jelölőnégyzeteket, vagy törölje belőlük a jelet (a használni kívánt funkcióktól függően):

    - **Attribútumkeresés**  – az [attribútumkeresési funkció](engineering-attributes-and-search.md) engedélyezéséhez jelölje be ezt a jelölőnégyzetet. Javasoljuk, hogy engedélyezze ezt a funkciót; ha nem használja, akkor törölheti a jelölést ebből a jelölőnégyzetből.
    - **Változáskezelés a folyamatszerű gyártáshoz** – jelölje be ezt a jelölőnégyzetet, ha a Tervezési változáskezelés funkcióival szeretné kezelni a folyamatszerű gyártáshoz használatos receptúrák módosításait. Ha nem kell receptúrákat kezelnie, akkor törölheti a jelet a jelölőnégyzetből. További tudnivalók: [Receptúrák és receptúra-összetevők változásainak kezelése](manage-formula-changes.md).

1. Ha használni szeretné a verziódimenziót is, jelölje be a **Termékdimenzió – Verzió** jelölőnégyzetet is. (Ez a jelölőnégyzet a listában lejjebb van, nem a **Műszaki módosítások kezelése** csomópont alatt.)
1. Kapcsolja ki a karbantartási módot a [Karbantartási mód](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md) alatt leírtak szerint.

> [!IMPORTANT]
> 2022 áprilisától kezdve a **Mérnöki változások kezelése** és a **Termékdimenzió – Verzió** licenckulcsok alapértelmezés szerint engedélyezve lesznek minden új telepítés esetén, de szükség esetén továbbra is letilthatja őket.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
