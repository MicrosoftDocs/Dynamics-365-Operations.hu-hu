---
title: Mobileszköz-menüelem beállítása a kitárolási sor áttekintésének biztosításához
description: Ez a témakör azt mutatja be, hogyan lehet meghatározni, hogy az összes munkasor listája mikor jelenik meg a raktári dolgozók számára, akik mobileszközön dolgoznak fel raktári munkát. Ez a lehetőség olyan raktári dolgozók számára hasznos, akik gyakran igényelnek áttekintést a kivételezési sorokról egy munkarendelésben, hogy optimalizálni tudják a kitárolási sorozatot.
author: MarkusFogelberg
manager: tfehr
ms.date: 09/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2020-09-03
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: 433ed2152c47dbe698a640b099cb34727fe63452
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4989693"
---
# <a name="set-up-a-mobile-device-menu-item-to-provide-a-pick-line-overview"></a>Mobileszköz-menüelem beállítása a kitárolási sor áttekintésének biztosításához

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Ez a témakör azt mutatja be, hogyan lehet beállítani a kitárolási munka feldolgozásához használt mobileszköz-menüelemeket, amelyek a kitárolási munka feldolgozásához használatosak. A kitárolási sor áttekintése a raktári dolgozók számára lehetővé teszi az aktuális feladathoz kapcsolódó összes munkasor listájának megtekintését és a kiválasztást abból. Ez a funkció segítséget nyújt a dolgozóknak a kitárolási folyamat optimalizálásában. A szolgáltatás olyan beállításokat tartalmaz, amelyek a szokásos **Kihagyás** gombot cserélik le, hogy a dolgozók rögzített sorrendben, egyenként haladjanak végig a sorokon. (Ugyanakkor a gomb használatának lehetősége továbbra is elérhető.)

Az adminisztrátorok egyenként állíthatják be az egyes menüelemeket annak meghatározására, hogy a raktári alkalmazás milyen módon jeleníti meg a kitárolási sor áttekintését.

## <a name="turn-on-the-work-pick-line-overview-feature"></a>A Munkakitárolási-sor áttekintése funkció bekapcsolása

A funkció használata előtt be kell azt kapcsolnia saját rendszerében. A rendszergazdák használhatják a [funkciókezelési](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) beállításokat a funkció állapotának ellenőrzéséhez, és szükség esetén bekapcsolásához. A **Funkció kezelése** munkaterületen a funkció a következő módon van listázva:

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

    - **Csak kérés alapján jelenik meg** – A dolgozók választhatják a kitárolási sor listája megjelenítését ha az **Ugrás a következőre** gombot választják a raktári alkalmazásban.
    - **Megjelenítés minden kitárolás kezdetén** – A dolgozók minden alkalommal látják a listát, amikor egy kitárolási sort kezdenek vagy fejeznek be. A listát újra megtekinthetik, ha kiválasztják az **Ugrás a következőre** gombot a raktári alkalmazásban.
    - **Megjelenítés csak az első kitárolás kezdetén**: A dolgozók a listát minden új kitárolási munka indításakor látják, de az egyes sorok után nem. A listát újra megtekinthetik, ha kiválasztják az **Ugrás a következőre** gombot a raktári alkalmazásban.
    - **Soha ne jelenítse meg** – A szokásos **Kihagyás** gomb látható a raktári alkalmazásban, és a munkasorok listájának megjelenítése ki van kapcsolva. A **Kihagyás** gombbal a dolgozók egy rögzített sorrendben válthatnak a sorok között. A listán tetszőleges számú alkalommal is végighaladhatnak, amíg az összes sort fel nem dolgozzák.

1. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.

    Ha a **Munkasorok listájának megjelenítése** mezőt bármilyen a *Soha ne jelenítse meg* értéktől eltérő a Műveleti panel **Mezőlista** gombja elérhetővé válik.

1. A Műveleti ablaktáblán válassza ki a **Mezőlista** lehetőséget.
1. A **Mezőlista** lapon konfigurálja azokat az adatokat, amelyeket a raktári alkalmazás a lista minden sorához megjelenít.

    - Az **Elsődleges vezérlés** mező értéke mindig *LineNum*. Ennek megfelelően a lista minden sora egy sorszámmal kezdődik.
    - A többi **Megjelenített mező** mezővel legfeljebb hét további megjeleníthető mezőt adhat hozzá igény szerint. Mindegyik **Megjelenített mező** mezőben válassza ki a munkasor mező nevét. Ekkor minden sor megjelenít egy értéket a mezőben. Az értékek az itt kiválasztott sorrendben jelennek meg. Ha nem szükséges mind a hét érték, akkor üresen hagyhat egyes **Megjelenítendő mező** mezőket.

1. A művelet ablaktáblán válassza a **Mentés** elemet., majd zárja be a **Mezőlista** oldalt.
