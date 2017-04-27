---
title: "Pénzügyi jelentéskészítés a Dynamics 365 for Operations rendszerben"
description: "A Pénzügyi jelentéskészítés a Microsoft Dynamics 365 for Operations rendszerben lehetővé teszi üzleti és pénzügyi szakembereknek pénzügyi kimutatások létrehozását, karbantartását, telepítését és megtekintését. A hagyományos jelentési korlátokon túlmenően különböző típusú jelentések hatékony tervezésében nyújt segítséget."
author: RobinARH
manager: AnnBe
ms.date: 2016-03-18 15 - 31 - 29
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Management Reporter
ms.custom: 68813
ms.assetid: fe8b27e7-a40a-4689-ac6a-7f7401c387f5
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 
ms.dyn365.ops.version: 
translationtype: Human Translation
ms.sourcegitcommit: f707d45290682e79ee439ba0d504852429defa90
ms.openlocfilehash: 519b3d3fb53b20d0014c97bcb1b9b21802a376d6
ms.lasthandoff: 03/30/2017


---

# <a name="financial-reporting-for-dynamics-365-for-operations"></a>Pénzügyi jelentéskészítés a Dynamics 365 for Operations rendszerben

A Pénzügyi jelentéskészítés a Microsoft Dynamics 365 for Operations rendszerben lehetővé teszi üzleti és pénzügyi szakembereknek pénzügyi kimutatások létrehozását, karbantartását, telepítését és megtekintését. A hagyományos jelentési korlátokon túlmenően különböző típusú jelentések hatékony tervezésében nyújt segítséget.

Pénzügyi jelentéskészítés tartalmazza a dimenzió támogatást. Ezért a számlaszegmensek vagy dimenziók azonnal elérhetők. További eszközök vagy konfigurációs lépések nem szükségesek.

## <a name="financial-reporting-components"></a>A pénzügyi jelentés összetevői
A pénzügyi jelentéskészítés következő elemeivel a jelentések létrehozása, megtekintése és ütemezése rendkívül egyszerűvé válik.

| Összetevő        | Függvények                                                                                                                                                                                                                                                                           | További információk                                                                          |
|------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------|
| Jelentéstervező  | A jelentések építőelemeit hozhatja létre ezzel, amelyekből később jelentést határozhat meg és hozhat létre. A jelentésvarázsló a kevésbé tapasztalt felhasználókat kalauzolja végig a tervezési folyamaton. A haladó felhasználók létrehozhatnak új jelentés-építőelemeket vagy kedvükre módosíthatják a meglévő építőelemeket. |                                                                                                 |
| Webes megjelenítő       | Jelentések megtekintése a böngészőben. A Web Viewer nem igényli pénzügyi jelentéskészítő kiszolgáló-összetevők telepítését.                                                                                                                                                        | [Webes megjelenítő](financial-reporter-designer-web-client.md)            |
| Jelentésütemezések | Ütemezzen egyetlen jelentést vagy jelentéscsoportot úgy, hogy az rendszeressé váljon.                                                                                                                                                                                          | [A jelentés létrehozása](/dynamics365/operations/financials/general-ledger/generate-financial-report) |

## <a name="features"></a>Jellemzők
<table>
<thead>
<tr class="header">
<th>Szolgáltatás</th>
<th>Leírás</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Rugalmas jelentéstervezés</td>
<td>A jelentéstervező jelentés tervezésekor az alábbi jelentési beállításokat nyújtja:
<ul>
<li>Dimenziókombinációk mentése, azok későbbi használata több jelentéshez.</li>
<li>Szabályozhatja a dimenzióleírások formázását és megjelenítését.</li>
<li>Azonosíthatja a számlákat és dimenziókat, amelyek kimaradtak a jelentések építőelemeiből.</li>
<li>Formázhatja a fejléceket a gördülő előrejelzésekhez.</li>
</ul></td>
</tr>
<tr class="even">
<td>Pénzügyi jelentési együttműködés</td>
<td>Az alábbi funkciók segítségével szabályozhatja a jelentések létrehozását és felosztását:
<ul>
<li>Jelentések ütemezése a napi, heti, havi vagy éves létrehozás beállításához.</li>
<li>Exportálás csak olvasható XPS formátumba, amely nagyobb dokumentumbiztonságot nyújt digitális aláírással.</li>
<li>Exportálás Microsoft Excel-munkalapra.</li>
<li>A jelentések megosztásához létrehozhat e-maileket, amelyek a jelentésre mutató hivatkozást tartalmaznak.</li>
</ul></td>
</tr>
<tr class="odd">
<td>Jelentések interaktív megtekintése</td>
<td>Az interaktív funkciók segítségével az alábbi műveleteket végezeti el:
<ul>
<li>Módosítsa a jelentés dátumát a jelentésben, melyet éppen megtekint.</li>
<li>Módosítsa a pénznemet a jelentésben, melyet éppen megtekint.</li>
<li>A jelentés összefoglaló vagy részletes nézetben való megtekintése.</li>
<li>Dimenzió-szűrés hozzáadása jelentés tartalmának egy adott dimenzióra vagy a dimenziók kombinációjára való korlátozására.</li>
<li>Attribútum-szűrés hozzáadása jelentés tartalmának egy adott attribútumra vagy a attribútumok kombinációjára való korlátozására.</li>
</ul>
További információkért lást az „Interaktív összetevők és navigációs funkciók” szakaszt az <a href="https://technet.microsoft.com/en-us/library/dn469079.aspx">Asztali megjelenítő felületen</a> .</td>
</tr>
</tbody>
</table>

#<a name="see-also"></a>Lásd még

[Pénzügyi jelentés készítése]((dynamics365\operations\financials\general-ledger\generate-financial-report)


