---
title: A felhasználói felület elemei
description: Ez a témakör az alkalmazásban használt felhasználói felület (UI) elemeit mutatja be.
author: tlefor
manager: AnnBe
ms.date: 08/09/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: ''
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: tlefor
ms.search.validFrom: ''
ms.dyn365.ops.version: 7.2999999999999998
ms.openlocfilehash: 8087090b16ddbcf9586ae289c6ec7c1d23087422
ms.sourcegitcommit: c0929ebda9dfb7affe2a187336abf980ce2009a6
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2020
ms.locfileid: "2994118"
---
# <a name="user-interface-elements"></a>A felhasználói felület elemei

Ez a témakör az alkalmazásban használt felhasználói felület (UI) elemeit mutatja be. Mielőtt a felhasználók navigálni tudnak a kezelőfelületen, fontos tudni a felületet alkotó elemek neveit és funkcióit.

## <a name="overview"></a>Áttekintés

- **Műveleti ablaktábla** – a navigációs sáv alatti sáv. Itt választhatja ki az oldalon látható rekordok módosítására szolgáló lapokat. A rekordok itt szerkeszthetők és menthetők.  
- **Adatterület** – a panelen megjelenítheti az adatokat, és nyomon követheti az egyes rekordok műveleteit.  
- **Adatterületek ablaktábla** itt lapozhatja át a rekord különböző szempontjait, amely az adatterületen látható.  
- **Szűrési ablaktábla** – Egyes oldalakon a **Szűrők megjelenítése** lehetőséggel megnyithatja ezt az ablaktáblát. Ez lehetővé teszi a lapon látható eredmények szűkítését.  
- **Navigációs sáv** – a felület felső részén található sáv. Itt található a **Dynamics 365 portál**, a **Keresés**, a **Vállalatválasztó**, a **Műveleti központ**, a **Beállítások**, a **Súgó és támogatás**, valamint a felhasználói profil.  
- **Navigációs lista** – egyes oldalakon az ablaktáblán görgetve megkeresheti a megadott rekordot. Ha be van jelölve, akkor a rekord adatai megjelennek a lapon.  
- **Navigációs ablaktábla** - A leginkább bal oldali ablaktábla. Innen a termék bármelyik lapját megtalálhatja.  
- **Oldal** – a felület központi fókusza. A többi felhasználóifelület-összetevőn végzett kiválasztások befolyásolják, hogy itt milyen rekordok jelennek meg.  
- **Ablaktábla** - A leginkább jobb oldali ablaktábla. Ez bizonyos esetekben megnyílik, amikor a rekordok jellemzőit módosítani és menteni kell.  
- **Lap** – a műveleti ablakra történő hivatkozáskor ez egy olyan beállítási menü, amely akkor jelenik meg, ha a műveleti ablaktáblában kiválasztja a megadott beállítást.  

![A következő kép bemutatja ezeknek az elemeknek az elhelyezkedését a kezelőfelületen.](media/user-interface-01.png)

## <a name="tabs-fields-and-sections"></a>Lapok, mezők és szakaszok

A *lap* egy kiválasztás az oldalon, amely egy rekord másik aspektusát nyitja meg ugyanazon az oldalon. Gyakran engedélyezi bizonyos *mezők* módosítását, vagy olyan felhasználóifelület-elemekét, amelyek gépelt bevitelt engedélyeznek. 

A *Gyorslap* egy olyan lap, amelynek további előnye, hogy egyszerre több lapot is láthatóvá tesz. A gyorslap kibontásához kattintson a jobb szélén látható lefelé mutató nyílra.

![A következő kép egy példát mutat a lapokra és Gyorslapokra.](media/user-interface-02.png)

A *szakasz* hasonló egy laphoz. A „szakasz” szót gyakran használják egy oldal olyan területeinek leírására, amelyek információk egy megadott kategóriáját tartalmazzák. A következő képen a szakaszok példái láthatók: Összegzés, Rendelések és kedvencek, valamint Hivatkozások.

![A következő kép egy példát mutat a lapokra és szakaszokra.](media/user-interface-03.png)

## <a name="dialog-boxes-and-drop-down-menus"></a>Párbeszédpanelek és legördülő menük

A *párbeszédpanel* egy olyan ablak, amely akkor jelenik meg, amikor bizonyos kiválasztásokkal egy rekordot kívánnak módosítani vagy létrehozni. A párbeszédpanelek olyan mezőket tartalmaznak, amelyek lehetővé teszik gépelt bemenetek megadását. Előfordulhat, hogy egy megadott mezőből ki lehet választani egy lefelé mutató nyilat, amely megnyitja a választható lehetőségek listáját. Ezt nevezzük *legördülő menünek*. Az alábbi képen a **Típus** és **Vevőcsoport** mezőkben szerepel a legördülő menü megnyitási lehetősége.

![A következő kép egy példát mutat a párbeszédpanelekre.](media/user-interface-04.png)

Bizonyos esetekben egy párbeszédpanel nyílik meg egy adott gomb mellett, amikor rákattint. Ezt nevezzük *legördülő párbeszédablaknak*. Az alábbi képen kiválasztottuk az **Adott naptól** gombot, amely megnyitott egy legördülő párbeszédpanelt.

![A következő kép egy példát mutat a legördülő párbeszédpanelekre.](media/user-interface-05.png)

## <a name="notifications"></a>Értesítések

A felügyelt objektumok bizonyos módosításai *értesítésekként* jelennek meg. A rendszer értesítésekkel tájékoztathatja, amikor egy bizonyos ügyfél adatai módosultak, vagy figyelmezteti, amikor a rendszer nem fogadja el a bizonyos mezőkbe bevitt értékeket. Megtanulhatja, hogy hogyan szabályozhatja, hogy miről kapjon értesítéseket a [Figyelmeztetések áttekintése](../get-started/alerts-overview.md) részben.

Az értesítések számos módon megjelennek.
- **Funkcióbuborék** – Ez egy mező, lap vagy más gomb mellett jelenik meg, és magyarázatot nyújt a funkció használati módjára. 
- **Műveleti központ** - Az értesítést tartalmazó mező a navigációs sávon, a Műveleti központ gomb mellett jelenik meg. Az értesítéssel kapcsolatos részleteket a **Műveleti központ** kiválasztásával jelenítheti meg .  
- **Üzenetsáv** – ez a műveleti ablaktábla alatt fog megjelenni.  

A következő kép példákat mutat be az ilyen típusú értesítésekre.

![A következő kép példákat mutat be az értesítésekre.](media/user-interface-06.png)

- **Üzenetpanel** – Ez a felületen keresztben jelenik meg, és reagálni kell rá, mielőtt folytathatná a termék használatát.  

![A következő kép egy példát mutat az üzenetpanelekre.](media/user-interface-07.png)

## <a name="toolbars-grids-and-lists"></a>Eszköztárak, rácsok és listák

Az *eszköztár* olyan eszközöket tartalmaz, mint például a mezők hozzáadásának vagy a rekordok eltávolításának a képessége. Előfordulhat, hogy egy oldalon egy eszköztár egy *rács* fölött jelenik meg. Ez a terület, a rács, a rekordok sorainak és a hozzájuk kapcsolódó különböző adatoszlopoknak adott név. Nem minden rács felett van eszköztár.

A *lista* rekordok gyűjteményének a neve, amelyeket át lehet görgetni. Ezeket a rekordokat átviheti az oldalra, ha kijelöli őket. Ez a művelet gyakran egy rácsot nyit meg.

![A következő kép példákat mutat be az eszköztárakra, rácsokra és listákra.](media/user-interface-08.png)
