---
title: Az MPOS .appx fájl aláírása kódalá aláírási tanúsítvánnyal
description: Ez a témakör bemutatja, hogy hogyan lehet aláírni az MPOS-t a kódalálá aláírási tanúsítványával.
author: mugunthanm
ms.date: 05/27/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: tfehr
ms.custom: 28021
ms.search.region: Global
ms.author: mumani
ms.search.validFrom: 2019-09-2019
ms.openlocfilehash: 38c094de6f94381a809fdb68d2e76d410e406934
ms.sourcegitcommit: 336a0ad772fb55d52b4dcf2fafaa853632373820
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/28/2022
ms.locfileid: "8811085"
---
# <a name="sign-the-mpos-appx-file-with-a-code-signing-certificate"></a>Az MPOS .appx fájl aláírása kódalá aláírási tanúsítvánnyal

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

A Modern POS (MPOS) telepítéséhez alá kell írnia az MPOS alkalmazást egy megbízható szolgáltatótól származó kódalá aláírási tanúsítványával, és telepítenie kell ugyanazt a tanúsítványt minden olyan gépre, ahol az MPOS az aktuális felhasználó megbízható gyökérmappába van telepítve.

Az MPOS alkalmazás tanúsítványos aláírásához használja a **Retail SDK\\Build tool\\Customization.settings** fájlban a következő beállítások valamelyikét:

- Adja hozzá a build lépéseit a Biztonságos fájlfeladat részhez Azure DevOps, és töltse fel a tanúsítványt a fájlfeladat biztonságának érdekében. A biztonságos fájlfeladat kimeneti útvonalának változóját használja paraméterként a Testreszabás.beállítások fájlban.

    > [!NOTE]
    > A biztonságos fájlfeladat nem támogatja a jelszóval védett tanúsítványt. A feladat feltöltése előtt el kell távolítania a jelszót. Mivel a tanúsítvány az Azure rendszer biztonságos feladatára van feltöltve, csak erre a lépésre vonatkozó jelszó távolítható el. A jelszó eltávolítását azonban meg kell vitatni a biztonsági szakértőkkel, hogy megállapítsa, ez-e a megfelelő művelet a projektben. Ne távolítsa el a tanúsítványjelszót más helyzetekben.
- A fájlrendszerben található tanúsítvány használata. Ehhez töltse le vagy generálja a tanúsítványt, és helyezze be azt a fájlrendszerbe, ahol a build fut. A Microsoft által tárolt ügynöknek vagy buildfelhasználónak hozzá kell férni ehhez az elérési úthoz és fájlhoz.
- Az ujjlenyomat segítségével keresse meg a tanúsítványt az üzletben, és jelentkezzen be azzal a tanúsítványsal.

## <a name="use-a-secure-file-task-for-universal-windows-platform-app-signing"></a>Biztonságos fájlfeladat használata az universal Windows Platform alkalmazás aláíráshoz

> [!NOTE]
> Az Azure-kulcsKént tárolt tanúsítványt és az Azure-aláírási eszközt is használhatja a Modern POS .appx fájl és az önkiszolgáló rendszer telepítőinek aláírására. A minta csővezeték-parancsfájlokkal és további információkkal [kapcsolatban a Azure DevOps Retail önkiszolgáló csomagokat generáló csővezeték beállítása](build-pipeline.md#set-up-a-build-pipeline-in-azure-devops-to-generate-retail-self-service-packages).

Az universal Windows Platform (UWP) alkalmazásalá aláírásakor a biztonságos fájlfeladat használata ajánlott. A csomagalá aláírásával kapcsolatos további tudnivalókat lásd A csomagalá [aláírásának konfigurálása](/windows/uwp/packaging/auto-build-package-uwp-apps#configure-package-signing). Ez a folyamat a következő képben látható.

![MPOS-alkalmazás aláírási folyamat](media/POSSigningFlow.png)

> [!NOTE]
> Az OOB-csomagolás jelenleg csak az .appx fájl aláírását támogatja, a folyamat nem írja alá a különböző önkiszolgáló telepítőket, például az MPWS, a HOPU és a HWS adatokat. Manuálisan kell aláírnia a SignTool vagy más aláírási eszközök segítségével. Az .appx fájl aláírásához használt tanúsítványt telepíteni kell arra a gépre, ahol a Modern POS telepítve van.

## <a name="steps-to-configure-the-certificate-for-signing-in-azure-pipelines"></a>Az Azure csővezeték-ekben való naplózáshoz szükséges tanúsítvány konfigurálás lépései

### <a name="certificate-in-the-file-systemsecure-location"></a>Tanúsítvány a fájlrendszerben/biztonságos helyen

Töltse le [a DownloadFile feladatot,](/visualstudio/msbuild/downloadfile-task) és adja hozzá a feladat a buildfolyamat első lépéseként. A biztonságos fájl feladat használatának előnye az, hogy a fájl titkosítva van, és a lemezre kerül a build során, függetlenül attól, hogy a csővezeték sikeresen működik, sikertelen vagy megszakad. A fájl törlődik a letöltési helyről, miután a felépítési folyamat befejeződött.

1. Töltse le és adja hozzá a biztonságos fájlfeladatot az Azure összeállítási folyamat első lépéseként. A biztonságos fájlfeladat letölthető a [DownloadFile fájlból](https://marketplace.visualstudio.com/items?itemName=automagically.DownloadFile).
1. Töltse fel a tanúsítványt a biztonságos fájlfeladatba, és állítsa be a hivatkozás nevét a Kimeneti változók alatt, amint azt a következő kép mutatja.
    > [!div class="mx-imgBorder"]
    > ![A fájlfeladat biztonságossá teve.](media/SecureFile.png)
1. Új változó létrehozása az Azure csővezeték-szolgáltatásban **az Új változó kiválasztásával a** **Változók** lapon.
1. Adjon nevet a változónak az értékmezőben, **például MySigningCert**.
1. Mentse a változót.
1. Nyissa meg a **RetailSDK\\BuildTools** **testreszabási.beállításait**, és frissítse a **ModernPOSPackageCertificateKeyFile** fájlt a folyamatban létrehozott változónévvel (3. lépés). Példa:

    ```Xml
    <ModernPOSPackageCertificateKeyFile Condition="'$(ModernPOSPackageCertificateKeyFile)' ==''">$(MySigningCert)</ModernPOSPackageCertificateKeyFile>
    ```
    Erre a lépésre akkor van szükség, ha a tanúsítvány nem jelszóval védett. Ha a tanúsítvány jelszóval védett, folytassa a következő lépésekkel.
    
1. Ha szeretné időbélyegzővel időbélyegzőt az MPOS .appx fájllal aláírni, nyissa meg a Retail SDK Build tool **Customization.settings \\\\ fájlt,** és frissítse a ModernPOSPackageCertificateTimestamp változót **az időbélyeg-szolgáltatóval (**`http://timestamp.digicert.com` például).
1. A csővezeték Változói lapján **adjon** hozzá egy új biztonságos szöveges változót. Állítsa be a **nevet a MySigningCert.titkos** névre, és adja meg a tanúsítványhoz hozzárendelt jelszó értékét. A változó biztonságának érdekében válassza ki a zárolási ikont.
1. Powershell Parancsfájl-feladat **hozzáadása a csővezetékhez (a Biztonságos fájl letöltése után és a** buildlépés előtt). Adja meg **a Megjelenítendő** nevet, és állítsa be a típust Inline **típusúként**. A következők másolása és beillesztése a forgatókönyv szakaszba.

    ```powershell
    Write-Host "Start adding the PFX file to the certificate store."
    $pfxpath = '$(MySigningCert.secureFilePath)'
    $secureString = ConvertTo-SecureString "$(MySigningCert.secret)" -AsPlainText -Force
    Import-PfxCertificate -FilePath $pfxpath -CertStoreLocation Cert:\CurrentUser\My -Password $secureString
    ```

1. Nyissa meg **a Testreszabás.beállítási** fájlt **a RetailSDK\\BuildTools** eszközből, és frissítse a **ModernPOSPackageCertificateTolásbprint-fájlt** a tanúsítvány ujjlenyomat-értékével.

    ```Xml
       <ModernPOSPackageCertificateThumbprint Condition="'$(ModernPOSPackageCertificateThumbprint)' == ''"></ModernPOSPackageCertificateThumbprint>
    ```
 
A tanúsítvány ujjlenyomatának beolvasásával kapcsolatos részleteket [lásd a tanúsítvány ujjlenyomatának beolvasásával kapcsolatban](/dotnet/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate#to-retrieve-a-certificates-thumbprint). 

## <a name="download-or-generate-a-certificate-to-sign-the-mpos-app-manually-using-msbuild-in-sdk"></a>Tanúsítvány letöltése vagy létrehozása az MPOS-alkalmazásnak az MSbuild készletben való manuális aláírásához

Ha letöltött vagy generált tanúsítványt használnak az MPOS alkalmazás aláírására, akkor a **BuildTools\\Customization.settings** fájlBan található **ModernPOSPackageCertificateKeyFile** csomópont frissítése, amely a PFX-fájl helyére (**$(SdkReferencesPath)\\appxsignkey.pfx**) mutat. Példa:

```xml
<ModernPOSPackageCertificateKeyFile Condition="'$(ModernPOSPackageCertificateKeyFile)' ==''">$(SdkReferencesPath)\appxsignkey.pfx</ModernPOSPackageCertificateKeyFile>
```

Ebben az esetben a tanúsítványfájl neve **appxsignkey.pfx**, amely a **Retail SDK\\ Hivatkozás** mappájában található.

## <a name="use-thumbprint-to-sign-the-mpos-app"></a>Ujjlenyomat használata az MPOS alkalmazás aláírására

Ha az ujjlenyomat segítségével aláírja az MPOS alkalmazást, akkor telepítse helyileg a tanúsítványt. Az ujjlenyomat értékének frissítése a **ModernPOSPackageCertificateThumbprint** csomópontban a **BuildTools\\Customization.settings** fájlban.

Ez a beállítás akkor működik, ha a buildfelhasználó helyi felhasználó. Ha azonban a Azure DevOps megbízottakat használja a build generál használatára, akkor lehet, hogy az ügynöknek nincs engedélye hozzáférni a tanúsítvány aláíráshoz való hozzáféréshez, vagy a buildgépen nem lesz telepítve a tanúsítvány. Ebben az esetben a megoldás az, hogy a buildfelhasználót helyi felhasználóra módosítják, és a mezőbe telepítik a tanúsítványt. Ez a beállítás azonban nem működik, ha nincs rendszergazdai hozzáférése a jelölőnégyzethez.

> [!NOTE]
> Ha a .pfx fájl vagy a biztonságos fájl feladat beállítás használható az alkalmazás aláírására, **akkor hagyja üresen a ModernPOSPackageCertificateTprintbprint** **csomópontot a Testreszabás.beállítások** között. Ha az ujjlenyomat lehetőséget használja, akkor hagyja **üresen a ModernPOSPackageCertificateKeyFile** mezőt. Ha mindkét érték frissítve van, akkor a build nem fog sikerülni.

### <a name="certification-renewal"></a>Tanúsítvány megújítása

### <a name="renew-a-certificate-from-trusted-ca"></a>Tanúsítvány megújítása a megbízható hitelesítésszolgáltatótól

Forduljon a tanúsító hatósághoz a tanúsítvány megújítási folyamatáért. Megbízható tanúsítvány esetén nincs szükség semmilyen műveletre az MPOS oldalon.

### <a name="renew-a-self-signed-certificate"></a>Az öna aláírt tanúsítvány megújítása

Ne használja a Retail SDK termékfejlesztői készletében termeléshez elérhető mintabizonylványt. Csak fejlesztési célokra használható. A Contoso-minta tanúsítvány nem újítható meg, és a Retail SDK 10.0.16-os vagy korábbi verziójában szereplő mintabizonyítvány 2020. december 31-én lejár. Ha ezt a tanúsítványt vagy önálló aláírt tanúsítványt egy testreszabott Modern POS-aláírásra használtak, akkor nagy lehetőség van arra, hogy a Modern POS a mai dátum után nem fog megfelelően működni.
 
### <a name="impact"></a>Hatás
 
Ha a fentiek igazak, akkor az a probléma, hogy a telepítő 2020. december 31-e után nem fog tudni futni. A vállalati it-házirendtől függően előfordulhat, hogy a Modern POS nem fog tudni használni. Fontos, hogy a dátumot ideiglenesen egy jövőbeli dátumra módosítva tesztelje a tesztet, hogy megállapítsa, milyen hatással van a szervezetre.
 
### <a name="steps-to-determine-the-issue"></a>A probléma megállapításának lépései
 
1.  A Windows-beállítások segítségével módosíthatja a számítógép óraóráját a 2021-es évre megadott dátumra és időpontra.
2.  Ellenőrizze, hogy a Modern POS megnyitható-e, lehetséges-e a bejelentkezés, és el lehet-e végrehajtani a tranzakciót.
3.  Győződjön meg róla, hogy a Modern POS önkiszolgáló szolgáltatás telepítője futtatható, és ha igen, a telepítés sikeresen befejeződik.
4.  A Windows órabeállításának visszaállítása a megfelelő dátumra és időpontra.
 
Ha ezeket a lépéseket probléma nélkül el tudja külön-külön végrehajtani, akkor az aktuális tanúsítványt 2020. december 31-én tudja kezelni.  
 
### <a name="steps-going-forward"></a>A lépések előre haladnak 

Kifejezetten ajánljuk, hogy újítsa meg a korábban használt tanúsítványt. Javasoljuk, hogy szerezzen be egy új tanúsítványt. Ehhez a következő műveletek egyikét kell végrehajtania:
 
- **Preferált** – kódalálá aláírási tanúsítványának beszerzése megbízható hitelesítésszolgáltatótól.

- **Nem preferált** – önaláírt aláírási tanúsítvány létrehozása használatra. Ez általában csak fejlesztési célokat szolgál egy tartományon belül, és nem ajánlott termelésre. 

- **Ideiglenes megoldásként elérhető** – a contosoi kód új aláírási tanúsítványának használata. Ezt általában tesztelési célokra használják, ezért nem ajánlott élesben telepíteni.
 
Ezután hozzon létre egy új, testreszabott Modern POS-csomagot, amelyet ezzel a tanúsítványsal aláírással szereznek be a fenti műveletek egyikből. A tanúsítványtól függően az alábbi lépések valamelyikét kell követni:
 
- Új, megbízható tanúsítvány (vagy új, önkiszolgáló aláírású tanúsítvány) használata esetén minden eszközre telepítenie kell egy új tanúsítványt. Ezt követően el kell távolítania az újonnan létrehozott Modern POS-csomagot (telepítőt), el kell távolítania a meglévő alkalmazást, majd újra kell telepítenie az új Modern POS-csomagot. A Modern POS eszköz aktiválását minden eszközön végre kell majd végeznie.

- A megújításos Contoso-tanúsítvány használata esetén minden eszközre telepítenie kell az új tanúsítványt, és telepítenie kell a Modern POS-csomagot (telepítő). Az eltávolítás nem szükséges, azonban újra kell telepítenie az eszközön. Ne feledje, hogy a Modern POS eszköz aktiválása nem szükséges. Ez a lehetőség ideiglenes megoldás. Csak akkor használja ezt a lehetőséget, ha el kell kerülni az újraaktiválást, és fel kell oldani a problémát, mielőtt beszerez egy új megbízható tanúsítványt.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
