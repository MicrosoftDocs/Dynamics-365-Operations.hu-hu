---
title: Jelentésdefiníciók a pénzügyi jelentéstervezőben
description: Ez a cikk a jelentésdefiníciókról tartalmaz információt.
author: ShylaThompson
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: kfend
ms.custom: 59131
ms.assetid: 966a3f1d-c59c-4a84-acd4-5bb7e65144c8
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 52322453328814b06bacefb4829bb10bf9953186
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5755444"
---
# <a name="report-definitions-in-financial-report-designer"></a>Jelentésdefiníciók a pénzügyi jelentéstervezőben

[!include [banner](../includes/banner.md)]

Ez a cikk a jelentésdefiníciókról tartalmaz információt. A jelentésdefiníció egy jelentés-összetevő (vagy építőelem), amely egy sordefiníció, egy oszlopdefiníció és egy opcionális jelentési-fa definíciót használ a jelentés elkészítéséhez. Továbbá a jelentésdefiníció biztosít lehetőségeket és beállításokat, a jelentés testreszabásához. 

A jelentésdefiníció egy jelentés-összetevő (vagy építőelem), amely egy sordefiníció, egy oszlopdefiníció és egy opcionális jelentési-fa definíciót használ a jelentés elkészítéséhez. A jelentésdefiníció emellett a jelentés testre szabását lehetővé tevő lehetőségeket és beállításokat is tartalmaz. A sordefiníciók és oszlopdefiníciók meghatározása után kombinálni kell azokat egy jelentésdefinícióban. Ezen a ponton határozhatja meg a definíciók egyéb aspektusait, például a részletezési szintet és a jelentés dátumát. Ezután mentheti, majd generálhat jelentéseket. A pénzügyi jelentéskészítés a következő részletességi szinteket nyújtja:

- Pénzügyi
- Pénzügy és számla
- Pénzügy, Számla és Tranzakció

Előfordulhat azonban – attól függően, hogyan tárolja a Microsoft Dynamics ERP rendszer az adatokat –, hogy a tranzakciók részletes adatai nem érhetők el a jelentésekben.

## <a name="create-a-report-definition"></a>Jelentésmeghatározás létrehozása
1. A jelentéstervezőben a **Fájl** menüben kattintson az **Új** lehetőségre, majd válassza a **Jelentésdefiníció** lehetőséget.
2. A szükséges információkat a **Jelentés**, **Kimenet és elosztás**, **Fejlécek és láblécek**, valamint a **Beállítások** lapokon határozhatja meg.

## <a name="contents-of-a-report-definition"></a>Jelentésdefiníció tartalma
A következő táblázat bemutatja a jelentésdefinícióban lévő lapokat és az információk használatának módját.

<table>
<thead>
<tr>
<th>Lap</th>
<th>Leírás</th>
</tr>
</thead>
<tbody>
<tr>
<td>Jelentés</td>
<td>Jelentése létrehozás, jelentés beállítása vagy meglévő jelentés módosítása.</td>
</tr>
<tr>
<td>Kimenet és felosztás</td>
<td>A kimenet típusának és a jelentés céljának módosítása.</td>
</tr>
<tr>
<td>Fejlécek és láblécek</td>
<td>A jelentés fejléceinek és lábléceinek meghatározása és formázása. Például hozzáadhat szöveget vagy képeket a fejléchez vagy a lábléchez. A pénzügyi jelentéskészítés a .bmp, .jpg, és .png formátumokat támogatja képek esetén. Az autotext kódok hozzáadásával egyéb információkat is beszúrhat, például a cég nevét, a jelentés nevét vagy az oldalszámot.</td>
</tr>
<tr>
<td>Beállítások</td>
<td>Adja meg a jelentésdefiníció beállításait, például a következőket:
<ul>
<li>Formázás és kerekített összegek</li>
<li>Részletes jelentés formázása</li>
<li>Jelentéskészítési fa formátum</li>
<li>Kivétel jelentés készítése</li>
<li>Pénznem átváltásának meghatározása</li>
<li>Részösszeg és szűrőszámla részletei</li>
</ul>
</td>
</tr>
</tbody>
</table>

## <a name="additional-resources"></a>További erőforrások

[Pénzügyi jelentéskészítés](financial-reporting-intro.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]