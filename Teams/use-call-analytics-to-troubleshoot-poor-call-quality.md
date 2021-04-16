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
description: 디바이스, 네트워크 및 연결에 대한 사용자당 통화 분석 세부 정보를 사용하여 Microsoft Teams 호출 및 모임에 대한 사용자 문제를 해결합니다.
ms.openlocfilehash: 4732cf68624b824a452455fc779b22ae7eb32d56
ms.sourcegitcommit: ca2230a981a1e3c03437d1ecb8727d66ad6967f9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2021
ms.locfileid: "51760567"
---
# <a name="use-call-analytics-to-troubleshoot-poor-call-quality"></a>통화 분석을 사용하여 통화 품질 불량 문제 해결

이 문서에서는 통화 분석을 사용하여 Teams 관리자 또는 Teams 통신 지원 전문가 또는 엔지니어인 경우 개별 사용자의 Microsoft Teams 통화 또는 모임 품질이 좋지 않은 문제를 해결하는 방법을 설명합니다.

## <a name="call-analytics-permissions"></a>통화 분석 사용 권한

이 문서에서는 호출 분석을 이미 설정했다고 가정합니다. 그렇지 않은 경우 [Teams에 대한 호출 분석 설정 을 읽습니다.](set-up-call-analytics.md)

## <a name="introduction-to-call-analytics"></a>호출 분석 소개

통화 분석은 Office 365 계정의 각 사용자에 대한 Teams 호출 및 모임에 대한 자세한 정보를 보여줍니다. 여기에는 디바이스, 네트워크, 연결 및 통화 품질에 대한 정보가 포함됩니다(이러한 중 어느 것이 통화 또는 모임 품질이 좋지 않은 요인일 수 있습니다). 건물, 사이트 및 테넌트 정보를 업로드하는 경우 각 통화 및 모임에 대해 이 정보도 표시됩니다. 통화 분석을 사용하여 사용자가 통화 또는 모임 환경이 좋지 않은 이유를 알아 내는 데 도움이 됩니다.

통화 분석은 한 참가자에서 두 번째 참가자로의 통화 또는 모임의 각 다리를 보여줍니다. 이러한 세부 정보를 분석하여 Teams 관리자는 문제 영역을 격리하고 품질이 좋지 않은 근본 원인을 식별할 수 있습니다.

Teams 관리자는 각 사용자에 대한 모든 호출 분석 데이터에 대한 모든 액세스 권한을 얻습니다. 또한 직원을 지원하기 위해 Azure Active Directory 역할을 할당할 수 있습니다. 이러한 역할에 대한 자세한 내용은 지원 및 지원 데스크 직원에 대한 권한 부여 [를 읽어보아야 합니다.](set-up-call-analytics.md#give-permission-to-support-and-helpdesk-staff) 아래에서 각 [Teams 지원](#what-does-each-teams-support-role-do) 역할의 작업을 놓치지 마세요.

## <a name="where-to-find-per-user-call-analytics"></a>사용자당 호출 분석을 찾을 수 있는 위치

사용자의 모든 통화 정보와 데이터를 표시하려면 Teams 관리 [센터 으로 이동하세요.](https://admin.teams.microsoft.com) 사용자 **아래에서** 사용자를 선택한 다음 사용자의 **프로필 페이지에서** & 모임 탭을 니다. 여기서는 지난 30일 동안 해당 사용자의 모든 통화 및 모임을 찾을 수 있습니다.

![모든 분석 사용자 데이터의 스크린샷](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image1.png)

자세한 미디어 및 네트워킹 통계를 비롯한 특정 세션에 대한 추가 정보를 얻려면 세션을 클릭하여 세부 정보를 확인합니다.

![통화 분석 사용자 세션 데이터의 스크린샷](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image2.png)

## <a name="what-does-each-teams-support-role-do"></a>각 Teams 지원 역할은 어떻게 하나요?

Teams **통신 지원 전문가(계층** 1 지원)는 기본 통화 품질 문제를 처리합니다. 모임과 관련한 문제를 조사하지 않습니다. 대신, 관련 정보를 수집한 다음 통신 지원 엔지니어로 에스컬레이터합니다.

Teams **통신 지원 엔지니어(계층** 2 지원)는 Teams 통신 지원 전문가로부터 숨겨져 있는 자세한 통화 로그의 정보를 볼 수 있습니다. 아래 표에는 각 Teams 통신 지원 역할에 사용할 수 있는 정보가 나열됩니다.

다음 표에서는 각 통신 지원 역할에 사용할 수 있는 사용자당 정보를 제공합니다.

|활동|정보|통신의 정보<br>지원 *전문가가*|통신의 정보<br>지원 *엔지니어가*|
|---|---|---|---|
|**통화**|발신자 이름|에이전트가 검색한 사용자의 이름만입니다.|사용자 이름입니다.|
||받는 사람 이름|내부 사용자 또는 외부 사용자로 표시|받는 사람 이름입니다.|
||호출자 전화 번호|마지막 세 자리를 제외한 전체 전화 번호는 스테리스크 기호로 난시됩니다. 예를 들어 15552823 \* \* \* .|마지막 세 자리를 제외한 전체 전화 번호는 스테리스크 기호로 난시됩니다. 예를 들어 15552823 \* \* \* .|
||받는 사람 전화 번호|마지막 세 자리를 제외한 전체 전화 번호는 스테리스크 기호로 난시됩니다. 예를 들어 15552823 \* \* \* .|마지막 세 자리를 제외한 전체 전화 번호는 스테리스크 기호로 난시됩니다. 예를 들어 15552823 \* \* \* .|
||**통화 세부 정보** \> **고급** 탭|정보가 표시되지 않습니다.|디바이스 이름, IP 주소, 서브넷 매핑 등 표시된 모든 세부 정보입니다.|
||**통화 세부 정보** \> **고급** \> **디버그 탭**|정보가 표시되지 않습니다.|DNS 접미사 및 SSID와 같은 표시된 모든 세부 정보입니다.|
|**모임**|참가자 이름|에이전트가 검색한 사용자의 이름만입니다. 내부 사용자 또는 외부 사용자로 식별된 다른 참가자.|표시된 모든 이름입니다.|
||참가자 수|참가자 수입니다.|참가자 수입니다.|
||세션 세부 정보|예외와 함께 표시된 세션 세부 정보입니다. 에이전트가 검색한 사용자의 이름만 표시됩니다. 내부 사용자 또는 외부 사용자로 식별된 다른 참가자. 마지막으로 세 자릿수의 전화 번호가 스테리스크 기호로 난시됩니다.|표시된 세션 세부 정보입니다. 표시된 사용자 이름 및 세션 세부 정보입니다. 마지막으로 세 자릿수의 전화 번호가 스테리스크 기호로 난시됩니다.|
||||

## <a name="troubleshoot-user-call-quality-problems"></a>사용자 통화 품질 문제 해결

1. Teams 관리 센터() 를 열고 Teams 통신 지원 또는 Teams 관리자 자격 증명으로 <https://admin.teams.microsoft.com> 로그인합니다.

2. 대시보드 **의** **사용자** 검색에서 문제 해결하려는 사용자의 이름 또는 SIP 주소를 입력하거나 사용자  보기를 선택하여 사용자 목록을 볼 수 있습니다.

3. 목록에서 사용자를 선택합니다.

4. 통화 **기록을** 선택한 다음 문제 해결하려는 통화 또는 모임을 선택합니다.

5. 고급 **탭을** 선택한 다음, 통화 품질 또는 연결 문제가 나쁨을 나타내는 노란색 및 빨간색 항목을 확인합니다.

   각 통화 또는 모임에 대한 세션 세부 정보에서 사소한 문제가 노란색으로 표시됩니다. 노란색이면 정상 범위에서 멀어 문제의 원인이 될 수 있지만 문제의 주된 원인일 가능성은 낮습니다. 빨간색이면 중요한 문제로, 이 세션의 통화 품질이 좋지 않은 주요 원인일 수 있습니다.

드물게 오디오 세션에 대해 경험 품질 데이터가 수신되지 않는 경우가 있습니다. 종종 호출이 끊어지거나 클라이언트와의 연결이 종료될 때 발생하기도 합니다. 이 경우 세션 등급을 사용할 **수 없습니다.**

QoE(환경 품질) 데이터가 있는 오디오 세션의 경우 다음 표에서는 세션을 가난한 것으로 한정하는 주요 문제를 **설명합니다.**

|문제|영역|설명|
|---|---|---|
|통화 설정|세션|오류 코드 Ms-diag 20-29는 호출 설정이 실패했다고 나타냅니다. 사용자가 통화 또는 모임에 참가할 수 없습니다.|
|오디오 네트워크 분류 불량 호출|세션|네트워크 품질 문제(예: 패킷 손실, 지터, NMOS 성능 저하, RTT 또는 은닉된 비율)가 발생했습니다.|
|디바이스가 작동하지 않습니다.|장치|디바이스가 제대로 작동하지 않습니다. 디바이스가 작동하지 않는 비율은: <p> DeviceRenderNotFunctioningEventRatio >= 0.005 <br>  DeviceCaptureNotFunctioningEventRatio >= 0.005|
||||

## <a name="related-topics"></a>관련 항목

[사용자당 통화 분석 설정](set-up-call-analytics.md)
