---
title: Adóelőleg-hatóságok beállítása a TDS adótípusokhoz
description: Ez a témakör elmagyarázza, hogyan kell hatóságokat beállítani a forrásnál levont adóhoz (TDS).
author: kailiang
ms.date: 02/12/2021
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
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: 5375363a9b1383a83e80fc3c4b841780adab4172
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023290"
---
# <a name="set-up-withholding-tax-authorities-for-the-tds-tax-type"></a><span data-ttu-id="3b2a6-103">Adóelőleg-hatóságok beállítása a TDS adótípusokhoz</span><span class="sxs-lookup"><span data-stu-id="3b2a6-103">Set up withholding tax authorities for the TDS tax type</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="3b2a6-104">Ez a témakör elmagyarázza, hogyan kell hatóságokat beállítani a forrásnál levont adóhoz (TDS).</span><span class="sxs-lookup"><span data-stu-id="3b2a6-104">This topic explains how to set up Tax Deducted at Source (TDS) authorities.</span></span>

1. <span data-ttu-id="3b2a6-105">Ugorjon az **Adó \> Közvetett adók \> Adóelőleg-hatóságok** helyre.</span><span class="sxs-lookup"><span data-stu-id="3b2a6-105">Go to **Tax \> Indirect taxes \> Withholding tax authorities**.</span></span>

    <span data-ttu-id="3b2a6-106">[![Adóelőleg-hatóságok oldal](./media/apac-ind-TDS-12.png)](./media/apac-ind-TDS-12.png)</span><span class="sxs-lookup"><span data-stu-id="3b2a6-106">[![Withholding tax authorities page](./media/apac-ind-TDS-12.png)](./media/apac-ind-TDS-12.png)</span></span>

2. <span data-ttu-id="3b2a6-107">Az **Adótípus** mezőben válassza ki a **TDS** lehetőséget a TDS adótípus adóelőleg-hatóságok beállításához.</span><span class="sxs-lookup"><span data-stu-id="3b2a6-107">In the **Tax type** field, select **TDS** to set up withholding tax authorities for the TDS tax type.</span></span>
3. <span data-ttu-id="3b2a6-108">Jelölje be a műveleti ablakban az **Új** lehetőséget az új sor létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="3b2a6-108">On the Action Pane, select **New** to create a line.</span></span>
4. <span data-ttu-id="3b2a6-109">Az **Adóelőleg-hatóság** mezőben adjon nevet a TDS-hatóságnak.</span><span class="sxs-lookup"><span data-stu-id="3b2a6-109">In the **Withholding tax authority** field, enter a name for the TDS authority.</span></span>
5. <span data-ttu-id="3b2a6-110">Adjon meg egy leírást a **Leírás** mezőben.</span><span class="sxs-lookup"><span data-stu-id="3b2a6-110">In the **Description** field, enter a description.</span></span>
6. <span data-ttu-id="3b2a6-111">Az **Általános** gyorslap **Szállítói számla** mezőjében válassza ki az TDS-hatósághoz tartozó szállítói számlát.</span><span class="sxs-lookup"><span data-stu-id="3b2a6-111">On the **General** FastTab, in the **Vendor account** field, select the vendor account for the TDS authority.</span></span>

    > [!NOTE]
    > <span data-ttu-id="3b2a6-112">Meg kell határoznia annak a banknak a nevét, ahol a TDS-hatósági szállítónak járó pénzeszközöket letétbe helyezik.</span><span class="sxs-lookup"><span data-stu-id="3b2a6-112">You must define the name of the bank where funds that are owed to the TDS authority vendor will be deposited.</span></span> <span data-ttu-id="3b2a6-113">A bank neve a **Bankszámlák** oldalon van meg definiálva (**Kötelezettségek \> Minden szállító \> Szállítója \> Beállítások \> Bankszámlákat**).</span><span class="sxs-lookup"><span data-stu-id="3b2a6-113">The bank's name is defined on the **Bank accounts** page (**Accounts payable \> All vendors \> Vendor \> Set up \> Bank accounts**).</span></span>

7. <span data-ttu-id="3b2a6-114">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="3b2a6-114">Close the page.</span></span>
