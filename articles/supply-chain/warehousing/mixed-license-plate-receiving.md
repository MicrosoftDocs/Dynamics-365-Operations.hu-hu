---
title: "Vegyes azonosítótábla bevételezése"
description: "Ez a témakör leírja, hogyan használható a vegyes azonosítótáblák bevételezése munka regisztrálásához és létrehozásához több cikkhez, mobileszközzel."
author: Mirzaab
manager: AnnBe
ms.date: 05/26/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 0e785d71e7ae3c5f60d36d8b190001b5e356c626
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---

# <a name="mixed-license-plate-receiving"></a><span data-ttu-id="97c91-103">Vegyes azonosítótábla bevételezése</span><span class="sxs-lookup"><span data-stu-id="97c91-103">Mixed license plate receiving</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="97c91-104">A vegyes azonosítótábla bevételezése teszi lehetővé több cikkből álló azonosítótábla létrehozását a betárolási munka regisztrálása és létrehozása előtt.</span><span class="sxs-lookup"><span data-stu-id="97c91-104">Mixed license plate receiving allows you to build a license plate consisting of multiple items before you register and create put-away work.</span></span> 

<span data-ttu-id="97c91-105">A több cikkből álló azonosítótáblát nem kell felosztani a bevételezési tárolónál minden egyes cikk regisztrálásához.</span><span class="sxs-lookup"><span data-stu-id="97c91-105">A license plate that consists of multiple items does not have to be split at the receiving dock for you to register each item.</span></span> 

<span data-ttu-id="97c91-106">Ha egy cikkel kapcsolatos folyamatot használunk a forrásbizonylat sorainak azonosítására, lehetőség van vonalkódok beolvasására a cikkellenőrzéskor.</span><span class="sxs-lookup"><span data-stu-id="97c91-106">When using an item-related flow to identify the source document lines, you can scan bar codes on the item control.</span></span> <span data-ttu-id="97c91-107">Ha a vonalkódhoz konfigurálva van mennyiség és mértékegység, a rendszer automatikusan hozzáadja a cikket és a mennyiséget a vegyes azonosítótáblához, majd ismét megjeleníti a képernyőt egy másik cikk beolvasásához.</span><span class="sxs-lookup"><span data-stu-id="97c91-107">If the bar code has a quantity and a unit of measure (UOM) configured on it, the item and quantity will automatically be added to the mixed license plate, and you will be returned to the screen to scan another item.</span></span> <span data-ttu-id="97c91-108">Ez lehetővé teszi, hogy gyorsan beolvassa az elemeket anélkül, hogy mindegyik lépésénél el kellene végezni a megerősítést.</span><span class="sxs-lookup"><span data-stu-id="97c91-108">This allows you to quickly scan all the items without having to make a confirmation at each step.</span></span> 

<span data-ttu-id="97c91-109">A vegyes azonosítótábla bevételezésének folyamatában megjelenítheti az azonosítótáblára már beolvasott elemek listáját, és módosíthatja vagy javíthatja a cikkek mennyiségét.</span><span class="sxs-lookup"><span data-stu-id="97c91-109">In the flow for mixed license plate receiving, you can display the list of items that are already scanned to the license plate and from here you can modify or correct the quantity of an item.</span></span>

## <a name="where-it-applies"></a><span data-ttu-id="97c91-110">Alkalmazási kör</span><span class="sxs-lookup"><span data-stu-id="97c91-110">Where it applies</span></span>

<span data-ttu-id="97c91-111">A vegyes azonosítótáblák bevételezése mobileszközös fogadási folyamat munka regisztrálásához és létrehozásához több sorhoz/cikkhez, egy időben.</span><span class="sxs-lookup"><span data-stu-id="97c91-111">Mixed license plate receiving is a mobile device receiving flow to register and create work for multiple lines/items at the same time.</span></span> <span data-ttu-id="97c91-112">Akkor hasznos, ha több cikkből álló bejövő azonosítótáblákat bevételez.</span><span class="sxs-lookup"><span data-stu-id="97c91-112">This is useful if you receive inbound license plates with multiple items.</span></span> 

## <a name="how-to-set-up-mixed-license-plate-receiving"></a><span data-ttu-id="97c91-113">Vegyes azonosítótáblák bevételezésének beállítása</span><span class="sxs-lookup"><span data-stu-id="97c91-113">How to set up mixed license plate receiving</span></span>
<span data-ttu-id="97c91-114">A vegyes azonosítótábla bevételezése mobileszköz-menüelemként van beállítva.</span><span class="sxs-lookup"><span data-stu-id="97c91-114">Mixed license plate receiving is set up as a mobile device menu item.</span></span>

<span data-ttu-id="97c91-115">Létre kell hoznia egy új menüelemet olyan munka móddal, amely nem használ meglévő munkát, és a következő módszerek valamelyikét használja:</span><span class="sxs-lookup"><span data-stu-id="97c91-115">You need to create a new menu item with mode work that does not use existing work and use one of the following methods:</span></span>

- <span data-ttu-id="97c91-116">Vegyes azonosítótábla bevételezése</span><span class="sxs-lookup"><span data-stu-id="97c91-116">Mixed license plate receiving</span></span>
- <span data-ttu-id="97c91-117">Vegyes azonosítótábla bevételezése és eltárolása</span><span class="sxs-lookup"><span data-stu-id="97c91-117">Mixed license plate receiving and put away</span></span>

<span data-ttu-id="97c91-118">A forrásbizonylat sorainak azonosítására szolgáló beállítások a következők: beszerzési rendelés – cikk, beszerzésirendelés-sor, visszárurendelés, átmozgatási rendelés – cikk és átmozgatási rendelés sora.</span><span class="sxs-lookup"><span data-stu-id="97c91-118">The options to identify the source document lines are purchase order item, purchase order line, return order, transfer order item, and transfer order line.</span></span> <span data-ttu-id="97c91-119">Ezek a beállítások módosíthatják a bevételezési rendelést vagy egyetlen azonosítótáblát.</span><span class="sxs-lookup"><span data-stu-id="97c91-119">These options can change the receiving order on a single license plate.</span></span> <span data-ttu-id="97c91-120">Az utolsó beállítás a rakománycikk szerint.</span><span class="sxs-lookup"><span data-stu-id="97c91-120">The last option is by load item.</span></span> <span data-ttu-id="97c91-121">Több cikket lehet hozzáadni egy azonosítótáblához, de több rakomány között nem lehet váltani.</span><span class="sxs-lookup"><span data-stu-id="97c91-121">You can add multiple items to a license plate, but you cannot switch between multiple loads.</span></span>
