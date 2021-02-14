---
title: 통화 분석을 사용하여 통화 품질 불량 문제 해결
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
description: 장치, 네트워크 및 연결에 대한 사용자당 통화 분석 세부 정보를 사용하여 Microsoft Teams 통화 및 모임의 사용자 문제를 해결합니다.
ms.openlocfilehash: 8bee41e79f2610adcb9a1fed3f895c728526f5ea
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/06/2020
ms.locfileid: "46583627"
---
# <a name="use-call-analytics-to-troubleshoot-poor-call-quality"></a>통화 분석을 사용하여 통화 품질 불량 문제 해결

이 문서에서는 Teams 관리자 또는 Teams 통신 지원 전문가 또는 엔지니어인 경우 통화 분석을 사용하여 개별 사용자의 Microsoft Teams 통화 또는 모임 품질 문제를 해결하는 방법을 설명하고 있습니다.


  
## <a name="call-analytics-permissions"></a>Analytics 사용 권한 호출

이 문서에서는 호출 분석을 이미 설정했다고 가정합니다. 아직 없는 경우 Teams에 대한 [통화 분석 설정을 읽어 읽습니다.](set-up-call-analytics.md)

## <a name="introduction-to-call-analytics"></a>호출 분석 소개

통화 분석은 Office 365 계정의 각 사용자에 대한 Teams 통화 및 모임에 대한 자세한 정보를 보여줍니다. 여기에는 장치, 네트워크, 연결 및 통화 품질에 대한 정보가 포함됩니다(이러한 기능 중 어느 것이든 통화 또는 모임 품질이 좋지 않은 요인이 될 수 있습니다). 건물, 사이트 및 테넌트 정보를 업로드하는 경우 각 통화 및 모임에 대해 이 정보도 표시됩니다. 통화 분석을 사용하여 사용자가 통화 또는 모임 환경이 좋지 않은 이유를 알아내기 위해 도움을 줄 수 있습니다.

통화 분석은 한 참가자에서 두 번째 참가자까지 통화 또는 모임의 각 레그를 보여줍니다. Teams 관리자는 이러한 세부 정보를 분석하여 문제 영역을 격리하고 품질이 나쁜 근본 원인을 식별할 수 있습니다.
   
Teams 관리자는 각 사용자에 대한 모든 통화 분석 데이터에 대한 모든 액세스 권한을 얻게 됩니다. 또한 지원 담당자에게 Azure Active Directory 역할을 할당할 수 있습니다. 이러한 역할에 대한 자세한 내용은 지원 및 기술 지원 기술 지원 직원에게 권한 [부여를 읽어 보아야 합니다.](set-up-call-analytics.md#give-permission-to-support-and-helpdesk-staff) 각 Teams 지원 역할의 역할을 놓치지 [마세요.](#what-does-each-teams-support-role-do)

## <a name="where-to-find-per-user-call-analytics"></a>사용자당 호출 분석을 찾을 수 있는 위치

사용자의 모든 통화 정보와 데이터를 표시하려면 Teams 관리 [센터로 이동하세요.](https://admin.teams.microsoft.com) 사용자 **아래에서** 사용자를 선택한 다음  사용자의 프로필 페이지에서 통화 기록 탭을 니다. 여기에서 지난 30일 동안 해당 사용자의 모든 통화 및 모임을 찾을 수 있습니다.

![모든 분석 사용자 데이터의 스크린샷](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image1.png)

자세한 미디어 및 네트워킹 통계를 포함하여 특정 세션에 대한 추가 정보를 얻려면 세션을 클릭하여 세부 정보를 확인합니다.

![호출 분석 사용자 세션 데이터의 스크린샷](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image2.png)
  
## <a name="what-does-each-teams-support-role-do"></a>각 Teams 지원 역할은 무엇을 하나요?

**Teams 통신 지원 전문가(계층** 1 지원)는 기본적인 통화 품질 문제를 처리합니다. 모임 관련 문제는 조사하지 않습니다. 대신 관련 정보를 수집한 다음 통신 지원 엔지니어에게 에스컬레이터합니다. 

**Teams 통신 지원** 엔지니어(계층 2 지원)는 Teams 통신 지원 전문가로부터 숨겨져 있는 자세한 통화 로그의 정보를 볼 수 있습니다. 아래 표에는 각 Teams 통신 지원 역할에 사용할 수 있는 정보가 나열됩니다.

다음 표에서는 각 통신 지원 역할에 사용할 수 있는 사용자당 정보를 제공합니다.

|**활동**|**정보**|통신 지원 전문가가 **보는** 정보|통신 지원 엔지니어가 **보는** 정보|
|:-----|:-----|:-----|:-----|
|**통화** <br/> |호출자 이름  <br/> |에이전트가 검색한 사용자의 이름만  <br/> |사용자 이름입니다.  <br/> |
||받는 사람 이름  <br/> |내부 사용자 또는 외부 사용자로 표시  <br/> |받는 사람 이름입니다.  <br/> |
||호출자 전화 번호  <br/> |마지막 3자리를 제외한 전체 전화 번호는 불일치가 났습니다. 예를 들어 15552823***입니다.  <br/> |마지막 3자리를 제외한 전체 전화 번호는 불일치가 났습니다. 예를 들어 15552823***입니다.  <br/> |
||받는 사람 전화 번호  <br/> |마지막 3자리를 제외한 전체 전화 번호는 불일치가 났습니다. 예를 들어 15552823***입니다.  <br/> |마지막 3자리를 제외한 전체 전화 번호는 불일치가 났습니다. 예를 들어 15552823***입니다.  <br/> |
||**통화 세부 정보**  >  **고급** 탭 <br/> |정보가 표시되지 않습니다.  <br/> |디바이스 이름, IP 주소, 서브넷 매핑 등 표시되는 모든 세부 정보입니다.  <br/> |
||**통화 세부 정보**  >  **고급**  >  **디버그** 탭 <br/> |정보가 표시되지 않습니다.  <br/> |DNS 접미사 및 SSID와 같은 모든 세부 정보가 표시됩니다.  <br/> |
|**모임** <br/> |참가자 이름  <br/> |에이전트가 검색한 사용자의 이름만 내부 사용자 또는 외부 사용자로 식별된 다른 참가자.  <br/> |표시된 모든 이름입니다.  <br/> |
||참가자 수  <br/> |참가자 수입니다.  <br/> |참가자 수입니다.  <br/> |
||세션 세부 정보  <br/> |예외와 함께 표시된 세션 세부 정보입니다. 에이전트가 검색된 사용자의 이름만 표시됩니다. 내부 사용자 또는 외부 사용자로 식별된 다른 참가자. 마지막 3자리 전화 번호가 난수로 표시된 경우,  <br/> |표시된 세션 세부 정보입니다. 표시된 사용자 이름 및 세션 세부 정보입니다. 마지막 3자리 전화 번호가 난수로 표시된 경우,  <br/> |
||||
  
## <a name="troubleshoot-user-call-quality-problems"></a>사용자 통화 품질 문제 해결 

1. Teams 관리 센터를 열고 Teams 통신 지원 또는 Teams 관리자 자격 증명으로 https://admin.teams.microsoft.com) 로그인합니다.

2. 대시보드의  **사용자** 검색에서 호출 문제를 해결하려는 사용자의 이름 또는 SIP 주소를 입력하거나 사용자  보기를 선택하여 사용자 목록을 볼 수 있습니다.

3. 목록에서 사용자를 선택합니다.

4. 통화 **기록을** 선택한 다음 문제 해결을 위해 통화 또는 모임을 선택합니다.
    
5. 고급 **탭을** 선택한 다음 통화 품질 또는 연결 문제를 나타내는 노란색 및 빨간색 항목을 찾아 봐야 합니다.
    
    각 통화 또는 모임에 대한 세션 세부 정보에서 사소한 문제가 노란색으로 표시됩니다. 노란색이면 정상 범위를 밖에 있으며 문제의 원인이 될 수 있지만 문제의 주요 원인일 가능성은 낮습니다. 빨간색이면 심각한 문제로, 이 세션의 통화 품질이 좋지 않은 주요 원인일 수 있습니다. 
      
드문 경우지만 오디오 세션에 대한 경험 품질 데이터는 수신되지 않습니다. 호출이 끊어지거나 클라이언트와의 연결이 종료되는 경우가 종종 있습니다. 이 경우 세션 등급을 사용할 **수 없습니다.**
  
QoE(경험 품질) 데이터가 있는 오디오 세션의 경우 다음 표에서는 세션을 불량으로 한정하는 주요 문제에 **대해 설명하고 있습니다.**
  
|**문제**|**영역**|**설명**|
|:-----|:-----|:-----|
|통화 설정  <br/> |세션  <br/> |오류 코드 Ms-diag 20-29는 호출 설정이 실패했다는 것입니다. 사용자가 통화 또는 모임에 참가할 수 없습니다.  <br/> |
|오디오 네트워크 분류 불량 통화  <br/> |세션  <br/> |네트워크 품질 문제(예: 패킷 손실, 지터, NMOS 성능 저하, RTT 또는 은신 비율)가 발생했습니다.  <br/> |
|디바이스가 작동하지 않습니다.  <br/> |장치  <br/> | 디바이스가 올바르게 작동하지 않습니다. 디바이스가 작동하지 않는 비율은 <br/>  DeviceRenderNotFunctioningEventRatio >= 0.005 <br/>  DeviceCaptureNotFunctioningEventRatio >= 0.005 <br/> |
   

## <a name="related-topics"></a>관련 항목

[사용자당 호출 분석 설정](set-up-call-analytics.md)



  
 
