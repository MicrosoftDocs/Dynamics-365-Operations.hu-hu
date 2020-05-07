---
title: Követelések és beszedések kezelése Power BI tartalom
description: Ez a témakör a Követelések és beszedések kezelése Power BI-tartalom modul tartalmát ismerteti. Leírja, hogy hogyan kell hozzáférni a Power BI-jelentésekhez, és információkat nyújt a tartalomcsomag összeállításához korábban használt entitásokkal és adatmodellekkel kapcsolatban.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 04/21/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustomerCollectionManagerWorkspace
audience: Application User, IT Pro
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: 5c4a2289d7fa0f062735c93cf26cba9ac29ab94e
ms.sourcegitcommit: e9fadf6f6dafdcefaff8e23eaa3c85f53437db3f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/22/2020
ms.locfileid: "3278874"
---
# <a name="credit-and-collections-management-power-bi-content"></a>Követelések és beszedések kezelése Power BI tartalom

[!include [banner](../includes/banner.md)]

Ez a témakör a **Követelések és beszedések kezelése** Microsoft Power BI-tartalom modul tartalmát ismerteti. Leírja, hogy hogyan kell hozzáférni a Power BI-jelentésekhez, és információkat nyújt a tartalomcsomag összeállításához előzőleg használt entitásokkal és adatmodellekkel kapcsolatban.

## <a name="overview"></a>Áttekintés

A **Követelések és beszedések kezelése** Power BI-tartalom a követelésekért és beszedésekért felelős vezetők és a beszedési ügyintézők számára készült. Kulcsfontosságú hitellel és beszedéssel kapcsolatos adatokat kínál, például a kintlevőség-elmaradási napok számát, a késedelmes egyenlegeket, a hitelkockázatot és azokat az ügyfeleket, akik túllépték hitelkeretüket. Tranzakciós adatokat használ, és összesített nézeteket nyújt a hitelekről és a beszedésekről minden vállalatnál. Emellett vállalat, ügyfélcsoport és ügyfél szerinti lebontást kínál.

Ez a Power BI-tartalom 10 jelentésoldalt tartalmaz:

- Két áttekintő oldal (egy oldal a hitelek áttekintésére és egy a beszedések áttekintésére)
- Nyolc részletező oldal, amelyek részleteket nyújtanak azokról a hitelekkel és beszedésekkel kapcsolatos mutatókról, amelyek különbüző dimenziók alapján jelennek meg.

Minden összeg a rendszer pénznemében van megadva. Beállíthatja az rendszer alapértelmezett pénznemét a **Rendszerparaméterek** oldalon.

Alapértelmezés szerint a jelenlegi vállalat követeléseinek és beszedéseinek adatait jeleníti meg. Ha az összes vállalatra vonatkozó adatot látni szeretné, rendelje a **CustCollectionsBICrossCompany** kötelességet a szerepkörhöz.

## <a name="setup-needed-to-view-power-bi-content"></a>A Power BI-tartalom megtekintéséhez beállítás szükséges

A következő beállításokat meg kell adni, hogy az adatok megjelenjenek a **Vevői követelések és beszedések** között, a Power BI vizuális elemei között.

1. Nyissa meg a **Rendszeradminisztráció > Beállítás > Rendszerparaméterek** pontot a **Rendszerpénznem** és a **Rendszerváltási árfolyam** beállításához.
2. Ugrás a **Főkönyv > Beállítás > Főkönyv** részre, és a **Könyvelési pénznem** és az **Árfolyamtípus** beállítása.
3. Adja meg az árfolyamokat a tranzakció pénznemei és a könyvelési pénznem, a könyvelési pénznem és a rendszer pénzneme között. Lépjen ide: **Főkönyv > Pénznemek > Pénznemek árfolyamtípusai**.
4. Lépjen a **Rendszerfelügyelet > Beállítás > Entitástár** részre a **CustCollectionsBIMeasurementsV2** összesítő mérték frissítéséhez.

## <a name="accessing-the-power-bi-content"></a>A Power BI tartalom elérése

A **Követelések és beszedések kezelése** Power BI-tartalom a **Vevői követelések és beszedések** munkaterületen jelenik meg.

## <a name="reports-that-are-included-in-the-power-bi-content"></a>Jelentések, amelyek a Power BI-tartalomban szerepelnek

A **CustCollectionsBICrossCompany** Power BI-tartalom jelentést is tartalmaz, amelyben a mutatók egy készlete található. Ezek a metrikák mozaikok, táblázatok és diagramok formájában jelennek meg. Az alábbi táblázatban a **CustCollectionsBICrossCompany** Power BI-tartalom megjelenítési formáinak áttekintése található.

| Jelentéslap                 | Megjelenítés |
|-----------------------------|---------------|
| Fizetési felszólítások áttekintése        | <ul><li>Késedelmes vevők</li><li>Hitelkeretet túllépő vevők</li><li>DSO 30 nap</li><li>Nyitott esetek</li><li>Ügy lezárásáig hátralévő napok átlaga</li><li>Nyitott tevékenységek</li><li>Tevékenységek lezárásáig hátralévő napok átlaga</li><li>Kamatlevelek megnyitása</li><li>Fizetési felszólítások megnyitása</li><li>Vevőfelfüggesztés</li><li>Értékesítési felfüggesztés</li><li>Korosított egyenlegek</li><li>Felszólítási állapot - összegek</li><li>Felszólító kódok összegei</li><li>Leírás indok szerint</li><li>Esedékes egyenleg régiónként</li><li>Várható kifizetések</li></ul> |
| Jóváírás áttekintése             | <ul><li>Késedelmes vevők</li><li>Hitelkeret és esedékes egyenlege</li><li>Hitelkeretet túllépő vevők rácsa</li><li>Hitelkeretet túllépő vevők vállalatonként</li><li>Felhasznált hitel és összesített hitelkeret</li><li>Hitelkeret és felhasznált hitel régiónként</li><li>Vevők hitelminősítés szerint</li></ul> |
| Hitelkeret                | <ul><li>Hitelkeret</li><li>Hitelkeret részletei</li><li>Hitelkeret vevőnként</li><li>Hitelkeret vevőcsoportonként</li><li>Hitelkeret hitelminősítés szerint vállalatonként</li><li>Hitelkeret és felhasznált hitel régiónként</li></ul> |
| Hitelkeretet túllépő vevők | <ul><li>Hitelkeretet túllépő vevők</li><li>Hitelkeretet túllépő vevők részletei</li><li>Hitelkeretet túllépő vevők vállalatonként</li><li>Hitelkeretet túllépő vevők vevőcsoport szerint</li><li>Hitelkeretet túllépő vevők régió szerint</li></ul> |
| Késedelmes vevők          | <ul><li>Késedelmes vevők</li><li>Lejárt határidejű vevők részletei</li><li>Késedelmes ügyfelek vállalatonként</li><li>Késedelmes vevők vevőcsoport szerint</li><li>Késedelmes vevők régió szerint</li></ul> |
| Korosított egyenlegek               | <ul><li>Korosított egyenlegek</li><li>Korosított egyenlegek részletei</li><li>Korosított egyenlegek vállalat szerint</li><li>Korosított egyenlegek vevőcsoportok szerint</li></ul> |
| Várható kifizetések           | <ul><li>Várható kifizetések</li><li>Várható kifizetések részletei</li><li>Várt kifizetések vállalatonként</li><li>Várt kifizetések vevőcsoport szerint</li><li>Várt kifizetések régiónként</li></ul> |
| Leírások                  | <ul><li>Leírások régió szerint</li><li>Leírások részletei</li><li>Leírások fő számla szerint</li><li>Leírások vállalatonként</li><li>Leírások vevőcsoportonként</li><li>Leírások régió szerint</li></ul> |
| Beszedések állapota          | <ul><li>Vitatott</li><li>Nem tartotta a fizetési ígéretet</li><li>Fizetési ígéret</li><li>Beszedések állapotának részletei</li><li>Felszólítási állapot - összegek</li><li>Nyitott esetek</li><li>Nyitott tevékenységek</li></ul> |
| Fizetési felszólítások         | <ul><li>Felszólító kód - összegek</li><li>Felszólító kód összegének részletei</li><li>Fizetési felszólító levelek összege vállalatok szerint</li><li>Fizetési felszólítások összege vevőcsoportok szerint</li><li>Fizetési felszólító levelek összege régió szerint</li></ul> |

Az összes ilyen jelentésben szereplő diagramot és a lapot ki lehet szűrni és rögzíteni lehet az irányítópulton. A szűréssel és a Power BI-n történő rögzítéssel kapcsolatos információkért lásd: [Irányítópult létrehozása és konfigurálása](https://powerbi.microsoft.com/guided-learning/powerbi-learning-4-2-create-configure-dashboards/). Használhatja a Mögöttes adatok exportálása funkciót is azoknak a mögöttes adatoknak az exportálásához, amelyeknek összegzése ábrán látható.
