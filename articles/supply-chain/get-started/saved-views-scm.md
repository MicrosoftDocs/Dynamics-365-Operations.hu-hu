---
title: A Supply Chain Management szabványos mentett nézetei
description: Ez a témakör a rendelkezésre álló szabványos mentett nézeteket írja le, és bemutatja az ilyen nézetek engedélyezésének a módszerét.
author: kamaybac
ms.date: 08/05/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2021-02-03
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: f94fffb9aa2c208b8c2c0005a2892853eda66a01
ms.sourcegitcommit: 203c8bc263f4ab238cc7534d4dd902fd996d2b0f
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/23/2022
ms.locfileid: "9334835"
---
# <a name="standard-saved-views-for-supply-chain-management"></a>A Supply Chain Management szabványos mentett nézetei

[!include [banner](../../includes/banner.md)]

A Microsoft Dynamics 365 Supply Chain Management számos mentett nézetet tartalmaz, amelyek a szükséges módon engedélyezhetők és használhatók. A szabványos mentett nézetek közül néhány egy konkrét szerepkörre vagy feladatra van optimalizálva vagy azok után van elnevezve (például „Minőség-ellenőrzés” vagy „Bevétel”). Mások optimalizálása úgy történik, hogy csak azokat a mezőket és beállításokat tartalmazzák, amelyekre a Microsoft használati statisztikája úgy utal mint a vevők által leggyakrabban használtakra. Ezeket a mentett nézeteket általában *egyszerűsített* nézeteknek is nevezik. Ez a témakör az elérhető szabványos mentett nézeteket írja le, és bemutatja az ilyen nézetek engedélyezését és testreszabását.

A mentett nézetekkel való munkavégzésről (a szabványos mentett nézeteket is beleértve) az engedélyezésüket követő részletes információkért lásd: [Mentett nézetek](../../fin-ops-core/fin-ops/get-started/saved-views.md?toc=/dynamics365/supply-chain/toc.json).

## <a name="customizing-the-standard-saved-views"></a>A szabványos mentett nézetek testreszabása

Testreszabhatja a szabványos mentett nézeteket, ahogy a saját mentett nézeteit is. Ha azonban testreszab egy szabványos mentett nézetet, javasoljuk, hogy új néven mentse az egyéni verziót. Ellenkező esetben az Supply Chain Management frissítése során felülírhatók lesznek a testreszabások.

A mentett nézetek testreszabásáról és átnevezéséről lásd: [Mentett nézetek](../../fin-ops-core/fin-ops/get-started/saved-views.md?toc=/dynamics365/supply-chain/toc.json).

## <a name="available-saved-views-and-how-to-enable-them"></a>Elérhető mentett nézetek és engedélyezésük

A mentett nézetek használatához – függetlenül attól, *·*[hogy](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) a normál mentett nézeteket fogja-e használni – be kell kapcsolnia a Funkciókezelés Mentett nézet funkcióját (a 10.0.21-es verzióban ez a funkció alapértelmezés szerint engedélyezve van).

A cikk további részei olyan táblákat tartalmaznak, amelyek leírják az egyes modulokban jelenleg elérhető szabványos mentett nézeteket. Minden tábla megjeleníti az egyes mentett nézeteket, azt a lapot, ahol megtalálható, valamint a leírását. Minden tábla a mentett nézetet tartalmazó funkció nevét is megjeleníti. Ha egy szabványos mentett nézetet meg szeretne tekinteni a rendszerben, be kell kapcsolnia a [Funkciókezelés](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) helyen megadott funkciót. A 10.0.25-ös verziótól minden felsorolt nézet alapértelmezés szerint be van kapcsolva.

## <a name="saved-views-for-the-inventory-management-module"></a>A Készletkezelési modul mentett nézetei

Az alábbi táblázat leírja a Készletkezelési modulban elérhető mentett nézeteket.

| Oldal | Nézet neve | A leírás megtekintése | Funkció neve |
|---|---|---|---|
| Aktuális készlet listája | Pénzügyek | Ezzel az egyszerűsített nézettel a pénzügyi információkra fókuszálhat az aktuális készlet kezelése közben. | Mentett nézetek a készletgazdálkodáshoz<br><br>(Alapértelmezés szerint a 10.0.21-es verziónak van beállítva. Kötelező a verziószám szerint 10.0.29.) |
| Aktuális készlet listája | Minőség-ellenőrzés | Ezzel az egyszerűsített nézettel a minőség-ellenőrzésre fókuszálhat az aktuális készlet kezelése közben. | Mentett nézetek a készletgazdálkodáshoz<br><br>(Alapértelmezés szerint a 10.0.21-es verziónak van beállítva. Kötelező a verziószám szerint 10.0.29.) |
| Aktuális készlet listája | Bevételezés | Ezzel az egyszerűsített nézettel a bevételezési műveletekre fókuszálhat az aktuális készlet kezelése közben. | Mentett nézetek a készletgazdálkodáshoz<br><br>(Alapértelmezés szerint a 10.0.21-es verziónak van beállítva. Kötelező a verziószám szerint 10.0.29.) |
| Aktuális készlet listája | Kiszállítás | Ezzel az egyszerűsített nézettel a szállítási műveletekre fókuszálhat az aktuális készlet kezelése közben. | Mentett nézetek a készletgazdálkodáshoz<br><br>(Alapértelmezés szerint a 10.0.21-es verziónak van beállítva. Kötelező a verziószám szerint 10.0.29.) |
| Tranzakciók | Egyszerűsített | Ezzel az egyszerűsített nézettel anélkül lehet áttekinteni a készlet állapotát, hogy a pénzügyi adatok és a kevésbé gyakran használt mezők elvonnák a figyelmet. | Mentett nézetek a készletgazdálkodáshoz<br><br>(Alapértelmezés szerint a 10.0.21-es verziónak van beállítva. Kötelező a verziószám szerint 10.0.29.) |
| Átmozgatási rendelések | Kiszállítás | Ezzel az egyszerűsített nézettel a szállítási műveletekre fókuszálhat az átmozgatási rendelések kezelése közben. | Mentett nézetek a készletgazdálkodáshoz<br><br>(Alapértelmezés szerint a 10.0.21-es verziónak van beállítva. Kötelező a verziószám szerint 10.0.29.) |
| Átmozgatási rendelések | Bevételezés | Ezzel az egyszerűsített nézettel a bevételezési műveletekre fókuszálhat az átmozgatási rendelések kezelése közben. | Mentett nézetek a készletgazdálkodáshoz<br><br>(Alapértelmezés szerint a 10.0.21-es verziónak van beállítva. Kötelező a verziószám szerint 10.0.29.) |
| Átmozgatási rendelések | Minőség-ellenőrzés | Ezzel az egyszerűsített nézettel a minőség-ellenőrzésre fókuszálhat az átmozgatási rendelések kezelése közben. | Mentett nézetek a készletgazdálkodáshoz<br><br>(Alapértelmezés szerint a 10.0.21-es verziónak van beállítva. Kötelező a verziószám szerint 10.0.29.) |
| Átmozgatási rendelések | Pénzügyek | Ezzel az egyszerűsített nézettel a pénzügyi információkra fókuszálhat az átmozgatási rendelések kezelése közben. | Mentett nézetek a készletgazdálkodáshoz<br><br>(Alapértelmezés szerint a 10.0.21-es verziónak van beállítva. Kötelező a verziószám szerint 10.0.29.) |

## <a name="saved-views-for-the-master-planning-module"></a>Az Alaptervezési modul mentett nézetei

Az alábbi táblázat leírja az Alaptervezési modulban elérhető mentett nézeteket.

| Oldal | Nézet neve | A leírás megtekintése | Funkció neve |
|---|---|---|---|
| Tervezett rendelések: Tervezett rendelés részletei oldal | Egyszerűsített | Ez az egyszerűsített nézet csak azokat a mezőket tartalmazza, amelyek az egyetlen tervezett rendelés részleteivel kapcsolatos munkához leggyakrabban használhatók. Ily módon gyorsabb áttekintést és egyszerűbb munkafolyamatot nyújt. | Tervezett rendelések mentett nézete<br><br>(Alapértelmezés szerint a 10.0.25-ös verzióban. Kötelező a verziószám szerint 10.0.29.) |
| Tervezett rendelések: Tervezett rendelések listája oldal | Egyszerűsített | Ez az egyszerűsített nézet csak azokat a mezőket tartalmazza, amelyek a tervezett rendelés listájával kapcsolatos munkához leggyakrabban használhatók. Ily módon gyorsabb áttekintést és egyszerűbb munkafolyamatot nyújt. | Tervezett rendelések mentett nézete<br><br>(Alapértelmezés szerint a 10.0.25-ös verzióban. Kötelező a verziószám szerint 10.0.29.) |

## <a name="saved-views-for-the-procurement-and-sourcing-module"></a>A Beszerzés és forrás modul mentett nézetei

Az alábbi táblázat leírja a Beszerzés és forrás modulban elérhető mentett nézeteket.

| Oldal | Nézet neve | A leírás megtekintése | Funkció neve |
|---|---|---|---|
| Beszerzési rendelés részletei | Rendelés létrehozása | Ez az egyszerűsített nézet az új beszerzési rendelések létrehozásához van optimalizálva. | Mentett nézetek beszerzési rendelésekhez<br><br>Alapértelmezés szerint a 10.0.25-ös verzióban. Kötelező a verziószám szerint 10.0.29.) |
| Beszerzési rendelés részletei | Készletgazdálkodás | Az egyszerűsített nézet a készlettel kapcsolatos tevékenységek végrehajtásához van optimalizálva, például a bevételezésre került készletre, a bevételezésre, a nettó követelmények ellenőrzésére és a rendelési mennyiségek módosítására. | Mentett nézetek beszerzési rendelésekhez<br><br>Alapértelmezés szerint a 10.0.25-ös verzióban. Kötelező a verziószám szerint 10.0.29.) |
| Beszerzési rendelés részletei | Pénzgazdálkodás | Ez az egyszerűsített nézet a pénzügyekkel kapcsolatos tevékenységek, például az árak, az összegek és a költségek számlázása és ellenőrzése érdekében optimalizálható. | Mentett nézetek beszerzési rendelésekhez<br><br>Alapértelmezés szerint a 10.0.25-ös verzióban. Kötelező a verziószám szerint 10.0.29.) |
| Beszerzési rendelés részletei | Megrendelés jóváhagyása | Ez az egyszerűsített nézet az új beszerzési rendelések jóváhagyásához van optimalizálva. | Mentett nézetek beszerzési rendelésekhez<br><br>Alapértelmezés szerint a 10.0.25-ös verzióban. Kötelező a verziószám szerint 10.0.29.) |

## <a name="saved-views-for-the-product-information-management-module"></a>A Termékinformáció kezelése modul mentett nézetei

Az alábbi táblázat leírja a Termékinformációk kezelése modulban elérhető mentett nézeteket.

| Oldal | Nézet neve | A leírás megtekintése | Funkció neve |
|---|---|---|---|
| Megjelent termékek listája | Termék létrehozása | Egyszerűsített lapnézet, amely csak a termékek létrehozásakor leggyakrabban használt mezőket tartalmazza. | Kiadott termékekhez tartozó mentett nézet<br><br>(Alapértelmezés szerint a 10.0.21-es verziónak van beállítva. Kötelező a verziószám szerint 10.0.29.) |
| Megjelent termék részletei | Termék létrehozása | Egyszerűsített lapnézet, amely csak a termékek létrehozásakor leggyakrabban használt mezőket tartalmazza. | Kiadott termékekhez tartozó mentett nézet<br><br>(Alapértelmezés szerint a 10.0.21-es verziónak van beállítva. Kötelező a verziószám szerint 10.0.29.) |
| Megjelent termék részletei | Logisztikai információkezelés | Egyszerűsített lapnézet, amely csak a termékek logisztikai információinak kezelésekor leggyakrabban használt mezőket tartalmazza. | Kiadott termékekhez tartozó mentett nézet<br><br>(Alapértelmezés szerint a 10.0.21-es verziónak van beállítva. Kötelező a verziószám szerint 10.0.29.) |
| Megjelent termék részletei | Beszerzési adatok kezelése | Egyszerűsített lapnézet, amely csak a termékek beszerzési adatainak kezelésekor leggyakrabban használt mezőket tartalmazza. | Kiadott termékekhez tartozó mentett nézet<br><br>(Alapértelmezés szerint a 10.0.21-es verziónak van beállítva. Kötelező a verziószám szerint 10.0.29.) |
| Megjelent termék részletei | Értékesítési adatok kezelése | Egyszerűsített lapnézet, amely csak a termékek értékesítési információinak kezelésekor leggyakrabban használt mezőket tartalmazza. | Kiadott termékekhez tartozó mentett nézet<br><br>(Alapértelmezés szerint a 10.0.21-es verziónak van beállítva. Kötelező a verziószám szerint 10.0.29.) |

## <a name="saved-views-for-the-production-control-module"></a>A Gyártásvezérlési modul mentett nézetei

Az alábbi táblázat leírja a Gyártásvezérlési modulban elérhető mentett nézeteket.

| Oldal | Nézet neve | A leírás megtekintése | Funkció neve |
|---|---|---|---|
| Termelési rendelés darabjegyzékoldala | Egyszerűsített | Ez az egyszerűsített nézet csak a leggyakrabban használt mezőket tartalmazza. Ily módon gyorsabb áttekintést és egyszerűbb munkafolyamatot nyújt. | Mentett nézetek a termelés vezérléséhez<br><br>(Alapértelmezés szerint a 10.0.21-es verziónak van beállítva. Kötelező a verziószám szerint 10.0.29.) |
| Termelési rendelés részleteit tartalmazó oldal | Egyszerűsített | Ez az egyszerűsített nézet csak a leggyakrabban használt mezőket tartalmazza. Ily módon gyorsabb áttekintést és egyszerűbb munkafolyamatot nyújt. | Mentett nézetek a termelés vezérléséhez<br><br>(Alapértelmezés szerint a 10.0.21-es verziónak van beállítva. Kötelező a verziószám szerint 10.0.29.) |
| Termelési rendelés – kitárolásilista-oldal | Egyszerűsített | Ez az egyszerűsített nézet csak a leggyakrabban használt mezőket tartalmazza. Ily módon gyorsabb áttekintést és egyszerűbb munkafolyamatot nyújt. | Mentett nézetek a termelés vezérléséhez<br><br>(Alapértelmezés szerint a 10.0.21-es verziónak van beállítva. Kötelező a verziószám szerint 10.0.29.) |
| Termelési rendelések listaoldala | Egyszerűsített | Ez az egyszerűsített nézet csak a leggyakrabban használt mezőket tartalmazza. Ily módon gyorsabb áttekintést és egyszerűbb munkafolyamatot nyújt. | Mentett nézetek a termelés vezérléséhez<br><br>(Alapértelmezés szerint a 10.0.21-es verziónak van beállítva. Kötelező a verziószám szerint 10.0.29.) |

## <a name="saved-views-for-the-sales-and-marketing-module"></a>Az Értékesítés és marketing modul mentett nézetei

Az alábbi táblázat leírja az Értékesítés és marketing modulban elérhető mentett nézeteket.

| Oldal | Nézet neve | A leírás megtekintése | Funkció neve |
|---|---|---|---|
| Szállítólevél naplója | Napló áttekintése | Ez az egyszerűsített nézet csak azokat a mezőket tartalmazza, amelyek leggyakrabban használatosak a szállítólevél-naplók áttekintéséhez. | Az értékesítés és marketing modul mentett nézetei<br><br>(Alapértelmezés szerint a 10.0.25-ös verzióban. Kötelező a verziószám szerint 10.0.29.) |
| Értékesítési rendelés | Rendelés létrehozása | Ez az egyszerűsített nézet csak azokat a mezőket tartalmazza, amelyek leggyakrabban használatosak az értékesítési rendelések létrehozásához. | Az értékesítés és marketing modul mentett nézetei<br><br>(Alapértelmezés szerint a 10.0.25-ös verzióban. Kötelező a verziószám szerint 10.0.29.) |
| Értékesítési rendelés | Rendelés áttekintése | Ez az egyszerűsített nézet csak azokat a mezőket tartalmazza, amelyek leggyakrabban használatosak az értékesítési rendelések áttekintéséhez. | Az értékesítés és marketing modul mentett nézetei<br><br>(Alapértelmezés szerint a 10.0.25-ös verzióban. Kötelező a verziószám szerint 10.0.29.) |
| Értékesítési ajánlat | Árajánlat létrehozása | Ez az egyszerűsített nézet csak azokat a mezőket tartalmazza, amelyek leggyakrabban használatosak az értékesítési árajánlatok létrehozásához. | Az értékesítés és marketing modul mentett nézetei<br><br>(Alapértelmezés szerint a 10.0.25-ös verzióban. Kötelező a verziószám szerint 10.0.29.) |

## <a name="saved-views-for-the-warehouse-management-module"></a>A Raktárkezelési modul mentett nézetei

Az alábbi táblázat leírja a Raktárkezelési modulban elérhető mentett nézeteket.

| Oldal | Nézet neve | A leírás megtekintése | Funkció neve |
|---|---|---|---|
| Minden rakomány | Bejövő feldolgozása | Ez az egyszerűsített nézet csak azokat a mezőket tartalmazza, amelyek leggyakrabban használatosak a bejövő rakományok feldolgozásához. | Rakományfeldolgozás mentett nézetei<br><br>(Alapértelmezés szerint a 10.0.25-ös verzióban. Kötelező a verziószám szerint 10.0.29.) |
| Minden rakomány | Kimenő feldolgozás | Ez az egyszerűsített nézet csak azokat a mezőket tartalmazza, amelyek leggyakrabban használatosak a kimenő rakományok feldolgozásához. | Rakományfeldolgozás mentett nézetei<br><br>(Alapértelmezés szerint a 10.0.25-ös verzióban. Kötelező a verziószám szerint 10.0.29.) |
| Minden szállítmány | Bejövő feldolgozás | Ez az egyszerűsített nézet csak azokat a mezőket tartalmazza, amelyek leggyakrabban használatosak a bejövő szállítmányok feldolgozásához. | Szállítmányfeldolgozás mentett nézetei<br><br>(Alapértelmezés szerint a 10.0.25-ös verzióban. Kötelező a verziószám szerint 10.0.29.) |
| Minden szállítmány | Kimenő feldolgozás | Ez az egyszerűsített nézet csak azokat a mezőket tartalmazza, amelyek leggyakrabban használatosak a kimenő szállítmányok feldolgozásához. | Szállítmányfeldolgozás mentett nézetei<br><br>(Alapértelmezés szerint a 10.0.25-ös verzióban. Kötelező a verziószám szerint 10.0.29.) |
| Minden hullám | Egyszerűsített | Ez az egyszerűsített nézet csak a leggyakrabban használt mezőket tartalmazza. Ily módon gyorsabb áttekintést és egyszerűbb munkafolyamatot nyújt. | Hullámfeldolgozás mentett nézete<br><br>(Alapértelmezés szerint a 10.0.25-ös verzióban. Kötelező a verziószám szerint 10.0.29.) |
| Rakománytervező munkaterület | Egyszerűsített | Ez az egyszerűsített nézet csak a leggyakrabban használt mezőket tartalmazza. Ily módon gyorsabb áttekintést és egyszerűbb munkafolyamatot nyújt. | A rakománytervezési munkaterület mentett nézetei<br><br>(Alapértelmezés szerint a 10.0.25-ös verzióban. Kötelező a verziószám szerint 10.0.29.) |
| Munka részletes adatai | Egyszerűsített | Ez az egyszerűsített nézet csak a leggyakrabban használt mezőket tartalmazza. Ily módon gyorsabb áttekintést és egyszerűbb munkafolyamatot nyújt. | A munka részleteit tartalmazó oldal mentett nézete<br><br>(Alapértelmezés szerint a 10.0.25-ös verzióban. Kötelező a verziószám szerint 10.0.29.) |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]