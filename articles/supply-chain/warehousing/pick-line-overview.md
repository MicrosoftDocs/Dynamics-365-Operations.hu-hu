---
title: Mobileszköz-menüelem beállítása a kitárolási sor áttekintésének biztosításához
description: Ez a cikk bemutatja, hogy mikor jelenik meg a munkasorok listája a mobileszközön raktári munkát feldolgozó raktári dolgozók számára. Ez a lehetőség olyan raktári dolgozók számára hasznos, akik gyakran igényelnek áttekintést a kivételezési sorokról egy munkarendelésben, hogy optimalizálni tudják a kitárolási sorozatot.
author: Mirzaab
ms.date: 09/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: intro-internal
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-09-03
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: aeadca6f3c31d5d8c1ef9d334b0e531896ac99b1
ms.sourcegitcommit: 203c8bc263f4ab238cc7534d4dd902fd996d2b0f
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/23/2022
ms.locfileid: "9336305"
---
# <a name="set-up-a-mobile-device-menu-item-to-provide-a-pick-line-overview"></a>Mobileszköz-menüelem beállítása a kitárolási sor áttekintésének biztosításához

[!include [banner](../includes/banner.md)]

Ez a témakör leírja, hogyan kell konfigurálni a kitárolási munka feldolgozásához használt mobileszköz-menüpontok kitárolási soráttekintő beállításokat. A kitárolási sor áttekintése a raktári dolgozók számára lehetővé teszi az aktuális feladathoz kapcsolódó összes munkasor listájának megtekintését és a kiválasztást abból. Ez a funkció segítséget nyújt a dolgozóknak a kitárolási folyamat optimalizálásában. A szolgáltatás olyan beállításokat tartalmaz, amelyek a szokásos **Kihagyás** gombot cserélik le, hogy a dolgozók rögzített sorrendben, egyenként haladjanak végig a sorokon. (Ugyanakkor a gomb használatának lehetősége továbbra is elérhető.)

Az adminisztrátorok egyenként állíthatják be az egyes menüelemeket annak meghatározására, hogy a Raktárkezelés mobilalkalmazás milyen módon jeleníti meg a kitárolási sor áttekintését.

## <a name="turn-on-the-work-pick-line-overview-feature"></a>A Munkakitárolási-sor áttekintése funkció bekapcsolása

A funkció használata előtt be kell kapcsolva lennie a rendszeren. A rendszergazdák használhatják a [funkciókezelési](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) beállításokat a funkció állapotának ellenőrzéséhez, és szükség esetén bekapcsolásához. A **Funkció kezelése** munkaterületen a funkció a következő módon van listázva:

- **Modul:** _Raktárkezelés_
- **Funkció neve:** _Munkakitárolási-sor áttekintése_

## <a name="configure-menu-items-to-show-a-list-of-all-work-lines"></a>Menüelemek konfigurálása az összes munkasor listájának megjelenítéséhez

Mobileszköz-menüelem beállításához a kitárolási sor áttekintésének biztosításához kövesse az alábbi lépéseket.

1. Lépjen a **Raktárkezelés \> Beállítás \> Mobileszköz \> Mobileszköz-menüelemek** részre.
1. Válasszon ki vagy hozzon létre a kitárolási munkához kapcsolódó menüelemet, és állítsa be a következő értékeket:

    - **Mód:** *Munka*
    - **Meglévő munka használata:** *Igen*
    - **Irányító:** *Felhasználó által irányított* vagy *Rendszer által irányított*

    A menüelemek létrehozásával és a **Mobileszköz menüpontjai** lapján elérhető különböző beállításokkal kapcsolatos további tudnivalókat lásd: [Mobileszközök beállítása raktári munkához](configure-mobile-devices-warehouse.md).

1. Az **Általános** gyorslapon konfigurálja a szolgáltatást úgy, hogy a **Munkasorok listájának megjelenítése** mezőt a következő értékek valamelyikére állítja:

    - **Csak kérés alapján jelenik meg** – A dolgozók választhatják a kitárolási sor listája megjelenítését ha az **Ugrás a következőre** gombot választják a Raktárkezelés mobilalkalmazásban.
    - **Megjelenítés minden kitárolás kezdetén** – A dolgozók minden alkalommal látják a listát, amikor egy kitárolási sort kezdenek vagy fejeznek be. A listát újra megtekinthetik, ha kiválasztják az **Ugrás a következőre** gombot a Raktárkezelés mobilalkalmazásban.
    - **Megjelenítés csak az első kitárolás kezdetén**: A dolgozók a listát minden új kitárolási munka indításakor látják, de az egyes sorok után nem. A listát újra megtekinthetik, ha kiválasztják az **Ugrás a következőre** gombot a Raktárkezelés mobilalkalmazásban.
    - **Soha ne jelenítse meg** – A szokásos **Kihagyás** gomb látható a Raktárkezelés mobilalkalmazásban, és a munkasorok listájának megjelenítése ki van kapcsolva. A **Kihagyás** gombbal a dolgozók egy rögzített sorrendben válthatnak a sorok között. A listán tetszőleges számú alkalommal is végighaladhatnak, amíg az összes sort fel nem dolgozzák.

1. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.

    Ha a **Munkasorok listájának megjelenítése** mezőt bármilyen a *Soha ne jelenítse meg* értéktől eltérő a Műveleti panel **Mezőlista** gombja elérhetővé válik.

1. A Műveleti ablaktáblán válassza ki a **Mezőlista** lehetőséget.
1. A **Mezőlista** lapon konfigurálja azokat az adatokat, amelyeket a Raktárkezelés mobilalkalmazás a lista minden sorához megjelenít.

    - Az **Elsődleges vezérlés** mező értéke mindig *LineNum*. Ennek megfelelően a lista minden sora egy sorszámmal kezdődik.
    - A többi **Megjelenített mező** mezővel legfeljebb hét további megjeleníthető mezőt adhat hozzá igény szerint. Mindegyik **Megjelenített mező** mezőben válassza ki a munkasor mező nevét. Ekkor minden sor megjelenít egy értéket a mezőben. Az értékek az itt kiválasztott sorrendben jelennek meg. Ha nem szükséges mind a hét érték, akkor üresen hagyhat egyes **Megjelenítendő mező** mezőket.

1. A művelet ablaktáblán válassza a **Mentés** elemet., majd zárja be a **Mezőlista** oldalt.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]