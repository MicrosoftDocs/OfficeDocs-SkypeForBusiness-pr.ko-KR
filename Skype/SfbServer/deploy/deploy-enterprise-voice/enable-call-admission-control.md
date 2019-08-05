---
title: 비즈니스용 Skype 서버에서 통화 허용 제어 사용
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 80201105-18f7-4c02-9c71-8df5a952f6c7
description: 비즈니스용 Skype Server Enterprise Voice에서 통화 허용 제어 기능을 사용 하도록 설정 합니다.
ms.openlocfilehash: ed770a79a7237de682822e8280a13de4516921ec
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192078"
---
# <a name="enable-call-admission-control-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 통화 허용 제어 사용
 
비즈니스용 Skype Server Enterprise Voice에서 통화 허용 제어 기능을 사용 하도록 설정 합니다. 
  
통화 허용 제어 배포에 대 한 네트워크 설정을 구성한 후에는 CAC를 사용 하도록 설정 하 여 대역폭 정책을 적용 해야 합니다.
  
### <a name="to-enable-call-admission-control-by-using-skype-for-business-server-management-shell"></a>비즈니스용 Skype Server Management Shell을 사용 하 여 통화 허용 제어를 사용 하도록 설정 하려면

1. 비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.
    
2. Set-csnetworkconfiguration cmdlet을 실행 하 여 네트워크에서 CAC를 사용 하도록 설정 합니다. 예를 들어 다음을 실행합니다.
    
   ```
   Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 1
   ```

    네트워크에서 CAC를 사용 하지 않도록 설정 하려면 다음을 실행 합니다.
    
   ```
   Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 0
   ```

### <a name="to-enable-call-admission-control-by-using-skype-for-business-server-control-panel"></a>비즈니스용 Skype 서버 제어판을 사용 하 여 통화 허용 제어를 사용 하도록 설정 하려면

1. 비즈니스용 Skype Server 제어판을 엽니다.
    
2. 왼쪽 탐색 모음에서 **네트워크 구성을**클릭 합니다.
    
3. **전역** 탐색 단추를 클릭 합니다.
    
4. 목록에서 **전역** 을 클릭 한 다음 **편집** 메뉴에서 **세부 정보 표시** 를 선택 합니다.
    
5. **전역 설정 편집** 페이지에서 **통화 허용 제어 사용** 확인란을 선택 합니다.
    
    > [!NOTE]
    > 배포 전체에서 통화 허용 제어를 사용 하지 않도록 설정 하려면이 확인란의 선택을 취소 합니다. 
  
6. **커밋**을 클릭합니다. 
    
## <a name="see-also"></a>참고 항목

[Get-Set-csnetworkconfiguration](https://docs.microsoft.com/powershell/module/skype/get-csnetworkconfiguration?view=skype-ps)
  
[Set-Set-csnetworkconfiguration](https://docs.microsoft.com/powershell/module/skype/set-csnetworkconfiguration?view=skype-ps)
  
[제거-Set-csnetworkconfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkconfiguration?view=skype-ps)
