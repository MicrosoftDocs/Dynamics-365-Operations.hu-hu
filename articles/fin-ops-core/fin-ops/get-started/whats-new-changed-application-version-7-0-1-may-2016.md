---
title: Mi az új vagy mi változott a Dynamics AX alkalmazásban verziószám 7.0.1 (2016. május)
description: Ez a cikk a Microsoft Dynamics AX 7.0.1 alkalmazásverziójában található új vagy módosított szolgáltatásokat írja le. Ez a verzió 2016 Májusában jelent meg és a build száma 7.0.1265.23014.
author: sericks007
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ROBOTS: NOINDEX, NOFOLLOW
audience: Application User, Developer, IT Pro
ms.reviewer: josaw
ms.search.scope: Operations
ms.custom: 91213
ms.assetid: f0bbc78f-87fc-40e9-b46a-6655893f69be
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 715e0f8d08c6abbde35eb917cddc4ecf4b7b67ed
ms.sourcegitcommit: 57bc7e17682e2edb5e1766496b7a22f4621819dd
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/18/2019
ms.locfileid: "2811456"
---
# <a name="whats-new-or-changed-in-dynamics-ax-application-version-701-may-2016"></a>Mi az új vagy mi változott a Dynamics AX alkalmazásban verziószám 7.0.1 (2016. május)

[!include [banner](../includes/banner.md)]

Ez a cikk a Microsoft Dynamics AX 7.0.1 alkalmazásverziójában található új vagy módosított szolgáltatásokat írja le. Ez a verzió 2016 Májusában jelent meg és a build száma 7.0.1265.23014.

## <a name="electronic-reporting-er"></a>Elektronikus jelentés (EJ)

| Mit lehet tenni? | Miért fontos ez? |
|------------------|------------------------|
| Futási idő párbeszédpanel konfigurálása Elektronikus jelentések (EJ) tervezéséhez, így a felhasználók kijelölhetik az általuk választott pénzügyi dimenziókat. | A párbeszédpanelen egy EJ jelentés futtatása közben a felhasználók több pénzügyi dimenziót választhatnak ki. A kijelölt pénzügyi dimenziók részletei a létrehozott elektronikus dokumentumban jelennek meg. |
| Állítson be hozzáférést több pénzügyi dimenzióhoz az EJ jelentés létrehozása során egy egyszerű hozzárendelés segítségével a kívánt adatforráshoz. | Ugyanaz az ER-jelentéskonfiguráció használható elektronikus dokumentumok létrehozására, melyek tranzakciós adatokat és pénzügyi dimenziók részleteit a felhasználó vagy a jogi személy által választott dimenziók számától függetlenül tartalmazzák. |
| Konfiguráljon EJ jelentést adatok beviteléhez az elektronikus dokumentum dinamikusan generált oszlopaiba, amely OPENXML munkalap formátumban jön létre. | Az EJ-jelentés adatokat írhat be az oszlopok vízszintes replikálásán keresztül létrejött OPENXML munkalapokba. Ezért ugyanaz az EJ-jelentés konfiguráció újrahasználható eltérő számú dinamikusan generált oszloppal rendelkező elektronikus dokumentumok létrehozásához. |
| EJ célok beállítása úgy, hogy a kimeneti formátum eredménye meghatározott rendeltetési helyre irányuljon: fájl, e-mail vagy archívum (Microsoft SharePoint-mappa vagy Microsoft Azure tárolás). | Korábban, egy EJ-konfiguráció futtatásakor egy üzenetpanel jelent meg, amely egy fájl mentéséhez vagy megnyitásához felhasználó beavatkozást kért. Most külön elő-konfigurálhatja az egyes formátum-konfiguráció célját és annak kimeneti összetevőit (egy mappa vagy egy fájl). Megfelelő hozzáférési jogokkal rendelkező felhasználók módosíthatják a célbeállításokat futásidőben is. |

## <a name="pos--microsoft-dynamics-ax-retail"></a>Pénztár – Microsoft Dynamics AX Retail

| Mit lehet tenni? | Miért fontos ez? |
|------------------|------------------------|
| Használja a Google Chrome böngészőt. | Kiskereskedők mostantól a Felhőalapú pénztárt elindíthatják Chrome böngészőből, és a Felhőalapú pénztár minden, Microsoft Edge és az Internet Explorer böngészőkben elérhető szolgáltatását megtapasztalhatják. |

## <a name="financial-reporting"></a>Pénzügyi jelentéskészítés

| Mit lehet tenni? | Miért fontos ez? |
|------------------|------------------------|
| A pénzügyi jelentési adatpiac újraépítése. | Amikor Dynamics AX adatbázisokat környezetek között helyezi át, vagy egyéb invazív módosítások hajt végre a Dynamics AX környezetében, a pénzügyi jelentéskészítő adatbázis újraépítése szükséges lesz valószínűleg. A Windows PowerShell-parancsfájl most lehetővé teszi az adatbázis újraépítését. |
| Már nem választhat érvénytelen jelentéstervező lehetőségek közül. | Számos Management reporter forgalmazott verziójában használt jelentéstervező a Dynamics AX ezen verziójára nem vonatkozik. Ezek a beállítások a pénzügyi jelentés tervező, a kimeneti és a csatolás voltak kapcsolatosak. Ezek a beállítások felhasználói hibák elkerülése érdekében a pénzügyi jelentés tervező el lett távolítva. |

## <a name="financial-management"></a>Pénzgazdálkodás

| Mit lehet tenni? | Miért fontos ez? |
|------------------|------------------------|
| Bérszámfejtési bankszámlához tartozó ellenőrzött fizetési fájl generálása | Banki csekk csalás megelőzése érdekében a fizetési ellenőrző fájlok hozhatók létre. |

## <a name="warehouse-and-production"></a>Raktár és termelés

<table>
<thead>
<tr>
<th>Mit lehet tenni?</th>
<th>Miért fontos ez?</th>
</tr>
</thead>
<tbody>
<tr>
<td>Határozzon meg raktári munka-irányelvet az egyes helyeken létrehozott termékek szabályozására.</td>
<td>A raktárkezelési folyamatok nem mindig tartalmazzák a munkát. Az új raktári munka irányelveinek használatával megakadályozhatja a nyersanyag kitárolására és a befejezett termékek betárolására vonatkozó munka létrehozását egy termékkészletre vonatkozóan az adott helyeken.</td>
</tr>
<tr>
<td>Adja meg, hogy a gyártási kimenet helye nem azonosítótáblás szabályozású.</td>
<td>Most megadhatja, hogy a gyártási kimenet helye nem azonosítótáblás szabályozású. Ez a szolgáltatás akkor hasznos, például, ha egy felsőbb rétegbeli termelési rendelés késztermékeket jelent közvetlenül alsóbb rétegbeli termelések beérkezési helyére.</td>
</tr>
<tr>
<td>Eltérő termékdimenziókkal rendelkező azonos termékeket tartalmazó anyagjegyzék támogatása.</td>
<td>A termelés során egy vagy több termékméretet használva előfordulhatnak olyan helyzetek, ahol ugyanazt az elemet szeretné egy másik változata alapján létrehozni. További tájékoztatást a <a href="https://blogs.msdn.microsoft.com/axmfg/2015/12/22/support-for-boms-that-includes-items-with-different-product-dimensions-of-the-same-item/">ezen a blogon talál</a>.</td>
</tr>
<tr>
<td>Az anyagjegyzékek első szintjén lévő körkörös struktúrájú termelési rendelések kizárásra kerülnek az anyagjegyzék-szint erőforrás-tervezés kiszámításánál.</td>
<td>Nincs lehetőség a megfelelő Anyagjegyzék-szintek Anyagjegyzék-hierarchiában körkörösséget okozó termékváltozatok hozzárendeléséhez.</td>
</tr>
<tr>
<td>Külön anyagjegyzékszintek számítása és erőforrástervezésre a költség kiszámításra:
<ul>
<li>Az anyag típusú erőforrás-tervezésnél anyagjegyzék szinteket új <strong>ReqItemLevel</strong> táblában számolják. Befejezett termelési rendelések kiszámítása során figyelmen kívül hagyja.</li>
<li>A termelési költség kiszámításánál anyagjegyzék szinteket a <strong>InventTable</strong> táblán számolnak. Befejezett termelési rendelések kiszámítása során figyelembe veszi.</li>
</ul>
</td>
<td>
<ul>
<li>Anyag típusú erőforrás tervezés futtatásakor alaptervezési ütemezés tervezése és alábontása esetén csak az anyag típusú erőforrás-tervezéskor használt anyagjegyzékszinteket kell számítani. Más szóval nincs szükség termelési készletértékelési kiszámításához használt Anyagjegyzékszintek kiszámításakor.</li>
<li>Árkalkulációs műveletek futtatásakor, mint például készletzárás, csak az anyagjegyzékeket használó termelési árkalkulációt kell újraszámolni.</li>
</ul>
</td>
</tr>
</tbody>
</table>

## <a name="additional-resources"></a>További erőforrások

[Új vagy módosult elemek a Finance and Operations kezdőlapján](whats-new-changed.md)

[Új vagy frissített feladat-útmutatók (2016. május)](new-updated-task-guides-available-may-2016.md)
