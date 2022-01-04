---
title: Az Aktuális készlet listaoldal szűrőablaka nem a vártnak megfelelően működik
description: Az "On-hand list" oldal szűrőablakában található szűrők nem szűrik az eredményeket a várt szerint.
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
ms.openlocfilehash: 2b2b233e22378c8710a63dce83d168bfd89eba7f
ms.sourcegitcommit: 008779c530798f563fe216810d34b2d56f2c8d3c
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/14/2021
ms.locfileid: "7920498"
---
# <a name="the-filter-pane-on-the-on-hand-list-page-doesnt-work-as-expected"></a>Az Aktuális készlet listaoldal szűrőablaka nem a vártnak megfelelően működik

## <a name="symptoms"></a>Tünetek

A szűrőablak szűrőablaka nem úgy szűri az eredményeket, ahogyan **az** elvárt.

## <a name="resolution"></a>Megoldás

Az **Aktuális lista** lap egy részletes aktuális készlettáblából van összeállítva, amely az összes elérhető dimenziót tartalmazza. A lap listája azonban összesítés jellegű. Így előfordulhat, hogy a forrástábla sorait egyesíti a megjelenített dimenzióknak megfelelő értékek összesítésével.

A szűrőablakban beállított szűrők a forrástáblára vonatkoznak, nem az összesített listára. Ez a viselkedés időnként nem várt eredményt hoz, ahogy [ezek a példák](/dynamics365/supply-chain/inventory/inventory-on-hand-list.md#examples) mutatják.

A rácsban megadott [szűrők azonban](/dynamics365/supply-chain/inventory/inventory-on-hand-list.md#grid-filters) *vonatkoznak* az összesített listára. Ezek a szűrők egyaránt tartalmazzák a rács felső részén található GyorsSzűrő, valamint az egyes oszlopok fejlécének szűrőjét.
