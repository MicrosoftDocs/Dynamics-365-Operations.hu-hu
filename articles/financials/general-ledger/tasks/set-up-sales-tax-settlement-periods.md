--- 
title: "Áfafizetési időszakok beállítása"
description: "Az Áfakiegyenlítési időszakok információval rendelkeznek a periódusokról, hogy melyik áfát kell jelenteni és fizetni."
author: twheeloc
manager: AnnBe
ms.date: 10/15/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: TaxPeriod
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 81214cc52b1488bb70ac5fd6ccc817f6f979163d
ms.openlocfilehash: 1087ed78e91b487ca7157bfdac1d72ae3f477875
ms.contentlocale: hu-hu
ms.lasthandoff: 10/16/2018

---
# <a name="set-up-sales-tax-settlement-periods"></a>Áfafizetési időszakok beállítása

[!include [task guide banner](../../includes/task-guide-banner.md)]

Az Áfakiegyenlítési időszakok információval rendelkeznek a periódusokról, hogy melyik áfát kell jelenteni és fizetni. Egy kiegyenlítési folyamat futtatható egy kiegyenlítési időszak megadott intervallumában. Minden kiegyenlítési időszakhoz rendelt adókód kiegyenlítésre kerül. Az érintett Adóhatóság beállításaitól függően az adókötelezettség feladásra kerül a szállítóhoz vagy a Főkönyvi számlához.



Ez a feladat az USMF bemutatócéget használja.



1. Ugrás az Adó > Közvetett adók > Áfa > Áfa kiegyenlítési periódusok elemre.
2. Kattintson az Új lehetőségre.
3. Írjon be egy értéket a Kiegyenlítési időszak meghatározása mezőbe.
4. A Leírás mezőben adjon meg egy értéket.
5. A Hatóság mezőben válassza ki azt az adóhatóságot, amely a kifizetési időszakhoz létrehozott jelentéseket és kifizetéseket kapja.
6. A kívánt rekord megkeresése és kijelölése a listán
7. A listában kattintson a kijelölt sorban lévő hivatkozásra.
8. A Fizetési feltételek mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
    * Az érintett Adóhatóság beállítható szállítóként és az Áfakiegyenlítés nyitott szállítói számlát hoz létre. A Fizetés feltételei meghatározzák a Határidőt nyitott szállítói számla esetén.  
9. Keresse meg és jelölje ki a kívánt rekordot a listán.
10. A listában kattintson a kijelölt sorban lévő hivatkozásra.
11. Válasszon a kiegyenlítési időszakok időtartamaihoz egy típust.
12. Adja meg a Periódus időtartam egységek periódusokra vonatkoztatott számát. Például egy negyedév 3 hónapból áll.
13. Jelölje be, vagy törölje a Kötegfolyamat használata forgalmi adó kiegyenlítéshez jelölőnégyzetet.
    * A kiegyenlítési időszakhoz tartozó kiegyenlítési folyamat kötegelt feladatként feldolgozható a háttérben. Ez adott időszakban nagyszámú adótranzakcióhoz ajánlott.  
14. Válassza ki, vagy törölje a jelölést Az ellenoldali adótranzakciók létrehozásának megakadályozása jelölőnégyzetből.
    * Alapértelmezés szerint a rendszer létrehozza az ellenoldali adótranzakciókat a kiegyenlítési folyamat során, amely teljesítményproblémákat, okozhat ha nagy számú adótranzakciók van egy időintervallumon belül. Jelölje be ezt a jelölőnégyzetet ellenoldali adótranzakciók létrehozásának megakadályozásához.
15. Bontsa ki az Időszak időtartamai fület.
16. Kattintson a Hozzáadás gombra.
17. A listában jelölje meg a kiválasztott sort.
18. Adjon meg egy dátumot a Kezdő dátum mezőben.
19. Adja meg a dátumot a „Záró dátum” mezőben.
20. Kattintson az Új időszak intervalluma.
    * Amint megadta az első intervallumot az új időszakok automatikusan létrejönnek. Visszatérhet és szükség szerint új intervallumokat adhat hozzá.  
21. Zárja be a lapot.


