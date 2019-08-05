---
title: 비즈니스용 Skype 서버에서 SIP 트렁크 구성 설정의 기존 모음 삭제
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
ms.assetid: 3b25f14d-884b-42dd-a866-460d276d3e43
description: '요약: 비즈니스용 Skype 서버 제어판을 사용 하 여 트렁크 구성 설정 모음을 삭제 하는 방법에 대해 알아봅니다.'
ms.openlocfilehash: 830f5c42e26c4ef7a5ffca0a57fc7e70c2509f83
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36189039"
---
# <a name="delete-an-existing-collection-of-sip-trunk-configuration-settings-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 SIP 트렁크 구성 설정의 기존 모음 삭제
 
**요약:** 비즈니스용 Skype 서버 제어판을 사용 하 여 트렁크 구성 설정 모음을 삭제 하는 방법에 대해 알아봅니다.
  
SIP 트렁크 구성 설정은 중재 서버와 PSTN (공개 통신 네트워크) 게이트웨이, IP-공용 분기 교환 (PBX) 또는 서비스 공급자의 SBC (세션 경계 컨트롤러) 간에 관계와 접근 권한 값을 정의 합니다. 이러한 설정은 다음을 지정 하는 등의 작업을 수행 합니다.
  
- Trunks에서 미디어 바이패스를 사용 해야 하는지 여부
    
- RTCP (실시간 전송 제어 프로토콜) 패킷이 전송 되는 조건입니다.
    
- 각 트렁크에서 보안 실시간 전송 프로토콜 (SRTP) 암호화가 필요한 지 여부
    
비즈니스용 Skype 서버를 설치 하면 SIP 트렁크 구성 설정의 전역 컬렉션이 생성 됩니다. 이 전역 설정 모음은 삭제할 수 없습니다. 그러나 비즈니스용 Skype Server 제어판 또는 [set-cstrunkconfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cstrunkconfiguration?view=skype-ps) cmdlet을 사용 하 여 전역 컬렉션의 속성을 기본값으로 "다시 설정" 할 수 있습니다. 예를 들어 Enable3pccRefer 속성을 True로 설정한 경우 전역 컬렉션을 다시 설정 하면 Enable3pccRefer 속성은 기본값으로 False로 되돌려집니다.
  
또한 관리자는 사이트 범위 또는 서비스 범위 (개별 PSTN 게이트웨이의 경우)에서 사용자 지정 트렁크 구성 설정을 만들 수 있습니다. 이러한 사용자 지정 설정은 제거할 수 있습니다. 이러한 사용자 지정 설정을 제거 하는 경우 다음 사항에 유의 하세요.
  
- 서비스 범위 설정을 제거 하는 경우 해당 설정에서 관리 하는 SIP 트렁크는 해당 사이트에 적용 된 설정 (있는 경우)에 의해 관리 됩니다. 사이트 설정이 없는 경우 해당 trunks는 트렁크 구성 설정의 전역 컬렉션을 통해 관리 됩니다.
    
- 사이트 범위 설정을 제거 하면 해당 설정으로 관리 되는 모든 SIP trunks는 트렁크 구성 설정의 전역 컬렉션에서 관리 됩니다.
    
### <a name="to-remove-trunk-configuration-settings-with-skype-for-business-server-control-panel"></a>비즈니스용 Skype Server 제어판에서 트렁크 구성 설정을 제거 하려면

1. 비즈니스용 Skype 서버 제어판에서 **음성 라우팅을** 클릭 한 다음 **트렁크 구성을**클릭 합니다.
    
2. **트렁크 구성** 탭에서 삭제할 SIP 트렁크 구성 설정 모음을 선택 하 고 **편집** 을 클릭 한 다음 **삭제**를 클릭 합니다. 동일한 작업에서 여러 컬렉션을 삭제 하려면 삭제할 첫 번째 컬렉션을 클릭 한 다음 Ctrl 키를 누른 채 제거할 추가 모음을 클릭 합니다.
    
3. 컬렉션에 대 한 State 속성이 **커밋되지**않은 **상태로** 업데이트 됩니다. 변경 내용을 커밋하고 컬렉션을 삭제 하려면 **커밋을** 클릭 한 다음 **모두 커밋을**클릭 합니다.
    
4. 커밋되지 않은 **음성 구성 설정** 대화 상자에서 **확인**을 클릭 합니다.
    
5. **비즈니스용 Skype Server 제어판** 대화 상자에서 **확인을**클릭 합니다.
    
6. 생각이 바뀌어 컬렉션을 삭제 하지 않기로 결정 한 경우에는 **커밋을** 클릭 한 다음 커밋되지 않은 **변경 내용 모두 취소**를 클릭 합니다. **비즈니스용 Skype 서버 제어판** 대화 상자가 표시 되 면 **확인**을 클릭 합니다.
    
## <a name="removing-trunk-configuration-settings-by-using-skype-for-business-server-management-shell-cmdlets"></a>비즈니스용 Skype Server Management Shell Cmdlet을 사용 하 여 트렁크 구성 설정 제거

비즈니스용 Skype Server Management Shell 및 **set-cstrunkconfiguration** cmdlet을 사용 하 여 트렁크 구성 설정을 삭제할 수 있습니다. 비즈니스용 Skype 서버 관리 셸에서 또는 비즈니스용 Skype Server Management Shell의 원격 세션에서이 cmdlet을 실행할 수 있습니다.
  
### <a name="to-remove-a-specified-collection-of-settings"></a>지정 된 설정 모음을 제거 하려면

- 다음 명령은 Redmond 사이트에 적용 된 트렁크 구성 설정을 제거 합니다.
    
  ```
  Remove-CsTrunkConfiguration -Identity site:Redmond
  ```

### <a name="to-remove-all-the-collections-applied-to-the-site-scope"></a>사이트 범위에 적용 된 모든 컬렉션을 제거 하려면

- 이 명령은 서비스 범위에 적용 된 모든 트렁크 구성 설정을 제거 합니다.
    
  ```
  Get-CsTrunkConfiguration -Filter "service:*" | Remove-CsTrunkConfiguration
  ```

### <a name="to-remove-all-the-collections-where-media-bypass-is-enabled"></a>미디어 바이패스를 사용 하도록 설정 된 모든 컬렉션을 제거 하려면

- 다음 명령은 미디어 바이패스를 사용 하도록 설정 된 모든 트렁크 구성 설정을 제거 합니다.
    
  ```
  Get-CsTrunkConfiguration | Where-Object {$_.EnableBypass -eq $True} | Remove-CsTrunkConfiguration
  ```

자세한 내용은 [제거 set-cstrunkconfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cstrunkconfiguration?view=skype-ps) cmdlet에 대 한 도움말 항목을 참조 하세요.
  

