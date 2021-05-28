---
title: A készként történő jelentéshez sztornírozása egy váratlan nyitott tranzakciót hoz létre
description: A befejezettként történő jelentés sztornírozása, amely jelöléssel rendelkezik, egy nyitott tranzakciót hoz létre, ahol a sztornóhoz kapcsolódó mennyiség készletdimenziói megegyeznek a sztornírozott tranzakcióval.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ProdTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: ea9044a9008e766c7fc92f98e27cfb91076f5b44
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026587"
---
# <a name="reversal-of-reporting-as-finished-creates-an-unexpected-open-transaction"></a>A készként történő jelentéshez sztornírozása egy váratlan nyitott tranzakciót hoz létre

Tudásbáziscikk száma: 4612469

## <a name="symptoms"></a>Tünetek

A befejezettként történő jelentés sztornírozása esetén a rendszer egy nyitott tranzakciót hoz létre, ahol a sztornóhoz kapcsolódó mennyiség készletdimenziói megegyeznek a sztornírozott tranzakcióval.

## <a name="resolution"></a>Felbontás

Készként jelentési művelet sztornírozása során a készletdimenziót a termelési naplóból inicializálja a program. Ebből következően a kötegszámot megkapja. A jelölés miatt az értékesítési rendelés tranzakciói öröklik a kötegszámot.

A dimenziót alaphelyzetbe lehet állítani a készként jelentés feladott feladása után.
