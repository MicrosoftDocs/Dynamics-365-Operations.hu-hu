---
title: Eszköz életciklus-állapotai
description: Ez a témakör bemutatja az eszközök életciklusának állam- és életciklusmodelljeit az Eszközkezelésben.
author: johanhoffmann
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetLifecycleModelStateNext, EntAssetObjectLifecycleState, EntAssetLifecycleStateUpdate, EntAssetObjectLifecycleModel
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 43b1ff9438437e6c1ff33bab9a7ba0361029cb6d
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8901060"
---
# <a name="asset-lifecycle-states"></a>Eszköz életciklus-állapotai

[!include [banner](../../includes/banner.md)]

 

Ez a témakör bemutatja az eszközök életciklusának állam- és életciklusmodelljeit az Eszközkezelésben. Az eszköz életciklus-állapota határozza meg, hogy az eszköz aktív vagy inaktív-e. Például beállíthat olyan eszköz-életciklusállapotokat, mint **Létrehozott**, **Aktív** vagy **Megszakított**.

> [!NOTE]
> - A kérések életciklus-állapotai kapcsolódnak az eszköz életciklus-állapotaihoz. Ezért ha egy kérés új kérési életciklus-állapotra módosul, akkor a kéréshez csatolt eszköz életciklus-állapota is egy újra módosul. Például ha egy kérés életciklus-állapota **Bejövő** lesz, akkor a csatolt eszköz életciklus-állapota arra az életciklus-állapotra módosul, amelyet az **Eszköz életciklus-állapotának modelljei** oldal **Eszköz életciklus-állapot** gyorslapjának **Bejövő életciklus-állapot** mezőjében ki van választva. 


Az eszközéletciklus-állapotok beállíthatók az eszköz életciklusmodelljein, ahol meghatározhatja a különböző típusú eszközökhöz szükséges életciklus-állapotokat. Először be kell állítani az életciklus-állapotokat. Ezután létre kell hoznia egy életciklusmodellt, és ki kell választania a hozzá tartozó életciklus-állapotokat.

1. Válassza ki az **Eszközkezelés** \> **Beállítás** \> **Eszközök** \> **Életciklus-állapotok** elemet.
2. Válassza az **Új** lehetőséget egy új eszköz életciklus-állapot létrehozásához.
3. Az **Életciklus-állapot** mezőben adja meg az életciklus-állapot azonosítóját.
4. A **Név** mezőbe adja meg a leírást.

    Az **Életciklusmodellek** mezőben látható az adott eszközéletciklus-állapotot használó életciklusmodellek száma.

5. Állítsa az **Aktív** beállítást **Igen** értékre, ha ez az életciklus-állapot aktív életciklus-állapot legyen (azaz munkarendeléseket lehet létrehoznia az ilyen életciklus-állapotú eszközökhöz).
6. Állítsa a **Nyitott naptársorok törlése** beállítást **Igen** értékre, ha a **Létrehozott** eszközéletciklus-állapottal rendelkező nyitott eszköznaptársorokat törölni kell, ha ebben az életciklus-állapoban vannak. Ez a beállítás akkor hasznos, ha el szeretné takarítani azokat a nyitott karbantartási ütemezéseket, amelyek az eszköz szempontjából már nem relevánsak (például, ha az eszköz már nem aktív).

> [!NOTE]
> Az eszközéletciklus-állapotok, eszközéletciklus-modellek és eszköztípusok kapcsolódnak egymáshoz. Ugyanúgy használhatók, mint a munkarendelések életciklus-állapotai, a munkarendelés életciklus-modelljei és a munkarendelés-típusok. 


Miután létrehozta a szükséges eszközéletciklus-állapotokat, beállíthat életciklus-állapotokat az eszközéletciklus-modellekben.

1. Válassza ki az **Eszközkezelés** \> **Beállítás** \> **Eszközök** \> **Életciklusmodellek** elemet.
2. Válassza az **Új** lehetőséget egy új eszköz életciklusmodell létrehozásához.
3. Az **Életciklusmodell** mezőben adja meg az életciklusmodell azonosítóját.
4. A **Név** mezőbe adja meg a leírást.

    Az **Életciklus-állapotok** mezőben látható az adott eszközéletciklus-modellben kiválasztott eszközéletciklus-állapotok száma. Az **Eszköztípusok** mezőben az életciklusmodellt használó eszköztípusok száma látható.

5. Az **Életciklus-állapotok** gyorslapon válassza ki azokat az eszközéletciklus-állapotokat, amelyeket fel kell venni az eszközéletciklus-modellbe:

    - Ha életciklus-állapotot szeretne használni a modellhez, válassza ki azt a **Hátralévő életciklus-állapotok** szakaszban, majd válassza a jobb nyílgombot ![Jobb nyíl.](media/15-setup-for-objects.png) elemet az áthelyezéshez az **Életciklus-állapotok kiválasztva** szakaszba.
    - Ahhoz, hogy az összes elérhető életciklus-állapotot használhassa a modellhez, nyomja meg az **Összes elérhető életciklus-állapot** ![Összes elérhető életciklus-állapot.](media/20-setup-for-objects.png) gombot. Az összes életciklus-állapot a **Kijelölt életciklus-állapotok** szakaszba kerül.
    - Ha életciklus-állapotot szeretne eltávolítani a modellből, válassza ki azt a **kiválasztott életciklus-állapotok** szakaszban, majd válassza a bal nyílgombot ![Bal nyíl.](media/16-setup-for-objects.png) elemet az áthelyezéshez a **Fennmaradó életciklus-állapotok** szakaszba.

6. Válassza az **Életciklus-állapot frissítései** elemet, amellyel meghatározhatja a kijelölt életciklus-állapotot követő eszközéletciklus-állapotokat.
7. Az **Eszközállapot** gyorslapon a javításra kapott eszközök kezelése használható. A **Bejövő/kimenő** szakaszban kiválaszthat eszközéletciklus-állapotokat, amelyekkel jelezheti a javításra kapott eszköz munkafolyamatát. Ha ügyfelei vagy részlegei számára hiteleszközöket kínál, akkor a **Kölcsön** részben kiválaszthatja a kölcsönzött eszközökre vonatkozó életciklus-állapotokat.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]