---
title: 비즈니스용 통화 파킹된 통화 음악 사용자 지정
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 비즈니스용 Skype 서버 2016에서 통화 파크 음악 Enterprise Voice.
ms.openlocfilehash: 766b51895acda27c0558352968d21a39764b13a6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49837078"
---
# <a name="customize-call-park-music-on-hold-inskype-for-business"></a>비즈니스용 통화 파킹된 통화 음악 사용자 지정
 
비즈니스용 Skype 서버 2016에서 통화 파크 음악 Enterprise Voice.
  
비즈니스용 Skype 서버와 함께 제공된 기본 음악 파일 대신 보류된 음악에 사용할 음악 파일을 직접 지정할 수 있습니다. 대기 음악을 사용자 지정하려면 **Set-CsCallParkServiceMusicOnHoldFile** cmdlet을 사용합니다.
  
> [!NOTE]
> 보류된 음악을 사용자 지정하고 여러 사이트에 대해 동일한 음악을 사용하려면 통화 파크 응용 프로그램을 실행하는 각 사이트에 대해 음악 파일을 구성해야 합니다. 
  
### <a name="to-customize-the-music-file"></a>음악 파일을 사용자 지정하려면

1. 비즈니스용 Skype 서버 관리 셸이 RTCUniversalServerAdmins 그룹의 구성원 또는 위임 설치 권한에 설명된 필요한 사용자 권한으로 설치된 컴퓨터에 로그온합니다. 
    
2. 비즈니스용 Skype 서버 관리 셸 시작: **시작,** 모든 **프로그램,** 비즈니스용 **Skype 2015,** 비즈니스용 Skype 서버 관리 셸을 **클릭합니다.**
    
3. 을 실행합니다.
    
   ```powershell
   Set-CsCallParkServiceMusicOnHoldFile -Service <ServiceID where the Call Park application resides> -Content <Byte >
   ```

    > [!TIP]
    > **Get-CsService** cmdlet을 사용하여 서비스를 식별합니다. 자세한 내용은 [Get-CsService를 참조합니다.](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps) 
  
    다음 예에서는 soothingmusic.wma 파일의 내용을 바이트 배열로 가져와서 변수에 지정하는 방법을 보여 줍니다. 그런 후에 오디오 파일은 통화 대기용 대기 음악 파일로 지정됩니다. 자세한 내용은 [Set-CsCallParkServiceMusicOnHoldFile을 참조합니다.](https://docs.microsoft.com/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps)
    
   ```powershell
   $a = Get-Content -ReadCount 0 -Encoding byte "C:\MoHFiles\soothingmusic.wma"
   Set-CsCallParkServiceMusicOnHoldFile -Service Redmond1-applicationserver-1 -Content $a
   ```

## <a name="see-also"></a>참고 항목

[Set-CsCallParkServiceMusicOnHoldFile](https://docs.microsoft.com/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps)
  
[Get-CsService](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps)
