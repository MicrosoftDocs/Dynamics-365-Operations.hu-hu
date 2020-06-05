---
title: Szállítói bankszámla létrehozása
description: Ez az eljárás bemutatja a szállítóhoz tartozó bankszámla létrehozásának módját.
author: mkirknel
manager: tfehr
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendTable, VendBankAccounts, LogisticsPostalAddressSingle
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f8092ab7f960fd36515afb8448dfe1e262197595
ms.sourcegitcommit: 8a2127c5af6cdbda30ccc1f9bef9bd4ab61e9e50
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/18/2020
ms.locfileid: "3383136"
---
# <a name="create-a-vendor-bank-account"></a>Szállítói bankszámla létrehozása

[!include [banner](../../includes/banner.md)]

Ez az eljárás bemutatja a szállítóhoz tartozó bankszámla létrehozásának módját. Az USMF bemutatócég adataiban használhatja ezt az eljárást.

1. Válassza ezt: **Navigációs ablaktábla > Modulok > Beszerzés és forrás > Szállítók > Összes beszállító**.
2. Válassza ki azt a szállítót, akihez létre szeretne hozni bankszámlát, majd kattintson a **Szállítói számla azonosító** mezőn található hivatkozásra.
3. A **Műveleti panelen** kattintson a **Szállító** elemre.
4. Kattintson a **Bankszámlák** lehetőségre.
5. A **Műveleti panelen** kattintson az **Új** elemre.
6. A **Bankszámla** mezőben adjon meg egy értéket. Ez az azonosító a szállítói rekordban szereplő bankszámla azonosítására szolgál.  
7. Írjon be egy értéket a **Név** mezőbe.
8. A **Bankcsoportok** mezőben adjon meg vagy válasszon ki egy értéket.
9. Válasszon ki egy beállítást az **Útvonalszám típusa** mezőben. Ez a nemzetközi fizetésekhez használt útvonalszám típusa.  
10. A **Bankszámlaszám** mezőben adjon meg egy értéket.
11. A **SWIFT kód** mezőbe írjon be egy értéket.
12. Az **IBAN** mezőben adjon meg egy értéket.
    - Megfelelő formátumban kell megadni az IBAN számot. Például, a következő számot használhatja: DE89370400440532013000.  
    - A bankszámla állapota aktív, ha a rendszer elérte az Aktivitás dátumát, és nem lépte túl a Lejárati dátumot. Ez akkor is aktív, ha az Aktiválás dátuma és a Lejárati dátum mező egyaránt üres. Ha az Aktiválás dátuma és a Lejárati dátum mezőben szereplő dátumok egyaránt jövőbeli dátumok, akkor nincs lehetőség elektronikus fizetésre. A bankszámla egyébként aktív, és az egyéb fizetési típusok alkalmazhatók.  
13. Bontsa ki a **Beállítások** szakaszt.
14. Adjon meg egy értéket a **Szöveges kód** mezőben. Ez a mező egy olyan kódot határoz meg, amely az átvevő banki kivonatán fog megjelenni.  
15. Adjon meg egy értéket az **Üzenet a banknak** mezőben.
16. Adjon meg egy értéket az **Árfolyam-hivatkozás** mezőben. Ez az esetleges előzetes vagy a rögzített átváltási árfolyam hivatkozási száma.
17. A **Pénznem** mezőben adjon meg vagy válasszon ki egy értéket. Az ellenőrző tranzakciók elküldésekor, ez a szakasz egy áttekintést nyújt a (folyamatban lévő vagy engedélyezett) állapotukról.  
18. Bontsa ki a **Cím** szakaszt.
19. Bontsa ki az **Ellenőrző tranzakciók** szakaszt.
20. Bontsa ki a **Kapcsolattartási adatok** szakaszt.
21. Írjon be egy értéket a **Telefon** mezőbe.
22. Zárja be a lapot.
23. Kattintson a **Szerkesztés** lehetőségre.
24. Bontsa ki a **Kifizetés** szakaszt.
25. Válassza ki az újonnan létrehozott számlát a **Bankszámla** mezőben.
26. Kattintson a **Mentés** gombra. A cím örökölhető a banki csoporttól, ha meg van határozva egy cím, illetve itt, hozzá is adhatja azt.  

