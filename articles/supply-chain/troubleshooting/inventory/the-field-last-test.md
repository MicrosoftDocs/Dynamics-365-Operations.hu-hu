---
title: Több minőségi rendelés létrehozásakor nem frissül a Legutóbbi tesztelés dátuma mező
description: Több minőségi rendelés létrehozásakor nem frissül a Legutóbbi tesztelés dátuma mező.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: InventBatch
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 6f796bdaa88d32b1c58dd8a4bca19f0ce4f3943d
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026586"
---
# <a name="the-last-tested-date-field-isnt-updated-when-multiple-quality-orders-are-created"></a><span data-ttu-id="be092-103">Több minőségi rendelés létrehozásakor nem frissül a Legutóbbi tesztelés dátuma mező</span><span class="sxs-lookup"><span data-stu-id="be092-103">The Last tested date field isn't updated when multiple quality orders are created</span></span>

<span data-ttu-id="be092-104">Tudásbáziscikk száma: 4612803</span><span class="sxs-lookup"><span data-stu-id="be092-104">KB number: 4612803</span></span>

## <a name="symptoms"></a><span data-ttu-id="be092-105">Tünetek</span><span class="sxs-lookup"><span data-stu-id="be092-105">Symptoms</span></span>

<span data-ttu-id="be092-106">Több minőségi rendelés létrehozásakor nem frissül a **Legutóbbi tesztelés dátuma** mező.</span><span class="sxs-lookup"><span data-stu-id="be092-106">The **Last tested date** field isn't updated when multiple quality orders are created.</span></span>

## <a name="resolution"></a><span data-ttu-id="be092-107">Felbontás</span><span class="sxs-lookup"><span data-stu-id="be092-107">Resolution</span></span>

<span data-ttu-id="be092-108">A rendszer úgy viselkedik, ahogy tervezték.</span><span class="sxs-lookup"><span data-stu-id="be092-108">The system is behaving as designed.</span></span> <span data-ttu-id="be092-109">A legutóbbi tesztelés dátuma nem kapcsolódik minőségi rendelésekhez.</span><span class="sxs-lookup"><span data-stu-id="be092-109">The last tested date isn't related to quality orders.</span></span> <span data-ttu-id="be092-110">Azt a dátumot tárolja, amikor a késztermékeket először vásárolták vagy gyártották.</span><span class="sxs-lookup"><span data-stu-id="be092-110">It stores the date when the finished goods were first purchased or manufactured.</span></span> <span data-ttu-id="be092-111">Ez a dátum használatos az eltarthatósági idő ajánlott dátumának kiszámításához.</span><span class="sxs-lookup"><span data-stu-id="be092-111">This date is used to calculate the shelf life advice date.</span></span>
