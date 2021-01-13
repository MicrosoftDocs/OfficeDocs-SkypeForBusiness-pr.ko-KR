---
title: 비즈니스용 Skype 서버에서 직장을 통한 통화 배포
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
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4802d733-14ef-4509-92b9-07173614e45f
description: '요약: 일부 또는 전체 사용자에 대해 비즈니스용 Skype 서버에서 직장 전화 서비스를 배포하는 방법을 설명하는 정보를 제공합니다.'
ms.openlocfilehash: 41a0ae8462b12cabf735a2501e5b22eac64abe42
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825008"
---
# <a name="deploy-call-via-work-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 직장을 통한 통화 배포
 
**요약:** 일부 또는 모든 사용자를 위해 비즈니스용 Skype 서버에서 직장에서 전화를 통해 통화를 배포하는 방법을 배워야 합니다.
  
다음 단계에 따라 사용자를 위해 직장 전화 기능을 배포합니다. 계획 고려 사항은 비즈니스용 Skype 서버의 직장을 통해 [전화하기 계획에 설명됩니다.](../plan-your-deployment/enterprise-voice-solution/call-via-work.md) 이전 버전의 Lync Server 원격 통화 제어는 사용자가 Lync Server를 사용하여 PBX 전화를 제어할 수 있는 기능입니다. 비즈니스용 Skype 서버에서는 이 기능이 직장 전화로 대체됩니다. 
  
## <a name="prerequisites-for-call-via-work"></a>업무를 통한 전화에 대한 선행 작업

UCWA(Unified Communications Web API)를 사용하여 모든 비즈니스용 Skype 서버 프런트 엔드 서버에 자동으로 설치됩니다. 사용자가 직장을 통해 전화를 걸 수 있도록 설정하려면 다음과 같은 선행 사항도 준비되어 있어야 합니다. 
  
- 중재 서버는 프런트 엔드 서버의 일부로 또는 독립 실행형 역할로 배포해야 합니다. IP-PBX 게이트웨이도 배포해야 합니다.
    
- 업무를 통해 전화 기능을 사용할 수 있는 모든 사용자는 PBX 전화 시스템에서 DID(Direct Inward Dialing)가 있어야 합니다. 
    
- 사용자에 대해 모든 업무용 통화 사용자를 사용하도록 설정해야 Enterprise Voice. 이렇게 하는 경우 각 사용자에 대한 비즈니스용 Skype DID 번호를 해당 PBX 전화 시스템에 대한 해당 DID 번호로 구성해야 합니다. 
    
- 업무를 통해 전화를 사용할 모든  사용자는 비즈니스용  Skype 클라이언트의 고급 연결 옵션에서 자동 구성을 선택해야 합니다. 이렇게 하면 클라이언트가 UCWA URL을 검색할 수 있습니다. **자동 구성이** 기본 선택입니다.
    
- 각 업무용 전화 사용자에 대해 통화 전달 및 동시 전화 울림을 사용하도록 설정합니다. 
    
- 각 업무용 전화 사용자에 대해 전화 접속 회의 및 회의 전화 접속이 사용하도록 설정되어 있는지 확인합니다. 이렇게 하면 이러한 사용자가 비즈니스용 Skype 회의에 들어와서 회의에서 에서 나서야 할 수 있습니다.
    
- 모든 통화 사용자에 대해 위임, 팀 통화 및 응답 그룹을 사용하지 않도록 설정해야 합니다.
    
## <a name="deploy-call-via-work"></a>회사번호로 전화

선행 작업을 준비한 후 다음을 합니다.
  
- 업무번호로 전화 걸기 전화를 걸고 있는 사용자의 PBX 발신자 번호에 비즈니스용 Skype가 표시하는 배포용 전역 전화 번호를 생성합니다. 
    
- 하나 이상의 업무로 전화 정책 만들기
    
- 직장에서 전화 기능을 사용할 각 사용자에게 직장 전화 정책 할당
    
### <a name="create-the-call-via-work-global-phone-number"></a>직장번호로 전화 걸기 전역 전화 번호 만들기

- 다음 cmdlet을 입력합니다.
    
  ```powershell
  Set-CsRoutingConfiguration -CallViaWorkCallerId +<PhoneNumber>
  ```

    예를 들어 다음 cmdlet은 전역 전화 번호를 1-555-123-4567로 설정합니다.
    
  ```powershell
  Set-CsRoutingConfiguration -CallViaWorkCallerId +15551234567
  ```

### <a name="create-a-call-via-work-policy"></a>직장 전화 정책 만들기

- 다음 cmdlet을 입력합니다.
    
  ```powershell
  New-CsCallViaWorkPolicy [-Identity] <XdsIdentity> [-Tenant <guid>] [-Enabled <bool>] [-UseAdminCallbackNumber  <bool>] [-AdminCallbackNumber <string>] [-InMemory] [-Force] [-WhatIf] [-Confirm]  [<CommonParameters>]
  ```

    예를 들어 다음 cmdlet은 ContosoUser1CvWP라는 업무용 통화 정책을 만들고, 사용자가 관리자 콜백 번호를 사용하도록 요구하고, 해당 콜백 번호를 1-555-789-1234로 설정합니다.
    
  ```powershell
  New-CsCallViaWorkPolicy -Identity Tag:ContosoUser1CvWP -Enabled $true -UseAdminCallbackNumber $true -AdminCallbackNumber +15557891234
  ```

### <a name="assign-a-call-via-work-policy-to-a-user"></a>사용자에게 직장 전화 정책 할당

- 다음 cmdlet을 입력합니다.
    
  ```powershell
  Grant-CsCallViaWorkPolicy -Identity <UserName> -PolicyName Tag:<PolicyName>
  ```

    예를 들어 다음 cmdlet은 ContosoUser1이라는 사용자에게 업무 시간 전화 정책 "ContosoUser1CvWP"를 **할당합니다.**
    
  ```powershell
  Grant-CsCallViaWorkPolicy -Identity ContosoUser1 -PolicyName Tag:ContosoUser1CvWP
  ```

## <a name="see-also"></a>참고 항목

[비즈니스용 Skype 서버에서 직장을 통한 통화 계획](../plan-your-deployment/enterprise-voice-solution/call-via-work.md)

