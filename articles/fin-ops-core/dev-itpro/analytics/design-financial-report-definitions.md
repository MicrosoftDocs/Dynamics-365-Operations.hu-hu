---
title: Jelentésdefiníciók a pénzügyi jelentéstervezőben
description: Ez a cikk a jelentésdefiníciókról tartalmaz információt.
author: aprilolson
ms.date: 11/22/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.custom: 59131
ms.assetid: 966a3f1d-c59c-4a84-acd4-5bb7e65144c8
ms.search.form: FinancialReports
ms.openlocfilehash: 2ffef335c694af56486ccd7738818c4edda49b9e
ms.sourcegitcommit: d27fef61593c6d1e9e26d5c9fad21411bc52fabc
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/23/2022
ms.locfileid: "9802532"
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
1. A Jelentéstervező fájl menüjében **kattintson** az Új **gombra**, majd válassza a **Jelentésdefiníciót**.
2. Adja meg a megfelelő adatokat a **Jelentés,** Kimenet **és** elosztás, **Fejlécek és láblécek**, Valamint **Beállítások lapon** .

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
<td>Kimenet és elosztás</td>
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
