---
title: EDU Microsoft 부모 앱에 대한 관리자 설정
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: Microsoft Teams EDU 문서 문서의 전제요구 및 부모 앱에 대한 PowerShell 설정에 대해 설명할 수 있습니다.
ms.localizationpriority: Normal
ROBOTS: NOINDEX, NOFOLLOW
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9ca2c252964f610ee13924f25f5d4ca8e31b9d59
ms.sourcegitcommit: 4a9ea18808d17e2eb6e4e2e7e3894e33c14e8631
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2021
ms.locfileid: "59475915"
---
# <a name="deploying-the-parents-app-in-microsoft-teams"></a>부모 앱을 Microsoft Teams

[!INCLUDE [preview-feature](includes/preview-feature.md)]

부모 앱을 Microsoft Teams 하는 것은 관리자에게 간단한 프로세스로, 교사가 테넌트에 남아 있는 학생 및 해당 연락처에 통신할 수 있는 안전한 방법을 제공하며, 이는 교육자 조직 전체에서 확장됩니다.

## <a name="requirements"></a>요구 사항

- SDS(학교 데이터 동기화) - CSV 옵션을 사용하여 학생과 관련된 관련 연락처를 SDS에 업로드해야 합니다. 자세한 내용은 [SDS 및](/schooldatasync/set-up-your-sds-flow) 업데이트 관련 CSV [구성을](/graph/api/relatedcontact-update) 체크 아웃합니다.
- Teams 관리 센터에서 클래스 소유자는 **채팅을** 사용하도록 설정해야 합니다. 조직에서 관리하지 않는 Teams **페더리드** 채팅이 **있어야 합니다.**

사용자당 페더러드 채팅을 사용하도록 설정해야 하는 경우 단계는 아래와 같습니다.

## <a name="enabling-federated-chat-on-a-per-user-basis"></a>사용자당 페더링된 채팅 사용

1. 최신 PowerShell Microsoft Teams 미리 보기를 설치합니다.

    ```powershell
    Install-Module -Name PowerShellGet -Force -AllowClobber
    Install-Module -Name MicrosoftTeams -AllowPrerelease -Force -AllowClobber
    ```
    
2. 관리자 권한이 있는 자격 증명을 사용하여 명령 창에서 실행합니다.

    ```powershell
    $credential = Get-Credential
    Connect-MicrosoftTeams -Credential $credential
    ```
    
3. 전역 그룹/사용자 수준 구성 또는 테넌트 수준 구성에서 끄고 끄기

    ```powershell
    #Retrieves tenant level configuration
    Get-CsTenantFederationConfiguration
    #Turn OFF tenant level configuration
    Set-CsTenantFederationConfiguration -AllowTeamsConsumer $false
    #Turn ON tenant level configuration
    Set-CsTenantFederationConfiguration -AllowTeamsConsumer $true
    #Turn OFF Global GROUP/USER level configuration
    Set-CsExternalAccessPolicy -EnableTeamsConsumerAccess $false
    #Turn ON Global GROUP/USER level configuration
    Set-CsExternalAccessPolicy -EnableTeamsConsumerAccess $false
    ```
        
    > [!NOTE]
    > 이 PowerShell을 실행하는 경우 변경 내용을 완료하는 데 1시간 이상이 걸릴 수 있습니다.
    
## <a name="more-information"></a>추가 정보

- [CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy)
- [사용자에게 정책 할당](/powershell/module/skype/grant-csexternalaccesspolicy)
