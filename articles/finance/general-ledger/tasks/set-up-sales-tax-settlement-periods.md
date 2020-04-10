---
title: Áfafizetési időszakok beállítása
description: Ez a témakör bemutatja, hogyan állítsuk be az áfakiegyenlítési időszakokat a Dynamics 365 Finance szolgáltatásban.
author: twheeloc
manager: AnnBe
ms.date: 08/05/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxPeriod
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5972c44261a6ebd49df0fcbcef9a8c60aaa487e2
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/18/2020
ms.locfileid: "3144720"
---
# <a name="set-up-sales-tax-settlement-periods"></a>Áfafizetési időszakok beállítása

[!include [banner](../../includes/banner.md)]

Ez a témakör bemutatja, hogyan állítsuk be az áfakiegyenlítési időszakokat. Az Áfakiegyenlítési időszakok információval rendelkeznek a periódusokról, hogy melyik áfát kell jelenteni és fizetni. Egy kiegyenlítési folyamat futtatható egy kiegyenlítési időszak megadott intervallumában. Minden kiegyenlítési időszakhoz rendelt adókód kiegyenlítésre kerül. Az érintett Adóhatóság beállításaitól függően az adókötelezettség feladásra kerül a szállítóhoz vagy a Főkönyvi számlához.

Ez a feladat az USMF bemutatócéget használja.

1. A Navigációs ablaktáblán lépjen a **Modulok > Adó > Közvetett adók > Áfa > Áfakiegyenlítési időszakok** elemre.
2. Válassza az **Új** lehetőséget.
3. Írjon be egy értéket a **Kiegyenlítési időszak** meghatározása mezőbe.
4. Írjon egy értéket a **Leírás** mezőbe.
5. A **Hatóság mezőben** válassza ki azt az adóhatóságot, amely a kifizetési időszakhoz létrehozott jelentéseket és kifizetéseket kapja.
6. Keresse meg és jelölje ki a kívánt rekordot a listán.
7. A **Fizetési feltételek** mezőben válassza ki a kívánt rekordot a legördülő menüből. Az érintett Adóhatóság beállítható szállítóként és az Áfakiegyenlítés nyitott szállítói számlát hoz létre. A Fizetés feltételei meghatározzák a Határidőt nyitott szállítói számla esetén.  
8. Válasszon a kiegyenlítési időszakok időtartamaihoz egy típust.
9. Adja meg a Periódus időtartam egységek periódusokra vonatkoztatott számát. Például egy negyedév 3 hónapból áll.
10. Jelölje be, vagy törölje a **Kötegelt feldolgozás használata az áfa kiegyenlítéséhez** jelölőnégyzetet. A kiegyenlítési időszakhoz tartozó kiegyenlítési folyamat kötegelt feladatként feldolgozható a háttérben. Ez adott időszakban nagyszámú adótranzakcióhoz ajánlott.  
    > [!NOTE]
    > Jelenleg nem támogatott Spanyolországban, Japánban és Hollandiában.
11. Válassza ki, vagy törölje a jelölést **Az ellenoldali adótranzakciók létrehozásának megakadályozása**  jelölőnégyzetből. Alapértelmezés szerint a rendszer létrehozza az ellenoldali adótranzakciókat a kiegyenlítési folyamat során, amely teljesítményproblémákat, okozhat ha nagy számú adótranzakciók van egy időintervallumon belül. Jelölje be ezt a jelölőnégyzetet ellenoldali adótranzakciók létrehozásának megakadályozásához.
12. Bontsa ki az **Időszak időtartamai** fület.
13. Válassza a **Hozzáadás** lehetőséget.
14. A **Kezdő dátum** mező új sorában adja meg a dátumot.
15. Adjon meg egy dátumot a **Záró dátum** mezőben.
16. Válassza ki az **Új időszak intervalluma** elemet. Amint megadta az első intervallumot az új időszakok automatikusan létrejönnek. Visszatérhet és szükség szerint új intervallumokat adhat hozzá.  
17. Zárja be a lapot.

