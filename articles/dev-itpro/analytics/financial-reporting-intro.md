---
title: Pénzügyi jelentéskészítés
description: A Pénzügyi jelentéskészítés a Finance and Operations rendszerben lehetővé teszi üzleti és pénzügyi szakembereknek pénzügyi kimutatások létrehozását, karbantartását, telepítését és megtekintését. A hagyományos jelentési korlátokon túlmenően különböző típusú jelentések hatékony tervezésében nyújt segítséget.
author: aprilolson
manager: AnnBe
ms.date: 12/01/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: FinanicalReportingSetup
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 68813
ms.assetid: fe8b27e7-a40a-4689-ac6a-7f7401c387f5
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: ae2087cf142fc2670bda3c542b336f12978178a6
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2019
ms.locfileid: "323778"
---
# <a name="financial-reporting"></a>Pénzügyi jelentéskészítés

[!include [banner](../includes/banner.md)]

A Pénzügyi jelentéskészítés a Finance and Operations rendszerben lehetővé teszi üzleti és pénzügyi szakembereknek pénzügyi kimutatások létrehozását, karbantartását, telepítését és megtekintését. A hagyományos jelentési korlátokon túlmenően különböző típusú jelentések hatékony tervezésében nyújt segítséget.

Pénzügyi jelentéskészítés tartalmazza a dimenzió támogatást. Ezért a számlaszegmensek vagy dimenziók azonnal elérhetők. További eszközök vagy konfigurációs lépések nem szükségesek.

## <a name="financial-reporting-setup"></a>Pénzügyi jelentéskészítés beállítása
A **Pénzügyi jelentéskészítés beállítása** lapja tartalmazza a rendszer összes pénzügyi dimenziójának listáját. **Főkönyv** \> **Főkönyv beállításai** \> **Pénzügyi jelentéskészítés beállítása**.

A **Pénzügyi jelentéskészítés beállítása** lap két részből áll, amelyek meghatározzák a pénzügyi jelentésekben jelentésre kerülő adatokat:

- **Dimenziók lap** – Mivel a különböző vállalatok különböző dimenziókat és számlastruktúrákat használnak, nem lehet meghatározni, hogy a felhasználók milyen sorrendben akarják megtekinteni az összes pénzügyi dimenziót a jelentéseken. Ezen a lapon beállítható, hogy a pénzügyi dimenziók milyen sorrendben jelenjenek meg, amikor jelentést készít vagy tekint meg a pénzügyi jelentésekben.
- **Attribútumok lap** – Itt választható ki, hogy **Szállítók** vagy a **Vevők** legyen használva attribútumként a szűréshez és a jelentéstervezéséhez. A jelentéskészítés szállítók és vevők szerint csak akkor hasznos, ha nem ad meg több szállítót vagy vevőt egy bizonylaton a tranzakciók feladásakor. A Szállító és/vagy a Vevő kiválasztása növeli az integrációs időt.

## <a name="financial-reporting-components"></a>A pénzügyi jelentés összetevői
A pénzügyi jelentéskészítés következő elemeivel a jelentések létrehozása, megtekintése és ütemezése rendkívül egyszerűvé válik.

| Összetevő        | Függvények | További információk |
|------------------|-----------|------------------------|
| Jelentéstervező  | A jelentések építőelemeit hozhatja létre ezzel, amelyekből később jelentést határozhat meg és hozhat létre. A jelentésvarázsló a kevésbé tapasztalt felhasználókat kalauzolja végig a tervezési folyamaton. A haladó felhasználók létrehozhatnak új jelentés-építőelemeket vagy kedvükre módosíthatják a meglévő építőelemeket. | |
| Jelentésütemezések | Ütemezzen egyetlen jelentést vagy jelentéscsoportot úgy, hogy az rendszeressé váljon. | [Pénzügyi jelentés létrehozása](generate-financial-report.md) |

## <a name="features"></a>Jellemzők
<table>
<thead>
<tr>
<th>Szolgáltatás</th>
<th>Leírás</th>
</tr>
</thead>
<tbody>
<tr>
<td>Rugalmas jelentéstervezés</td>
<td>A jelentéstervező jelentés tervezésekor az alábbi jelentési beállításokat nyújtja:
<ul>
<li>Dimenziókombinációk mentése, azok későbbi használata több jelentéshez.</li>
<li>Szabályozhatja a dimenzióleírások formázását és megjelenítését.</li>
<li>Azonosíthatja a számlákat és dimenziókat, amelyek kimaradtak a jelentések építőelemeiből.</li>
<li>Formázhatja a fejléceket a gördülő előrejelzésekhez.</li>
</ul>
</td>
</tr>
<tr>
<td>Pénzügyi jelentési együttműködés</td>
<td>Az alábbi funkciók segítségével szabályozhatja a jelentések létrehozását és felosztását:
<ul>
<li>Jelentések ütemezése a napi, heti, havi vagy éves létrehozás beállításához.</li>
<li>Exportálás csak olvasható XPS formátumba, amely nagyobb dokumentumbiztonságot nyújt digitális aláírással.</li>
<li>Exportálja egy Microsoft Excel-munkalapra.</li>
<li>A jelentések megosztásához létrehozhat e-maileket, amelyek a jelentésre mutató hivatkozást tartalmaznak.</li>
</ul>
</td>
</tr>
<tr>
<td>Jelentések interaktív megtekintése</td>
<td>Az interaktív funkciók segítségével az alábbi műveleteket végezeti el:
<ul>
<li>Módosítsa a jelentés dátumát a jelentésben, melyet éppen megtekint.</li>
<li>Módosítsa a pénznemet a jelentésben, melyet éppen megtekint.</li>
<li>A jelentés összefoglaló vagy részletes nézetben való megtekintése.</li>
<li>Dimenzió-szűrés hozzáadása jelentés tartalmának egy adott dimenzióra vagy a dimenziók kombinációjára való korlátozására.</li>
<li>Attribútum-szűrés hozzáadása jelentés tartalmának egy adott attribútumra vagy a attribútumok kombinációjára való korlátozására.</li>
</ul>
</td>
</tr>
</tbody>
</table>

## <a name="additional-resources"></a>További erőforrások
[Pénzügyi jelentés létrehozása](generate-financial-report.md)
