---
title: 외부 사용자 액세스 정책 할당
ms.reviewer: ''
ms:assetid: 736fcaad-9f95-4896-b767-e199d86a00a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398551(v=OCS.15)
ms:contentKeyID: 48184483
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
description: 비즈니스용 Skype Server에 대해 사용자가 사용 하도록 설정한 경우에는 특정 사용자에 게 적절 한 정책을 적용 하 여 비즈니스용 Skype Server 제어판에서 SIP 페더레이션, 원격 사용자 액세스 및 IM (공용 인스턴트 메시징) 연결을 구성할 수 있습니다.
ms.openlocfilehash: b87eb377b23063dbcdfd9562a99533da230a8f30
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818329"
---
# <a name="assign-an-external-user-access-policy-to-a-skype-for-business-enabled-user"></a>비즈니스용 Skype 사용 가능 사용자에 게 외부 사용자 액세스 정책 지정

비즈니스용 Skype Server에 대해 사용자가 사용 하도록 설정한 경우에는 특정 사용자에 게 적절 한 정책을 적용 하 여 비즈니스용 Skype Server 제어판에서 SIP 페더레이션, 원격 사용자 액세스 및 IM (공용 인스턴트 메시징) 연결을 구성할 수 있습니다. 예를 들어 원격 사용자 액세스를 지 원하는 정책을 만든 경우 사용자가 원격 위치에서 비즈니스용 Skype Server에 연결 하 고 원격 위치의 내부 사용자와 공동 작업을 수행 하기 전에 사용자에 게이를 적용 해야 합니다.


> [!NOTE]  
> 외부 사용자 액세스를 지원 하려면 지원할 각 외부 사용자 액세스 유형에 대 한 지원을 사용 하도록 설정 하 고 해당 정책 및 사용을 제어 하는 기타 옵션을 구성 해야 합니다. 자세한 내용은 [비즈니스용 Skype 서버에 대 한 페더레이션 및 외부 액세스 관리](../managing-federation-and-external-access.md)를 참조 하세요.


이 항목의 절차를 사용 하 여 이전에 만든 외부 사용자 액세스 정책을 하나 이상의 사용자 계정에 적용할 수 있습니다.


## <a name="to-apply-an-external-user-policy-to-a-user-account"></a>외부 사용자 정책을 사용자 계정에 적용 하려면 다음을 사용 합니다.

1.  CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다. 

3.  왼쪽 탐색 모음에서 **사용자**를 클릭하고 구성할 사용자 계정을 검색합니다.

4.  검색 결과가 나열된 표에서 사용자 계정을 클릭하고 **편집**을 클릭한 후에 **자세한 정보 표시**를 클릭합니다.

5.  **비즈니스용 Skype 서버 사용자 편집** 의 **외부 액세스 정책**에서 적용 하려는 사용자 정책을 선택 합니다.
     
> [!NOTE]  
> 자동>설정은 기본 서버 또는 글로벌 정책 설정을 적용 합니다. ** \<**


## <a name="assigning-per-user-external-access-policies-by-using-windows-powershell-cmdlets"></a>Windows PowerShell Cmdlet을 사용 하 여 사용자 단위 외부 액세스 정책 지정

사용자 단위 외부 액세스 정책은 Windows PowerShell 및 CsExternalAccessPolicy cmdlet을 사용 하 여 할당할 수 있습니다. 이 cmdlet은 비즈니스용 Skype 서버 관리 셸에서 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다. 

## <a name="to-assign-a-per-user-external-access-policy-to-a-single-user"></a>사용자별 외부 액세스 정책을 단일 사용자에 게 할당 하려면

  - 이 명령은 사용자 단위 외부 액세스 정책 RedmondExternalAccessPolicy을 사용자: 진구 Myer에 할당 합니다.
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName "RedmondExternalAccessPolicy"


## <a name="to-assign-a-per-user-external-access-policy-to-multiple-users"></a>사용자별 외부 액세스 정책을 여러 사용자에 게 할당 하려면

  - 이 명령은 Active Directory의 미국 OU에 계정이 있는 모든 사용자에 게 사용자별 외부 액세스 정책 USAExternalAccessPolicy를 할당 합니다. 이 명령에 사용 되는 OU 매개 변수에 대 한 자세한 내용은 [Get CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsUser) cmdlet에 대 한 설명서를 참조 하세요.
    
        Get-CsUser -OU "ou=UnitedStates,dc=litwareinc,dc=com" | Grant-CsExternalAccessPolicy -PolicyName "USAExternalAccessPolicy"


## <a name="to-unassign-a-per-user-external-access-policy"></a>사용자별 외부 액세스 정책 할당 취소

  - 이 명령은 이전에: 진구 Myer에 할당 된 사용자 단위 외부 액세스 정책을 할당 취소 합니다. 사용자별 정책에 할당 되지 않은 경우: 진구 Myer는 전역 정책을 사용 하 여 자동으로 관리 되거나 있는 경우 해당 로컬 사이트 정책이 됩니다. 사이트 정책이 전역 정책 보다 우선 합니다.
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName $Null



자세한 내용은 [CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsExternalAccessPolicy) cmdlet에 대 한 도움말 항목을 참조 하세요.


