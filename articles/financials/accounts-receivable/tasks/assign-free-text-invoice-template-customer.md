--- 
title: "Szabadszöveges számlasablon hozzárendelése egy ügyfélhez"
description: "A feladat bemutatja, hogyan kell szabadszöveges számlasablont vevőhöz hozzárendelni."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: ea5f1ddd8f6be8a1dd2cee47b7746c4764ba28a4
ms.contentlocale: hu-hu
ms.lasthandoff: 05/08/2018

---
# <a name="assign-a-free-text-invoice-template-to-a-customer"></a><span data-ttu-id="b08a0-103">Szabadszöveges számlasablon hozzárendelése egy ügyfélhez</span><span class="sxs-lookup"><span data-stu-id="b08a0-103">Assign a free text invoice template to a customer</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="b08a0-104">A feladat bemutatja, hogyan kell szabadszöveges számlasablont vevőhöz hozzárendelni.</span><span class="sxs-lookup"><span data-stu-id="b08a0-104">This task demonstrates how to assign a free text invoice template to a customer.</span></span> <span data-ttu-id="b08a0-105">Ez a feladat az USMF bemutató vállalatot veszi alapul, és az a felhasználó használja, aki felelős a kintlévőségek számláinak kezeléséért és feldolgozásáért.</span><span class="sxs-lookup"><span data-stu-id="b08a0-105">This task uses the USMF demo company and is intended for the user who is responsible for managing and processing A/R invoices.</span></span>

1. <span data-ttu-id="b08a0-106">Ugorjon a Kinnlevőségek > Vevők > Minden vevő pontra.</span><span class="sxs-lookup"><span data-stu-id="b08a0-106">Go to Accounts receivable > Customers > All customers.</span></span>
2. <span data-ttu-id="b08a0-107">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="b08a0-107">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="b08a0-108">A Művelet panelen kattintson a Számla lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b08a0-108">On the Action Pane, click Invoice.</span></span>
4. <span data-ttu-id="b08a0-109">Kattintson az Ismétlődő számlák lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b08a0-109">Click Recurring invoices.</span></span>
    * <span data-ttu-id="b08a0-110">Ezen a lapon szabadszöveges számlasablonokat rendelhet hozzá a vevőkhöz, és megadhatja, hogy milyen gyakran történjen számlázás a vevő részére.</span><span class="sxs-lookup"><span data-stu-id="b08a0-110">Use this page to assign free text invoice templates to customers and specify how frequently invoices will be sent to the customer.</span></span>  
5. <span data-ttu-id="b08a0-111">Az Új gombra kattintva új sablont rendel a vevőhöz.</span><span class="sxs-lookup"><span data-stu-id="b08a0-111">Click New to assign a new template to the customer.</span></span>
6. <span data-ttu-id="b08a0-112">Válassza ki a szabadszöveges számlasablont, amelyet hozzá kíván rendelni a vevőhöz.</span><span class="sxs-lookup"><span data-stu-id="b08a0-112">Select the free text invoice template you want to assign to the customer.</span></span>
7. <span data-ttu-id="b08a0-113">A kívánt rekord megkeresése és kijelölése a listán</span><span class="sxs-lookup"><span data-stu-id="b08a0-113">In the list, find and select the desired record.</span></span>
8. <span data-ttu-id="b08a0-114">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="b08a0-114">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="b08a0-115">Írja be az első számla létrehozásának dátumát.</span><span class="sxs-lookup"><span data-stu-id="b08a0-115">Enter the date when the first invoice will be generated.</span></span>
    * <span data-ttu-id="b08a0-116">Ismétlődő záró dátum megadása.</span><span class="sxs-lookup"><span data-stu-id="b08a0-116">Enter a recurring end date.</span></span>  
    * <span data-ttu-id="b08a0-117">Válassza ki a következők valamelyikét: Nincs záró dátum – A számlázás folyamatosan történik, amíg a sablont el nem távolítja a vevői fiókból.</span><span class="sxs-lookup"><span data-stu-id="b08a0-117">Select one of the following: No end date – Invoices will be generated indefinitely until the template is removed from the customer account.</span></span>  <span data-ttu-id="b08a0-118">Számlázás záró dátuma – Válassza ezt az opciót, ha szeretné megadni, mi az a legutolsó dátum, amikor még generálható számla.</span><span class="sxs-lookup"><span data-stu-id="b08a0-118">Billing end date – Select this option and enter the last date that the invoice can be generated.</span></span>  
    * <span data-ttu-id="b08a0-119">Maximális halmozott összeg, amely után a számlák létrehozása leáll.</span><span class="sxs-lookup"><span data-stu-id="b08a0-119">Maximum cumulative amount after which invoice generation will stop.</span></span>  
    * <span data-ttu-id="b08a0-120">Adja meg a maximális halmozott összeget, amely a kiválasztott sablon használatával elérhető.</span><span class="sxs-lookup"><span data-stu-id="b08a0-120">Enter the maximum cumulative amount that can be reached using the selected template.</span></span> <span data-ttu-id="b08a0-121">Ha például 1000,00-t ad meg és havonta 100,00-ról állít ki számlát, a tizedik számla után nem jön létre több számla.</span><span class="sxs-lookup"><span data-stu-id="b08a0-121">For example, if you enter 1,000.00 and generate monthly invoices for 100.00 each, invoices will stop generating after the tenth invoice is generated.</span></span>  
    * <span data-ttu-id="b08a0-122">A szabadszöveges számlasablon vagy a vevői fiók alapértelmezett értékeit felhasználva ismétlődő számlákat állíthat ki.</span><span class="sxs-lookup"><span data-stu-id="b08a0-122">Generate recurring invoices by using the default values from either free text invoice template or the customer account.</span></span>  
    * <span data-ttu-id="b08a0-123">Válassza ki, hogy a rendszer a szabadszöveges számlasablon vagy a vevői számla alapján határozza meg a nyelvet, a feladási profilt, az áfacsoportot, a cikkáfacsoportot, a listakód, a szállítási országot/területet, a pénznemet, a fizetési feltételeket, a fizetési módot, a fizetési specifikációt, a részletfizetést, a készpénzfizetési engedményt, a pénzügyi dimenziókat, illetve a zsíró alapú pénzátutalási bizonylatot a számlák létrehozásakor.</span><span class="sxs-lookup"><span data-stu-id="b08a0-123">Select whether to use the free text invoice template or the customer account to determine the default values for the language, posting profile, sales tax group, item sales tax group, list code, country/region for delivery, currency, terms of payment, method of payment, payment specification, payment schedule, cash discount, financial dimensions, and giro money transfer slip when invoices are created.</span></span>  
10. <span data-ttu-id="b08a0-124">Válasszon ki egy ismétlődési szabályt.</span><span class="sxs-lookup"><span data-stu-id="b08a0-124">Select the recurrence pattern.</span></span>
    * <span data-ttu-id="b08a0-125">Napi – Válassza ezt az opciót, majd adja meg a napok számát a / mezőben.</span><span class="sxs-lookup"><span data-stu-id="b08a0-125">Daily – Select this option and enter the number of days in the Per field.</span></span> <span data-ttu-id="b08a0-126">Ha például a 15 értéket adja meg, akkor a rendszer 15 naponta generál számlát ehhez a vevőhöz.</span><span class="sxs-lookup"><span data-stu-id="b08a0-126">For example, if you enter 15, an invoice will be generated every 15 days for this customer.</span></span>  <span data-ttu-id="b08a0-127">Hetente – Válassza a Hetente opciót, majd adja meg a hetek számát a / mezőben.</span><span class="sxs-lookup"><span data-stu-id="b08a0-127">Weekly - Select this option and enter the number of weeks in the Per field.</span></span> <span data-ttu-id="b08a0-128">Ha például a 2 értéket adja meg, akkor a rendszer kéthetente generál számlát ehhez a vevőhöz.</span><span class="sxs-lookup"><span data-stu-id="b08a0-128">For example, if you enter 2, an invoice will be generated every two weeks for this customer.</span></span>  <span data-ttu-id="b08a0-129">Havonta – Válassza a Havonta opciót, majd adja meg a hónapok számát a / mezőben.</span><span class="sxs-lookup"><span data-stu-id="b08a0-129">Monthly - Select this option and enter the number of months in the Per field.</span></span> <span data-ttu-id="b08a0-130">Ha például a 6 értéket adja meg, akkor a rendszer félévente generál számlát ehhez a vevőhöz.</span><span class="sxs-lookup"><span data-stu-id="b08a0-130">For example, if you enter 6, an invoice will be generated every six months for this customer.</span></span>  <span data-ttu-id="b08a0-131">Évente – Válassza az Évente opciót, majd adja meg az évek számát a / mezőben.</span><span class="sxs-lookup"><span data-stu-id="b08a0-131">Yearly – Select this option and enter the number of years in the Per field.</span></span> <span data-ttu-id="b08a0-132">Ha például a 2 értéket adja meg, akkor a rendszer kétévente generál számlát ehhez a vevőhöz.</span><span class="sxs-lookup"><span data-stu-id="b08a0-132">For example, if you enter 2, an invoice will be generated every two years for this customer.</span></span>  
11. <span data-ttu-id="b08a0-133">A / mezőben adjon meg egy számot.</span><span class="sxs-lookup"><span data-stu-id="b08a0-133">In the Per field, enter a number.</span></span>


