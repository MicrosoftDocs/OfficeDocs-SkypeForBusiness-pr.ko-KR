---
title: Skype 채팅방 시스템 도메인 가입 고려 사항
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3034fdcb-7c89-42c4-9c5e-13400e82d88f
ms.collection:
- M365-collaboration
description: 관리자는 Skype 채팅방 시스템 어플라이언스 PC를 Active Directory 도메인에 가입하는 방법과 이를 위한 고려 사항을 배울 수 있습니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: dfcee1421c25903a5ec8deb2f66871ed1d57ef1c
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2020
ms.locfileid: "43905440"
---
<!-- This asset missed in the rebrand, and honestly not sure if it's worth keeping.   -->

# <a name="skype-room-system-domain-joining-considerations"></a>Skype 채팅방 시스템 도메인 가입 고려 사항
 
이 항목을 읽고 Skype 채팅방 시스템 어플라이언스 PC를 도메인에 가입하는 방법을 알아보십시오.
  
## <a name="domain-joining-considerations"></a>도메인 가입 고려 사항

Skype 채팅방 시스템 어플라이언스 PC를 Active Directory 도메인에 가입하거나 작업대에 두면 됩니다. 이 결정을 내리기 전에 다음을 고려합니다.
  
- Skype 채팅방 시스템 어플라이언스 PC를 도메인에 가입하면 조직의 개인 루트 인증서 체인을 자동으로 가져올 수 있습니다.
- Skype 채팅방 시스템 어플라이언스 PC에 도메인 가입을 사용하면 도메인 사용자 및 그룹 관리 권한을 부여할 수 있습니다. 이렇게 하면 로컬 컴퓨터 수준 관리자 계정 암호를 기억할 수 없습니다.
- Skype 채팅방 시스템 어플라이언스 PC를 도메인에 가입할 때 모든 Skype 채팅방 시스템 컴퓨터 개체가 있는 OU에 GPO(그룹 정책 개체) 제외를 제공할 수 있도록 별도의 OU(조직 구성 단위)를 만들어야 합니다. 이렇게 하는 경우 Skype 채팅방 시스템 어플라이언스 PC를 도메인에 가입하기 전에 OU에서 컴퓨터 개체를 만드십시오.
- 대부분의 조직에는 Skype Room System 어플라이언스 PC 기능에 영향을 주는 다음과 같은 GPOS가 있습니다. Skype 채팅방 시스템 OU에서 이러한 GPOS의 상속을 다시 설정하거나 차단해야 합니다.

  - 로그온 세션의 시간 제한(자동 잠금)
  - 전원 관리 관련 정책
  - 추가 인증 단계 요구
  - 로컬 드라이브에 대한 액세스 거부
  - 사용자에게 느린 네트워크 연결 프롬프트
  - 로그온 시 특정 프로그램 시작
  - 모든 도메인에 가입된 머신에 다른 도메인 사용자 계정을 만들 수 있습니다.
  - Skype 채팅방 시스템에 Windows 업데이트 푸시
    
- 또는 어플라이언스 PC를 작업대에 두기로 결정할 수 있습니다. 데스크톱 Microsoft Teams 또는 비즈니스용 Skype 클라이언트와 함께 Skype 채팅방 시스템 어플라이언스 PC에서 루트 인증서 체인을 수동으로 가져와야 합니다. 배포에서 공용 인증서(예: Entrust, VeriSign 등)를 사용하는 경우 루트 인증서 체인을 가져올 필요는 없습니다. 
    
Skype 채팅방 시스템 컴퓨터를 도메인에 가입할 계획인 경우 의도하지 않은 OU에 Skype 채팅방 시스템 머신이 의도하지 않은 OU에 가입하지 않도록 방지하려면 올바른 OU에 가입해야 합니다. Skype 채팅방 시스템 머신에서 다음 cmdlet을 사용하여 올바른 OU에 가입할 수 있으며 LRS 기능을 차단할 수 있는 GPOS를 받지 못합니다. 시스템 관리자 또는 OEM 파트너에게 문의하여 다음 cmdlet을 실행합니다.
  
```
$username = "contso.local\LRS01"
$password = ConvertTo-SecureString "password123" -AsPlainText -Force
$myCred = New-Object System.Management.Automation.PSCredential $username, $password
Add-Computer -DomainName contoso.local -Credential $mycred -OUPath "OU=LyncRoomSystem,OU=Resources,DC=CONTOSO,DC=LOCAL"
```

별도의 OU를 만들고 상속을 차단하는 경우에도 더 높은 수준에서 문제를 일으킬 수 있는 몇 가지 정책이 있습니다. [정책에 대한 설정 없음]이 있는 그룹 정책은 차단 정책 상속 설정을 사용하여 OU를 꺾습니다. 자세한 내용은 그룹 정책 [](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10)) 설명서의 차단 정책 상속과 비교하여 비재정 없음 문서를 참조하세요.
  
이러한 문제를 해결하기 위한 여러 가지 접근 방식이 있을 수 있습니다. Active Directory 전문가에게 문의하여 적절한 GPO 설정이 있는 OU 또는 이전에 설명한 정책이 없는 OU를 제공하도록 하는 것이 좋습니다. Skype 채팅방 시스템 장치에 QoS(서비스 품질)를 사용하도록 설정하는 것이 좋습니다.

## <a name="related-topics"></a>관련 항목
  
[장치 구성: 새로 만들기 또는 기존 항목 편집](/skypeforbusiness/help-topics/help-lscp/device-configuration-create-new-or-edit-existing.md)

[서비스 품질 관리](/skypeforbusiness/plan-your-deployment/network-requirements/network-requirements.#managing-quality-of-service)
