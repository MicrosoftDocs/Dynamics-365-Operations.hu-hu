---
title: A kivétel kezelésére vonatkozó raktári munka visszavonása
description: Ez a témakör a Munka érvénytelenítése funkciót mutatja be, amellyel a raktár felügyelői kezelhetik a blokkolt munkát.
author: omulvad
manager: tfehr
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSTroubIeshootingSeIfService
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2019-10-1
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: cb725885fb48293a08915f13a4fb14085e930444
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/02/2020
ms.locfileid: "3205805"
---
# <a name="cancel-warehouse-work-for-exception-handling"></a><span data-ttu-id="1b85f-103">A kivétel kezelésére vonatkozó raktári munka visszavonása</span><span class="sxs-lookup"><span data-stu-id="1b85f-103">Cancel warehouse work for exception handling</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="1b85f-104">A Microsoft Dynamics 365 Supply Chain Management Munk érvénytelenítése funkciója lehetővé teszi az adminisztrátor felhasználó számára, hogy jelenleg folyamatban lévő konkrét raktári munkát töröljön, de amit a rendszer blokkolt, vagy nem hajtható végre rendkívüli körülmények miatt.</span><span class="sxs-lookup"><span data-stu-id="1b85f-104">The Cancel work functionality in Microsoft Dynamics 365 Supply Chain Management lets the admin user cancel specific warehouse work that is currently in progress, but that is blocked by the system or can't be completed because of exceptional circumstances.</span></span> <span data-ttu-id="1b85f-105">Ez a funkció vonzó és biztonságos alternatívája az SQL-javító parancsfájloknak, amelyek a nem konzisztens adatokat javítják.</span><span class="sxs-lookup"><span data-stu-id="1b85f-105">This functionality is an attractive and secure alternative to SQL corrective scripts that fix inconsistent data.</span></span> <span data-ttu-id="1b85f-106">Azonban mivel ezeket a parancsfájlokat általában informatikai szakemberektől kell kérni, a munka visszavonása funkciót a vállalat rendszergazdai jogosultságokkal rendelkező felhasználói használhatják.</span><span class="sxs-lookup"><span data-stu-id="1b85f-106">However, whereas these scripts are typically requested from IT professionals, the Cancel work functionality can be used by users in the company who have admin rights.</span></span>

<span data-ttu-id="1b85f-107">A Munka érvénytelenítése funkciót a **Raktárkezelési** \> **Ismétlődő feladatok** \> **Tisztítás \> Munka érvénytelenítése** helyen érheti el.</span><span class="sxs-lookup"><span data-stu-id="1b85f-107">You can access the Cancel work functionality at **Warehouse management** \> **Periodic tasks** \> **Clean up \> Cancel work**.</span></span> <span data-ttu-id="1b85f-108">A **Munka érvénytelenítése** párbeszédpanelen adja meg az érvényteleníteni kívánt munka munkaazonosítóját, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="1b85f-108">In the **Cancel work** dialog box, specify the work ID of the work to cancel, and then select **OK**.</span></span>

## <a name="warehouse-work-that-can-be-canceled"></a><span data-ttu-id="1b85f-109">Nem érvényteleníthető raktári munka</span><span class="sxs-lookup"><span data-stu-id="1b85f-109">Warehouse work that can be canceled</span></span>

<span data-ttu-id="1b85f-110">A raktári kitárolási műveletek során előfordulhat, hogy a dolgozó olyan helyzetekkel találkozik, amikor a tárolási helyről bejegyezték a saját felhasználói helyükre, de ekkor nem tudják regisztrálni a betárolási műveletet.</span><span class="sxs-lookup"><span data-stu-id="1b85f-110">During warehouse picking operations, a worker might encounter situations where they have registered quantities as picked from a storage location to their user location, but then they can't register the put operation.</span></span> <span data-ttu-id="1b85f-111">Az inkonzisztens raktári adatok gyakran, de nem mindig a munka blokkolásának okát jelentik.</span><span class="sxs-lookup"><span data-stu-id="1b85f-111">Inconsistent warehouse data is often, but not always, the reason why work is blocked.</span></span>

<span data-ttu-id="1b85f-112">A szokásos Érvénytelenítés funkcióval szemben, amely az **Érvénytelenítés** gombbal érhető el a munka fejlécében a Munka érvénytelenítése funkcióhoz nem szükséges, hogy az utolsó befejezett munkasor **betárolás** típusú legyen.</span><span class="sxs-lookup"><span data-stu-id="1b85f-112">Unlike the regular Cancel functionality that can be accessed by using the **Cancel** button on the work header, the Cancel work functionality doesn't require that the last completed work line be a work line of the **put** type.</span></span> <span data-ttu-id="1b85f-113">Más szóval a munka érvénytelenítése funkció esetében a visszavonási logika akkor is futtatható, ha egy munkasorban szereplő cikkmennyiség egy felhasználói helyen van.</span><span class="sxs-lookup"><span data-stu-id="1b85f-113">In other words, for the Cancel work functionality, cancellation logic can be run even if the item quantity on a work line is in a user location.</span></span>

> [!NOTE]
> <span data-ttu-id="1b85f-114">A működési okokból érvénytelenítendő munkákhoz a raktári felhasználók toovábbra is a szokásos Érvénytelenítés funkciót kell használják a munka oldalon.</span><span class="sxs-lookup"><span data-stu-id="1b85f-114">For work that must be canceled for operational reasons, warehouse users must continue to use the regular Cancel functionality on the work page.</span></span>

<span data-ttu-id="1b85f-115">A munka visszavonása funkcióval csak az **Értékesítés**, **Átmozgatási probléma** **Nyersanyag kitárolása** vagy **Újratöltés** típusok érvényteleníthetők.</span><span class="sxs-lookup"><span data-stu-id="1b85f-115">Only work of the **Sales**, **Transfer issue**, **Raw material picking**, or **Replenishment** type can be canceled by using the Cancel work functionality.</span></span> <span data-ttu-id="1b85f-116">Az érvénytelenítési logika nem futtatható a nyersanyag-kitárolási munkához vagy olyan munkához, amelyet a szokásos megszakítás funkcióval is érvényteleníteni lehet (lásd az előző megjegyzést).</span><span class="sxs-lookup"><span data-stu-id="1b85f-116">Cancellation logic won't be run for frozen raw material picking work or work that can be canceled by using the regular Cancel functionality (see the preceding note).</span></span>

<span data-ttu-id="1b85f-117">A munka blokkolásának feloldásához a rendszer törli a hátralévő munkasorokat, és rögzíti a munkaazonosítóhoz társított felhasználó által megadott raktári adatokat.</span><span class="sxs-lookup"><span data-stu-id="1b85f-117">To unblock the work, the system cancels any remaining work lines and fixes the warehouse data that is associated with the work ID that the user specified.</span></span> <span data-ttu-id="1b85f-118">A program ezután folytatja az érintett cikkmennyiséget magába foglaló szokásos raktárkezelési műveleteket.</span><span class="sxs-lookup"><span data-stu-id="1b85f-118">Any regular warehouse-handling operations that involve the affected item quantity can then resume.</span></span>

<span data-ttu-id="1b85f-119">Ha azt szeretné, hogy az érintett elem egy meghatározott helyre kerüljön a munka érvénytelenítése után, a felhasználónak egy készletmozgatás mennyiségi helyesbítési műveletét kell használnia egy mobileszközön.</span><span class="sxs-lookup"><span data-stu-id="1b85f-119">To put the affected item in a specific location after the work is canceled, the user must use an inventory movement or quantity adjustment operation on a mobile device.</span></span>
