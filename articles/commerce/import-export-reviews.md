---
title: Minősítések és felülvizsgálatok importálása és exportálása
description: Ez a témakör azt ismerteti, hogyan lehet importálni és exportálni a termékminősítéseket és -értékeléseket a következőben:Microsoft Dynamics 365 Commerce
author: gvrmohanreddy
ms.date: 01/12/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgri
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2017-06-20
ms.openlocfilehash: 3ae85f21f7a78d56621aed60527207badcee9c75
ms.sourcegitcommit: 7adf9ad53b4e6d1c4d5d612ce0977b76c61ec173
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/13/2022
ms.locfileid: "7968404"
---
# <a name="import-and-export-ratings-and-reviews"></a>Minősítések és felülvizsgálatok importálása és exportálása

[!include [banner](includes/banner.md)]

Ez a témakör azt ismerteti, hogyan lehet importálni és exportálni a termékminősítéseket és -értékeléseket a következőben:Microsoft Dynamics 365 Commerce

Dynamics 365 Commerce A [<a0/<a0/<a2/aki minősítéseket és](ratings-reviews-overview.md) értékeléseket kínál csatorna-megoldásként. Amikor a "Minősítések és áttekintések" megoldásra vált, érdemes lehet a meglévő értékeléseket áthelyezni, és az adatokat át kell vizsgálni a Dynamics 365 Commerce Commerce platformra. Az üzleti követelmények alapján előfordulhat, hogy exportálni szeretné a minősítéseket, és áttekinti a Commerce rendszerből származó adatokat. A csatlakoztató segítségével minősítéseket és értékeléseket Power Automate importálhat a Commerce rendszerből, és exportálhatja azokat a Commerce rendszerből.

> [!NOTE]
> A logikai folyamatokkal való első lépésekről a Következőben Power Automate található [a Felhőáramlás létrehozása Power Automate](/power-automate/get-started-logic-flow).

## <a name="prerequisites"></a>Előfeltételek

A minősítések és az ellenőrzések importálása és exportálása előtt teljesítenie kell a következő előfeltételeket:

- A minősítéseket és az áttekintési megoldást engedélyezni kell a Commerce platformon található e-commerce webhelyen. A további tudnivalókat lásd [az "Értékelés és áttekintések" lehetőség használatára való regisztrációval](opt-in-ratings-reviews.md) kapcsolatban.
- A Dynamics 365 minősítéseket és a Reviews Power App Connector alkalmazást úgy kell beállítani, hogy lehetővé tegye az "Ellenőrzés elküldése" vagy az "Export reviews" műveleteket a Power Automate programban. A további tudnivalókat lásd [Dynamics 365 Commerce – Minősítések és értékelések (Előnézet)](/connectors/dynamics365ratingsre/).
- A szolgáltatás-szolgáltatás (S2S) hitelesítést úgy kell konfigurálni, hogy biztonságosan hívható legyen a Commerce rendszerből származó alkalmazásprogramozási felület (API). A további tudnivalókat lásd [a Szolgáltatás-szolgáltatás hitelesítés konfigurálása.](service-to-service-auth.md)

## <a name="import-ratings-and-reviews"></a>Minősítések és felülvizsgálatok importálása

A minősítések importálása és a meglévő rendszerből származó adatok Commerce rendszerbe való ellenőrzéséhez egy meglévő folyamathoz vagy egy új folyamathoz kell hozzáadnia a Dynamics 365 Minősítések és az Áttekintés Power Automate Power Automate csatlakoztatóját. A további tudnivalókat lásd [Dynamics 365 Commerce – Minősítések és értékelések (Előnézet)](/connectors/dynamics365ratingsre/).

> [!IMPORTANT]
> Az eljárás befejezése előtt konfigurálnia kell az [S2S](service-to-service-auth.md) hitelesítést.

A következő lépések szerint importálhatja a minősítéseket és az értékeléseket a Commerce alkalmazásba a Dynamics 365 Minősítések és Power Automate áttekintések csatlakoztató segítségével.

1. Válassza a **Felhasználó-ellenőrzés elküldése** műveletet.
1. Kapcsolat létrehozása az S2S hitelesítés konfigurálásakor létrehozott Azure Active Directory (Azure AD) alkalmazásinformációk alapján. A további tudnivalókat lásd [A szolgáltatás-szolgáltatás hitelesítésének](service-to-service-auth.md) konfigurálása.
1. A **Felhasználó-ellenőrzés elküldése művelet egyszerre csak** egy áttekintést vesz igénybe. Ezért ismételje meg a műveletet. A forrás-ellenőrzésekkel tömegesen küldheti el az listára vonatkozó listában.
    
## <a name="export-ratings-and-reviews"></a>Minősítések és felülvizsgálatok exportálása

A minősítések exportáláshoz és a Commerce rendszerből származó adatok ellenőrzéséhez hozzá kell adni a Dynamics 365 Minősítések és az Áttekintés csatlakoztatóját egy meglévő folyamathoz vagy Power Automate Power Automate egy új folyamathoz. A további tudnivalókat lásd [Dynamics 365 Commerce – Minősítések és értékelések (Előnézet)](/connectors/dynamics365ratingsre/).

A következő lépések szerint exportálhatja a minősítéseket és az értékeléseket a Commerce rendszerből a Dynamics 365 Minősítések és Power Automate áttekintések csatlakoztató segítségével.

1. Válassza az **Összes ellenőrzés exportálása** műveletet.
1. A művelet befejezése. 

## <a name="additional-resources"></a>További erőforrások

[Minősítések és értékelések áttekintése](ratings-reviews-overview.md)

[A minősítések és értékelések használatának bekapcsolása](opt-in-ratings-reviews.md)

[Minősítések és értékelések kezelése](manage-reviews.md)

[Minősítések és értékelések konfigurálása](configure-ratings-reviews.md)

[A termék minősítések szinkronizálása](sync-product-ratings.md)

[A minősítések és az értékelések moderátor általi manuális közzétételének engedélyezése](manual-publish-rating-reviews.md)

[Szolgáltatás-szolgáltatás hitelesítés konfigurálása](service-to-service-auth.md)

[Értékelések és vélemények GYIK](ratings-reviews-faq.md)
