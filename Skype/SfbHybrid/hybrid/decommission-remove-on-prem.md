---
title: 비즈니스용 Skype 서버 해제
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: 비즈니스용 Skype 서버를 해제하기 위한 지침입니다.
ms.openlocfilehash: 668e3d5ebf5dfa03fcfb883adcc3e08fc5924bae
ms.sourcegitcommit: f223b5f3735f165d46bb611a52fcdfb0f4b88f66
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/06/2021
ms.locfileid: "51593906"
---
# <a name="remove-your-on-premises-skype-for-business-deployment"></a>비즈니스용 Skype 배포를 제거합니다.

이 문서에서는 비즈니스용 Skype 배포를 제거하는 방법을 설명합니다. 이 단계는 다음 단계 중 3단계로, 프레미스 환경을 해제합니다.

- 1단계. 필요한 모든 사용자 및 [응용 프로그램 끝점을](decommission-move-on-prem-users.md)프레미스에서 온라인으로 이동 

- 2단계. [하이브리드 구성을 사용하지 않도록 설정합니다.](cloud-consolidation-disabling-hybrid.md)

- **3단계. 비즈니스용 Skype 배포를 제거합니다.** (이 문서)


> [!IMPORTANT] 
> 이 문서의 단계는 여기에 설명된 사용자 특성 관리에 메서드 2를 사용하는 경우만 [적용됩니다.](cloud-consolidation-disabling-hybrid.md#method-2---clear-skype-for-business-attributes-for-all-on-premises-users-in-active-directory) 방법 1을 사용하는 경우 이 문서에 설명된 단계를 사용하여 비즈니스용 Skype 서버를 제거하지 않습니다. 대신 서버를 다시 이미지화할 수 있습니다.

이 문서의 단계를 완료하려면 Schema Admins 그룹과 Enterprise Admin 그룹에 대한 권한이 필요합니다. Active Directory 도메인 서비스에 대한 비즈니스용 Skype 서버 schema 및 포리스트 수준 변경을 취소하려면 이러한 권한이 필요합니다. 또한 RTCUniversalServerAdmins 그룹의 구성원이 되야 합니다.


## <a name="prepare-to-remove-the-skype-for-business-deployment"></a>비즈니스용 Skype 배포 제거 준비

필요한 모든 사용자 계정을 클라우드로 이동한 후에도 정리해야 하는 연락처 및 응용 프로그램과 같은 몇 가지 남아 있는 사내 개체가 남아 있을 수 있습니다.

아래 단계를 사용하여 이러한 개체를 정리하고 로컬 관리자 그룹과 RTCUniversalServerAdmins 그룹의 구성원이 있는지 확인하십시오. ExUmContacts 및 PersistantChatEndPoints는 비즈니스용 Skype 서버 2019에서는 사용할 수 없습니다. 비즈니스용 Skype 서버 2019가 있는 경우 아래 단계에서 해당 cmdlet을 생략해야 합니다.

1. 비즈니스용 Skype 서버의 사내 배포와 연결된 연락처 또는 응용 프로그램이 있는지 확인하기 위해 다음 비즈니스용 Skype 서버 PowerShell cmdlet을 실행합니다.

   ```PowerShell
   Get-CsMeetingRoom
   Get-CsCommonAreaPhone
   Get-CsAnalogDevice
   Get-CsExUmContact
   Get-CsDialInConferencingAccessNumber
   Get-CsRgsWorkflow
   Get-CsTrustedApplicationEndpoint
   Get-CsTrustedApplication
   Get-CsPersistentChatEndpoint
   Get-CsAudioTestServiceApplication
   Get-CsCallParkOrbit
   ```
2. 1단계의 cmdlet에서 출력 목록을 검토합니다. 그런 다음 개체를 제거할 수 있는 경우 다음 비즈니스용 Skype 서버 PowerShell cmdlet을 실행합니다.

   ```PowerShell
   Get-CsMeetingRoom | Disable-CsMeetingRoom
   Get-CsCommonAreaPhone | Remove-CsCommonAreaPhone 
   Get-CsAnalogDevice | Remove-CsAnalogDevice
   Get-CsExUmContact | Remove-CsExUmContact
   Get-CsDialInConferencingAccessNumber | Remove-CsDialInConferencingAccessNumber
   Get-CsRgsWorkflow | Remove-CsRgsWorkflow
   Get-CsTrustedApplicationEndpoint | Remove-CsTrustedApplicationEndpoint
   Get-CsTrustedApplication | Remove-CsTrustedApplication -Force
   Get-CsPersistentChatEndpoint |  Remove-CsPersistentChatEndpoint
   Get-CsCallParkOrbit | Remove-CsCallParkOrbit -Force
   Get-CsVoiceRoute | Remove-CsVoiceRoute -Force
   ```
## <a name="remove-your-on-premises-skype-for-business-deployment"></a>비즈니스용 Skype 배포를 제거합니다.

모든 예비 단계를 완료한 후 다음 단계에 따라 비즈니스용 Skype 배포를 제거할 수 있습니다.

1. 다음과 같이 단일 프런트 엔드를 제외하고 비즈니스용 Skype 서버 배포를 논리적으로 제거합니다.

   a. 단일 프런트 엔드 풀을 있도록 비즈니스용 Skype 서버 토폴로지 업데이트:

     - 토폴로지 작성기에서 새 복사본을 다운로드하고 프런트 엔드 풀로 이동합니다.
     - 풀을 마우스 오른쪽 단추로 클릭한 다음 **속성 편집** 을 클릭합니다.
     - **연결에서** 에지  풀 연결(미디어 구성 요소)을 선택하지 않은 다음 확인을 **클릭합니다.**
     - 프런트 엔드 풀이 여러 개 있는 경우 나머지 모든 풀에 대한 연결 제거
     - 배포 **제거 > 작업을 선택합니다.**
     - **토폴로지 > 작업 을 선택합니다.**

    b. 토폴로지 게시 후 마법사에 설명된 추가 단계를 완료합니다.

2. 다음 비즈니스용 Skype 서버 PowerShell cmdlet을 실행하여 비즈니스용 Skype 서버 회의를 제거합니다.

   ```PowerShell
   Get-CsConferenceDirectory | Remove-CsConferenceDirectory -Force
   ```

3. 다음 비즈니스용 Skype 서버 PowerShell cmdlet을 실행하여 비즈니스용 Skype 서버 배포 제거를 마무리합니다.

   ```PowerShell
   Publish-CsTopology -FinalizeUninstall
   ```
   > [!NOTE]
   > 이 단계에서 오류가 반환된 경우 Microsoft 지원 티켓을 열어 나머지 부실 개체를 제거하는 데 도움이 됩니다.

4. 다음 비즈니스용 Skype 서버 PowerShell cmdlet을 실행하여 중앙 관리 저장소 서비스 제어 지점을 제거합니다.

   ```PowerShell
   Remove-CsConfigurationStoreLocation
   ``` 

5. 다음 비즈니스용 Skype 서버 PowerShell cmdlet을 실행하여 비즈니스용 Skype 서버 Active Directory 도메인 포리스트 수준 변경 실행을 취소합니다.

   ```PowerShell
   Disable-CsAdDomain
   ```
6. 다음 비즈니스용 Skype 서버 PowerShell cmdlet을 실행하여 비즈니스용 Skype 서버 Active Directory 도메인의 변경 내용을 실행 취소합니다.

   ```PowerShell
   Disable-CsAdForest
   ```

## <a name="see-also"></a>참고 항목

- [비즈니스용 Skype 환경 해제](decommission-on-prem-overview.md)

- [클라우드로 사용자 및 끝점 이동](decommission-move-on-prem-users.md)

- [하이브리드 구성을 사용하지 않도록 설정](cloud-consolidation-disabling-hybrid.md)














