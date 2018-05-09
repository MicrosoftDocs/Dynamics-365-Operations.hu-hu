---
title: "Pénzügyi dimenziók és fő számlák egy jobbról balra író nyelv esetében"
description: "Ez a témakör néhány olyan, a megvalósítási döntésekre vonatkozó szempontot ismertet, amelyet figyelembe kell venni, amikor jobbról balra író nyelvet használ, és be kell állítania a pénzügyi dimenziókat és a fő számlákat."
author: aprilolson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 222564
ms.assetid: 875dcebb-1bbb-4841-a8c6-9e134da07e96
ms.search.region: global
ms.author: aolson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 857f2c7ea948717695c3c741a20f6b3e922b33e1
ms.contentlocale: hu-hu
ms.lasthandoff: 05/08/2018

---

# <a name="financial-dimensions-and-main-accounts-in-a-right-to-left-language"></a><span data-ttu-id="c708b-103">Pénzügyi dimenziók és fő számlák egy jobbról balra író nyelv esetében</span><span class="sxs-lookup"><span data-stu-id="c708b-103">Financial dimensions and main accounts in a right-to-left language</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c708b-104">Ez a témakör néhány olyan, a megvalósítási döntésekre vonatkozó szempontot ismertet, amelyet figyelembe kell venni, amikor jobbról balra író nyelvet használ, és be kell állítania a pénzügyi dimenziókat és a fő számlákat.</span><span class="sxs-lookup"><span data-stu-id="c708b-104">This topic describes some of the implementation decisions that you should consider when you use a right-to-left language, and you must set up financial dimensions and main accounts.</span></span>

<span data-ttu-id="c708b-105">A pénzügyi dimenziók és a fő számlák rendkívül alkotóelemek a megvalósítás tervezési szakaszában.</span><span class="sxs-lookup"><span data-stu-id="c708b-105">Financial dimensions and main accounts are key components of the planning phase for an implementation.</span></span> <span data-ttu-id="c708b-106">Miután létrehozták a pénzügyi dimenziókat és a fő számlákat a rendszerben, ezek a következő oldalakon kerülnek felhasználásra: **Számlastruktúrák konfigurálása**, **Speciális szabálystruktúrák** és **Pénzügyi dimenzió konfigurációja alkalmazások integrálásához**.</span><span class="sxs-lookup"><span data-stu-id="c708b-106">After financial dimensions and main accounts are created in the system, they are used on the **Configure account structures**, **Advanced rule structures**, and **Financial dimension configuration for integrating applications** pages.</span></span> <span data-ttu-id="c708b-107">Az ezeken a lapokon meghatározott rendelés adatbevitelre és felhasználásra szolgál a rendszerben.</span><span class="sxs-lookup"><span data-stu-id="c708b-107">The order that is defined on those pages is used in the system for data entry and consumption.</span></span> <span data-ttu-id="c708b-108">A rendszer egyes helyein a pénzügyi dimenziók és a fő számlák külön mezőkben jelennek meg.</span><span class="sxs-lookup"><span data-stu-id="c708b-108">In some places in the system, the financial dimensions and main accounts appear in separate fields.</span></span> <span data-ttu-id="c708b-109">Más helyeken azonban, például naplókban, a pénzügyi dimenziók és a fő számlák egyetlen karakterláncként jelennek meg.</span><span class="sxs-lookup"><span data-stu-id="c708b-109">However, in other places, such as journals, the financial dimensions and main accounts appear as a single string.</span></span>

### <a name="best-practices-for-setting-up-financial-dimensions-and-main-accounts-in-a-right-to-left-system"></a><span data-ttu-id="c708b-110">Gyakorlati tanácsok a pénzügyi dimenziók és a fő számlák beállításához egy jobbról balra író rendszerben</span><span class="sxs-lookup"><span data-stu-id="c708b-110">Best practices for setting up financial dimensions and main accounts in a right-to-left system</span></span>

-   <span data-ttu-id="c708b-111">Amikor bejelöli a számlatükrök elválasztó karakterét, válasszon ki egyet a kettős elválasztási lehetőségek közül: dupla kötőjel (--), a dupla sáv (||) vagy két pont (..) vagy dupla aláhúzás (\_\_).</span><span class="sxs-lookup"><span data-stu-id="c708b-111">When you select the delimiter for charts of accounts, select one of the double delimiter options: double hyphen (--), double bar (||) or double period (..), or double underscore (\_\_).</span></span>
-   <span data-ttu-id="c708b-112">Amikor létrehozza a pénzügyi dimenziók és a fő számla értékeit, csak számokat és jobbról balra irányú nyelvi karaktereket használjon.</span><span class="sxs-lookup"><span data-stu-id="c708b-112">When you create financial dimension and main account values, use only numbers and right-to-left language characters.</span></span>
-   <span data-ttu-id="c708b-113">Ne használja a számlatükör kiválasztott elválasztó karakterét a pénzügyi dimenzió és a főszámla értékei esetében.</span><span class="sxs-lookup"><span data-stu-id="c708b-113">Avoid using the selected chart of accounts delimiter in financial dimension and main account values.</span></span>

<span data-ttu-id="c708b-114">Ha követi ezeket a gyakorlati tanácsokat, azzal segít garantálni a felhasználó által meghatározott sorrend pontos betartását mindenhol a rendszerben..</span><span class="sxs-lookup"><span data-stu-id="c708b-114">By following these best practices, you help guarantee consistent representation of the user defined-order throughout the system.</span></span>




