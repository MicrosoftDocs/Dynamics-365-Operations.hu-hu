---
title: Tárgyieszköz-kivezetés feladási számlái
description: Ez a cikk bemutatja, hogy hogyan állíthat be főkönyvi feladási számlákat tárgyi eszközök beszerzéséhez.
author: ShylaThompson
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetPosting
audience: Application User
ms.reviewer: roschlom
ms.custom: 23021
ms.assetid: d7e86f72-95db-4423-9b04-761e9536a959
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1d4c1b4de2e58b964bcf6ab07929897083f4c826
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5822009"
---
# <a name="fixed-asset-acquisition-posting-accounts"></a><span data-ttu-id="c2a4f-103">Tárgyieszköz-kivezetés feladási számlái</span><span class="sxs-lookup"><span data-stu-id="c2a4f-103">Fixed asset acquisition posting accounts</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c2a4f-104">Ez a cikk bemutatja, hogy hogyan állíthat be főkönyvi feladási számlákat tárgyi eszközök beszerzéséhez.</span><span class="sxs-lookup"><span data-stu-id="c2a4f-104">This article explains how to set up general ledger posting accounts for acquiring assets.</span></span>

<span data-ttu-id="c2a4f-105">Tárgyieszköz-beszerzések feladásához használt számlák az eszköz megszerzésének módszerétől függően változhat.</span><span class="sxs-lookup"><span data-stu-id="c2a4f-105">Accounts used for posting fixed asset acquisitions may vary depending upon the method used to acquire the asset.</span></span> <span data-ttu-id="c2a4f-106">A tárgyi eszköz feladási profilok lapján, a főkönyvi számlák lapján válassza a beszerzési és beszerzés-módosítás kiigazitása a tárgyi eszköz számlák beállításához a főkönyvbe történő feladás érdekében.</span><span class="sxs-lookup"><span data-stu-id="c2a4f-106">On the Fixed asset posting profiles page, on the Ledger accounts tab, select Acquisition and Acquisition adjustment to set up fixed asset accounts to post to the ledger.</span></span> 

<span data-ttu-id="c2a4f-107">A naplókban és a beszerzési rendelésekben a főkönyvi számla általános esetben a az a mérlegszámla, amelyen az új tárgyi eszköz beszerzési értéke terhelve van.</span><span class="sxs-lookup"><span data-stu-id="c2a4f-107">In journals and on purchase orders, Ledger account is typically the balance sheet account, where the acquisition value of the new fixed asset is debited.</span></span> <span data-ttu-id="c2a4f-108">Ez a számla a naplóban nem látható, és a tranzakciókban nem helyettesíthető.</span><span class="sxs-lookup"><span data-stu-id="c2a4f-108">This account is not displayed in the journal and cannot be replaced in transactions.</span></span> 

<span data-ttu-id="c2a4f-109">Ellenszámla szintén egy mérlegszámla.</span><span class="sxs-lookup"><span data-stu-id="c2a4f-109">Offset account is also a balance sheet account.</span></span> <span data-ttu-id="c2a4f-110">Az általános naplóban és a tárgyieszköznaplóban gyakran ez az a számla, amelyről az eszköz beszerzési árának a kifizetése történik.</span><span class="sxs-lookup"><span data-stu-id="c2a4f-110">In the general journal and in the fixed assets journal, this account often will be the bank account that is used to pay for the acquisition of the asset.</span></span> <span data-ttu-id="c2a4f-111">Az ellenszámla egy alapértelmezett számla, amelyet a program felajánl a naplókban.</span><span class="sxs-lookup"><span data-stu-id="c2a4f-111">The offset account is a default account, which is suggested in the journals.</span></span> <span data-ttu-id="c2a4f-112">A naplóban át lehet állítani a számlatükör bármely másik számlájára vagy – ha a tárgyi eszközt egy szállítótól vásárolta – egy szállítói számlára.</span><span class="sxs-lookup"><span data-stu-id="c2a4f-112">It can be changed in the journal to any other account from the chart of accounts or to a vendor account, if the fixed asset was purchase from a vendor.</span></span> 

<span data-ttu-id="c2a4f-113">Amikor a számlanaplót vagy a beszerzési rendeléseket tárgyieszköz-beszerzésekhez használják a kötelezettségekben, akkor a tárgyi eszköz tranzakciók ellenszámláját a tranzakcióhoz kiválasztott szállító számla kicseréli.</span><span class="sxs-lookup"><span data-stu-id="c2a4f-113">When Invoice journal or Purchase orders in Accounts payable are used for fixed asset acquisitions, the offset account for the fixed asset transaction is replaced by the vendor account that is selected for the transaction.</span></span>

<span data-ttu-id="c2a4f-114">A feladott beszerzések esetén a főkönyvben található tárgyi eszközök tárának felhasználásával a tárgyi eszköz beszerzése nem külső forrásból, hanem a vállalat saját készletéből történik.</span><span class="sxs-lookup"><span data-stu-id="c2a4f-114">For acquisitions posted using the Inventory to fixed assets journal in General ledger, the fixed asset is not bought from external sources, but transferred from the company's own inventory.</span></span> <span data-ttu-id="c2a4f-115">Emiatt az ellenszámla a  készletcikkének egy készletkiadási számlája.</span><span class="sxs-lookup"><span data-stu-id="c2a4f-115">Therefore, the offset account is an inventory issue account for the inventory item in Inventory management.</span></span>

<span data-ttu-id="c2a4f-116">További tudnivalókért lásd: [Eszközök vételezése beszerzésen keresztül](acquire-assets-procurement.md).</span><span class="sxs-lookup"><span data-stu-id="c2a4f-116">For more information, see [Acquire assets through procurement](acquire-assets-procurement.md).</span></span>





[!INCLUDE[footer-include](../../includes/footer-banner.md)]