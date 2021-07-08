---
title: Az adatpiac alaphelyzetbe állítása – GYIK
description: Ez a témakör az adatpiac alaphelyzetbe állításával kapcsolatos néhány gyakran ismételt kérdésre ad választ.
author: jinniew
ms.date: 06/09/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2021-05-06
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 7cd96c7bc698986ef1ef07ca88479a3d49f22924
ms.sourcegitcommit: ecabf43282a3e55f1db40341aa3f3c7950b9e94c
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/16/2021
ms.locfileid: "6266609"
---
# <a name="data-mart-resets-faq"></a><span data-ttu-id="1fcba-103">Az adatpiac alaphelyzetbe állítása – GYIK</span><span class="sxs-lookup"><span data-stu-id="1fcba-103">Data mart resets FAQ</span></span>

<span data-ttu-id="1fcba-104">Ez a témakör az adatpiac alaphelyzetbe állításával kapcsolatos néhány gyakran ismételt kérdésre ad választ.</span><span class="sxs-lookup"><span data-stu-id="1fcba-104">This topic provides answers to some frequently asked questions about data mart resets.</span></span> <span data-ttu-id="1fcba-105">Az adatpiac alaphelyzetbe állítása időigényes folyamat lehet, és a körülményektől függően előfordulhat, hogy nem ez a megoldás szükséges.</span><span class="sxs-lookup"><span data-stu-id="1fcba-105">A reset of the data mart can be a time-consuming process and, depending on the circumstances, might not be the solution that is required.</span></span> <span data-ttu-id="1fcba-106">Ennek megfelelően ez a témakör tájékoztatást nyújt az olyan körülményekről, amikor az adatpiac alaphelyzetbe állítása segíthet, illetve az olyan körülményekről, amikor valószínűleg nem segít.</span><span class="sxs-lookup"><span data-stu-id="1fcba-106">Therefore, this topic includes information about circumstances where a data mart reset might help and also circumstances where it's unlikely to help.</span></span>

## <a name="what-is-a-data-mart-reset"></a><span data-ttu-id="1fcba-107">Mit jelent az adatpiac alaphelyzetbe állítása?</span><span class="sxs-lookup"><span data-stu-id="1fcba-107">What is a data mart reset?</span></span>

<span data-ttu-id="1fcba-108">Az adatpiac alaphelyzetbe állítása letiltja az integrációs feladatokat, törli az adatpiac összes adatát, majd újra engedélyezi az integrációt.</span><span class="sxs-lookup"><span data-stu-id="1fcba-108">A data mart reset will disable the integration tasks, delete all the data mart data, and then re-enable integration.</span></span>

<span data-ttu-id="1fcba-109">Annak érdekében, hogy a rendszer ne szúrjon be régi adatokat, az adatpiac visszaállítása csak a meglévő feladatok befejeződése után kezdődik el.</span><span class="sxs-lookup"><span data-stu-id="1fcba-109">To ensure that old data isn't inserted, a data mart reset can be started only after existing tasks are completed.</span></span> <span data-ttu-id="1fcba-110">Ha az összes feladat befejezése előtt próbálja alaphelyzetbe állítani az adatpiacot, a következőhöz hasonló üzenet jelenik meg: „Az adatpiac visszaállítását egy aktív feladat miatt nem sikerült feldolgozni.</span><span class="sxs-lookup"><span data-stu-id="1fcba-110">If you try to reset the data mart before all tasks are completed, you might receive a message such as, "The data mart reset was unable to be processed because of an active task.</span></span> <span data-ttu-id="1fcba-111">Próbálkozzon újra később.”</span><span class="sxs-lookup"><span data-stu-id="1fcba-111">Please try again later."</span></span>

## <a name="when-do-i-have-to-do-a-data-mart-reset"></a><span data-ttu-id="1fcba-112">Mikor kell alaphelyzetbe állítanom az adatpiacot?</span><span class="sxs-lookup"><span data-stu-id="1fcba-112">When do I have to do a data mart reset?</span></span>

<span data-ttu-id="1fcba-113">Ha a következők közül egy vagy több érvényes, akkor a szervezete számára hasznos lehet az adatpiac alaphelyzetbe állítása:</span><span class="sxs-lookup"><span data-stu-id="1fcba-113">If one or more of the following statements apply to your situation, your organization can benefit from a data mart reset:</span></span>

- <span data-ttu-id="1fcba-114">Az alkalmazás-adatbázis vissza lett állítva.</span><span class="sxs-lookup"><span data-stu-id="1fcba-114">The application database was restored.</span></span>
- <span data-ttu-id="1fcba-115">Támogatási jegyet nyitott meg, és egy ügyfélszolgálati szakértő arra utasítja, hogy állítsa vissza az adatpiacot egy hibaelhárítási lépés részeként.</span><span class="sxs-lookup"><span data-stu-id="1fcba-115">You opened a support ticket, and a Support engineer instructed you to reset the data mart as part of a troubleshooting step.</span></span>
 
## <a name="when-is-a-data-mart-reset-inappropriate"></a><span data-ttu-id="1fcba-116">Mikor nem megfelelő lépés az adatpiac alaphelyzetbe állítása?</span><span class="sxs-lookup"><span data-stu-id="1fcba-116">When is a data mart reset inappropriate?</span></span>

<span data-ttu-id="1fcba-117">Az alábbi körülmények között nem ajánljuk az adatpiac alaphelyzetbe állítását:</span><span class="sxs-lookup"><span data-stu-id="1fcba-117">Here are some of the circumstances where we don't recommend that you reset the data mart:</span></span>

- <span data-ttu-id="1fcba-118">Adatszinkronizálással kapcsolatos teljesítményproblémákat tapasztal.</span><span class="sxs-lookup"><span data-stu-id="1fcba-118">You're experiencing performance issues that are associated with data synchronization.</span></span>
- <span data-ttu-id="1fcba-119">A következő okok valamelyike miatt ismétlődik az alaphelyzetbe állítás:</span><span class="sxs-lookup"><span data-stu-id="1fcba-119">You have a recurring reset pattern for any of the following reasons:</span></span>

    - <span data-ttu-id="1fcba-120">**Hiányzó adatok** – ha azt veszi észre, hogy adatok hiányoznak, nyisson támogatási jegyet a Microsofttal, hogy ellenőrizze a jelentés formátumát és az esetleges szinkronizálási problémákat.</span><span class="sxs-lookup"><span data-stu-id="1fcba-120">**Missing data** – If you notice that data is missing, open a support ticket with Microsoft to review your report format and possible data synchronization issues.</span></span>
    - <span data-ttu-id="1fcba-121">**Elakadt integrációs állapot**</span><span class="sxs-lookup"><span data-stu-id="1fcba-121">**Stuck integration state**</span></span>
    - <span data-ttu-id="1fcba-122">**Elavult rekordok** – Az elavult rekordok önmagukban nem feltétlenül igazolják az adatpiac alaphelyzetbe állítását.</span><span class="sxs-lookup"><span data-stu-id="1fcba-122">**Stale records** – Stale records by themselves don't necessarily justify a data mart reset.</span></span> <span data-ttu-id="1fcba-123">Ha nagy adatkészlet van beállítva, az alaphelyzetbe állítási folyamat futása időt vesz igénybe, de nem valószínű, hogy ez javulást eredményez.</span><span class="sxs-lookup"><span data-stu-id="1fcba-123">If you have a large data set, the reset process will take some time to run but is unlikely to lead to any improvement.</span></span>

## <a name="if-i-reset-the-data-mart-will-i-lose-reports-that-ive-already-designed"></a><span data-ttu-id="1fcba-124">Ha alaphelyzetbe állítom az adatpiacot, elvesznek a már megtervezett jelentések?</span><span class="sxs-lookup"><span data-stu-id="1fcba-124">If I reset the data mart, will I lose reports that I've already designed?</span></span>

<span data-ttu-id="1fcba-125">Nem.</span><span class="sxs-lookup"><span data-stu-id="1fcba-125">No.</span></span> <span data-ttu-id="1fcba-126">A jelentések olyan SQL-táblákban vannak tárolva, amelyekre nincs hatással az adatpiac alaphelyzetbe állítása.</span><span class="sxs-lookup"><span data-stu-id="1fcba-126">Your reports are stored in SQL tables that aren't affected by a data mart reset.</span></span> <span data-ttu-id="1fcba-127">Ha aggódik a megtervezett jelentések elvesztése miatt, biztonsági másolatot készíthet a megőrizni kívánt tervekről.</span><span class="sxs-lookup"><span data-stu-id="1fcba-127">If you're concerned about losing reports that you've designed, you can back up the designs that you don't want to lose.</span></span> <span data-ttu-id="1fcba-128">A tervek biztonsági mentéséhez nyissa meg a Report Designert, és lépjen a **Vállalat \> Vállalatok \> Építőelemek \> Exportálás** részre.</span><span class="sxs-lookup"><span data-stu-id="1fcba-128">To back up designs, open Report Designer, and go to **Company \> Companies \> Building Blocks \> Export**.</span></span>
 
## <a name="do-all-users-have-to-exit-the-system-before-i-can-reset-the-data-mart"></a><span data-ttu-id="1fcba-129">Minden felhasználónak ki kell lépnie a rendszerből az adatpiac alaphelyzetbe állításához?</span><span class="sxs-lookup"><span data-stu-id="1fcba-129">Do all users have to exit the system before I can reset the data mart?</span></span>

<span data-ttu-id="1fcba-130">Nem.</span><span class="sxs-lookup"><span data-stu-id="1fcba-130">No.</span></span> <span data-ttu-id="1fcba-131">A felhasználók dolgozhatnak a rendszerben az adatpiac alaphelyzetbe állítása során.</span><span class="sxs-lookup"><span data-stu-id="1fcba-131">Users can continue to work in the system during a data mart reset.</span></span> <span data-ttu-id="1fcba-132">Az alaphelyzetbe állítás befejeződéséig azonban nem férhetnek hozzá a Financial Reporter használatával létrehozott jelentésekhez.</span><span class="sxs-lookup"><span data-stu-id="1fcba-132">However, until the reset is completed, users won't be able to access any reports that were created by using Financial Reporter.</span></span>

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
