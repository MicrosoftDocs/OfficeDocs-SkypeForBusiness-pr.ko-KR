---
title: '통합 연락처 저장소를 비즈니스용 Skype 서버 '
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: d1c9ebd8-af42-42a0-87d9-fc899fbd7c42
description: '요약: 통합 연락처 저장소를 비즈니스용 Skype 서버.'
---

# <a name="deploy-unified-contact-store-in-skype-for-business-server"></a>통합 연락처 저장소를 비즈니스용 Skype 서버
 
**요약:** 통합 연락처 저장소를 비즈니스용 Skype 서버.
  
통합 연락처 저장소를 비즈니스용 Skype 서버 토폴로지 설정이 필요하지 않습니다. 사용자에 대해 통합 연락처 저장소를 사용하도록 설정하려면
  
- 통합 연락처 저장소 정책이 사용하도록 설정됩니다(기본값 사용).
    
- 사용자가 한 번 이상 비즈니스용 Skype 로그인합니다.
    
사용자의 연락처가 마이그레이션되고 나면 사용자가 비즈니스용 Skype 로그인할 때 자동으로 수행되며 사용자는 비즈니스용 Skype, Outlook 2013 또는 Outlook Web Access에서 비즈니스용 Skype 연락처에 액세스하고 관리할 수 있습니다. 사용자가 웹 액세스 또는 웹 액세스에서 연락처를 관리하기 위해 비즈니스용 Skype 로그인할 Outlook Outlook 없습니다.
  
> [!IMPORTANT]
> 사용자가 마이그레이션 후 비즈니스용 Skype 로그인하면 연락처 및 그룹을 사용할 수 있으며 최신 상태이지만 사용자가 해당 연락처를 관리할 수 없습니다(즉, 추가, 삭제, 이동, 태그 지정, 태그 지정 취소 또는 수정). 
  
## <a name="enable-users-for-unified-contact-store"></a>사용자가 통합 연락처 저장소를 사용할 수 있도록 설정

토폴로지 비즈니스용 Skype 서버 배포하면 기본적으로 모든 사용자에 대해 통합 연락처 저장소가 사용하도록 설정됩니다. 통합 연락처 저장소를 배포한 후 통합 연락처 저장소를 사용하도록 설정하기 위해 추가 작업을 수행하지 비즈니스용 Skype 서버. 하지만 **Set-CsUserServicesPolicy** cmdlet을 사용해서 통합 연락처 저장소를 사용할 수 있는 사용자를 사용자 지정할 수 있습니다. 이 기능은 전역, 사이트별, 테넌트별 또는 개인이나 개인 그룹별로 설정할 수 있습니다.
  
### <a name="to-enable-users-for-unified-contact-store"></a>통합 연락처 저장소에 대해 사용자를 설정하려면

1. 관리 비즈니스용 Skype 서버 시작 **: 시작,** 모든 프로그램, 비즈니스용 Skype, 관리 **비즈니스용 Skype 서버 클릭합니다**.
    
2. 다음을 수행합니다.
    
   - 모든 비즈니스용 Skype 서버 사용자에 대해 통합 연락처 저장소를 전역으로 사용하도록 설정하려면 Windows PowerShell 명령줄 인터페이스에서 다음 cmdlet을 사용합니다.
    
   ```powershell
   Set-CsUserServicesPolicy -Identity global -UcsAllowed $True
   ```

   - 특정 사이트의 사용자에 대해 통합 연락처 저장소를 사용하도록 설정하려면 프롬프트에 다음을 입력합니다.
    
   ```powershell
   New-CsUserServicesPolicy -Identity site:<site name> -UcsAllowed $True
   ```

   예제:
    
   ```powershell
   New-CsUserServicesPolicy -Identity site:Redmond -UcsAllowed $True
   ```

   - 테넌트가 통합 연락처 저장소를 사용하도록 설정하려면 프롬프트에 다음을 입력합니다.
    
   ```powershell
   Set-CsUserServicesPolicy -Tenant <tenantId> -UcsAllowed $True
   ```

   예제:
    
   ```powershell
   Set-CsUserServicesPolicy -Tenant "38aad667-af54-4397-aaa7-e94c79ec2308" -UcsAllowed $True
   ```

   - 특정 사용자에 대해 통합 연락처 저장소를 사용하도록 설정하려면 프롬프트에 다음을 입력합니다.
    
   ```powershell
   New-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $True
   Grant-CsUserServicesPolicy -Identity "<user display name>" -PolicyName <"policy name">
   ```

    > [!NOTE]
    > 또한 사용자 표시 이름 대신 사용자의 별칭 또는 SIP URI를 사용할 수도 있습니다. 
  
    예:
    
   ```powershell
   New-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $True
   Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "UCS Enabled Users"
   ```

    > [!NOTE]
    > 위 예제에서 첫 번째 명령은 UcsAllowed 플래그가 True로 설정된 UCS Enabled Users라는 새로운 사용자별 정책을 만듭니다. 두 번째 명령은 정책을 Ken Myer라는 표시 이름의 사용자에게 지정합니다. 즉, Ken Myer가 통합 연락처 저장소를 사용할 수 있도록 설정됩니다.
  
## <a name="migrate-users-to-unified-contact-store"></a>사용자를 통합 연락처 저장소로 마이그레이션

사용자가 다음을 수행하면 사용자의 연락처가 Exchange 2013 서버로 자동으로 마이그레이션됩니다.
  
- UcsAllowed가 True로 설정된 사용자 서비스 정책을 할당한 경우
    
- 2013 Exchange 프로비전되고 사서함에 한 번 이상 로그인한 경우
    
- 리치 클라이언트를 사용하여 비즈니스용 Skype 로그인합니다.
    
사용자가 Lync 또는 이전 클라이언트로 로그인하거나 사용자가 Exchange 2013 서버에 연결되어 있지 않은 경우 사용자 서비스 정책이 무시되고 사용자의 연락처가 비즈니스용 Skype 서버.
  
다음 방법 중 하나를 사용하여 사용자 연락처가 마이그레이션되었는지 확인할 수 있습니다. 
  
- 클라이언트 컴퓨터에서 다음 레지스트리 키를 확인합니다.
    
    \\ HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync<SIP URL\>\UCS
    
    사용자의 연락처가 Exchange 2013에 저장되어 있는 경우 이 키에는 InUCSMode 값이 2165인 값이 들어 있습니다.
    
- **Test-CsUnifiedContactStore** cmdlet을 실행합니다. 관리 비즈니스용 Skype 서버 명령줄에 다음을 입력합니다.
    
  ```powershell
  Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"
  ```

    **Test-CsUnifiedContactStore** 가 정상적으로 실행되면 사용자 연락처가 통합 연락처 저장소로 마이그레이션된 것입니다.
    
## <a name="roll-back-migrated-users"></a>마이그레이션된 사용자 롤백

통합 연락처 저장소 기능을 롤백해야 하는 경우 사용자를 Exchange 2010 또는 Lync Server 2010으로 다시 이동하는 경우 연락처만 롤백합니다. 롤백하기 위해 사용자에 대한 정책을 사용하지 않도록 설정한 다음 **Invoke-CsUcsRollback** cmdlet을 실행합니다. 정책을 사용하지 않도록 설정하지 않은 경우 통합 연락처 저장소 마이그레이션이 다시 시작될 것이기 때문에 **Invoke-CsUcsRollback** 만 실행하면 영구 롤백을 보장하기에 충분하지 않습니다. 예를 들어 Exchange 2013이 Exchange 2010으로 롤백되어 사용자 사서함이 Exchange 2013으로 이동되어 사용자가 롤백되면 사용자 서비스 정책에서 사용자에 대해 통합 연락처 저장소를 계속 사용하도록 설정한 경우 통합 연락처 저장소 마이그레이션이 롤백 후 7일 후에 다시 시작됩니다.
  
**Move-CsUser** cmdlet은 다음과 같은 상황에서 Exchange 2013에서 비즈니스용 Skype 서버 연락처 저장소를 자동으로 롤백합니다.
  
- 사용자가 Microsoft Lync Server 2013 또는 비즈니스용 Skype 서버 Lync Server 2010으로 이동하는 경우 
    
- 사용자가 크로스 프레미스로 마이그레이션되는 경우(예: 사용자가 비즈니스용 Skype Online에서 비즈니스용 Skype 서버 또는 그 반대로 마이그레이션되는 경우).
    
백업 데이터베이스에서 통합 연락처 저장소 데이터를 가져올 경우 통합 연락처 저장소 모드가 내보내기와 가져오기 간에 변경되면 통합 연락처 저장소 데이터 및 사용자 데이터가 손상될 수 있습니다. 예를 들면 다음과 같습니다.
  
- 사용자의 연락처가 Exchange 2013으로 마이그레이션되기 전에 연락처 목록을 내보내고 마이그레이션 후에 동일한 데이터를 가져오면 통합 연락처 저장소 데이터 및 연락처 목록이 손상됩니다.
    
- 사용자를 Exchange 2013으로 마이그레이션한 후 사용자 데이터를 내보낼 경우 마이그레이션을 롤백한 다음 마이그레이션 후 데이터를 가져오는 경우 통합 연락처 저장소 데이터 및 연락처 목록이 손상됩니다.
    
> [!IMPORTANT]
> Exchange 사서함을 Exchange 2013에서 Exchange 2010으로 이동하기 전에 Exchange 관리자는 비즈니스용 Skype 서버 관리자가 비즈니스용 Skype 서버 사용자 연락처를 비즈니스용 Skype 서버 롤백해야 Exchange  2013 - 비즈니스용 Skype 서버. 통합 연락처 저장소 연락처를 비즈니스용 Skype 서버 이 섹션의 뒷부분에 있는 "Exchange 2013에서 통합 연락처 저장소 연락처를 비즈니스용 Skype 서버" 절차를 참조하십시오. 
  
 **사용자 연락처를 롤백하는 방법:** **Move-CsUser** cmdlet을 사용하여 비즈니스용 Skype 서버 2015와 Lync Server 2010 간에 사용자를 이동하는 경우 **Move-CsUser** cmdlet은 사용자를 비즈니스용 Skype 서버 2015에서 Lync Server 2010으로 이동할 때 통합 연락처 저장소를 자동으로 롤백하기 때문에 이러한 단계를 건너뛸 수 있습니다. **Move-CsUser** 는 통합 연락처 저장소 정책을 사용하지 않도록 설정하지 않습니다. 따라서 사용자가 2015년 2015년으로 다시 이동하면 통합 연락처 저장소로의 마이그레이션이 비즈니스용 Skype 서버 합니다.
  

