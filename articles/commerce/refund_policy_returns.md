---
title: Visszáruk és visszatérítések irányelvének létrehozása és frissítése a csatornához
description: Ez a témakör azt mutatja be, hogyan lehet beállítani egy csatorna visszárukra és visszatérítésekre vonatkozó irányelvét.
author: ShalabhjainMSFT
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rapraj
ms.search.validFrom: 2020-01-21
ms.dyn365.ops.version: Retail 10.0.9 update
ms.openlocfilehash: 89e8fe78414e73053317ebe19e3afcc89231d440
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4979704"
---
# <a name="create-and-update-a-returns-and-refunds-policy-for-a-channel"></a>Visszáruk és visszatérítések irányelvének létrehozása és frissítése a csatornához

[!include [banner](includes/banner.md)]

## <a name="overview"></a>Áttekintés

A csatorna visszaküldési irányelve a Dynamics 365 Commerce-ben lehetővé teszi a kiskereskedők számára, hogy olyan érvényesítéseket állítsanak be, amelyeknél engedélyezhetők a fizetőeszközök a megtérülés pénztári eszközöknél való feldolgozásához.  

Ez a témakör annak lépéseit írja le, hogyan lehet beállítani egy csatorna visszárukra és visszatérítésekre vonatkozó irányelvét.

Az irányelv hatálya jelenleg csak a csatornán megengedhető fizetőeszközök beállításához használható. A „megengedett” lista a beszerzés elkészítésekor használt fizetési módokon alapul. Példa:

- Ha egy beszerzéskor ajándékutalványt alkalmaznak, az áruházi irányelv célja, hogy csak egy új ajándékutalvány számára vagy üzleti hitel céljából dolgozza fel a visszatérítéseket. 
- Ha az értékesítés készpénzes fizetéssel történik, akkor a visszatérítésre engedélyezett lehetőségek a készpénz, az ajándékutalvány és a vevői számla, a hitelkártya azonban nem. 


## <a name="enable-return-policy"></a>Visszatérítési irányelv engedélyezése

A csatorna-visszaküldési irányelvek funkcióinak engedélyezéséhez hajtsa végre a következőket:

1. Ugorjon a **Funkciókezelés** munkaterülethez a Dynamics 365 Commerce-ben.
2. Keresse meg a **Csatornavisszaküldési irányelvek engedélyezése** funkciót a szolgáltatások neveinek listáján.
3. Válassza az **Engedélyezés most** lehetőséget. 

## <a name="configure-return-policy"></a>Konfigurálja a visszaküldési irányelvet

Hajtsa végre a következő lépéseket a kiskereskedelmi üzlet vagy online kiskereskedelmi csatolna visszatérítési irányelvének konfigurálásához.

1. Ugorjon a **Retail és Commerce** \> **Csatorna beállítása** \> **Visszáruk** \> **Csatorna-visszaküldési irányelv** elemre.

2. Válassza az **Új** lehetőséget új visszaküldésiirányelv-sablon létrehozásához. Meglévő sablon használatához válassza ki a sablont a bal oldali ablaktáblán. Új sablonok esetében adjon meg egy nevet és egy leírást, amely segítséget nyújt az irányelvnek a csatornára való alkalmazásakor.

   ![Új visszaküldési irányelv hozzáadása](media/Return-policy-page1.png "Új visszaküldési irányelv hozzáadása")
     
   
3. Az **Engedélyezett visszatérítési mód** szakaszban határozza meg az egyes fizetési módokhoz **Engedélyezett** visszáru-kifizetési eszközöket.
   ![Fizetési módok hozzáadása](media/Return-policy-page2.PNG "Engedélyezett fizetési módok megadása fizetéstípusonként")
   
    > [!IMPORTANT]
    > - A fizetési módok a szervezethez beállított fizetési módokból vannak származtatva.
    > - Ha egy engedélyezett visszárueszköz-típust ad meg mindegyik felsorolt kifizetési módhoz, akkor biztosítja, hogy a visszaküldések megvalósíthatók legyenek az engedélyezett visszárueszköz-típussal.
    
4. A visszaküldési irányelv sablonját társítsa azokkal az üzletekkel, ahol használatban lesz. Válassza **Hozzáadás** lehetőséget a **Kiskereskedelmi csatornák** lapon, majd társítsa az elérhető csatornákat. 

    - A **Szervezeti csomópontok kiválasztása** párbeszédpanelen válassza ki azokat az üzleteket, régiókat és szervezeteket, amelyekkel a sablont társítani szeretné.
    - Minden üzlethez csak egy visszaküldésiirányelv-sablon tartozhat.
    - A nyílgombokkal válassza ki az üzleteket, régiókat vagy szervezeteket.
    - Az irányelv érvényességi dátuma az a dátum, amelyen a rendszer a csatornákra alkalmazza a szabályokat, és a csatorna feladatait futtatja. 

    ![Szervezeti csomópontok párbeszédpanel kiválasztása](media/Return-policy-page3.PNG "Szervezeti csomópontok párbeszédpanel kiválasztása")

5. A **Felosztási ütemezés** lapon futtassa az **1070-es** feladatot, hogy a csatorna visszaküldési irányelve elérhető legyen a pénztár számára.

## <a name="preview-the-channel-return-policy-in-the-pos"></a>A csatorna-visszaküldési irányelv előnézetének megtekintése a pénztárban

Kövesse az alábbi lépések egyikét, ha a pénztárban engedélyezett visszárueszköz-típusokat szeretné megtekinteni.

1. Jelentkezzen be a pénztárba pénztárosként vagy vezetőként.
2. A **Műszak és a fiók** területen válassza a **Napló megjelenítése** lehetőséget.
3. Válassza ki azt a tranzakciót, amely a visszáru része. 
4. Válassza ki a visszatérítéshez használandó cikkeket, és válassza ki a fizetési módot.  
- Ha a kiválasztott fizetési mód szerepel a visszárueszköz-típusok engedélyezett listáján, a pénztáros elvégezheti a tranzakciót.
- Ha a kiválasztott fizetési mód nem engedélyezett, akkor egy hibaüzenet jelenik meg.
- Válassza ki az **Esedékes összeget** az összes engedélyezett visszárueszköz-típus listájának megjelenítéséhez.

– vagy –

1. Jelentkezzen be a pénztárba pénztárosként vagy vezetőként.
2. Válassza ki a **Visszáru-tranzakciót**, és írja be a nyugta azonosítóját vonalkód-beolvasással vagy manuális bevitellel. 
3. Válassza ki azt a tranzakciót, amely a visszáru része. 
4. Válassza ki a visszatérítéshez használandó cikkeket, és válassza ki a fizetési módot.  
- Ha a kiválasztott fizetési mód szerepel a visszárueszköz-típusok engedélyezett listáján, a pénztáros elvégezheti a tranzakciót.
- Ha a kiválasztott fizetési mód nem engedélyezett, akkor egy hibaüzenet jelenik meg.
- Válassza ki az **Esedékes összeget** az összes engedélyezett visszárueszköz-típus listájának megjelenítéséhez.

![Visszatérítés nem engedélyezett](media/Return-policy-page6.png "Nem engedélyezett visszatérítés-típus")



![Fizetési módok listája](media/Return-policy-page5.PNG "Engedélyezett visszatérítés-típusok")


[!INCLUDE[footer-include](../includes/footer-banner.md)]