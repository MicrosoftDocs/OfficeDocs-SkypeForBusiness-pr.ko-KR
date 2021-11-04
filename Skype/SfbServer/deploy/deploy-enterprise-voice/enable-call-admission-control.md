---
title: 2016년 8월에 통화 비즈니스용 Skype 서버
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
ms.assetid: 80201105-18f7-4c02-9c71-8df5a952f6c7
description: 2016년 8월 1일부로 비즈니스용 Skype 서버 Enterprise Voice.
ms.openlocfilehash: b35e55bbe0a9929222eb5d67f7449e2247cf91e0
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60775778"
---
# <a name="enable-call-admission-control-in-skype-for-business-server"></a>2016년 8월에 통화 비즈니스용 Skype 서버
 
2016년 8월 1일부로 비즈니스용 Skype 서버 Enterprise Voice. 
  
통화 허용 제어 배포에 대한 네트워크 설정을 구성한 후 CAC를 사용하도록 설정하여 대역폭 정책을 적용해야 합니다.
  
### <a name="to-enable-call-admission-control-by-using-skype-for-business-server-management-shell"></a>관리 셸을 사용하여 통화 비즈니스용 Skype 서버 사용하려면

1. 비즈니스용 Skype 서버 시작: **시작,** 모든 프로그램, 비즈니스용 Skype **2015를** 클릭한 다음 관리 **비즈니스용 Skype 서버 를 클릭합니다.**
    
2. Set-CsNetworkConfiguration cmdlet을 실행하여 네트워크에서 CAC를 사용하도록 설정합니다. 예를 들어 다음을 실행합니다.
    
   ```powershell
   Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 1
   ```

    네트워크에서 CAC를 사용하지 않도록 설정하려면 다음을 실행합니다.
    
   ```powershell
   Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 0
   ```

### <a name="to-enable-call-admission-control-by-using-skype-for-business-server-control-panel"></a>제어판을 사용하여 통화 비즈니스용 Skype 서버 제어를 사용하도록 설정하려면

1. 제어판을 비즈니스용 Skype 서버 를 니다.
    
2. 왼쪽 탐색 모음에서 **네트워크 구성** 을 클릭합니다.
    
3. **전역** 탐색 단추를 클릭합니다.
    
4. 목록에서 **전역** 을 클릭한 다음 **편집** 메뉴에서 **세부 정보 표시** 를 선택합니다.
    
5. **전역 설정 편집** 페이지에서 **통화 허용 제어 사용** 확인란을 선택합니다.
    
    > [!NOTE]
    > 배포 전체에서 통화 허용 제어를 사용하지 않도록 설정하려면 이 확인란을 선택 취소합니다. 
  
6. **커밋** 을 클릭합니다. 
    
## <a name="see-also"></a>참고 항목

[Get-CsNetworkConfiguration](/powershell/module/skype/get-csnetworkconfiguration?view=skype-ps)
  
[Set-CsNetworkConfiguration](/powershell/module/skype/set-csnetworkconfiguration?view=skype-ps)
  
[Remove-CsNetworkConfiguration](/powershell/module/skype/remove-csnetworkconfiguration?view=skype-ps)