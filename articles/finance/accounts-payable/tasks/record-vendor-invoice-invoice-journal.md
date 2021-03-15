---
title: Szállítói számla rögzítése a számlanaplóban
description: Ez a feladat-útmutató bemutatja, hogyan rögzíthet szállítói számlákat amelyek nem kapcsolódnak beszerzési rendeléssel.
author: abruer
manager: AnnBe
ms.date: 07/11/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendInvoiceWorkspace, LedgerJournalTable, LedgerJournalTransVendInvoice
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 18d8b74bd8783c23e548a3185414d1461bc1d869
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4971828"
---
# <a name="record-a-vendor-invoice-in-the-invoice-journal"></a>Szállítói számla rögzítése a számlanaplóban

[!include [banner](../../includes/banner.md)]

Ez a feladat-útmutató bemutatja, hogyan rögzíthet szállítói számlákat amelyek nem kapcsolódnak beszerzési rendeléssel. Ilyen típusú számlák esetében a számla magában foglalja a szállítók és szolgáltatások költségeit.  Ez a felvétel az USMF bemutatócéget használja.

1. Ugorjon a **Navigációs ablaktábla > Modulok > Kötelezettségek > Munkaterületek > Szállítói számla bevitele** elemre.
2. A **Műveleti ablaktáblán** kattintson az **Új számlanapló** elemre.
3. Kattintson az **Új** elemre.
4. A **Név** mezőben adja meg a napló nevét, vagy kattintson a legördülő gombra a keresőlista megnyitásához.
5. Írjon egy értéket a **Leírás** mezőbe.
6. A **Művelet ablaktáblán** kattintson a **Sorok** elemre. A **Dátum** mezőben adja meg a feladás dátumát, ami frissül a Főkönyvben.  
7. A **Számla** mezőben adja meg a **Szállítói számlát**.
8. A **Számla** mezőben adja meg a számlaszámot.
9. Írjon egy értéket a **Leírás** mezőbe.
10. A **Hitelkeret** mezőben adjon meg egy számot.
11. Az **Ellenszámla** mezőben adja meg a számlaszámot, vagy kattintson a legördülő gombra a keresőlista megnyitásához
    * Az **Áfacsoport** alapértelmezett értéke a szállítói számlából származik.  
    * A **Cikk áfacsoportjának** alapértelmezett értéke a főszámlán az **Ellenszámla** mezőben megadott értékből származik.  
    * A **Határidőt** a Fizetési feltételek alapján számítja ki a rendszer.  
    * A **Készpénzfizetési engedmény** alapértelmezett értéke a Szállítói számlából származik.
12. Ha engedélyezte a Szállítói számlanapló munkafolyamatát, kattintson a **Munkafolyamat > Küldés** lehetőségre.
    * A beküldés jóváhagyásakor a program a dátumot a következő nyitott időszak első napjára vezeti, ha a tranzakció feladási dátuma a Várakoztatott vagy a Főkönyvi könyveléshez lezárt időszakon belülre esik.
12. Kattintson a **Bejegyzés** lehetőségre.
13. Zárja be a lapot.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]