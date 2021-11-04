---
title: 비즈니스용 에디션에서 통화 파킹 음악 사용자 지정
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3d78e6f9-a4ae-49f4-a89f-4515acb49dac
description: 통화 파크 음악의 보류를 비즈니스용 Skype 서버 Enterprise Voice.
ms.openlocfilehash: 925749819a041ed451df816902dae8b932cffbbd
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60753619"
---
# <a name="customize-call-park-music-on-hold-inskype-for-business"></a>비즈니스용 에디션에서 통화 파킹 음악 사용자 지정
 
통화 파크 음악의 보류를 비즈니스용 Skype 서버 Enterprise Voice.
  
음악 파일과 함께 제공된 기본 음악 파일 대신 보류된 음악에 사용할 음악 파일을 직접 지정할 비즈니스용 Skype 서버. 대기 음악을 사용자 지정하려면 **Set-CsCallParkServiceMusicOnHoldFile** cmdlet을 사용합니다.
  
> [!NOTE]
> 보류된 음악을 사용자 지정하고 여러 사이트에 대해 동일한 음악을 사용하려는 경우 통화 파크 응용 프로그램을 실행하고 있는 각 사이트에 대해 음악 파일을 구성해야 합니다. 
  
### <a name="to-customize-the-music-file"></a>음악 파일을 사용자 지정하려면

1. 비즈니스용 Skype 서버 관리 셸이 RTCUniversalServerAdmins 그룹의 구성원으로 설치되거나 설치 권한 위임에 설명된 필요한 사용자 권한으로 컴퓨터에 **로그온합니다.**
    
2. 비즈니스용 Skype 서버 시작: **시작,** 모든 프로그램, 비즈니스용 Skype **2015를** 클릭한 다음 관리 **비즈니스용 Skype 서버 를 클릭합니다.**
    
3. 을(를) 실행합니다.
    
   ```powershell
   Set-CsCallParkServiceMusicOnHoldFile -Service <ServiceID where the Call Park application resides> -Content <Byte >
   ```

    > [!TIP]
    > **Get-CsService** cmdlet을 사용하여 서비스를 식별합니다. 자세한 내용은 [Get-CsService 를 참조합니다.](/powershell/module/skype/get-csservice?view=skype-ps) 
  
    다음 예에서는 soothingmusic.wma 파일의 내용을 바이트 배열로 가져와서 변수에 지정하는 방법을 보여 줍니다. 그런 후에 오디오 파일은 통화 대기용 대기 음악 파일로 지정됩니다. 자세한 내용은 [Set-CsCallParkServiceMusicOnHoldFile을 참조합니다.](/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps)
    
   ```powershell
   $a = Get-Content -ReadCount 0 -Encoding byte "C:\MoHFiles\soothingmusic.wma"
   Set-CsCallParkServiceMusicOnHoldFile -Service Redmond1-applicationserver-1 -Content $a
   ```

## <a name="see-also"></a>참고 항목

[Set-CsCallParkServiceMusicOnHoldFile](/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps)
  
[Get-CsService](/powershell/module/skype/get-csservice?view=skype-ps)