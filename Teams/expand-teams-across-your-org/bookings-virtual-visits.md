---
title: Microsoft Teams 및 Bookings 앱을 통한 가상 약속
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
description: Teams Bookings 앱을 사용하여 가상 약속을 예약, 관리 및 수행하는 방법을 알아봅니다.
ms.openlocfilehash: a89eaa242cd62238d4e5c6c9d7a88f3a2e9ac62c
ms.sourcegitcommit: 39fc58109da6b4628ffb658f2c6b94099e0ab604
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/15/2022
ms.locfileid: "66103385"
---
# <a name="virtual-appointments-with-microsoft-teams-and-the-bookings-app"></a>Microsoft Teams 및 Bookings 앱을 통한 가상 약속

## <a name="overview"></a>개요

Microsoft Teams [Bookings 앱](https://support.microsoft.com/office/what-is-bookings-42d4e852-8e99-4d8f-9b70-d7fc93973cb5)은 조직에서 직원과 참석자를 위한 가상 약속을 예약하고 관리하는 간단한 방법을 제공합니다. 의료 방문, 재무 상담, 인터뷰, 고객 지원, 가상 피팅 및 상담, 교육 사무실 시간 등과 같은 약속을 예약하는 데 사용합니다.

Bookings 앱을 사용하면 모든 조직의 복잡한 일정 요구를 쉽게 관리할 수 있습니다. 스케줄러는 한 번의 경험으로 여러 부서 및 직원 일정을 관리할 수 있을 뿐만 아니라 내부 및 외부 참석자들과의 커뮤니케이션도 관리할 수 있습니다.

가상 약속은 강력한 비디오 회의 기능을 제공하는 Microsoft Teams 회의를 통해 진행됩니다. 예를 들어 의사는 화면을 공유하고 환자와 테스트 결과를 검토할 수 있습니다. 또는 은행 관리자가 문서에 전자 서명을 요청하여 원격으로 거래를 종료할 수 있습니다.

각 가상 약속에는 전자 메일로 참석자에게 전송되는 Teams 모임 링크가 포함되어 있습니다. 이 링크는 웹 브라우저 또는 모든 디바이스의 Teams 쉽게 참가할 수 있습니다. 자동화된 이메일 미리 알림은 노쇼를 줄이고 고객 및 클라이언트 참여를 향상시키는 데 도움이 됩니다.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4TQop]

Bookings를 사용하면 업계에 맞는 환경을 얻을 수 있습니다. 조직에서 사용할 수 있는 방법에 대한 몇 가지 예는 다음과 같습니다.

|산업 | 예제 |
|---------|---------|
|금융 서비스    |  원격 판매 및 서비스에 대한 가상 약속<br/>은행 관계 관리자, 재무 고문 및 클레임 조정자에 대한 약속을 예약하고 관리하여 효율성과 편의성을 높이기 위해 고객에게 서비스를 제공합니다.  |
|소매   | 가상 피팅 및 상담 <br/>영업 담당자, 제품 전문가 및 디자인 컨설턴트의 약속을 예약하고 관리하여 고객과 가상 피팅 및 상담을 수행합니다.   |
|의료   |  환자 치료를 위한 가상 약속 <br/>의료 팀 구성원이 환자 또는 다른 의료 제공자와 만나 의료 서비스에 대해 논의할 약속을 예약하고 관리합니다.   |

이 문서에서는 Teams Bookings 앱을 사용하여 가상 약속을 예약, 관리 및 수행하는 방법에 대한 개요를 제공합니다.

## <a name="before-you-get-started"></a>시작하기 전

관리자인 경우 [Teams Bookings 앱 관리를](../bookings-app-admin.md) 참조하여 Teams Bookings 앱을 사용하기 위한 필수 구성 요소, 조직의 Bookings에 대한 액세스를 제어하는 방법, 권장 정책 및 관리자 설정에 대해 알아보세요.

조직의 스케줄러만 Teams Bookings 앱을 설치해야 합니다. 가상 약속을 수행하거나 참여하는 직원은 앱이 필요하지 않습니다. Teams 또는 Outlook 일정에서 또는 예약 확인 전자 메일의 모임 링크를 사용하여 약속에 참여합니다.

## <a name="set-up-a-new-booking-calendar"></a>새 예약 일정 설정

### <a name="create-the-booking-calendar"></a>예약 일정 만들기

Teams **Bookings** > **시작** 로 이동한 다음 새 **예약 일정을** 선택합니다. 양식을 작성하고 조직의 관련 비즈니스 유형을 선택해야 합니다.

:::image type="content" source="../media/bookings-virtual-visits-new-booking-calendar.png" alt-text="비즈니스 유형을 보여 주는 새 예약 일정 화면의 스크린샷":::

대규모 조직인 경우 참석자가 전체 조직이 아닌 특정 부서에서 예약 전자 메일을 받도록 하려면 둘 이상의 예약 일정을 만드는 것이 좋습니다.
자세한 내용은 [예약 일정 만들기를 참조하세요](https://support.microsoft.com//office/create-a-bookings-calendar-921cfd26-a24d-4aca-9004-561594112148).

> [!NOTE]
> Bookings 앱에서 처음 수행되지 않거나 기존 예약 일정에서 작업하려는 경우 Bookings에서 조직 이름 옆에 있는 드롭다운 화살표를 선택한 다음 **기존 예약 일정을** 선택합니다. 여기에서 원하는 항목을 검색할 수 있습니다.

### <a name="add-staff"></a>직원 추가

예약 일정에서 **추가 옵션**(...) > **설정** 이동한 다음, **직원을** 선택합니다. 직원 구성원을 추가하고 추가한 각 사람에게 역할을 할당합니다. 예약 일정에 최대 100명의 직원을 추가할 수 있습니다.

Bookings 앱은 Outlook 통합됩니다. 직원을 추가하면 해당 사용자의 일정 가용성을 확인하고 예약을 예약할 수 있습니다. 자세한 내용은 [직원 추가 및 Bookings 일정 보기를](https://support.microsoft.com/office/add-staff-and-view-a-bookings-calendar-6c579f61-8adb-4514-9458-021de2023fa0) 참조하세요.  

### <a name="create-appointment-types"></a>약속 유형 만들기

조직에서 제공하는 서비스를 나타내고 예약 환경을 조정하기 위해 특정 약속 유형을 만듭니다. 그런 다음 스케줄러는 약속 유형을 사용하여 약속을 예약할 수 있습니다.

예약 일정에서 **추가 옵션**(...) > **설정** 이동하여 **약속 유형을** 선택한 다음 **약속 유형 추가** 를 선택합니다. 계정 개설, 처방전 갱신, 대출 상담, 세금 준비&mdash;및 원하는 기타 정보 및 설정과 같은 이름을&mdash;입력합니다.

추가하는 정보는 이 유형의 약속을 예약할 때마다 참석자에게 전송되는 전자 메일 확인에 포함됩니다. Teams 다운로드하지 않고도 참석자가 [데스크톱 또는 모바일 브라우저에서 참가](browser-join.md)할 수 있는지 여부와 같은 전자 메일 미리 알림 및 기타 옵션을 설정할 수 있습니다.

Bookings 관리자인 경우 이 약속 유형을 예약할 때마다 참석자가 작성할 수 있도록 최대 4개의 양식을 연결할 수 있습니다. 예를 들어 참석자가 약속에 참가하기 전에 등록 양식을 작성하도록 요구할 수 있습니다. 폼을 연결하려면 **양식 연결을** 선택합니다. 양식의 URL을 입력한 다음 **링크를 선택합니다.** 폼을 처음 연결하는 경우 양식을 저장할 Microsoft 365 그룹을 만들라는 메시지가 표시됩니다. **그룹 만들기** 를 선택하여 그룹을 만듭니다. 예약 일정에 대해 한 번만 수행하면 됩니다.)

양식으로 작업할 때 다음 사항에 유의하세요.

- 약속 유형에 이미 연결된 양식을 변경하려면 약속 유형 또는 Microsoft 365 그룹 [https://forms.office.com](https://forms.office.com)내에서 양식을 선택합니다.
- 모든 참석자가 동일한 조직에서 온 경우 [파일 업로드 질문이](https://support.microsoft.com/office/add-questions-that-allow-for-file-uploads-6a75a658-c02b-450e-b119-d068f3cba4cf) 포함된 양식에 파일 업로드가 지원됩니다.

스케줄러가 약속 유형을 사용하여 약속을 예약하는 경우 양식을 포함하거나 제거하거나 약속 유형에 연결된 다른 양식을 추가하도록 선택할 수 있습니다. 참석자는 약속에 참가하기 전에 양식을 작성해야 합니다.

> [!NOTE]
> 의료 기록 연속성 또는 보존 목적에 필요한 예약 또는 가상 약속 서비스의 일부로 Forms에서 환자가 제공하는 모든 정보는 해당 레코드에서 직접 다운로드, 복사 및/또는 공지해야 합니다. 이 서비스는 법적 의료 기록 또는 지정된 레코드 집합을 구성하지 않습니다.

자세한 내용은 [약속 유형 만들기를](https://support.microsoft.com/office/create-an-appointment-type-810eac77-6a65-4dc8-964d-c00eadf43887) 참조하세요.

## <a name="schedule-an-appointment"></a>약속 예약

예약 일정에서 **새 예약** 을 선택합니다. 약속 유형을 선택한 다음 관련 정보를 입력합니다.

여기에는 참석자 연락처 정보, 서비스를 제공할 직원 구성원, 직원만 볼 수 있는 내부 메모, 전자 메일 미리 알림 및 참석자가 모바일 브라우저에서 참가할 수 있는지 여부가 포함됩니다. 양식이 약속 유형에 연결된 경우 양식을 포함하거나 제거하거나 다른 연결된 양식을 추가하도록 선택할 수 있습니다.

참석자에게 보낸 전자 메일 확인에는 일정에 가상 약속을 추가할 수 있도록 모임 링크와 첨부 파일이 포함됩니다. 또한 직원은 전자 메일 확인 및 모임 초대를 받습니다. 약속에 양식이 포함된 경우 Bookings 관리자 및 스케줄러는 약속 전에 참석자가 양식을 완료했는지 확인하고 참석자의 응답을 볼 수 있습니다.

자세한 내용은 [Teams Bookings 앱에서 예약 예약을 참조하세요](https://support.microsoft.com/office/schedule-a-booking-in-the-teams-bookings-app-e275049d-0d0f-4161-8526-461a9f29439f).

## <a name="conduct-an-appointment"></a>약속 수행

Teams 또는 Outlook 일정에서 예약으로 이동한 다음 **참가** 또는 Teams 모임 링크를 선택합니다. 오디오 및 비디오 설정을 확인한 다음 지금 **참가** 를 선택합니다. 자세한 내용은 [예약 예약 수행을](https://support.microsoft.com/office/conduct-a-bookings-appointment-a86a4007-e26c-4909-9893-f7036e2747cd) 참조하세요.

## <a name="monitor-appointments-and-get-real-time-status-updates"></a>약속 모니터링 및 실시간 상태 업데이트 가져오기

Bookings의 [큐 보기](https://support.microsoft.com/office/queue-view-in-bookings-3eea2840-a1e0-4bcd-8e09-d3cf51c184d6) 는 직원에게 실시간으로 업데이트와 함께 하루 동안 모든 가상 약속을 모니터링할 수 있는 대시보드를 제공합니다. 큐를 보려면 Bookings의 **큐** 탭으로 이동합니다.

:::image type="content" source="../media/bookings-virtual-visits-queue.png" alt-text="Teams Bookings 앱의 큐 보기 스크린샷" lightbox="../media/bookings-virtual-visits-queue.png":::

큐에서 스케줄러는 새 예약을 추가하고, 관련 약속 세부 정보를 보고, 하루 종일 약속 상태를 볼 수 있습니다. 환자가 대기실에 조인하면 상태가 변경되고 대기 시간이 표시되고 추적됩니다. 변경 내용을 쉽게 식별할 수 있도록 색으로 구분된 업데이트로 보기가 자동으로 새로 고쳐집니다.

직원은 큐에서 직접 약속을 조인하고 관리할 수도 있습니다.

> [!NOTE]
> 현재 Bookings 앱은 예약 일정당 최대 100명의 직원을 추가할 수 있도록 지원합니다. Graph API를 사용하여 예약 일정에 직원을 설정하고 추가한 경우 이 제한이 적용되지 않을 수 있습니다. 이 시나리오에서는 **큐** 탭에서 직원이 100명 이상인 일정의 콘텐츠를 렌더링할 수 없습니다. 최적의 환경을 위해 예약 일정에 100명 이하의 직원을 추가하는 것이 좋습니다. 향후 릴리스에서 이러한 제한을 해결하기 위해 노력하고 있습니다.

## <a name="additional-capabilities-with-the-bookings-web-app"></a>Bookings 웹앱의 추가 기능

Bookings 웹앱은 추가 기능을 제공합니다. 예를 들어 직원이 약속을 예약할 수 있는 셀프 서비스 온라인 예약 페이지를 게시할 수 있습니다. Bookings 웹앱에 액세스하려면 **추가 옵션** (...) > **Bookings 웹앱 열기** 로 이동합니다.

자세한 내용은 [Microsoft Bookings](/microsoft-365/bookings/bookings-overview) 참조하세요.

## <a name="get-insight-into-virtual-appointments-usage"></a>가상 약속 사용에 대한 인사이트 가져오기

Microsoft Teams 관리 센터의 [가상 방문 사용 현황 보고서는](../teams-analytics-and-reports/virtual-visits-usage-report.md) 관리자에게 조직의 Teams 가상 약속 활동에 대한 개요를 제공합니다. 이 보고서는 Bookings 약속을 포함한 가상 약속에 대한 자세한 분석을 보여 줍니다.

로비 대기 시간 및 약속 기간과 같은 주요 메트릭을 볼 수 있습니다. 이 정보를 사용하여 사용량 추세에 대한 인사이트를 확보하여 더 나은 비즈니스 결과를 제공하기 위해 가상 약속을 최적화할 수 있습니다.

## <a name="related-articles"></a>관련 기사

- [모바일 브라우저에서 Teams 가상 약속에 대한 조인 환경 관리](browser-join.md)

- [가상 방문 사용 현황 보고서 Teams](../teams-analytics-and-reports/virtual-visits-usage-report.md)

- [의료 기관을 위한 Teams 시작](healthcare/teams-in-hc.md)

- [Teams 도움말 설명서의 예약 앱](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?#PickTab=Bookings)
