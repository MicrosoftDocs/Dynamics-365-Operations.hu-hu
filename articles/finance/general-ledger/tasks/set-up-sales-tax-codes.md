---
title: Áfakódok beállítása
description: Ez a cikk bemutatja az áfakódok beállítását a Dynamics 365 Pénzügyben.
author: twheeloc
ms.date: 09/27/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TaxTable, TaxData
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: kfend
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b12133583f40cc17cb85f6dbd86697592af25caf
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8858468"
---
# <a name="set-up-sales-tax-codes"></a>Áfakódok beállítása

[!include [banner](../../includes/banner.md)]

Ez a cikk bemutatja az áfakódok beállítását. Áfakódok jönnek létre minden közvetett adóhoz vagy járulékhoz, amelyet a vállalat köteles kiszámítani, beszedni és megfizetni az adóhatóság számára.

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

    A **Számítás** gyorslapon az **Eredet** mezőben ha az **Egységárankénti** beállítást választja, az érték meg lesz szorozva a tranzakció összegével az áfaösszeg kiszámításához.  Ha az áfakód nem egy egységalapú adó, az értéke egy százalék, amelyet az ehhez az áfakódhoz tartozó Eredeti értékre alkalmaz az áfaösszeg kiszámításához.     

11. Válassza a **Mentés** lehetőséget.
12. Zárja be a lapot.
13. Válassza a **Mentés** lehetőséget.

Microsoft Dynamics Az Adószolgáltatás használata esetén a 10.0.22-es [...](../../localizations/global-tax-calcuation-service-overview.md)[**·**](../../localizations/emea-multiple-vat-registration-numbers.md)**pénzügyi** verzió 365-ös verziója szerint a Funkciókezelés munkaterületén engedélyezve van a Több áfaregisztrációs szám támogatása funkció, **az** adókód típusának megadására az Adótípus mező használható. A következő értékek állnak rendelkezésre:

- Normál áfa
- Csökkentett áfa
- Áfa (0%)
- Fogyasztási adó
- Egyéb

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
