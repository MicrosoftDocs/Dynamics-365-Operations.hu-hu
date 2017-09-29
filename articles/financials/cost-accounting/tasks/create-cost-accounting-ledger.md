--- 
title: "Költségkönyvelési főkönyv létrehozása"
description: "A költségkönyvelési főkönyv megfelel a teljes adatszolgáltatási egységnek."
author: YuyuScheller
manager: AnnBe
ms.date: 06/27/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: ba8562f01ef440dd98db242550ee0e60db7acfc5
ms.contentlocale: hu-hu
ms.lasthandoff: 08/29/2017

---
# <a name="create-a-cost-accounting-ledger"></a><span data-ttu-id="1ce13-103">Költségkönyvelési főkönyv létrehozása</span><span class="sxs-lookup"><span data-stu-id="1ce13-103">Create a cost accounting ledger</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="1ce13-104">A költségkönyvelési főkönyv megfelel a teljes adatszolgáltatási egységnek.</span><span class="sxs-lookup"><span data-stu-id="1ce13-104">A cost accounting ledger represents the overall reporting unit.</span></span> <span data-ttu-id="1ce13-105">A következők határozzák meg: költségösszetevő-dimenzió, statisztikai dimenzió, pénzügyi naptár és pénznem.</span><span class="sxs-lookup"><span data-stu-id="1ce13-105">It is defined by a cost element dimension, statistical dimension, fiscal calendar, and currency.</span></span> <span data-ttu-id="1ce13-106">Független a jogi személyek fogalmától.</span><span class="sxs-lookup"><span data-stu-id="1ce13-106">It is agnostic to the concept of legal entities.</span></span> <span data-ttu-id="1ce13-107">A jogi személy és annak adatai számos költségkönyvelési főkönyvvel társíthatók.</span><span class="sxs-lookup"><span data-stu-id="1ce13-107">A legal entity and its data can be associated with many cost accounting ledgers.</span></span> <span data-ttu-id="1ce13-108">Ez a felvétel az USP2 bemutató vállalati adatait használja.</span><span class="sxs-lookup"><span data-stu-id="1ce13-108">This recording uses the USP2 demo data company.</span></span>

1. <span data-ttu-id="1ce13-109">Lépjen a Költségkönyvelés > Főkönyv beállításai > Költségkönyvelési főkönyvek lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="1ce13-109">Go to Cost accounting > Ledger setup > Cost accounting ledgers.</span></span>
2. <span data-ttu-id="1ce13-110">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="1ce13-110">Click New.</span></span>
3. <span data-ttu-id="1ce13-111">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="1ce13-111">In the Name field, type a value.</span></span>
4. <span data-ttu-id="1ce13-112">A Költségösszetevő-dimenzió mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="1ce13-112">In the Cost element dimension field, enter or select a value.</span></span>
5. <span data-ttu-id="1ce13-113">A Pénzügyi naptár mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="1ce13-113">In the Fiscal calendar field, enter or select a value.</span></span>
6. <span data-ttu-id="1ce13-114">A Könyvelési pénznem mezőben írjon be vagy adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="1ce13-114">In the Accounting currency field, enter or select a value.</span></span>
7. <span data-ttu-id="1ce13-115">Az Árfolyamtípus mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="1ce13-115">In the Exchange rate type field, enter or select a value.</span></span>
8. <span data-ttu-id="1ce13-116">A Statisztikai dimenzió mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="1ce13-116">In the Statistical dimension field, enter or select a value.</span></span>
9. <span data-ttu-id="1ce13-117">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="1ce13-117">Click Save.</span></span>


