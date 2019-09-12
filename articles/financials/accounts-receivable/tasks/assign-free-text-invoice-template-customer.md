---
title: Szabadszöveges számlasablon hozzárendelése vevőhöz
description: A feladat bemutatja, hogyan kell szabadszöveges számlasablont vevőhöz hozzárendelni.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/12/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustTable, CustRecurrenceInvoice
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d9535a4678ea0c68227a54cf3c5d1b06b116a288
ms.sourcegitcommit: cbcf344b3b552acca56c3e27606eac7f2f124afe
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/22/2019
ms.locfileid: "1916346"
---
# <a name="assign-free-text-invoice-template-to-a-customer"></a><span data-ttu-id="57ecb-103">Szabadszöveges számlasablon hozzárendelése vevőhöz</span><span class="sxs-lookup"><span data-stu-id="57ecb-103">Assign free text invoice template to a customer</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="57ecb-104">A feladat bemutatja, hogyan kell szabadszöveges számlasablont vevőhöz hozzárendelni.</span><span class="sxs-lookup"><span data-stu-id="57ecb-104">This task demonstrates how to assign a free text invoice template to a customer.</span></span> <span data-ttu-id="57ecb-105">Ez a feladat az USMF bemutató vállalatot veszi alapul, és az a felhasználó használja, aki felelős a kintlévőségek számláinak kezeléséért és feldolgozásáért.</span><span class="sxs-lookup"><span data-stu-id="57ecb-105">This task uses the USMF demo company and is intended for the user who is responsible for managing and processing A/R invoices.</span></span>

1. <span data-ttu-id="57ecb-106">A **Navigációs ablaktáblán** ugorjon a **Modulok > Kintlévőségek > Ügyfelek > Minden ügyfél** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="57ecb-106">In the **Navigation pane**, go to **Modules > Accounts receivable > Customers > All customers**.</span></span>
2. <span data-ttu-id="57ecb-107">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="57ecb-107">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="57ecb-108">A **Művelet panelen** kattintson a **Számla** elemre.</span><span class="sxs-lookup"><span data-stu-id="57ecb-108">On the **Action Pane**, click **Invoice**.</span></span>
4. <span data-ttu-id="57ecb-109">Kattintson az **Ismétlődő számlák** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="57ecb-109">Click **Recurring invoices**.</span></span> <span data-ttu-id="57ecb-110">Ezen a lapon szabadszöveges számlasablonokat rendelhet hozzá a vevőkhöz, és megadhatja, hogy milyen gyakran történjen számlázás a vevő részére.</span><span class="sxs-lookup"><span data-stu-id="57ecb-110">Use this page to assign free text invoice templates to customers and specify how frequently invoices will be sent to the customer.</span></span>  
5. <span data-ttu-id="57ecb-111">Az **Új** gombra kattintva új sablont rendel a vevőhöz.</span><span class="sxs-lookup"><span data-stu-id="57ecb-111">Click **New** to assign a new template to the customer.</span></span>
6. <span data-ttu-id="57ecb-112">A **Sablon** mezőben válassza ki a szabadszöveges számlasablont, amelyet hozzá kíván rendelni a vevőhöz.</span><span class="sxs-lookup"><span data-stu-id="57ecb-112">In the **Template** field, select the free text invoice template you want to assign to the customer.</span></span>
7. <span data-ttu-id="57ecb-113">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="57ecb-113">In the list, find and select the desired record.</span></span>
8. <span data-ttu-id="57ecb-114">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="57ecb-114">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="57ecb-115">A **Számlázási kezdési dátum** mezőben adja meg azt a dátumot, amikor az első számla létrejön.</span><span class="sxs-lookup"><span data-stu-id="57ecb-115">In the **Billing start date** field, enter the date when the first invoice will be generated.</span></span>
10. <span data-ttu-id="57ecb-116">Az **Ismétlődés vége** szakaszban írjon be egy ismétlődő záró dátumot.</span><span class="sxs-lookup"><span data-stu-id="57ecb-116">In the **Recurrence end** section, enter a recurring end date.</span></span>  
    * <span data-ttu-id="57ecb-117">Válassza ki a következők valamelyikét: Nincs záró dátum – A számlázás folyamatosan történik, amíg a sablont el nem távolítja a vevői fiókból.</span><span class="sxs-lookup"><span data-stu-id="57ecb-117">Select one of the following: No end date – Invoices will be generated indefinitely until the template is removed from the customer account.</span></span>
    * <span data-ttu-id="57ecb-118">Számlázás záró dátuma – Válassza ezt az opciót, ha szeretné megadni, mi az a legutolsó dátum, amikor még generálható számla.</span><span class="sxs-lookup"><span data-stu-id="57ecb-118">Billing end date – Select this option and enter the last date that the invoice can be generated.</span></span>  
11. <span data-ttu-id="57ecb-119">A **Maximális halmozott összeg** mezőbe írja be azt a maximális halmozott összeget, amely után a számla generálása leáll.</span><span class="sxs-lookup"><span data-stu-id="57ecb-119">In the **Maximum cummulative amount** field, enter the maximum cumulative amount after which invoice generation will stop.</span></span> <span data-ttu-id="57ecb-120">Adja meg a maximális halmozott összeget, amely a kiválasztott sablon használatával elérhető.</span><span class="sxs-lookup"><span data-stu-id="57ecb-120">Enter the maximum cumulative amount that can be reached using the selected template.</span></span> <span data-ttu-id="57ecb-121">Ha például 1000,00-t ad meg és havonta 100,00-ról állít ki számlát, a tizedik számla után nem jön létre több számla.</span><span class="sxs-lookup"><span data-stu-id="57ecb-121">For example, if you enter 1,000.00 and generate monthly invoices for 100.00 each, invoices will stop generating after the tenth invoice is generated.</span></span>  
12. <span data-ttu-id="57ecb-122">Az **Ismétlődő számlák létrehozása a következő alapértelmezett értékeivel:** szakaszban válassza a szabadszöveges számlasablon vagy a vevői fiók lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="57ecb-122">In the **Generate recurring invoices by using the default values from** section, select either free text invoice template or the customer account.</span></span> <span data-ttu-id="57ecb-123">Válassza ki, hogy a rendszer a szabadszöveges számlasablon vagy a vevői számla alapján határozza meg a nyelvet, a feladási profilt, az áfacsoportot, a cikkáfacsoportot, a listakód, a szállítási országot/területet, a pénznemet, a fizetési feltételeket, a fizetési módot, a fizetési specifikációt, a részletfizetést, a készpénzfizetési engedményt, a pénzügyi dimenziókat, illetve a zsíró alapú pénzátutalási bizonylatot a számlák létrehozásakor.</span><span class="sxs-lookup"><span data-stu-id="57ecb-123">Select whether to use the free text invoice template or the customer account to determine the default values for the language, posting profile, sales tax group, item sales tax group, list code, country/region for delivery, currency, terms of payment, method of payment, payment specification, payment schedule, cash discount, financial dimensions, and giro money transfer slip when invoices are created.</span></span>  
13. <span data-ttu-id="57ecb-124">Az **Ismétlődési szabály** mezőben válassza ki a kívánt ismétlődési mintát.</span><span class="sxs-lookup"><span data-stu-id="57ecb-124">In the **Recurrence pattern** field, select the recurrence pattern.</span></span>
    + <span data-ttu-id="57ecb-125">Napi – Válassza ezt az opciót, majd adja meg a napok számát a / mezőben.</span><span class="sxs-lookup"><span data-stu-id="57ecb-125">Daily – Select this option and enter the number of days in the Per field.</span></span> <span data-ttu-id="57ecb-126">Ha például a 15 értéket adja meg, akkor a rendszer 15 naponta generál számlát ehhez a vevőhöz.</span><span class="sxs-lookup"><span data-stu-id="57ecb-126">For example, if you enter 15, an invoice will be generated every 15 days for this customer.</span></span>
    + <span data-ttu-id="57ecb-127">Hetente – Válassza a Hetente opciót, majd adja meg a hetek számát a / mezőben.</span><span class="sxs-lookup"><span data-stu-id="57ecb-127">Weekly - Select this option and enter the number of weeks in the Per field.</span></span> <span data-ttu-id="57ecb-128">Ha például a 2 értéket adja meg, akkor a rendszer kéthetente generál számlát ehhez a vevőhöz.</span><span class="sxs-lookup"><span data-stu-id="57ecb-128">For example, if you enter 2, an invoice will be generated every two weeks for this customer.</span></span>
    + <span data-ttu-id="57ecb-129">Havonta – Válassza a Havonta opciót, majd adja meg a hónapok számát a / mezőben.</span><span class="sxs-lookup"><span data-stu-id="57ecb-129">Monthly - Select this option and enter the number of months in the Per field.</span></span> <span data-ttu-id="57ecb-130">Ha például a 6 értéket adja meg, akkor a rendszer félévente generál számlát ehhez a vevőhöz.</span><span class="sxs-lookup"><span data-stu-id="57ecb-130">For example, if you enter 6, an invoice will be generated every six months for this customer.</span></span>
    + <span data-ttu-id="57ecb-131">Évente – Válassza az Évente opciót, majd adja meg az évek számát a / mezőben.</span><span class="sxs-lookup"><span data-stu-id="57ecb-131">Yearly – Select this option and enter the number of years in the Per field.</span></span> <span data-ttu-id="57ecb-132">Ha például a 2 értéket adja meg, akkor a rendszer kétévente generál számlát ehhez a vevőhöz.</span><span class="sxs-lookup"><span data-stu-id="57ecb-132">For example, if you enter 2, an invoice will be generated every two years for this customer.</span></span>  
14. <span data-ttu-id="57ecb-133">A **/** mezőben adjon meg egy számot.</span><span class="sxs-lookup"><span data-stu-id="57ecb-133">In the **Per** field, enter a number.</span></span>

