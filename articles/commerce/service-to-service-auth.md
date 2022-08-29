---
title: Szolgáltatás a szolgáltatáshoz típusú hitelesítés konfigurálása
description: Ez a témakör azt ismerteti, hogyan kell konfigurálni a szolgáltatás-szolgáltatás hitelesítést a szolgáltatási API-k Microsoft Dynamics 365 Commerce biztonságos hívására az értékeléshez és az ellenőrzéshez.
author: gvrmohanreddy
ms.date: 01/12/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2017-06-20
ms.openlocfilehash: e3134d4ddb2e4f3d260e51d49e7399ff84e0d74a
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9279448"
---
# <a name="configure-service-to-service-authentication"></a>Szolgáltatás a szolgáltatáshoz típusú hitelesítés konfigurálása

[!include [banner](includes/banner.md)]

Ez a témakör leírja, hogyan kell konfigurálni a Szolgáltatás szolgáltatáshoz (S2S) Microsoft Dynamics 365 Commerce hitelesítést a szolgáltatási alkalmazásprogramozási felületek (API-k) biztonságos hívására az értékeléshez és az ellenőrzéshez.

A Dynamics 365 Commerce [minősítéseket és értékeléseket](ratings-reviews-overview.md) kínál omnicsatornás megoldásként. Ez a megoldás a Commerce rendszerből származó szolgáltatási API-khoz való hozzáférést teszi lehetővé, így különböző feladatokat lehet végrehajtani. Ilyen feladat lehet például a külső rendszerből a Commerce rendszerbe történő minősítések és felülvizsgálatok importálása, valamint a Commerce rendszerből származó minősítések és felülvizsgálatok exportálása. Ahhoz, hogy a Commerce biztonságosan hívhatja a minősítéseket és ellenőrizze a szolgáltatási API-kat, először konfigurálnia kell az S2S-hitelesítést az ebben a cikkben olvasható eljárásokkal.

## <a name="add-a-new-app-registration"></a>Új alkalmazásregisztráció hozzáadása

Új alkalmazásregisztráció hozzáadása előtt létre kell hoznia egy [alkalmazást az Azure-portál használatával](https://portal.azure.com). Ha regisztrálni szeretné az alkalmazásokat (Azure Active Directory) és Azure AD engedélyezni szeretné a hitelesítést, [Azure Active Directory kövesse az Egyéni csatlakoztatóval való használat lépést a következőben:Power Automate](/connectors/custom-connectors/azure-active-directory-authentication)

A következő adatok gyűjtése az Azure-portálról. Az alábbi lépésekben szüksége lesz ezekre az edd-ökre.

- Ügyfélalkalmazás azonosítója
- Ügyfélkönyvtár (bérlő) azonosítója

A Következő lépések szerint adhat hozzá új alkalmazásregisztrációt a Commerce Webhelyszerkesztőben.

1. Nyissa meg a **Kezdőlap \> Értékelések \> Beállítások** elemet.
1. Válassza **a Kezelés lehetőséget a Szolgáltatás szolgáltatásba (S2S) hitelesítés** **alatt**.

    ![A Commerce Webhelyszerkesztő Szolgáltatás-szolgáltatás hitelesítés (S2S) hitelesítési szakaszában található Gomb kezelése.](media/Ratings-reviews-settings-service-to-service-authentication.png)

1. A jobb oldalon **megjelenő S2S alkalmazásbejegyzések ablakban válassza az Új S2S** **alkalmazásregisztráció hozzáadása lehetőséget**.
1. **Az S2S** alkalmazásbejegyzés hozzáadása párbeszédpanelen adja meg a következő kötelező adatokat. Az Azure-alkalmazásregisztráció értékeinek használata.

    - **Név** – adja meg a pályázat nevét (például App **Gyár**).
    - **Ügyfélalkalmazás azonosítója** – adja meg az alkalmazásazonosítót (például **00000000-0000-0000-0000-000000000000**).
    - **Címtár (bérlő) azonosítója** – adja meg a könyvtárazonosítót (például **00000000-0000-0000-0000-000000000000**).

    ![Az S2S alkalmazásbejegyzés hozzáadása párbeszédpanel a Commerce Webhelyszerkesztőben](media/Ratings-reviews-settings-S2S-APP-entry.png)

1. Válassza a **Beküldés** lehetőséget. A pályázat nevének meg kell jelenni a **S2S alkalmazásbejegyzések ablakában látható listában**.
1. Zárja be az **S2S alkalmazás bejegyzései ablakot**.
1. Válassza a **Mentés** lehetőséget.

## <a name="edit-an-existing-app-registration"></a>Meglévő alkalmazásregisztráció szerkesztése

A Commerce Webhelyszerkesztőben meglévő alkalmazásregisztráció szerkesztéséhez hajtsa végre a következő lépéseket.

1. Nyissa meg a **Kezdőlap \> Értékelések \> Beállítások** elemet.
1. Válassza **a Kezelés lehetőséget a Szolgáltatás szolgáltatásba (S2S) hitelesítés** **alatt**.
1. **Az S2S alkalmazás** bejegyzései ablakban válassza ki a szerkeszteni kívánt bejegyzés melletti szimbólumot.
1. Szükség szerint frissítse **az értékeket a Név**, **az Ügyfélalkalmazás azonosítója** **és a Címtár (bérlő) azonosító** mezőjében.
1. Válassza a **Beküldés** lehetőséget.
1. Zárja be az **S2S alkalmazás bejegyzései ablakot**.
1. Válassza a **Mentés** lehetőséget.

## <a name="remove-an-existing-app-registration"></a>Meglévő alkalmazásregisztráció eltávolítása

Ha el szeretne távolítani egy meglévő alkalmazásregisztrációt a Commerce webhelyszerkesztőben, kövesse ezeket a lépéseket.

1. Nyissa meg a **Kezdőlap \> Értékelések \> Beállítások** elemet.
1. Válassza **a Kezelés lehetőséget a Szolgáltatás szolgáltatásba (S2S) hitelesítés** **alatt**.
1. **Az S2S alkalmazás** bejegyzései ablakban válassza ki az eltávolítani kívánt bejegyzés mellettican szimbólumot. A bejegyzés el lesz távolítva a listáról.
1. Zárja be az **S2S alkalmazás bejegyzései ablakot**.
1. Válassza a **Mentés** lehetőséget.

## <a name="additional-resources"></a>További erőforrások

[Minősítések és értékelések áttekintése](ratings-reviews-overview.md)

[A minősítések és értékelések használatának bekapcsolása](opt-in-ratings-reviews.md)

[Minősítések és értékelések kezelése](manage-reviews.md)

[Minősítések és értékelések konfigurálása](configure-ratings-reviews.md)

[A termék minősítések szinkronizálása](sync-product-ratings.md)

[A minősítések és az értékelések moderátor általi manuális közzétételének engedélyezése](manual-publish-rating-reviews.md)

[Értékelések és véleményezések importálása és exportálása](import-export-reviews.md)

[Értékelések és vélemények GYIK](ratings-reviews-faq.md) 
