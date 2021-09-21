---
title: Az Aktuális készlet listaoldal szűrőablaka nem a vártnak megfelelően működik
description: Az „Aktuális lista” oldal szűrőablakának szűrői nem úgy szűrik az eredményeket, ahogyan azt ön elvárja.
author: sherry-zheng
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: df11b1c1e7de36fa0458cd931d4be7f84a15d143
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476581"
---
# <a name="the-filter-pane-on-the-on-hand-list-page-doesnt-work-as-expected"></a>Az Aktuális készlet listaoldal szűrőablaka nem a vártnak megfelelően működik

## <a name="symptoms"></a>Tünetek

Az **Aktuális lista** oldal szűrőablakának szűrői nem úgy szűrik az eredményeket, ahogyan azt ön elvárja.

## <a name="resolution"></a>Megoldás

Az **Aktuális lista** lap egy részletes aktuális készlettáblából van összeállítva, amely az összes elérhető dimenziót tartalmazza. A lap listája azonban összesítés jellegű. Így előfordulhat, hogy a forrástábla sorait egyesíti a megjelenített dimenzióknak megfelelő értékek összesítésével.

A szűrők ablaktáblán beállított szűrők a forrástáblára vonatkoznak, nem az összesített listára. Ez a viselkedés időnként nem várt eredményt hoz, ahogy [ezek a példák](/dynamics365/supply-chain/inventory/inventory-on-hand-list.md#examples) mutatják.

Azonban a  [rácsban megadott szűrők](/dynamics365/supply-chain/inventory/inventory-on-hand-list.md#grid-filters) *nem* alkalmazandók az összesített listára. Ezek a szűrők egyaránt tartalmazzák a rács felső részén található GyorsSzűrő, valamint az egyes oszlopok fejlécének szűrőjét.
