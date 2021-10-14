---
title: Tervezési változáskezelés áttekintése
description: Ez a témakör áttekintést nyújt a tervezési változáskezeléssel kapcsolatban, amely segítséget nyújt a termék verziószámozásának tervezéséhez és kezeléséhez, valamint a termékéletciklusok és mérnöki változásainak kezeléséhez.
author: t-benebo
ms.date: 08/26/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: intro-internal
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-09-28
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 89a3eb584275e52910726ca5a9ed53f744f10b8d
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/29/2021
ms.locfileid: "7574689"
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

## <a name="turn-on-the-engineering-change-management-features-for-your-system"></a>A rendszer tervezési változáskezelési funkcióinak bekapcsolása

A tervezési változáskezelés használata előtt engedélyeznie kell a *Tervezési változáskezelés* szolgáltatást és annak konfigurációs kulcsát. Ha a tranzakciókban nyomon szeretné követni a termékek verziódimenzióját is (opcionális), akkor engedélyeznie kell a *Termékverzió dimenzió* szolgáltatást és annak konfigurációs kulcsát is. Az előfeltételek szükség szerint való beállítása után bekapcsolhatja a tervezési változáskezelés további választható funkcióit.

### <a name="turn-on-the-basic-engineering-change-management-features"></a>A rendszer alapszintű tervezési változáskezelési funkcióinak bekapcsolása

Először kapcsolja be a funkciókat a következő lépések végrehajtásával.

1. Ugorjon a [Funkciókezelés](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) munkaterületre.
1. Keressen frissítéseket.
1. Kapcsolja be a *Mérnöki módosításkezelés* szolgáltatást.
1. Ha használni szeretné, kapcsolja be a *Termékdimenzió verziója* nevű szolgáltatást is.

### <a name="turn-on-the-required-configuration-keys"></a>A szükséges konfigurációs kulcsok bekapcsolás

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

### <a name="turn-on-additional-engineering-change-management-features"></a>A rendszer további tervezési változáskezelési funkcióinak bekapcsolása

Miután bekapcsolta az alapvető tervezési változáskezelési funkciókat, és engedélyezi a konfigurációs kulcsokat, a funkciókezeléshez további és választható tervezési változáskezelési funkciók is hozzáadódnak. Ezek a funkciók a **Tervezési változáskezelés** modulban vannak felsorolva. A következő táblázat az egyes választható funkciókat írja le, és további tájékoztatásért tartalmaz hivatkozásokat.

| Funkcióneve a funkciókezelésben | Leírás |
|---|---|
| Változáskezelés engedélyezése meglévő termékek esetében | <p>Ezzel a funkcióval a meglévő termékeket tervezési termékekké konvertálhatja, hogy a tervezési változáskezelés segítségével el tudja kezdeni a termékek kezelését.</p><p>További információk: [Változáskezelés engedélyezése meglévő termékek esetében](change-management-existing-products.md).</p> |
| Tervezési értesítések a termelés számára | <p>Ha egy termék műszaki tervezésben módosul, akkor fontos lehet a termelést értesíteni a változásokról. Ily módon a termelési dolgozók meg tudnak tenni megfelelő lépéseket, például az összetevő-helyettesítést, az anyagjegyzék-cserét vagy az útvonalcserét. Ez a funkció lehetővé teszi a termelés értesítését az előállított termékek változásairól.</p><p>További tájékoztatást [A mérnöki termékek módosításának kezelése](engineering-change-management.md) részben talál.</p> |
| Továbbfejlesztett attribútumöröklődés a tervezési változáskezeléshez | <p>Ez a funkció egyszerűbbé teszi a késztermékek és közbenső cikkek attribútumainak kezelését. Ha ez a funkció be van kapcsolva, akkor egyszerűbben azonosítani lehet az adott cikkhez tartozó összes attribútumot, és ki lehet választani azokat az attribútumokat, amelyek az adott cikkből a szülő cikkbe kell származtatni. Ez a funkció például akkor hasznos, ha egy késztermék egyik összetevője törékeny, mérgező vagy gyúlékony, mivel így könnyen azonosítani lehet a törékeny, méregző vagy gyúlékony attribútumot, és tovább lehet azt vinni a késztermékbe.</p><p>További információ: [Mérnöki attribútumok és mérnöki attribútumok keresése](engineering-attributes-and-search.md).</p> |
| Termékkészültségi ellenőrzések | <p>Ezzel a funkcióval normál (nem tervezési) termékekhez készenléti ellenőrzéseket is beállíthat. A termék készenléti ellenőrzése révén gondoskodhat arról, hogy minden termék teljesen meg legyen határozva, és minden szükséges házirend konfigurálva legyenl, mielőtt a terméket elérhetővé tette és tranzakciókban felhasználta. Ha letiltja ezt a funkciót egy ideig történő alkalmazás után, a normál termékekre vonatkozó összes készenlét-ellenőrzés törlődik.</p><p>További információ: [Termékkészenlét](product-readiness.md).</p> |
| Receptúrák és összetevőik módosításainak kezelése | <p>Ez a funkció lehetővé teszi a receptúrás összetevők, társtermékek és melléktermékek változásainak nyomon követését.</p><p>További tudnivalók: [Receptúrák és receptúra-összetevők változásainak kezelése](manage-formula-changes.md).</p> |
| Változatlétrehozás tervezési termékekhez | <p>Ezzel a funkcióval a rendelkezésre álló dimenzióértékek alapján változatokat lehet létrehozni a tervezési termékekhez.</p><p>További tájékoztatás: [Változatok létrehozása tervezési termékekhez](engineering-variants.md).</p> |

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
