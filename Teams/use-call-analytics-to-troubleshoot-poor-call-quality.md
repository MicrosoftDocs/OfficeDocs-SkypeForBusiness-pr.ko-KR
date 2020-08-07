---
title: 통화 분석을 사용 하 여 통화 품질 저하 문제 해결
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: mikedav, vkorlep
ms.topic: article
ms.assetid: 66945036-ae87-4c08-a0bb-984e50d6b009
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.directrouting.callanalytics
- ms.teamsadmincenter.users.activity.audioqualitycolumn
- Reporting
description: 장치, 네트워크 및 연결에 대 한 사용자별 통화 분석 세부 정보를 사용 하 여 Microsoft 팀원의 통화 및 모임에서 발생 하는 문제를 해결할 수 있습니다.
ms.openlocfilehash: 8bee41e79f2610adcb9a1fed3f895c728526f5ea
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/06/2020
ms.locfileid: "46583627"
---
# <a name="use-call-analytics-to-troubleshoot-poor-call-quality"></a>통화 분석을 사용 하 여 통화 품질 저하 문제 해결

이 문서에서는 팀 관리자 또는 팀 통신 지원 전문가 또는 엔지니어의 경우 통화 분석을 사용 하 여 개별 사용자의 불충분 한 Microsoft 팀 통화 또는 모임 품질 문제를 해결 하는 방법을 설명 합니다.


  
## <a name="call-analytics-permissions"></a>통화 분석 사용 권한

이 문서에서는 이미 통화 분석을 설정한 것으로 가정 합니다. 그렇지 않은 경우 [팀에 대 한 통화 분석 설정을](set-up-call-analytics.md)읽어 보세요.

## <a name="introduction-to-call-analytics"></a>통화 분석 소개

통화 분석에서는 Office 365 계정에서 각 사용자의 팀 호출 및 모임에 대 한 자세한 정보를 보여 줍니다. 여기에는 장치, 네트워크, 연결, 통화 품질에 대 한 정보가 포함 되어 있습니다 (통화 품질이 좋지 않을 수 있습니다.). 빌드, 사이트 및 테 넌 트 정보를 업로드 하는 경우, 각 통화와 모임에 대 한 정보도 함께 표시 됩니다. 통화 분석을 사용 하 여 사용자의 통화 또는 모임 환경이 좋지 않은 이유를 알아낼 수 있습니다.

통화 분석에서는 한 명의 참가자에서 두 번째 참가자에 이르기까지 통화 또는 모임의 각 레그를 보여 줍니다. 팀 관리자는 이러한 세부 정보를 분석 하 여 문제 영역을 분리 하 고 품질이 좋지 않은 경우 근본 원인을 파악할 수 있습니다.
   
팀 관리자는 각 사용자에 대 한 모든 통화 분석 데이터에 대 한 모든 액세스 권한을 얻을 수 있습니다. 또한 지원 직원에 게 Azure Active Directory 역할을 할당할 수 있습니다. 이러한 역할에 대 한 자세한 내용은 [지원 및 헬프 데스크 직원에 대 한 사용 권한을](set-up-call-analytics.md#give-permission-to-support-and-helpdesk-staff)읽어 보세요. [각 팀이 역할을 지 원하는 기능](#what-does-each-teams-support-role-do) 을 놓치지 마세요.

## <a name="where-to-find-per-user-call-analytics"></a>사용자별 통화 분석을 찾을 수 있는 위치

사용자의 모든 통화 정보 및 데이터를 보려면 [팀 관리 센터로](https://admin.teams.microsoft.com)이동 합니다. 사용자 **에서**사용자를 선택한 다음 사용자 프로필 페이지에서 **통화 기록** 탭을 엽니다. 여기에서 지난 30 일간 해당 사용자의 모든 통화와 모임을 찾을 수 있습니다.

![모든 분석 사용자 데이터의 스크린샷](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image1.png)

자세한 미디어 및 네트워킹 통계를 포함 하 여 지정 된 세션에 대 한 추가 정보를 얻으려면 세션을 클릭 하 여 세부 정보를 확인 합니다.

![통화 분석 사용자 세션 데이터 스크린샷](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image2.png)
  
## <a name="what-does-each-teams-support-role-do"></a>각 팀이 역할을 지 원하는 기능은 무엇 인가요?

**팀 의사 소통 지원 전문가** (계층 1 지원)는 기본 통화 품질 문제를 처리 합니다. 모임 관련 문제를 조사 하지 않습니다. 그 대신 관련 정보를 수집한 다음 통신 지원 엔지니어로 승격 합니다. 

**팀 의사 소통 지원 엔지니어** (계층 2 지원)는 팀 통신 지원 전문가에 게 서 숨겨진 자세한 콜 로그의 정보를 표시 합니다. 아래 표에는 각 팀 통신 지원 역할에 사용할 수 있는 정보가 나열 되어 있습니다.

다음 표에서는 각 통신 지원 역할에 사용할 수 있는 사용자별 정보를 알려줍니다.

|**활동**|**방법**|통신 지원 **전문가가** 볼 수 있는 기능|통신 지원 **엔지니어가** 볼 수 있는 기능|
|:-----|:-----|:-----|:-----|
|**전화가** <br/> |발신자 이름  <br/> |에이전트에서 검색 한 사용자의 이름만  <br/> |사용자 이름입니다.  <br/> |
||받는 사람 이름  <br/> |내부 사용자 또는 외부 사용자로 표시 됩니다.  <br/> |받는 사람 이름입니다.  <br/> |
||호출자 전화 번호  <br/> |마지막 세 자리 숫자를 제외한 전체 전화 번호는 별표 기호로 난독 처리 됩니다. 예를 들어 15552823 * * *.  <br/> |마지막 세 자리 숫자를 제외한 전체 전화 번호는 별표 기호로 난독 처리 됩니다. 예를 들어 15552823 * * *.  <br/> |
||받는 사람 전화 번호  <br/> |마지막 세 자리 숫자를 제외한 전체 전화 번호는 별표 기호로 난독 처리 됩니다. 예를 들어 15552823 * * *.  <br/> |마지막 세 자리 숫자를 제외한 전체 전화 번호는 별표 기호로 난독 처리 됩니다. 예를 들어 15552823 * * *.  <br/> |
||**통화 정보**  >  **고급** 탭 <br/> |정보가 표시 되지 않습니다.  <br/> |표시 되는 모든 정보 (예: 장치 이름, IP 주소, 서브넷 매핑 등)  <br/> |
||**통화 정보**  >  **고급**  >  **디버그** 탭 <br/> |정보가 표시 되지 않습니다.  <br/> |DNS 접미사 및 SSID와 같이 표시 되는 모든 정보  <br/> |
|**모임** <br/> |참가자 이름  <br/> |에이전트에서 검색 한 사용자의 이름만 다른 참가자가 내부 사용자 또는 외부 사용자로 식별 되었습니다.  <br/> |모든 이름이 표시 됩니다.  <br/> |
||참가자 수  <br/> |참가자 수입니다.  <br/> |참가자 수입니다.  <br/> |
||세션 정보  <br/> |세션 정보가 예외와 함께 표시 됩니다. 에이전트가 검색 한 사용자의 이름만 표시 됩니다. 다른 참가자가 내부 사용자 또는 외부 사용자로 식별 되었습니다. 별표 기호로 난독 처리 된 전화 번호의 마지막 세 자리입니다.  <br/> |세션 정보가 표시 됩니다. 사용자 이름 및 세션 정보가 표시 됩니다. 별표 기호로 난독 처리 된 전화 번호의 마지막 세 자리입니다.  <br/> |
||||
  
## <a name="troubleshoot-user-call-quality-problems"></a>사용자 통화 품질 문제 해결 

1. 팀 관리 센터를 열고 https://admin.teams.microsoft.com) 팀 통신 지원 또는 팀 관리자 자격 증명을 사용 하 여 로그인 합니다.

2. **대시보드의** **사용자 검색**에서 문제를 해결할 사용자의 이름 또는 SIP 주소를 입력 하거나 **사용자 보기** 를 선택 하 여 사용자 목록을 표시 합니다.

3. 목록에서 사용자를 선택 합니다.

4. **통화 내역**을 선택한 다음 문제를 해결할 통화 또는 모임을 선택 합니다.
    
5. **고급** 탭을 선택 하 고 잘못 된 통화 음질 또는 연결 문제를 나타내는 노란색 및 빨간색 항목을 찾습니다.
    
    각 통화 또는 모임에 대 한 세션 세부 정보에서 경미한 문제는 노란색으로 표시 됩니다. 노란색이 있는 것은 정상 범위를 벗어나므로 문제가 될 수 있지만 문제의 주요 원인이 되는 경우는 거의 없습니다. 무언가 빨간색 인 경우 중대 한 문제가 될 수 있으며,이 세션에 대 한 통화 품질이 좋지 않을 수 있습니다. 
      
드문 경우 지만 오디오 세션에 대 한 경험 치 데이터를 받지 못하는 경우가 있습니다. 이 오류는 일반적으로 호출 손실 또는 클라이언트와의 연결이 종료 될 때 발생 합니다. 이 문제가 발생 하면 세션 등급을 **사용할 수 없습니다**.
  
체감 품질 (환경 품질) 데이터를 사용 하는 오디오 세션의 경우 다음 표에서는 세션을 **불량**으로 정규화 하는 주요 문제에 대해 설명 합니다.
  
|**문제**|**지역을**|**설명**|
|:-----|:-----|:-----|
|전화 걸기 설정  <br/> |세션  <br/> |오류 코드 Ms-diag 20-29는 통화 설정이 실패 했음을 나타냅니다. 사용자가 통화 또는 모임에 참가할 수 없습니다.  <br/> |
|오디오 네트워크에서 낮은 통화 분류  <br/> |세션  <br/> |네트워크 품질 문제 (예: 패킷 손실, 지터, NMOS 성능 저하, RTT 또는 숨겨진 비율)가 발생 했습니다.  <br/> |
|장치가 작동 하지 않음  <br/> |장치  <br/> | 장치가 제대로 작동 하지 않습니다. 장치 작동 비율이 아닌 이유는 다음과 같습니다. <br/>  DeviceRenderNotFunctioningEventRatio >= 0.005 <br/>  DeviceCaptureNotFunctioningEventRatio >= 0.005 <br/> |
   

## <a name="related-topics"></a>관련 항목

[사용자별 통화 분석 설정](set-up-call-analytics.md)



  
 
