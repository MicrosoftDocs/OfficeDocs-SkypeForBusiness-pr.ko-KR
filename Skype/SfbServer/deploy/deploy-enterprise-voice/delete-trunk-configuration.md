---
title: 비즈니스용 Skype 서버에서 SIP 트렁크 구성 설정의 기존 컬렉션 삭제
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
ms.assetid: 3b25f14d-884b-42dd-a866-460d276d3e43
description: '요약: 비즈니스용 Skype 서버 제어판을 사용하여 트렁크 구성 설정 컬렉션을 삭제하는 방법을 설명하는 문서입니다.'
ms.openlocfilehash: a9065304860a257a7787c557e59da38d03abfef0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49836978"
---
# <a name="delete-an-existing-collection-of-sip-trunk-configuration-settings-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 SIP 트렁크 구성 설정의 기존 컬렉션 삭제
 
**요약:** 비즈니스용 Skype 서버 제어판을 사용하여 트렁크 구성 설정 컬렉션을 삭제하는 방법을 확인합니다.
  
SIP 트렁크 구성 설정은 중재 서버와 PSTN(Public Switched Telephone Network) 게이트웨이, 서비스 공급자의 IP-Public Branch eXchange(PBX) 또는 SBC(Session Border Controller) 간의 관계와 기능을 정의합니다. 이러한 설정은 지정할 경우 다음과 같은 기능을 수행합니다.
  
- 트렁크에 미디어 우회를 설정할지 여부
    
- RTCP(Realtime Transport Control Protocol) 패킷이 전송되는 조건입니다.
    
- 각 트렁크에 SRTP(Secure Realtime Transport Protocol) 암호화가 필요한지 여부
    
비즈니스용 Skype 서버를 설치하면 전역 SIP 트렁크 구성 설정 컬렉션이 만들어집니다. 이 전역 설정 컬렉션은 삭제할 수 없습니다. 그러나 비즈니스용 Skype 서버 제어판 또는 [Remove-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cstrunkconfiguration?view=skype-ps) cmdlet을 사용하여 전역 컬렉션의 속성을 기본값으로 "다시 설정"할 수 있습니다. 예를 들어 Enable3pccRefer 속성을 True로 설정한 경우 전역 컬렉션을 다시 설정하면 Enable3pccRefer 속성이 기본값인 False로 돌아갑니다.
  
관리자는 개별 PSTN 게이트웨이에 대해 사이트 범위 또는 서비스 범위에서 사용자 지정 트렁크 구성 설정을 만들 수도 있습니다. 이러한 사용자 지정 설정은 제거할 수 있습니다. 이와 같은 사용자 지정 설정을 제거할 때는 다음 사항에 유의하십시오.
  
- 서비스 범위 설정을 제거하면 해당 설정에 의해 관리되는 SIP 트렁크는 사이트에 적용되는 설정(있는 경우)에 의해 관리됩니다. 사이트 설정이 없으면 트렁크는 트렁크 구성 설정의 전역 컬렉션에 의해 관리됩니다.
    
- 사이트 범위 설정을 제거하면 해당 설정에 의해 관리되는 SIP 트렁크는 트렁크 구성 설정의 전역 컬렉션에 의해 관리됩니다.
    
### <a name="to-remove-trunk-configuration-settings-with-skype-for-business-server-control-panel"></a>비즈니스용 Skype 서버 제어판을 사용하여 트렁크 구성 설정을 제거하려면

1. 비즈니스용 Skype 서버 제어판에서 음성 라우팅을 클릭한 다음 **트렁크 구성을 클릭합니다.** 
    
2. **트렁크 구성** 탭에서 삭제할 SIP 트렁크 구성 설정 컬렉션을 선택하고 **편집**, **삭제** 를 차례로 클릭합니다. 같은 작업에서 여러 컬렉션을 삭제하려면 삭제할 첫 번째 컬렉션을 클릭하고 Ctrl 키를 누른 상태로 제거할 추가 컬렉션을 클릭합니다.
    
3. 컬렉션의 **상태** 속성이 **커밋되지 않음** 으로 업데이트됩니다. 변경 내용을 커밋하고 컬렉션을 삭제하려면 **커밋**, **모두 커밋** 을 차례로 클릭합니다.
    
4. **커밋되지 않은 음성 구성 설정** 대화 상자에서 **확인** 을 클릭합니다.
    
5. 비즈니스용 **Skype 서버 제어판** 대화 상자에서 확인을 **클릭합니다.**
    
6. 컬렉션을 삭제하지 않으려는 경우 **커밋** 을 클릭한 다음 **커밋되지 않은 모든 변경 내용 취소** 를 클릭합니다. 비즈니스용 **Skype 서버 제어판** 대화 상자가 나타나면 확인을 **클릭합니다.**
    
## <a name="removing-trunk-configuration-settings-by-using-skype-for-business-server-management-shell-cmdlets"></a>비즈니스용 Skype 서버 관리 셸 cmdlet을 사용하여 트렁크 구성 설정 제거

비즈니스용 Skype 서버 관리 셸 및 **Remove-CsTrunkConfiguration** cmdlet을 사용하여 트렁크 구성 설정을 삭제할 수 있습니다. 이 cmdlet은 비즈니스용 Skype 서버 관리 셸 또는 비즈니스용 Skype 서버 관리 셸의 원격 세션에서 실행할 수 있습니다.
  
### <a name="to-remove-a-specified-collection-of-settings"></a>지정한 설정 컬렉션을 제거하려면

- 다음 명령은 Redmond 사이트에 적용된 트렁크 구성 설정을 제거합니다.
    
  ```powershell
  Remove-CsTrunkConfiguration -Identity site:Redmond
  ```

### <a name="to-remove-all-the-collections-applied-to-the-site-scope"></a>사이트 범위에 적용된 모든 컬렉션을 제거하려면

- 다음 명령은 서비스 범위에 적용된 모든 트렁크 구성 설정을 제거합니다.
    
  ```powershell
  Get-CsTrunkConfiguration -Filter "service:*" | Remove-CsTrunkConfiguration
  ```

### <a name="to-remove-all-the-collections-where-media-bypass-is-enabled"></a>미디어 우회가 사용하도록 설정된 모든 컬렉션을 제거하려면

- 다음 명령은 미디어 바이패스가 사용하도록 설정된 모든 트렁크 구성 설정을 제거합니다.
    
  ```powershell
  Get-CsTrunkConfiguration | Where-Object {$_.EnableBypass -eq $True} | Remove-CsTrunkConfiguration
  ```

자세한 내용은 [Remove-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cstrunkconfiguration?view=skype-ps) cmdlet에 대한 도움말 항목을 참조하십시오.
  

