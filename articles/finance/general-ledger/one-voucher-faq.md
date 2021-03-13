---
title: Egy bizonylat GYIK
description: Ez a témakör az Egy bizonylat funkcióval kapcsolatos gyakori kérdéseket tartalmazza. A pénzügyi naplók (főkönyvi napló, tárgyieszköz-napló, szállítói kifizetési napló és így tovább) Egy bizonylat funkciójának használatával bevihető több analitikusnapló-tranzakció egyetlen bizonylat keretein belül.
author: kweekley
manager: AnnBe
ms.date: 11/05/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalSetup, LedgerParameters, AssetProposalDepreciation
audience: Application User
ms.reviewer: roschlom
ms.custom: 14091
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2018-03-16
ms.dyn365.ops.version: 8.0.2
ms.openlocfilehash: 916f0172a2d7f9fad9dcd70b31f8ecf65e47b2c8
ms.sourcegitcommit: bd4763cc6088e114818e80bb1c27c6521b039743
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/02/2021
ms.locfileid: "5107749"
---
# <a name="one-voucher-faq"></a><span data-ttu-id="8db05-104">Egy bizonylat GYIK</span><span class="sxs-lookup"><span data-stu-id="8db05-104">One voucher FAQ</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="8db05-105">Ez a témakör az Egy bizonylat funkcióval kapcsolatos gyakori kérdéseket tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="8db05-105">This topic answers frequently asked questions about the One voucher functionality.</span></span> <span data-ttu-id="8db05-106">A pénzügyi naplók Egy bizonylat funkciójának használatával bevihető több analitikusnapló-tranzakció egyetlen bizonylat keretein belül.</span><span class="sxs-lookup"><span data-stu-id="8db05-106">One voucher for financial journals lets you enter multiple subledger transactions in the context of a single voucher.</span></span> <span data-ttu-id="8db05-107">A bizonylatba foglalható naplók lehetnek többek között főkönyvi naplók, tárgyieszköz-naplók és szállítói kifizetési naplók.</span><span class="sxs-lookup"><span data-stu-id="8db05-107">The journals that you can include in that voucher can be general journals, fixed asset journals, and vendor payment journals, among others.</span></span>

## <a name="when-will-the-one-voucher-functionality-be-deprecated"></a><span data-ttu-id="8db05-108">Mikor válik elavulttá az Egy bizonylat funkció?</span><span class="sxs-lookup"><span data-stu-id="8db05-108">When will the One voucher functionality be deprecated?</span></span>

<span data-ttu-id="8db05-109">Bár a Microsoft nem tud pontos becslést adni arról, hogy mikorra válik elavulttá az Egy bizonylat funkció, az értékcsökkenés valószínűleg legalább két év múlva következik be.</span><span class="sxs-lookup"><span data-stu-id="8db05-109">Although Microsoft can't provide an accurate estimate about when the One voucher functionality will be deprecated, it will likely be at least two years before the deprecation occurs.</span></span>

<span data-ttu-id="8db05-110">Mint azt az Egy bizonylat dokumentációja is tartalmazza, számos üzleti követelmény csak az Egy bizonylat funkcióval teljesíthető.</span><span class="sxs-lookup"><span data-stu-id="8db05-110">As is noted in the One voucher documentation, numerous business requirements can be met only by using One voucher.</span></span> <span data-ttu-id="8db05-111">A Microsoftnak gondoskodnia kell arról, hogy a funkció értékcsökkenése után is teljesülni tudjanak a rendszerben az azonosított üzleti követelmények.</span><span class="sxs-lookup"><span data-stu-id="8db05-111">Microsoft must ensure that all the identified business requirements can still be met in the system after the functionality is deprecated.</span></span> <span data-ttu-id="8db05-112">Ennek megfelelően a működési hiányok kitöltéséhez valószínűleg új funkciókat kell hozzáadni.</span><span class="sxs-lookup"><span data-stu-id="8db05-112">Therefore, new features will probably have to be added to fill functional gaps.</span></span>

<span data-ttu-id="8db05-113">Miután minden működési hiányt kitöltött, a Microsoft közli, hogy a funkció elavulttá válik.</span><span class="sxs-lookup"><span data-stu-id="8db05-113">After all functional gaps are filled, Microsoft will communicate that the feature will be deprecated.</span></span> <span data-ttu-id="8db05-114">Az értékcsökkenés azonban a tájékoztatás után legalább egy évig nem lép hatályba.</span><span class="sxs-lookup"><span data-stu-id="8db05-114">However, the deprecation won't be effective for least one year after that communication.</span></span>

<span data-ttu-id="8db05-115">További részletek az [Egy bizonylat dokumentációjában](one-voucher.md) találhatók.</span><span class="sxs-lookup"><span data-stu-id="8db05-115">For more information, see the [One voucher documentation](one-voucher.md).</span></span>

## <a name="what-will-the-solution-that-replaces-one-voucher-look-like"></a><span data-ttu-id="8db05-116">Milyen megoldás lép az Egy bizonylat funkció helyébe?</span><span class="sxs-lookup"><span data-stu-id="8db05-116">What will the solution that replaces One voucher look like?</span></span>

<span data-ttu-id="8db05-117">A Microsoft nem tud konkrét megoldást kínálni, mivel minden működési hiány más, és az üzleti követelmények alapján kell felmérni őket.</span><span class="sxs-lookup"><span data-stu-id="8db05-117">Microsoft can't provide a specific solution, because each feature gap is different and must be evaluated based on the business requirements.</span></span> <span data-ttu-id="8db05-118">Bizonyos működési hiányokat valószínűleg olyan funkciók írnak felül, amelyek megfelelnek az egyes üzleti követelményeknek.</span><span class="sxs-lookup"><span data-stu-id="8db05-118">Some functional gaps will likely be replaced with features that help meet specific business requirements.</span></span> <span data-ttu-id="8db05-119">Előfordulhat azonban, hogy más hiányokat úgy lehet kitölteni, hogy lehetővé teszik a naplóban való bevitelt, mint amikor az Egy bizonylat funkciót használják, de javítani kell a rendszeren, hogy szükség szerint nyomon kövesse a részletesebb adatokat.</span><span class="sxs-lookup"><span data-stu-id="8db05-119">However, other gaps might be filled by continuing to allow for entry in a journal, as when One voucher is used, but enhancing the system to track more detail as required.</span></span>

## <a name="where-can-i-track-the-progress-of-the-feature-gaps-being-filled"></a><span data-ttu-id="8db05-120">Hol követhetem nyomon a kitöltött működési hiányok előrehaladását?</span><span class="sxs-lookup"><span data-stu-id="8db05-120">Where can I track the progress of the feature gaps being filled?</span></span>

<span data-ttu-id="8db05-121">Mint minden új funkció esetében, a vevőknek figyelniük kell a Kiadási tervet és az Új vagy módosult elemek dokumentációt.</span><span class="sxs-lookup"><span data-stu-id="8db05-121">As for every new feature, customers must watch the Release plan and "What's new or changed" documentation.</span></span> <span data-ttu-id="8db05-122">Minden funkciót hozzáadnak ezekhez a dokumentumokhoz, és egy megjegyzés jelzi, hogy a funkció olyan üzleti követelmény teljesítéséhez szükséges, amely korábban az Egy bizonylat funkció használatát írta elő.</span><span class="sxs-lookup"><span data-stu-id="8db05-122">Each feature will be added to these documents, and a note will indicate that the feature is required to meet a business requirement that previously required the One voucher functionality.</span></span>

## <a name="when-the-deprecation-date-is-identified-where-will-it-be-communicated"></a><span data-ttu-id="8db05-123">Amikor meghatározzák az értékcsökkenés dátumát, hol jelzik ezt a felhasználóknak?</span><span class="sxs-lookup"><span data-stu-id="8db05-123">When the deprecation date is identified, where will it be communicated?</span></span>

<span data-ttu-id="8db05-124">Az Egy bizonylat értékcsökkenése jelentős változás, amelyről széles körben folyik majd tájékoztatás.</span><span class="sxs-lookup"><span data-stu-id="8db05-124">The deprecation of One voucher is a significant change that will be widely communicated.</span></span> <span data-ttu-id="8db05-125">Ez a termékdokumentáción, blogbejegyzésben és az érintett Microsoft-konferenciákon elhangzó közlemények révén történik, jóval az értékcsökkenés hatálybalépésének dátuma előtt.</span><span class="sxs-lookup"><span data-stu-id="8db05-125">It will be communicated through the product documentation, a blog post, and announcements at applicable Microsoft conferences, well in advance of the date when the deprecation takes effect.</span></span>
