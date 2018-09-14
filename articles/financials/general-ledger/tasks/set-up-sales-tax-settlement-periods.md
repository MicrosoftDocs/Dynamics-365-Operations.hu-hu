--- 
title: "Áfafizetési időszakok beállítása"
description: "Az Áfakiegyenlítési időszakok információval rendelkeznek a periódusokról, hogy melyik áfát kell jelenteni és fizetni."
author: twheeloc
manager: AnnBe
ms.date: 08/29/2018
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
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: ab7d3a00a327f42a9f70c954d9b64a360a7f9163
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

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
14. Bontsa ki az Időszak időtartamai fület.
15. Kattintson a Hozzáadás gombra.
16. A listában jelölje meg a kiválasztott sort.
17. Adjon meg egy
Adjon meg egy dátumot a Kezdő dátum mezőben.
18. Adja meg a dátumot a „Záró dátum” mezőben.
19. Kattintson az Új időszak intervalluma.
    * Amint megadta az első intervallumot az új időszakok automatikusan létrejönnek. Visszatérhet és szükség szerint új intervallumokat adhat hozzá.  
20. Zárja be a lapot.


