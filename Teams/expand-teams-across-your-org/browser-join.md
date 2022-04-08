---
title: 브라우저에서 Teams 가상 방문에 대한 조인 환경 관리
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
ms.reviewer: hafarmer
description: 브라우저에서 가상 방문 Teams 조인 환경에 대해 알아봅니다.
ms.openlocfilehash: 276e33b16972f0543566014adf264fd12e45c4ae
ms.sourcegitcommit: 1e8cff687b12348d4ecc538084ab57bbba23b523
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/07/2022
ms.locfileid: "64703751"
---
# <a name="manage-the-join-experience-for-teams-virtual-visits-on-browsers"></a>브라우저에서 Teams 가상 방문에 대한 조인 환경 관리

Microsoft Teams 사용하면 사용자가 Teams 다운로드하지 않고도 가상 약속에 쉽게 가입할 수 있습니다. 보다 원활한 환경을 위해 참석자는 데스크톱 또는 모바일 브라우저에서 의료 방문 및 재무 상담과 같은 약속에 참여할 수 있습니다. 참석자는 디바이스에 Teams 앱을 설치할 필요가 없습니다.

브라우저 조인을 사용하면 참석자가 약속에 참가할 때 Teams 다운로드하라는 메시지가 표시되지 않습니다. 대신 Teams 브라우저에서 열립니다. 그러면 참석자가 **지금 참가** 를 선택하여 참가할 수 있습니다. 이 기능을 사용하면 Teams 디바이스에 이미 설치된 경우 Teams 앱이 아닌 브라우저에서 열립니다.

현재 브라우저 조인은 다음을 통해 예약된 약속에 사용할 수 있습니다.

- [Bookings 앱](https://support.microsoft.com/office/what-is-bookings-42d4e852-8e99-4d8f-9b70-d7fc93973cb5)
- Microsoft Teams EHR(Electronic Health Record) 커넥터

  - [Cerner EHR](healthcare/ehr-admin-cerner.md)과 통합
  - [Epic EHR](healthcare/ehr-admin.md)과 통합

## <a name="set-up-browser-join"></a>브라우저 조인 설정

### <a name="appointments-scheduled-through-the-bookings-app"></a>Bookings 앱을 통해 예약된 약속

조직의 스케줄러는 특정 약속 유형 및 Bookings 앱의 개별 약속에 대해 이 기능을 설정할 수 있습니다.

이 기능이 켜지면 참석자에게 전송되는 확인 전자 메일 또는 SMS 텍스트에 데스크톱 또는 모바일 브라우저에서 Teams 열리는 모임 참가 링크가 포함됩니다. 지원되는 브라우저 목록은 [지원되는 브라우저를 참조하세요](#supported-browsers).

#### <a name="turn-on-browser-join-for-an-appointment-type"></a>약속 유형에 대한 브라우저 조인 켜기

Bookings **설정** > **사용 유형** 으로 이동하여 [약속 유형을](https://support.microsoft.com/office/create-an-appointment-type-810eac77-6a65-4dc8-964d-c00eadf43887) 선택한 다음 **참석자가 브라우저에서 참가할 수 있도록 허용** 을 켭니다. 이렇게 하면 이 유형의 모든 약속에 대한 브라우저 조인이 가능합니다.

:::image type="content" source="../media/browser-join-bookings-appointment-type.png" alt-text="Bookings 앱의 약속 유형에 대한 브라우저 설정에서 참석자가 참가할 수 있도록 허용하는 스크린샷":::

#### <a name="turn-on-browser-join-for-an-individual-appointment"></a>개별 약속에 대한 브라우저 조인 켜기

Bookings **새 예약** 을 선택한 다음 참석자가 **브라우저에서 참가할 수 있도록 허용을** 켭니다.

:::image type="content" source="../media/browser-join-bookings-form.png" alt-text="Bookings 앱의 새 예약 양식에 있는 브라우저 설정에서 참석자가 참가할 수 있도록 허용하는 스크린샷":::

### <a name="appointments-scheduled-through-the-teams-ehr-connector"></a>Teams EHR 커넥터를 통해 예약된 약속

사용자 또는 직원이 설치할 필요가 없습니다!

**Cerner EHR과의 통합**: Teams EHR 커넥터는 SMS 문자 메시지의 링크를 통해 가상 약속에 가입하는 환자를 지원합니다. 약속 시 환자는 SMS 문자 메시지의 링크를 탭하여 참가할 수 있으며 브라우저에서 Teams 열립니다.

**Epic EHR과의 통합**: Teams EHR 커넥터는 MyChart 웹 및 모바일을 통해 가상 약속에 가입하는 환자를 지원합니다. 약속 시 환자는 가상 방문 시작 단추를 사용하여 MyChart에서 **방문을** 시작할 수 있으며 브라우저에서 Teams 열립니다.

## <a name="supported-browsers"></a>지원되는 브라우저

현재 지원되는 브라우저는 다음과 같습니다. 달리 명시되지 않는 한 최신 버전과 두 개의 이전 버전을 지원합니다.

|플랫폼  |크롬 |사파리 |Edge(Chromium)|
|---------|:---|:---|:---:|
|Android   | &#x2714; &sup1;      |         |         |
|iOS    |         | &#x2714; &sup1; &sup2; |         |
|macOS     | &#x2714; | &#x2714;|         |
|Windows    | &#x2714; |   | &#x2714; |
|Ubuntu/Linux     | &#x2714;         |     |         |

&sup1; 나가는 화면 공유는 iOS 또는 Android에서 지원되지 않습니다.

&sup2; Safari의 iOS 앱은 마이크 및 스피커 디바이스를 선택할 수 없습니다. 예를 들어 디바이스를 Bluetooth. 이는 기본 디바이스 선택을 제어하는 운영 체제의 제한 사항입니다.

## <a name="things-to-consider"></a>고려해야 할 사항

방문을 수행하는 직원은 데스크톱 또는 모바일 브라우저에서 참가하는 참석자와 Teams 데스크톱, 모바일 또는 웹 클라이언트에서 화면을 공유할 수 있습니다. 그러나 참석자는 데스크톱 또는 모바일 브라우저에서 화면을 공유할 수 없습니다.

## <a name="related-articles"></a>관련 기사

- [Teams 및 Bookings 앱을 사용하여 가상 방문](bookings-virtual-visits.md)
- [Bookings 약속 유형 만들기](https://support.microsoft.com/office/create-an-appointment-type-810eac77-6a65-4dc8-964d-c00eadf43887)
- [참석자로 Bookings 약속 참가](https://support.microsoft.com/office/join-a-bookings-appointment-as-an-attendee-95cea12d-2220-421f-a663-6efb20913c7f)
- [Teams 가상 방문 - Cerner EHR에 통합](healthcare/ehr-admin-cerner.md)
- [Teams 가상 방문 - Epic EHR에 통합](healthcare/ehr-admin.md)
