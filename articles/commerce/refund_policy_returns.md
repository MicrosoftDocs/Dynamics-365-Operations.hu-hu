---
title: Visszáruk és visszatérítések irányelvének létrehozása és frissítése a csatornához
description: Ez a cikk bemutatja, hogyan lehet beállítani egy csatornára vonatkozó visszatérítési és visszatérítési irányelveket.
author: ShalabhjainMSFT
ms.date: 07/13/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.author: shajain
ms.search.validFrom: 2020-01-21
ms.dyn365.ops.version: Retail 10.0.9 update
ms.custom: ''
ms.search.industry: Retail
ms.openlocfilehash: d01ad490301dd2f4103b8bd3f702db12b93a45a8
ms.sourcegitcommit: bd7b1ffe90b25eb4c68d6aaebd063bf33e09d9cd
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/05/2022
ms.locfileid: "9627496"
---
# <a name="create-and-update-a-returns-and-refunds-policy-for-a-channel"></a>Visszáruk és visszatérítések irányelvének létrehozása és frissítése a csatornához

[!include [banner](includes/banner.md)]

A csatorna visszaküldési irányelve a Dynamics 365 Commerce-ben lehetővé teszi a kiskereskedők számára, hogy olyan érvényesítéseket állítsanak be, amelyeknél engedélyezhetők a fizetőeszközök a megtérülés pénztári eszközöknél való feldolgozásához.  

Ez a témakör a csatornákra vonatkozó visszatérítési és visszatérítési irányelvek beállításának lépéseit ismerteti.

Az irányelv hatálya jelenleg csak a csatornán megengedhető fizetőeszközök beállításához használható. A „megengedett” lista a beszerzés elkészítésekor használt fizetési módokon alapul. Példa:

- Ha egy beszerzéskor ajándékutalványt alkalmaznak, az áruházi irányelv célja, hogy csak egy új ajándékutalvány számára vagy üzleti hitel céljából dolgozza fel a visszatérítéseket. 
- Ha az értékesítés készpénzes fizetéssel történik, akkor a visszatérítésre engedélyezett lehetőségek a készpénz, az ajándékutalvány és a vevői számla, a hitelkártya azonban nem. 

## <a name="enable-return-policy"></a>Visszatérítési irányelv engedélyezése

Ez a funkció alapértelmezés szerint be van kapcsolva. A funkció a **funkciókezelés** **munkaterületén** úgy érhető el, hogy megkeresi a csatorna-visszaküldési házirendeket a funkciónevek listájában.


## <a name="configure-return-policy"></a>Konfigurálja a visszaküldési irányelvet

Hajtsa végre a következő lépéseket a kiskereskedelmi üzlet vagy online kiskereskedelmi csatolna visszatérítési irányelvének konfigurálásához.

1. Ugorjon a **Retail és Commerce** \> **Csatorna beállítása** \> **Visszáruk** \> **Csatorna-visszaküldési irányelv** elemre.

1. Válassza az **Új** lehetőséget új visszaküldésiirányelv-sablon létrehozásához. Meglévő sablon használatához válassza ki a sablont a bal oldali ablaktáblán. Új sablonok esetében adjon meg egy nevet és egy leírást, amely segítséget nyújt az irányelvnek a csatornára való alkalmazásakor.

   ![Új visszaküldési irányelv hozzáadása.](media/Return-policy-page1.png)
     
   
1. Az **Engedélyezett visszatérítési mód** szakaszban határozza meg az egyes fizetési módokhoz **Engedélyezett** visszáru-kifizetési eszközöket.
   ![Engedélyezett fizetési módok megadása fizetéstípusonként.](media/Return-policy-page2.png)
   
    > [!IMPORTANT]
    > - A fizetési módok a szervezethez beállított fizetési módokból vannak származtatva.
    > - Ha egy engedélyezett visszárueszköz-típust ad meg mindegyik felsorolt kifizetési módhoz, akkor biztosítja, hogy a visszaküldések megvalósíthatók legyenek az engedélyezett visszárueszköz-típussal.
    
1. A visszaküldési irányelv sablonját társítsa azokkal az üzletekkel, ahol használatban lesz. Válassza **Hozzáadás** lehetőséget a **Kiskereskedelmi csatornák** lapon, majd társítsa az elérhető csatornákat. 

    - A **Szervezeti csomópontok kiválasztása** párbeszédpanelen válassza ki azokat az üzleteket, régiókat és szervezeteket, amelyekkel a sablont társítani szeretné.
    - Minden üzlethez csak egy visszaküldésiirányelv-sablon tartozhat.
    - A nyílgombokkal válassza ki az üzleteket, régiókat vagy szervezeteket.
    - Az irányelv érvényességi dátuma az a dátum, amelyen a rendszer a csatornákra alkalmazza a szabályokat, és a csatorna feladatait futtatja. 

    ![Szervezeti csomópontok párbeszédpanel kiválasztása.](media/Return-policy-page3.png)

1. A **Felosztási ütemezés** lapon futtassa az **1070-es** feladatot, hogy a csatorna visszaküldési irányelve elérhető legyen a pénztár számára.

## <a name="preview-the-channel-return-policy-in-the-pos"></a>A csatorna-visszaküldési irányelv előnézetének megtekintése a pénztárban

Kövesse az alábbi lépések egyikét, ha a pénztárban engedélyezett visszárueszköz-típusokat szeretné megtekinteni.

1. Jelentkezzen be a pénztárba pénztárosként vagy vezetőként.
1. A **Műszak és a fiók** területen válassza a **Napló megjelenítése** lehetőséget.
1. Válassza ki azt a tranzakciót, amely a visszáru része. 
1. Válassza ki a visszatérítéshez használandó cikkeket, és válassza ki a fizetési módot.  
    - Ha a kiválasztott fizetési mód szerepel a visszárueszköz-típusok engedélyezett listáján, a pénztáros elvégezheti a tranzakciót.
    - Ha a kiválasztott fizetési mód nem engedélyezett, akkor egy hibaüzenet jelenik meg.
    - Válassza ki az **Esedékes összeget** az összes engedélyezett visszárueszköz-típus listájának megjelenítéséhez.

– vagy –

1. Jelentkezzen be a pénztárba pénztárosként vagy vezetőként.
1. Válassza ki a **Visszáru-tranzakciót**, és írja be a nyugta azonosítóját vonalkód-beolvasással vagy manuális bevitellel. 
1. Válassza ki azt a tranzakciót, amely a visszáru része. 
1. Válassza ki a visszatérítéshez használandó cikkeket, és válassza ki a fizetési módot.  
    - Ha a kiválasztott fizetési mód szerepel a visszárueszköz-típusok engedélyezett listáján, a pénztáros elvégezheti a tranzakciót.
    - Ha a kiválasztott fizetési mód nem engedélyezett, akkor egy hibaüzenet jelenik meg.
    - Válassza ki az **Esedékes összeget** az összes engedélyezett visszárueszköz-típus listájának megjelenítéséhez.

![Nem engedélyezett visszatérítés-típus.](media/Return-policy-page6.png)



![Engedélyezett visszatérítés-típusok.](media/Return-policy-page5.png)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
