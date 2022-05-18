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
ms.openlocfilehash: 3857ce3720430c6f512d5abc4c9c4d390a0c3377
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/04/2022
ms.locfileid: "8686683"
---
# <a name="the-filter-pane-on-the-on-hand-list-page-doesnt-work-as-expected"></a>Az Aktuális készlet listaoldal szűrőablaka nem a vártnak megfelelően működik

## <a name="symptoms"></a>Tünetek

A szűrőablak szűrőablaka nem **úgy** szűri az eredményeket, ahogyan az elvárt.

## <a name="resolution"></a>Megoldás

Az **Aktuális lista** lap egy részletes aktuális készlettáblából van összeállítva, amely az összes elérhető dimenziót tartalmazza. A lap listája azonban összesítés jellegű. Így előfordulhat, hogy a forrástábla sorait egyesíti a megjelenített dimenzióknak megfelelő értékek összesítésével.

A szűrőablakban beállított szűrők a forrástáblára vonatkoznak, nem az összesített listára. Ez a viselkedés időnként nem várt eredményt hoz, ahogy [ezek a példák](/dynamics365/supply-chain/inventory/inventory-on-hand-list#examples) mutatják.

A rácsban megadott [szűrők azonban](/dynamics365/supply-chain/inventory/inventory-on-hand-list#grid-filters) *vonatkoznak* az összesített listára. Ezek a szűrők egyaránt tartalmazzák a rács felső részén található GyorsSzűrő, valamint az egyes oszlopok fejlécének szűrőjét.
