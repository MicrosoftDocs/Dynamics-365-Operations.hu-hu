---
title: Szállítói kifizetések létrehozása és exportálása ISO20022 fizetési formátumban
description: Ez az eljárás bemutatja, hogyan hozhat létre fizetési sorokat a szállítói kifizetési naplóban, és hogyan hozhat létre szállítói fizetési fájlt az ISO2022 átutalást használva példaként.
author: mrolecki
ms.date: 01/17/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransVendPaym, SysQueryForm, VendPaymProposalEdit, BankAccountTableLookUp
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c7bd5308e7589cb280244ea85e184422cbe2aa09f1cb548a81445defbd082e42
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6752098"
---
# <a name="create-and-export-vendor-payments-using-iso20022-payment-format"></a>Szállítói kifizetések létrehozása és exportálása ISO20022 fizetési formátumban

[!include [banner](../../includes/banner.md)]

Ez az témakör bemutatja, hogyan hozhat létre fizetési sorokat a szállítói kifizetési naplóban, és hogyan hozhat létre szállítói fizetési fájlt az ISO2022 átutalást használva példaként.

Ez az ötödik azon öt eljárás közül, amelyek elektronikus jelentési beállítások használatával mutatják be a szállítói kifizetési folyamatot. Az DEMF bemutatóadatok segítségével végezze el ezt az példát.

## <a name="example"></a>Példa

1.    Ugorjon a **Kötelezettségek > Fizetési beállítás > Fizetési napló** pontra.
2.    Kattintson az **Új** elemre.
3.    A **Név** mezőben adjon meg vagy válasszon ki egy értéket.
4.    Kattintson a **Sorok > Kifizetési javaslat > Fizetési javaslat létrehozása** menügombra.
5.    Bontsa ki a **Szerepeltetni kívánt rekordok** szakaszt.
6.    Kattintson a **Szűrő** parancsra.
7.    A listában jelölje ki a **Szállítók táblára** és a **Szállítói számla mezőre** vonatkozó sort.
8.    A **Feltétel** mezőben adjon meg vagy válasszon ki egy értéket. Bármilyen feltétel alkalmazható a szállítói fizetési tranzakció kiválasztásához, ebben a példában a DE-001-et használjuk szállítói számlaként.
12.    Kattintson az **OK** gombra.
13.    Kattintson az **OK** gombra.
14.    Kattintson a **Fizetések létrehozása** lehetőségre.
15. Hozzon létre egy ISO20022 típusú fizetési fájlt.
    1.    Kattintson a **Kifizetések létrehozása** elemre.
    2.    A **Fizetési mód** mezőben adjon meg vagy válasszon ki egy értéket.
    3.    Írjon be egy értéket a **Fájlnév** mezőbe. Ebben a példában az euróban történő fizetés miatt a létrehozott fájl SEPA kompatibilis lesz. A ISO20022 jóváírás-átutalás és a többi szállítói fizetési dormátum is használható a fizetések létrehozására más pénznemekben.
    4.    A **Bankszámlák** mezőben adjon meg vagy válasszon ki egy értéket.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]