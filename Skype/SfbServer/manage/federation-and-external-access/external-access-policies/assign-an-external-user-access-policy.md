---
title: 외부 사용자 액세스 정책 할당
ms.reviewer: ''
ms:assetid: 736fcaad-9f95-4896-b767-e199d86a00a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398551(v=OCS.15)
ms:contentKeyID: 48184483
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 사용자가 비즈니스용 Skype 서버 사용하도록 설정된 경우 비즈니스용 Skype 서버 제어판에서 특정 사용자에게 적절한 정책을 적용하여 SIP 페더전, 원격 사용자 액세스 및 공용 IM(인스턴트 메시징) 연결을 구성할 수 있습니다.
ms.openlocfilehash: 4a5f6bfe13c27360c535957cefcfd4093b6a1bad
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58587022"
---
# <a name="assign-an-external-user-access-policy-to-a-skype-for-business-enabled-user"></a>외부 사용자 액세스 정책을 사용하도록 설정된 사용자에게 비즈니스용 Skype 할당

사용자가 비즈니스용 Skype 서버 사용하도록 설정된 경우 비즈니스용 Skype 서버 제어판에서 특정 사용자에게 적절한 정책을 적용하여 SIP 페더전, 원격 사용자 액세스 및 공용 IM(인스턴트 메시징) 연결을 구성할 수 있습니다. 예를 들어 원격 사용자 액세스를 지원하는 정책을 만든 경우 사용자가 원격 위치에서 비즈니스용 Skype 서버 연결하고 원격 위치에서 내부 사용자와 공동 작업을 하기 전에 해당 정책을 사용자에게 적용해야 합니다.


> [!NOTE]  
> 외부 사용자 액세스에 대해 지원하려면 지원할 각 외부 사용자 액세스 유형에 대한 지원을 사용하도록 설정하고 사용을 제어할 적절한 정책 및 기타 옵션을 구성해야 합니다. 자세한 내용은 [Managing federation and external access to 비즈니스용 Skype 서버.](../managing-federation-and-external-access.md)


이 항목의 절차를 사용하여 하나 이상의 사용자 계정에 이전에 만든 외부 사용자 액세스 정책을 적용합니다.


## <a name="to-apply-an-external-user-policy-to-a-user-account"></a>사용자 계정에 외부 사용자 정책을 적용하려면

1.  CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.

2.  브라우저 창을 열고 관리 URL을 입력하여 관리 비즈니스용 Skype 서버 열 수 있습니다. 

3.  왼쪽 탐색 모음에서 **사용자** 를 클릭하고 구성할 사용자 계정을 검색합니다.

4.  검색 결과가 나열된 표에서 사용자 계정을 클릭하고 **편집** 을 클릭한 후에 **세부 정보 표시** 를 클릭합니다.

5.  외부 **액세스 비즈니스용 Skype 서버 사용자** 편집에서 적용할 사용자 정책을 선택합니다.
     
> [!NOTE]  
> 이 **\<Automatic>** 설정은 기본 서버 또는 글로벌 정책 설정을 적용합니다.


## <a name="assigning-per-user-external-access-policies-by-using-windows-powershell-cmdlets"></a>cmdlet을 Per-User 외부 액세스 정책 Windows PowerShell 할당

사용자당 외부 액세스 정책은 Windows PowerShell cmdlet을 사용하여 Grant-CsExternalAccessPolicy 있습니다. 이 cmdlet은 관리 셸 또는 비즈니스용 Skype 서버 원격 세션에서 실행할 수 Windows PowerShell. 

## <a name="to-assign-a-per-user-external-access-policy-to-a-single-user"></a>단일 사용자에게 사용자당 외부 액세스 정책을 할당하는 경우

  - 이 명령은 사용자별 외부 액세스 정책 RedmondExternalAccessPolicy를 Ken Myer라는 사용자에게 지정합니다.<br/><br/>Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName "RedmondExternalAccessPolicy"


## <a name="to-assign-a-per-user-external-access-policy-to-multiple-users"></a>여러 사용자에게 사용자당 외부 액세스 정책을 할당하는 경우

  - 이 명령은 사용자별 외부 액세스 정책 USAExternalAccessPolicy를 Active Directory의 UnitedStates OU에 계정이 있는 모든 사용자에게 지정합니다. 이 명령에 사용되는 OU 매개 변수에 대한 자세한 내용은 [Get-CsUser](/powershell/module/skype/Get-CsUser) cmdlet에 대한 설명서를 참조하십시오.<br/><br/>Get-CsUser -OU "ou=United States,dc=litwareinc,dc=com" | Grant-CsExternalAccessPolicy -PolicyName "USAExternalAccessPolicy"


## <a name="to-unassign-a-per-user-external-access-policy"></a>사용자당 외부 액세스 정책의 위임

  - 이 명령은 이전에 Ken Myer에게 지정되었던 사용자별 외부 액세스 정책의 지정을 해제합니다. 사용자별 정책을 지정 해제한 후 Ken Myer는 자동으로 글로벌 정책 또는 로컬 사이트 정책(있는 경우)을 사용해서 관리됩니다. 사이트 정책은 글로벌 정책보다 우선 적용됩니다.<br/><br/>Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName $Null


자세한 내용은 [Grant-CsExternalAccessPolicy](/powershell/module/skype/Grant-CsExternalAccessPolicy) cmdlet에 대한 도움말 항목을 참조하십시오.
