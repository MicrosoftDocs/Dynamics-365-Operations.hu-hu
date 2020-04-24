---
title: Szervizrendelések automatikus létrehozása
description: Szervizrendeléseket lehet létrehozni egy vagy több szolgáltatási szerződéshez.
author: ShylaThompson
manager: tfehr
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e4ba2cf115faacda14e25838a488fc54c53f48f3
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/02/2020
ms.locfileid: "3202721"
---
# <a name="create-service-orders-automatically"></a><span data-ttu-id="f3c08-103">Szervizrendelések automatikus létrehozása</span><span class="sxs-lookup"><span data-stu-id="f3c08-103">Create service orders automatically</span></span>    

[!include [banner](../includes/banner.md)]


<span data-ttu-id="f3c08-104">Szervizrendeléseket lehet létrehozni egy vagy több szolgáltatási szerződéshez.</span><span class="sxs-lookup"><span data-stu-id="f3c08-104">You can create service orders for one service agreement or for several service agreements.</span></span> <span data-ttu-id="f3c08-105">A létrehozásuk után a szervizrendeléseket a **Szervizrendelések** képernyőn lehet megtekinteni.</span><span class="sxs-lookup"><span data-stu-id="f3c08-105">When they are created, you can view your service orders in the **Service orders** form.</span></span>

<span data-ttu-id="f3c08-106">A szervizrendelések csak a szolgáltatási szerződésben érvényes időszakra vonatkozóan jönnek létre.</span><span class="sxs-lookup"><span data-stu-id="f3c08-106">Service orders are created only for the valid period of the service agreement.</span></span> <span data-ttu-id="f3c08-107">Ha a **Szervizrendelések létrehozása** képernyőn megadott intervallum a szolgáltatási szerződés kezdő dátuma elé vagy záró dátuma utánra esik, akkor a szervizrendelések csak az intervallum azon részéhez jönnek létre, amely a szolgáltatási szerződés időszakára esik.</span><span class="sxs-lookup"><span data-stu-id="f3c08-107">If the interval that you specify in the **Create service orders** form is before the starting date or after the ending date of the service agreement, service orders are created only for the part of the interval that is within the service agreement dates.</span></span>

<span data-ttu-id="f3c08-108">Ha manuálisan vagy automatikusan szervizrendeléseket hoz létre a szolgáltatásiszerződés-sorból, akkor a szervizrendelésnek a sor kezdő és záró dátuma által meghatározott időintervallumban kell lennie, kivéve ha a sorban nincs megadva záró dátum.</span><span class="sxs-lookup"><span data-stu-id="f3c08-108">When you create service orders manually or automatically from the service agreement line, the service order must be in the time interval that is defined by the starting and ending dates for the line, unless you do not specify an ending date on the line.</span></span>

## <a name="create-service-orders-automatically-for-a-service-agreement"></a><span data-ttu-id="f3c08-109">Szervizrendelések automatikus létrehozása a szolgáltatási szerződésekhez</span><span class="sxs-lookup"><span data-stu-id="f3c08-109">Create service orders automatically for a service agreement</span></span>

1.  <span data-ttu-id="f3c08-110">Kattintson a **Szolgáltatáskezelés** \> **Közös** \> **Szolgáltatási szerződések** \> **Szolgáltatási szerződések** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="f3c08-110">Click **Service management** \> **Common** \> **Service agreements** \> **Service agreements**.</span></span>

2.  <span data-ttu-id="f3c08-111">Válasszon ki egy szolgáltatási szerződést.</span><span class="sxs-lookup"><span data-stu-id="f3c08-111">Select a service agreement.</span></span>

3.  <span data-ttu-id="f3c08-112">Kattintson a **Szállítása** fülre, majd a **Tervezett szervizrendelések** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="f3c08-112">Click the **Deliver** tab, and then click **Planned service orders**.</span></span>

4.  <span data-ttu-id="f3c08-113">A **Kezdő dátum** és a **Záró dátum** mező értékeinek a beállításával határozza meg a szolgáltatás időszakát.</span><span class="sxs-lookup"><span data-stu-id="f3c08-113">Specify dates in the **From date** and **To date** fields to define the service period.</span></span>

5.  <span data-ttu-id="f3c08-114">Jelölje be az **Információs napló megjelenítése** jelölőnégyzetet a létrehozott szervizrendelések listájának a megjelenítése érdekében.</span><span class="sxs-lookup"><span data-stu-id="f3c08-114">Select the **Show Infolog** check box to display a list of the service orders that are created.</span></span>

6.  <span data-ttu-id="f3c08-115">Válassza ki a tranzakciótípusokat a **Tranzakciótípusok szerepeltetése** mezőcsoportban.</span><span class="sxs-lookup"><span data-stu-id="f3c08-115">Select transaction types in the **Include transaction types** field group.</span></span> <span data-ttu-id="f3c08-116">A tranzakciótípusok a szolgáltatási szerződésben létrehozott soroknak felelnek meg, és minden kiválasztott tranzakciótípus több szervizrendelést hoz létre, a szolgáltatási megállapodás sorában beállított szolgáltatási intervallumtól függően.</span><span class="sxs-lookup"><span data-stu-id="f3c08-116">The transaction types represent the lines that are created in the service agreement, and each transaction type that you select generates several service orders, depending on the service interval that is specified on the service agreement line.</span></span>

7.  <span data-ttu-id="f3c08-117">Jelölje be a **Folytonos** jelölőnégyzetet, ha minden olyan szervizrendelést létre szeretne hozni, amely hiányzik a szervizrendelések egy folytonos sorozatából.</span><span class="sxs-lookup"><span data-stu-id="f3c08-117">To create any service orders that are missing from continuous series of service orders, select the **Continuous** check box.</span></span>

8.  <span data-ttu-id="f3c08-118">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="f3c08-118">Click **OK**.</span></span>

## <a name="create-service-orders-automatically-for-several-service-agreements"></a><span data-ttu-id="f3c08-119">Szervizrendelések automatikus létrehozása több szolgáltatási megállapodáshoz</span><span class="sxs-lookup"><span data-stu-id="f3c08-119">Create service orders automatically for several service agreements</span></span>

1.  <span data-ttu-id="f3c08-120">Kattintson a következőkre: **Szolgáltatáskezelés** \> **Rendszeres** \> **Szervizrendelések** \> **Szervizrendelések létrehozása**.</span><span class="sxs-lookup"><span data-stu-id="f3c08-120">Click **Service management** \> **Periodic** \> **Service orders** \> **Create service orders**.</span></span>

2.  <span data-ttu-id="f3c08-121">Kattintson a **Kiválasztás** lehetőségre ahhoz, hogy a szervizrendelések létrehozásához használt kritériumokat adjon hozzá vagy távolítson el.</span><span class="sxs-lookup"><span data-stu-id="f3c08-121">Click **Select** to make selections to add or remove criteria to use to create service orders.</span></span>

3.  <span data-ttu-id="f3c08-122">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="f3c08-122">Click **OK**.</span></span>

## <a name="see-also"></a><span data-ttu-id="f3c08-123">Lásd még</span><span class="sxs-lookup"><span data-stu-id="f3c08-123">See also</span></span>

[<span data-ttu-id="f3c08-124">Szervizrendelések</span><span class="sxs-lookup"><span data-stu-id="f3c08-124">Service orders</span></span>](service-orders.md)

[<span data-ttu-id="f3c08-125">Szervizrendelések automatikus létrehozása</span><span class="sxs-lookup"><span data-stu-id="f3c08-125">Automatically create service orders</span></span>](auto-create-service-orders.md)

  


