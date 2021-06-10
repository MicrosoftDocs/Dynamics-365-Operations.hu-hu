---
title: Pénzügyi naplósablonok megnyitása az Office programban
description: Ez a témakör olyan problémákat ír le, amelyek akkor fordulhatnak elő, ha egyéni pénzügyi naplókat hoz létre Microsoft Excel-sablon alapján.
author: kweekley
ms.date: 05/14/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2020-05-14
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 0773f47551b2460ec310b92b67c634b433147749
ms.sourcegitcommit: 8c5b3e872825953853ad57fc67ba6e5ae92b9afe
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/24/2021
ms.locfileid: "6089457"
---
# <a name="open-financial-journal-templates-in-office"></a><span data-ttu-id="34893-103">Pénzügyi naplósablonok megnyitása az Office programban</span><span class="sxs-lookup"><span data-stu-id="34893-103">Open financial journal templates in Office</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="34893-104">Ez a témakör olyan problémákat ír le, amelyek akkor fordulhatnak elő, ha egyéni pénzügyi naplókat hoz létre Microsoft Excel-sablon alapján.</span><span class="sxs-lookup"><span data-stu-id="34893-104">This topic describes issues that might occur when you create custom financial journals by using a Microsoft Excel template.</span></span>

## <a name="symptom"></a><span data-ttu-id="34893-105">Tünet</span><span class="sxs-lookup"><span data-stu-id="34893-105">Symptom</span></span>

<span data-ttu-id="34893-106">Létrehozott egy egyéni Excel-sablont a pénzügyi naplók számára, de az nem jelenik meg az **Sorok megnyitása az Excelben** menüjében.</span><span class="sxs-lookup"><span data-stu-id="34893-106">You created a custom Excel template for financial journals, but it doesn't appear on the **Open lines in Excel** menu.</span></span> <span data-ttu-id="34893-107">Másik lehetőségként megjelenhet a menüben, de amikor kiválasztja, egy másik sablont nyit meg.</span><span class="sxs-lookup"><span data-stu-id="34893-107">Alternatively, it does appear on the menu, a different template is opened but when you select it.</span></span>

## <a name="resolution"></a><span data-ttu-id="34893-108">Megoldás</span><span class="sxs-lookup"><span data-stu-id="34893-108">Resolution</span></span>

<span data-ttu-id="34893-109">Az Excel programban történő megnyitás alapértelmezett funkciója az aktuális lap gyökéradatforrását (tábláját) használja annak meghatározására, hogy mely Office-sablonok vagy -adatentitások jelenjenek meg lehetőségként az **Excel programban történő megnyitás** menüben.</span><span class="sxs-lookup"><span data-stu-id="34893-109">The default Open in Excel functionality uses the root data source (table) of the current page to determine which Office templates or data entities appear as options on the **Open in Excel** menu.</span></span> <span data-ttu-id="34893-110">Ez a viselkedés nem ideális a pénzügyi naplók számára, mivel a pénzügyi naplók sok más típusú napló gyökéradatforrásaként használják ugyanazon táblákat (LedgerJournalTable és LedgerJournalTrans).</span><span class="sxs-lookup"><span data-stu-id="34893-110">This behavior isn't an ideal experience for financial journals, because financial journals use the same tables (LedgerJournalTable and LedgerJournalTrans) as the root data source of many other types of journals.</span></span>

<span data-ttu-id="34893-111">Pénzügyi naplók esetén a Sorok megnyitása az Excelben funkció célja az éppen használt naplóhoz – például az általános naplóhoz vagy a kifizetési naplóhoz – készült sablonok megjelenítése.</span><span class="sxs-lookup"><span data-stu-id="34893-111">For financial journals, the Open Lines in Excel functionality is intended to show templates that are designed for the journal that you're currently working in the context of, such as the general journal or a payment journal.</span></span> <span data-ttu-id="34893-112">Például egy szállítói kifizetési naplóval való használatra szánt sablon az elsődleges számla szállítói számlaként való érvényesítésére lesz kialakítva.</span><span class="sxs-lookup"><span data-stu-id="34893-112">For example, a template that is intended to be used with a vendor payment journal will be designed to enforce your primary account as a vendor account.</span></span>

<span data-ttu-id="34893-113">Ha beállítana egy sablont, hogy az elérhető legyen a **Sorok megnyitása az Excelben** és az **Excel programban történő megnyitás** menükben, akkor egy egyszerű fejlesztői tapasztalat szerint a **LedgerIJournalExcelTemplate** felület implementálása és a **DocuTemplateRegistrationBase** osztály kiterjesztése lehet a megoldás.</span><span class="sxs-lookup"><span data-stu-id="34893-113">If you want to promote a template so that it's available on the **Open lines in Excel** and **Open in Excel** menus, an easy developer experience is to implement the **LedgerIJournalExcelTemplate** interface and extend the **DocuTemplateRegistrationBase** class.</span></span> <span data-ttu-id="34893-114">Erre a megközelítésre számos példa van a rendszerben.</span><span class="sxs-lookup"><span data-stu-id="34893-114">Many examples of this approach are implemented in the system.</span></span> <span data-ttu-id="34893-115">Hivatkozásként használható példa az általános naplóhoz (vagy napi naplóhoz) létrehozott **LedgerDailyJournalExcelTemplate** felület.</span><span class="sxs-lookup"><span data-stu-id="34893-115">One example that can be used for reference is the **LedgerDailyJournalExcelTemplate** interface that was created for the general journal (or daily journal).</span></span>

<span data-ttu-id="34893-116">Ha a sablonhoz implementálva van a **LedgerIJournalExcelTemplate** felület, a **Sorok megnyitása az Excelben** menü a napló típusa szerint szűri a sablonokat, és csak az adott naplóhoz elérhető sablonokat mutatja.</span><span class="sxs-lookup"><span data-stu-id="34893-116">When the **LedgerIJournalExcelTemplate** interface is implemented for your template, the **Open Lines in Excel** menu will filter templates by the journal type of your journal and will show only the templates that are available for that journal.</span></span> <span data-ttu-id="34893-117">A felület olyan ellenőrzési módszert is biztosít, amely gondoskodik arról, hogy ne lehessen megnyitni egy sablont egy naplóhoz, ha az nem felel meg a számlatípus követelményeinek.</span><span class="sxs-lookup"><span data-stu-id="34893-117">The interface also provides a validation method that ensures that a template can't be opened for a journal if it doesn't meet the account type requirements.</span></span> <span data-ttu-id="34893-118">Megadhatja például, hogy a számlatípus **Szállító** vagy **Főkönyv** típusú legyen.</span><span class="sxs-lookup"><span data-stu-id="34893-118">For example, you can specify that the account type must be of the **Vendor** or **Ledger** type.</span></span>

<span data-ttu-id="34893-119">A további tudnivalókat erről a funkcióról lásd: [Sablonok hozzáadása a Sorok megnyitása az Excelben menühöz](../../fin-ops-core/dev-itpro/user-interface/add-templates-open-lines-excel-menu.md).</span><span class="sxs-lookup"><span data-stu-id="34893-119">For more information about this functionality, see [Add templates to the Open lines in Excel menu](../../fin-ops-core/dev-itpro/user-interface/add-templates-open-lines-excel-menu.md).</span></span>
