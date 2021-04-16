---
title: Áfakifizetés létrehozása
description: Az áfakiegyenlítési és -feladási munkaeljárás kiegyenlíti az áfaegyenlegesek az áfaszámlákon, és átvezeti az áfaelszámolási számlára az adott időszakra.
author: twheeloc
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: Dialog
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5066689fb85dd176da1ca1561614e443cb87d816
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5832754"
---
# <a name="create-a-sales-tax-payment"></a><span data-ttu-id="b99eb-103">Áfakifizetés létrehozása</span><span class="sxs-lookup"><span data-stu-id="b99eb-103">Create a sales tax payment</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="b99eb-104">Az áfakiegyenlítési és -feladási munkaeljárás kiegyenlíti az áfaegyenlegesek az áfaszámlákon, és átvezeti az áfaelszámolási számlára az adott időszakra.</span><span class="sxs-lookup"><span data-stu-id="b99eb-104">The settle and post sales tax job procedure settles sales tax balances on the sales tax accounts, and offsets them to the sales tax settlement account for a given period.</span></span>

1. <span data-ttu-id="b99eb-105">Ugorjon az **Adó > Bevallások > Áfa > Áfa kiegyenlítése és feladása** pontra.</span><span class="sxs-lookup"><span data-stu-id="b99eb-105">Go to **Tax > Declarations > Sales tax > Settle and post sales tax**.</span></span>
2. <span data-ttu-id="b99eb-106">A **Kiegyenlítési időszak** mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="b99eb-106">In the **Settlement period** field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="b99eb-107">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="b99eb-107">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="b99eb-108">Adjon meg egy dátumot a **Kezdő dátum** mezőben.</span><span class="sxs-lookup"><span data-stu-id="b99eb-108">In the **From date** field, enter a date.</span></span>
    * <span data-ttu-id="b99eb-109">Ha nem választja ki a **Javítások figyelembevétele** opciót a **Főkönyvi paraméterek** lapon, a kiegyenlítés különböző verziókhoz feldolgozhatók.</span><span class="sxs-lookup"><span data-stu-id="b99eb-109">If you don't select the **Include corrections** option on the **General ledger parameters** page, the settlement can be processed for different versions.</span></span> <span data-ttu-id="b99eb-110">Az eredeti az időszak-intervallum első kiegyenlítése, és a rendszer csak egyszer dolgozza fel az időszak-intervallumban.</span><span class="sxs-lookup"><span data-stu-id="b99eb-110">Original is the first settlement for a period interval and can be processed only once for a period interval.</span></span> <span data-ttu-id="b99eb-111">A legutóbbi korrekciók kiegyenlíti az áfatranzakciókat, amelyeket az eredeti verzió létrehozása után adtak fel.</span><span class="sxs-lookup"><span data-stu-id="b99eb-111">The latest corrections will settle sales tax transactions which have been posted after the original version has been created.</span></span>   
5. <span data-ttu-id="b99eb-112">A **Tranzakció dátuma** mezőben adjon meg egy dátumot.</span><span class="sxs-lookup"><span data-stu-id="b99eb-112">In the **Transaction date** field, enter a date.</span></span>
6. <span data-ttu-id="b99eb-113">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="b99eb-113">Click **OK**.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]