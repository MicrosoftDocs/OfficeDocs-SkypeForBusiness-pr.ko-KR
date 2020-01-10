---
title: 비즈니스용 Skype 서버에서 대역폭 정책 프로필 만들기
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a71881ef-b04a-465e-9abb-0577bfd182f3
description: 비즈니스용 Skype 서버에서 엔터프라이즈 음성 통화 허용 제어에 사용 되는 대역폭 정책을 만들거나 수정 합니다.
ms.openlocfilehash: 86ab5d7fc7ae46223118250626d12107c35b9ef8
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41001768"
---
# <a name="create-bandwidth-policy-profiles-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 대역폭 정책 프로필 만들기 
 
비즈니스용 Skype 서버에서 엔터프라이즈 음성 통화 허용 제어에 사용 되는 대역폭 정책을 만들거나 수정 합니다. 
  
대역폭 정책은 실시간 오디오 및 비디오 형식을 대역폭 사용량에 대 한 제한을 정의 합니다. 대역폭 정책은 호출 허용 제어를 위해 여러 네트워크 사이트에 적용할 수 있는 tobandwidth 정책 프로필에 적용 됩니다.
  
CAC 배포에 설정 해야 하는 대역폭 제한에 대 한 지침은 비즈니스용 [Skype 서버의 통화 허용 제어 계획](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md)을 참조 하세요.
  
다음 절차에서 만든 예제 정책은 전체 오디오 트래픽, 개별 오디오 세션, 전체 비디오 트래픽, 개별 비디오 세션에 대 한 제한을 설정 합니다. 예를 들어 5Mb_Link 대역폭 정책 프로필은 다음 제한을 설정 합니다. 
  
- 오디오 제한: 2000 kbps
    
- 오디오 세션 제한: 200 kbps
    
- 비디오 제한: 1400 kbps
    
- 비디오 세션 제한: 700 kbps
    
> [!NOTE]
> 최소 오디오 세션 제한 값은 40 kbps입니다. 최소 비디오 세션 제한 값은 100 kbps입니다. 
  
### <a name="to-create-bandwidth-policy-profiles-by-using-skype-for-business-server-management-shell"></a>비즈니스용 Skype Server Management Shell을 사용 하 여 대역폭 정책 프로필을 만들려면

1. 비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.
    
2. 만들려는 각 대역폭 정책 프로필에 대해 새 CsNetworkBandwidthPolicyProfile cmdlet을 실행 합니다. 예를 들어 다음을 실행합니다.
    
   ```powershell
   New-CsNetworkBandwidthPolicyProfile -Identity 5Mb_Link -Description "BW profile for 5Mb links" -AudioBWLimit 2000 -AudioBWSessionLimit 200 -VideoBWLimit 1400   -VideoBWSessionLimit 700
   ```

   ```powershell
   New-CsNetworkBandwidthPolicyProfile -Identity 10Mb_Link -Description "BW profile for 10Mb links" -AudioBWLimit 4000 -AudioBWSessionLimit 200 -VideoBWLimit 2800 -VideoBWSessionLimit 700
   ```

   ```powershell
   New-CsNetworkBandwidthPolicyProfile -Identity 50Mb_Link -Description "BW profile for 50Mb links" -AudioBWLimit 20000 -AudioBWSessionLimit 200 -VideoBWLimit 14000 -VideoBWSessionLimit 700
   ```

   ```powershell
   New-CsNetworkBandwidthPolicyProfile -Identity 25Mb_Link -Description "BW profile for 25Mb links" -AudioBWLimit 10000 -AudioBWSessionLimit 200 -VideoBWLimit 7000 -VideoBWSessionLimit 700
   ```

### <a name="to-create-bandwidth-policy-profiles-by-using-skype-for-business-server-control-panel"></a>비즈니스용 Skype Server 제어판을 사용 하 여 대역폭 정책 프로필 만들기

1. 비즈니스용 Skype Server 제어판을 엽니다.
    
2. 왼쪽 탐색 모음에서 **네트워크 구성을**클릭 합니다.
    
3. **정책 프로필** 탐색 단추를 클릭 합니다.
    
4. **새로 만들기**를 클릭 합니다.
    
5. **새 정책 프로필** 페이지에서 **이름을** 클릭 한 다음 대역폭 정책 프로필의 이름을 입력 합니다.
    
6. **오디오 제한을**클릭 한 다음 최대 kbps를 입력 하 여 모든 오디오 세션을 결합할 수 있습니다.
    
7. **오디오 세션 제한을**클릭 한 다음 최대 kbps를 입력 하 여 각 개별 오디오 세션을 허용 합니다.
    
8. **비디오 제한을**클릭 한 다음 최대 kbps를 입력 하 여 모든 비디오 세션을 결합할 수 있습니다.
    
9. **비디오 세션 제한을**클릭 한 다음 최대 kbps를 입력 하 여 각 개별 비디오 세션을 허용 합니다.
    
10. 필요에 따라 **설명을**클릭 한 다음이 대역폭 정책 프로필을 설명 하는 추가 정보를 입력 합니다.
    
11. **커밋**을 클릭합니다.
    
12. 토폴로지에 대 한 대역폭 정책 프로필 만들기를 완료 하려면 다른 대역폭 정책 프로필에 대 한 설정을 사용 하 여 4 ~ 11 단계를 반복 합니다.
    
## <a name="see-also"></a>참고 항목

[새로운 CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/new-csnetworkbandwidthpolicyprofile?view=skype-ps)
  
[Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/get-csnetworkbandwidthpolicyprofile?view=skype-ps)
  
[Set-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/set-csnetworkbandwidthpolicyprofile?view=skype-ps)
  
[제거-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkbandwidthpolicyprofile?view=skype-ps)
