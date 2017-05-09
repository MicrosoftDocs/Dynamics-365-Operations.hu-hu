---
title: "Mi az új vagy mi változott a Dynamics AX alkalmazásban verziószám 7.0.1 (2016. május)"
description: "Ez a leírás ismerteti az új vagy módosított a 7.0.1 alkalmazásverziójú Microsoft Dynamics AX szolgáltatásokat. Ez a verzió 2016 Májusában jelent meg és a build száma 7.0.1265.23014."
author: sericks007
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, Developer, IT Pro
ms.search.scope: AX 7.0.0, Operations
ms.custom: 91213
ms.assetid: f0bbc78f-87fc-40e9-b46a-6655893f69be
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: a638d89656b4a9d808526d1421dcd8865573b28f
ms.lasthandoff: 03/31/2017


---

# <a name="whats-new-or-changed-in-dynamics-ax-application-version-701-may-2016"></a>Mi az új vagy mi változott a Dynamics AX alkalmazásban verziószám 7.0.1 (2016. május)

[!include[banner](../includes/banner.md)]


Ez a leírás ismerteti az új vagy módosított a 7.0.1 alkalmazásverziójú Microsoft Dynamics AX szolgáltatásokat. Ez a verzió 2016 Májusában jelent meg és a build száma 7.0.1265.23014.

<a name="electronic-reporting-er"></a>Elektronikus jelentés (EJ)
-------------------------

|                                                                                                                                                                                        |                                                                                                                                                                                                                                                                                                                                                        |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Mit lehet tenni?**                                                                                                                                                                   | **Miért fontos ez?**                                                                                                                                                                                                                                                                                                                             |
| Futási idő párbeszédpanel konfigurálása Elektronikus jelentések (EJ) tervezéséhez, így a felhasználók kijelölhetik az általuk választott pénzügyi dimenziókat.                                     | A párbeszédpanelen egy EJ jelentés futtatása közben a felhasználók több pénzügyi dimenziót választhatnak ki. A kijelölt pénzügyi dimenziók részletei a létrehozott elektronikus dokumentumban jelennek meg.                                                                                                                              |
| Állítson be hozzáférést több pénzügyi dimenzióhoz az EJ jelentés létrehozása során egy egyszerű hozzárendelés segítségével a kívánt adatforráshoz.                                                  | Ugyanaz az ER-jelentéskonfiguráció használható elektronikus dokumentumok létrehozására, melyek tranzakciós adatokat és pénzügyi dimenziók részleteit a felhasználó vagy a jogi személy által választott dimenziók számától függetlenül tartalmazzák.                                             |
| Konfiguráljon EJ jelentést adatok beviteléhez az elektronikus dokumentum dinamikusan generált oszlopaiba, amely OPENXML munkalap formátumban jön létre.                                           | Az EJ-jelentés adatokat írhat be az oszlopok vízszintes replikálásán keresztül létrejött OPENXML munkalapokba. Ezért ugyanaz az EJ-jelentés konfiguráció újrahasználható eltérő számú dinamikusan generált oszloppal rendelkező elektronikus dokumentumok létrehozásához.                                                                                 |
| EJ célok beállítása úgy, hogy a kimeneti formátum eredménye meghatározott rendeltetési helyre irányuljon: fájl, e-mail vagy archívum (Microsoft SharePoint-mappa vagy Microsoft Azure tárolás). | Korábban, egy EJ-konfiguráció futtatásakor egy üzenetpanel jelent meg, amely egy fájl mentéséhez vagy megnyitásához felhasználó beavatkozást kért. Most külön elő-konfigurálhatja az egyes formátum-konfiguráció célját és annak kimeneti összetevőit (egy mappa vagy egy fájl). Megfelelő hozzáférési jogokkal rendelkező felhasználók módosíthatják a célbeállításokat futásidőben is. |

## <a name="pos--microsoft-dynamics-ax-retail"></a>Pénztár – Microsoft Dynamics AX Retail
|                                |                                                                                                                                                                                         |
|--------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Mit lehet tenni?**           | **Miért fontos ez?**                                                                                                                                                              |
| Használja a Google Chrome böngészőt. | Kiskereskedők mostantól a Felhőalapú pénztárt elindíthatják Chrome böngészőből, és a Felhőalapú pénztár minden, Microsoft Edge és az Internet Explorer böngészőkben elérhető szolgáltatását megtapasztalhatják. |

## <a name="financial-reporting"></a>Pénzügyi jelentéskészítés
|                                                                     |                                                                                                                                                                                                                                                                                                                    |
|---------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Mit lehet tenni?**                                                | **Miért fontos ez?**                                                                                                                                                                                                                                                                                         |
| A pénzügyi jelentési adatpiac újraépítése.                          | Amikor Dynamics AX adatbázisokat környezetek között helyezi át, vagy egyéb invazív módosítások hajt végre a Dynamics AX környezetében, a pénzügyi jelentéskészítő adatbázis újraépítése szükséges lesz valószínűleg. A Windows PowerShell-parancsfájl most lehetővé teszi az adatbázis újraépítését.                                                                |
| Már nem választhat érvénytelen jelentéstervező lehetőségek közül. | Számos Management reporter forgalmazott verziójában használt jelentéstervező a Dynamics AX ezen verziójára nem vonatkozik. Ezek a beállítások a pénzügyi jelentés tervező, a kimeneti és a csatolás voltak kapcsolatosak. Ezek a beállítások felhasználói hibák elkerülése érdekében a pénzügyi jelentés tervező el lett távolítva. |

## <a name="financial-management"></a>Pénzgazdálkodás
|                                                            |                                                                  |
|------------------------------------------------------------|------------------------------------------------------------------|
| **Mit lehet tenni?**                                       | **Miért fontos ez?**                                       |
| Bérszámfejtési bankszámlához tartozó ellenőrzött fizetési fájl generálása | Banki csekk csalás megelőzése érdekében a fizetési ellenőrző fájlok hozhatók létre. |

## <a name="warehouse-and-production"></a>Raktár és termelés
|                                                                                                                                                                                                                                                                                                                                                                                         |                                                                                                                                                                                                                                                                                                                                                                                                                                         |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Mit lehet tenni?**                                                                                                                                                                                                                                                                                                                                                                    | **Miért fontos ez?**                                                                                                                                                                                                                                                                                                                                                                                                              |
| Határozzon meg raktári munka-irányelvet az egyes helyeken létrehozott termékek szabályozására.                                                                                                                                                                                                                                                                          | A raktárkezelési folyamatok nem mindig tartalmazzák a munkát. Az új raktári munka irányelveinek használatával megakadályozhatja a nyersanyag kitárolására és a befejezett termékek betárolására vonatkozó munka létrehozását egy termékkészletre vonatkozóan az adott helyeken.                                                                                                                                                                                                     |
| Adja meg, hogy a gyártási kimenet helye nem azonosítótáblás szabályozású.                                                                                                                                                                                                                                                                                                               | Most megadhatja, hogy a gyártási kimenet helye nem azonosítótáblás szabályozású. Ez a szolgáltatás akkor hasznos, például, ha egy felsőbb rétegbeli termelési rendelés késztermékeket jelent közvetlenül alsóbb rétegbeli termelések beérkezési helyére.                                                                                                                                                     |
| Eltérő termékdimenziókkal rendelkező azonos termékeket tartalmazó anyagjegyzék támogatása.                                                                                                                                                                                                                                                                                                     | A termelés során egy vagy több termékméretet használva előfordulhatnak olyan helyzetek, ahol ugyanazt az elemet szeretné egy másik változata alapján létrehozni. További tájékoztatást a [ezen a blogon talál](https://blogs.msdn.microsoft.com/axmfg/2015/12/22/support-for-boms-that-includes-items-with-different-product-dimensions-of-the-same-item/).                                                                  |
| Az anyagjegyzékek első szintjén lévő körkörös struktúrájú termelési rendelések kizárásra kerülnek az anyagjegyzék-szint erőforrás-tervezés kiszámításánál.                                                                                                                                                                                                                                     | Nincs lehetőség a megfelelő Anyagjegyzék-szintek Anyagjegyzék-hierarchiában körkörösséget okozó termékváltozatok hozzárendeléséhez.                                                                                                                                                                                                                                                                                                  |
| Külön anyagjegyzékszintek számítása és erőforrástervezésre a költség kiszámításra: • Az anyag típusú erőforrás-tervezésnél anyagjegyzék szinteket új **ReqItemLevel** táblában számolják. Befejezett termelési rendelések kiszámítása során figyelmen kívül hagyja. • A termelési költség kiszámításánál anyagjegyzék szinteket a **InventTable** táblán számolnak. Befejezett termelési rendelések kiszámítása során figyelembe veszi. | • Anyag típusú erőforrás tervezés futtatásakor alaptervezési ütemezés tervezése és alábontása esetén csak az anyag típusú erőforrás-tervezéskor használt anyagjegyzékszinteket kell számítani. Más szóval nincs szükség termelési készletértékelési kiszámításához használt Anyagjegyzékszintek kiszámításakor. • Árkalkulációs műveletek futtatásakor, mint például készletzárás, csak az anyagjegyzékeket használó termelési árkalkulációt kell újraszámolni. |

 

<a name="see-also"></a>Lásd még
--------

[Mi az, ami új vagy módosított](whats-new-changed.md)

[Új vagy frissített feladat-útmutatók (2016. május)](new-updated-task-guides-available-may-2016.md)




