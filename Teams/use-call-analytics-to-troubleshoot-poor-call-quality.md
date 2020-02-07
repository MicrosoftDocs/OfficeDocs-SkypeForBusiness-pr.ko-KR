---
title: 통화 분석을 사용하여 통화 품질 저하 문제 해결
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, wlooney
ms.date: 03/08/2019
ms.topic: article
ms.assetid: 66945036-ae87-4c08-a0bb-984e50d6b009
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.directrouting.callanalytics
- ms.teamsadmincenter.users.activity.audioqualitycolumn
- Reporting
description: 장치, 네트워크 및 연결에 대 한 통화 분석 세부 정보를 사용 하 여 Microsoft 팀과 비즈니스용 Skype 통화 및 모임에서 발생 하는 사용자 문제를 해결할 수 있습니다.
ms.openlocfilehash: a9ef3265fa86349ef92c6174c6f561b006af4d1a
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41836768"
---
# <a name="use-call-analytics-to-troubleshoot-poor-call-quality"></a>통화 분석을 사용하여 통화 품질 저하 문제 해결

통화 분석을 통해 Microsoft 팀과 비즈니스용 Skype의 통화 또는 연결 문제를 해결할 수 있습니다. 통화 분석에서는 Office 365 계정에서 각 사용자의 통화 및 모임에 대 한 장치, 네트워크 및 연결에 대 한 자세한 정보를 보여 줍니다. 빌드, 사이트 및 테 넌 트 정보가 통화 분석에 추가 된 경우 각 통화와 세션에 대해서도 표시 됩니다. 통화 분석을 통해 사용할 수 있는 정보는 사용자의 통화 또는 모임 환경이 좋지 않은 이유를 파악 하는 데 도움이 될 수 있습니다. 
  
## <a name="call-analytics-permissions"></a>통화 분석 사용 권한

관리자는 통화 분석의 모든 기능에 대 한 모든 권한을 얻을 수 있습니다. 또한 지원 직원에 게 Azure Active Directory 역할을 할당할 수 있습니다. 통화 분석을 제한 된 보기를 사용 해야 하는 사용자에 게 팀 의사 소통 지원 전문가 역할을 배정 합니다. 통화 분석의 전체 기능에 대 한 액세스 권한이 필요한 사용자에 게 팀 의사 소통 지원 엔지니어 역할을 할당 합니다. 두 사용 권한 수준 모두에서 나머지 Microsoft 팀 관리 센터에 대 한 액세스를 방지 합니다.

통신 지원 전문가는 기본 통화 품질 문제를 처리 합니다. 모임 관련 문제를 조사 하지 않습니다. 그 대신 관련 정보를 수집한 다음 통신 지원 엔지니어로 승격 합니다. 통신 지원 엔지니어가 통신 지원 전문가에 게 서 숨겨진 자세한 콜 로그의 정보를 확인 합니다. 다음 표에서는 통화 분석을 사용할 때 통신 지원 엔지니어가 제공 하는 정보에 대 한 개요를 제공 합니다.

사용자에 게 할당 된 사용 권한 수준은 통화 분석에서 액세스할 수 있는 정보 유형을 결정 합니다.
  
- **팀 서비스 관리자 또는 팀 통신 관리자**: 통화 분석 및 Microsoft 팀 관리 센터의 모든 정보에 액세스할 수 있습니다.
    
- **팀 의사 소통 지원 전문가**: 통화 분석에서 제한 된 데이터 집합을 볼 수 있습니다. 통화 문제를 해결할 수 있지만, 팀 의사 소통 지원 엔지니어에 대 한 모임 문제는 해결 하겠습니다. 나머지 Microsoft 팀 관리 센터에 액세스할 수 있는 권한이 없습니다.
    
- **팀 의사 소통 지원 엔지니어**: 통화 분석에서 사용할 수 있는 모든 데이터를 볼 수 있으며, 통화와 모임 모두의 문제를 해결 하는 데 도움이 됩니다. 나머지 Microsoft 팀 관리 센터에 액세스할 수 있는 권한이 없습니다.
    
> [!NOTE]
> 커뮤니케이션 지원 전문가 역할은 계층 1 지원과 같으며 통신 지원 엔지니어 역할은 계층 2 지원과 동일 합니다.

팀 관리자 역할에 대 한 자세한 내용은 [Microsoft 팀 관리자 역할을 사용 하 여 팀 관리](using-admin-roles.md)를 참조 하세요. 팀 의사 소통 지원 전문가 및 팀 의사 소통 지원 엔지니어 역할에 대 한 자세한 비교는 [통화 분석 설정을](set-up-call-analytics.md#set-call-analytics-permissions) 참조 하세요. 
  
사용 권한에 대 한 도움이 필요한 경우 팀과 비즈니스용 Skype 관리자에 게 문의 하세요.
  
## <a name="troubleshoot-call-quality-problems-using-call-analytics"></a>통화 분석을 사용 하 여 통화 품질 문제 해결

1. 팀 통신 지원 또는 팀 관리자 자격 증명을 사용 하 여 로그인 합니다.

2. 웹 브라우저에서으로 이동 *https://admin.teams.microsoft.com*합니다.
    
3. **대시보드의** **사용자 검색**에서 문제를 해결할 사용자의 이름 또는 sip 주소를 입력 하거나 사용자 **보기** 를 선택 하 여 사용자 목록을 표시 합니다.
    
    ![통화 분석의 사용자 검색 상자 스크린샷](media/use-call-analytics-to-troubleshoot-image-1.png)
  
4. 목록에서 사용자를 선택 합니다.

5. **통화 내역**을 선택한 다음 문제를 해결할 통화 또는 모임을 선택 합니다.
    
    ![사용자의 통화 기록 페이지 스크린샷.](media/use-call-analytics-to-troubleshoot-image-2.png)
  
6. **고급** 탭을 선택 하 고 잘못 된 통화 음질 또는 연결 문제를 나타내는 노란색 및 빨간색 항목을 찾습니다.
    
    각 통화 또는 모임에 대 한 세션 세부 정보에서 경미한 문제는 노란색으로 표시 됩니다. 예를 들어 다음 스크린샷은 평균 지터, 최대 지터 및 평균 패킷 손실률에 대 한 값이 노란색으로 되어 있습니다. 노란색이 있는 것은 정상 범위를 벗어나므로 문제가 될 수 있지만 문제의 주요 원인이 되는 경우는 거의 없습니다. 무언가 빨간색 인 경우 중대 한 문제가 될 수 있으며,이 세션에 대 한 통화 품질이 좋지 않을 수 있습니다. 
    
    ![사용자의 통화 기록 고급 탭 스크린샷 ](media/use-call-analytics-to-troubleshoot-image-3.png)
  
드문 경우 지만 오디오 세션에 대 한 경험 치 데이터를 받지 못하는 경우가 있습니다. 이 오류는 일반적으로 호출을 끊는 것이 고 클라이언트를 종료 하는 연결 때문에 발생 합니다. 이 문제가 발생 하면 세션 등급을 **사용할 수 없습니다**.
  
체감 품질 (환경 품질) 데이터를 사용 하는 오디오 세션의 경우 다음 표에서는 세션을 **불량**으로 정규화 하는 주요 문제에 대해 설명 합니다.
  
|**문제**|**지역을**|**설명**|
|:-----|:-----|:-----|
|전화 걸기 설정  <br/> |세션  <br/> |오류 코드 Ms-diag 20-29는 통화 설정이 실패 했음을 나타냅니다. 사용자가 통화 또는 모임에 참가할 수 없습니다.  <br/> |
|오디오 네트워크에서 낮은 통화 분류  <br/> |세션  <br/> |네트워크 품질 문제 (예: 패킷 손실, 지터, NMOS 성능 저하, RTT 또는 숨겨진 비율)가 발생 했습니다. 불량 통화를 분류 하는 데 사용 되는 조건에 대 한 자세한 내용은이 [Microsoft 블로그 게시물](https://go.microsoft.com/fwlink/p/?linkid=852133)을 참조 하세요.  <br/> |
|장치가 작동 하지 않음  <br/> |장치  <br/> | 장치가 제대로 작동 하지 않습니다. 장치 작동 비율이 아닌 이유는 다음과 같습니다. <br/>  DeviceRenderNotFunctioningEventRatio >= 0.005 <br/>  DeviceCaptureNotFunctioningEventRatio >= 0.005 <br/> |
   
## <a name="related-topics"></a>관련 항목
[통화 분석 설정](set-up-call-analytics.md)

[통화 분석 및 통화 품질 대시보드](difference-between-call-analytics-and-call-quality-dashboard.md)

  
 
