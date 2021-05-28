---
title: A tételszám törlődik, ha új tételazonosítót választott
description: Ha egy kitárolási lista naplósorát tekinti át, a Tételszám mezőben lévő érték törlődik, ha új értéket jelöl ki a Tételazonosító mezőben.
author: johanhoffmann
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ProdJournalTransBOM
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: datra
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 71977a04adb066a8b51c9bf7b8c5a4e752ca902e
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026560"
---
# <a name="batch-number-is-cleared-when-a-new-lot-id-is-selected"></a><span data-ttu-id="00696-103">A tételszám törlődik, ha új tételazonosítót választott</span><span class="sxs-lookup"><span data-stu-id="00696-103">Batch number is cleared when a new lot ID is selected</span></span>

<span data-ttu-id="00696-104">Tudásbáziscikk száma: 4613107</span><span class="sxs-lookup"><span data-stu-id="00696-104">KB number: 4613107</span></span>

## <a name="symptoms"></a><span data-ttu-id="00696-105">Tünetek</span><span class="sxs-lookup"><span data-stu-id="00696-105">Symptoms</span></span>

<span data-ttu-id="00696-106">Ha egy kitárolási lista naplósorát tekinti át, a **Tételszám** mezőben lévő érték törlődik, ha új értéket jelöl ki a **Tételazonosító** mezőben.</span><span class="sxs-lookup"><span data-stu-id="00696-106">When you're reviewing a picking list journal line, the value in the **Batch number** field is cleared if you select a new value in the **Lot ID** field.</span></span>

## <a name="resolution"></a><span data-ttu-id="00696-107">Felbontás</span><span class="sxs-lookup"><span data-stu-id="00696-107">Resolution</span></span>

<span data-ttu-id="00696-108">A rendszer úgy viselkedik, ahogy tervezték.</span><span class="sxs-lookup"><span data-stu-id="00696-108">The system is behaving as designed.</span></span> <span data-ttu-id="00696-109">Ha módosítja a tételazonosítót, módosítja az elemkörnyezetet.</span><span class="sxs-lookup"><span data-stu-id="00696-109">If you change the lot ID, you change the item context.</span></span> <span data-ttu-id="00696-110">Ebből következően a kötegszámot vissza lesz állítva.</span><span class="sxs-lookup"><span data-stu-id="00696-110">Therefore, the batch number is reset.</span></span>

<span data-ttu-id="00696-111">A tételszámhoz tételazonosító társításához először be kell állítania a tételazonosítót.</span><span class="sxs-lookup"><span data-stu-id="00696-111">To associate the batch number with a lot ID, you must set the lot ID first.</span></span>
