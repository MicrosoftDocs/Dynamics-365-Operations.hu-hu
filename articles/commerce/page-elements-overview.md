---
title: Oldal modell szószedete
description: Ez a témakör a Microsoft Dynamics 365 Commerce webhelyének oldalain használt különböző elemeket ismerteti.
author: phinneyridge
manager: annbe
ms.date: 10/09/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: niholman
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: f676503691049938fb8b6b7bfcac159e2f61bc6f
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4972682"
---
# <a name="page-model-glossary"></a>Oldal modellszószedete


[!include [banner](includes/banner.md)]

Ez a témakör a Microsoft Dynamics 365 Commerce webhelyének oldalain használt különböző elemeket ismerteti.

## <a name="page-element-definitions"></a>Oldalelem definíciói

A következő táblázat bemutatja, hogy milyen kifejezéseket érdemes ismernie, amikor módosítja a webhely megjelenését, érzetét és tartalmát. A részletesebb magyarázatokért és eljárásokért kövesse a hivatkozásokat.

| Időszak | Leírás és megjegyzések |
|------|-----------------------|
| [Modul](work-with-modules.md) | <p>**Definíció:** A modulok olyan építőelemek, amelyek szerkeszthetők, és a weblapok vázát alkotják. Ilyen például a fejléc, a főkép és a forgótár modul.</p><p>**Ha be van jelölve**, A telepített modulok a webhelyszerkesztő munkafolyamat különböző szakaszaiban választhatók ki és konfigurálhatók, például a sablon, az elrendezés, az oldal és a töredék szerkesztési fázisokban.</p><p>**A szerkesztés helye:** Az egyéni modulok kódban vannak létrehozva szoftverfejlesztő készlet (SDK) használatával. Ezután fel leszenek töltve a webhelyére, ahol elérhetővé válnak kiválasztáshoz.</p> |
| Modultulajdonság | <p>**Definíció:** A Modultulajdonságok a modul által meghatározott specifikus beállítások. Az e-Commerce szerkesztőeszközeiben szerkeszthetők. A modul tulajdonságai használatosak például egy szalagcím modul fejlécének és hátterének beállításához.</p><p>**Hol vannak konfigurálva** A modul tulajdonságai a tulajdonság ablaktáblán választhatók ki és szerkeszthetők a sablonok, elrendezések, lapok, töredékek és a alkalmazás-beállítások szerkesztői környezetében (Szerkesztő).</p> |
| [Sablon](templates-layouts-overview.md) | <p>**Definíció:** A sablonok határozzák meg, hogy mely modul-kombinációkat és beállításokat kell használni az oldalkategóriákhoz (például marketinges lapok, kategória lapok és a termék oldalak).</p><p>**Hol lehet kiválasztani** A sablonok az oldal vagy az elrendezés létrehozása munkafolyamatok során is kiválaszthatók.</p><p>**Hol lehet szerkeszteni** A sablonok szerkesztése a sablonszerkesztőben történik. Nem szükséges kód egy elem létrehozásához vagy módosításához.</p> |
| [Elrendezés](templates-layouts-overview.md) | <p>**Definíció:** Az elrendezések határozzák meg a modulok végső kijelölését és elrendezését a szülő sablon beállításkészletéből. Egy elrendezés konfigurálható egyetlen oldalhoz (*egyéni elrendezés*), vagy több oldallal is megoszthatók (*előre beállított elrendezés*).</p><p>**Hol lehet kiválasztani:** Az elrendezések az új lapok létrehozása során is kiválaszthatók, illetve, amikor egy meglévő laphoz egy másik elrendezés szükséges.</p><p>**Hol lehet szerkeszteni** Az elrendezések szerkesztése az elrendezésszerkesztőben történik. Nem szükséges kód egy elem létrehozásához vagy módosításához.</p> |
| [Lappéldány](modify-existing-page.md) | <p>**Definíció:** A lappéldányok határozzák meg, hogy az egyes oldalakon milyen végleges, oldalspecifikus lokalizált tartalom van. Ez a tartalom a modultulajdonságok értékeiből származik.</p><p>**Hol lehet kiválasztani:** A lapok az URL-címek hozzárendelése során választhatók ki.</p><p>**Hol lehet szerkeszteni** Az oldalak szerkesztése az oldalszerkesztőben történik. Nem szükséges kód egy elem létrehozásához vagy módosításához.</p> |
| [Téma](select-site-theme.md) | <p>**Definíció:** A témák definiálják az egymásra épülő stíluslapokat (CSS), és meghatározzák a lapon megjelenített modulok megjelenését és hangulatát.</p><p>**Hol lehet kiválasztani:** Miután a webhelyre feltöltött egy témát a Microsoft Dynamics Lifecycle Services (LCS) használatával, az a lap tároló moduljának új tulajdonságaként választható ki.</p><p>**Hol lehet szerkeszteni:** A témák jelenleg az SDK segítségével hozhatók létre és szerkeszthetők. Az LCS használatával lehet azokat feltölteni a weboldalára.</p> |
| [Töredék](work-with-fragments.md) | <p>**Definíció:** A töredékek olyan teljes mértékben konfigurált modulok, amelyek honosított tartalmakat tartalmaznak, és központilag frissíthetők több oldalon. Például egy fejléc modulból létrehozott töredék használható minden sablonban és a webhely összes lapján, és központilag frissíthető egy helyen.</p><p>**Hol lehet kiválasztani** A töredékek mindenhol kiválaszthatók, ahol a modulok választhatók ki. Ezek a modulok helyettesítésére használhatók a hatékonyság növelése érdekében, az újrahasználható és központilag szerkeszthetők.</p><p>**Hol lehet szerkeszteni** Az töredékek szerkesztése az töredékszerkesztőben történik. Nem szükséges kód egy elem létrehozásához vagy módosításához.</p> |
| [URL-cím](create-page-URL.md) | <p>**Definíció:** Az URL-címek (URL-ek) weboldalakra vagy más URL-címekre mutató címek.</p><p>**Hol lehet kiválasztani:** Az URL-címek ott válaszhatók ki, ahol oldalak közötti hivatkozásokra van szükség.</p><p>**Hol lehet szerkeszteni** Az URL-címek szerkesztése az URL-cím-szerkesztőben történik. Nem szükséges kód egy elem létrehozásához vagy módosításához.</p> |
| Eszköz | <p>**Definíció:** Az eszközök olyan bináris fájlok, amelyek kiterjesztése: .jpg, .docx, .pdf vagy .mpg.</p><p>**Hol lehet kiválasztani** Az eszközöket modultulajdonságként lehet kiválasztani azokhoz a modulokhoz, amelyekhez szükségesek.</p><p>**Hol lehet szerkeszteni:** Az eszközök feltöltése és a kapcsolódó metaadatok szerkesztése az eszközkezelőben lehetséges.</p> |

## <a name="additional-resources"></a>További erőforrások

[A tartalom hozzáadásának módjai](add-manage-content.md)

[Állapotok és életciklus-dokumentálás](document-states-overview.md)

[A közzétételi csoportokkal végzett munka](publish-groups.md)

[Csatornaközi megosztás engedélyezése és használata](cross-channel-sharing.md)

[Modulok használata](work-with-modules.md)

[Töredékek használata](work-with-fragments.md)

[Sablonok és elrendezések áttekintése](templates-layouts-overview.md)

[Webhely-navigáció testreszabása](customize-site-navigation.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]