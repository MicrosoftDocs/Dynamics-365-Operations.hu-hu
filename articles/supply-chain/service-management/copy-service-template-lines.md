---
title: Szolgáltatási sablonok sorainak másolása
description: A sablonadatokat be lehet másolni szolgáltatási szerződésbe vagy szervizrendelésbe.
author: ShylaThompson
manager: AnnBe
ms.date: 10/11/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAAgreementTable, SMAServiceOrderTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 26b400d00a73c43ab74bb74b58dee833c792dad8
ms.sourcegitcommit: 0099fb24f5f40ff442020b488ef4171836c35c48
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/23/2019
ms.locfileid: "2653226"
---
# <a name="copy-service-templates-lines"></a><span data-ttu-id="fe9b6-103">Szolgáltatási sablonok sorainak másolása</span><span class="sxs-lookup"><span data-stu-id="fe9b6-103">Copy service templates lines</span></span> 

[!include [banner](../includes/banner.md)]

<span data-ttu-id="fe9b6-104">A sablonadatokat be lehet másolni szolgáltatási szerződésbe vagy szervizrendelésbe.</span><span class="sxs-lookup"><span data-stu-id="fe9b6-104">Template information can be copied to either a service agreement or a service order.</span></span>

## <a name="copy-service-template-lines-into-a-service-agreement"></a><span data-ttu-id="fe9b6-105">Szolgáltatássablon sorainak másolása szolgáltatási szerződésbe</span><span class="sxs-lookup"><span data-stu-id="fe9b6-105">Copy service template lines into a service agreement</span></span>

1. <span data-ttu-id="fe9b6-106">Kattintson a **Szolgáltatási szerződések** pontra.</span><span class="sxs-lookup"><span data-stu-id="fe9b6-106">Click **Service agreements**.</span></span>
2. <span data-ttu-id="fe9b6-107">Kattintson duplán a szolgáltatási szerződésre a **Szolgáltatási szerződések** képernyő megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="fe9b6-107">Double-click a service agreement to open the **Service agreements** page.</span></span>
3. <span data-ttu-id="fe9b6-108">Kattintson a **Sablonsorok** lehetőségre a **Szolgáltatási sablon sorainak másolása** lap megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="fe9b6-108">Click **Template lines** to open the **Copy service template lines** page.</span></span>
4. <span data-ttu-id="fe9b6-109">A **Fa ellenőrzése** lapon bontsa ki a fát, keresse meg azt a sablont, amely a szolgáltatási szerződésbe másolni kívánt összes sort tartalmazza, és jelölje ki a szolgáltatássablont.</span><span class="sxs-lookup"><span data-stu-id="fe9b6-109">On the **Tree control** tab, expand the tree, find the template that contains the lines that you want to copy to the service agreement, and then select the service template.</span></span>
5. <span data-ttu-id="fe9b6-110">Jelölje be a **Sorok** lapon azoknak a szolgáltatásisablon-soroknak a **Kijelölés** jelölőnégyzetét, amelyeket másolni szeretne.</span><span class="sxs-lookup"><span data-stu-id="fe9b6-110">On the **Lines** tab, select the **Select** check box for the service template lines that you want to copy.</span></span>
6. <span data-ttu-id="fe9b6-111">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="fe9b6-111">Click **OK**.</span></span>
7. <span data-ttu-id="fe9b6-112">A módosítások mentéséhez zárja be a lapokat.</span><span class="sxs-lookup"><span data-stu-id="fe9b6-112">Close the pages to save your changes.</span></span>

<span data-ttu-id="fe9b6-113">A szolgáltatássablon sorait a program ekkor a kapcsolt szolgáltatási objektummal és szervizfeladat-kapcsolatokkal együtt a szolgáltatási szerződésbe másolja.</span><span class="sxs-lookup"><span data-stu-id="fe9b6-113">The service template lines are now copied to the service agreement, together with the attached service object and service task relations.</span></span>

## <a name="copy-service-template-lines-into-a-service-order"></a><span data-ttu-id="fe9b6-114">Szolgáltatássablon sorainak másolása szervizrendelésbe</span><span class="sxs-lookup"><span data-stu-id="fe9b6-114">Copy service template lines into a service order</span></span>

1. <span data-ttu-id="fe9b6-115">Kattintson a **Szervizrendelések** pontra.</span><span class="sxs-lookup"><span data-stu-id="fe9b6-115">Click **Service orders**.</span></span>
2. <span data-ttu-id="fe9b6-116">Kattintson duplán egy szolgáltatási rendelésre a **Szolgáltatási rendelések** lap megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="fe9b6-116">Double-click a service order to open the **Service orders** page.</span></span>
3. <span data-ttu-id="fe9b6-117">Kattintson a Másolás \> Sablonsorok másolása lehetőségre a **Szolgáltatási sablon sorainak másolása** lap megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="fe9b6-117">Click Copy \> Copy template lines to open the **Copy service template lines** page.</span></span>
4. <span data-ttu-id="fe9b6-118">A **Fa ellenőrzése** lapon bontsa ki a fát, keresse meg azt a sablont, amely a szolgáltatási rendelésbe másolni kívánt összes sort tartalmazza, és jelölje ki a szolgáltatássablont.</span><span class="sxs-lookup"><span data-stu-id="fe9b6-118">On the **Tree control** tab, expand the tree, find the template that contains the lines that you want to copy to the service order, and then select the service template.</span></span>
5. <span data-ttu-id="fe9b6-119">Jelölje be a **Sorok** lapon azoknak a szolgáltatásisablon-soroknak a **Kijelölés** jelölőnégyzetét, amelyeket másolni szeretne.</span><span class="sxs-lookup"><span data-stu-id="fe9b6-119">On the **Lines** tab, select the **Select** check box for the service template lines that you want to copy.</span></span>
6. <span data-ttu-id="fe9b6-120">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="fe9b6-120">Click **OK**.</span></span>
7. <span data-ttu-id="fe9b6-121">A módosítások mentéséhez zárja be a lapokat.</span><span class="sxs-lookup"><span data-stu-id="fe9b6-121">Close the pages to save your changes.</span></span>

<span data-ttu-id="fe9b6-122">A szolgáltatássablon sorait a program ekkor a kapcsolt szolgáltatási objektummal és szervizfeladat-kapcsolatokkal együtt az új szervizrendelésbe másolja.</span><span class="sxs-lookup"><span data-stu-id="fe9b6-122">The service template lines are now copied to the new service order, together with the attached service object and service task relations.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="fe9b6-123">Kapcsolódó témakörök</span><span class="sxs-lookup"><span data-stu-id="fe9b6-123">Related topics</span></span>

[<span data-ttu-id="fe9b6-124">Szolgáltatási sablonok</span><span class="sxs-lookup"><span data-stu-id="fe9b6-124">Service templates</span></span>](service-template.md)


