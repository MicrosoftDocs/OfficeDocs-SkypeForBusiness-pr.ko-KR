---
title: 통화 대기 음악 사용자 지정 (비즈니스용 Skype for Business)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3d78e6f9-a4ae-49f4-a89f-4515acb49dac
description: 비즈니스용 Skype 서버 엔터프라이즈 음성을 사용할 때 통화 대기 음악을 사용자 지정 합니다.
ms.openlocfilehash: 61c82a9ba6c817eb3c61e93ae28d76208855e089
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767741"
---
# <a name="customize-call-park-music-on-hold-inskype-for-business"></a>통화 대기 음악 사용자 지정 (비즈니스용 Skype for Business)
 
비즈니스용 Skype 서버 엔터프라이즈 음성을 사용할 때 통화 대기 음악을 사용자 지정 합니다.
  
비즈니스용 Skype 서버와 함께 제공 되는 기본 음악 파일 대신 음악에 사용할 음악 파일을 지정 하 여 저장할 수 있습니다. 유지할 음악을 사용자 지정 하려면 **Set-CsCallParkServiceMusicOnHoldFile** cmdlet을 사용 합니다.
  
> [!NOTE]
> 계속 해 서 음악을 사용자 지정 하 고 여러 사이트의 동일한 음악을 만들려는 경우에는 통화 공원 응용 프로그램을 실행 하는 각 사이트에 대해 음악 파일을 구성 해야 합니다. 
  
### <a name="to-customize-the-music-file"></a>음악 파일을 사용자 지정 하려면

1. 비즈니스용 Skype 서버 관리 셸이 설치 되어 있는 컴퓨터에 RTCUniversalServerAdmins 그룹의 구성원 또는 **대리인 설정 권한에**설명 된 대로 필요한 사용자 권한으로 로그온 합니다.
    
2. 비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.
    
3. 런
    
   ```powershell
   Set-CsCallParkServiceMusicOnHoldFile -Service <ServiceID where the Call Park application resides> -Content <Byte >
   ```

    > [!TIP]
    > **Get-csservice** cmdlet을 사용 하 여 서비스를 식별 합니다. 자세한 내용은 [Get-CsService](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps)를 참조 하세요. 
  
    다음 예제에서는 바이트 배열로 soothingmusic 파일의 내용을 가져와이를 변수에 할당 하는 방법을 보여 줍니다. 그러면 오디오 파일이 통화 공원에 대 한 음악 보존 파일로 지정 됩니다. 자세한 내용은 [Set-CsCallParkServiceMusicOnHoldFile](https://docs.microsoft.com/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps)을 참조 하세요.
    
   ```powershell
   $a = Get-Content -ReadCount 0 -Encoding byte "C:\MoHFiles\soothingmusic.wma"
   Set-CsCallParkServiceMusicOnHoldFile -Service Redmond1-applicationserver-1 -Content $a
   ```

## <a name="see-also"></a>참고 항목

[Set-CsCallParkServiceMusicOnHoldFile](https://docs.microsoft.com/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps)
  
[Get-CsService](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps)
