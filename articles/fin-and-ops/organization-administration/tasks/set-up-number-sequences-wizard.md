--- 
title: "Állítson be minden szükséges számsorozatot a varázsló segítségével"
description: "A számsorozatokat az alapadatok és az azokat igénylő tranzakciós bejegyzések olvasható, egyedi azonosítóinak létrehozására használja a rendszer."
author: sericks007
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Operations
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: e7d988cd1261c00925ad7ae612a947a0083028ee
ms.contentlocale: hu-hu
ms.lasthandoff: 04/13/2018

---
# <a name="set-up-number-sequences-by-using-a-wizard"></a><span data-ttu-id="8d041-103">Állítson be minden szükséges számsorozatot a varázsló segítségével</span><span class="sxs-lookup"><span data-stu-id="8d041-103">Set up number sequences by using a wizard</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="8d041-104">A számsorozatokat az alapadatok és az azokat igénylő tranzakciós bejegyzések olvasható, egyedi azonosítóinak létrehozására használja a rendszer.</span><span class="sxs-lookup"><span data-stu-id="8d041-104">Number sequences are used to generate readable, unique identifiers for master data records and transaction records that require them.</span></span> <span data-ttu-id="8d041-105">Az azonosítókat igénylő alapadatokat és tranzakciós bejegyzéseket hivatkozásnak nevezik.</span><span class="sxs-lookup"><span data-stu-id="8d041-105">A master data or transaction record that requires an identifier is referred to as a reference.</span></span> <span data-ttu-id="8d041-106">Egy hivatkozáshoz tartozó új rekordok létrehozása előtt be kell állítania egy számsorozatot, és a hivatkozáshoz társítani.</span><span class="sxs-lookup"><span data-stu-id="8d041-106">Before you can create new records for a reference, you must set up a number sequence and associate it with the reference.</span></span> <span data-ttu-id="8d041-107">Ez az eljárás bemutatja, hogyan tudja egyszerre beállítani az összes szükséges számsorozatot egy varázsló segítségével.</span><span class="sxs-lookup"><span data-stu-id="8d041-107">This procedure explains how to set up all required number sequences at the same time by using a wizard.</span></span> <span data-ttu-id="8d041-108">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="8d041-108">The demo data company used to create this procedure is USMF.</span></span>

1. <span data-ttu-id="8d041-109">Ugorjon a Szervezeti adminisztráció > Számsorozatok > Számsorozatokra pontra.</span><span class="sxs-lookup"><span data-stu-id="8d041-109">Go to Organization administration > Number sequences > Number sequences.</span></span>
2. <span data-ttu-id="8d041-110">Kattintson a Létrehozás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="8d041-110">Click Generate.</span></span>
3. <span data-ttu-id="8d041-111">Kattintson a Tovább gombra.</span><span class="sxs-lookup"><span data-stu-id="8d041-111">Click Next.</span></span>
    * <span data-ttu-id="8d041-112">Ezen az oldalon módosíthatja az azonosító kódot, a legkisebb és a legnagyobb értéket.</span><span class="sxs-lookup"><span data-stu-id="8d041-112">On this page, you can modify the identification code, the lowest value, and the highest value.</span></span> <span data-ttu-id="8d041-113">Ezenkívül megadhatja, hogy a számsorozatnak folyamatosnak kell-e lennie.</span><span class="sxs-lookup"><span data-stu-id="8d041-113">In addition, you can indicate whether the number sequence must be continuous.</span></span>   
    * <span data-ttu-id="8d041-114">Ne jelölje be a Folyamatos lehetőséget, ha előzetesen le kell foglalnia számokat a számsorozathoz.</span><span class="sxs-lookup"><span data-stu-id="8d041-114">Do not select the Continuous option if you must preallocate numbers for the number sequence.</span></span>     <span data-ttu-id="8d041-115">Egy számsorozat formátumához úgy adhat hozzá egy hatókörszegmenst, hogy a listában kiválasztja a formátumot, majd rákattint a Hatókör belefoglalása a formátumba gombra.</span><span class="sxs-lookup"><span data-stu-id="8d041-115">To add a scope segment to the format of a number sequence, select the format in the list, and then click Include scope in format.</span></span>     <span data-ttu-id="8d041-116">Egy számsorozat formátumából úgy vehet el egy hatókörszegmenst, hogy a listában kiválasztja a formátumot, majd rákattint a Hatókör eltávolítása a formátumból gombra.</span><span class="sxs-lookup"><span data-stu-id="8d041-116">To remove a scope segment from the format of a number sequence, select the format in the list, and then click Remove scope from format.</span></span>     <span data-ttu-id="8d041-117">Egy számsorozatnak az automatikus létrehozásból való kizárásához válassza ki a számsorozatot a listában, és kattintson a Törlés gombra.</span><span class="sxs-lookup"><span data-stu-id="8d041-117">To exclude a number sequence from automatic generation, select the number sequence in the list, and then click Delete.</span></span>  
4. <span data-ttu-id="8d041-118">Kattintson a Tovább gombra.</span><span class="sxs-lookup"><span data-stu-id="8d041-118">Click Next.</span></span>
5. <span data-ttu-id="8d041-119">Kattintson a Finish gombra.</span><span class="sxs-lookup"><span data-stu-id="8d041-119">Click Finish.</span></span>


