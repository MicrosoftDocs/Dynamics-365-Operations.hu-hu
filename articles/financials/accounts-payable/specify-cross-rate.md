---
title: A keresztárfolyam megadása
description: Ez a témakör általános tájékoztatást tartalmaz a Microsoft Dynamics 365 for Finance and Operations keresztárfolyamaival kapcsolatban.
author: abruer
manager: AnnBe
ms.date: 05/16/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 112f77738b33aae94babe0cf8e9e61ff2ea3d004
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2019
ms.locfileid: "320236"
---
# <a name="specify-the-cross-rate"></a><span data-ttu-id="5e109-103">A keresztárfolyam megadása</span><span class="sxs-lookup"><span data-stu-id="5e109-103">Specify the cross rate</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5e109-104">Ez a témakör bemutatja a keresztárfolyam, és a keresztárfolyam megadása, amikor egy kifizetést számlát célját.</span><span class="sxs-lookup"><span data-stu-id="5e109-104">This topic explains the purpose of a cross rate, and how to specify the cross rate when you settle a payment with an invoice.</span></span> <span data-ttu-id="5e109-105">A keresztárfolyam akkor kell használni, amikor az összes, a következő feltételek vonatkoznak:</span><span class="sxs-lookup"><span data-stu-id="5e109-105">Use a cross rate when all of the following criteria apply:</span></span> 
-   <span data-ttu-id="5e109-106">A kifizetési számlát egyenlít ki.</span><span class="sxs-lookup"><span data-stu-id="5e109-106">You are settling a payment with an invoice.</span></span> 
-   <span data-ttu-id="5e109-107">A számlasor és a számlasor használja a különféle pénznemekben.</span><span class="sxs-lookup"><span data-stu-id="5e109-107">The payment line and the invoice line use different currencies.</span></span> 
-   <span data-ttu-id="5e109-108">Sem pénzneme nem az alapértelmezett pénznemben.</span><span class="sxs-lookup"><span data-stu-id="5e109-108">Neither currency is the accounting currency.</span></span> 

<span data-ttu-id="5e109-109">A keresztárfolyam nem használatos a fizetési tranzakció devizaátváltásának kiszámítására a kifizetés könyvelési pénznemhez.</span><span class="sxs-lookup"><span data-stu-id="5e109-109">The cross rate is not used to calculate the payment transaction currency translation to the payment accounting currency.</span></span> <span data-ttu-id="5e109-110">Az árfolyamok beolvasására az árfolyamtáblákból azért kerül sor, hogy kiszámítsák a fizetési tranzakció pénznemének összegét és a fizetés könyvelési pénznemének összegét.</span><span class="sxs-lookup"><span data-stu-id="5e109-110">Instead, the exchange rates from the exchange rate tables are retrieved to calculate the value of the payment transaction currency amount and the payment accounting currency amount.</span></span> 

<span data-ttu-id="5e109-111">Például a könyvelési pénznemben USD, számla pénzneme CAD, pedig a kifizetés pénznemében EUR.</span><span class="sxs-lookup"><span data-stu-id="5e109-111">For example, the accounting currency is USD, the invoice currency is CAD, and the payment currency is EUR.</span></span> <span data-ttu-id="5e109-112">A keresztárfolyam segítségével fordításához CAD és euró közötti közvetlen átváltási árfolyam megadása, és nem kell lefordítani USD keresztül.</span><span class="sxs-lookup"><span data-stu-id="5e109-112">The cross rate lets you enter an exchange rate to translate directly between CAD and EUR, and not have to translate through USD.</span></span> <span data-ttu-id="5e109-113">Amikor kiválaszt egy számlát és egy elsődleges kifizetést, a számla sorához keresztárfolyamot adhat meg.</span><span class="sxs-lookup"><span data-stu-id="5e109-113">When you select an invoice and a primary payment, you can enter a cross rate for the invoice line.</span></span> <span data-ttu-id="5e109-114">A keresztárfolyam az ilyen tranzakciók pénznemeinek a kiegyenlítés napján érvényes átváltási árfolyama.</span><span class="sxs-lookup"><span data-stu-id="5e109-114">The cross rate is the exchange rate between the currencies for those transactions, as of the settlement date.</span></span>

1.  <span data-ttu-id="5e109-115">Lépjen az alábbiak közül valamelyik lapra:</span><span class="sxs-lookup"><span data-stu-id="5e109-115">Go to one of the following pages:</span></span>
- <span data-ttu-id="5e109-116">**Kinnlevőségek > Közös > Vevők > Minden vevő**</span><span class="sxs-lookup"><span data-stu-id="5e109-116">**Accounts receivable > Common > Customers > All customers**</span></span> 
- <span data-ttu-id="5e109-117">**Kötelezettségek > Közös > Szállítók > Minden szállító**</span><span class="sxs-lookup"><span data-stu-id="5e109-117">**Accounts payable > Common > Vendors > All vendors**</span></span> 
- <span data-ttu-id="5e109-118">**Beszerzés és forrás > Közös > Szállítók > Minden szállító**</span><span class="sxs-lookup"><span data-stu-id="5e109-118">**Procurement and sourcing > Common > Vendors > All vendors**</span></span>
2.  <span data-ttu-id="5e109-119">Válassza ki a vevőt vagy szállítót, amelynek nyitott tranzakcióit elszámolja.</span><span class="sxs-lookup"><span data-stu-id="5e109-119">Select the customer or vendor whose open transactions you are settling.</span></span> 
3.  <span data-ttu-id="5e109-120">Egy adott vevő esetében a **Minden vevő** listaoldalon lépjen ide: **Beszedés > Nyitott tranzakciók kiegyenlítése**.</span><span class="sxs-lookup"><span data-stu-id="5e109-120">For a customer, on the **All customers** list page, go to **Collect > Settle open transactions**.</span></span> <span data-ttu-id="5e109-121">Egy adott szállító esetében a **Minden szállító** listaoldalon lépjen ide: **Számla > Nyitott tranzakciók kiegyenlítése**.</span><span class="sxs-lookup"><span data-stu-id="5e109-121">For a vendor, on the **All vendors** list page, go to **Invoice > Settle open transactions**.</span></span> 
4.  <span data-ttu-id="5e109-122">Válassza ki az elsődleges kifizetést jelentő tranzakciót, majd kattintson a **Kifizetés megjelölése** gombra.</span><span class="sxs-lookup"><span data-stu-id="5e109-122">Select the transaction that is the primary payment, and then click **Mark payment**.</span></span> <span data-ttu-id="5e109-123">A **Megjelölés** oszlopban található jelölőnégyzet be lesz jelölve, és egy információs ikon jelenik meg az **Elsődleges kifizetés** oszlopban.</span><span class="sxs-lookup"><span data-stu-id="5e109-123">The check box in the **Mark** column is selected, and an information icon is shown in the **Primary payment** column.</span></span> 
5.  <span data-ttu-id="5e109-124">A **Keresztárfolyam** mezőbe írja be a számla és a kifizetés pénzneme közötti átváltási árfolyam szorzóját a kifizetés napján érvényes értékkel.</span><span class="sxs-lookup"><span data-stu-id="5e109-124">In the **Cross rate** field, enter the exchange rate between the invoice currency and the payment currency, as of the settlement date.</span></span> 
