---
title: Pontos ár- és engedményszámítás késleltetése a jobb teljesítmény érdekében
description: Ez a témakör ismerteti Microsoft Dynamics 365 Commerce a késleltetett árszámítási lehetőségeket, amelyek a pénztárnál és a hívásközpontban érhetők el.
author: boycezhu
ms.date: 09/09/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgri
ms.search.region: Global
ms.author: boycez
ms.search.validFrom: 2017-06-20
ms.openlocfilehash: 6926c288a91dbe66b6ffc2e6c06f866d3ebd7652
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8845897"
---
# <a name="delay-exact-price-and-discount-calculation-for-improved-performance"></a>Pontos ár- és engedményszámítás késleltetése a jobb teljesítmény érdekében

[!include [banner](includes/banner.md)]

Ez a témakör ismerteti Microsoft Dynamics 365 Commerce a késleltetett árszámítási lehetőségeket, amelyek a pénztárnál és a hívásközpontban érhetők el.

A Dynamics 365 Commerce többsoros engedmények létrehozását támogatja, amelyek az értékesítési rendelés vagy értékesítési ajánlat több értékesítési sorának kombinálásakor vannak alkalmazva. Ilyen engedmény például a kombinációs, a küszöbérték- és a mennyiségi engedmény.

Amikor új sort adnak egy rendeléshez, a Commerce árképzési motor a teljes kosarat értékeli ki, és meghatározza, hogy alkalmazható-e a többsoros engedmény. Az újraszámítás miatt az új sorok létrehozása befolyásolhatja a teljesítményt, ahogy egy értékesítési rendelés nő.

A vállalatoknak értékesítő (B2B) vállalatoknak és néhány fogyasztóknak értékesítő vállalatnak (B2C) gyakran nagy rendelési méretük van. Emiatt az árképzési motorrra hosszú ideig fog várni, amíg az egyes cikkek a kosárba kerülése után elvégzésre kerül az újraszámítás. Ezenkívül a nagy rendeléseknél általában nem nagyon fontos, hogy a pontos ár és engedmény mindig látható legyen minden olyan alkalommal, amikor cikket adnak a kosárhoz. Fontosabb, hogy a felhasználók gyorsan hozzá tudjanak adni cikkeket. Jelentős mértékben javíthatja a teljesítményt az a képesség, amely a pontos ár- és engedményszámítást elhalasztja, amíg egy felhasználó véglegesít egy rendelést vagy nagy javításokat végez azon. Ez csökkentheti a rendelés befejezéséhez szükséges időt is.

A pénztárban már hosszú ideje elérhető a pontos ár- és engedményszámítás késleltetésének képessége. A Commerce rendszer 10.0.22-es verziójától a hívásközpontban is elérhető.

## <a name="enable-delayed-price-and-discount-calculation-for-pos"></a>Késleltetett ár- és engedményszámítás engedélyezése a pénztárhoz

Késleltetett ár- és engedményszámítás engedélyezéséhez a pénztárhoz kövesse az alábbi lépéseket.

1. A Commerce központ szolgáltatásban menjen a fizikai üzlethez társított funkcióprofilhoz.
1. Az **Összeg** gyorslapon engedélyezze a **Több cikkengedmény manuális számítása** konfigurációt.
1. Nyissa meg a képernyőelrendezés-tervezőt azokkal a pénztárgépekkel, amelyekben engedélyezni szeretné a késleltetett számítást.
1. Az **Összesítés számítása** művelethez gomb hozzáadása a kívánt gombrácshoz.
1. Futtassa az **1070**-es és az **1090**-es feladatokat.

Amikor cikkeket adnak hozzá egy tranzakcióhoz, a többsoros engedmények számítása csak akkor történik meg, ha a pénztáros a **Végösszeg számítása** gombot választja. Miután kiválasztotta egy tranzakcióhoz a **Végösszeg számítása** lehetőséget, a többsoros engedmények számítása mindig meg fog történni. A pénztárosnak nem kell újra kiválasztania a gombot, még akkor sem, ha további cikkeket adnak hozzá a kosárhoz. A rendszer mindaddig nem engedélyezi a pénztáros számára a fizetés rögzítését, amíg nincs kiválasztva a **Végösszeg kiszámítása** lehetőség.

## <a name="enable-delayed-price-and-discount-calculation-for-call-center"></a>Késleltetett ár- és engedményszámítás engedélyezése a hívásközponthoz

Késleltetett ár- és engedményszámítás engedélyezéséhez a hívásközponthoz kövesse az alábbi lépéseket.

1. Funkciókezelés munkaterületen válassz a **Munkaterületek \> Funkciókezelés** lehetőséget.
1. Kapcsolja be a **Kereskedelmi rendelések véletlen árszámításának megakadályozása** funkciót. Ez a funkció előfeltétele a késleltetett ár- és engedményszámítási képességnek.

    > [!NOTE]
    > Az új telepítések esetén alapértelmezés szerint engedélyezve van a **Kereskedelmi rendelések véletlen árszámításának megakadályozása** funkció.

1. Menjen a **Kereskedelmi paraméterek \> Árak és engedmények** menüpontba.
1. A **Vegyes** szakaszban engedélyezze a **Többsoros árak és engedmények manuális számítása** konfigurációt.

Most, amikor értékesítési rendelést vagy értékesítési ajánlatot hoznak létre vagy szerkesztnek a hívásközpontban, a rendelés pontos árának és engedményének számítása késleltetve lesz. Az árképzési motor csak a hozzáadott vagy szerkesztett értékesítési sorokat veszi figyelembe, az összes többi értékesítési sort figyelmen kívül hagyja. A cikk nettó összege tartalmazza az árszámítást és az egyszerű engedményeket (engedmény százaléka vagy összeg egy adott cikkre). A kombinációs, a küszöbérték- és mennyiségi engedmények azonban nem lesznek alkalmazva. A hívásközponti felhasználók, akik a pontos árat szeretnék megtekinteni, beleértve az összes engedményt, a következő három gomb közül választhatnak: **Újraszámítás**, **Összesítés** vagy **Befejezés**.

> [!NOTE]
> Hívásközponti rendelések esetén a rendszer figyelmeztető üzenetet küld, amely figyelmezteti a felhasználót, hogy a pontos ár- és engedményszámításhoz be kell választania az **Újraszámítás**, az **Összegek** vagy a **Befejezés** gombot. Olyan rendelések esetén, amelyekben elérhető a **Befejezés** gomb, nincs lehetőség arra, hogy a hívásközpont felhasználója kihagyja a pontos ár- és engedményszámítást, mivel a rendelés rögzítéséhez a **Befejezés** lehetőséget kell választania. Olyan rendelésekhez, amelyekben a **Befejezés** gomb nem érhető el, nincs a rendelésrögzítés befejezését jelző művelet. Ezért a hívásközpont felhasználója felelős az **Újraszámítás** vagy a **Végösszeg** kiválasztásáért, mielőtt befejezik a rendelés rögzítését.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
