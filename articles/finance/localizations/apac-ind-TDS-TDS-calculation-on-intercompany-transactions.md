---
title: TDS kiszámítása vállalatközi tranzakciókhoz
description: Ez a témakör azt a folyamatot írja le, amelyet a Forrásnál levont adó (TDS) kiszámítására használnak a vállalatközi tranzakciókhoz a fázisokban.
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: 0e304747cc93bfe0a39beababc3182ca14664b11
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023301"
---
# <a name="tds-calculation-on-intercompany-transactions"></a><span data-ttu-id="a7350-103">TDS kiszámítása vállalatközi tranzakciókhoz</span><span class="sxs-lookup"><span data-stu-id="a7350-103">TDS calculation on intercompany transactions</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a7350-104">Ez a témakör azt a folyamatot írja le, amelyet a Forrásnál levont adó (TDS) kiszámítására használnak a vállalatközi tranzakciókhoz a fázisokban.</span><span class="sxs-lookup"><span data-stu-id="a7350-104">This topic describes the process that is used to calculate Tax Deducted at Source (TDS) on intercompany transactions in phases.</span></span>

<span data-ttu-id="a7350-105">Vállalatközi beszerzési vagy értékesítési rendelés létrehozásakor a vevő vagy szállító számára meghatározott alapértelmezett TDS-csoport szolgál a TDS-összeg kiszámítására.</span><span class="sxs-lookup"><span data-stu-id="a7350-105">When an intercompany purchase order or sales order is created, the default TDS group that is defined for the customer or vendor is used to calculate the TDS amount.</span></span> <span data-ttu-id="a7350-106">A TDS-összeg a számla könyvelése után kerül feladásra a visszatéríthető vagy fizetendő számlákra.</span><span class="sxs-lookup"><span data-stu-id="a7350-106">The TDS amount is posted to the recoverable or payable accounts after the invoice is posted.</span></span>

<span data-ttu-id="a7350-107">A vállalatközi értékesítési rendelés vagy beszerzési rendelés automatikusan létrejön az eredeti megrendeléshez vagy értékesítési megrendeléshez.</span><span class="sxs-lookup"><span data-stu-id="a7350-107">An intercompany sales order or purchase order is automatically created for the original purchase order or sales order.</span></span> <span data-ttu-id="a7350-108">Az alapértelmezett TDS-csoport megjelenik a vállalatközi rendelésben, így a TDS kiszámítható.</span><span class="sxs-lookup"><span data-stu-id="a7350-108">The default TDS group is shown on the intercompany order, so that TDS can be calculated.</span></span> <span data-ttu-id="a7350-109">A TDS-csoport módosítható.</span><span class="sxs-lookup"><span data-stu-id="a7350-109">You can change the TDS group.</span></span> <span data-ttu-id="a7350-110">A számla csak akkor könyvelhető, ha az automatikusan létrehozott vállalatközi megrendelés nettó számlaösszege megegyezik az eredeti megrendelés nettó számlaösszegével.</span><span class="sxs-lookup"><span data-stu-id="a7350-110">The invoice can be posted only if the net invoice amount on the intercompany order that is automatically created matches the net invoice amount on the original order.</span></span> <span data-ttu-id="a7350-111">(A nettó összeg a számla összege a TDS levonása után.)</span><span class="sxs-lookup"><span data-stu-id="a7350-111">(The net amount is the invoice amount after TDS is deducted.)</span></span>

<span data-ttu-id="a7350-112">Például egy értékesítési számla jön létre 50 000 értékben és a **10%-os** TDS csoport van csatolva hozzá.</span><span class="sxs-lookup"><span data-stu-id="a7350-112">For example, a sales invoice is created for 50,000, and the **10%** TDS group is attached to it.</span></span> <span data-ttu-id="a7350-113">A könyvelt számla összege 45 000, az értékesítési számla feladott TDS-összege pedig 5000.</span><span class="sxs-lookup"><span data-stu-id="a7350-113">The posted invoice amount is 45,000, and the posted TDS amount for the sales invoice is 5,000.</span></span> <span data-ttu-id="a7350-114">A vállalatközi értékesítési rendeléshez automatikusan létrejön egy beszerzési rendelés, amelyhez a **10%-os** TDS-csoport van csatolva.</span><span class="sxs-lookup"><span data-stu-id="a7350-114">A purchase order is automatically created for the intercompany sales order, and the  **10%** TDS group is attached to it.</span></span> <span data-ttu-id="a7350-115">Ha a TDS csoportot **15%-ra** módosítja, nem tudja könyvelni a számlát, mert az automatikusan létrehozott vállalatközi értékesítési rendelés nettó számlaösszege nem egyezik meg az eredeti értékesítési rendelés nettó számlaösszegével.</span><span class="sxs-lookup"><span data-stu-id="a7350-115">If you change the TDS group to **15%**, you can't post the invoice, because the net invoice amount of the intercompany sales order that was automatically created doesn't match the net invoice amount of the original sales order.</span></span>

<span data-ttu-id="a7350-116">A vállalatközi számlához létrehozott fizetési napló automatikusan könyvelve lesz.</span><span class="sxs-lookup"><span data-stu-id="a7350-116">A payment journal that is created for an intercompany invoice is automatically posted.</span></span> <span data-ttu-id="a7350-117">Ez a fizetési napló csak akkor könyvelhető, ha a rajta lévő nettó fizetési összeg megegyezik az eredeti fizetési naplóban található nettó fizetési összeggel.</span><span class="sxs-lookup"><span data-stu-id="a7350-117">That payment journal can be posted only if the net payment amount on it matches the net payment amount on the original payment journal.</span></span>
