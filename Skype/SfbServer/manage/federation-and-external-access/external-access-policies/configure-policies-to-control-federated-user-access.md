---
title: 페더레이션 사용자 액세스를 컨트롤하는 정책 구성
ms.reviewer: ''
ms:assetid: 5485e208-81e4-4e59-9aeb-1232c11dd8a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398359(v=OCS.15)
ms:contentKeyID: 48184180
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: '페더레이션 파트너와의 통신을 지원할 정책을 구성할 경우 정책이 페더레이션 도메인의 사용자에 적용됩니다. '
ms.openlocfilehash: 2b7976492fe4f789c2f3130fb51deaaef44af701
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817308"
---
# <a name="configure-policies-to-control-federated-user-access-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 페더전된 사용자 액세스를 제어하는 정책 구성

페더레이션 파트너와의 통신을 지원할 정책을 구성할 경우 정책이 페더레이션 도메인의 사용자에 적용됩니다. 하나 이상의 외부 사용자 액세스 정책을 구성하여 페더타 도메인의 사용자가 비즈니스용 Skype 서버 사용자와 공동 작업을 할 수 있는지 여부를 제어할 수 있습니다. 페더레이션 사용자 액세스를 제어하려면 전역, 사이트 및 사용자 수준에서 정책을 구성할 수 있습니다. 한 정책 수준에서 적용되는 비즈니스용 Skype 서버 정책 설정은 다른 정책 수준에서 적용되는 설정을 다시 적용할 수 있습니다. 비즈니스용 Skype 서버 정책 우선 순위는 다음과 같습니다. 사용자 정책(가장 큰 영향)이 사이트 정책을 재정의한 다음 사이트 정책이 글로벌 정책 (가장 큰 영향)을 재정의합니다. 즉, 정책 설정이 정책이 영향을 주는 개체에 가까울수록 개체에 미치는 영향이 커집니다.


> [!NOTE]  
> 조직에 대해 페더레이션을 사용하도록 설정하지 않았더라도 페더레이션 사용자 액세스를 제어하는 정책을 구성할 수 있습니다. 그러나 구성하는 정책은 조직에 대해 페더레이션을 사용하도록 설정하는 경우에만 적용됩니다. 페더링을 사용하도록 설정하는 데 대한 자세한 내용은 원격 사용자 액세스 사용 또는 사용 [안 을 참조합니다.](../access-edge/enable-or-disable-remote-user-access.md)  또한 페더전된 사용자 액세스를 제어하기 위한 사용자 정책을 지정하는 경우 해당 정책은 비즈니스용 Skype 서버에 대해 사용하도록 설정되어 있으며 정책을 사용하도록 구성된 사용자에게만 적용됩니다.


## <a name="to-configure-a-policy-to-support-access-by-users-of-federated-domains"></a>페더레이션 도메인 사용자의 액세스를 지원하기 위한 정책을 구성하려면

1.  RTCUniversalServerAdmins 그룹의 구성원(또는 이와 동등한 사용자 권한)인 사용자 계정에서 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포의 컴퓨터에 로그온합니다.

2.  브라우저 창을 열고 관리 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다.

3.  왼쪽 탐색 모음에서 **외부 사용자 액세스** 를 클릭하고 **외부 액세스 정책** 을 클릭합니다.

4.  **외부 액세스 정책** 페이지에서 다음 중 하나를 수행합니다.
    
      - 페더레이션 사용자 액세스를 지원하기 위한 글로벌 정책을 구성하려면 글로벌 정책을 클릭하고 **편집** 을 클릭한 후에 **세부 정보 표시** 를 클릭합니다.
    
      - 새 사이트 정책을 만들려면 **새로 만들기** 를 클릭하고 **사이트 정책** 을 클릭합니다. **사이트 선택** 의 목록에서 적절한 사이트를 클릭하고 **확인** 을 클릭합니다.
    
      - 새 사용자 정책을 만들려면 **새로 만들기** 를 클릭하고 **사용자 정책** 을 클릭합니다. **새 외부 액세스 정책** 의 **이름** 필드에서 사용자 정책이 다루는 내용을 나타내는 고유한 이름을 만듭니다(예: 페더레이션 도메인 사용자에 대한 통신을 사용하도록 설정하는 사용자 정책의 경우 **EnableFederatedUsers**).
    
      - 기존 정책을 변경하려면 테이블에 나열되어 있는 적절한 정책을 클릭하고 **편집**, **세부 정보 표시** 를 차례로 클릭합니다.

5.  (선택 사항) 설명을 추가하거나 편집하려면 정책에 대한 정보를 **설명** 에 지정합니다.

6.  다음 중 하나를 수행합니다.
    
      - 정책에 대한 페더레이션 사용자 액세스를 사용하도록 설정하려면 **페더레이션 사용자와의 통신 사용** 확인란을 선택합니다.
    
      - 정책에 대한 페더레이션 사용자 액세스를 사용하지 않도록 설정하려면 **페더레이션 사용자와의 통신 사용** 확인란 선택을 취소합니다.

7.  **커밋** 을 클릭합니다.

페더레이션 사용자 액세스를 허용하려면 조직에서 페더레이션을 지원하도록 설정해야 합니다. 자세한 내용은 페더ation 및 공용 IM 연결 사용 또는 사용 안 [하도록 설정 을 참조 합니다.](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md)

사용자 정책의 경우에는 페더레이션 사용자와 공동 작업하도록 할 사용자에게도 정책을 적용해야 합니다. 자세한 내용은 외부 사용자 액세스 [정책 할당을 참조합니다.](assign-an-external-user-access-policy.md)

## <a name="to-configure-an-existing-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a>페더화 도메인의 Windows PowerShell 액세스를 지원하기 위해 기존 정책을 구성하려면

1.  RTCUniversalServerAdmins 그룹의 구성원(또는 이와 동등한 사용자 권한)인 사용자 계정에서 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포의 컴퓨터에 로그온합니다.

2.  비즈니스용 Skype 서버 관리 셸 시작: **시작,** **모든** 프로그램, 비즈니스용 **Skype 서버,** 비즈니스용 Skype 서버 관리 셸을 **클릭합니다.**

3.  비즈니스용 Skype 서버 관리 셸에 다음을 입력합니다.
    
    ```PowerShell
    Set-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAcess <$true, $false> -EnablePublicCloudAudioVideoAcess <$true, $false> -EnableOutsideAcess <$true, $false>
    ```
       

    > [!TIP]  
    > "EnablePublicCloudAudioVideoAccess" 매개 변수에 비즈니스용 Skype 서버 제어판에서 해당 선택이 없습니다.


## <a name="to-create-a-new-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a>페더화 도메인의 Windows PowerShell 액세스를 지원하기 위해 새 정책을 만들 수 있습니다.

1.  RTCUniversalServerAdmins 그룹의 구성원(또는 이와 동등한 사용자 권한)인 사용자 계정에서 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포의 컴퓨터에 로그온합니다.

2.  비즈니스용 Skype 서버 관리 셸을 시작합니다. **시작,** 모든 **프로그램,** **Microsoft 비즈니스용 Skype 서버,** 비즈니스용 Skype 서버 관리 셸을 **클릭합니다.**

3.  비즈니스용 Skype 서버 관리 셸에 다음을 입력합니다.
    
    ```PowerShell
    New-CsExtenalAccessPolicy -Identity <name of site or user policy - you cannot create a new global policy using New-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAccess <$true, $false> -EnablePublicCloudAudioVideoAccess <$true, $false> -EnableOutsideAccess <$true, $false>
    ```
    
    새 사이트 정책을 만드는 예:
    
    ```PowerShell
    New-CsExternalAccessPolicy -Identity site:Redmond -EnableFederationAccess $true -EnableXmppAccess $true -EnableOutsideAccess $true -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true
    ```


## <a name="to-delete-or-reset-a-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a>페더타 도메인의 Windows PowerShell 액세스를 지원하기 위해 정책을 삭제하거나 다시 설정하려면

1.  RTCUniversalServerAdmins 그룹의 구성원(또는 이와 동등한 사용자 권한)인 사용자 계정에서 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포의 컴퓨터에 로그온합니다.

2.  비즈니스용 Skype 서버 관리 셸에 다음을 입력합니다.
    
    `Remove-CsExternalAccessPolicy -Identity <name of global, site or user policy>`
    
    글로벌 정책을 다시 설정하는 예(글로벌 정책은 해당 설정만 제거할 수 있으며, 정책 자체를 삭제할 수 없습니다.):
    
    `Remove-CsExternalAccessPolicy -Identity global`
    
    사이트 정책을 제거하려면 다음을 입력합니다.
    
    `Remove-CsExternalAccessPolicy -Identity site:Redmond` 
    
    사이트 정책 Redmond를 삭제합니다. 이름이 UserEAPPolicy인 사용자 정책을 삭제하려면 다음을 입력합니다.
    
    `Remove-CsExternalAccessPolicy -Identity UserEAPPolicy`


## <a name="see-also"></a>참고 항목


[페더레이션 및 공개 IM 연결을 사용하도록 설정 또는 해제](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md) 

[외부 사용자 액세스 정책 할당](assign-an-external-user-access-policy.md)

[조직의 SIP 페더레이션 도메인 관리](../sip-domains/manage-sip-federated-domains-for-your-organization.md)
 
[조직의 SIP 페더레이션 제공자 관리](../sip-providers/manage-sip-federated-providers-for-your-organization.md)

[Set-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsExternalAccessPolicy)  
[New-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsExternalAccessPolicy)  
[Get-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsExternalAccessPolicy)  
[Remove-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy)  
[Grant-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy)  
  

