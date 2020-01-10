---
title: Skype 채팅방 시스템 도메인 참가 고려 사항
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3034fdcb-7c89-42c4-9c5e-13400e82d88f
description: 이 항목에서는 Skype 채팅방 시스템 기기 PC를 도메인에 참가 하는 방법에 대해 알아보세요.
ms.openlocfilehash: b34161f946b2c79508555145635445214159bd61
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003518"
---
# <a name="skype-room-system-domain-joining-considerations"></a>Skype 채팅방 시스템 도메인 참가 고려 사항
 
이 항목에서는 Skype 채팅방 시스템 기기 PC를 도메인에 참가 하는 방법에 대해 알아보세요.
  
## <a name="domain-joining-considerations"></a>도메인 가입 고려 사항

Skype 채팅방 System 기기 PC를 Active Directory 도메인에 가입 하거나 작업 그룹에 남길 수 있습니다. 이러한 결정을 내리기 전에 다음 사항을 고려 하세요.
  
- 도메인-Skype 대화방 시스템 기기 PC에 가입 하면 조직의 개인 루트 인증서 체인을 자동으로 가져올 수 있습니다.
    
- Domain-Skype 채팅방 System 기기 PC에 가입 하면 도메인 사용자와 그룹의 관리자 권한을 부여할 수 있습니다. 이렇게 하면 로컬 컴퓨터 수준 관리자 계정 암호를 따로 저장할 필요가 없습니다.
    
- Skype 채팅방 System 기기 PC를 도메인에 참가 하는 경우, 모든 Skype 룸 시스템 개체가 있는 OU에 대 한 GPO (그룹 정책 개체) 제외를 제공할 수 있도록 별도의 OU (조직 구성 단위)를 만들어야 합니다. 이렇게 하는 경우, Skype 룸 시스템 기기 PC를 도메인에 참가 하기 전에 OU에 기계 개체를 만듭니다.
    
- 많은 조직에는 Skype 실 시스템 기기 PC 기능에 영향을 주는 다음과 같은 Gpo가 있습니다. Skype 대화방 시스템 OU에서 Gpo의 상속을 무시 하거나 차단 해야 합니다. 
    
  - 로그온 세션 제한 시간 (자동 잠금)
    
  - 전원 관리 관련 정책
    
  - 추가 인증 단계 필요
    
  - 로컬 드라이브에 대 한 액세스 거부
    
  - 사용자에 게 느린 네트워크 연결을 묻는 메시지 표시
    
  - 로그온 할 때 특정 프로그램 시작
    
  - 모든 도메인에 가입 된 컴퓨터에서 다른 도메인 사용자 계정을 만듭니다.
    
  - Skype 채팅방 시스템에 Windows 업데이트 푸시
    
- 또는, 기기 PC를 작업 그룹에 그대로 둘 수 있습니다. 비즈니스용 데스크톱 비즈니스용 Skype 클라이언트와 마찬가지로,이를 위해서는 Skype 채팅방 시스템 기기 PC에서 루트 인증서 체인을 수동으로 가져와야 합니다. 비즈니스용 Skype 배포에서 공용 인증서 (예: Entrust, VeriSign 등)를 사용 하는 경우 루트 인증서 체인을 가져오지 않아도 됩니다. 
    
Skype room 시스템 컴퓨터를 도메인에 참가 하는 경우, 실수로 Skype 채팅방 시스템을 Gpo에서 사용할 수 없는 의도 하지 않은 OU에 가입 하는 것을 방지 하려면 올바른 OU에 가입 하 고 있는지 확인 하세요. Skype 대화방 시스템 컴퓨터에서 다음 cmdlet을 사용 하 여 올바른 OU에 가입 하 고 LRS 기능을 차단할 수 있는 Gpo를 수신 하지 않습니다. 다음 cmdlet을 실행 하려면 시스템 관리자 또는 OEM 파트너에 게 문의 하세요.
  
```powershell
$username = "contso.local\LRS01"
$password = ConvertTo-SecureString "password123" -AsPlainText -Force
$myCred = New-Object System.Management.Automation.PSCredential $username, $password
Add-Computer -DomainName contoso.local -Credential $mycred -OUPath "OU=LyncRoomSystem,OU=Resources,DC=CONTOSO,DC=LOCAL"
```

별도의 OU를 만들고 상속을 차단 하는 경우에도 더 높은 수준에서 문제를 일으킬 수 있는 몇 가지 정책이 있습니다. 무시 설정이 없는 그룹 정책은 정책의 상속을 차단 하는 설정을 사용 하는 OU 보다 더 비트 합니다. 자세한 내용은 그룹 정책 설명서에서 [정책 상속을 차단 하는 방법에 대 한 재정의 없음](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10)) 문서를 참조 하세요.
  
이러한 문제를 해결 하는 방법에는 여러 가지가 있을 수 있습니다. Active Directory 전문가와 상의 하 여 적절 한 GPO 설정이 나 적어도 이전에 설명한 정책이 존재 하지 않는 OU를 사용 하는 ou를 제공 하도록 안내 합니다. Skype 채팅방 시스템 장치에 QoS (서비스 품질)를 사용 하도록 설정 하는 것이 좋습니다.

## <a name="see-also"></a>참고 항목
  
[장치 구성: 새로 만들기 또는 기존 항목 편집](../../help-topics/help-lscp/device-configuration-create-new-or-edit-existing.md)

[서비스 품질 관리](../../plan-your-deployment/network-requirements/network-requirements.md#managing-quality-of-service)
