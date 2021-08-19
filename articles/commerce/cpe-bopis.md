---
title: BOPIS konfigurálása Dynamics 365 Commerce értékelési környezetben
description: Ez a témakör azt mutatja be, hogyan lehet konfigurálni „online vásárlás, átvétel az áruházban” "(BOPIS) folyamatot a Microsoft Dynamics 365 Commerce-környezetben a kiépítés után.
author: rubendel
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: rubendel
ms.search.validFrom: 2020-04-20
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 1087e13da870a855c703cb87cc2327521acd19e4c205fbf75b343b9bbd8e81b6
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6751601"
---
# <a name="configure-bopis-in-a-dynamics-365-commerce-evaluation-environment"></a>BOPIS konfigurálása Dynamics 365 Commerce értékelési környezetben

[!include [banner](includes/banner.md)]

Ez a témakör azt mutatja be, hogyan lehet konfigurálni „online vásárlás, átvétel az áruházban” "(BOPIS) folyamatot a Microsoft Dynamics 365 Commerce értékelési környezetben a környezet kiépítése után.

## <a name="prerequisite"></a>Előfeltételek

A jelen témakörben ismertetett eljárásokat csak a Commerce értékelési környezet létesítését és konfigurálását követően hajtsa végre. A környezet kiépítésével és konfigurálásával kapcsolatban lásd [Dynamics 365 Commerce értékelési környezet kiépítése](provisioning-guide.md) és [Dynamics 365 Commerce értékelési környezet konfigurálása](./cpe-post-provisioning.md) című részeket.

Miután kiépítette és konfigurálta a Commerce környezetet végponttól végpontig, ezzel a témakörrel engedélyezheti a BOPIS eseteket.

## <a name="configure-the-pos"></a>Pénztár konfigurálása

### <a name="configure-modern-pos"></a>Modern POS konfigurálása

A hitelkártyás fizetést tartalmazó BOPIS esetekhez hardverállomás szükséges. A hardverállomás be van építve a Windows és Android klienseken futó Modern POS-programokba. Ha Cloud POS vagy Modern POS szolgáltatást használ iOS rendszeren, a pénztár (POS) klient párosítani kell egy megosztott hardverállomással. Ez a témakör azt mutatja be, hogyan lehet konfigurálni a BOPIS-t Windows és Android klienseken. A megosztott hardverállomás beállításával kapcsolatos további tudnivalókért lásd: [Retail hardverállomás konfigurálása és telepítése](./retail-hardware-station-configuration-installation.md).

1. Ugorjon a **Kiskereskedelem és kereskedelem \> Csatorna beállítása \> Pénztár beállítása \> Pénztárgépek** pontra.
2. Válassza ki a **SANFRAN-5** pénztárgépet, majd a **Szerkesztés** lehetőséget.
3. Módosítsa a **Hardverprofil** mező értékét **HW002** értékről **HW001** értékre, majd válassza a **Mentés** lehetőséget.
4. A módosítások szinkronizálásához nyissa meg a **Retail és Commerce \> Retail és Commerce IT \> Elosztási ütemezés** menüpontot.
5. Válassza ki az **1090** elosztási ütemezést, majd válassza a műveleti panelen a **Futtatás most** parancsot.
6. Válassza az **Igen** lehetőséget, majd kattintson az **OK** gombra az adatszinkronizálás kezdeményezéséhez. 

### <a name="install-modern-pos"></a>Modern POS telepítése

1. Ugorjon a **Kiskereskedelem és kereskedelem \> Csatorna beállítása \> Pénztár beállítása \> Eszközök** pontra.
2. Válassza ki a **SANFRANCIS-5** eszközt.
3. A műveleti ablaktáblán válassza a **Letöltés**, majd a **Konfigurációs fájl** elemet.
4. Válassza a **Letöltés**, majd a **Retail Modern POS** elemet. 
5. Amikor a **ModernPOSSetup.exe** fájl letöltése befejeződött, válassza a **Fájl megnyitása** lehetőséget.

    ![Fájl megnyitása.](./dev-itpro/media/PAYMENTS/openfile.png)

6. Válassza a **Következő** elemet a telepítési folyamat végrehajtásához. Ha a telepítés befejeződött, válassza a **Bezárás** elemet.

### <a name="activate-modern-pos"></a>Modern POS aktiválása

1. A Windows asztalon válassza a **Start** gombot, és gépelje be a **Retail Modern POS** nevét.
2. Az aktiválás indításához válassza a **Retail Modern POS** alkalmazást.
3. Válassza ki **Következő** lehetőséget. A **Kiszolgáló URL-címe**, **Eszközazonosító** és **Pénztárgép száma** mezőket a rendszernek előzetesen be kell állítania az előző eljárásban letöltött konfigurációs fájlból származó adatokkal.
4. Válassza az **Aktiválás** lehetõséget.
5. Megjelenik egy hitelesítési párbeszédpanel. Válassza ki azt a számlát, amely korábban a **000713 – Andrew Collette** nevű dolgozóhoz társított e-mail-címet használja.

    > [!NOTE]
    > Ha még nem társított egy dolgozót az identitásához, az aktiválás sikertelen lesz. Ebben az esetben kövesse a „Dolgozó társítása az identitásához” szakaszban leírt lépéseket a [Dynamics 365 Commerce értékelési környezete konfigurálása](cpe-post-provisioning.md#associate-a-worker-with-your-identity) témakörben.
    
6. Amikor a program rákérdez, hogy engedélyezze a szervezetnek az eszköz kezelését, válassza a **Csak ez az alkalmazás** lehetőséget.
7. Az aktiválás befejezését követően válassza az **Indítás** elemet.

### <a name="enable-bopis-in-modern-pos"></a>BOPIS engedélyezése a Modern POS rendszerben

1. Jelentkezzen be a Modern POS alkalmazásba a **000713** operátorazonosítóval és **123** jelszóval.
2. A bevezető útmutató videó lejátszása közben válassza a párbeszédablak bal alsó sarkában található két jelölőnégyzetet, majd zárja be a párbeszédablakot.
3. Ha a rendszer nem kéri fel a műszak lezárására, görgessen jobbra az **Üdvözlőlap** oldalon, válassza a **Műszak lezárása**, majd jelentkezzen be a pénztárba.
4. Miután bejelentkezett a rendszerbe, a rákérdezéskor válassza a **Nem pénztárgépfiókkal kapcsolatos művelet végrehajtása** elemet.
5. Az **Üdvözlőlap** oldalon görgessen jobbra, és válassza a **Hardverállomás kiválasztása** műveletet.
6. Válassza a **Kezelés** lehetőséget, majd állítsa a **Hardverállomás használata** beállítást **Be** értékre, majd válassza az **OK** lehetőséget.
7. Jelentkezzen ki a pénztárból, majd ismét jelentkezzen be.
8. Miután bejelentkezett, válassza az **Új műszak megnyitása** lehetőséget,majd válassza a **Pénztárgépfiók** elemet.

## <a name="complete-a-bopis-scenario"></a>BOPIS-eset végrehajtása

### <a name="create-a-storefront-order-for-in-store-pickup"></a>Üzleti megrendelés létrehozása üzletbeli felvételhez

1. Nyissa meg az [E-kereskedelem indítása](./provisioning-guide.md#initialize-e-commerce) lépésben a környezet konfigurációja során megadott URL-címet.
2. Válasszon egy cikket, majd válassza a **Hozzáadás a kosárhoz** lehetőséget.
3. A bevásárlótáska oldalon válassza az utoljára hozzáadott rendelési sorhoz tartozó **Cikk felvétele** lehetőséget.
4. Az **Üzlet kiválasztása** párbeszédablakban adja meg a **San Francisco** értéket, majd válassza a **Keresés** gombot.
5. A találatok listájában keresse meg a san franciscói üzletet, és válassza a **Felvétel itt** elemet.
6. A bevásárlótáska oldalon válassza a **Fizetés vendégként**. 

    > [!NOTE]
    > A fizetés folytatásához el kell fogadnia a cookie-kről szóló értesítést. A fizetés lap tetején egy értesítés jelenik meg szalagcímként.

7. A hitelkártyás fizetési módnál adja meg az alábbi adatokat:

    - **Kártyatulajdonos neve:** Adjon meg bármilyen nevet.
    - **Kártyaszám:** Adja meg a **4111-1111-1111-1111** számot.
    - **Lejárati dátum:** Adja meg: **10/20**.
    - **Kártyaellenőrző kód (CVV):** Adja meg: **737**.

    > [!IMPORTANT]
    > Semmilyen körülmények között ne próbáljon ki tényleges hitelkártya-adatokat a tesztoldalon.

8. Folytassa a fizetést a számlázási cím megadásával, majd válassza a **Mentés és folytatás** elemet.
9. Amikor készen áll a rendelés elküldésére, válassza a **Fizetés** lehetőséget.

### <a name="synchronize-online-orders-to-the-back-office"></a>Online rendelések szinkronizálása a háttérirodával

Az online rendelések szinkronizálásának módjával kapcsolatos információkért lásd: [Online értékesítések és kifizetések feladása](./tasks/posting-online-sales-payments.md).

### <a name="pick-up-an-order-in-the-store"></a>Megrendelés felvéle az üzletben

1. Bejelentkezés a pénztárba.
2. Az **Üdvözlőlap** képernyőn válassza a **Rendelés teljesítése** lehetőséget.
3. A felvehető cikkek listájában válassza az online elküldött megrendeléshez tartozó sort.
4. Miközben a rendelési sor ki van választva, válassza a **Felvétel** elemet.

    A sorcikket a rendszer hozzáadja a tranzakciós képernyőhöz, és az esedékes egyenlegnél **0,00 $** szerepel.

5. Válassza a **0,00 $** értékű esedékes egyenleget, vagy válasszon bármilyen fizetési módot a tranzakció megkötéséhez.

## <a name="troubleshooting"></a>Hibaelhárítás

### <a name="online-orders-that-are-retrieved-in-the-pos-have-a-non-zero-balance-due"></a>A pénztárban beolvasott online rendelések nem 0 értékű esedékes egyenleggel rendelkeznek

Ha egy rendelést üzletben való felvételre olvastak be, és az egyenleg nem 0 (nulla), ellenőrizze, hogy a Modern POS-t használják, és a hardverállomás aktív. Ha Cloud POS vagy Modern POS van használatban iOS rendszeren, ellenőrizze, hogy a megosztott hardverállomás aktív. Az online végzett fizetésekhez beolvasásához valamilyen típusú aktív hardverállomás szükséges.

### <a name="general-issues-with-payment-capture"></a>Általános problémák a kifizetés rögzítésével

Minden általános probléma esetén első lépésként mindig tekintse át a Modern POS vagy az Internet Information Services (IIS) hardverállomás eseménynaplóit. Ezeket a naplókat a Windows eseménynaplókban a következő csomópontokban találja:

- Alkalmazási és szolgáltatási naplók \> Microsoft \> Dynamics \> Commerce-ModernPOS
- Alkalmazási és szolgáltatási naplók \> Microsoft \> Dynamics \> Commerce-hardverállomás

## <a name="additional-resources"></a>További erőforrások

[Dynamics 365 Commerce értékelési környezet áttekintése](cpe-overview.md)

[Dynamics 365 Commerce értékelési környezet kiépítése](provisioning-guide.md)

[Dynamics 365 Commerce értékelési környezet választható funkcióinak konfigurálása](cpe-optional-features.md)

[Dynamics 365 Commerce értékelési környezet GYIK](cpe-faq.md)

[Microsoft Lifecycle Services (LCS)](/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide)

[Retail Cloud Scale Unit (RCSU)](/business-applications-release-notes/october18/dynamics365-retail/retail-cloud-scale-unit)

[Microsoft Azure-portál](https://azure.microsoft.com/features/azure-portal)

[Dynamics 365 Commerce-webhely](https://aka.ms/Dynamics365CommerceWebsite)

[Adyen fizetési összekötő](./dev-itpro/adyen-connector.md?tabs=8-1-3)

[Online fizetési eszközök mentése az Adyen összekötővel](./dev-itpro/adyen-connector-listpi.md)

[Többcsatornás fizetések áttekintése](./omni-channel-payments.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]