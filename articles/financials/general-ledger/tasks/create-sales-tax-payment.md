---
title: Áfakifizetés létrehozása
description: Az áfakiegyenlítési és -feladási munka kiegyenlíti az áfaegyenlegesek az áfaszámlákon, és átvezeti az áfaelszámolási számlára az adott időszakra.
author: twheeloc
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: Dialog
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ee69cfee672be1571fd5cc630e33601bb5a48eac
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/01/2019
ms.locfileid: "1846559"
---
# <a name="create-a-sales-tax-payment"></a><span data-ttu-id="f0beb-103">Áfakifizetés létrehozása</span><span class="sxs-lookup"><span data-stu-id="f0beb-103">Create a sales tax payment</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="f0beb-104">Az áfakiegyenlítési és -feladási munka kiegyenlíti az áfaegyenlegesek az áfaszámlákon, és átvezeti az áfaelszámolási számlára az adott időszakra.</span><span class="sxs-lookup"><span data-stu-id="f0beb-104">The settle and post sales tax job settles sales tax balances on the sales tax accounts and offsets them to the sales tax settlement account for a given period.</span></span>

1. <span data-ttu-id="f0beb-105">Ugorjon az Adó > Bevallások > Áfa > Áfa kiegyenlítése és feladása pontra.</span><span class="sxs-lookup"><span data-stu-id="f0beb-105">Go to Tax > Declarations > Sales tax > Settle and post sales tax.</span></span>
2. <span data-ttu-id="f0beb-106">A Kiegyenlítési időszak mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="f0beb-106">In the Settlement period field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="f0beb-107">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="f0beb-107">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="f0beb-108">Adjon meg egy dátumot a Kezdő dátum mezőben.</span><span class="sxs-lookup"><span data-stu-id="f0beb-108">In the From date field, enter a date.</span></span>
    * <span data-ttu-id="f0beb-109">Ha a Javítások figyelembevételével opció a Főkönyvi paraméterek lapon nincs bejelölve, a kiegyenlítés különböző verziókhoz feldolgozhatók.</span><span class="sxs-lookup"><span data-stu-id="f0beb-109">If the Include corrections option is not selected on the General ledger parameters page, the settlement can be processed for different versions.</span></span> <span data-ttu-id="f0beb-110">Az Eredeti az időszak-intervallum első kiegyenlítése, és a rendszer csak egyszer dolgozza fel az időszak-intervallumban.</span><span class="sxs-lookup"><span data-stu-id="f0beb-110">Original is the first settlement for a period interval and can only processed once for a period interval.</span></span> <span data-ttu-id="f0beb-111">A Legutóbbi korrekciók kiegyenlíti az áfatranzakciókat, amelyeket az eredeti verzió létrehozása után adtak fel.</span><span class="sxs-lookup"><span data-stu-id="f0beb-111">Latest corrections will settle sales tax transactions which have been posted after the original version has been created.</span></span>   
5. <span data-ttu-id="f0beb-112">A Tranzakció dátuma mezőben adjon meg egy dátumot.</span><span class="sxs-lookup"><span data-stu-id="f0beb-112">In the Transaction date field, enter a date.</span></span>
6. <span data-ttu-id="f0beb-113">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="f0beb-113">Click OK.</span></span>

