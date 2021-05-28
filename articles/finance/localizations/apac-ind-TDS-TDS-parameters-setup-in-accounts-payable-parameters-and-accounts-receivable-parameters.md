---
title: TDS-paraméterek beállítása Kötelezettségek és Kinnlevőségek esetében
description: Ez a témakör bemutatja, hogyan lehet beállítani paramétereket a Kötelezettségek és Kinnlevőségek között a forrásnál levont adó (TDS) levonások támogatásához.
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
ms.openlocfilehash: 4540cdfff2362d8fb7cc2b4cccf9c340be9750ce
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023298"
---
# <a name="set-tds-parameters-in-accounts-payable-and-accounts-receivable"></a><span data-ttu-id="af56b-103">TDS-paraméterek beállítása Kötelezettségek és Kinnlevőségek esetében</span><span class="sxs-lookup"><span data-stu-id="af56b-103">Set TDS parameters in Accounts payable and Accounts receivable</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="af56b-104">Ez a témakör bemutatja, hogyan lehet beállítani paramétereket a Kötelezettségek és Kinnlevőségek között a forrásnál levont adó (TDS) levonások támogatásához.</span><span class="sxs-lookup"><span data-stu-id="af56b-104">This topic explains how to set parameters in Accounts payable and Accounts receivable to support Tax Deducted at Source (TDS) deductions.</span></span>

1. <span data-ttu-id="af56b-105">Lépjen az **Adó \> Beállítások \> Paraméterek \> Kintlévőségek paraméterei** helyre.</span><span class="sxs-lookup"><span data-stu-id="af56b-105">Go to **Tax \> Setup \> Parameters \> Accounts receivable parameters**.</span></span>
2. <span data-ttu-id="af56b-106">A **Frissítések** lapon válassza a **Rendeléssorok frissítése** lehetőséget a **Rendeléssorok frissítése** párbeszédpanel megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="af56b-106">On the **Updates** tab, select **Update order lines** to open the **Update order lines** dialog box.</span></span>
3. <span data-ttu-id="af56b-107">A **TDS csoport** szakasz **TDS csoport frissítése** mezőjében adja meg a sor szintjén a TDS-csoport frissítéséhez használni kívánt módszert.</span><span class="sxs-lookup"><span data-stu-id="af56b-107">In the **TDS group** section, in the **Updating TDS group** field, specify the method to use to update the TDS group at the line level.</span></span> <span data-ttu-id="af56b-108">Ez a beállítás akkor használatos, amikor a TDS-csoport frissül a rendelés fejlécében.</span><span class="sxs-lookup"><span data-stu-id="af56b-108">This setting is used when the TDS group is updated on an order header.</span></span> <span data-ttu-id="af56b-109">Ehhez a következő lehetőségek állnak rendelkezésre:</span><span class="sxs-lookup"><span data-stu-id="af56b-109">The following options are available:</span></span>

    - <span data-ttu-id="af56b-110">**Soha** – A rendelésfejlécben való frissítéskor a rendeléssorok TDS-csoportja nem frissül.</span><span class="sxs-lookup"><span data-stu-id="af56b-110">**Never** – The TDS group isn't updated on the order lines when it's updated on the order header.</span></span>
    - <span data-ttu-id="af56b-111">**Mindig** – A rendelésfejlécben való frissítéskor a rendeléssorok TDS-csoportja automatikusan frissül.</span><span class="sxs-lookup"><span data-stu-id="af56b-111">**Always** – The TDS group is automatically updated on the order lines when it's updated on the order header.</span></span>
    - <span data-ttu-id="af56b-112">**Kérdés** – A felhasználók egy üzenetet kapnak, amely kéri őket a rendeléssorok TDS-csoportjának frissítésére.</span><span class="sxs-lookup"><span data-stu-id="af56b-112">**Prompt** – Users receive a message that prompts them to update the TDS group on the order lines.</span></span>
4. <span data-ttu-id="af56b-113">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="af56b-113">Select **OK**.</span></span>

    <span data-ttu-id="af56b-114">[![Rendeléssorok frissítése párbeszédpanel](./media/apac-ind-TDS-26.PNG)](./media/apac-ind-TDS-26.PNG)</span><span class="sxs-lookup"><span data-stu-id="af56b-114">[![Update order lines dialog box](./media/apac-ind-TDS-26.PNG)](./media/apac-ind-TDS-26.PNG)</span></span>

5. <span data-ttu-id="af56b-115">Lépjen az **Adó \> Beállítások \> Paraméterek \> Kötelezettségek paraméterei** helyre.</span><span class="sxs-lookup"><span data-stu-id="af56b-115">Go to **Tax \> Setup \> Parameters \> Accounts payable parameters**.</span></span>
6. <span data-ttu-id="af56b-116">Az **Általános** lap **Felosztás szállítási adatok szerint** gyorslapján állítsa **Igen** beállításra a **Termékbevételezés** lehetőséget különböző szállítási címekkel és adószámlaszámmal (TAN) rendelkező termékbevételezés felosztásához.</span><span class="sxs-lookup"><span data-stu-id="af56b-116">On the **General** tab, on the **Split based on delivery information** FastTab, set the **Product receipt** option to **Yes** to post and split a product receipt that has different delivery addresses and tax account numbers (TANs).</span></span> <span data-ttu-id="af56b-117">Ha ez a beállítás **Nem**, nem lehet olyan beszerzési csomagjegyzéket sem elküldeni, amely más szállítási címekkel és TAN-ekkel rendelkezik.</span><span class="sxs-lookup"><span data-stu-id="af56b-117">If this option is set to **No**, you can't post a purchase packing slip that has different delivery addresses and TANs.</span></span>
7. <span data-ttu-id="af56b-118">A **Számla** beállítás **Igen** étékre állításával különböző szállítási címekkel rendelkező beszerzési számlát lehet feladni és felosztani.</span><span class="sxs-lookup"><span data-stu-id="af56b-118">Set the **Invoice** option to **Yes** to post and split a purchase invoice that has different delivery addresses and TANs.</span></span>

    <span data-ttu-id="af56b-119">[![Felosztás a szállítási adatok alapján gyorslap](./media/apac-ind-TDS-25.png)](./media/apac-ind-TDS-25.png)</span><span class="sxs-lookup"><span data-stu-id="af56b-119">[![Split based on delivery information FastTab](./media/apac-ind-TDS-25.png)](./media/apac-ind-TDS-25.png)</span></span>

8. <span data-ttu-id="af56b-120">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="af56b-120">Close the page.</span></span>
