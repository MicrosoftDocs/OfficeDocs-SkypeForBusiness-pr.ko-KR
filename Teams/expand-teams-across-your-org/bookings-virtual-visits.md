---
title: Microsoft Teams 및 Bookings 앱을 가상으로 방문
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
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- microsoftcloud-healthcare
- m365solution-healthcare
- m365solution-scenario
ms.reviewer: ''
description: 가상 방문을 예약, 관리 및 Teams 예약하는 방법에 대해 자세히 알아보십시오.
ms.openlocfilehash: a37a024e31c75bbedbdb36d9aa0d6acfd2af614c
ms.sourcegitcommit: 9364f4fdf3dcd5ab6805360ff913d4e2e7ca9cfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/17/2021
ms.locfileid: "59432460"
---
# <a name="virtual-visits-with-microsoft-teams-and-the-bookings-app"></a>Microsoft Teams 및 Bookings 앱을 가상으로 방문

## <a name="overview"></a>개요

이 [앱의 Bookings](https://support.microsoft.com/office/what-is-bookings-42d4e852-8e99-4d8f-9b70-d7fc93973cb5) Microsoft Teams 조직은 직원 및 참석자에 대한 가상 약속을 예약하고 관리할 수 있는 간단한 방법을 제공합니다. 이를 사용하여 의료 방문, 재무 상담, 인터뷰, 고객 지원, 가상 쇼핑 환경, 교육 사무실 시간 등의 가상 약속을 예약할 수 있습니다.

Bookings 앱을 사용하면 조직의 복잡한 예약 요구를 쉽게 관리할 수 있습니다. 스케줄러는 한 번의 경험으로 여러 부서 및 직원 일정을 관리할 수 있을 뿐만 아니라 내부 및 외부 참석자들과의 커뮤니케이션도 관리할 수 있습니다.

가상 방문은 강력한 Microsoft Teams 회의 기능을 제공하는 모임을 통해 개최됩니다. 예를 들어 의사는 화면을 공유하고 환자와 테스트 결과를 검토할 수 있습니다. 또는 은행 고문이 문서에 전자 서명을 요청할 수 있어 원격으로 트랜잭션을 닫을 수 있습니다.

각 가상 약속에는 Teams 웹 브라우저에서 또는 모든 장치에서 쉽게 참가할 수 있는 참석자에 Teams 모임 링크가 포함되어 있습니다. 자동화된 전자 메일 미리 알림은 노쇼를 줄이고 고객 및 클라이언트 참여를 향상시키는 데 도움이 됩니다.

Bookings를 사용하면 업계에 맞는 환경을 얻을 수 있습니다. 조직에서 사용할 수 있는 방법에 대한 몇 가지 예는 다음과 같습니다.

|산업 | 예제 |
|---------|---------|
|금융 서비스    |  원격 판매 및 서비스에 대한 가상 방문<br/>은행 관계 관리자, 재무 고문 및 클레임 조정자에 대한 가상 약속을 예약하고 관리하여 고객의 효율성과 편의성을 높이기 위해 몇 가지 이름을 지정합니다.  |
|의료 서비스   |  환자 진료를 위한 가상 방문 <br/>의료진이 환자 또는 기타 의료 공급자를 만나 의료 서비스를 논의하기 위해 가상 방문을 예약하고 관리합니다.   |
|소매점   | 가상 쇼핑 환경 <br/>고객과 가상 쇼핑 환경을 수행하기 위해 영업 직원, 제품 전문가 및 디자인 컨설턴트에 대한 약속을 예약하고 관리합니다.   |

이 문서에서는 가상 방문을 예약, 관리 및 Teams 예약에서 Bookings 앱을 사용하는 방법에 대한 개요를 제공합니다.

## <a name="before-you-get-started"></a>시작하기 전

관리자인 경우 Teams 예약 [](../bookings-app-admin.md) 앱 관리를 참조하여 Teams 조직의 예약에 대한 액세스를 제어하는 방법 및 권장 정책 및 관리자 설정에 대해 자세히 알아보십시오.

조직의 스케줄러만 예약자에 Bookings 앱을 설치해야 Teams. 가상 약속을 수행하거나 참여하는 직원은 앱이 필요하지 않습니다. 해당 일정 또는 Teams Outlook 예약 확인 전자 메일에서 모임 링크를 사용하여 약속에 참가합니다.

## <a name="set-up-a-new-booking-calendar"></a>새 예약 일정 설정

### <a name="create-the-booking-calendar"></a>예약 일정 만들기

Teams 시작 으로 이동한 다음 새 예약 일정  >   **을 선택합니다.** 양식을 완료하고 조직의 관련 비즈니스 유형을 선택해야 합니다.

:::image type="content" source="../media/bookings-virtual-visits-new-booking-calendar.png" alt-text="비즈니스 유형을 보여주는 새 예약 일정 화면 스크린샷":::

대규모 조직인 경우 참석자들이 전체 조직이 아닌 특정 부서에서 예약 전자 메일을 받기를 원할 경우 두 개 이상의 예약 일정을 만드는 것이 고려됩니다.
자세한 내용은 [예약 일정 만들기 를 참조하세요.](https://support.microsoft.com//office/create-a-bookings-calendar-921cfd26-a24d-4aca-9004-561594112148)

> [!NOTE]
> 예약 앱에서 처음 사용할 수 없는 경우 또는 기존 예약 일정에서 작업하려는 경우 Bookings에서 조직 이름 옆에 있는 드롭다운 화살표를 선택한 다음 기존 예약 일정 을 **선택합니다.** 여기에서 원하는 것을 검색할 수 있습니다.

### <a name="add-staff"></a>직원 추가

예약 일정에서 추가  옵션(...) > 설정 로 **이동한 다음, Staff 를** **선택합니다.** 직원 구성원을 추가하고 추가하는 각 사용자에게 역할을 할당합니다.

Bookings 앱은 앱과 Outlook. 직원을 추가하면 해당 사람의 일정 가용성을 보고 예약을 예약할 수 있습니다. 자세한 내용은 직원 [추가를 참조하고 Bookings 일정 을 참조하세요.](https://support.microsoft.com/office/add-staff-and-view-a-bookings-calendar-6c579f61-8adb-4514-9458-021de2023fa0)  

### <a name="create-appointment-types"></a>약속 형식 만들기

조직에서 제공하는 서비스를 나타내고 예약 환경을 조정하기 위해 특정 약속 유형을 만드십시오.

예약 일정에서 추가  옵션(...) > 약속 유형으로 이동한 다음 **새** 약속 유형 **을 선택합니다.** 계정 열기, 처방 갱신, 대출 상담, 세금 준비 및 원하는 기타 정보 및 설정과 같은 이름을 &mdash; &mdash; 입력합니다.

추가하는 정보 및 링크는 이 유형의 약속을 예약할 때마다 참석자에게 전송되는 전자 메일 확인에 포함됩니다. 참석자는 다운로드하지 않고도 모바일 브라우저에서 참가할 [](mobile-browser-join.md) 수 있는지 여부와 같은 전자 메일 미리 알림 및 기타 옵션을 설정할 Teams. 자세한 내용은 약속 유형 [만들기 를 참조합니다.](https://support.microsoft.com/office/create-an-appointment-type-810eac77-6a65-4dc8-964d-c00eadf43887)

## <a name="schedule-a-virtual-visit"></a>가상 방문 예약

예약 일정에서 새 **예약을 선택합니다.** 약속 유형을 선택한 다음 관련 정보를 입력합니다.

여기에는 참석자 연락처 정보, 서비스를 제공하게 될 직원 구성원, 직원만 볼 수 있는 내부 노트, 전자 메일 미리 알림 및 참석자는 모바일 브라우저에서 참가할 수 있는지 여부가 포함됩니다. 자세한 내용은 예약 앱에서 예약 예약을 Teams [참조하세요.](https://support.microsoft.com/office/schedule-a-booking-in-the-teams-bookings-app-e275049d-0d0f-4161-8526-461a9f29439f)

참석자에게 보낸 전자 메일 확인에는 모임 링크와 첨부 파일이 포함되어 일정에 가상 약속을 추가할 수 있습니다. 직원에게 전자 메일 확인 및 모임 초대도 받게 됩니다.

## <a name="conduct-a-virtual-visit"></a>가상 방문 수행

일정 또는 Teams 일정에서 Outlook 예약으로 이동한 다음 참가  또는 모임 Teams 선택합니다. 오디오 및 비디오 설정을 확인한 다음 지금 **참가를 선택합니다.** 자세한 내용은 예약 약속 [수행 을 참조합니다.](https://support.microsoft.com/office/conduct-a-bookings-appointment-a86a4007-e26c-4909-9893-f7036e2747cd)

## <a name="additional-capabilities-with-the-bookings-web-app"></a>Bookings 웹앱을 통해 추가 기능

Bookings 웹앱은 추가 기능을 제공합니다. 예를 들어 직원이 약속을 예약할 수 있는 셀프 서비스 온라인 예약 페이지를 게시할 수 있습니다. Bookings 웹앱에 액세스하기  위해 Bookings 웹앱 열기 > 옵션(...)으로 **이동하세요.**

자세한 내용은 [Microsoft Bookings 를 참조합니다.](/microsoft-365/bookings/bookings-overview)

## <a name="related-articles"></a>관련 문서

[모바일 브라우저에서 가상 Teams 조인 환경 관리](mobile-browser-join.md)

[의료 조직을 위한 Teams 시작](healthcare/teams-in-hc.md)

[도움말 설명서에서 Teams 앱 예약](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?#PickTab=Bookings)
