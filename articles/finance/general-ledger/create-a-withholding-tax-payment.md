---
title: Adóelőleg-fizetés létrehozása
description: Az adóelőleg-kiegyenlítési és -feladási munkaeljárás kiegyenlíti a Kötelezettségek adóelőleg-egyenlegeit az adóelőleg-számlákon, és átvezeti az adóelőleg-elszámolási számlára az adott időszakra. Ez a témakör az adóelőleg-fizetés beállításának lépéseit mutatja be.
author: roschlom
manager: AnnBe
ms.date: 01/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2020-01-12
ms.dyn365.ops.version: AX 10.0.16
ms.openlocfilehash: e522711340b663bd849825b3d4dd2b7e78e4737c
ms.sourcegitcommit: 630a0b3f800f36ced49b79156dd52132904fef75
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/25/2021
ms.locfileid: "5060747"
---
# <a name="create-a-withholding-tax-payment"></a><span data-ttu-id="45d2d-104">Adóelőleg-fizetés létrehozása</span><span class="sxs-lookup"><span data-stu-id="45d2d-104">Create a withholding tax payment</span></span>

<span data-ttu-id="45d2d-105">Az adóelőleg-kiegyenlítési és -feladási munkaeljárás kiegyenlíti a Kötelezettségek adóelőleg-egyenlegeit az adóelőleg-számlákon, és átvezeti az adóelőleg-elszámolási számlára az adott időszakra.</span><span class="sxs-lookup"><span data-stu-id="45d2d-105">The Withholding tax payment job procedure settles withholding tax balances from Accounts payable on withholding tax accounts, and offsets them to the withholding tax settlement account for a given period.</span></span> <span data-ttu-id="45d2d-106">Ez a témakör az adóelőleg-fizetés beállításának lépéseit mutatja be.</span><span class="sxs-lookup"><span data-stu-id="45d2d-106">This topic lists the steps for setting up a withholding tax payment.</span></span>

> [!NOTE] 
> <span data-ttu-id="45d2d-107">A program az adóelőleg-ellenszámlát (a kinnlevőségekből) nem veszi figyelembe az adóelőleg-fizetés kiszámítása során.</span><span class="sxs-lookup"><span data-stu-id="45d2d-107">Withholding tax offset (from accounts receivable) is not taken into account when a withholding tax payment is calculated.</span></span>

1. <span data-ttu-id="45d2d-108">Ugorjon a **Navigációs ablaktábla > Modulok > Adó > Bevallások > Adóelőleg > Adóelőleg-kifizetés elemre**.</span><span class="sxs-lookup"><span data-stu-id="45d2d-108">Go to **Navigation pane > Modules > Tax > Declarations > Withholding tax > Withholding tax payment**.</span></span>
2. <span data-ttu-id="45d2d-109">A **Kiegyenlítési időszak** mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="45d2d-109">In the **Settlement period** field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="45d2d-110">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="45d2d-110">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="45d2d-111">Adjon meg egy dátumot a **Kezdő dátum** mezőben.</span><span class="sxs-lookup"><span data-stu-id="45d2d-111">In the **From date** field, enter a date.</span></span>
5. <span data-ttu-id="45d2d-112">A **Tranzakció dátuma** mezőben adjon meg egy dátumot.</span><span class="sxs-lookup"><span data-stu-id="45d2d-112">In the **Transaction date** field, enter a date.</span></span>
6. <span data-ttu-id="45d2d-113">A **Frissítés** lehetőség kiválasztásával adóelőleg-fizetési bizonylatot adhat fel az adóelőleg-elszámolási számlára.</span><span class="sxs-lookup"><span data-stu-id="45d2d-113">Select **Update** to post withholding tax payment voucher to the withholding tax settlement account.</span></span>
7. <span data-ttu-id="45d2d-114">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="45d2d-114">Click **OK**.</span></span>

![Adóelőleg-fizetés paraméterei](media/withholding-tax-payment.png)
