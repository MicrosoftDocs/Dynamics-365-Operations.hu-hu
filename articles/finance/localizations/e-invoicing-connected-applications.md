---
title: Csatlakoztatott alkalmazások
description: Ez a témakör bemutatja a csatlakoztatott alkalmazások beállítását az Elektronikus számlázás modulban.
author: dkalyuzh
ms.date: 02/07/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkalyuzh
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 7a0a9c19009c49b80ca8c182c31592c1a713a2aa
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8906287"
---
# <a name="connected-applications"></a>Csatlakoztatott alkalmazások

[!include [banner](../includes/banner.md)]

A csatlakoztatott alkalmazások a Microsoft Dynamics 365 Pénzügy Dynamics 365 Supply Chain Management példányai, és a konfigurációs szolgáltatáson (RCS) keresztül lehet szükség. A csatlakoztatott alkalmazásokon keresztül a Pénzügy és az Ellátásilánc-kezelés globalizációs funkcióját be lehet állítani, hogy az elektronikus számlázási helyzet működjön.

A globalizációs funkció telepítésekor a Pénzügyi vagy Ellátásilánc-kezelés alkalmazásra vonatkozó beállítási információk közvetlenül közzé tehetőek az RCS rendszerből a megfelelő csatlakoztatott alkalmazásba.

Az RCS pénzügyi és ellátásilánc-kezelési paramétereinek rendelkezésre állása több alkalmazási környezetben is hasznos, például a felhasználók elfogadási tesztelése (UAT) és a gyártási környezetek esetében, és ezeket a paramétereket több különböző környezetre telepítve szeretné konzisztensen tartani.

## <a name="create-a-connected-application"></a>Csatlakoztatott alkalmazás létrehozása

1. Jelentkezzen be a RCS-fiókba.
2. A **Globalizációs funkció** munkaterületen a **Környezet** szakaszban válassza ki az **Elektronikus számlázás bővítmény** csempét.
3. A Környezet **beállítási lapján**, a munkaablakban válassza a Kapcsolódó alkalmazások **lehetőséget**.
4. Válassza ki az **Új** lehetőséget egy csatlakoztatott alkalmazás létrehozásához.
5. A **Név** mezőben adja meg a csatlakoztatni kívánt alkalmazás nevét.
6. A Típus **mezőben** válassza a **Dynamics 365 Pénzügy lehetőséget**.
7. Az Alkalmazás **mezőben** adja meg a csatlakoztatni kívánt környezet URL-címét.
8. A Bérlő **mezőben** adja meg a környezet bérlőját.
9. Válassza a **Mentés** lehetőséget.
10. A Művelet ablaktáblán válassza a **Kapcsolat ellenőrzése** lehetőséget a környezettel való kapcsolat teszteléséhez. Ezután zárja be az oldalt.

## <a name="link-connected-applications-to-environments"></a>Csatlakoztatott alkalmazások csatolása környezetekhez

1. A Környezet **beállítási lapon** válassza az Új **lehetőséget,** ha a környezethez hozzá szeretne rendelni egy csatlakoztatott alkalmazást.
2. A **Csatlakoztatott alkalmazás** mezőben válasszaon ki egy csatlakoztatott alkalmazást.
3. Válassza ki a szolgáltatási környezetet a **Szolgáltatási környezet** mezőben.
4. Válassza a **Mentés** gombot, majd zárja be az oldalt.
