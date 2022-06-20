---
title: Származási ország
description: Számos szervezet állít ki tanúsítványt a szállítóknak annak biztosítása érdekében, hogy a termékek megfelelnek a meghatározott minősítési szabványoknak. Ezek a tanúsítványok gyakran a származási országtól függenek. Ez a cikk a származási ország funkcióval kapcsolatban tartalmaz tájékoztatást, amellyel összekapcsolhatja a cikkeket a származási országgal, és nyomon követheti a termék tanúsítványát.
author: t-benebo
ms.date: 07/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: COOVendorCerts
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-07-15
ms.dyn365.ops.version: 10.0.9
ms.openlocfilehash: 60d5a2067b8e3d311af89fb09cfa3b5c007db219
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8882518"
---
# <a name="country-of-origin"></a>Származási ország

[!include [banner](../includes/banner.md)]

Számos szervezet állít ki tanúsítványt a szállítóknak annak biztosítása érdekében, hogy a termékek megfelelnek a meghatározott minősítési szabványoknak. Ezek a tanúsítványok gyakran a származási országtól függenek. Aa származási ország funkció lehetővé teszi, hogy a terméket a származási országhoz kapcsolja, és nyomon kövesse a termék minősítéseit.

## <a name="turn-on-the-country-of-origin-feature"></a>A származási ország funkció bekapcsolása

Az Ellátásilánc-kezelés 10.0.21-es verziója szerint ez a funkció alapértelmezés szerint be van kapcsolva. A rendszergazdák a Szolgáltatáskezelés [lapon ellenőrizhetik](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) a funkció állapotát, és szükség esetén engedélyezhetik vagy letilthatják azt. Itt a funkció a következőként szerepel:

- **Modul:** *Termékinformáció-kezelés*
- **Funkció neve:** *Származási ország kezelési funkciója*

## <a name="configure-source-and-destination-countries"></a>Forrás- és célországok konfigurálása

A termékre vonatkozó tanúsítvány kiállítása előtt csatolni kell a terméket a célországhoz és a származási országhoz.

1. Lépjen a **Termékinformációk kezelése \> Beállítás \> Termék megfelelősége \> Származási ország \> Származási ország szabályai** elemre.
2. Válasszon ki egy meglévő országbeállítást a szerkesztéshez, vagy a műveleti ablak **új** elemét választva hozzon létre egy új ország-beállítást.
3. Állítsa be a következő értékeket a kiválasztott vagy az új országhoz.

    | Mező | Leírás |
    |---|---|
    | Cikkszám | Válassza ki a termék cikkszámát. |
    | Célország | Válassza ki azt az országot, ahova a terméket küldeni szeretné. |
    | Származási ország | Válassza ki azt az országot, ahonnan a terméket küldeni szeretné. |

Ennek a beállításnak az a célja, hogy segítséget jelentsen egy darabjegyzék (BOM)-jelentés létrehozásához, ahol megadhatja a származási országot mindegyik részhez, ahol a forrás- és célországot meg kell adni. Ez a jelentés segít Önnek teljes körű képet kapni arról, hogy honnan jönnek az alkatrészek, és hová mennek.

## <a name="keep-track-of-vendor-certificates"></a>Szállítói tanúsítványok nyomon követése

A **Származási ország szállítói tanúsítványai** oldalon nyomon követheti azokat az minősítéseket, amelyeket szállítóknak kibocsátott.

El kell döntenie, hogy mely minősítési dokumentumokat kell kiadnia, és hogyan fogja jelenteni azokat a vevők számára. Ez a funkció segít nyomon követni a tanúsítványokat. Azt is megadhatja, hogy a megfelelő tanúsítványszámok szerepeljenek-e a számlákon, a szállítóleveleken és/vagy a rendelés-visszaigazolásokon.

A tínúsítványadatok beállításához kövesse az alábbi lépéseket.

1. Lépjen a **Termékinformációk kezelése \> Beállítás \> Termék megfelelősége \> Származási ország \> Származási ország szállítói tanúsítványai** elemre.
2. Válasszon ki egy meglévő tanúsítványbeállítást a szerkesztéshez, vagy a műveleti ablak **új** elemét választva hozzon létre egy új tanúsítványbeállítást.
3. Állítsa be a következő beállításokat a kiválasztott vagy az új tanúsítványra.

    | Mező | Leírás |
    |---|---|
    | Szállítói számla | Válassza ki azt a szállítót, akinek a tanúsítványt kibocsátotta. |
    | Cikkszám | Válassza ki azt a cikket, akinek a tanúsítványt kibocsátotta. |
    | Ország/régió | A célország vagy régió, ahol a tanúsítványt használni kell. |
    | Tanúsítványszám | Adja meg a kibocsátott tanúsítvány azonosítószámát. |
    | Hatályos | Válassza ki az első dátumot, amikor az aktuális tanúsítvány érvényes.|
    | Lejárat | Válassza ki az utolsó dátumot, amikor az aktuális tanúsítvány érvényes. |
    | Nyomtatás számlára | Jelölje be ezt a jelölőnégyzetet, ha a megadott dátumtartomány során a megadott országnak címzett számlákra rá szeretné nyomtatni a tanúsítvány számát. |
    | Nyomtatás szállítólevélre | Jelölje be ezt a jelölőnégyzetet, ha a megadott dátumtartomány során a megadott országnak címzett szállítólevelekre rá szeretné nyomtatni a tanúsítvány számát. |
    | Nyomtatás az értékesítési rendelésre | Jelölje be ezt a jelölőnégyzetet, ha a megadott dátumtartomány során a megadott országnak címzett értékesítési rendelésekre rá szeretné nyomtatni a tanúsítvány számát. |

## <a name="include-the-country-of-origin-on-bom-reports"></a>A származási ország szerepeltetése a darabjegyzék-jelentésekben

Ha DBJ-jelentést hoz létre, akkor a **Származási ország szabályai** oldal mindegyik részénél szerepeltetheti a származási országot, amelyhez meghatározta a cél- és forrásországokat.

1. Kattintson a **Termékinformációk kezelése \> Termékek \> Kiadott termékek** lehetőségre.
1. Válasszon ki vagy hozzon létre egy terméket, és nyissa meg a **Kapcsolódó termékadatok** oldalát.
1. A Műveleti ablaktáblán a **Tervező** lapon a **DBJ** csoportban válassza a **Tervező** lehetőséget.
1. A megjelenő oldalon a műveleti ablaktáblán kattintson a **DBJ \> Nyomtatás** lehetőségre.
1. A **Darabjegyzéksorok** párbeszédablakban állítsa a **Célország** mezőt a jelentésen megtekinteni kívánt célországra.
1. Válassza ki az **OK** lehetőséget.

Létrejön és megjelenik egy jelentés, amely információt jelenít meg a származási országról az egyes alkatrészekhez. Íme, egy példa a jelentésre.

![Származási ország jelentés.](media/country-of-origin-report.png "Származási ország jelentés")


[!INCLUDE[footer-include](../../includes/footer-banner.md)]