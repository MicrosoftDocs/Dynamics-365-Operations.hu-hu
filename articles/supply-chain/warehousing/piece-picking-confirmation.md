---
title: Darabkitárolás megerősítése
description: A darabkitárolás lehetővé teszi, hogy minden egyes készletet mobileszközön végzett kitárolási vagy leltározási munka segítségével hagyjon jóvá.
author: Mirzaab
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSRFAutoConfirm, WHSRFMenuItem
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3f9da533998341de60d210e196baae64d285d372
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5818848"
---
# <a name="piece-picking-confirmation"></a><span data-ttu-id="bfbe0-103">Darabkitárolás megerősítése</span><span class="sxs-lookup"><span data-stu-id="bfbe0-103">Piece picking confirmation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="bfbe0-104">A darabkitárolás lehetővé teszi, hogy minden egyes készletet mobileszközön végzett kitárolási vagy leltározási munka segítségével hagyjon jóvá.</span><span class="sxs-lookup"><span data-stu-id="bfbe0-104">Piece picking allows you to confirm each piece of inventory through picking or counting work on a mobile device.</span></span> <span data-ttu-id="bfbe0-105">A kitároláshoz megersítheti a feldolgozandó munka mennyiségét a kitárolni kívánt mennyiségére vonatkoztatva.</span><span class="sxs-lookup"><span data-stu-id="bfbe0-105">For picks, you can confirm the quantity of work to be processed up to the quantity that is specified on work to be picked.</span></span> <span data-ttu-id="bfbe0-106">Leltározási munka esetén beolvashatja a leltározandó készletet, és nyomon követheti a teljes mennyiséget.</span><span class="sxs-lookup"><span data-stu-id="bfbe0-106">For counting work, you can scan the inventory you are counting and track the total amount.</span></span>

<span data-ttu-id="bfbe0-107">Darabkitárolás engedélyezésekor a program automatikusan kijelöli a termék megerősítése lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="bfbe0-107">When you enable piece picking, product confirmation is automatically selected.</span></span> <span data-ttu-id="bfbe0-108">Munkatípusú kitárolás esetén beállíthatja a maximális darabszámot.</span><span class="sxs-lookup"><span data-stu-id="bfbe0-108">For work-type picks, you can set a maximum number of pieces.</span></span> <span data-ttu-id="bfbe0-109">Ez lehetővé teszi a munka során kötelezően megerősítendő darabok maximumának beállítását.</span><span class="sxs-lookup"><span data-stu-id="bfbe0-109">This allows you to set a maximum to the number of pieces that must be confirmed during the work process.</span></span> <span data-ttu-id="bfbe0-110">A maximális mennyiség a feldolgozás alatt álló aktuális munkaegységen alapul.</span><span class="sxs-lookup"><span data-stu-id="bfbe0-110">The maximum quantity is based on the current work unit that is being processed.</span></span> <span data-ttu-id="bfbe0-111">A leltározási munkatípus esetében nincs maximum.</span><span class="sxs-lookup"><span data-stu-id="bfbe0-111">The counting work type does not allow a maximum.</span></span>

<span data-ttu-id="bfbe0-112">A beolvasott vonalkódhoz társított mennyiséget és mértékegységet is használhatja.</span><span class="sxs-lookup"><span data-stu-id="bfbe0-112">You can also use the quantity and unit of measure (UOM) that is associated with a scanned bar code.</span></span> <span data-ttu-id="bfbe0-113">Ez működik a bejövő folyamatok esetén, beleértve a vegyes azonosítótáblák bevételezését, a beszerzési rendelési cikket, az átmozgatási rendelési cikket és a rakománycikket.</span><span class="sxs-lookup"><span data-stu-id="bfbe0-113">This will work for receiving on inbound flows including mixed license plate receiving, purchase order item, transfer order item, and load item.</span></span> <span data-ttu-id="bfbe0-114">Működik a darabkitárolás esetén is, ahol a vonalkód beolvasása hozzáadja a mennyiséget a megerősített darabok számához, a konvertálás pedig a vonalkódon levő mértékegység és a munkaegység között történik.</span><span class="sxs-lookup"><span data-stu-id="bfbe0-114">It also works for piece picking where scanning the bar code will add the quantity to the total number of confirmed pieces converting between the UOM on the bar code and the work unit.</span></span> <span data-ttu-id="bfbe0-115">Ha a vonalkódon levő mértékegység leltározása során megerősítést nyer, hogy a mennyiség engedélyezve van a szekvenciacsoport leltározásához, a mennyiséget a rendszer hozzáadja a teljes számhoz.</span><span class="sxs-lookup"><span data-stu-id="bfbe0-115">When counting the UOM on the bar code, if it is confirmed that the quantity is allowed for counting on the sequence group, the quantity will be added to the total count.</span></span>

## <a name="where-it-applies"></a><span data-ttu-id="bfbe0-116">Alkalmazási kör</span><span class="sxs-lookup"><span data-stu-id="bfbe0-116">Where it applies</span></span>

<span data-ttu-id="bfbe0-117">A darabkitárolás minden leltározási munka esetén és bármilyen munkatípus kezdeti kitárolása esetén működik</span><span class="sxs-lookup"><span data-stu-id="bfbe0-117">Piece picking works for all counting work and for the initial pick for any type of work.</span></span> <span data-ttu-id="bfbe0-118">A darabkitárolás nem alkalmazható, hogy a cikket sorozatszámok vezérlik, vagy ha a cikk egy termelési vagy kanbankitárolás egy azonosítótáblával szabályozott helyről, és a cikk előkészítésre van beállítva.</span><span class="sxs-lookup"><span data-stu-id="bfbe0-118">Piece picking does not apply if the item is controlled by serial numbers or if it is a production or kanban pick from a license plate (LP) location and the item is set to staging.</span></span>

## <a name="set-up-piece-picking"></a><span data-ttu-id="bfbe0-119">Darabkitárolás beállítása</span><span class="sxs-lookup"><span data-stu-id="bfbe0-119">Set up piece picking</span></span>

1.  <span data-ttu-id="bfbe0-120">A mobileszköz menüpontjában nyissa meg a munkamegerősítés beállítási képernyőjét: Raktárkezelés > **Raktárkezelés** > **Beállítás** > **Mobileszköz** > **Mobileszköz menüpontjai**.</span><span class="sxs-lookup"><span data-stu-id="bfbe0-120">On a mobile device menu item, open the setup form for work confirmation: Warehouse management > **Warehouse management** > **Setup** > **Mobile device** > **Mobile device menu items**.</span></span> 
2. <span data-ttu-id="bfbe0-121">A mobileszköz menüpontjából nyissa meg a Munkamegerősítés beállítását.</span><span class="sxs-lookup"><span data-stu-id="bfbe0-121">From the mobile device menu item, open Work confirmation setup.</span></span>

<span data-ttu-id="bfbe0-122">A következő lehetőségek közül választhat, ha a munka típusa kitárolás vagy leltározás.</span><span class="sxs-lookup"><span data-stu-id="bfbe0-122">The following options become available for selection when the work type is pick or counting.</span></span>


|           <span data-ttu-id="bfbe0-123">Lehetőség</span><span class="sxs-lookup"><span data-stu-id="bfbe0-123">Option</span></span>           |                                                                            <span data-ttu-id="bfbe0-124">Leírás</span><span class="sxs-lookup"><span data-stu-id="bfbe0-124">Description</span></span>                                                                            |
|----------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="bfbe0-125">Darab kitárolásának megerősítése</span><span class="sxs-lookup"><span data-stu-id="bfbe0-125">Piece picking confirmation</span></span> | <span data-ttu-id="bfbe0-126">Elérhető kitárolási és leltározási munkatípusok esetében.</span><span class="sxs-lookup"><span data-stu-id="bfbe0-126">Available for pick and counting work types.</span></span> <span data-ttu-id="bfbe0-127">A termék megerősítése automatikusan be van jelölve.</span><span class="sxs-lookup"><span data-stu-id="bfbe0-127">Product confirmation is automatically selected.</span></span> <span data-ttu-id="bfbe0-128">Lehetővé teszi, hogy a mobileszközről erősítse meg a készlet minden elemét.</span><span class="sxs-lookup"><span data-stu-id="bfbe0-128">Allows you to confirm each piece of inventory from the mobile device.</span></span> |
|  <span data-ttu-id="bfbe0-129">Darabok maximális száma</span><span class="sxs-lookup"><span data-stu-id="bfbe0-129">Maximum number of pieces</span></span>  |                   <span data-ttu-id="bfbe0-130">Elérhető kitárolási munkához, ha a darabkitárolás megerősítése engedélyezve van.</span><span class="sxs-lookup"><span data-stu-id="bfbe0-130">Available for pick work if piece picking confirmation is enabled.</span></span> <span data-ttu-id="bfbe0-131">Beállítja a megerősítendő darabszám maximális értékét.</span><span class="sxs-lookup"><span data-stu-id="bfbe0-131">Sets a limit to the number of pieces that you must confirm.</span></span>                   |



[!INCLUDE[footer-include](../../includes/footer-banner.md)]