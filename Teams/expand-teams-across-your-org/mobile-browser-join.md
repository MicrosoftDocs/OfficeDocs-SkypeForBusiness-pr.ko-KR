---
title: 모바일 브라우저에서 가상 Teams 대한 조인 환경 관리
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
description: 모바일 브라우저에서 가상 Teams 조인 경험에 대해 자세히 알아보습니다.
ms.openlocfilehash: 83bbe6e2db29a1ed43bbe1646f8545072dac7d2d
ms.sourcegitcommit: 2e8daa3511cd198b3e0d43b153dd37a59cb21692
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/11/2022
ms.locfileid: "62763712"
---
# <a name="manage-the-join-experience-for-teams-virtual-visits-on-mobile-browsers"></a>모바일 브라우저에서 가상 Teams 대한 조인 환경 관리

Microsoft Teams 앱을 다운로드하지 않고도 사람들이 모바일 장치에서 약속에 쉽게 참여할 수 Teams. 보다 원활한 환경을 위해 참석자들은 모바일 브라우저에서 의료 방문, 재무 상담, 교육자 사무실 시간 등의 약속에 참가할 수 있습니다. 참석자들은 Android 또는 iOS 모바일 Teams 모바일 앱을 설치할 필요가 없습니다.

모바일 브라우저 조인을 통해 참석자가 모바일 장치에서 약속에 조인하면 모바일 브라우저를 다운로드하라는 메시지가 Teams. 대신, Teams 브라우저에서 열리며, 여기서 참석자도 지금 참가를 선택하여 **참가할 수** 있습니다. 이 기능을 사용하면 참석자 모바일 Teams 이미 설치되어 있는 경우 앱에서 Teams 브라우저에서 열립니다.

현재 모바일 브라우저 조인은 다음을 통해 예약된 약속에 사용할 수 있습니다.

- [Bookings 앱](https://support.microsoft.com/office/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?ui=en-us&rs=en-us&ad=us#PickTab=Bookings)
- Microsoft Teams EHR(전자 상태 레코드) 커넥터

  - [Cerner EHR과의 통합](healthcare/ehr-admin-cerner.md)
  - [Epic EHR과의 통합](healthcare/ehr-admin.md)

## <a name="set-up-mobile-browser-join"></a>모바일 브라우저 조인 설정

### <a name="appointments-scheduled-through-the-bookings-app"></a>Bookings 앱을 통해 예약된 약속

조직의 스케줄러는 특정 약속 유형 및 Bookings 앱에서 개별 약속에 대해 이 기능을 켜면 됩니다.

이 기능이 켜진 후 참석자에 보낸 확인 전자 메일 또는 SMS 텍스트에는 모바일 브라우저에서 모임을 여는 모임 Teams 링크가 포함되어 있습니다. Android 모바일 장치에서는 Chrome에서 Teams 열립니다. iOS 모바일 디바이스에서 Safari에서 Teams 열립니다.

#### <a name="turn-on-mobile-browser-join-for-an-appointment-type"></a>약속 유형에 대한 모바일 브라우저 조인 설정

Bookings에서  >  설정 **Appointment** 형식으로 이동하고 약속 유형을 선택한 [다음 참석자](https://support.microsoft.com/office/create-an-appointment-type-810eac77-6a65-4dc8-964d-c00eadf43887)들이 모바일 브라우저에서 참가하도록 허용을 **켜십시오**. 이렇게 하면 모바일 브라우저가 이 유형의 모든 약속에 조인할 수 있습니다.

:::image type="content" source="../media/mobile-browser-join-bookings-appointment-type.png" alt-text="예약 앱에서 약속 유형에 대한 모바일 브라우저 설정에서 참석자 참가 허용 스크린샷":::

#### <a name="turn-on-mobile-browser-join-for-an-individual-appointment"></a>개별 약속에 대한 모바일 브라우저 조인 설정

예약에서 새 예약을 선택한 **다음 참석자** 들이 모바일 브라우저에서 참가하도록 허용을 **켜십시오**.

:::image type="content" source="../media/mobile-browser-join-bookings-form.png" alt-text="Bookings 앱의 새 예약 양식의 모바일 브라우저 설정에서 참석자 참가 허용 스크린샷":::

### <a name="appointments-scheduled-through-the-teams-ehr-connector"></a>EHR 커넥터를 통해 예약된 Teams 약속

사용자 또는 직원이 설정할 필요가 없습니다!

**Cerner EHR** 과의 통합: Teams EHR 커넥터는 모바일을 통해 가상 약속에 참가하는 환자를 지원합니다. 약속 시 환자는 SMS 문자 메시지의 링크를 탭하여 참가할 수 있습니다. 환자가 원하는 브라우저를 선택한 다음 해당 Teams 열립니다.

**Epic EHR** 과의 통합: Teams EHR 커넥터는 MyChart 웹 및 모바일을 통해 가상 약속에 참가하는 환자를 지원합니다. 약속 시 환자는 가상 방문 시작 단추를 사용하여 MyChart에서 방문을 **시작할 수** 있습니다. 환자가 원하는 브라우저를 선택한 다음 해당 Teams 열립니다.

## <a name="supported-mobile-browsers"></a>지원되는 모바일 브라우저

현재 지원되는 모바일 브라우저는 다음과 같습니다. 달리 표시되지 않는 한 최신 버전과 이전 버전 2개가 지원됩니다.

|플랫폼  |Chrome |Safari |Edge(Chromium)|
|---------|:---:|:---:|:---:|
|Android   |   &#x2714;      |         |         |
|iOS    |         |  &#x2714; &sup1;       |         |
|macOS     |         |  &#x2714; &sup2;    |         |

&sup1; Safari의 iOS 앱은 마이크 및 스피커 디바이스를 선택할 수 없습니다. 예를 들어 디바이스 Bluetooth 있습니다. 이는 기본 디바이스 선택을 제어하는 운영 체제의 제한 사항입니다.

&sup2; Safari 14+ 및 macOS 11+는 발신 비디오 지원에 필요합니다.

## <a name="things-to-consider"></a>고려해야 할 일

방문을 수행하는 직원 구성원은 모바일 브라우저에서 참가하는 참석자와 Teams 데스크톱, 모바일 또는 웹 클라이언트에서 자신의 화면을 공유할 수 있습니다. 그러나 참석자들은 모바일 브라우저에서 자신의 화면을 공유할 수 없습니다.

> [!NOTE]
> 향후 릴리스에서 모임 참가 경험에 더 많은 기능을 Teams 있으므로 최신 정보를 다시 확인하세요. 다가오는 주요 기능을 Teams 로드맵을 Microsoft 365 [있습니다](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=microsoft%2Cteams).

## <a name="related-articles"></a>관련 기사

- [가상 Teams 및 Bookings 앱을 통해 가상 방문](bookings-virtual-visits.md)
- [예약 약속 유형 만들기](https://support.microsoft.com/office/create-an-appointment-type-810eac77-6a65-4dc8-964d-c00eadf43887)
- [참석자로 Bookings 약속 참가](https://support.microsoft.com/office/join-a-bookings-appointment-as-an-attendee-95cea12d-2220-421f-a663-6efb20913c7f)
- [가상 Teams - Cerner EHR에 통합](healthcare/ehr-admin-cerner.md)
- [가상 Teams - Epic EHR에 통합](healthcare/ehr-admin.md)
