---
title: Sorozatszámmal szabályozott termékek visszaküldése a pénztárban
description: Ez a témakör a Microsoft Dynamics 365 Commerce pénztári (POS) alkalmazás visszárufolyamatának részeként a sorozatszámmal rendelkező termékek ellenőrzését írja le.
author: hhainesms
ms.date: 06/01/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: global
ms.author: hhaines
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 7a067994828f3df577c0dc4146d26ac81990d4ac
ms.sourcegitcommit: 927574c77f4883d906e5c7bddf0af9b717e492bf
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/01/2021
ms.locfileid: "6129811"
---
# <a name="return-serial-numbercontrolled-products-in-pos"></a><span data-ttu-id="cb409-103">Sorozatszámmal szabályozott termékek visszaküldése a pénztárban</span><span class="sxs-lookup"><span data-stu-id="cb409-103">Return serial number–controlled products in POS</span></span>

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

<span data-ttu-id="cb409-104">Ez a témakör a Microsoft Dynamics 365 Commerce pénztári (POS) alkalmazás visszárufolyamatának részeként a sorozatszámmal rendelkező termékek ellenőrzését írja le.</span><span class="sxs-lookup"><span data-stu-id="cb409-104">This topic describes the capabilities for validating serialized items as part of the return process in the Microsoft Dynamics 365 Commerce point of sale (POS) application.</span></span>

> [!NOTE]
> <span data-ttu-id="cb409-105">A Commerce 10.0.20 és újabb kiadásaiban , a POS-terminálon elérhető egy új funkció, amelynek neve **Egyesített visszaküldés-feldolgozási élmény a pénztárban**.</span><span class="sxs-lookup"><span data-stu-id="cb409-105">In the Commerce version 10.0.20 release and later, a new feature that is named **Unified return processing experience in POS** is available.</span></span> <span data-ttu-id="cb409-106">Ahhoz, hogy a visszárurendelések feldolgozása során a sorozatszám érvényesség ellenőrzése használható legyen a pénztárban, be kell kapcsolnia ezt a funkciót.</span><span class="sxs-lookup"><span data-stu-id="cb409-106">To use serial number validation during return order processing in POS, you must turn on this feature.</span></span> <span data-ttu-id="cb409-107">A funkció bekapcsolása által biztosított egyéb funkciókkal kapcsolatos tudnivalókat lásd [Visszatérítések létrehozása a pénztárban](POS-returns.md).</span><span class="sxs-lookup"><span data-stu-id="cb409-107">For information about others capabilities that this feature provides when it's turned on, see [Create returns in POS)](POS-returns.md).</span></span>
>
> <span data-ttu-id="cb409-108">A funkciót a bekapcsolása után nem lehet kikapcsolni.</span><span class="sxs-lookup"><span data-stu-id="cb409-108">After the feature is turned on, it can't be turned off.</span></span>

## <a name="options-for-validating-serialized-returns"></a><span data-ttu-id="cb409-109">Szerializált visszaküldések érvényességének ellenőrzésével kapcsolatos beállítások</span><span class="sxs-lookup"><span data-stu-id="cb409-109">Options for validating serialized returns</span></span>

<span data-ttu-id="cb409-110">Ha az **Egyesített visszaküldés-feldolgozási élmény a pénztárban** funkció be van kapcsolva, a szervezetek a pénztáron keresztül ellenőrzést végezhetnek a sorozatszámmal szabályozott cikkek visszaküldéseiben.</span><span class="sxs-lookup"><span data-stu-id="cb409-110">When the **Unified return processing experience in POS** feature is turned on, organizations can perform a validation on returns of serial number–controlled items through POS.</span></span> <span data-ttu-id="cb409-111">Ez a képesség képes figyelmeztetni a felhasználókat, ha a visszaadott sorozatszám eltér az eredeti eladott sorozatszámtól.</span><span class="sxs-lookup"><span data-stu-id="cb409-111">This capability can warn users if the serial number that is being returned differs from the original serial number that was sold.</span></span> <span data-ttu-id="cb409-112">A Commerce 10.0.20 vagy újabb verzióiban a felhasználók által kapott üzenet csak figyelmeztető üzenet.</span><span class="sxs-lookup"><span data-stu-id="cb409-112">In the Commerce version 10.0.20 release and later, the message that users receive is only a warning message.</span></span> <span data-ttu-id="cb409-113">A felhasználók továbbra is feldolgozhatnak egy olyan sorozatszámot, amely eltér az eredetileg eladott sorozatszámtól.</span><span class="sxs-lookup"><span data-stu-id="cb409-113">Users can continue to process a return against a serial number that differs from the serial number that was originally sold.</span></span>

<span data-ttu-id="cb409-114">A **Egyesített visszaküldés-feldolgozási élmény a pénztárban** funkció bekapcsolását követően a sorozatszámok ellenőrzésének bekapcsolásához egy szervezetben válassza a **Kiskereskedelem és kereskedelem \> Központ beállítása \> Paraméterek \> Commerce paraméterek** lehetőséget a Commerce központban.</span><span class="sxs-lookup"><span data-stu-id="cb409-114">To configure serial number validation for an organization after the **Unified return processing experience in POS** feature is turned on, go to **Retail and Commerce \> Headquarters setup \> Parameters \> Commerce parameters** in Commerce headquarters.</span></span> <span data-ttu-id="cb409-115">A **Készlet** lapon az **Üzletkészlet műveletei** gyorslapon állítsa a **Sorozatszámok ellenőrzésének engedélyezése a pénztári visszatérítéseknél** lehetőséget **Igen** értékre.</span><span class="sxs-lookup"><span data-stu-id="cb409-115">On the **Inventory** tab, on the **Store inventory operations** FastTab, set the **Enable validation of serial numbers on POS returns** option to **Yes**.</span></span>

## <a name="process-returns-for-serialized-items-in-pos"></a><span data-ttu-id="cb409-116">Szerializált cikkek visszaküldésének feldolgozása a pénztárban</span><span class="sxs-lookup"><span data-stu-id="cb409-116">Process returns for serialized items in POS</span></span>

<span data-ttu-id="cb409-117">Ha a **Sorozatszámok ellenőrzésének engedélyezése a pénztári visszatérítéseknél** beállítás **Igen** beállításra lett állítva,amikor sorozatszámmal szabályozott cikk visszaadása történik a pénztáron keresztül, a felhasználó megadhatja a visszáru sorozatszámát a **Visszáru-termékek** lap részletek ablakában.</span><span class="sxs-lookup"><span data-stu-id="cb409-117">If the **Enable validation of serial numbers on POS returns** option has been set to **Yes**, when a serial number–controlled item is returned through POS, the user can enter the serial number for the return line in the details pane on the **Returnable products** page.</span></span> <span data-ttu-id="cb409-118">Ha a megadott sorozatszám nem egyezik meg az értékesítési tranzakcióhoz tartozó eredeti sorozatszámmal, a felhasználó figyelmeztető üzenetet kap.</span><span class="sxs-lookup"><span data-stu-id="cb409-118">If the serial number that is entered doesn't match the original serial number that was sold for the sales transaction, the user receives a warning message.</span></span> <span data-ttu-id="cb409-119">Az alkalmazás azonban nem akadályozza meg, hogy a felhasználó továbbra is feladja a visszárut.</span><span class="sxs-lookup"><span data-stu-id="cb409-119">However, the application doesn't prevent the user from continuing to post the return.</span></span>

> [!NOTE]
> <span data-ttu-id="cb409-120">A pénztár jelenleg csak olyan visszárusorok sorozatszámának érvényesítését támogatja, amelyekben az eredeti rendelt mennyiség nem egynél több.</span><span class="sxs-lookup"><span data-stu-id="cb409-120">Currently, POS supports validation of serial numbers only on return lines where the original ordered quantity is no more than one.</span></span> <span data-ttu-id="cb409-121">Ha az eredeti értékesítésirendelés-sor nem a pénztár csatornában jött létre, és az adott értékesítési sorban szerializált cikkhez rendelt mennyiség egynél több, akkor a cikk nem küldhető vissza megfelelően a pénztári terminálon keresztül.</span><span class="sxs-lookup"><span data-stu-id="cb409-121">If the original sales order line was created in a non-POS channel, and if the quantity that was ordered for the serialized item on a given sales line is more than one, the item can't be correctly returned through POS.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="cb409-122">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="cb409-122">Additional resources</span></span>

[<span data-ttu-id="cb409-123">Visszatérítések létrehozása a pénztárban</span><span class="sxs-lookup"><span data-stu-id="cb409-123">Create returns in POS</span></span>](POS-returns.md)
