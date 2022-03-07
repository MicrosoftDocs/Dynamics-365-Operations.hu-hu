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
ms.openlocfilehash: 73ebc45ee83516f573c3f73ef8106da9ae44c590c05d8dbd08520bc5ef19e49a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6714210"
---
# <a name="reversal-of-reporting-as-finished-creates-an-unexpected-open-transaction"></a>A készként történő jelentéshez sztornírozása egy váratlan nyitott tranzakciót hoz létre

Tudásbáziscikk száma: 4612469

## <a name="symptoms"></a>Tünetek

A befejezettként történő jelentés sztornírozása esetén a rendszer egy nyitott tranzakciót hoz létre, ahol a sztornóhoz kapcsolódó mennyiség készletdimenziói megegyeznek a sztornírozott tranzakcióval.

## <a name="resolution"></a>Felbontás

Készként jelentési művelet sztornírozása során a készletdimenziót a termelési naplóból inicializálja a program. Ebből következően a kötegszámot megkapja. A jelölés miatt az értékesítési rendelés tranzakciói öröklik a kötegszámot.

A dimenziót alaphelyzetbe lehet állítani a készként jelentés feladott feladása után.
