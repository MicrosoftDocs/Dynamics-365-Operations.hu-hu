---
title: A készletpufferek és a készlet szintjeinek konfigurálása
description: Ez a témakör azt mutatja be, hogyan lehet konfigurálni a készletpuffereket és a készlet szintjét, amelyek meghatározzák a Microsoft Dynamics 365 Commerce webhelyein a készlet elérhetőségével kapcsolatos üzenetküldést.
author: boycezhu
ms.date: 06/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: global
ms.author: boycez
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.12
ms.openlocfilehash: 842389811169f785235de7ac7d9a49ab903f99ddf7d43f139aba0873a2577d72
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6727533"
---
# <a name="configure-inventory-buffers-and-inventory-levels"></a>Készletpufferek és készletszintek konfigurálása

[!include [banner](includes/banner.md)]

Ez a témakör azt mutatja be, hogyan lehet konfigurálni a készletpuffereket és a készlet szintjét, amelyek meghatározzák a Microsoft Dynamics 365 Commerce webhelyein a készletek elérhetőségével kapcsolatos üzenetküldést.

A Dynamics 365 Commerce központ készletadatokat és különféle csatornákat tartalmaz, mint a pénztár (POS) alkalmazások, az e-Commerce üzletek és más, a készletet aszinkron módon küldő és lehívó egyéni integrált alkalmazások. Ennélfogva a Commerce központ aktuális készlet lapján, a POS felhasználói felületen (UI) és az e-Commerce készletelérhetőségi API-kon keresztül kapott elérhető készletértékek nem mindig 100%-osan pontosak valós időben.

Az e-Commerce áruházak tényleges készletértékének megjelenítése helyett számos kiskereskedő szívesebben jeleníti meg a készlet elérhetőségi állapotával kapcsolatos üzenetküldést (például „elérhető” vagy „elfogyott”), hogy tájékoztassa a vevőket, hogy egy cikk megvásárolható-e, vagy elfogyott. Ehhez a módszerhez rendelkezésre kell bocsátania és konfigurálnia kell azokat a készletpuffereket és készletszinteket, amelyek meghatározzák a készlet elérhetőségi üzeneteit.

## <a name="prerequisite-turn-on-the-inventory-buffers-and-inventory-levels-feature"></a>Előfeltétel: Kapcsolja be a készletpufferek és a készletszintek funkciókat

A készletpufferek és a készletszintek funkció a Commerce-központ Funkciókezelése segítségével vezérelhető. Ha be szeretné kapcsolni a funkciót, hajtsa végre az alábbi lépéseket.

1. Válassza a **Rendszerfelügyelet** \> **Munkaterületek** \> **Funkciókezelés** elemet.
1. Keresse meg a **Készletpufferek és készletszintek engedélyezése** funkciót, válassza ki a sorát, majd válassza az **Engedélyezés most** lehetőséget.

A funkció bekapcsolását követően a készletszintet a **Retail és Commerce \> Készletkezelés** alatt találja.

## <a name="create-and-configure-an-inventory-level-profile"></a>Készletmodellprofil létrehozása és konfigurálása

A *Készletmodellprofil* határozza meg, hogy az adott termékmennyiség állapota készleten, elfogyott vagy más egyéni állapotúnak minősül-e. Jogi személyenként több készletmodellprofilt hozhat létre és állíthat be. Minden profil készletszintek halmazából áll, és a szintek egy *tartomány*, egy *kód* és egy *címke* szerint vannak meghatározva.

- **Tartomány** – A tartományokat a *kezdő mennyiség* és a *záró mennyiség* határozza meg. A mennyiségérték egy tartományba esik, ha a tartomány kezdő mennyiségét meghaladja, és nem haladja meg a záró mennyiségét.
- **Kód** – A kód a szintet jelölő belső rövidítés. Azok az ügyfelek, akik közvetlenül integrálják a készlet API-ket, kódokat alkalmazhatnak egy adott készletszint további logikájának létrehozásához. Például ki tudják kapcsolni a termékre vonatkozó vásárlási képességet, amikor a készlet szintjének kódja **OOS** ("out of stock" – elfogyott).
- **Címke** – A címke egy olyan, a vevő által látható, értelmes üzenet, amely egy e-Commerce webhely vevői számára ad információt a készletszintről.

### <a name="create-an-inventory-level-profile"></a>Készletszintprofil létrehozása

Készletszintprofil létrehozásához hajtsa végre az alábbi lépéseket.

1. Nyissa meg a **Retail és Commerce** \> **Készletkezelés** \> **Készletszintek** modult.
1. A Művelet panelen válassza az **Új** lehetőséget, majd írja be az értékeket a **Profil azonosítója** és a **Leírás** mezőbe.
1. Új szint hozzáadásához válassza a **Tartományok** gyorslap **Hozzáadás** elemét, majd adja meg az értékeket a szint **Kezdő mennyiség**, **Záró mennyiség**, **Kód** és a **Címke** oszlopaiban. Ismételje meg ezt a lépést a további szintek hozzáadásához. A szükséges módon szerkesztheti az adatrács értékét, de a **Törlés** lehetőséget is kiválaszthatja a szint eltávolításához.
1. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.

Új profil létrehozásakor a program automatikusan két készletszintet inicializál:

- **OOS** – Az "out of stock" (elfogyott) szint, ahol a tartomány alsó határa negatív végtelen. A kezdő mennyiség és a kód nem szerkeszthető a szint esetében.
- **AVAIL** – Az "elérhető" szint, ahol a tartomány felső határa végtelen. A záró mennyiség és a kód nem szerkeszthető a szint esetében.

> [!NOTE]
> A profil definíciós tartományai között nem lehetnek hézagok vagy átfedések.

A Művelet panel **Fordítások** gombjával konfigurálhatja a címkeüzenetekhez tartozó honosított karakterláncokat. Ezt követően futtatnia kell az **1110** (**Globális konfiguráció**) elosztási ütemezési feladatot, hogy szinkronizálja a honosított karakterláncokat a csatornával.

### <a name="configure-an-inventory-level-profile"></a>Készletszintprofil létrehozása

A készletszint a termékkategória szintjén vagy az egyes termékek szintjén is konfigurálható. Ha egy termékhez egy készletszintprofilt konfigurál, akkor a program a kapcsolódó profilban megadott tartományok alapján határozza meg a készlet szintjét. Ellenkező esetben az "elérhető" vagy "elfogyott" készletszintet annak alapján határozza meg, hogy a termék pozitív aktuális készlettel rendelkezik-e.

Kategória készletszintprofiljának konfigurálásához hajtsa végre az alábbi lépéseket.

1. Ugorjon a **Kiskereskedelem és kereskedelem** \> **Termékek és kategóriák** \> **Kereskedelmi termékhierarchia** lehetőségre.
1. Válassza ki a kategóriát, amelyhez készletszintprofilt szeretne konfigurálni.
1. Az **Termékértékesítési tulajdonságok** gyorslapon válasszon egy jogi személyt.
1. A **Kereskedelmi készlet** szakasz **Készletszintprofil** mezőjében válassza ki az előre definiált készletszintprofilok egyikét.

A Művelet panel **Termékek frissítése** gombjánka használatával továbbíthatja a kategóriaszintű profilok értékét a kategóriába tartozó termékekre. További tájékoztatás: [Termékkategóriák és termékek kezelése](category-management-product-creation.md).

Kiadott termék készletszintprofiljának konfigurálásához hajtsa végre az alábbi lépéseket.

1. Nyissa meg a következőt: **Kiskereskedelem és kereskedelem** \> **Termékek és kategóriák** \> **Felszabadított termékek kategóriák szerint**.
1. Válasszon ki egy terméket, majd nyissa meg a termék részletes adatait tartalmazó lapot.
1. Az **Eladás** gyorslapon a **Kereskedelmi készlet** szakasz **Készletszintprofil** mezőjében válassza ki az előre definiált készletszintprofilok egyikét.

Új termék létrehozásakor a **Készletmodellprofil** mező, mint a sok más termékszintű attribútum, a termékhez társított kategória értékére lesz beállítva.

> [!NOTE]
> A készletmodellprofil egy jogi személyre specifikus attribútum. Ugyanazon kategória vagy termék esetében a készletmodellprofil értéke különböző lehet a jogi személyekben.

A következő lépésekkel szinkronizálhatja a készletmodellprofilok konfigurációit a csatornára.

1. Ugorjon a **Kiskereskedelem és kereskedelem** \> **Kiskereskedelem és kereskedelem informatika** \> **Elosztási ütemezés** pontra.
1. Futtassa az **1040** (**Termék**) elosztási ütemezést.

## <a name="configure-an-inventory-buffer"></a>Készletpuffer konfigurálása

A *készletpuffer* olyan felhasználó által definiált érték, amely a becsült mennyiség kiszámításához kivonja egy adott termék további mennyiségét az eredeti mennyiségből. Ez a becsült mennyiség biztonságos puffert biztosít a kiskereskedők számára, hogy ne értékesítsenek többet egy termékből annál, mint ami készleten van. A készletpuffer a termékkategória szintjén vagy az egyes termékek szintjén is konfigurálható. Ha nincs megadva készletpuffer, akkor a program az alapértelmezett **0** (nulla) értéket használja.

Kategória készletpufferének konfigurálásához hajtsa végre az alábbi lépéseket.

1. Ugorjon a **Kiskereskedelem és kereskedelem** \> **Termékek és kategóriák** \> **Kereskedelmi termékhierarchia** lehetőségre.
1. Válassza ki a kategóriát, amelyhez a készletpuffert konfigurálni szeretné.
1. Az **Termékértékesítési tulajdonságok** gyorslapon válasszon egy jogi személyt.
1. A **Kereskedelmi készlet** szakasz **Készletpuffer** mezőjébe írjon be egy pozitív értéket.

A Művelet panel **Termékek frissítése** gombjánka használatával továbbíthatja a kategóriaszintű puffer értékét a kategóriába tartozó termékekre. További tájékoztatás: [Termékkategóriák és termékek kezelése](category-management-product-creation.md).

Kiadott termék készletpufferének konfigurálásához hajtsa végre az alábbi lépéseket.

1. Nyissa meg a következőt: **Kiskereskedelem és kereskedelem** \> **Termékek és kategóriák** \> **Felszabadított termékek kategóriák szerint**.
1. Válasszon ki egy terméket, majd nyissa meg a termék részletes adatait tartalmazó lapot.
1. Az **Eladás** gyorslapon, a **Kereskedelmi készlet** szakasz **Készletpuffer** mezőjébe írjon be egy pozitív értéket.

Új termék létrehozásakor a **Készletpuffer** mező termékhez társított kategória értékére lesz beállítva.

> [!NOTE]
> Ha mind a készletpuffer, mind a készletszintprofilok be vannak állítva a termékhez, akkor a program a termék becsült mennyiségét (azaz az eredeti mennyiséget mínusz a puffer értékét) használja a tartomány számításához a készlet szintjének megállapításához.

A következő lépésekkel szinkronizálhatja a készletpufferek konfigurációit a csatornára.

1. Ugorjon a **Kiskereskedelem és kereskedelem** \> **Kiskereskedelem és kereskedelem informatika** \> **Elosztási ütemezés** pontra.
1. Futtassa az **1040** (**Termék**) elosztási ütemezést.

## <a name="use-inventory-buffers-and-inventory-levels-in-e-commerce-scenario"></a>A készletpufferek és a készletszintek használata az e-Commerce forgatókönyvben

A Commerce webhelykészítő a Commerce-központ készletpuffer és készletszint funkcióival határozza meg az e-Commerce webhelyeken az elérhető készlettel kapcsolatos üzeneteket. További információk: [Készletbeállítások alkalmazása](inventory-settings.md).

Alternatív megoldásként egy harmadik fél e-Commerce megoldásával való integráció esetén, a **GetEstimatedAvailability** és a **GetEstimatedProductWarehouseAvailability** API-k segítségével jelenítheti meg az e-Commerce forgatókönyvekben szereplő termékek elérhetőségét. Az alkalmazásprogramozási felületekkel kapcsolatos további tudnivalókat lásd: [Kiskereskedelmi csatornák készletelérhetőségének kiszámítása](calculated-inventory-retail-channels.md).

A készletpufferek és a készletszint bevezetése lehetővé teszi ezeknek az API-knek, hogy a készletszintkódokat és címkeüzeneteket adjanak vissza, amelyek az összes elérhető és fizikailag elérhető értékek alapján kerülnek megállapításra. Az API-k tovább módosíthatók annak meghatározására, hogy a készletmennyiség az üzenettel együtt kerül-e visszaadásra, és hogy a rendelkezésre álló mennyiséget csökkenti-e a rendszer a készletpuffer értékével.

A termékelérhetőségi API-k válaszának konfigurálásához kövesse az alábbi lépéseket.

1. Menjen a **Kiskereskedelem és kereskedelem** \> **Központ beállítása** \> **Paraméterek** \> **Kiskereskedelmi paraméterek** lehetőségre.
1. A **Kiskereskedelmi árukészlet** szakasz **Készlet** lapján, az **Termékelérhetőségi API-k e-Commerce-hez** mezőben válasszon egy értéket.
1. A beállítások csatornákra történő alkalmazásához futtassa az **1110** (**Globális konfiguráció**) elosztási ütemezési feladatot.

## <a name="additional-resources"></a>További erőforrások

[Termékkategóriák és termékek kezelése](category-management-product-creation.md)

[Készlet beállításainak alkalmazása](inventory-settings.md)

[Kiskereskedelmi csatornák készletelérhetőségének kiszámítása](calculated-inventory-retail-channels.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
