---
title: Szállítói kifizetési feltételek meghatározása
description: Ez a témakör ismerteti a szállítói számlák fizetési feltételeinek beállítását.
author: abruer
ms.date: 02/11/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: PaymTerm, CashDisc
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2199c12e92d631d3eb058637c48b53335d779f2d
ms.sourcegitcommit: 3105642fca2392edef574b60b4748a82cda0a386
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/12/2022
ms.locfileid: "8109807"
---
# <a name="define-vendor-payment-terms"></a>Szállítói kifizetési feltételek meghatározása

[!include [banner](../../includes/banner.md)]

Ez a témakör ismerteti a szállítói számlák fizetési feltételeinek beállítását. Ez a feladat az USMF bemutatócéget használja.

1. Válassza a **Navigációs ablaktábla > Modulok >Kötelezettségek > Kifizetés beállítása > Fizetési feltételek** elemet.
2. Válassza az **Új** lehetőséget. A **Fizetési feltételek lapon** lehet meghatározni a határidő számításának módját. Ez nem a készpénzfizetési engedmény dátumának számítására való.  
3. Írjon be egy értéket a **Fizetési feltételek** mezőbe.
4. Írjon egy értéket a **Leírás mezőbe**.
5. A **Napok** mezőbe írjon be egy számot. Az itt megadott szám lesz használva az **esedékesség dátumának, illetve a fizetési módban meghatározott időszak záró dátumának hozzáadásához**. Ha például a **Nettó** lehetőséget választja, a szám az esedékességi dátumhoz adódik hozzá. Ha az **Aktuális hónap** lehetőséget választja, a szám hozzáadódik az aktuális hónap utolsó napjához, és így kerül kiszámításra az esedékességi dátum.  
6. Válassza a **Mentés** lehetőséget.
7. Zárja be a lapot.
8. Ugrás a **Kötelezettségek > Kifizetés beállítása > Készpénzfizetési** engedmények elemre.
9. Válassza az **Új** lehetőséget.
10. A **Készpénzfizetési engedmény** mezőbe írjon egy azonosítót.
11. Írjon egy értéket a **Leírás** mezőbe.
12. Ha a szállító többszintű engedményt kínál, válassza ki a következő készpénzfizetési engedményt, ha a jelenlegi lejárt.
13. Zárja be a lapot.
14. A **Napok** mezőbe írjon be egy számot. A Program **a** **Napok** mezőben megadott mennyiséget használja a készpénzfizetési engedmény dátumának kiszámításához, **a Nettó/aktuális mezőben kiválasztott beállítás** alapján. Ha a **Nettó** lehetőséget választotta, a mennyiség hozzáadódik a számla dátumához, és így kerül kiszámításra a készpénzfizetési engedmény dátuma. Ha az **Aktuális hónap** lehetőséget választotta, a mennyiség hozzáadódik az aktuális hónap végéhez, így kerül kiszámításra a készpénzfizetési engedmény dátuma.  
15. Az **Engedmény** mezőben adja meg a készpénzfizetési engedmény százalékát. 
16. Adja meg azt a fő számlát, amelyre a készpénzfizetési engedmény feladása történik a vevői számlákhoz, majd adja meg azt a fő számlát, amelyre a készpénzfizetési engedmény feladása történik a szállítói számlákhoz. Ha a **Kedvezmény ellenszámlák** beállításnál a **Fő számlát jelöli meg a szállítói kedvezményekhez**, akkor a rendszer a fő számlát fogja használni. Ha a beállítás a **Számlasorokon Számlák**, a készpénzfizetési engedmény feladása a számlasor eszköz-/költségszámla részére kerül feladásra.  
17. Válassza a **Mentés** lehetőséget.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
