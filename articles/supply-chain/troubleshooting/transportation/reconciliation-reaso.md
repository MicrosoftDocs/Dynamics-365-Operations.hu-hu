---
title: Egyeztetési okokból csak a főszámlát adhat hozzá hitelszámlaként
description: Ha a Szállításkezelésben egyeztetési okot állít be, csak a főszámlát adhat hozzá hitelszámlaként.
author: Henrikan
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: TMSFBDetailReconcile
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 708081370b27fd51ef9a2329d8392f4515353dcb
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026561"
---
# <a name="you-can-add-only-the-main-account-as-the-credit-account-for-reconciliation-reasons"></a><span data-ttu-id="60c92-103">Egyeztetési okokból csak a főszámlát adhat hozzá hitelszámlaként</span><span class="sxs-lookup"><span data-stu-id="60c92-103">You can add only the main account as the credit account for reconciliation reasons</span></span>

<span data-ttu-id="60c92-104">Tudásbáziscikk száma: 4603538</span><span class="sxs-lookup"><span data-stu-id="60c92-104">KB number: 4603538</span></span>

## <a name="symptoms"></a><span data-ttu-id="60c92-105">Tünetek</span><span class="sxs-lookup"><span data-stu-id="60c92-105">Symptoms</span></span>

<span data-ttu-id="60c92-106">Ha a Szállításkezelésben egyeztetési okot állít be, csak a főszámlát adhat hozzá hitelszámlaként.</span><span class="sxs-lookup"><span data-stu-id="60c92-106">When you set up a reconciliation reason in Transportation management, you can add only the main account as the credit account.</span></span> <span data-ttu-id="60c92-107">Nem adhat hozzá költségközpontot vagy más dimenziót hitelszámlaként.</span><span class="sxs-lookup"><span data-stu-id="60c92-107">You can't add a cost center or any other dimension as the credit account.</span></span> <span data-ttu-id="60c92-108">A terhelési számla azonban lehetővé teszi más dimenziók kiválasztását.</span><span class="sxs-lookup"><span data-stu-id="60c92-108">However, the debit account lets you select other dimensions.</span></span>

## <a name="resolution"></a><span data-ttu-id="60c92-109">Felbontás</span><span class="sxs-lookup"><span data-stu-id="60c92-109">Resolution</span></span>

<span data-ttu-id="60c92-110">Ha az egyeztetés nem a szállító kifizetésével, hanem egy adott főszámlára történő jóváírással történik, a rendszer nem teszi lehetővé a hitelszámla pénzügyi dimenziójának kiválasztását az egyeztetési ok beállításakor.</span><span class="sxs-lookup"><span data-stu-id="60c92-110">If the reconciliation isn't done to pay the vendor but to credit a specific main account, the system doesn't allow you to select a financial dimension for the credit account when you set up the reconciliation reason.</span></span>

<span data-ttu-id="60c92-111">Ha a számlastruktúra a hitel főszámlájának adott pénzügyi dimenzióértékét igényli, a kapott szállítói napló nem adható fel automatikusan, mert hiányzik a pénzügyi dimenzió értéke.</span><span class="sxs-lookup"><span data-stu-id="60c92-111">If the account structure requires a specific financial dimension value for the credit main account, the resulting vendor journal can't be posted automatically, because the financial dimension value is missing.</span></span> <span data-ttu-id="60c92-112">Ezért először manuálisan kell megadnia a hitelszámlát a **Számlanapló** oldalon.</span><span class="sxs-lookup"><span data-stu-id="60c92-112">Therefore, you must first manually specify the credit account by using the **Invoice journal** page.</span></span>

<span data-ttu-id="60c92-113">Mivel a hitelszámlához dimenzióérték szükséges, a szállítói számlanapló nem adható fel automatikusan.</span><span class="sxs-lookup"><span data-stu-id="60c92-113">Because a dimension value is required for the credit account, the vendor invoice journal can't be automatically posted.</span></span> <span data-ttu-id="60c92-114">Manuálisan kell elküldenie, miután manuálisan hozzáadta a dimenzióértéket a hitelsor fő számlájához.</span><span class="sxs-lookup"><span data-stu-id="60c92-114">You must manually post it after you manually add the dimension value to the main account for the credit line.</span></span>
