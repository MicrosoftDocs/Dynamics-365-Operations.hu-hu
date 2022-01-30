---
title: Szolgáltatás-szolgáltatás hitelesítés konfigurálása
description: Ez a témakör azt ismerteti, hogyan kell konfigurálni a szolgáltatás-szolgáltatás hitelesítést a szolgáltatási API-k biztonságos hívására az értékeléshez és az Microsoft Dynamics 365 Commerce ellenőrzéshez.
author: gvrmohanreddy
ms.date: 01/12/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgri
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2017-06-20
ms.openlocfilehash: da780de5f15d72bdac85a261eae809125c830260
ms.sourcegitcommit: 7adf9ad53b4e6d1c4d5d612ce0977b76c61ec173
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/13/2022
ms.locfileid: "7968403"
---
# <a name="configure-service-to-service-authentication"></a>Szolgáltatás-szolgáltatás hitelesítés konfigurálása

[!include [banner](includes/banner.md)]

Ez a témakör azt ismerteti, hogyan kell konfigurálni a Szolgáltatás szolgáltatáshoz (S2S) hitelesítést a szolgáltatási alkalmazásprogramozási felületek (API-k) biztonságos hívására az értékeléshez és az Microsoft Dynamics 365 Commerce ellenőrzéshez.

Dynamics 365 Commerce A [<a0/<a0/<a2/aki minősítéseket és](ratings-reviews-overview.md) értékeléseket kínál csatorna-megoldásként. Ez a megoldás a Commerce rendszerből származó szolgáltatási API-khoz való hozzáférést teszi lehetővé, így különböző feladatokat lehet végrehajtani. Ilyen feladat lehet például a külső rendszerből a Commerce rendszerbe történő minősítések és felülvizsgálatok importálása, valamint a Commerce rendszerből származó minősítések és felülvizsgálatok exportálása. Ahhoz, hogy a Commerce biztonságosan hívhatja a minősítéseket és ellenőrizze a szolgáltatási API-kat, először konfigurálnia kell az S2S-hitelesítést az ebben a témakörben található eljárások segítségével.

## <a name="add-a-new-app-registration"></a>Új alkalmazásregisztráció hozzáadása

Új alkalmazásregisztráció hozzáadása előtt létre kell hoznia egy alkalmazást az [Azure-portál használatával](https://portal.azure.com). Ha regisztrálni szeretné az alkalmazásokat a () funkcióban, és engedélyezni szeretné a hitelesítést, hajtsa végre az Egyéni csatlakoztatóval való használat Azure Active Directory Azure AD lépést a [Azure Active Directory következőben:Power Automate](/connectors/custom-connectors/azure-active-directory-authentication)

A következő adatok gyűjtése az Azure-portálról. Az alábbi lépésekben szüksége lesz ezekre az edd-ökre.

- Ügyfélalkalmazás azonosítója
- Ügyfélkönyvtár (bérlő) azonosítója

A Következő lépések szerint adhat hozzá új alkalmazásregisztrációt a Commerce Webhelyszerkesztőben.

1. Nyissa meg a **Kezdőlap \> Értékelések \> Beállítások** elemet.
1. A **Szolgáltatás szolgáltatásba (S2S) hitelesítés alatt válassza a** Kezelés **lehetőséget**.

    ![A Commerce Webhelyszerkesztő Szolgáltatás-szolgáltatás hitelesítés (S2S) hitelesítési szakaszában található Gomb kezelése.](media/Ratings-reviews-settings-service-to-service-authentication.png)

1. A jobb oldalon megjelenő S2S alkalmazásbejegyzések ablakban válassza **az** Új **S2S alkalmazásregisztráció hozzáadása** lehetőséget.
1. Az **S2S alkalmazásbejegyzés** hozzáadása párbeszédpanelen adja meg a következő kötelező adatokat. Az Azure-alkalmazásregisztráció értékeinek használata.

    - **Név** – adja meg a pályázat nevét (például App **Gyár**).
    - **Ügyfélalkalmazás azonosítója** – adja meg az alkalmazásazonosítót (például). **00000000-0000-0000-0000-000000000000**
    - **Címtár (bérlő) azonosítója** – adja meg a könyvtárazonosítót (például). **00000000-0000-0000-0000-000000000000**

    ![Az S2S alkalmazásbejegyzés hozzáadása párbeszédpanel a Commerce Webhelyszerkesztőben](media/Ratings-reviews-settings-S2S-APP-entry.png)

1. Válassza a **Beküldés** lehetőséget. A pályázat nevének meg kell jelenni a **S2S alkalmazásbejegyzések ablakában látható** listában.
1. Zárja be az **S2S alkalmazás bejegyzései** ablakot.
1. Válassza a **Mentés** lehetőséget.

## <a name="edit-an-existing-app-registration"></a>Meglévő alkalmazásregisztráció szerkesztése

A Commerce Webhelyszerkesztőben meglévő alkalmazásregisztráció szerkesztéséhez hajtsa végre a következő lépéseket.

1. Nyissa meg a **Kezdőlap \> Értékelések \> Beállítások** elemet.
1. A **Szolgáltatás szolgáltatásba (S2S) hitelesítés alatt válassza a** Kezelés **lehetőséget**.
1. Az S2S alkalmazás bejegyzései ablakban válassza ki a szerkeszteni kívánt bejegyzés melletti **szimbólumot**.
1. Szükség esetén frissítse az értékeket **a** Név, az Ügyfélalkalmazás azonosítója és a **Címtár** **(bérlő)** azonosító mezőben.
1. Válassza a **Beküldés** lehetőséget.
1. Zárja be az **S2S alkalmazás bejegyzései** ablakot.
1. Válassza a **Mentés** lehetőséget.

## <a name="remove-an-existing-app-registration"></a>Meglévő alkalmazásregisztráció eltávolítása

Ha el szeretne távolítani egy meglévő alkalmazásregisztrációt a Commerce webhelyszerkesztőben, kövesse ezeket a lépéseket.

1. Nyissa meg a **Kezdőlap \> Értékelések \> Beállítások** elemet.
1. A **Szolgáltatás szolgáltatásba (S2S) hitelesítés alatt válassza a** Kezelés **lehetőséget**.
1. Az S2S alkalmazás bejegyzései ablakban válassza ki az eltávolítani kívánt bejegyzés **mellettican** szimbólumot. A bejegyzés el lesz távolítva a listáról.
1. Zárja be az **S2S alkalmazás bejegyzései** ablakot.
1. Válassza a **Mentés** lehetőséget.

## <a name="additional-resources"></a>További erőforrások

[Minősítések és értékelések áttekintése](ratings-reviews-overview.md)

[A minősítések és értékelések használatának bekapcsolása](opt-in-ratings-reviews.md)

[Minősítések és értékelések kezelése](manage-reviews.md)

[Minősítések és értékelések konfigurálása](configure-ratings-reviews.md)

[A termék minősítések szinkronizálása](sync-product-ratings.md)

[A minősítések és az értékelések moderátor általi manuális közzétételének engedélyezése](manual-publish-rating-reviews.md)

[Minősítések és felülvizsgálatok importálása és exportálása](import-export-reviews.md)

[Értékelések és vélemények GYIK](ratings-reviews-faq.md) 
