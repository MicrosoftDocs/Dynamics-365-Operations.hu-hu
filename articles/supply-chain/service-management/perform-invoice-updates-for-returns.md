---
title: "Visszárura vonatkozó számlafrissítés végrehajtása"
description: "A rendszernek ezek a funkciói támogatják a szervezet azon üzleti folyamatait, amelyek során ugyanaz a személy egyszerre számlázza a visszárurendeléseket és az értékesítési rendeléseket."
author: ShylaThompson
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: d9747ba144d56c9410846769e5465372c89ea111
ms.openlocfilehash: 2f962641f7fdae18a360567d6f37348fabbfc302
ms.contentlocale: hu-hu
ms.lasthandoff: 08/07/2018

---


# <a name="perform-invoice-updates-for-returns"></a><span data-ttu-id="08333-103">Visszárura vonatkozó számlafrissítés végrehajtása</span><span class="sxs-lookup"><span data-stu-id="08333-103">Perform invoice updates for returns</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="08333-104">A visszárurendelés olyan értékesítési rendeléstípus, amelynek cikkei visszárurendelésként vannak megjelölve.</span><span class="sxs-lookup"><span data-stu-id="08333-104">A return order is a type of sales order that is marked as a returned order.</span></span> <span data-ttu-id="08333-105">Emiatt a **Minden értékesítési rendelés** listaoldalt használja a rendszer a visszárurendelések számláinak létrehozásához a **Visszárurendelések** képernyő helyett.</span><span class="sxs-lookup"><span data-stu-id="08333-105">Therefore, the **All sales orders** list page is used to generate invoices for return orders instead of the **Return orders** form.</span></span> <span data-ttu-id="08333-106">A rendszernek ezek a funkciói támogatják a szervezet azon üzleti folyamatait, amelyek során ugyanaz a személy egyszerre számlázza a visszárurendeléseket és az értékesítési rendeléseket.</span><span class="sxs-lookup"><span data-stu-id="08333-106">This functionality supports the business processes of organizations that choose to have return orders and sales orders invoiced at the same time and by the same person.</span></span>

<span data-ttu-id="08333-107">Mivel a visszaküldött cikk számlája negatív összeg, ezt jóváírásnak nevezik.</span><span class="sxs-lookup"><span data-stu-id="08333-107">Because the invoice for a returned item is for a negative amount, it is called a credit note.</span></span>

<span data-ttu-id="08333-108">Ha kötegelten végzi a számlafrissítést, akkor a **Visszárurendelés** típusú értékesítési rendelés visszárusorának **Bevételezve** állapotban kell lennie, ami azt jelzi, hogy a rendelés csomagjegyzékét frissítették.</span><span class="sxs-lookup"><span data-stu-id="08333-108">When you set up the invoice update for batch processing, the sales order of type **Returned order** must have a return line status of **Received**, which indicates that the order's packing slip has been updated.</span></span>

## <a name="post-an-invoice-for-a-return-order"></a><span data-ttu-id="08333-109">Számla feladása egy visszárurendeléshez</span><span class="sxs-lookup"><span data-stu-id="08333-109">Post an invoice for a return order</span></span>

1.  <span data-ttu-id="08333-110">Kattintson a következőkre: **Kinnlevőségek** \> **Közös** \> **Értékesítési rendelések** \> **Minden értékesítési rendelés**.</span><span class="sxs-lookup"><span data-stu-id="08333-110">Click **Accounts receivable** \> **Common** \> **Sales orders** \> **All sales orders**.</span></span>

2.  <span data-ttu-id="08333-111">Válasszon egy olyan értékesítési rendelést, amelyhez **Visszaküldött rendelés** jelenik meg a **Rendelés típusa** mezőben.</span><span class="sxs-lookup"><span data-stu-id="08333-111">Select a sales order for which **Returned order** is displayed in the **Order type** field.</span></span>

3.  <span data-ttu-id="08333-112">A Műveleti ablaktábla **Számla** lapján a **Létrehozás** csoportban kattintson a **Számla** elemre.</span><span class="sxs-lookup"><span data-stu-id="08333-112">On the Action Pane, on the **Invoice** tab, in the **Generate** group, click **Invoice**.</span></span>

4.  <span data-ttu-id="08333-113">A **Paraméterek** lapon jelölje be a **Feladás** jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="08333-113">On the **Parameters** tab, select the **Posting** check box.</span></span>

5.  <span data-ttu-id="08333-114">Ellenőrizze a képernyőn lévő információkat, és végezze el a szükséges változtatásokat.</span><span class="sxs-lookup"><span data-stu-id="08333-114">Review information in the form and make any changes that are needed.</span></span>

6.  <span data-ttu-id="08333-115">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="08333-115">Click **OK**.</span></span> <span data-ttu-id="08333-116">A jóváírás feladásra került.</span><span class="sxs-lookup"><span data-stu-id="08333-116">The credit note is posted.</span></span>

## <a name="see-also"></a><span data-ttu-id="08333-117">Lásd még</span><span class="sxs-lookup"><span data-stu-id="08333-117">See also</span></span>

[<span data-ttu-id="08333-118">Visszárura vonatkozó csomagjegyzék-frissítés</span><span class="sxs-lookup"><span data-stu-id="08333-118">Packing slip updates for returns</span></span>](packing-slip-updates-returns.md)

  



