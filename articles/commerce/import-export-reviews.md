---
title: Értékelések és véleményezések importálása és exportálása
description: Ez a témakör azt ismerteti, hogyan lehet importálni és exportálni a termékminősítéseket és -értékeléseket a következőben:Microsoft Dynamics 365 Commerce
author: gvrmohanreddy
ms.date: 01/12/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgri
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2017-06-20
ms.openlocfilehash: 97407f62d462c0ae370e9ea0d2799d3f30ecacfa
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8863401"
---
# <a name="import-and-export-ratings-and-reviews"></a>Értékelések és véleményezések importálása és exportálása

[!include [banner](includes/banner.md)]

Ez a témakör azt ismerteti, hogyan lehet importálni és exportálni a termékminősítéseket és -értékeléseket a következőben:Microsoft Dynamics 365 Commerce

A Dynamics 365 Commerce [minősítéseket és értékeléseket](ratings-reviews-overview.md) kínál omnicsatornás megoldásként. Amikor a Dynamics 365 Commerce Minősítések és áttekintések megoldásra vált, érdemes lehet a meglévő értékeléseket áthelyezni, és az adatokat át kell vizsgálni a Commerce platformra. Az üzleti követelmények alapján előfordulhat, hogy exportálni szeretné a minősítéseket, és áttekinti a Commerce rendszerből származó adatokat. A Power Automate csatlakoztató segítségével minősítéseket és értékeléseket importálhat a Commerce rendszerből, és exportálhatja azokat a Commerce rendszerből.

> [!NOTE]
> A logikai folyamatokkal Power Automate való első lépésekről a Következőben található [Felhőáramlás létrehozása a Power Automate-ben](/power-automate/get-started-logic-flow).

## <a name="prerequisites"></a>Előfeltételek

A minősítések és az ellenőrzések importálása és exportálása előtt teljesítenie kell a következő előfeltételeket:

- A minősítéseket és az áttekintési megoldást engedélyezni kell a Commerce platformon található e-commerce webhelyen. A további tudnivalókat lásd [Értékelések és áttekintések használatának engedélyezése](opt-in-ratings-reviews.md)
- A Dynamics 365 minősítéseket és a Reviews Power App Connector alkalmazást úgy kell beállítani, hogy lehetővé tegye az "Ellenőrzés elküldése" vagy az "Export reviews" műveleteket a Power Automate-szolgáltatásban. A további tudnivalókat lásd [Dynamics 365 Commerce – Minősítések és értékelések (Előnézet)](/connectors/dynamics365ratingsre/).
- A szolgáltatás-szolgáltatás (S2S) hitelesítést úgy kell konfigurálni, hogy biztonságosan hívható legyen a Commerce rendszerből származó alkalmazásprogramozási felület (API). A további tudnivalókat lásd [Szolgáltatások közötti hitelesítés konfigurálása](service-to-service-auth.md).

## <a name="import-ratings-and-reviews"></a>Minősítések és felülvizsgálatok importálása

A minősítések importálása és a meglévő rendszerből származó adatok Commerce rendszerbe való ellenőrzéséhez egy meglévő Power Automate folyamathoz vagy egy új folyamathoz kell hozzáadnia a Dynamics 365 Minősítések és az Áttekintések Power Automate csatlakoztatóját. A további tudnivalókat lásd [Dynamics 365 Commerce – Minősítések és értékelések (Előnézet)](/connectors/dynamics365ratingsre/).

> [!IMPORTANT]
> Az eljárás befejezése előtt [be kell állítania az S2S hitelesítést](service-to-service-auth.md).

A következő lépések szerint importálhatja a minősítéseket és az értékeléseket a Commerce alkalmazásba a Dynamics 365 Minősítések és áttekintések Power Automate összekötő segítségével.

1. Válassza a **Felhasználói értékelés beküldése** műveletet.
1. Kapcsolat létrehozása az S2S hitelesítés konfigurálásakor létrehozott Azure Active Directory (Azure AD) alkalmazásinformációk alapján. A további tudnivalókat lásd a [Szolgáltatások közötti hitelesítés konfigurálása](service-to-service-auth.md) részben.
1. A **Felhasználói minősítés beküldése** művelet egyszerre csak egy minősítést vesz figyelembe. Ezért ismételje meg a műveletet. A forrás-ellenőrzésekkel tömegesen küldheti el az listára vonatkozó listában.
    
## <a name="export-ratings-and-reviews"></a>Minősítések és felülvizsgálatok exportálása

A minősítések importálásához és a Commerce rendszerből származó adatok ellenőrzéséhez hozzá kell adni a Dynamics 365 Minősítések és az Áttekintés Power Automate csatlakoztatóját egy meglévő Power Automate folyamathoz vagy egy új folyamathoz. A további tudnivalókat lásd [Dynamics 365 Commerce – Minősítések és értékelések (Előnézet)](/connectors/dynamics365ratingsre/).

A következő lépések szerint exportálhatja a minősítéseket és az értékeléseket a Commerce rendszerből a Dynamics 365 Minősítések és áttekintések Power Automate csatlakoztató segítségével.

1. Válassza az **Összes értékelésexportálása** műveletet.
1. A művelet befejezése. 

## <a name="additional-resources"></a>További erőforrások

[Minősítések és értékelések áttekintése](ratings-reviews-overview.md)

[A minősítések és értékelések használatának bekapcsolása](opt-in-ratings-reviews.md)

[Minősítések és értékelések kezelése](manage-reviews.md)

[Minősítések és értékelések konfigurálása](configure-ratings-reviews.md)

[A termék minősítések szinkronizálása](sync-product-ratings.md)

[A minősítések és az értékelések moderátor általi manuális közzétételének engedélyezése](manual-publish-rating-reviews.md)

[Szolgáltatás a szolgáltatáshoz típusú hitelesítés konfigurálása](service-to-service-auth.md)

[Értékelések és vélemények GYIK](ratings-reviews-faq.md)
