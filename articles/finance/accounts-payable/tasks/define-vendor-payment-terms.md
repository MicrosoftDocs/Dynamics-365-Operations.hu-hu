---
title: Szállítói kifizetési feltételek meghatározása
description: Ez a témakör ismerteti a szállítói számlák fizetési feltételeinek beállítását.
author: abruer
manager: AnnBe
ms.date: 07/09/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PaymTerm, CashDisc
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1b69b505996b5536088578885c11a7e8c27f4975
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4971853"
---
# <a name="define-vendor-payment-terms"></a>Szállítói kifizetési feltételek meghatározása

[!include [banner](../../includes/banner.md)]

Ez a témakör ismerteti a szállítói számlák fizetési feltételeinek beállítását. Ez a feladat az USMF bemutatócéget használja.

1. Válassza a **Navigációs ablaktábla > Modulok >Kötelezettségek > Kifizetés beállítása > Fizetési feltételek** elemet.
2. Válassza az **Új** lehetőséget. A fizetési feltételek oldalon meghatározhatja az esedékességi dátum számítását. Ez nem a készpénzfizetési engedmény dátumának számítására való.  
3. Írjon be egy értéket a **Fizetési feltételek** mezőbe.
4. Írjon egy értéket a **Leírás mezőbe**.
5. A **Napok** mezőbe írjon be egy számot. Az itt megadott szám hozzáadódik az esedékességi dátumhoz vagy a fizetési módban meghatározott időszak végéhez. Ha például a **Nettó** lehetőséget választja, a szám az esedékességi dátumhoz adódik hozzá. Ha az **Aktuális hónap** lehetőséget választja, a szám hozzáadódik az aktuális hónap utolsó napjához, és így kerül kiszámításra az esedékességi dátum.  
6. Válassza a **Mentés** lehetőséget.
7. Zárja be a lapot.
8. Ugrás a **Kötelezettségek > Kifizetés beállítása > Készpénzfizetési** engedmények elemre.
9. Válassza az **Új** lehetőséget.
10. A **Készpénzfizetési engedmény** mezőbe írjon egy azonosítót.
11. Írjon egy értéket a **Leírás** mezőbe.
12. Ha a szállító többszintű engedményt kínál, válassza ki a következő készpénzfizetési engedményt, ha a jelenlegi lejárt.
13. Zárja be a lapot.
14. A **Napok** mezőbe írjon be egy számot. A **Napok** mezőben megadott mennyiség segítségével a készpénzfizetési engedmény számítása történik a **Nettó/Aktuális** mezőben megadott lehetőségeket is figyelembe véve. Ha a **Nettó** lehetőséget választotta, a mennyiség hozzáadódik a számla dátumához, és így kerül kiszámításra a készpénzfizetési engedmény dátuma. Ha az **Aktuális hónap** lehetőséget választotta, a mennyiség hozzáadódik az aktuális hónap végéhez, így kerül kiszámításra a készpénzfizetési engedmény dátuma.  
15. Az **Engedmény** mezőben adja meg a készpénzfizetési engedmény százalékát. 
16. Adja meg azt a fő számlát, amelyre a készpénzfizetési engedmény feladása történik a vevői számlákhoz, majd adja meg azt a fő számlát, amelyre a készpénzfizetési engedmény feladása történik a szállítói számlákhoz. Ha a **Kedvezmény ellenszámlák** beállításnál a **Fő számlát jelöli meg a szállítói kedvezményekhez**, akkor a rendszer a fő számlát fogja használni. Ha a beállítás a **Számlasorokon Számlák**, a készpénzfizetési engedmény feladása a számlasor eszköz-/költségszámla részére kerül feladásra.  
17. Válassza a **Mentés** lehetőséget.

