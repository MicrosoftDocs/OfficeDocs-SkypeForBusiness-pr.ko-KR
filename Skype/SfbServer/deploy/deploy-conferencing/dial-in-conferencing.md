---
title: 비즈니스용 Skype 서버에서 전화 접속 회의 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 38d9f168-80b8-46f2-a1c0-becd84e58e73
description: '요약: 비즈니스용 Skype 서버에서 전화 접속 회의를 구성 하는 방법에 대 한 자세한 내용은이 항목을 참조 하세요.'
ms.openlocfilehash: 7c62ef5ec984fe89033aa4813bca9674979c1c36
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196944"
---
# <a name="configure-dial-in-conferencing-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 전화 접속 회의 구성
 
**요약:** 비즈니스용 Skype 서버에서 전화 접속 회의를 구성 하는 방법에 대 한 자세한 내용은이 항목을 참조 하세요.
  
회의 작업 부하와 선택한 전화 접속 회의를 포함 하는 토폴로지를 만든 후에는 추가 단계를 수행 하 여 전화 접속 회의를 구성 해야 합니다. 이 항목을 읽기 전에 비즈니스용 [Skype 서버에서 전화 접속 회의에 대 한 요금제](../../plan-your-deployment/conferencing/dial-in-conferencing.md), 비즈니스용 [skype 서버의 회의에 대 한 하드웨어 및 소프트웨어 요구 사항](../../plan-your-deployment/conferencing/hardware-and-software-requirements.md), [배포 순서도 및 검사 목록에 대 한 자세한 내용을 확인 하세요. 전화 접속 회의](deploy-conferencing.md#deployment-flowchart-and-checklist-for-dial-in-conferencing). 
  
전화 접속 회의를 구성 하려면 다음 작업을 수행 해야 합니다.
  
- [다이얼 플랜 구성](dial-in-conferencing.md#BKMK_ConfigureDialPlans)
    
- [전화 접속 회의 영역 구성](dial-in-conferencing.md#BKMK_ConfigureDialInRegions)
    
- [전화 접속 액세스 번호 구성](dial-in-conferencing.md#BKMK_ConfigureDialInAccessNumbers)
    
- [회의 정책 구성](dial-in-conferencing.md#BKMK_ConfigureConferencingPolicies)
    
- [사용자 계정에 줄 URI 지정](dial-in-conferencing.md#BKMK_AssignaLineURI)
    
또한 다음 선택적 작업을 수행할 수 있습니다. 이러한 선택적 작업에 대 한 자세한 내용은 [비즈니스용 Skype 서버에서 전화 접속 회의 관리](../../manage/conferencing/dial-in-conferencing.md)를 참조 하세요.
  
- 전화 접속 회의를 위한 PIN 정책 관리
    
- DTMF 명령에 대 한 키 매핑 관리
    
- 회의 디렉터리 만들기
    
- 컨퍼런스 참가 관리 및 공지 남기기
    
- 전화 접속 회의 설정 테스트
    
- 전화 접속 사용자에 게 환영 메일 보내기
    
## <a name="configure-dial-plans"></a>다이얼 플랜 구성
<a name="BKMK_ConfigureDialPlans"> </a>

전화 접속 회의를 배포 하는 경우 전화 접속 액세스 전화 번호를 라우팅하기 위해 하나 또는 그 이상의 다이얼 플랜을 만들거나 수정 해야 합니다. 또한 각 다이얼 플랜에는 E-164 형식의 완전 한 전화 번호로 변환 하는 규칙 인 정규화 규칙이 하나 이상 포함 되어 있는지도 확인 해야 합니다. 
  
전화 접속 회의 사용자는 개인 id 번호 (PIN)와 전화 번호를 입력 하 여 인증 된 엔터프라이즈 사용자로 회의에 참가 합니다. 내선 번호를 완전 한 전화 번호로 변환 하 여 사용자가 전화 내선 번호만 입력 하는 경우 인증 받을 수 있는 정규화 규칙이 필요 합니다.
  
전화 접속 회의에 대 한 다이얼 플랜을 설정 하려면 다음을 수행 합니다.
  
- 엔터프라이즈 음성을 배포할지 여부에 관계 없이 전화 접속 회의 영역을 추가 하도록 전역 다이얼 플랜을 수정 하 고 정규화 규칙이 전화 접속 액세스 번호를 정확 하 게 변환 하는지 확인 합니다. 자세한 지침은 [비즈니스용 Skype 서버에서 다이얼 플랜 만들기 또는 수정을](../../deploy/deploy-enterprise-voice/dial-plans.md)참조 하세요.
    
- 엔터프라이즈 음성을 배포 하지 않은 경우 전화 접속 회의 액세스 번호에 대 한 다이얼 플랜을 만듭니다. 전화 접속 회의 지역을 포함 해야 합니다. 자세한 지침은 [비즈니스용 Skype 서버에서 다이얼 플랜 만들기 또는 수정을](../../deploy/deploy-enterprise-voice/dial-plans.md)참조 하세요.
    
- 엔터프라이즈 음성을 배포한 경우 전화 접속 액세스 번호에 대 한 영역을 포함 하 고 적절 한 정규화 규칙을 사용 하도록 필요한 경우 Enterprise Voice dial 계획을 수정 합니다. 전화 접속 액세스 번호에만 사용 되는 전용 다이얼 플랜을 만들 수도 있습니다. 자세한 지침은 [비즈니스용 Skype 서버에서 다이얼 플랜 만들기 또는 수정을](../../deploy/deploy-enterprise-voice/dial-plans.md)참조 하세요.
    
정규화 규칙을 만드는 방법에 대 한 자세한 내용은 [비즈니스용 Skype에서 정규화 규칙 만들기 또는 수정을](../../deploy/deploy-enterprise-voice/normalization-rules.md)참조 하세요.
  
## <a name="configure-dial-in-conferencing-regions"></a>전화 접속 회의 영역 구성
<a name="BKMK_ConfigureDialInRegions"> </a>

다이얼 플랜을 설정할 때 해당 다이얼 플랜에 적용 되는 전화 접속 회의 영역을 지정 합니다. 전화 접속 회의 영역은 전화 접속 회의 액세스 번호를 적절 한 다이얼 플랜에 연결 합니다. 전화 접속 액세스 번호를 만들 때 적절 한 다이얼 플랜에 액세스 번호를 연결 하는 지역을 선택 합니다. 
  
모든 다이얼 플랜에 대 한 영역을 지정 하는 것이 중요 하기 때문에 모든 다이얼 플랜에 회의 영역이 있는지 확인 하는 것이 좋습니다. 
  
지역이 모든 전화 접속 회의 다이얼 플랜에 설정 되어 있는지 여부를 확인 하려면 **Get-CsDialPlan 플랜** cmdlet을 사용 합니다. 다이얼 플랜에서 지역이 누락 된 경우 **set-csdialplan** cmdlet을 사용 하 여 지역을 설정할 수 있습니다. 또한 비즈니스용 Skype Server 제어판을 사용 하 여 기존 다이얼 플랜의 지역을 업데이트할 수 있습니다. 비즈니스용 Skype Server 제어판을 사용 하는 방법에 대 한 자세한 내용은 비즈니스용 [Skype 서버에서 다이얼 플랜 만들기 또는 수정을](../../deploy/deploy-enterprise-voice/dial-plans.md)참조 하세요.
  
### <a name="to-verify-whether-dial-plans-have-the-region-property-set"></a>다이얼 플랜에 region 속성이 설정 되어 있는지 확인 하려면 다음을 입력 합니다.

1. RTCUniversalServerAdmins 그룹의 구성원 또는 **cs-VoiceAdministrator**, **Cs-Serveradministrator**또는 **csadministrator** 역할의 구성원으로 컴퓨터에 로그온 합니다.
    
2. 비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.
    
3. 명령 프롬프트에서 다음을 실행 합니다.
    
   ```
   Get-CsDialPlan [-Identity <Identifier of the dial plans to be retrieved>]
   ```

   예를 들면 다음과 같습니다.
    
   ```
   Get-CsDialPlan
   ```

   이 예제에서는 조직에 대해 구성 된 모든 다이얼 플랜이 반환 됩니다.
    
4. 반환 된 다이얼 플랜을 검토 하 여 전화 접속 회의 영역이 없는 것을 식별 합니다. 
    
자세한 내용은 [가져오기-CsDialPlan 플랜](https://docs.microsoft.com/powershell/module/skype/get-csdialplan?view=skype-ps)을 참조 하세요.
  
### <a name="to-set-the-region-property-for-a-dial-plan"></a>다이얼 플랜의 region 속성을 설정 하려면

1. RTCUniversalServerAdmins 그룹의 구성원 또는 **cs-VoiceAdministrator**, **Cs-Serveradministrator**또는 **csadministrator** 역할의 구성원으로 컴퓨터에 로그온 합니다.
    
2. 비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.
    
3. 전화 접속 회의 영역이 없는 다이얼 플랜의 경우 다음을 실행 합니다.
    
   ```
   Set-CsDialPlan [-Identity <Identity of the dial plan to be modified>] -DialinConferencingRegion "<new region>"
   ```

   예를 들면 다음과 같습니다.
    
   ```
   Set-CsDialPlan -Identity Redmond -DialinConferencingRegion "US West Coast"
   ```

   이 예제에서는 DialinConferencingRegion 속성을 "US 서 부 해안"로 설정 하도록 Redmond Id가 포함 된 다이얼 플랜을 수정 합니다. 
    
자세한 내용은 [CsDialPlan 플랜 설정을](https://docs.microsoft.com/powershell/module/skype/set-csdialplan?view=skype-ps)참조 하세요.
  
## <a name="configure-dial-in-access-numbers"></a>전화 접속 액세스 번호 구성
<a name="BKMK_ConfigureDialInAccessNumbers"> </a>

전화 접속 회의를 배포 하는 경우 오디오 회의에 참가 하기 위해 사용자가 PSTN (공개 전환 전화 네트워크)에서 전화를 걸 수 있는 전화 번호를 설정 해야 합니다. 이러한 전화 접속 액세스 번호는 모임 초대 및 전화 접속 회의 설정 웹 페이지에 표시 됩니다.
  
전화 접속 액세스 번호를 만들려면 먼저 전화 접속 회의 영역을 계획 한 다음 해당 지역으로 다이얼 플랜을 구성 해야 합니다. 지역에 대 한 자세한 내용은 [비즈니스용 Skype 서버의 전화 접속 회의 계획](../../plan-your-deployment/conferencing/dial-in-conferencing.md)을 참조 하세요. 전화 접속 회의에 대 한 다이얼 플랜을 구성 하는 방법에 대 한 자세한 내용은 비즈니스용 [Skype 서버에서 다이얼 플랜 만들기 또는 수정을](../../deploy/deploy-enterprise-voice/dial-plans.md)참조 하세요.
  
> [!NOTE]
> 해당 액세스 번호의 AD DS (Active Directory 도메인 서비스) 복제가 완료 될 때까지 새 전화 접속 액세스 번호를 사용할 수 없습니다. 복제를 완료 하는 데 몇 시간이 걸릴 수 있습니다. 
  
> [!NOTE]
> 전화 접속 액세스 번호를 만든 후에는 사용자가 올바른 액세스 번호를 더 쉽게 식별할 수 있도록 Active Directory 연락처 개체의 표시 이름을 수정할 수 있습니다. 표시 이름을 수정 하려면 [Set-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps) cmdlet을 사용 합니다. Active Directory 개체를 수동으로 수정 해서는 안 됩니다.
  
### <a name="to-create-a-dial-in-access-number"></a>전화 접속 액세스 번호를 만들려면

1. CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.
    
2. 비즈니스용 Skype Server 제어판을 엽니다.
    
3. 왼쪽 탐색 모음에서 **회의** 를 클릭 한 다음 **전화 접속 액세스 번호**를 클릭 합니다.
    
4. **전화 접속 액세스 번호** 페이지에서 다음 중 하나를 수행 합니다.
    
   - **새로 만들기** 를 클릭 하 여 **새 전화 접속 액세스 번호**를 엽니다.
    
   - 목록에서 전화 접속 액세스 번호 중 하나를 클릭 하 고 **편집**을 클릭 한 다음 **세부 정보 표시**를 클릭 합니다.
    
     > [!NOTE]
     > 검색 필드를 사용 하 여 전화 접속 액세스 번호 목록에서 열의 내용을 검색 하면 예상한 결과가 생성 되지 않을 수 있습니다. 대신 원하는 열을 기준으로 목록을 정렬 하 여 보거나 변경 하려는 전화 접속 액세스 번호를 확인 합니다. 
  
5. **표시 번호**에 공개 전환 전화 네트워크 (PSTN) 전화 사용자가 전화를 걸고 있는 전화 번호를 입력 합니다. 이 번호는 모임 초대 및 전화 접속 회의 설정 웹 페이지에 표시 됩니다.
    
6. **표시 이름**에 전화 접속 액세스 번호에 대 한 설명을 입력 합니다. 비즈니스용 Skype 검색 결과에서 전화 접속 액세스 번호와 연결 된 이름입니다. 이 이름은 사용자가 액세스 번호를 호출할 때 클라이언트에 표시 됩니다. 
    
7. **줄 uri**에서 번호 앞에 + 기호를 포함 하 고 공백을 제외 하 고 TEL uri 형식의 전화 접속 액세스 번호에 대 한 E 자의 번호를 입력 합니다. 예를 들어, tel: + 14255550200.
    
    > [!NOTE]
    > 같은 회선 URI를 다른 전화 접속 회의 액세스 번호로 재사용할 수 없습니다. 
  
8. **SIP URI**에서 다음을 수행 합니다.
    
   - 입력란에이 전화 접속 회의 액세스 번호에 대 한 고유한 SIP URI를 입력 합니다. 이 SIP URI는 통화 알림 메시지 및 이전 버전의 Lync 클라이언트를 포함 하 여 다양 한 위치에 표시 됩니다.
    
     > [!NOTE]
     > 같은 SIP URI를 다른 전화 접속 회의 액세스 번호에서 다시 사용할 수 없습니다. 액세스 번호를 만든 후 SIP URI를 수정할 수 없습니다. SIP URI를 변경 하는 유일한 방법은 액세스 번호를 삭제 하 고 다시 만드는 것입니다. 
  
   - 드롭다운 목록 상자에서이 전화 접속 액세스 번호를 지 원하는 회의 수행자 응용 프로그램의 도메인을 클릭 합니다.
    
9. **풀**에서이 전화 접속 액세스 번호를 지 원하는 회의 전화 교환 인스턴스를 실행 하는 풀을 클릭 합니다.
    
    > [!NOTE]
    > 액세스 번호를 만든 후에 풀을 변경 해야 하는 경우 [-CsApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/move-csapplicationendpoint?view=skype-ps) cmdlet을 사용 하거나 액세스 번호를 삭제 하 고 다시 만들어야 합니다.
  
10. **기본 언어**에서이 전화 접속 액세스 번호에 대 한 메시지가 재생 되는 언어를 클릭 합니다. 
    
    기본 언어는 회의 수행자가 통화에 응답 하는 데 사용 하는 언어입니다. 지원 되는 언어는 전화 접속 회의 설정 웹 페이지의 각 액세스 전화 번호 옆에 표시 됩니다.
    
11. ) **보조 언어 (최대 4 개)** 에서 **추가**를 클릭 하 고이 전화 접속 액세스 번호에 대 한 호출자에 대해 지원할 추가 언어를 하나 이상 선택 하 고 **확인**을 클릭 합니다. 
    
    각 전화 접속 액세스 번호에 대해 최대 4 개의 보조 언어를 선택할 수 있습니다. 사용자가 회의에 전화를 걸 때 전화 회의 ID를 입력 하기 전에 보조 언어를 선택할 수 있습니다.
    
12. 전화 접속 액세스 번호에 대 한 영역을 추가 하려면 **연결 된 지역**에서 **추가**를 클릭 하 고이 전화 접속 액세스 번호에 대 한 다이얼 플랜에 연결 된 하나 이상의 지역을 클릭 한 다음 **확인**을 클릭 합니다.
    
13. 전화 접속 액세스 번호에서 지역을 삭제 하려면 **연결 된 지역**에서 삭제할 지역을 클릭 한 다음 **제거**를 클릭 합니다.
    
14. **커밋**을 클릭합니다.
    
## <a name="configure-conferencing-policies"></a>회의 정책 구성
<a name="BKMK_ConfigureConferencingPolicies"> </a>

회의 정책은 참가자의 회의 환경을 지정 하는 사용자 계정 설정입니다. 사이트 범위 또는 사용자 범위를 사용 하 여 회의 정책을 만들 수 있습니다. 회의 정책 설정에는 회의 예약 및 참여의 여러 측면이 포함 됩니다. 여러 회의 정책 설정이 참가자에 대 한 전화 접속 회의를 지원 합니다. 전화 접속 회의를 구성 하는 경우 이러한 필드가 조직에 맞게 적절 하 게 설정 되어 있는지 확인 하 고 필요에 따라 수정 해야 합니다. 
  
회의 정책을 구성 하는 방법에 대 한 자세한 내용은 비즈니스용 [Skype 서버에서 회의 정책 관리](../../manage/conferencing/conferencing-policies.md)를 참조 하세요.
  
## <a name="assign-a-line-uri-to-a-user-account"></a>사용자 계정에 줄 URI 지정
<a name="BKMK_AssignaLineURI"> </a>

전화 접속 사용자는 전화 번호나 내선 번호와 PIN을 입력 하 여 인증 된 사용자로 회의에 참가할 수 있습니다. 비즈니스용 Skype 서버 사용자 계정에 지정 된 전화 통신 **회선 URI** 가 인증에 필요 합니다.
  
이 항목의 절차에서는 단일 사용자 계정에 대 한 **회선 URI** 를 할당 하는 방법에 대해 설명 합니다. 여러 사용자 계정에 대 한 **줄 URI** 를 할당 해야 하는 경우 **Set csuser** cmdlet을 사용 하는 스크립트를 만들 수 있습니다. 샘플 스크립트를 사용 하 여 여러 사용자 계정에 **줄 uri** 를 할당 하는 방법에 대 한 자세한 내용은 [여러 사용자에 게 줄 uri 할당](https://go.microsoft.com/fwlink/p/?linkId=196945)을 참조 하세요.
  
1. RTCUniversalServerAdmins 그룹의 구성원 또는 **Cs-useradministrator** 또는 **csadministrator** 역할의 구성원으로 컴퓨터에 로그온 합니다.
    
2.  비즈니스용 Skype Server 제어판을 엽니다.
    
3. 왼쪽 탐색 모음에서 **사용자**를 클릭 합니다.
    
4. 검색 필드에 전화 접속 회의에 대해 구성할 사용자의 이름을 입력 하거나, **필터 추가** 를 클릭 하 여 검색 필드를 지정 하 고 **찾기를**클릭 합니다.
    
5. 사용자 이름을 두 번 클릭 하 여 비즈니스용 **Skype 서버 사용자 편집** 대화 상자를 엽니다.
    
6. **전화 통신**아래의 **줄 URI** 필드에 고유한 정규화 된 전화 번호 (예: tel: + 14255550200)를 입력 합니다.
    
    > [!NOTE]
    > **전화 통신이** **pc 대 pc 전용**, **엔터프라이즈 음성**, **원격 통화 제어** 또는 **원격 통화 제어 전용 으로만**설정 된 경우에만 **줄 URI** 를 지정할 수 있습니다. 
  
7. **커밋**을 클릭합니다.
    

