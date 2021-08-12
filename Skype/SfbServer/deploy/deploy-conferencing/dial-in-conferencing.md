---
title: 2016에서 전화 접속 회의 비즈니스용 Skype 서버
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
ms.assetid: 38d9f168-80b8-46f2-a1c0-becd84e58e73
description: '요약: 이 항목을 통해 사용자 계정에서 전화 접속 회의를 구성하는 비즈니스용 Skype 서버.'
ms.openlocfilehash: 5e6540b926d3b632fdff21f8fb645667068ca2e362260131dcd2b6379d5ef0b4
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54303132"
---
# <a name="configure-dial-in-conferencing-in-skype-for-business-server"></a>2016에서 전화 접속 회의 비즈니스용 Skype 서버
 
**요약:** 이 항목을 통해 전화 접속 회의를 구성하는 방법을 비즈니스용 Skype 서버.
  
회의 작업 부하 및 선택된 전화 접속 회의가 포함된 토폴로지가 만들어진 후 추가 단계를 수행하여 전화 접속 회의를 구성해야 합니다. 이 항목을 읽기 전에 비즈니스용 Skype 서버 전화 접속 회의 계획, 비즈니스용 Skype 서버 회의의 하드웨어 및 소프트웨어 요구 사항 및 전화 접속 회의에 대한 [](deploy-conferencing.md#deployment-flowchart-and-checklist-for-dial-in-conferencing)배포 [흐름도](../../plan-your-deployment/conferencing/hardware-and-software-requirements.md)및 검사 목록을 읽어야 [합니다.](../../plan-your-deployment/conferencing/dial-in-conferencing.md) 
  
전화 접속 회의를 구성하려면 다음 작업을 수행해야 합니다.
  
- [다이얼 플랜을 구성합니다.](dial-in-conferencing.md#BKMK_ConfigureDialPlans)
    
- [전화 접속 회의 지역 구성](dial-in-conferencing.md#BKMK_ConfigureDialInRegions)
    
- [전화 접속 액세스 번호를 구성합니다.](dial-in-conferencing.md#BKMK_ConfigureDialInAccessNumbers)
    
- [회의 정책 구성](dial-in-conferencing.md#BKMK_ConfigureConferencingPolicies)
    
- [사용자 계정에 줄 URI 할당](dial-in-conferencing.md#BKMK_AssignaLineURI)
    
또한 다음과 같은 선택적 작업을 수행할 수 있습니다. 이러한 선택적 작업에 대한 자세한 내용은 [Manage dial-in conferencing in 비즈니스용 Skype 서버.](../../manage/conferencing/dial-in-conferencing.md)
  
- 전화 접속 회의에 대한 PIN 정책 관리
    
- DTMF 명령에 대한 키 매핑 관리
    
- 회의 Director 만들기
    
- 회의 참가 및 나가기 공지 관리
    
- 전화 접속 회의 설정 테스트
    
- 전화 접속 사용자에게 환영 메일 보내기
    
## <a name="configure-dial-plans"></a>다이얼 플랜을 구성합니다.
<a name="BKMK_ConfigureDialPlans"> </a>

전화 접속 회의를 배포할 경우 전화 접속 액세스 전화 번호를 라우팅하기 위해 하나 이상의 다이얼 플랜을 만들거나 수정해야 합니다. 또한 각 다이얼 플랜에 하나 이상의 정규화 규칙(내선 번호를 E.164 형식의 전체 전화 번호로 변환하는 규칙)이 포함되어 있는지도 확인해야 합니다. 
  
전화 접속 회의의 사용자는 PIN(개인 식별 번호) 및 전화 번호를 입력하여 인증된 엔터프라이즈 사용자로 전화 회의에 참가합니다. 사용자들이 전화 내선 번호를 입력할 때 사용자를 인증할 수 있도록 내선 번호를 완전한 전화 번호로 변환하는 정규화 규칙이 필요합니다.
  
전화 접속 회의에 대한 다이얼 플랜을 설정하는 경우:
  
- 배포 여부에 Enterprise Voice 전역 다이얼 플랜을 수정하여 전화 접속 회의 지역을 추가하고 정규화 규칙이 전화 접속 액세스 번호를 정확하게 변환하도록 합니다. 자세한 내용은 [에서 다이얼](../../deploy/deploy-enterprise-voice/dial-plans.md)플랜 만들기 또는 수정을 비즈니스용 Skype 서버.
    
- 배포하지 않은 Enterprise Voice 전화 접속 회의 액세스 번호에 대한 다이얼 플랜을 만드시오. 이 경우 전화 접속 회의 지역을 포함해야 합니다. 자세한 내용은 [에서 다이얼](../../deploy/deploy-enterprise-voice/dial-plans.md)플랜 만들기 또는 수정을 비즈니스용 Skype 서버.
    
- 배포한 Enterprise Voice 지역을 포함하도록 Enterprise Voice 다이얼 플랜을 수정하고 전화 접속 액세스 번호에 적절한 정규화 규칙을 사용하세요. 전화 접속 액세스 번호에만 사용되는 전용 다이얼 플랜을 만들 수도 있습니다. 자세한 내용은 [에서 다이얼](../../deploy/deploy-enterprise-voice/dial-plans.md)플랜 만들기 또는 수정을 비즈니스용 Skype 서버.
    
정규화 규칙을 만드는 자세한 내용은 에서 정규화 규칙 만들기 [또는 수정을 비즈니스용 Skype.](../../deploy/deploy-enterprise-voice/normalization-rules.md)
  
## <a name="configure-dial-in-conferencing-regions"></a>전화 접속 회의 지역 구성
<a name="BKMK_ConfigureDialInRegions"> </a>

다이얼 플랜을 설정할 때는 해당 다이얼 플랜에 적용되는 전화 접속 회의 지역을 지정합니다. 전화 접속 회의 지역은 전화 접속 회의 액세스 번호를 적절한 다이얼 플랜과 연결합니다. 그런 다음 전화 접속 액세스 번호를 만들 때 해당 액세스 번호를 적절한 다이얼 플랜과 연결하는 지역을 선택할 수 있습니다. 
  
모든 다이얼 플랜의 지역을 지정하는 것이 중요하기 때문에 모든 다이얼 플랜에 회의 지역이 있는지 확인하는 것이 좋습니다. 
  
지역이 모든 전화 접속 회의 다이얼 플랜에 대해 설정되어 있는지 확인하기 위해 **Get-CsDialPlan** cmdlet을 사용 합니다. 해당 지역이 다이얼 플랜에서 누락된 경우 **Set-CsDialPlan** cmdlet을 사용하여 이 지역을 설정할 수 있습니다. 또한 제어판을 사용하여 비즈니스용 Skype 서버 다이얼 플랜의 지역을 업데이트할 수도 있습니다. 제어판을 사용하는 비즈니스용 Skype 서버 자세한 내용은 에서 다이얼 플랜 만들기 또는 [수정을 비즈니스용 Skype 서버.](../../deploy/deploy-enterprise-voice/dial-plans.md)
  
### <a name="to-verify-whether-dial-plans-have-the-region-property-set"></a>다이얼 플랜에 지역 속성 집합이 있는지 확인하려면

1. RTCUniversalServerAdmins 그룹의 구성원이나 **Cs-VoiceAdministrator**, **Cs-ServerAdministrator** 또는 **CsAdministrator** 역할의 구성원으로 컴퓨터에 로그온합니다.
    
2. 비즈니스용 Skype 서버 시작: **시작,** 모든 프로그램, 비즈니스용 Skype **2015를** 클릭한 다음 관리 **비즈니스용 Skype 서버 를 클릭합니다.**
    
3. 명령 프롬프트에서 다음을 실행합니다.
    
   ```powershell
   Get-CsDialPlan [-Identity <Identifier of the dial plans to be retrieved>]
   ```

   예:
    
   ```powershell
   Get-CsDialPlan
   ```

   이 예에서는 조직에 대해 구성된 모든 다이얼 플랜이 반환됩니다.
    
4. 반환된 다이얼 플랜을 검토하여 전화 접속 회의 지역이 누락된 항목이 있는지 확인합니다. 
    
자세한 내용은 [Get-CsDialPlan을 참조하십시오.](/powershell/module/skype/get-csdialplan?view=skype-ps)
  
### <a name="to-set-the-region-property-for-a-dial-plan"></a>다이얼 플랜에 대해 지역 속성을 설정하려면

1. RTCUniversalServerAdmins 그룹의 구성원이나 **Cs-VoiceAdministrator**, **Cs-ServerAdministrator** 또는 **CsAdministrator** 역할의 구성원으로 컴퓨터에 로그온합니다.
    
2. 비즈니스용 Skype 서버 시작: **시작,** 모든 프로그램, 비즈니스용 Skype **2015를** 클릭한 다음 관리 **비즈니스용 Skype 서버 를 클릭합니다.**
    
3. 전화 접속 회의 지역이 누락된 다이얼 플랜에 대해 다음을 실행합니다.
    
   ```powershell
   Set-CsDialPlan [-Identity <Identity of the dial plan to be modified>] -DialinConferencingRegion "<new region>"
   ```

   예:
    
   ```powershell
   Set-CsDialPlan -Identity Redmond -DialinConferencingRegion "US West Coast"
   ```

   이 예에서는 ID가 Redmond인 다이얼 플랜이 수정되어 DialinConferencingRegion 속성이 "US West Coast"로 설정됩니다. 
    
자세한 내용은 [Set-CsDialPlan을 참조하십시오.](/powershell/module/skype/set-csdialplan?view=skype-ps)
  
## <a name="configure-dial-in-access-numbers"></a>전화 접속 액세스 번호를 구성합니다.
<a name="BKMK_ConfigureDialInAccessNumbers"> </a>

전화 접속 회의를 배포하려면 회의의 오디오 부분에 참가하기 위해 사용자가 PSTN(공중 전화망)을 통해 전화를 걸 수 있는 전화 번호를 설정해야 합니다. 이러한 전화 접속 액세스 번호는 모임 초대장 및 전화 접속 회의 설정 웹 페이지에 표시됩니다.
  
전화 접속 액세스 번호를 만들려면 먼저 전화 접속 회의 지역을 계획한 다음 해당 지역이 포함된 다이얼 플랜을 구성해야 합니다. 지역에 대한 자세한 내용은 [Plan for dial-in conferencing in 비즈니스용 Skype 서버.](../../plan-your-deployment/conferencing/dial-in-conferencing.md) 전화 접속 회의에 대한 다이얼 플랜을 구성하는 데 대한 자세한 내용은 에서 다이얼 플랜 만들기 [또는 수정을 비즈니스용 Skype 서버.](../../deploy/deploy-enterprise-voice/dial-plans.md)
  
> [!NOTE]
> 해당 액세스 번호에 대해 AD DS(Active Directory 도메인 서비스) 복제가 완료되어야 새 전화 접속 액세스 번호를 사용할 수 있습니다. 복제 작업은 몇 시간이 소요될 수 있습니다. 
  
> [!NOTE]
> 전화 접속 액세스 번호를 만든 후 사용자가 올바른 액세스 번호를 보다 쉽게 식별할 수 있도록 Active Directory 대화 상대 개체에 대한 표시 이름을 수정할 수 있습니다. 표시 이름을 수정하려면 [Set-CsDialInConferencingAccessNumber](/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps) cmdlet을 사용 합니다. Active Directory 개체는 수동으로 수정할 수 없습니다.
  
### <a name="to-create-a-dial-in-access-number"></a>전화 접속 액세스 번호를 만들면

1. CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.
    
2. 제어판을 비즈니스용 Skype 서버 를 니다.
    
3. 왼쪽 탐색 모음에서 **회의** 를 클릭한 다음 **전화 접속 액세스 번호** 를 클릭합니다.
    
4. 전화 접속 **액세스 번호 페이지에서** 다음 중 하나를 선택합니다.
    
   - 새로 **추가를** 클릭하여 새 전화 접속 액세스 **번호를 열 수 있습니다.**
    
   - 목록에서 전화 접속 액세스 번호 중 하나를 클릭하고 편집, 자세한 정보 **표시를 클릭합니다.**
    
     > [!NOTE]
     > 검색 필드를 사용하여 전화 접속 액세스 번호 목록에서 열의 내용을 검색하면 예상한 결과가 산출되지 않을 수 있습니다. 대신 보거나 변경할 전화 접속 액세스 번호를 식별하기 위해 원하는 열별로 목록을 정렬합니다. 
  
5. 표시 **번호에** PSTN(전화망) 전화 사용자가 전화 회의에 참가하기 위해 전화를 걸 전화 번호를 입력합니다. 이 번호는 모임 초대 및 전화 접속 회의 웹 설정 표시됩니다.
    
6. 표시 **이름에** 전화 접속 액세스 번호에 대한 설명을 입력합니다. 검색 결과에서 전화 접속 액세스 번호와 비즈니스용 Skype 이름입니다. 이 이름은 사용자가 액세스 번호로 전화를 걸 때 클라이언트에 표시됩니다. 
    
7. 줄 **URI에** 번호 앞에 + 기호를 입력하고 공백을 제외한 전화 접속 액세스 번호의 E.164 번호를 TEL URI 형식으로 입력합니다. 예를 들어 tel:+14255550200.
    
    > [!NOTE]
    > 다른 전화 접속 회의 액세스 번호에서 동일한 줄 URI를 다시 사용할 수 없습니다. 
  
8. **SIP URI에서** 다음을 합니다.
    
   - 텍스트 상자에 이 전화 접속 회의 액세스 번호에 대한 고유한 SIP URI를 입력합니다. 이 SIP URI는 통화 알림 메시지 및 이전 버전의 Lync 클라이언트를 비롯한 다양한 위치에 표시됩니다.
    
     > [!NOTE]
     > 다른 전화 접속 회의 액세스 번호에서 동일한 SIP URI를 다시 사용할 수 없습니다. 액세스 번호를 만든 후 SIP URI를 수정할 수 없습니다. SIP URI를 변경하는 유일한 방법은 액세스 번호를 삭제하고 다시 만드는 것입니다. 
  
   - 드롭다운 목록 상자에서 이 전화 접속 액세스 회의 도우미 애플리케이션 지원하는 도메인을 클릭합니다.
    
9. **풀에서** 이 전화 접속 액세스 번호를 지원하는 회의 도우미 풀을 클릭합니다.
    
    > [!NOTE]
    > 액세스 번호를 만든 후 풀을 변경해야 하는 경우 [Move-CsApplicationEndpoint](/powershell/module/skype/move-csapplicationendpoint?view=skype-ps) cmdlet을 사용하거나 액세스 번호를 삭제하고 다시 만들어야 합니다.
  
10. 기본 **언어에서** 이 전화 접속 액세스 번호에 대해 프롬프트가 재생되는 언어를 클릭합니다. 
    
    기본 언어는 통화에 응답하기 위해 회의 도우미 언어입니다. 지원되는 언어는 각 액세스 전화 번호와 함께 전화 접속 회의 웹 설정 표시됩니다.
    
11. (선택 사항) 보조 **언어(최대 4개)에서** 추가를 클릭하고, 이 전화 접속 액세스 번호에 대한 발신자에 대해 지원할 추가 언어를 하나 이상 선택하고 확인을 **클릭합니다.**  
    
    각 전화 접속 액세스 번호에 대해 최대 4개의 보조 언어를 선택할 수 있습니다. 사용자는 전화 회의에 전화 접속할 때 전화 회의 ID를 입력하기 전에 보조 언어를 선택할 수 있습니다.
    
12. 전화 접속 액세스 번호에 대한 지역을 추가하려면 관련 지역 아래에서 **추가를** 클릭하고 이 전화 접속 액세스 번호의 다이얼 플랜과 연결된 하나 이상의 지역을 클릭한 다음 확인을 **클릭합니다.**
    
13. 전화 접속 액세스 번호에서 지역을 삭제하려면 연결된 지역 아래에서 삭제할 지역을 클릭한 다음 제거를 **클릭합니다.** 
    
14. **커밋** 을 클릭합니다.
    
## <a name="configure-conferencing-policies"></a>회의 정책 구성
<a name="BKMK_ConfigureConferencingPolicies"> </a>

회의 정책은 참가자의 회의 환경을 지정하는 사용자 계정 설정이며, 사이트 범위나 사용자 범위에서 만들 수 있습니다. 회의 정책 설정에는 회의 예약 및 참가와 관련된 여러 측면이 포함됩니다. 여러 회의 정책 설정에서는 참가자를 위한 전화 접속 회의가 지원됩니다. 전화 접속 회의를 구성할 경우 이 필드가 조직에 적절하게 설정되어 있는지 확인하고 필요한 경우 필드를 수정해야 합니다. 
  
회의 정책을 구성하는 데 대한 자세한 내용은 [Manage conferencing policies in 비즈니스용 Skype 서버.](../../manage/conferencing/conferencing-policies.md)
  
## <a name="assign-a-line-uri-to-a-user-account"></a>사용자 계정에 줄 URI 할당
<a name="BKMK_AssignaLineURI"> </a>

전화 접속 사용자는 전화 번호 또는 내선 번호와 PIN을 입력하여 인증된 사용자로 전화 회의에 참가합니다. 인증을 위해 비즈니스용 Skype 서버 사용자 계정에 지정된 전화 통신 줄 **URI가** 필요합니다.
  
이 항목의 절차에서는 단일 사용자 계정에 대해 **줄 URI** 를 할당하는 방법에 대해 설명합니다. 여러 사용자 계정에 대해 **줄 URI** 를 할당해야 하는 경우 **Set-CsUser** cmdlet이 사용되는 스크립트를 만들 수 있습니다. 샘플 스크립트를 사용하여 여러 사용자 계정에 **줄 URI를** 할당하는 데 대한 자세한 내용은 [Assign Line URI to Multiple Users을 참조합니다.](https://go.microsoft.com/fwlink/p/?linkId=196945)
  
1. RTCUniversalServerAdmins 그룹의 구성원이나 **Cs-UserAdministrator** 또는 **CsAdministrator** 역할의 구성원으로 컴퓨터에 로그온합니다.
    
2.  제어판을 비즈니스용 Skype 서버 를 니다.
    
3. 왼쪽 탐색 모음에서 **사용자** 를 클릭합니다.
    
4. 검색 필드에 전화 접속 회의에 대해 구성할 사용자 이름을 입력하거나 **필터 추가** 를 클릭하여 검색 필드를 지정한 다음 **찾기** 를 클릭합니다.
    
5. 사용자 이름을 두 번 클릭하여 사용자 편집 **대화 상자를 비즈니스용 Skype 서버** 열 수 있습니다.
    
6. **전화 통신** 의 **줄 URI** 필드에 정규화된 고유한 전화 번호를 입력합니다(예: tel:+14255550200).
    
    > [!NOTE]
    > 전화 통신이 PC 대  **PC** 전용, Enterprise Voice, 원격 통화 제어 또는 원격  통화 제어로 설정된 경우만 줄 **URI를** 지정할 **수 있습니다.**  
  
7. **커밋** 을 클릭합니다.
