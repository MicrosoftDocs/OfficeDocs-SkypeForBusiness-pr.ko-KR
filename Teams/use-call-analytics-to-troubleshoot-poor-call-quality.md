---
title: 통화 분석을 사용하여 통화 품질 저하 문제 해결
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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.directrouting.callanalytics
- ms.teamsadmincenter.users.activity.audioqualitycolumn
- Reporting
description: 디바이스, 네트워크 및 연결에 대한 사용자별 통화 분석 세부 정보를 사용하여 Microsoft Teams 통화 및 모임의 사용자 문제를 해결합니다.
ms.openlocfilehash: 47b60eb979c36508ed1911a70f531695c03533e5
ms.sourcegitcommit: d16fb01f752d186445893ea8e3b0d4450a4a0e67
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/29/2022
ms.locfileid: "65125653"
---
# <a name="use-call-analytics-to-troubleshoot-poor-call-quality"></a>통화 분석을 사용하여 통화 품질 저하 문제 해결

이 문서에서는 Teams 관리자, Teams 통신 지원 전문가 또는 Teams 통신 지원 엔지니어 역할을 보유하고 있는 경우 Call Analytics를 사용하여 개별 사용자의 Microsoft Teams 통화 또는 모임 품질 저하 문제를 해결하는 방법을 설명합니다.

## <a name="call-analytics-permissions"></a>통화 분석 권한

이 문서에서는 이미 Call Analytics를 설정했음을 가정합니다. 그렇지 않은 경우 [Teams 대한 통화 분석 설정을 읽어봅니다](set-up-call-analytics.md).

## <a name="introduction-to-call-analytics"></a>통화 분석 소개

통화 분석에는 Office 365 계정의 각 사용자에 대한 Teams 통화 및 모임에 대한 자세한 정보가 표시됩니다. 여기에는 디바이스, 네트워크, 연결 및 통화 품질에 대한 정보가 포함됩니다(이러한 정보 중 어느 것이든 통화 또는 모임 품질 저하의 요인이 될 수 있음). 건물, 사이트 및 테넌트 정보를 업로드하는 경우 각 통화 및 모임에 대한 이 정보도 표시됩니다. 통화 분석을 사용하여 사용자가 통화 또는 모임 환경이 좋지 못한 이유를 파악할 수 있습니다.

통화 분석은 한 참가자에서 두 번째 참가자까지 통화 또는 모임의 각 레그를 보여 줍니다. Teams 관리자는 이러한 세부 정보를 분석하여 문제 영역을 격리하고 품질 저하의 근본 원인을 식별할 수 있습니다.

Teams 관리자는 각 사용자에 대한 모든 Call Analytics 데이터에 대한 모든 권한을 얻습니다. 또한 지원 직원에게 Azure Active Directory 역할을 할당할 수 있습니다. 이러한 역할에 대해 자세히 알아보려면 [지원 권한 부여 및 기술 지원팀 직원을](set-up-call-analytics.md#give-permission-to-support-and-helpdesk-staff) 읽어보세요. [각 Teams 지원 역할이 수행하는 작업을](#what-does-each-teams-support-role-do) 놓치지 마세요.

## <a name="where-to-find-per-user-call-analytics"></a>사용자별 통화 분석을 찾을 수 있는 위치

사용자의 모든 통화 정보 및 데이터를 보려면 [Teams 관리 센터로](https://admin.teams.microsoft.com) 이동합니다. **사용자** 아래에서 사용자를 선택한 다음 사용자의 프로필 페이지에서 **모임 & 통화** 탭을 엽니다. 여기서는 지난 30일 동안 해당 사용자의 모든 통화 및 모임을 찾을 수 있습니다.

![모든 분석 사용자 데이터의 스크린샷.](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image1.png)

자세한 미디어 및 네트워킹 통계를 포함하여 지정된 세션에 대한 추가 정보를 얻으려면 세션을 클릭하여 세부 정보를 확인합니다.

![통화 분석 사용자 세션 데이터의 스크린샷.](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image2.png)

## <a name="what-does-each-teams-support-role-do"></a>각 Teams 지원 역할은 무엇을 합니까?

**Teams 통신 지원 전문가**(계층 1 지원)는 기본 통화 품질 문제를 처리합니다. 모임 관련 문제는 조사하지 않습니다. 대신 관련 정보를 수집한 다음 Teams 통신 지원 엔지니어에게 에스컬레이션합니다.

**Teams 통신 지원 엔지니어**(계층 2 지원)는 Teams 통신 지원 전문가에게 숨겨진 자세한 통화 로그에 정보를 표시합니다. 아래 표에는 각 Teams 통신 지원 역할에 사용할 수 있는 정보가 나와 있습니다.

다음 표에서는 각 통신 지원 역할에 사용할 수 있는 사용자별 정보를 알려줍니다.

|활동|정보|통신 내용<br>지원 *전문가가* 보고|통신 내용<br>지원 *엔지니어* 가 보는 경우|
|---|---|---|---|
|**호출**|호출자 이름|에이전트가 검색한 사용자의 이름만 해당합니다.|사용자 이름입니다.|
||받는 사람 이름|내부 사용자 또는 외부 사용자로 표시됩니다.|받는 사람 이름입니다.|
||호출자 전화 번호|마지막 세 숫자를 제외한 전체 전화 번호는 별표 기호로 난독 처리됩니다. 예를 들어 15552823\*\*\*.|마지막 세 숫자를 제외한 전체 전화 번호는 별표 기호로 난독 처리됩니다. 예를 들어 15552823\*\*\*.|
||받는 사람 전화 번호|마지막 세 숫자를 제외한 전체 전화 번호는 별표 기호로 난독 처리됩니다. 예를 들어 15552823\*\*\*.|마지막 세 숫자를 제외한 전체 전화 번호는 별표 기호로 난독 처리됩니다. 예를 들어 15552823\*\*\*.|
||**통화 세부 정보** \> **고급** 탭|정보가 표시되지 않습니다.|표시된 모든 세부 정보(예: 디바이스 이름, IP 주소, 서브넷 매핑 등)|
||**통화 세부 정보** \> **고급** \> **디버그** 탭|정보가 표시되지 않습니다.|표시된 모든 세부 정보(예: DNS 접미사 및 SSID).|
|**모임**|참가자 이름|에이전트가 검색한 사용자의 이름만 해당합니다. 내부 사용자 또는 외부 사용자로 식별된 다른 참가자|표시된 모든 이름입니다.|
||참가자 수|참가자 수입니다.|참가자 수입니다.|
||세션 세부 정보|예외와 함께 표시되는 세션 세부 정보입니다. 에이전트가 검색한 사용자의 이름만 표시됩니다. 내부 사용자 또는 외부 사용자로 식별된 다른 참가자 별표 기호로 난독 처리된 전화 번호의 마지막 3자리 숫자입니다.|세션 세부 정보가 표시됩니다. 사용자 이름 및 세션 세부 정보가 표시됩니다. 별표 기호로 난독 처리된 전화 번호의 마지막 3자리 숫자입니다.|
||||

> [!NOTE]
> 고급 탭의 '기타' 섹션과 디버그 탭 모두에 포함된 정보에는 Microsoft 지원 엔지니어를 지원하기 위한 원격 분석 및 서비스 진단 데이터가 포함되어 있습니다. 엔지니어를 지원하는 데 사용할 수 있는 추가 데이터의 컨텍스트가 없으면 중복되거나 부정확하거나 혼동될 수 있습니다. 통화 문제 해결에서 다른 수준의 세부 정보를 찾고 있는 고급 사용자가 사용할 수 있도록 하지만 Microsoft 지원 없이 이 데이터를 기반으로 판단하는 것은 권장되지 않습니다.

## <a name="troubleshoot-user-call-quality-problems"></a>사용자 통화 품질 문제 해결

1. Teams 관리 센터(<https://admin.teams.microsoft.com>)를 열고 Teams 통신 지원 또는 Teams 관리자 자격 증명으로 로그인합니다.

2. **대시보드** 의 **사용자 검색** 에서 문제를 해결하려는 사용자의 이름 또는 SIP 주소를 입력하거나 **사용자 보기를** 선택하여 사용자 목록을 표시합니다.

3. 목록에서 사용자를 선택합니다.

4. **통화 기록을** 선택한 다음, 문제 해결하려는 통화 또는 모임을 선택합니다.

5. **고급** 탭을 선택한 다음 통화 품질 저하 또는 연결 문제를 나타내는 노란색 및 빨간색 항목을 찾습니다.

   각 통화 또는 모임에 대한 세션 세부 정보에 사소한 문제가 노란색으로 표시됩니다. 노란색이면 정상 범위를 벗어나고 문제에 영향을 줄 수 있지만 문제의 주요 원인이 될 가능성은 낮습니다. 빨간색이면 중요한 문제이며 이 세션의 통화 품질 저하의 주요 원인일 수 있습니다.

드문 경우로, 오디오 세션에 대한 경험 품질 데이터가 수신되지 않습니다. 이는 종종 끊어진 호출 또는 클라이언트와의 연결이 종료될 때 발생합니다. 이 경우 세션 등급을 **사용할 수 없습니다**.

QoE(경험 품질) 데이터가 있는 오디오 세션의 경우 다음 표에서는 세션을 **불량** 으로 한정하는 주요 문제에 대해 설명합니다.

|문제|영역|설명|
|---|---|---|
|통화 설정|세션|오류 코드 Ms-diag 20-29는 호출 설정이 실패했음을 나타냅니다. 사용자가 통화 또는 모임에 참가할 수 없습니다.|
|오디오 네트워크 분류 불량 통화|세션|네트워크 품질 문제(예: 패킷 손실, 지터, NMOS 저하, RTT 또는 은폐된 비율)가 발생했습니다.|
|디바이스가 작동하지 않음|장치|디바이스가 제대로 작동하지 않습니다. 디바이스가 작동하지 않는 비율은 다음과 같습니다. <p> DeviceRenderNotFunctioningEventRatio >= 0.005 <br>  DeviceCaptureNotFunctioningEventRatio >= 0.005|
||||

## <a name="related-topics"></a>관련 항목

[사용자별 통화 분석 설정](set-up-call-analytics.md)
