---
title: Dimenzión alapuló termékkonfiguráció áttekintése
description: A dimenzión alapuló termékkonfiguráció egy egyszerű megoldás több termékváltozat létrehozására egy alaptermékből és annak anyagjegyzékéből.
author: cvocph
manager: tfehr
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BOMConfigRule, BOMTable, ConfigChooseFromRoute, ConfigGroup, ConfigHierarchy, EcoResDimensionBasedConfiguration
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 19821
ms.assetid: 4db9890b-306b-4be7-ba98-3be2094d561f
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 525d18c2c734929fe03995ea2217d1915037e9f9
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/02/2020
ms.locfileid: "3208524"
---
# <a name="dimension-based-product-configuration-overview"></a>Dimenzión alapuló termékkonfiguráció áttekintése

[!include [banner](../includes/banner.md)]

A dimenzión alapuló termékkonfiguráció egy egyszerű megoldás több termékváltozat létrehozására egy alaptermékből és annak anyagjegyzékéből.

A dimenzión alapuló termékkonfiguráció egyike a három beépített termék konfigurációs technológiának. A két másik technológia az előre definiált változatok és a megszorításon alapuló konfiguráció. Minden három technológia alapterméket használ kiindulási pontként, és a felhasználó termékváltozatokat hozhat létre egy alaptermékhez.

## <a name="key-concepts"></a>Alapfogalmak
A dimenzión alapuló termékkonfiguráció a következő alapfogalmakon alapszik:

-   Alaptermékek
-   Termékdimenzió konfigurációja
-   Konfigurációs csoportok
-   Anyagjegyzék (BOM)
-   Konfigurációs útvonal
-   Konfigurációs szabályok

### <a name="product-masters"></a>Alaptermékek

Egy alaptermék lesz a kiindulópont minden termék konfigurációs folyamathoz. A termék dimenzión alapuló konfigurációjához szükség van egy alaptermékre ezzel az adott konfigurálási technológiával és termékdimenzió csoporttal, amely tartalmazza a konfigurációs termékdimenziót.

### <a name="configuration-product-dimension"></a>Termékdimenzió konfigurációja

A konfigurációs termékdimenzió egy alaptermék termékváltozatainak azonosítására használható, a dimenzión alapuló konfiguráció technológiával. A konfigurációs dimenzió értékét a felhasználó adja meg, és az egyedi termékváltozatok azonosításában segít.

### <a name="configuration-groups"></a>Konfigurációs csoportok

A konfigurációs csoportok egy központi tárházban meghatározottak, és minden dimenzión alapuló termékkonfigurációs modellhez használható. A konfigrációs csoportok különböző anyagjegyzék sorokhoz vannak társítva, és együtt sorcsoportokat alkotnak, amelyek kölcsönösen kizárólagosak. Ez azt jelenti, hogy a csoportnak csak egy sora lehet kiválasztva egy termékváltozathoz.

### <a name="bill-of-materials-bom"></a>Anyagjegyzék (BOM)

Az anyagjegyzék a dimenzión alapuló termékkonfiguráció felépítési egységét képviseli. Minden különböző terméket tartalmaznia kell, amely bármely termékváltozatban használható. Az anyagjegyzék minden sora hivatkozhat egy konfigurációs csoportot. Ha a sor nem hivatkozik egy konfigurációs csoportot, akkor szerepelni fog az összes termékváltozatban.

### <a name="configuration-route"></a>Konfigurációs útvonal

A konfigurációs útvonal határozza meg a konfigurációs csoportok sorozatát, amelyek megjelennek a felhasználó számára a termék-konfigurálás során.

### <a name="configuration-rules"></a>Konfigurációs szabályok

A konfigurációs szabályok egy meg megfeleltetést képviselnek, amely biztosítja, hogy a termék egy konfigurációs csoporthoz tartozik az anyagjegyzékben, amely megköveteli a termék hozzárendelését vagy kizárását különböző konfigurációs csoportokból ugyanabban az anyagjegyzékben.

## <a name="product-modeling-process"></a>Termékmodellezési folyamat
Egy termékmodell építés természetes sorozata, egy dimenzión alapuló termékhez, a kívánt konfigurációs csoportok meghatározásával kezdődik. Fontos, hogy az összes anyagjegyzékben használandó termék ahhoz a vállalathoz legyen kiadva, amelyhez a termékmodell épült. Ha a felépítési egységek a helyükön vannak, a felhasználó létrehozhat anyagjegyzéket és hozzárendelhet konfigurációs csoportokat az anyagjegyzék érintett soraihoz. Ha az anyagjegyzék kész, a konfigurációs útvonal meghatározható a konfigurációs csoportok a megfelelő sorrendben történő rendeléséhez. [![Dimenzión alapuló termékmodellezési folyamat](./media/dimension-based-product-modeling-process-v1.png)](./media/dimension-based-product-modeling-process-v1.png) Létrehozhat termékkapcsolatot biztosító szabályokat arra az esetre, ha különböző konfigurációs csoportokban található termékeket együtt kell használni, vagy nem használhatóak együtt. Miután az anyagjegyzéket egy anyagjegyzék verzió hozzákapcsolta egy dimenzión alapuló alaptermékhez és mindekettő elfogadása és aktválása után, létrehozhat termékkonfigurációkat, és mindegyiknek nevet adhat. A konfigurációkat a tranzakciók generálása előtt létre lehet hozni, vagy amikor szükség van egy bizonyos konfigurációra.

### <a name="suggested-use"></a>Javasolt használat

A dimenzión alapuló konfiguráció technológiát legjobban olyan termékeknél lehet alkalmazni, amelyek változtathatósága korlátozott, és az alap termékdimenziókkal, mérettel, színnel, vagy konfigurációval nem lehet azonosítani a termékváltozatot. Ilyen lehet például a kerékpár keret magassága, kerék mérete, fékbetét-típusok és különböző fokozatok.

### <a name="next-step"></a>Következő lépés 

A következő nyolc feladatútmutató abban a sorrendben van felsorolva, amelyben teljesítenie kell őket. 

1.  [Dimenzión alapuló alaptermék létrehozása](tasks/create-dimension-based-product-master.md)
2.  [Dimenzión alapuló alaptermék kibocsátása](tasks/release-dimension-based-product-master.md)
3.  [Kiadott alaptermék alapbeállításának kitöltése](tasks/complete-basic-setup-released-product-master.md)
4.  [Konfigurációs csoportok meghatározása](tasks/define-configuration-groups.md)
5.  [A dimenzión alapuló alaptermékre vonatkozó anyagjegyzék létrehozása](tasks/create-bill-materials-dimension-based-product-master.md)
6.  [Konfigurációs útvonalak meghatározása](tasks/define-configuration-route.md)
7.  [Konfigurációs szabályok létrehozása](tasks/create-configuration-rules.md)
8.  [Dimenzión alapuló konfigurációk létrehozása](tasks/create-dimension-based-configurations.md)

