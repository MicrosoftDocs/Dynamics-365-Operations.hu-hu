---
title: Lízingparaméterek konfigurálása (előzetes verzió)
description: Ez a témakör az Eszközlízing konfigurációs beállításait ismerteti, például a biztonsági információkat és a számlázási beállításokat.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: ff0aa5fd0b78814dfa5bb00d6d5ef2984c566d14
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4971403"
---
# <a name="configure-lease-parameters"></a><span data-ttu-id="91d19-103">Lízingparaméterek konfigurálása</span><span class="sxs-lookup"><span data-stu-id="91d19-103">Configure lease parameters</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="91d19-104">Számos konfigurációs beállítás befolyásolja az Eszközlízing működését.</span><span class="sxs-lookup"><span data-stu-id="91d19-104">Several configuration settings affect how Asset leasing behaves.</span></span> <span data-ttu-id="91d19-105">Ezek közé a beállítások közé tartoznak a naplónevek, az általános paraméterek és a feladási profil beállításai.</span><span class="sxs-lookup"><span data-stu-id="91d19-105">These settings include journal names, general parameters, and posting profile settings.</span></span>

1. <span data-ttu-id="91d19-106">Nyissa meg az **Eszközlízing \> Beállítás \> Eszközlízing paraméterei** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="91d19-106">Go to **Asset leasing \> Setup \> Asset leasing parameters**.</span></span>
2. <span data-ttu-id="91d19-107">A **Lízingek** fülön válassza az **Általános** gyorslapot.</span><span class="sxs-lookup"><span data-stu-id="91d19-107">On the **Leases** tab, select the **General** FastTab.</span></span>

    <span data-ttu-id="91d19-108">A **Manuális osztályzás felülbírálásának engedélyezése** paraméter határozza meg, hogy a lízingosztályzás felülbírálható-e a fizetési ütemezés visszautasítása előtt.</span><span class="sxs-lookup"><span data-stu-id="91d19-108">The **Allow manual classification override** parameter determines whether the lease classification can be overridden before the payment schedule is confirmed.</span></span>

    <span data-ttu-id="91d19-109">Az **Entitások közötti köteg** paraméter határozza meg, hogy könyvelhet-e más jogi személyeknek az aktuális jogi személytől.</span><span class="sxs-lookup"><span data-stu-id="91d19-109">The **Cross-entity batch** parameter determines whether you can post to other legal entities from the current legal entity.</span></span> <span data-ttu-id="91d19-110">Ha ez a paraméter be van kapcsolva, naplóbejegyzéseket hozhat létre azon jogi személyek számára, amelyekhez hozzáférése van.</span><span class="sxs-lookup"><span data-stu-id="91d19-110">If this parameter is turned on, you can create journal entries for the legal entities that you have access to.</span></span>

3. <span data-ttu-id="91d19-111">A **Visszaigazolt lízingek törlésének engedélyezése** beállítást állítsa **Igen** értékre a visszaigazolt fizetési ütemezéseket tartalmazó lízingek törlésének engedélyezéséhez.</span><span class="sxs-lookup"><span data-stu-id="91d19-111">Set the **Allow delete of confirmed leases** option to **Yes** to allow leases that have confirmed payment schedules to be deleted.</span></span> <span data-ttu-id="91d19-112">A lízingek nem törölhetők, ha feladott vagy fel nem adott tranzakciók vannak társítva, függetlenül ennek a lehetőségnek a beállításától.</span><span class="sxs-lookup"><span data-stu-id="91d19-112">Leases can't be deleted if posted or unposted transactions are associated with them, regardless of the setting of this option.</span></span> <span data-ttu-id="91d19-113">A lízingrekord törlés után nem állítható vissza.</span><span class="sxs-lookup"><span data-stu-id="91d19-113">You can't restore a lease record after it's deleted.</span></span> <span data-ttu-id="91d19-114">Ha egy törölt lízinghez tartalmazó rekordokat manuálisan vagy adatentitásokon keresztül tölt fel, a feltöltött adatokat a rendszer újként kezeli, nem pedig egy meglévő lízing frissítéseként.</span><span class="sxs-lookup"><span data-stu-id="91d19-114">If you upload any records for a deleted lease, either manually or through data entities, the uploaded information is treated as new, not as an update to an existing lease.</span></span>

    <span data-ttu-id="91d19-115">Ha ezt a beállítást **Igen** értékre állítja, és a könyv átmeneti típusa az **A vagy B kumulatív felzárkózási lehetőség**, akkor a rendszer a **Járulékos kamatláb** mezőt a **Könyv beállítása** lap átmeneti mezőjében lévő **Járulékos kamatláb váltás alatt** értékére állítja be.</span><span class="sxs-lookup"><span data-stu-id="91d19-115">If you set this option to **Yes**, and the transition type of the book is **Cumulative Catchup Option A or B**, the system sets the **Incremental borrowing rate** field to the value of the **Incremental borrowing rate at transition** field on the **Book setup** page.</span></span> <span data-ttu-id="91d19-116">Ha ez a lehetőség **Nem** értékre van állítva, akkor a fő lízing kamatlába a **Könyv részletei** lap **Járulékos kamatláb** értékű lesz, függetlenül a könyv átváltási típusától.</span><span class="sxs-lookup"><span data-stu-id="91d19-116">If this option is set to **No**, the rate on the head lease is set to the value of the **Incremental borrowing rate** field on the **Book details** page, regardless of the transition type of the book.</span></span>

4. <span data-ttu-id="91d19-117">Állítsa az **Értékcsökkenés sztornírozásának engedélyezése a lezárt könyv verzión** beállítást **Igen** értékre az értékcsökkenési költség tranzakciók sztornírozásának engedélyezéséhez.</span><span class="sxs-lookup"><span data-stu-id="91d19-117">Set the **Allow depreciation reversals on closed book version** option to **Yes** to allow depreciation expense transactions to be reversed.</span></span> <span data-ttu-id="91d19-118">A költségtranzakciók akkor is sztornírozhatók, ha a könyv verziója le van zárva.</span><span class="sxs-lookup"><span data-stu-id="91d19-118">Expense transactions can be reversed even when the book version is closed.</span></span>

    > [!NOTE]
    > <span data-ttu-id="91d19-119">Javasoljuk, hogy tartsa ezt a beállítást **Nem** értéken.</span><span class="sxs-lookup"><span data-stu-id="91d19-119">We recommend that you keep this option set to **No**.</span></span> <span data-ttu-id="91d19-120">Ennek a lehetőségnek a beállítása ellenőrzésként és vezérlésként szolgál, hogy megakadályozza a zárt könyvverzió véletlen értékcsökkenését.</span><span class="sxs-lookup"><span data-stu-id="91d19-120">The setting of this option is used as a validation and control to prevent a closed book version from being accidently depreciated.</span></span> <span data-ttu-id="91d19-121">Ha a beállításr **Nem** értéken tartja, akkor a nettó könyv szerinti érték és a jövőbeli értékcsökkenési számítások pontosak maradnak.</span><span class="sxs-lookup"><span data-stu-id="91d19-121">By keeping the option set to **No**, you help keep the net book value and future depreciation calculations accurate.</span></span>
