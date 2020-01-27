---
title: Fejlécmodul
description: Ez a témakör a fejlécmodulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket létrehozni a Microsoft Dynamics 365 Commerce alkalmazásban.
author: anupamar
manager: annbe
ms.date: 10/31/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar-ms
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: cc98419077f6f563ea2265d4e68ba809971cfbd6
ms.sourcegitcommit: ff93b8f6a11993f2cd00be2da7aa77ef0d950ab8
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/03/2019
ms.locfileid: "2885478"
---
# <a name="header-module"></a>Fejlécmodul

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Ez a témakör a fejlécmodulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket létrehozni a Microsoft Dynamics 365 Commerce alkalmazásban.

## <a name="overview"></a>Áttekintés

A fejlécmodul egy speciális tároló, amely a lapok fejlécében megjelenített modulok tárolására szolgál. Ez lehet például a webhely emblémája, a navigációs hierarchiára mutató hivatkozások, a webhely egyéb lapjaira mutató hivatkozások és a keresősáv.

A program automatikusan optimalizálja a fejlécmodult arra az eszközre, amelyről a webhelyet megtekintik (azaz egy asztali eszközre vagy egy mobileszközre). Egy mobileszköz esetében például a navigációs sáv össze van csukva egy **Menü** gombba (amelyet néha *hamburger menünek* neveznek).

## <a name="properties-of-a-header"></a>Fejléc tulajdonságai

Az általános tárolókhoz hasonlóan a fejlécmodul is támogatja a **fejléc** és **szélesség** tulajdonságokat.

A fejléc modul több helyet tartalmaz. Például vannak helyek a tájékoztató üzenetek, a navigációs menü, az embléma, a keresősáv, a kosár ikon, a kívánságlista ikon és a fiókinformációk számára. Minden hely a modulok meghatározott csoportját támogatja.

## <a name="modules-that-are-available-in-a-header-module"></a>A fejlécmodulban elérhető modulok

A következő modulban használható a fejlécmodulban:

- **Navigációs menü** – A navigációs menü a csatorna navigációs hierarchiáját és más statikus navigációs hivatkozásokat jelenít meg. A csatorna navigációs hierarchiája a Dynamics 365 Retail alkalmazásban állítható be. A konfigurált elemek ezután fejlécnavigációként jelennek meg. Ezenkívül statikus navigációs hivatkozások is konfigurálhatók, és az e-kereskedelmi webhely egyéb lapjaira mutató relatív hivatkozásokat is meg lehet adni. Maga a fejléc balra, jobbra vagy középre igazítható.
- **Kosár ikon** – A kosár ikon a kosarat ábrázoló speciális ikon. Ez a fejlécben látható, és a cikkek számát jelzi a kosárban. A kosárlapra mutató hivatkozást a kosárikonhoz kell társítani, hogy a vevők a kosárlapra legyenek irányítva, amikor a ikonra kattintanak.
- **Kívánságlista ikon** – A kívánságlista ikon a fejlécben látható, és azt jelzi, hogy hány cikket adtak hozzá a vevő kívánságlistájához. A kívánságlista lapra mutató hivatkozást ehhez az ikonhoz kell társítani, hogy a vevők a kívánságlista lapra legyenek irányítva, amikor a ikonra kattintanak.
- **Bejelentkezési modul** – A bejelentkezési modul a fejlécben jelenik meg. A vevők vagy a saját fiókjukba jelentkeznek be, vagy regisztrálnak egy fiókot. Ha a vevő már be van jelentkezve, a modul beállítható úgy, hogy a fióklapra, a rendelési előzmények lapra vagy egy egyéb lapra mutató hivatkozást jelenítsen meg.
- **Logó modul** – Ez a modul a kiskereskedőt és a márkát képviselő logót jeleníti meg. Ez egy kép egy hivatkozással. A hivatkozás általában úgy van beállítva, hogy a kezdőlapra irányítson át, így a vevők gyorsan visszatérhetnek a kezdőlapra a webhely bármely lapjáról.
- **Figyelmeztetés** – A figyelmeztetés a fejlécben jelenik meg, és egy olyan belső üzenetet jelenít meg, amely a webhely minden lapjára vonatkozik. Egy figyelmeztető üzenet például megjelenítheti a következő üzenetet: „Az éves akció 2 napon belül lejár”.
- **Keresősáv** – A keresősáv lehetővé teszi a felhasználók számára, hogy keresési kifejezéseket írjanak be, amelyekkel termékeket kereshetnek. A modult a keresési eredmények lap URL-címével kell konfigurálni. A lekérdezési karakterlánc paraméter konfigurálható (az alapértelmezett érték **„q”**). A keresősáv egy olyan automatikus javaslati helyet tartalmaz, ahol egy automatikus javaslati modul adható hozzá.
- **Automatikus javaslat** – Az automatikus javaslati modul automatikusan javasolt találatokat jelenít meg. Ezek a találatok olyan kulcsszavak, termékek vagy kategóriák lehetnek, amelyekben a keresési kifejezés megtalálható.

## <a name="create-a-header-module"></a>Fejlécmodul létrehozása

Fejlécmodul létrehozásához kövesse az alábbi lépéseket.

1. Hozzon létre egy fejlécmodult tartalmazó laptöredékét.
1. Adjon hozzá modulokat a fejlécmodul helyeihez.
1. Frissítse az egyes modulok beállításait.
1. Mentse a laptöredéket. 
1. Adja be a lapot, és tegye közzé.

Ha azt szeretné, hogy minden lapon megjelenjen a fejléc, hajtsa végre az alábbi lépéseket a webhelyhez létrehozott összes oldalsablon esetében.

1. Az alapértelmezett lapon adja hozzá a fejlécmodult tartalmazó laptöredéket a fő hely fejlécéhez.
1. Mentse a sablont. 
1. Adja be a sablont és tegye közzé.

## <a name="additional-resources"></a>További erőforrások

[Kezdő csomag áttekintése](starter-kit-overview.md)

[Tárolómodul](add-container-module.md)

[Vásárlásmező-modul](add-buy-box.md)

[Kosármodul](add-cart-module.md)

[Fizetésmodul](add-checkout-module.md)

[Rendelésmegerősítési modul](order-confirmation-module.md)

[Fejlécmodul](author-header-module.md)

[Láblécmodul](author-footer-module.md)
