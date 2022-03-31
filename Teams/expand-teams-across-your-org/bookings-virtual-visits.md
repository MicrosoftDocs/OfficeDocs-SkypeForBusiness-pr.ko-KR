---
title: 가상 Microsoft Teams 및 Bookings 가상 방문
author: lanachin
ms.author: v-lanachin
manager: samanro
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: ''
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
- Microsoft Cloud for Retail
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- microsoftcloud-healthcare
- microsoftcloud-retail
- m365solution-healthcare
- m365solution-scenario
ms.reviewer: ''
description: 가상 방문을 예약, 관리 및 수행하는 방법에 대해 Bookings 앱을 사용하여 Teams.
ms.openlocfilehash: 0db414765a649192d96122ac69764fa279a8dac5
ms.sourcegitcommit: cbdc80c302e97d18a923ef57bb5d4b6cf7676d00
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/30/2022
ms.locfileid: "64556539"
---
# <a name="virtual-visits-with-microsoft-teams-and-the-bookings-app"></a>Microsoft Teams 및 Bookings 앱을 가상으로 방문

## <a name="overview"></a>개요

Bookings [앱을 Microsoft Teams](https://support.microsoft.com/office/what-is-bookings-42d4e852-8e99-4d8f-9b70-d7fc93973cb5) 조직에서 직원 및 참석자에 대한 가상 약속을 예약하고 관리할 수 있는 간단한 방법을 제공합니다. 의료 방문, 재무 상담, 인터뷰, 고객 지원, 가상 피팅 및 상담, 교육 사무실 시간 등의 약속을 예약하는 데 사용할 수 있습니다.

이 Bookings 앱을 사용하면 조직의 복잡한 일과일정 요구를 쉽게 관리할 수 있습니다. 스케줄러는 한 번의 경험으로 여러 부서 및 직원 일정을 관리할 수 있을 뿐만 아니라 내부 및 외부 참석자들과의 커뮤니케이션도 관리할 수 있습니다.

가상 약속은 강력한 Microsoft Teams 회의 기능을 제공하는 모임을 통해 개최됩니다. 예를 들어 의사는 화면을 공유하고 환자와 테스트 결과를 검토할 수 있습니다. 또는 은행 고문이 문서에 전자 서명을 요청할 수 있어 원격으로 트랜잭션을 닫을 수 있습니다.

각 가상 약속에는 Teams 웹 브라우저에서 또는 모든 장치에서 쉽게 참가할 수 있는 참석자에 전자 메일로 전송되는 Teams 링크가 포함됩니다. 자동화된 전자 메일 미리 알림은 노쇼를 줄이고 고객 및 클라이언트 참여를 향상시키는 데 도움이 됩니다.

이 Bookings 업계에 맞는 환경을 얻을 수 있습니다. 조직에서 사용할 수 있는 방법에 대한 몇 가지 예는 다음과 같습니다.

|산업 | 예제 |
|---------|---------|
|금융 서비스    |  원격 판매 및 서비스에 대한 가상 방문<br/>은행 관계 관리자, 재무 고문 및 클레임 조정자에 대한 약속을 예약하고 관리하여 고객의 효율성과 편의성을 높이기 위해 몇 가지 이름을 지정합니다.  |
|소매점   | 가상 피팅 및 상담 <br/>고객과 가상 피팅 및 상담을 수행하기 위해 영업 직원, 제품 전문가 및 디자인 컨설턴트의 약속을 예약하고 관리합니다.   |
|의료 서비스   |  환자 진료를 위한 가상 방문 <br/>의료진의 약속을 예약하고 관리하여 환자 또는 다른 의료 공급자와 만나 의료 서비스를 논의합니다.   |

이 문서에서는 가상 방문을 예약, 관리 및 수행하는 방법에 대한 개요를 Bookings 앱을 사용하여 Teams.

## <a name="before-you-get-started"></a>시작하기 전

관리자인 경우 Bookings 앱 Teams 앱 관리를 [](../bookings-app-admin.md) 참조하여 Bookings 앱 사용에 대한 Teams, 조직의 앱에 대한 액세스를 제어하는 Bookings 방법 및 권장 정책 및 관리자 설정에 대해 자세히 알아보는 방법을 참조하세요.

조직의 스케줄러만 앱에 Bookings 앱을 설치해야 Teams. 가상 약속을 수행하거나 참여하는 직원은 앱이 필요하지 않습니다. 해당 일정 또는 Teams Outlook 예약 확인 전자 메일에서 모임 링크를 사용하여 약속에 참가합니다.

## <a name="set-up-a-new-booking-calendar"></a>새 예약 일정 설정

### <a name="create-the-booking-calendar"></a>예약 일정 만들기

Teams 에서  >  Bookings 시작 일정을 **선택한 다음 새 예약 일정을 선택합니다**. 양식을 완료하고 조직의 관련 비즈니스 유형을 선택해야 합니다.

:::image type="content" source="../media/bookings-virtual-visits-new-booking-calendar.png" alt-text="비즈니스 유형을 보여주는 새 예약 일정 화면 스크린샷":::

대규모 조직인 경우 참석자들이 전체 조직이 아닌 특정 부서에서 예약 전자 메일을 받기를 원할 경우 두 개 이상의 예약 일정을 만드는 것이 고려됩니다.
자세한 내용은 일정 만들기를 [Bookings 참조하세요](https://support.microsoft.com//office/create-a-bookings-calendar-921cfd26-a24d-4aca-9004-561594112148).

> [!NOTE]
> 기존 예약 Bookings 처음이 아니면 기존 예약 일정에서 작업하려는 경우 Bookings 조직 이름 옆에 있는 드롭다운 화살표를 선택한 다음 기존 예약 일정을 **선택합니다**. 여기에서 원하는 것을 검색할 수 있습니다.

### <a name="add-staff"></a>직원 추가

예약 일정에서 추가 옵션(...)으로 이동 **하여** **> 설정 직원** 을 **선택합니다**. 직원 구성원을 추가하고 추가하는 각 사용자에게 역할을 할당합니다. 예약 일정에 직원을 최대 100명까지 추가할 수 있습니다.

Bookings 앱은 앱과 Outlook. 직원을 추가하면 해당 사람의 일정 가용성을 보고 예약을 예약할 수 있습니다. 자세한 내용은 직원 추가를 참조[하고 일정을 Bookings 참조하세요](https://support.microsoft.com/office/add-staff-and-view-a-bookings-calendar-6c579f61-8adb-4514-9458-021de2023fa0).  

### <a name="create-appointment-types"></a>약속 형식 만들기

조직에서 제공하는 서비스를 나타내고 예약 환경을 조정하기 위해 특정 약속 유형을 만드십시오. 그런 다음 스케줄러는 약속 유형을 사용하여 방문을 예약할 수 있습니다.

예약 일정에서 추가 옵션(...)으로 이동하여 > 설정 유형을 선택한 **다음 약속** **유형** 추가 **를 선택합니다**. 이름 예를&mdash; 들어 계정 열기, 처방전 갱신, 대출 상담, 세금&mdash; 준비 및 원하는 기타 정보 및 설정을 입력합니다.

추가하는 정보는 이 유형의 약속을 예약할 때마다 참석자에게 전송되는 전자 메일 확인에 포함됩니다. 전자 메일 미리 알림 및 참석자는 다운로드하지 않고도 모바일 브라우저에서 참가할 [](mobile-browser-join.md) 수 있는지 여부와 같은 기타 옵션을 Teams.

관리자의 Bookings 참석자에 대해 최대 4개의 양식을 연결하여 이 약속 유형이 예약될 때마다 작성할 수 있습니다. 예를 들어 참석자들이 방문에 참가하기 전에 등록 양식을 완료해야 할 수 있습니다. 폼을 연결하려면 폼 **링크를 선택하세요**. 폼의 URL을 입력한 다음 링크를 **선택하세요**. 폼을 처음 연결하는 경우 폼을 저장할 Microsoft 365 묻는 메시지가 표시됩니다. 그룹 **만들기를 선택하면** 그룹을 만들 수 있습니다. 예약 일정에 대해 한 번만 이 작업을 완료해야 합니다.

폼을 사용할 때 다음을 염두에 두어야 합니다.

- 약속 유형에 이미 연결된 폼을 변경하려면 약속 형식의 폼 또는 의 의 Microsoft 365 그룹 내에서 폼을 선택합니다[https://forms.office.com](https://forms.office.com).
- 모든 참석자들이 동일한 조직에 있는 [](https://support.microsoft.com/office/add-questions-that-allow-for-file-uploads-6a75a658-c02b-450e-b119-d068f3cba4cf) 경우 파일 업로드 질문을 포함하는 양식에 파일을 업로드하는 것이 지원됩니다.

스케줄러가 약속 유형을 사용하여 방문을 예약하면 폼을 포함하거나, 제거하거나, 약속 유형에 연결된 다른 폼을 추가할 수 있습니다. 참석자는 방문에 참가하기 전에 양식을 작성해야 합니다.

자세한 내용은 약속 유형 [만들기를 참조합니다](https://support.microsoft.com/office/create-an-appointment-type-810eac77-6a65-4dc8-964d-c00eadf43887).

## <a name="schedule-a-visit"></a>방문 예약

예약 일정에서 새 **예약을 선택합니다**. 약속 유형을 선택한 다음 관련 정보를 입력합니다.

여기에는 참석자 연락처 정보, 서비스를 제공하게 될 직원 구성원, 직원만 볼 수 있는 내부 노트, 전자 메일 미리 알림 및 참석자는 모바일 브라우저에서 참가할 수 있는지 여부가 포함됩니다. 폼이 약속 유형에 연결되어 있는 경우 폼을 포함하거나, 제거하거나, 다른 연결된 폼을 추가할 수 있습니다.

참석자에게 보낸 전자 메일 확인에는 모임 링크와 첨부 파일이 포함되어 일정에 가상 약속을 추가할 수 있습니다. 직원에게 전자 메일 확인 및 모임 초대도 받게 됩니다. 폼이 약속에 포함된 경우 Bookings 관리자 및 스케줄러가 방문하기 전에 참석자에 의해 양식이 완료된지 여부를 볼 수 있으며 참석자 응답을 볼 수 있습니다.

자세한 내용은 앱에서 예약 예약을 Teams Bookings [참조하세요](https://support.microsoft.com/office/schedule-a-booking-in-the-teams-bookings-app-e275049d-0d0f-4161-8526-461a9f29439f).

## <a name="conduct-a-visit"></a>방문 수행

일정 또는 Teams Outlook 예약으로 이동한 다음 참가 또는 모임 Teams 선택합니다. 오디오 및 비디오 설정을 확인한 다음 지금 **참가를 선택합니다**. 자세한 내용은 약속 수행을 [Bookings 참조합니다](https://support.microsoft.com/office/conduct-a-bookings-appointment-a86a4007-e26c-4909-9893-f7036e2747cd).

## <a name="monitor-visits-and-get-real-time-status-updates"></a>방문 모니터링 및 실시간 상태 업데이트 확인

큐 [보기는](https://support.microsoft.com/office/queue-view-in-bookings-3eea2840-a1e0-4bcd-8e09-d3cf51c184d6) Bookings 실시간으로 모든 가상 약속을 모니터링할 수 있는 대시보드를 직원에게 제공합니다. 큐를 표시하기 위해 큐 탭으로  Bookings.

:::image type="content" source="../media/bookings-virtual-visits-queue.png" alt-text="Bookings 앱의 큐 보기 스크린샷 Teams" lightbox="../media/bookings-virtual-visits-queue.png":::

큐에서 스케줄러는 새 예약을 추가하고, 관련 약속 세부 정보를 보고, 하루 동안 약속 상태를 볼 수 있습니다. 환자가 대기실에 참가하면 상태가 변경되고 대기 시간이 표시되고 추적됩니다. 변경 내용을 쉽게 식별할 수 있도록 색으로 코딩된 업데이트로 보기가 자동으로 새로 고쳐집니다.

직원이 큐에서 직접 약속에 참가하고 관리할 수 있습니다.

> [!NOTE]
> 현재 Bookings 앱은 예약 달력당 최대 100명까지 직원을 추가하는 기능을 지원하고 있습니다. 예약 일정에 Graph API를 사용하여 직원을 추가한 경우 이 제한이 적용되지 않을 수 있습니다. 이 시나리오에서는 **큐** 탭에서 직원이 100명을 넘는 일정에 대한 콘텐츠를 렌더링할 수 없습니다. 최적의 환경을 위해 예약 일정에 직원을 100명 이상 추가하는 것이 좋습니다. 향후 릴리스에서 이 제한 사항을 해결하기 위해 작업 중입니다.

## <a name="additional-capabilities-with-the-bookings-web-app"></a>웹앱을 Bookings 추가 기능

웹 Bookings 추가 기능을 제공합니다. 예를 들어 직원이 약속을 예약할 수 있는 셀프 서비스 온라인 예약 페이지를 게시할 수 있습니다. 웹 Bookings 액세스하기 위해 웹앱 열기 > 추가 옵션  (...)**으로 Bookings 합니다**.

자세한 내용은 다음을 [Microsoft Bookings](/microsoft-365/bookings/bookings-overview).

## <a name="get-insight-into-virtual-visits-usage"></a>Virtual Visits 사용량에 대한 인사이트 확인

관리자 [센터](../teams-analytics-and-reports/virtual-visits-usage-report.md)의 가상 방문 Microsoft Teams 보고서는 관리자에게 조직의 가상 방문 Teams 개요를 제공합니다. 보고서는 방문을 포함하여 가상 약속에 대한 Bookings 보여줍니다.

로비 대기 시간 및 방문 기간과 같은 주요 메트릭을 볼 수 있습니다. 이 정보를 사용하여 사용 추세를 파악하여 가상 방문을 최적화하여 더 나은 비즈니스 성과를 얻을 수 있습니다.

## <a name="related-articles"></a>관련 기사

- [모바일 브라우저에서 가상 Teams 조인 환경 관리](mobile-browser-join.md)

- [Teams 가상 방문 사용 현황 보고서](../teams-analytics-and-reports/virtual-visits-usage-report.md)

- [시작 조직에 Teams 사용](healthcare/teams-in-hc.md)

- [Bookings 도움말 설명서의 Teams 앱](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?#PickTab=Bookings)
