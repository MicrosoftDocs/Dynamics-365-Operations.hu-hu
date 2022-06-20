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
ms.custom: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rapraj
ms.search.validFrom: 2020-01-21
ms.dyn365.ops.version: Retail 10.0.9 update
ms.openlocfilehash: 54dd19134aea68f73de51086fbaa096961447b62
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8873304"
---
# <a name="create-and-update-a-returns-and-refunds-policy-for-a-channel"></a>Visszáruk és visszatérítések irányelvének létrehozása és frissítése a csatornához

[!include [banner](includes/banner.md)]

A csatorna visszaküldési irányelve a Dynamics 365 Commerce-ben lehetővé teszi a kiskereskedők számára, hogy olyan érvényesítéseket állítsanak be, amelyeknél engedélyezhetők a fizetőeszközök a megtérülés pénztári eszközöknél való feldolgozásához.  

Ez a témakör a csatornákra vonatkozó visszatérítési és visszatérítési irányelvek beállításának lépéseit ismerteti.

Az irányelv hatálya jelenleg csak a csatornán megengedhető fizetőeszközök beállításához használható. A „megengedett” lista a beszerzés elkészítésekor használt fizetési módokon alapul. Példa:

- Ha egy beszerzéskor ajándékutalványt alkalmaznak, az áruházi irányelv célja, hogy csak egy új ajándékutalvány számára vagy üzleti hitel céljából dolgozza fel a visszatérítéseket. 
- Ha az értékesítés készpénzes fizetéssel történik, akkor a visszatérítésre engedélyezett lehetőségek a készpénz, az ajándékutalvány és a vevői számla, a hitelkártya azonban nem. 

## <a name="enable-return-policy"></a>Visszatérítési irányelv engedélyezése

Ha engedélyezni szeretné a Commerce központi felületén a csatorna-visszaküldési irányelvet, kövesse az alábbi lépéseket.

1. Ugorjon a **Funkciókezelés** munkaterülethez a Dynamics 365 Commerce-ben.
1. Keresse meg a **Csatornavisszaküldési irányelvek engedélyezése** funkciót a szolgáltatások neveinek listáján.
1. Válassza az **Engedélyezés most** lehetőséget.
1. Az **Elosztás ütemezése** lapon futtassa a **1110-es** (globális konfiguráció) feladatot a funkció változtatásának terjesztéséhez.

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
