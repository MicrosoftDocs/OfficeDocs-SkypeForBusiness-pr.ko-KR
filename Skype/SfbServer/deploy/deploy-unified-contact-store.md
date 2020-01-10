---
title: '비즈니스용 Skype 서버에서 통합 된 연락처 저장소 배포 '
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d1c9ebd8-af42-42a0-87d9-fc899fbd7c42
description: '요약: 비즈니스용 Skype 서버에서 통합 된 연락처 저장소를 사용 하도록 설정 합니다.'
ms.openlocfilehash: 6cadba38f40a8ff12501e0fe73f4243dc96a5831
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003068"
---
# <a name="deploy-unified-contact-store-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 통합 된 연락처 저장소 배포
 
**요약:** 비즈니스용 Skype 서버에서 통일 된 연락처 저장소를 사용 하도록 설정 합니다.
  
비즈니스용 Skype 서버에서 통합 된 대화 상대 저장소를 사용 하도록 설정 하는 것은 토폴로지 설정이 필요 하지 않습니다. 사용자를 위해 통합 된 연락처 저장소를 사용 하도록 설정 하려면:
  
- 통합 된 대화 상대 저장소 정책을 사용할 수 있습니다 (기본값 사용 가능).
    
- 사용자는 적어도 한 번은 비즈니스용 Skype를 사용 하 여 로그인 합니다.
    
사용자가 비즈니스용 Skype를 사용 하 여 로그인 할 때 자동으로 발생 하는 사용자의 연락처를 마이그레이션한 후에는 사용자가 비즈니스용 skype 연락처, Outlook 2013 또는 Outlook Web Access를 액세스 하 고 관리할 수 있습니다. 사용자는 비즈니스용 Skype에 로그인 하지 않아도 Outlook 또는 Outlook Web Access에서 연락처를 관리할 수 있습니다.
  
> [!IMPORTANT]
> 사용자가 마이그레이션 후 비즈니스용 Skype에서 로그인 하는 경우에는 연락처 및 그룹을 최신으로 사용할 수 있지만, 사용자는 해당 연락처를 관리 (추가, 삭제, 이동, 태그 지정, untag 또는 수정) 할 수 없습니다. 
  
## <a name="enable-users-for-unified-contact-store"></a>통합 연락처 저장소에 사용자 사용

비즈니스용 Skype 서버를 배포 하 고 토폴로지를 게시 하면 모든 사용자에 대해 통합 대화 저장소가 기본적으로 사용 하도록 설정 됩니다. 비즈니스용 Skype 서버를 배포한 후에는 통합 된 대화 상대 저장소를 사용 하도록 설정 하기 위해 추가 조치를 취할 필요는 없습니다. 그러나 **Set-Csuser서비스 정책** cmdlet을 사용 하 여 통합 된 연락처 저장소를 사용할 수 있는 사용자를 사용자 지정할 수 있습니다. 사이트, 테 넌 트 또는 개인 또는 개인 그룹 별로 전역으로이 기능을 사용 하도록 설정할 수 있습니다.
  
### <a name="to-enable-users-for-unified-contact-store"></a>통합 된 대화 상대 저장소에 대해 사용자를 사용 하도록 설정 하려면

1. 비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype**를 차례로 클릭 한 다음 비즈니스용 **skype server management shell**을 클릭 합니다.
    
2. 다음 중 하나를 수행 합니다.
    
   - 모든 비즈니스용 Skype Server 사용자에 대해 통합 된 연락처 저장소를 전역으로 사용 하도록 설정 하려면 Windows PowerShell 명령줄 인터페이스에서 다음 cmdlet을 실행 합니다.
    
   ```powershell
   Set-CsUserServicesPolicy -Identity global -UcsAllowed $True
   ```

   - 특정 사이트의 사용자에 대해 통합 된 연락처 저장소를 사용 하도록 설정 하려면 프롬프트에 다음을 입력 합니다.
    
   ```powershell
   New-CsUserServicesPolicy -Identity site:<site name> -UcsAllowed $True
   ```

   예를 들면 다음과 같습니다.
    
   ```powershell
   New-CsUserServicesPolicy -Identity site:Redmond -UcsAllowed $True
   ```

   - 테 넌 트에서 통합 된 대화 상대 저장소를 사용 하도록 설정 하려면 프롬프트에 다음을 입력 합니다.
    
   ```powershell
   Set-CsUserServicesPolicy -Tenant <tenantId> -UcsAllowed $True
   ```

   예를 들면 다음과 같습니다.
    
   ```powershell
   Set-CsUserServicesPolicy -Tenant "38aad667-af54-4397-aaa7-e94c79ec2308" -UcsAllowed $True
   ```

   - 특정 사용자에 대해 통합 된 대화 상대 저장소를 사용 하도록 설정 하려면 프롬프트에 다음을 입력 합니다.
    
   ```powershell
   New-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $True
   Grant-CsUserServicesPolicy -Identity "<user display name>" -PolicyName <"policy name">
   ```

    > [!NOTE]
    > 사용자 표시 이름 대신 사용자 별칭 또는 SIP URI를 사용할 수도 있습니다. 
  
    예를 들면 다음과 같습니다.
    
   ```powershell
   New-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $True
   Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "UCS Enabled Users"
   ```

    > [!NOTE]
    > 앞의 예제에서 첫 번째 명령은 UcsAllowed 플래그가 True로 설정 된 UCS를 사용 하는 사용자 별 정책을 새로 만듭니다. 두 번째 명령은 표시 이름: 진구 Myer를 사용 하 여 사용자에 게 정책을 할당 하며,이는: 진구 Myer이 이제 통합 연락처 저장소에 대해 사용 하도록 설정 됨을 의미 합니다.
  
## <a name="migrate-users-to-unified-contact-store"></a>통합 연락처 저장소로 사용자 마이그레이션

사용자의 연락처가 다음과 같이 자동으로 Exchange 2013 서버로 마이그레이션됩니다.
  
- (으)로 지정 된 사용자 서비스 정책에 대 한 모든 권한이 True로 설정 되었습니다.
    
- 이 (가) Exchange 2013 사서함으로 프로 비전 되었으며 사서함에 한 번 이상 로그인 되어 있습니다.
    
- 비즈니스용 Skype 리치 클라이언트를 사용 하 여 로그인 합니다.
    
사용자가 Lync 또는 이전 버전의 클라이언트를 사용 하 여 로그인 하거나 사용자가 Exchange 2013 서버에 연결 되어 있지 않으면 사용자 서비스 정책이 무시 되 고 사용자의 연락처가 비즈니스용 Skype 서버에 남아 있습니다.
  
다음 방법 중 하나를 사용 하 여 사용자의 연락처가 마이그레이션 되었는지 여부를 확인할 수 있습니다. 
  
- 클라이언트 컴퓨터에서 다음 레지스트리 키를 확인 합니다.
    
    HKEY_CURRENT_USER \Software\Microsoft\Office\15.0\Lync\\<SIP URL\>\ucs
    
    사용자의 연락처가 Exchange 2013에 저장 되어 있는 경우이 키에는 2165 값을 사용 하 여 InUCSMode 값이 포함 됩니다.
    
- **테스트 CsUnifiedContactStore** cmdlet을 실행 합니다. 비즈니스용 Skype 서버 관리 셸 명령줄에 다음을 입력 합니다.
    
  ```powershell
  Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"
  ```

    **테스트-CsUnifiedContactStore** 성공 하면 사용자의 연락처가 통일 된 대화 상대 저장소로 마이그레이션됩니다.
    
## <a name="roll-back-migrated-users"></a>마이그레이션된 사용자 롤 롤백

통합 된 대화 상대 저장소 기능을 롤백해야 하는 경우 사용자를 Exchange 2010 또는 Lync Server 2010로 다시 이동 하는 경우에만 연락처를 롤백합니다. 롤백하려면 사용자에 대해 정책을 사용 하지 않도록 설정한 다음 **CsUcsRollback** cmdlet을 실행 합니다. 정책을 사용 하지 않도록 설정 하면 통합 된 대화 상대 저장소 마이그레이션이 다시 시작 되기 때문에 **CsUcsRollback** 단독으로 실행 하는 것 만으로는 영구 롤백을 보장할 수 없습니다. 예를 들어 Exchange 2013이 Exchange 2010로 롤백 된 후 사용자의 사서함이 Exchange 2013로 이동 하는 경우, 통합 된 대화 상대 저장소를 사용 하는 한, 통합 대화 저장소 마이그레이션이 롤백 후 7 일이 지난 후에 다시 시작 됩니다. 사용자 서비스 정책에서 계속 해 서 사용자에 게 사용 하도록 설정 되어 있습니다.
  
다음과 같은 경우에는 **Csuser 사용자** cmdlet이 사용자의 연락처 저장소를 Exchange 2013에서 비즈니스용 Skype 서버로 자동으로 롤백합니다.
  
- 사용자가 비즈니스용 Skype 서버에서 Microsoft Lync Server 2013 또는 Lync Server 2010으로 이동 하는 경우 
    
- 사용자가 비즈니스용 Skype Online에서 비즈니스용 Skype Server 온-프레미스로 이동 하는 경우와 같이 사용자가 상호를 마이그레이션한 경우 또는 그 반대의 경우입니다.
    
백업 데이터베이스에서 통합 된 연락처 저장소 데이터를 가져오면 통합 된 대화 상대 저장소 모드가 내보내기와 가져오기 간에 변경 된 경우 사용자 데이터가 손상 될 수 있습니다. 예를 들면 다음과 같습니다.
  
- 사용자의 연락처가 Exchange 2013으로 마이그레이션될 때까지 연락처 목록을 내보낸 다음 마이그레이션 후 동일한 데이터를 가져오면 통합 된 연락처 저장소 데이터와 연락처 목록이 손상 됩니다.
    
- 사용자를 Exchange 2013으로 마이그레이션하고 마이그레이션을 마이그레이션한 다음 마이그레이션 후에 데이터를 가져오는 이유 중 일부 이유로 인해 통합 된 연락처 저장소 데이터 및 연락처 목록이 손상 될 수 있습니다.
    
> [!IMPORTANT]
> Exchange 사서함을 exchange 2013에서 Exchange 2010로 이동 하기 전에 먼저 비즈니스용 Skype 서버 관리자가 Exchange 2013의 비즈니스용 Skype 서버 사용자 연락처를 Skype로 롤백 해야 합니다. 비즈니스 서버. 통합 된 대화 상대 저장소 연락처를 비즈니스용 Skype 서버에 롤백하려면이 섹션의 뒷부분에 있는 "Exchange 2013에서 비즈니스용 Skype 서버에 대 한 통합 된 대화 상대 저장소를 롤백하는 방법" 절차를 참조 하세요. 
  
 **사용자 대화 상대를 롤백하는 방법:** **이동-CsUser** cmdlet을 사용 하 여 비즈니스용 skype server 2015 및 Lync server 2010 간에 사용자를 이동 하는 경우이 단계를 건너뛸 수 있습니다. **csuser** Cmdlet이 비즈니스용 Skype Server 2015에서 lync server 2010로 이동할 때 통합 된 연락처 저장소를 자동으로 롤백합니다. **이동-CsUser** 는 통합 된 대화 상대 저장소 정책을 사용 하지 않도록 설정 하지 않으므로 사용자가 비즈니스용 Skype 서버 2015로 다시 이동 하는 경우 통합 된 연락처 저장소로의 마이그레이션이 되풀이 됩니다.
  

