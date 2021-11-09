---
title: 2016에서 대역폭 정책 프로필 비즈니스용 Skype 서버
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
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
ms.assetid: a71881ef-b04a-465e-9abb-0577bfd182f3
description: 2013에서 통화 Enterprise Voice 제어에 사용되는 대역폭 정책을 만들거나 비즈니스용 Skype 서버.
ms.openlocfilehash: d1c7391abb535f3d7309809adea5b66a28087c75
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60841910"
---
# <a name="create-bandwidth-policy-profiles-in-skype-for-business-server"></a>2016에서 대역폭 정책 프로필 비즈니스용 Skype 서버 
 
2013에서 통화 Enterprise Voice 제어에 사용되는 대역폭 정책을 만들거나 비즈니스용 Skype 서버. 
  
대역폭 정책은 실시간 오디오 및 비디오의 대역폭 사용에 대한 제한을 정의합니다. 대역폭 정책은 통화 액세스 제어를 위해 여러 네트워크 사이트에 적용할 수 있는bandwidth 정책 프로필에 적용됩니다.
  
CAC 배포에서 설정해야 하는 대역폭 제한에 대한 지침은 Plan [for call admission control in 비즈니스용 Skype 서버.](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md)
  
다음 절차에서 만들어진 예 정책은 전체 오디오 트래픽, 개별 오디오 세션, 전체 비디오 트래픽 및 개별 비디오 세션에 대한 제한을 설정합니다. 예를 들어 5Mb_Link 대역폭 정책 프로필에서는 다음과 같은 제한이 설정됩니다. 
  
- 오디오 제한: 2,000kbps
    
- 오디오 세션 제한: 200kbps
    
- 비디오 제한: 1,400kbps
    
- 비디오 세션 제한: 700kbps
    
> [!NOTE]
> 최소 오디오 세션 제한 값은 40kbps이며, 최소 비디오 세션 제한 값은 100kbps입니다. 
  
### <a name="to-create-bandwidth-policy-profiles-by-using-skype-for-business-server-management-shell"></a>관리 셸을 사용하여 대역폭 정책 프로필을 비즈니스용 Skype 서버

1. 비즈니스용 Skype 서버 시작: **시작,** 모든 프로그램, 비즈니스용 Skype **2015를** 클릭한 다음 관리 **비즈니스용 Skype 서버 를 클릭합니다.**
    
2. 만들려는 각 대역폭 정책 프로필에 대해 New-CsNetworkBandwidthPolicyProfile cmdlet을 실행합니다. 예를 들어 다음을 실행합니다.
    
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

### <a name="to-create-bandwidth-policy-profiles-by-using-skype-for-business-server-control-panel"></a>제어판을 사용하여 대역폭 정책 프로필을 비즈니스용 Skype 서버

1. 제어판을 비즈니스용 Skype 서버 를 니다.
    
2. 왼쪽 탐색 모음에서 **네트워크 구성** 을 클릭합니다.
    
3. **정책 프로필** 탐색 단추를 클릭합니다.
    
4. **새로 만들기** 를 클릭합니다.
    
5. **새 프로필 정책** 페이지에서 **이름** 을 클릭한 후 대역폭 정책 프로필에 대한 이름을 입력합니다.
    
6. **오디오 제한** 을 클릭하고 결합된 모든 오디오 세션에 허용할 최대 kbps를 입력합니다.
    
7. **오디오 세션 제한** 을 클릭하고 각 개별 오디오 세션에 허용할 최대 kbps를 입력합니다.
    
8. **비디오 제한** 을 클릭하고 결합된 모든 비디오 세션에 허용할 최대 kbps를 입력합니다.
    
9. **비디오 세션 제한** 을 클릭하고 각 개별 비디오 세션에 허용할 최대 kbps를 입력합니다.
    
10. 경우에 따라 **설명** 을 클릭하고 이 대역폭 정책 프로필을 설명하는 추가 정보를 입력합니다.
    
11. **커밋** 을 클릭합니다.
    
12. 토폴로지에 대한 대역폭 정책 프로필 만들기를 종료하려면 다른 대역폭 정책 프로필에 대한 설정을 사용하여 4-11단계를 반복합니다.
    
## <a name="see-also"></a>참고 항목

[New-CsNetworkBandwidthPolicyProfile](/powershell/module/skype/new-csnetworkbandwidthpolicyprofile?view=skype-ps)
  
[Get-CsNetworkBandwidthPolicyProfile](/powershell/module/skype/get-csnetworkbandwidthpolicyprofile?view=skype-ps)
  
[Set-CsNetworkBandwidthPolicyProfile](/powershell/module/skype/set-csnetworkbandwidthpolicyprofile?view=skype-ps)
  
[Remove-CsNetworkBandwidthPolicyProfile](/powershell/module/skype/remove-csnetworkbandwidthpolicyprofile?view=skype-ps)