---
title: Áfafizetési időszakok beállítása
description: Ez a cikk bemutatja az áfafizetési időszakok beállítását a Dynamics 365 Pénzügyben.
author: twheeloc
ms.date: 08/05/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TaxPeriod
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3f8514494b5d3534fc236def817df0d58fe80d70
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8846683"
---
# <a name="set-up-sales-tax-settlement-periods"></a>Áfafizetési időszakok beállítása

[!include [banner](../../includes/banner.md)]

Ez a cikk bemutatja az áfafizetési időszakok beállítását. Az Áfakiegyenlítési időszakok információval rendelkeznek a periódusokról, hogy melyik áfát kell jelenteni és fizetni. Egy kiegyenlítési folyamat futtatható egy kiegyenlítési időszak megadott intervallumában. Minden kiegyenlítési időszakhoz rendelt adókód kiegyenlítésre kerül. Az érintett Adóhatóság beállításaitól függően az adókötelezettség feladásra kerül a szállítóhoz vagy a Főkönyvi számlához.

Ez a feladat az USMF bemutatócéget használja.

1. Ugrás az **áfafizetési > áfafizetési > áfafizetési > áfafizetési időszakokhoz**.
2. Válassza az **Új** lehetőséget.
3. Írjon be egy értéket a **Kiegyenlítési időszak** meghatározása mezőbe.
4. Írjon egy értéket a **Leírás** mezőbe.
5. A **Hatóság mezőben** válassza ki azt az adóhatóságot, amely a kifizetési időszakhoz létrehozott jelentéseket és kifizetéseket kapja.
6. Keresse meg és jelölje ki a kívánt rekordot a listán.
7. A **Fizetési feltételek** mezőben válassza ki a kívánt rekordot a legördülő menüből. Az érintett Adóhatóság beállítható szállítóként és az Áfakiegyenlítés nyitott szállítói számlát hoz létre. A Fizetés feltételei meghatározzák a Határidőt nyitott szállítói számla esetén.  
8. Válasszon a kiegyenlítési időszakok időtartamaihoz egy típust.
9. Adja meg a Periódus időtartam egységek periódusokra vonatkoztatott számát. Például egy negyedév 3 hónapból áll.
10. Jelölje be, vagy törölje a **Kötegelt feldolgozás használata az áfa kiegyenlítéséhez** jelölőnégyzetet. A kiegyenlítési időszakhoz tartozó kiegyenlítési folyamat kötegelt feladatként feldolgozható a háttérben. Ez adott időszakban nagyszámú adótranzakcióhoz ajánlott.
11. Válassza ki, vagy törölje a jelölést **Az ellenoldali adótranzakciók létrehozásának megakadályozása**  jelölőnégyzetből. Alapértelmezés szerint a rendszer létrehozza az ellenoldali adótranzakciókat a kiegyenlítési folyamat során, amely teljesítményproblémákat, okozhat ha nagy számú adótranzakciók van egy időintervallumon belül. Jelölje be ezt a jelölőnégyzetet ellenoldali adótranzakciók létrehozásának megakadályozásához.
12. Bontsa ki az **Időszak időtartamai** fület.
13. Válassza a **Hozzáadás** lehetőséget.
14. A **Kezdő dátum** mező új sorában adja meg a dátumot.
15. Adjon meg egy dátumot a **Záró dátum** mezőben.
16. Válassza ki az **Új időszak intervalluma** elemet. Amint megadta az első intervallumot az új időszakok automatikusan létrejönnek. Visszatérhet és szükség szerint új intervallumokat adhat hozzá.  
17. Zárja be a lapot.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
