---
title: 페더레이션 사용자 액세스를 제어할 정책 구성
ms.reviewer: ''
ms:assetid: 5485e208-81e4-4e59-9aeb-1232c11dd8a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398359(v=OCS.15)
ms:contentKeyID: 48184180
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: '페더레이션 파트너와의 통신을 지원 하도록 정책을 구성 하는 경우 페더레이션 도메인의 사용자에 게 정책이 적용 됩니다. '
ms.openlocfilehash: 2e9385436427fd73f90e308d7747cf304bf37501
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818319"
---
# <a name="configure-policies-to-control-federated-user-access-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 페더레이션된 사용자 액세스를 제어 하도록 정책 구성

페더레이션 파트너와의 통신을 지원 하도록 정책을 구성 하는 경우 페더레이션 도메인의 사용자에 게 정책이 적용 됩니다. 페더레이션 도메인 사용자가 비즈니스용 Skype 서버 사용자와 공동 작업할 수 있는지 여부를 제어 하는 하나 이상의 외부 사용자 액세스 정책을 구성할 수 있습니다. 페더레이션 사용자 액세스를 제어 하기 위해 전역, 사이트 및 사용자 수준에서 정책을 구성할 수 있습니다. 한 정책 수준에서 적용 되는 비즈니스용 Skype 서버 정책 설정은 다른 정책 수준에서 적용 된 설정을 무시할 수 있습니다. 비즈니스용 Skype 서버 정책 우선 순위: 사용자 정책 (대부분의 영향을 주지 않음)이 사이트 정책을 무시 하 고 사이트 정책이 전역 정책에 우선 합니다 (최소 영향). 즉 정책 설정이 정책에 영향을 미치는 개체에 대 한 자세한 내용은 개체에 더 많은 영향을 줍니다.


> [!NOTE]  
> 조직을 위한 페더레이션을 설정 하지 않은 경우에도 정책을 구성 하 여 페더레이션된 사용자 액세스를 제어할 수 있습니다. 그러나 구성 하는 정책은 조직에 페더레이션이 설정 되어 있는 경우에만 적용 됩니다. 페더레이션 사용에 대 한 자세한 내용은 [원격 사용자 액세스 사용 또는 사용 안 함을](../access-edge/enable-or-disable-remote-user-access.md)참조 하세요.  또한 페더레이션 사용자 액세스를 제어 하는 사용자 정책을 지정 하는 경우 비즈니스용 Skype Server에 대해 사용 하도록 설정 하 고 정책을 사용 하도록 구성 된 사용자 에게만 정책이 적용 됩니다.


## <a name="to-configure-a-policy-to-support-access-by-users-of-federated-domains"></a>페더레이션 도메인의 사용자가 액세스를 지원 하도록 정책을 구성 하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다.

3.  왼쪽 탐색 모음에서 **외부 사용자 액세스**를 클릭 한 다음 **외부 액세스 정책을**클릭 합니다.

4.  **외부 액세스 정책** 페이지에서 다음 중 하나를 수행 합니다.
    
      - 페더레이션 사용자 액세스를 지원 하도록 전역 정책을 구성 하려면 전역 정책을 클릭 하 고 **편집**을 클릭 한 다음 **세부 정보 표시**를 클릭 합니다.
    
      - 새 사이트 정책을 만들려면 **새로 만들기**를 클릭 한 다음 **사이트 정책을**클릭 합니다. **사이트 선택**의 목록에서 해당 사이트를 클릭 한 다음 **확인**을 클릭 합니다.
    
      - 새 사용자 정책을 만들려면 **새로 만들기**를 클릭 한 다음 **사용자 정책을**클릭 합니다. **새 외부 액세스 정책**에서 사용자 정책에 대 한 정보 (예: 페더레이션 도메인 사용자에 게 통신을 사용 하도록 설정 하는 사용자 정책에 대 한 **EnableFederatedUsers** )를 나타내는 고유한 이름을 **이름** 필드에 만듭니다.
    
      - 기존 정책을 변경 하려면 표에 나열 된 적절 한 정책을 클릭 하 고 **편집**을 클릭 한 다음 **세부 정보 표시**를 클릭 합니다.

5.  ) 설명을 추가 하거나 편집 하려면 **설명**에서 정책에 대 한 정보를 지정 합니다.

6.  다음 중 하나를 수행 합니다.
    
      - 정책에 대해 페더레이션 사용자 액세스를 사용 하도록 설정 하려면 **페더레이션 사용자와 통신 사용** 확인란을 선택 합니다.
    
      - 정책에 대해 페더레이션 사용자 액세스를 사용 하지 않도록 설정 하려면 **페더레이션 사용자와 통신 사용** 확인란의 선택을 취소 합니다.

7.  **커밋**을 클릭합니다.

페더레이션 사용자 액세스를 사용 하도록 설정 하려면 조직의 페더레이션에 대 한 지원도 사용 하도록 설정 해야 합니다. 자세한 내용은 [페더레이션 및 공용 IM 연결 사용 또는 사용 안 함을](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md)참조 하세요.

사용자 정책 인 경우 페더레이션 사용자와 공동 작업을 할 수 있도록 하는 사용자에 게도 정책을 적용 해야 합니다. 자세한 내용은 [외부 사용자 액세스 정책 할당](assign-an-external-user-access-policy.md)을 참조 하세요.

## <a name="to-configure-an-existing-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a>페더레이션 도메인 사용자의 액세스를 지원 하기 위해 Windows PowerShell을 사용 하 여 기존 정책을 구성 하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.

2.  명함 서버 관리 셸을 시작 하려면 **시작**을 클릭 하 고 **모든 프로그램**을 클릭 한 다음 비즈니스용 **skype server**를 클릭 하 고 비즈니스용 **skype server management shell**을 클릭 합니다.

3.  비즈니스용 Skype 서버 관리 셸에서 다음을 입력 합니다.
    
    ```PowerShell
    Set-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAcess <$true, $false> -EnablePublicCloudAudioVideoAcess <$true, $false> -EnableOutsideAcess <$true, $false>
    ```
       

    > [!TIP]  
    > "Enablepubliccloud오디오 Videoaccess" 매개 변수는 비즈니스용 Skype 서버 제어판에서 해당 항목을 선택 하지 않습니다.


## <a name="to-create-a-new-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a>페더레이션 도메인 사용자의 액세스를 지원 하기 위해 Windows PowerShell을 사용 하 여 새 정책을 만들려면

1.  RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.

2.  비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **Microsoft 비즈니스용 skype server**를 차례로 클릭 한 다음 비즈니스용 **skype server management shell**을 클릭 합니다.

3.  비즈니스용 Skype 서버 관리 셸에서 다음을 입력 합니다.
    
    ```PowerShell
    New-CsExtenalAccessPolicy -Identity <name of site or user policy - you cannot create a new global policy using New-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAccess <$true, $false> -EnablePublicCloudAudioVideoAccess <$true, $false> -EnableOutsideAccess <$true, $false>
    ```
    
    새 사이트 정책을 만드는 예:
    
    ```PowerShell
    New-CsExternalAccessPolicy -Identity site:Redmond -EnableFederationAccess $true -EnableXmppAccess $true -EnableOutsideAccess $true -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true
    ```


## <a name="to-delete-or-reset-a-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a>페더레이션 도메인 사용자의 액세스를 지원 하기 위해 Windows PowerShell을 사용 하 여 정책을 삭제 하거나 다시 설정 하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.

2.  비즈니스용 Skype 서버 관리 셸에서 다음을 입력 합니다.
    
    `Remove-CsExternalAccessPolicy -Identity <name of global, site or user policy>`
    
    전역 정책 다시 설정의 예 (전역 정책에는 해당 설정만 제거할 수 있음)가 있습니다. 정책을 삭제할 수 없음):
    
    `Remove-CsExternalAccessPolicy -Identity global`
    
    사이트 정책을 제거 하려면 다음을 입력 합니다.
    
    `Remove-CsExternalAccessPolicy -Identity site:Redmond` 
    
    사이트 정책 Redmond를 삭제 합니다. UserEAPPolicy 라는 사용자 정책을 삭제 하려면 다음을 입력 합니다.
    
    `Remove-CsExternalAccessPolicy -Identity UserEAPPolicy`


## <a name="see-also"></a>참고 항목


[페더레이션 및 공개 IM 연결을 사용하도록 설정 또는 해제](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md) 

[외부 사용자 액세스 정책 할당](assign-an-external-user-access-policy.md)

[조직의 SIP 페더레이션 도메인 관리](../sip-domains/manage-sip-federated-domains-for-your-organization.md)
 
[조직의 SIP 페더레이션 제공자 관리](../sip-providers/manage-sip-federated-providers-for-your-organization.md)

[Set-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsExternalAccessPolicy)  
[New-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsExternalAccessPolicy)  
[Get-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsExternalAccessPolicy)  
[Remove-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy)  
[부여-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsExternalAccessPolicy)  
  

