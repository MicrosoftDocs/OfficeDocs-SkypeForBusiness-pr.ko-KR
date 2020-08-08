---
title: IT 관리자를 위한 Microsoft 팀 교육에 대 한 자세한 정보
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: karsmith
description: 교육용 Microsoft Teams에 대한 정보를 관리하는 데 도움이 되는 IT 관리자 가이드입니다.
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e122071a9a4173250a78468126ed576d1e560607
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/06/2020
ms.locfileid: "46581499"
---
# <a name="insights-in-teams-for-education-for-it-admins"></a>IT 관리자를 위한 교육 팀에 대한 인사이트를 제공합니다.

교육용 Microsoft Teams의 인사이트를 통해 교육자는 디지털 참여, 할당 작업량, 등급, 커뮤니케이션 등에 대한 분석 데이터에 액세스할 수 있습니다.

Office 365 Education SKUs A1, A3, A5에서 통찰력이 활발합니다.

> [!NOTE]
> 교육자 여러분, 인사이트를 사용하는 방법을 [여기](https://support.microsoft.com/office/actionable-analytics-with-class-insights-in-teams-163add4f-997d-4a01-91de-2846fe4e99bc)에서 배워보세요.

## <a name="permissions"></a>사용 권한

교육자는 Teams 앱 모음의 앱으로 이동하여 인사이트를 검색하여 강의실 팀 내의 공개 채널에 통찰력을 추가할 수 있습니다.

- 학생은 라이선스로 식별되며 **Insights 탭에 액세스할 수 없습니다**(팀 소유자인 경우에도).
- 강사는 교직원용 라이선스에 의해 정의됩니다.
- 교육자는 인사이트 탭을 추가하려면 교원 자격증이 있어야 하며 학급 팀 소유자가 되어야 합니다. 탭에는 소유자가 아닌 모든 반 팀(팀 소유자가 아닌 교육자 포함)의 활동이 반영됩니다.

## <a name="compliance"></a>규정 준수

인사이트는 업계 최고의 규정 준수 의무를 가지고 있으며 Office 365 규정 준수 프레임워크 내에서 Tier-C 서비스로 분류됩니다.

> [!NOTE]
> [Microsoft 보안 센터](https://www.microsoft.com/trust-center)에 방문하여 Microsoft에서 데이터를 보호하는 방법에 대해 자세히 알아보세요.

## <a name="privacy"></a>개인 정보

인사이트를 통해 수집 및 표시되는 정보는 학생 및 자녀의 보안 및 기타 유사한 개인 정보 관련 규정에 대한 GDPR 및 FERPA(가족교육권 및 개인 정보에 관한 법률)를 포함하여 90개가 넘는 규정과 산업 표준을 충족합니다. IT 관리자는 학생별 기본으로 수집된 정보가 수업에서만 사용될 수 있다는 사실을 인지하여 강사가 수업 행동을 결정할 수 있도록 하는 것이 중요합니다. 이 정보는 수업 모임 참석, 메시지 게시, 친구 게시물에 응답, 과제 작업, 파일 편집 등과 같은 의미 있는 학습 활동을 위해 수집됩니다. 예를 들어 비공개 채팅 또는 Teams 로그인에 대한 정보는 표시되지 않습니다.

Microsoft의 목표는 강사가 참여를 이해하고 학생 교육 과정을 밝게 비추도록 돕는 것입니다. 이러한 수업 활동은 학생 수준의 작업에 초점을 맞출 수 있지만 Microsoft Teams에서는 이러한 작업에 할당한 긍정적 또는 부정적 가치가 없으며 기준에 따라 학생 개인을 판단할 수 없습니다. 예를 들어, 인사이트의 정보는 교육자에게 학생이 특정 기간 동안 도구에서 활동을 하지 않았거나 지난 주에 정시에 모든 과제를 완료했다고 알려줍니다. 학생과 학생의 가족 또는 보호자와 상호 작용하여 탐색된 활동 또는 비활동의 근본적인 원인을 파악하는 것은 강사의 책임입니다.

## <a name="data-collection"></a>데이터 수집

테넌트에 대해 교육 분석을 설정하면 인사이트에 대한 데이터를 수집합니다. 데이터는 교육 및 학습에 대한 실행 가능한 정보를 표시하기 위해 Teams 활동에서 수집됩니다.

기본적으로 Education Analytics는 **켜져** 있습니다.

현재 이 데이터는 다음과 같은 수업 팀의 학생과 강사 활동 영역에서 가져옵니다.

|팀 구성 요소  |수집된 데이터  |
|-----------------|------------------------|------------------------|
|과제 |과제 열기, 제출, 점수 지정 |
|채널 참여 |채널 방문, 게시물 작성, 게시물 응답 및 좋아요(채팅 콘텐츠 제외) |
|파일 |파일 업로드, 다운로드, 액세스, 수정, 댓글 달기, 공유(파일 콘텐츠 제외) |
|모임 |참석(모임 콘텐츠 제외) |

## <a name="data-location"></a>데이터 위치

유럽 기반 테넌트에 대한 통찰력 데이터는 유럽의 서버에 저장됩니다. 미국 기반 테넌트용 데이터는 미국의 서버에 저장됩니다. 인사이트를 사용하고 있으며 Office 365 테넌트가 유럽 또는 미국 외부 지역에 있는 경우, 데이터는 해당 지역에 저장됩니다.

## <a name="performance-and-reliability"></a>성능과 신뢰성

인사이트는 Teams 활동에서 수집된 대량의 데이터를 최적의 성능과 안정성으로 처리하도록 설계되었습니다.

데이터 수집 프로세스는 팀에 인사이트 탭 설치와 관계없이 별도의 서버에서 이루어집니다. 인사이트 탭 또는 개인 앱은 나머지 Teams 기능을 사용하는 교육자와 학생의 응용 프로그램 성능 또는 네트워크 대역폭에 영향을 미치지 않습니다.

> [!TIP]
> [여기](edu-remote-low-bandwidth.md)에서 대역폭이 낮으면 교육용 Teams를 사용하는 방법에 대해 읽어보세요.

## <a name="how-to-delete-your-data"></a>데이터 삭제 방법

교육 서비스는 수업 팀 컨텍스트에서 수행된 학생과 강사 활동을 저장합니다. 이 데이터는 통합된 데이터 집합으로 간주하므로 조직에서 학생 또는 강사 사용자 계정을 삭제한 후에도 서비스에서 자동으로 삭제되지 않습니다.

> [!NOTE]
> 데이터를 삭제하면 시간이 지남에 따라 수업 팀 참여를 분석하는 Insights의 기능에 부정적인 영향을 미칩니다.

- [여기](https://edusupport.microsoft.com/support)에서 지원 티켓을 공개합니다. 지원 티켓은 GDPR 삭제 DSR 작업 요청을 명확하게 명시해야 하며 삭제할 개체 ID를 포함해야 합니다. 삭제의 데이터 집합 또는 시간 창을 제한할 수 없습니다.
- 일단 제출되면 지원 티켓은 규정 준수 최소 보존 정책을 충족하기 위해 일주일 동안 큐에서 대기합니다. 이 기간에는 작업을 취소할 수 있습니다.
- 일주일 후에는 Education Analytics 팀에서 사용자 ID와 관련된 모든 데이터를 서비스에서 삭제하는 조치를 취합니다. Microsoft 지원에서는 ICM 티켓을 모니터링하여 삭제 프로세스가 완료되면 28일 이내에 공지합니다.

## <a name="turn-insights-off-and-on-using-school-data-sync-sds"></a>SDS(학교 데이터 동기화)를 사용하여 Insights를 켜고 끕니다.

SDS(학교 데이터 동기화)는 SIS(학생 정보 시스템) 데이터를 가져오고 Office 365와 동기화하는 프로세스를 자동화하는 데 도움이 됩니다.

인사이트를 사용하기 위해서는 SDS를 사용할 필요가 없습니다. 그러나 **설정** > **Education Analytics 관리**의 SDS 관리 센터에서 토글을 꺼서 언제든지 Education Analytics를 옵트아웃할 수 있습니다.

:::image type="content" source="media/class-insights-on-off.png" alt-text="인사이트를 사용하거나 사용하지 않도록 설정하는 켜기-끄기 스위치입니다.":::

기본적으로 교육 분석, 즉 정보 활용이 설정되어 있습니다. 분석에서 손을 떼면 인사이트 탭에 대해 수집된 모든 데이터가 삭제됩니다. 분석을 다시 설정하면 데이터를 다시 활성화할 때부터 수집하기 시작합니다.

자세한 정보: [교사를 위한 정보](https://support.microsoft.com/office/actionable-analytics-with-class-insights-in-teams-163add4f-997d-4a01-91de-2846fe4e99bc)
