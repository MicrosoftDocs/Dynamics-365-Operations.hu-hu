---
title: Mérnöki változáskezelés – áttekintés (videofelvételt tartalmaz)
description: Ez a témakör áttekintést nyújt a tervezési változáskezeléssel kapcsolatban, amely segítséget nyújt a termék verziószámozásának tervezéséhez és kezeléséhez, valamint a termékéletciklusok és mérnöki változásainak kezeléséhez.
author: t-benebo
ms.date: 01/11/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-09-28
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 54d91d009d70194dfc91c8c855e0088f9de01718
ms.sourcegitcommit: fcb8a3419e3597fe855cae9eb21333698518c2c7
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/09/2022
ms.locfileid: "8103813"
---
# <a name="engineering-change-management-overview"></a>Tervezési változáskezelés áttekintése

[!include [banner](../includes/banner.md)]

## <a name="feature-summary"></a>Funkció összegzése

A mai gyártóknak erős termékadat-kezelési, verziókövető és mérnöki változáskezelésre van szükségük ahhoz, hogy sikeresek legyenek a termékek életciklusát folyamatosan csökkenő követelmények, a nagyobb minőségi és megbízhatósági követelmények területén, és még inkább a termékbiztonságra fókuszálnak.

A műszaki változáskezelés a termékadat-kezelési folyamat szerkezetét és logikáját is jelenti, és a munkafolyamatok által támogatott, ellenőrzött módon teszi lehetővé a termékek definiálját, kiadott és módosított adatait. A termékverziók és a műszaki változáskezelés segítségével dokumentálhatja, kiértékelheti és alkalmazhatja a műszaki módosításokat a termék életciklusában.

A tervezési változáskezelés segítséget nyújt a termék verziószámozásának tervezéséhez és kezeléséhez, valamint a termékéletciklusok és mérnöki változásainak kezeléséhez. Itt van egy lista a fő funkciókról:

- Termék verziószámozása
- Továbbfejlesztett termékkiadási funkció, amely lehetővé teszi a termék alapadatainak karbantartását egy jogi személyben (a tervezési vállalatban), és közzéteheti a teljesen konfigurált kiadott terméket más jogi személyekbe
- Annak ellenőrzésére vonatkozó szabályok, hogy a kötelező adatokat megadták-e a termékverzió aktiválása előtt (készenléti ellenőrzések)
- Továbbfejlesztett termékéletciklus-kezelés a kiadott termék meghatározott üzleti folyamatokban való alkalmazásának részletes szabályozásával
- Tervezési változási kérelmek, amelyeket munkafolyamatok támogatnak
- Tervezési változási rendelések, amelyeket munkafolyamatok támogatnak

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4HE6B]

Az előző video -([Változáskezelési képességek Dynamics 365 Supply Chain Management](https://youtu.be/N313FqvRuBc) itt) [megtalálható a Pénzügy és műveletek online](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) elérhetővé válik YouTube.

## <a name="turn-on-the-engineering-change-management-features-for-your-system"></a>A rendszer tervezési változáskezelési funkcióinak bekapcsolása

A tervezési változáskezelés használata előtt engedélyeznie kell a *Tervezési változáskezelés* szolgáltatást és annak konfigurációs kulcsát. Ha a tranzakciókban nyomon szeretné követni a termékek verziódimenzióját is (opcionális), akkor engedélyeznie kell a *Termékverzió dimenzió* szolgáltatást és annak konfigurációs kulcsát is. Az előfeltételek szükség szerint való beállítása után bekapcsolhatja a tervezési változáskezelés további választható funkcióit.

### <a name="turn-the-basic-engineering-change-management-features-on-or-off"></a>Az alapvető műszaki változáskezelési funkciók be- és kikapcsolása

A következő lépésekkel kapcsolhatja be és kapcsolhatja ki az alapvető műszaki változáskezelési funkciókat. Az Ellátásilánc-kezelés 10.0.25-ös *verziója* szerint a műszaki változáskezelés szolgáltatás alapértelmezés szerint be van kapcsolva.

1. Ugorjon a [Funkciókezelés](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) munkaterületre.
1. Keressen frissítéseket.
1. A Műszaki változáskezelés *nevű funkció* szükség esetén be- és kikapcsolása.
1. Ha szeretné nyomon követni a tranzakciókban a termékek verziódimenzióját (nem kötelező), *kapcsolja be a Termékdimenzió-verzió nevű funkciót*.

### <a name="turn-the-required-configuration-keys-on-or-off"></a>A szükséges konfigurációs kulcsok be- és kikapcsolása

Ezután kapcsolja be a konfigurációs kulcsokat a következő lépések végrehajtásával. Ezek alapértelmezés szerint nincsenek bekapcsolva.

1. Állítsa a rendszert karbantartási módba a [Karbantartási mód](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md) alatt leírtak szerint.
1. Lépjen a **Rendszerfelügyelet \> Beállítás \> Licenckonfiguráció** elemre.
1. Bontsa ki a **Kereskedelem** csomópontot,
1. Engedélyezze vagy tiltsa le a fő funkció konfigurációs kulcsát a Mérnöki változáskezelés **jelölőnégyzet** segítségével.
1. Bontsa ki a **Tervezési változáskezelés** csomópontot, és szükség szerint jelölje be a következő jelölőnégyzeteket, vagy törölje belőlük a jelet (a használni kívánt funkcióktól függően):

    - **Attribútumkeresés**  – az [attribútumkeresési funkció](engineering-attributes-and-search.md) engedélyezéséhez jelölje be ezt a jelölőnégyzetet. Javasoljuk, hogy engedélyezze ezt a funkciót; ha nem használja, akkor törölheti a jelölést ebből a jelölőnégyzetből.
    - **Változáskezelés a folyamatszerű gyártáshoz** – jelölje be ezt a jelölőnégyzetet, ha a Tervezési változáskezelés funkcióival szeretné kezelni a folyamatszerű gyártáshoz használatos receptúrák módosításait. Ha nem kell receptúrákat kezelnie, akkor törölheti a jelet a jelölőnégyzetből. További tudnivalók: [Receptúrák és receptúra-összetevők változásainak kezelése](manage-formula-changes.md).

1. Ha használni szeretné a verziódimenziót is, jelölje be a **Termékdimenzió – Verzió** jelölőnégyzetet is. (Ez a jelölőnégyzet a listában lejjebb van, nem a <a0/1><a2/4><a2/<a2/ alá van beágyazva. **Műszaki módosításkezelés csomópont** .) Ha nincs szüksége erre a szolgáltatásra, akkor törli a jelölést a jelölőnégyzetből.
1. Kapcsolja ki a karbantartási módot a [Karbantartási mód](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md) alatt leírtak szerint.
1. Az adatbázist szinkronizálni kell, hogy a konfigurációs kulcsok megfelelően frissülve tükrözzék a módosításokat. Tegye a következő lépések valamelyikét attól függően, hogy milyen típusú környezeten dolgozik:
    - **1. rétegbeli (fejlesztői) környezetek esetén**: nyissa meg a projektet a Microsoft Visual Studio **programban, majd válassza a Dynamics 365 \> Szinkronizálás az adatbázis szinkronizálása \> lehetőséget**.
    - **2. rétegbeli (és magasabb)** környezetek esetén: Az adatbázis automatikusan szinkronizál, miután a környezetet betette a karbantartási üzemmódba, és ki van lépni a karbantartási üzemmódból, így ezt a lépést kihagyhatja.

### <a name="turn-on-additional-engineering-change-management-features"></a>A rendszer további tervezési változáskezelési funkcióinak bekapcsolása

Miután bekapcsolta az alapvető tervezési változáskezelési funkciókat, és engedélyezi a konfigurációs kulcsokat, a funkciókezeléshez további és választható tervezési változáskezelési funkciók is hozzáadódnak. Ezek a funkciók a **Tervezési változáskezelés** modulban vannak felsorolva. A következő táblázat az egyes választható funkciókat írja le, és további tájékoztatásért tartalmaz hivatkozásokat. Az Ellátásilánc-kezelés 10.0.25-ös verziója szerint ezek a funkciók alapértelmezés szerint be vannak kapcsolva, de kikapcsolhatja őket.

| Funkcióneve a funkciókezelésben | Leírás | Funkció állapota |
|---|---|---|
| Változáskezelés engedélyezése meglévő termékek esetében | <p>Ezzel a funkcióval a meglévő termékeket tervezési termékekké konvertálhatja, hogy a tervezési változáskezelés segítségével el tudja kezdeni a termékek kezelését.</p><p>További információk: [Változáskezelés engedélyezése meglévő termékek esetében](change-management-existing-products.md).</p> |
| Tervezési értesítések a termelés számára | <p>Ha egy termék műszaki tervezésben módosul, akkor fontos lehet a termelést értesíteni a változásokról. Ily módon a termelési dolgozók meg tudnak tenni megfelelő lépéseket, például az összetevő-helyettesítést, az anyagjegyzék-cserét vagy az útvonalcserét. Ez a funkció lehetővé teszi a termelés értesítését az előállított termékek változásairól.</p><p>További tájékoztatást [A mérnöki termékek módosításának kezelése](engineering-change-management.md) részben talál.</p> |
| Továbbfejlesztett attribútumöröklődés a tervezési változáskezeléshez | <p>Ez a funkció egyszerűbbé teszi a késztermékek és közbenső cikkek attribútumainak kezelését. Ha ez a funkció be van kapcsolva, akkor egyszerűbben azonosítani lehet az adott cikkhez tartozó összes attribútumot, és ki lehet választani azokat az attribútumokat, amelyek az adott cikkből a szülő cikkbe kell származtatni. Ez a funkció például akkor hasznos, ha egy késztermék egyik összetevője törékeny, mérgező vagy gyúlékony, mivel így könnyen azonosítani lehet a törékeny, méregző vagy gyúlékony attribútumot, és tovább lehet azt vinni a késztermékbe.</p><p>További információ: [Mérnöki attribútumok és mérnöki attribútumok keresése](engineering-attributes-and-search.md).</p> |
| Termékkészültségi ellenőrzések | <p>Ezzel a funkcióval normál (nem tervezési) termékekhez készenléti ellenőrzéseket is beállíthat. A termék készenléti ellenőrzése révén gondoskodhat arról, hogy minden termék teljesen meg legyen határozva, és minden szükséges házirend konfigurálva legyenl, mielőtt a terméket elérhetővé tette és tranzakciókban felhasználta. Ha letiltja ezt a funkciót egy ideig történő alkalmazás után, a normál termékekre vonatkozó összes készenlét-ellenőrzés törlődik.</p><p>További információ: [Termékkészenlét](product-readiness.md).</p> |
| Receptúrák és összetevőik módosításainak kezelése | <p>Ez a funkció lehetővé teszi a receptúrás összetevők, társtermékek és melléktermékek változásainak nyomon követését.</p><p>További tudnivalók: [Receptúrák és receptúra-összetevők változásainak kezelése](manage-formula-changes.md).</p> |
| Változatlétrehozás tervezési termékekhez | <p>Ezzel a funkcióval a rendelkezésre álló dimenzióértékek alapján változatokat lehet létrehozni a tervezési termékekhez.</p><p>További tájékoztatás: [Változatok létrehozása tervezési termékekhez](engineering-variants.md).</p> |

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
