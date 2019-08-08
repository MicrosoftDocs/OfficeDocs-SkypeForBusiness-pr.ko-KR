---
title: 비즈니스용 Skype 서버의 작업을 통해 통화 배포
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4802d733-14ef-4509-92b9-07173614e45f
description: '요약: 비즈니스용 Skype 서버에서 일부 또는 모든 사용자에 대해 작업을 통해 통화를 배포 하는 방법을 알아봅니다.'
ms.openlocfilehash: d1c55e44cae944664a51eaddb2ad54e758d4f52c
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36234523"
---
# <a name="deploy-call-via-work-in-skype-for-business-server"></a>비즈니스용 Skype 서버의 작업을 통해 통화 배포
 
**요약:** 비즈니스용 Skype 서버의 작업을 통해 일부 또는 모든 사용자의 통화를 배포 하는 방법에 대해 알아봅니다.
  
이 단계를 사용 하 여 사용자에 대 한 작업을 통해 전화를 배포 합니다. 계획 고려 사항에 대 한 자세한 내용은 비즈니스용 [Skype 서버의 작업을 통한 통화 계획](../plan-your-deployment/enterprise-voice-solution/call-via-work.md)을 참조 하세요. 이전 버전의 Lync Server 원격 통화 제어는 Lync Server를 사용 하 여 사용자가 PBX 전화를 제어할 수 있도록 하는 기능 이었습니다. 비즈니스용 Skype Server에서이 기능은 업무에의 한 통화를 통해 대체 되었습니다. 
  
## <a name="prerequisites-for-call-via-work"></a>작업을 통한 통화를 위한 필수 조건

직장을 통한 통화는 모든 비즈니스용 Skype Server 프런트 엔드 서버에 자동으로 설치 되는 통합 커뮤니케이션 웹 API (c)를 사용 합니다. 작업을 통해 사용자에 게 전화를 걸 수 있도록 설정 하려면 다음과 같은 필수 구성 요소도 준비 되어 있어야 합니다. 
  
- 프런트 엔드 서버의 일부로 또는 독립 실행형 역할로 중재 서버를 배포 해야 합니다. 또한 IP PBX 게이트웨이를 배포 해야 합니다.
    
- 작업을 통해 전화를 받을 수 있는 모든 사용자에 게는 PBX 전화 시스템의 직접적인 안쪽 전화 접속 ()이 있어야 합니다. 
    
- Enterprise Voice에 대 한 회사 사용자를 통해 모든 통화를 사용 하도록 설정 해야 합니다. 이 작업을 수행 하는 경우 각 사용자에 대 한 비즈니스용 Skype의 번호를 해당 PBX 전화 시스템의 해당 하는 번호를 사용 하 여 구성 해야 합니다. 
    
- 업무를 통해 전화를 사용 하는 모든 사용자에 게는 비즈니스용 Skype 클라이언트의 **고급 연결** 옵션에서 **자동 구성이** 선택 되어 있어야 합니다. 이렇게 하면 클라이언트가 cowa Url을 검색할 수 있습니다. **자동 구성은** 기본적으로 선택 되어 있습니다.
    
- 작업 사용자를 통한 각 통화에 대해 착신 전환 및 동시 연결을 사용 하도록 설정 합니다. 
    
- 작업 사용자를 통한 각 통화에 대해 전화 접속 회의 및 회의 전화 걸기를 사용할 수 있는지 확인 합니다. 이를 통해 이러한 사용자는 비즈니스용 Skype 회의를 시작 하거나 축소할 수 있습니다.
    
- 업무 사용자를 통한 모든 통화에 대해 위임, 팀 통화 및 응답 그룹을 사용 하지 않도록 설정 해야 합니다.
    
## <a name="deploy-call-via-work"></a>회사번호로 전화

필수 구성 요소를 입력 한 후 다음을 수행 합니다.
  
- 배포에 대 한 전역 전화 번호를 만듭니다. 비즈니스용 Skype에서 회사 전화를 통해 전화를 걸고 있는 사용자의 PBX 발신자 ID에 표시 됩니다. 
    
- 회사 정책을 통해 하나 이상의 통화 만들기
    
- 작업 정책을 통해 전화를 통해 전화를 받을 수 있는 각 사용자에 게 통화를 할당 합니다.
    
### <a name="create-the-call-via-work-global-phone-number"></a>회사 전역 전화 번호를 통해 통화 만들기

- 다음 cmdlet을 입력 합니다.
    
  ```
  Set-CsRoutingConfiguration -CallViaWorkCallerId +<PhoneNumber>
  ```

    예를 들어 다음 cmdlet은 전역 전화 번호를 1-555-123-4567으로 설정 합니다.
    
  ```
  Set-CsRoutingConfiguration -CallViaWorkCallerId +15551234567
  ```

### <a name="create-a-call-via-work-policy"></a>회사 정책을 통해 통화 만들기

- 다음 cmdlet을 입력 합니다.
    
  ```
  New-CsCallViaWorkPolicy [-Identity] <XdsIdentity> [-Tenant <guid>] [-Enabled <bool>] [-UseAdminCallbackNumber  <bool>] [-AdminCallbackNumber <string>] [-InMemory] [-Force] [-WhatIf] [-Confirm]  [<CommonParameters>]
  ```

    예를 들어 다음 cmdlet은 ContosoUser1CvWP 이라는 작업 정책을 통해 전화를 만들고, 사용자가 관리 콜백 번호를 사용 해야 하며, 해당 콜백 번호를 1-555-789-1234로 설정 합니다.
    
  ```
  New-CsCallViaWorkPolicy -Identity Tag:ContosoUser1CvWP -Enabled $true -UseAdminCallbackNumber $true -AdminCallbackNumber +15557891234
  ```

### <a name="assign-a-call-via-work-policy-to-a-user"></a>회사 정책을 통해 사용자에 게 전화 할당

- 다음 cmdlet을 입력 합니다.
    
  ```
  Grant-CsCallViaWorkPolicy -Identity <UserName> -PolicyName Tag:<PolicyName>
  ```

    예를 들어 다음 cmdlet은 작업 정책 "ContosoUser1CvWP"를 통해 호출을 **ContosoUser1**라는 사용자에 게 할당 합니다.
    
  ```
  Grant-CsCallViaWorkPolicy -Identity ContosoUser1 -PolicyName Tag:ContosoUser1CvWP
  ```

## <a name="see-also"></a>참고 항목

[비즈니스용 Skype 서버의 작업을 통한 통화 계획](../plan-your-deployment/enterprise-voice-solution/call-via-work.md)

