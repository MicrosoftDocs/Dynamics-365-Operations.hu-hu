---
title: Áfakódok beállítása
description: Ez a témakör bemutatja, hogyan állítsuk be az áfát a Dynamics 365 Finance szolgáltatásban.
author: twheeloc
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TaxTable, TaxData
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6c7208fa65905fcc902d9c08b5b90178745e76d4
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5815044"
---
# <a name="set-up-sales-tax-codes"></a>Áfakódok beállítása

[!include [banner](../../includes/banner.md)]

Ez a témakör bemutatja, hogyan állítsuk be az áfakódokat. Áfakódok jönnek létre minden közvetett adóhoz vagy járulékhoz, amelyet a vállalat köteles kiszámítani, beszedni és megfizetni az adóhatóság számára.

Ez a feladat az USMF bemutatócéget használja.

1. Ugorjon a **Navigációs ablaktábla > Adók > Közvetett adók > Áfa > Áfakódok** lehetőségre.
2. Válassza az **Új** lehetőséget.
3. Adjon meg egy értéket az **Áfakód** mezőben.
4. Írjon be egy értéket a **Név** mezőbe.
5. A lehúzható lista megnyitásával válasszon ki egy **Kiegyenlítési időszakot**, majd adja meg az adóhatóságot, és hogy milyen időközönként kell ezt az áfát bevallani és befizetni.
6. Válassza ki a **Főkönyvi feladási csoportot**, és határozza meg azokat a fő számlákat, amelyek áfáját fel kell adni a főkönyvbe.
7. Bontsa ki a **Számítás** gyorslapot. Ezen a lapon több mező szerepel, amelyek megszabják, hogyan történik az áfaösszegek kiszámítása. Töltse ki ezeket a mezőket, ha szükséges.  
8. A felület felső részén lévő **Műveleti ablaktáblán** válassza ki az **Áfakód** lehetőséget.
9. Válassza ki az **Értékek** lehetőséget.
10. Adja meg az adókód értékét az **érték** oszlopban.
    - A **Számítás** gyorslapon az Eredet mezőben ha az Egységárankénti beállítást választja, az érték meg lesz szorozva a tranzakció összegével az áfaösszeg kiszámításához.  Ha az áfakód nem egy egységalapú adó, az értéke egy százalék, amelyet az ehhez az áfakódhoz tartozó Eredeti értékre alkalmaz az áfaösszeg kiszámításához.     
11. Válassza a **Mentés** lehetőséget.
12. Zárja be a lapot.
13. Válassza a **Mentés** lehetőséget.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]