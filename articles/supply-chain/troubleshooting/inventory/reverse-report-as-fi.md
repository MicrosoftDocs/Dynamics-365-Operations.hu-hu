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
# <a name="reversal-of-reporting-as-finished-creates-an-unexpected-open-transaction"></a><span data-ttu-id="e4111-103">A készként történő jelentéshez sztornírozása egy váratlan nyitott tranzakciót hoz létre</span><span class="sxs-lookup"><span data-stu-id="e4111-103">Reversal of reporting as finished creates an unexpected open transaction</span></span>

<span data-ttu-id="e4111-104">Tudásbáziscikk száma: 4612469</span><span class="sxs-lookup"><span data-stu-id="e4111-104">KB number: 4612469</span></span>

## <a name="symptoms"></a><span data-ttu-id="e4111-105">Tünetek</span><span class="sxs-lookup"><span data-stu-id="e4111-105">Symptoms</span></span>

<span data-ttu-id="e4111-106">A befejezettként történő jelentés sztornírozása esetén a rendszer egy nyitott tranzakciót hoz létre, ahol a sztornóhoz kapcsolódó mennyiség készletdimenziói megegyeznek a sztornírozott tranzakcióval.</span><span class="sxs-lookup"><span data-stu-id="e4111-106">If you reverse reporting as finished that has marking, the system creates an open transaction where the reversed quantity has the same inventory dimensions as the transaction that was reversed.</span></span>

## <a name="resolution"></a><span data-ttu-id="e4111-107">Felbontás</span><span class="sxs-lookup"><span data-stu-id="e4111-107">Resolution</span></span>

<span data-ttu-id="e4111-108">Készként jelentési művelet sztornírozása során a készletdimenziót a termelési naplóból inicializálja a program.</span><span class="sxs-lookup"><span data-stu-id="e4111-108">When you reverse a report-as-finished operation, the inventory dimension is initialized from the production journal.</span></span> <span data-ttu-id="e4111-109">Ebből következően a kötegszámot megkapja.</span><span class="sxs-lookup"><span data-stu-id="e4111-109">Therefore, it gets the batch number.</span></span> <span data-ttu-id="e4111-110">A jelölés miatt az értékesítési rendelés tranzakciói öröklik a kötegszámot.</span><span class="sxs-lookup"><span data-stu-id="e4111-110">Because of marking, the sales order transactions will inherit the batch number.</span></span>

<span data-ttu-id="e4111-111">A dimenziót alaphelyzetbe lehet állítani a készként jelentés feladott feladása után.</span><span class="sxs-lookup"><span data-stu-id="e4111-111">The dimension can be reset when the reporting as finished is posted.</span></span>
