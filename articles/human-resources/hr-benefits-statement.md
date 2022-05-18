---
title: Juttatási kimutatás
description: A juttatási kimutatás bemutatja, hogy milyen juttatásokban részesül jelenleg az alkalmazott.
author: twheeloc
ms.date: 09/21/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: a12649cd0604fb6acd58420fdafb5b560fcc10cf
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/04/2022
ms.locfileid: "8688232"
---
# <a name="benefit-statement"></a>Juttatási kimutatás


[!INCLUDE [PEAP](../includes/peap-2.md)]

A **Juttatási kimutatás** jelentés kimutatást ad arról, hogy milyen juttatásokban részesül az alkalmazott. A jelentéshez közvetlenül az alkalmazott vagy a juttatások adminisztrátora fér hozzá. A **Juttatási kimutatás** listát nyújt az alkalmazott juttatásairól, fedezeti lehetőségeiről, költségeiről, valamint az esetleges eltartottakról és kedvezményezettekről. A kimutatás egyetlen dolgozóra vagy több dolgozóra is kinyomtatható.

> [!NOTE]
A **Juttatások kimutatása** funkciót be kell kapcsolni a következő a **Funkciókezelés** munkaterületen. Ehhez a **Juttatáskezelés** funkciónak bekapcsolva kell lennie a Funkciókezelésben. 


## <a name="importing-the-benefit-statement"></a>A Juttatási kimutatás importálása 

A **Juttatási kimutatás** csak akkor válik elérhetővé, ha a jelentéskonfigurációval importálja a **Juttatási kimutatást**. Ehhez a következő lépéseket kell végrehajtani:

1.  Ugrás a **Rendszerfelügyelet** munkaterületre.

2.  Válassza az **Elektronikus jelentéskészítés** csempét.

3.  Menjen a **Konfigurációszolgáltatók** részbe, és válassza ki a **Tárházak** lehetőséget.

  ![Tárházak kiválasztása.](https://user-images.githubusercontent.com/26801678/134203290-7faf7245-ed08-44e9-95a1-a7ba278c42c6.png)

4.  Válassza ki a **HR-erőforrások** lehetőséget a listából, majd válassza a **Megnyitás** lehetőséget.

    ![Konfiguráció-tárházak.](https://user-images.githubusercontent.com/26801678/134203619-b3fd087d-1fe9-45ef-a588-1afedfe38dfd.png)

5.  Válassza ki a **Juttatási kimutatás modellt** a bal oldali ablakban, és bontsa ki úgy, hogy a **Juttatáskimutatás formátuma** megjelenjen.

6.  Válassza ki a **Juttatási kimutatás formátuma** lehetőséget a bal oldali ablakban.

7.  A képernyő jobb oldalán egy **Verziók** gyorslap jelenik meg. Válassza az **Importálás** lehetőséget.

    ![Műveletek Gyorslap jelenik meg.](https://user-images.githubusercontent.com/26801678/134203763-f12ef549-e326-400d-ac69-b25fc94af47b.png)

## <a name="generate-the-benefit-statement-as-a-pdf-file"></a>Juttatási kimutatás létrehozása PDF-fájlként

A **Juttatási kimutatás** alapértelmezés szerint Microsoft Word-dokumentumként lesz kinyomtatva. PDF formátumú nyomtatáshoz konfigurálnia kell a PDF-beállítást az **Elektronikus jelentési célhelyen**. 

1. Ehhez a **Rendszerfelügyelet munkaterületén** > **Elektronikus jelentéskészítés** > **Kapcsolódó hivatkozások** > **Elektronikus jelentések célhelye** részben érhető el.

1.  Válassza az **Új** lehetőséget.

2.  A **Referencia** mezőben válassza a következőt: **Juttatási kimutatás formátuma**.

3.  Válassza az **Új** lehetőséget a **Fájl célja** gyorslapon.

4.  A **Név** mezőbe írja be: **Juttatási kimutatás (PDF)**.

5.  A **Fájlösszetevő neve** mezőbe írja be vagy válassza: **Juttatási kimutatás**.

6.  Jelölje be a **Konvertálás PDF-formátumba** jelölőnégyzet.

7.  Válassza a **Beállítások** lehetőséget a menüelemből. 

    ![Fájl célja.](https://user-images.githubusercontent.com/26801678/134203881-a3f1ebc3-d816-485d-a53b-026cc29cae64.png)

8.  Válassza a **Fájl** gyorslapot, majd válassza az **Engedélyezve** lehetőséget.

9.  Válassza ki az **OK** lehetőséget.
   
> [!NOTE]
> A juttatáskezelés szolgáltatás előzetes verzió állapotban van. Van egy ismert porbléma az e-mail-cél beállítás használatakor az **Elektronikus jelentés célja** jelentésben. Lehet, hogy hibaüzenetet kap, és az e-mail küldése sikertelen lesz.

A **Juttatás-kimutatás** a következő lapokról generálható:

-   **Juttatások kezelése munkaterület** > **Hivatkozások** > **Jelentések** > **Juttatás-kimutatás**

-   **Alkalmazottak (örökölt űrlap)** > **Személyes adatok lap** > **Juttatás-kimutatás**

-   **Korszerű alkalmazotti belépés** > **Juttatási jelentések** > **Juttatás-kimutatás**

-   **Alkalmazott önkiszolgáló rendszer** > **Juttatások** > **Juttatás-kimutatás megtekintése**

> [!NOTE]
>  Az **Alkalmazotti önkiszolgáló rendszer** **Juttatás-kimutatás** részének hozzáférését a **Juttatás-kimutatás megtekintése** jogosultság vezérli. Ez az **Alkalmazotti önkiszolgáló juttatások** feladat alatt található. Ezt a jogosultságot alapértelmezés szerint az alkalmazottak megkapják.

## <a name="report-contents"></a>Jelentés tartalma

A **Juttatás-kimutatás** kinyomtatja az alkalmazott visszaigazolt konstrukciókiválasztását, a lemondott konstrukciókkal együtt. A következő kép egy példát mutat erre a jelentésre. 

![Juttatás-kimutatás jelentés.](https://user-images.githubusercontent.com/26801678/134204058-61baa318-fede-4795-a256-acdf3217f9f9.png)

A jelentésben megjelenik a **Terv**, **Fedezeti beállítás**, **Alkalmazotti költség** és **Munkáltatói költség** elemeket. A jelentés felsorolja az esetleges érintett eltartottokat is. Ha a tervhez kedvezményezettek vannak társítva, akkor a kedvezményezettek, azok elosztási prioritása és százalékos aránya megjelenik.

A **Juttatás-kimutatás** jelentés egyszerre több alkalmazottra is nyomtatható a **Belefoglalandó rekordok** gyorslap használatával a **Juttatás-kimutatás** oldalon.
