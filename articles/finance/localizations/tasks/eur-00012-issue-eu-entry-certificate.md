---
title: EUR-00012 Európai beérkezési igazolás kibocsátása
description: Ez az eljárás bemutatja az EU beérkezési igazolás engedélyezésén és a vevői számla beállításán a beérkezési igazolások használata és az igazolás kiállítása érdekében.
author: mrolecki
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustParameters, CustTable, SalesTableListPage, SalesCreateOrder, SalesTable, SalesEditLines,  CustInvoiceJournal, CustEntryCertificateJour_W, SrsReportViewerForm
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0091af30b917aab3b8c4572a72a20d8d2d5d52e2
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4408018"
---
# <a name="eur-00012-issue-an-eu-entry-certificate"></a>EUR-00012 Európai beérkezési igazolás kibocsátása

[!include [banner](../../includes/banner.md)]
Ez az eljárás bemutatja az EU beérkezési igazolás engedélyezésén és a vevői számla beállításán a beérkezési igazolások használata és az igazolás kiállítása érdekében. Ez az eljárás a DEMF bemutatócég segítségével lett létrehozva.


## <a name="enable-entry-certificate-management"></a>Beérkezési igazolások kezelésének engedélyezése
1. Ugorjon a Kintlévőségek > Beállítás > Kinnlevőségek paraméterei pontra.
2. Kattintson a Szállítások fülre.
3. Bontsa ki a Beérkezési igazolás szakaszt.
4. Jelölje be az Igent a Beérkezési igazolások kezelésének engedélyezése mezőben.
5. Jelölje be az Igent a Beérkezési igazolások kiadásának engedélyezése mezőben.
6. Kattintson a Számsorozatok lapra.
7. A listában keresse meg és jelölje be a Beérkezési igazolás sort.
8. A Számsorrend kódja mezőben adjon meg, vagy válasszon ki egy értéket.

## <a name="set-up-a-customer"></a>Ügyfél beállítása
1. Ugorjon a Kinnlevőségek > Vevők > Minden vevő pontra.
2. Rekordok kereséséhez használja a gyorsszűrőt. Például szűkítsen a „Számla” mezővel a „DE-015” értéket beírva.
3. Nyissa meg a Vevői számla részletes adatait.
4. Kattintson a Szerkesztés lehetőségre.
5. Nyissa meg A számlázás és szállítás szakaszt.
6. Jelölje be az Igent a Beérkezési igazolás szükséges hozzá mezőben.
7. Jelölje be az Igent a Beérkezési igazolás kiadása mezőben.
8. Kattintson a Mentés gombra.

## <a name="create-an-eu-entry-certificate-automatically"></a>EU-s beérkezési igazolás automatikus létrehozása
1. Ugorjon a Kinnlevőségek > Rendelések > Minden értékesítési rendelés elemre.
2. Kattintson az Új lehetőségre.
3. A Vevőszámla mezőben adjon meg vagy válasszon ki egy értéket.
4. Kattintson az OK gombra.
5. Az Elemszám mezőben adjon meg, vagy válasszon ki egy értéket.
6. Kattintson a Mentés gombra.
7. A Művelet panelen kattintson a Kitárolás és csomagolás elemre.
8. Kattintson A szállítólevél feladása lehetőségre.
9. Bontsa ki a Paraméterek szakaszt.
10. A Mennyiség mezőben válassza a „Mind” lehetőséget.
11. Törölje a jelet a jelölőnégyzetből a Beérkezési igazolások kiállítása mellett.
    * A beérkezési igazolást a szállítólevél feladásakor, vagy a rendelés számlázása során állíthatja ki. Hagyja üresen a Beérkezési igazolás kiállítása jelölőnégyzetet, ha később szeretné azt kiállítani.  
12. Kattintson az OK gombra.
13. Kattintson az OK gombra.
14. A Művelet panelen kattintson a Számla lehetőségre.
15. Kattintson a Számla lehetőségre.
    * Győződjön meg róla, hogy a Beérkezési igazolás szükséges, és a Bejegyzési tanúsítvány kiadása, illetve az Áttekintés jelölőnégyzetek be vannak jelölve.  Kiválaszthatja a Beérkezési igazolás nyomtatása jelölőnégyzetet is az igazolás kinyomtatásához.  
16. Kattintson az OK gombra.
17. Kattintson az OK gombra.
18. A Művelet panelen kattintson a Számla lehetőségre.
19. Kattintson a Számla lehetőségre.
20. A Művelet panelen kattintson a Számla lehetőségre.
21. Kattintson a Kiállított beérkezési igazolások megtekintése elemre.
22. Kattintson a Nyomtatás parancsra.
23. Zárja be a lapot.
24. Kattintson az Állapot módosítása elemre.
25. Az Új állapot mezőben válasszon ki egy opciót.
26. Kattintson az OK gombra.
27. Zárja be a lapot.

## <a name="create-an-eu-entry-certificate-manually"></a>EU-s beérkezési igazolás manuális létrehozása
1. A Művelet panelen kattintson a Számla lehetőségre.
2. Kattintson a Beérkezési igazolás létrehozása elemre.
3. Kattintson az OK gombra.
4. A Művelet panelen kattintson a Számla lehetőségre.
5. Kattintson a Kiállított beérkezési igazolások megtekintése elemre.

