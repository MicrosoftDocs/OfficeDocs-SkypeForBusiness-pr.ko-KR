---
title: 클라이언트 버전 규칙
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientCVPolicyRuleEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.assetid: 6e7e94c2-1475-4334-b8da-716b24a4c255
ROBOTS: NOINDEX, NOFOLLOW
description: 클라이언트 버전 정책은 클라이언트 버전 규칙 집합으로 구성됩니다. 이러한 규칙은 사용자가 특정 클라이언트 및 클라이언트 버전으로 로그온을 시도할 때 수행해야 하는 작업을 정의합니다.
ms.openlocfilehash: 41e3e80e4cd836214f62fa40deab0a32077dfac1
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60835806"
---
# <a name="client-version-rule"></a>클라이언트 버전 규칙

클라이언트 버전 정책은 클라이언트 버전 규칙 집합으로 구성됩니다. 이러한 규칙은 사용자가 특정 클라이언트 및 클라이언트 버전으로 로그온을 시도할 때 수행해야 하는 작업을 정의합니다.

## <a name="tasks-you-can-perform"></a>수행할 수 있는 작업

**새 클라이언트 버전 구성** 또는 **클라이언트 버전 구성 편집** 페이지에서 다음 작업을 수행할 수 있습니다.

- 클라이언트 버전 정책에 새 규칙을 추가합니다.

- 기존 클라이언트 버전 정책을 구성하는 규칙 수정

## <a name="ui-reference"></a>UI 참조

다음 목록에서는 페이지의 메뉴, 명령, 필드 및 속성에 대해 설명합니다.

- **사용자 에이전트** 목록에서 클라이언트 유형을 선택할 수 있습니다. 다음 표에서는 사용자 에이전트 코드를 정의합니다. 이 목록에는 레거시 클라이언트 유형이 포함되는 중 일부는 더 이상 지원되지 않습니다.

|**클라이언트 이름**|**사용자 에이전트**|
|:-----|:-----|
|Lync 2013, Lync 2010, Office Communicator  <br/> |OC  <br/> |
|Lync Web App, Communicator Web Access  <br/> |CWA  <br/> |
|Lync 전화 Edition, Office Communicator 전화  <br/> |OCPhone  <br/> |
|Communicator 전화 버전 플랫폼  <br/> |CPE  <br/> |
|통합 통신 플랫폼  <br/> |UCCP  <br/> |
|Lync 2010 Attendee  <br/> |AOC  <br/> |
|Live Meeting Add-In  <br/> |LiveMeetingAddins  <br/> |
|Office Live Meeting  <br/> |LMC  <br/> |
|Windows Messenger  <br/> |WM  <br/> |
|실시간 통신 클라이언트  <br/> |RTC  <br/> |
|Lync 2010 for iPad  <br/> |iPadLync  <br/> |
|Lync 2010 for iPhone  <br/> |iPhoneLync  <br/> |
|Lync 2010 for Windows Phone  <br/> |WPLync  <br/> |
|Nokia용 Lync 2010  <br/> |NokiaLync  <br/> |
|Lync 2010 for Android  <br/> |AndroidLync  <br/> |
|Mobility Service  <br/> |McxService  <br/> |

- **버전 번호** 다음 필드의 버전 번호를 지정하거나 와일드카드를 사용하여 클라이언트 버전 번호를 나타낼 수 있습니다.

  - **주 버전** 클라이언트의 주 릴리스에 해당하는 번호를 지정합니다.

  - **부 버전** 클라이언트의 부 릴리스에 해당하는 번호를 지정합니다.

  - **빌드** 클라이언트의 주 릴리스 및 부 릴리스에 해당하는 빌드 번호를 지정합니다.

  - **업데이트** 클라이언트의 업데이트된 릴리스에 해당하는 번호를 지정합니다.

- **비교 작업** 이전 단계에서 지정한 클라이언트 버전에 대해 일치 작업을 지정할 수 있습니다. 다음 작업을 사용할 수 있습니다.

  - **같아야 합니다.**

  - **아닌**

  - **보다 새로 추가**

  - **더 이상 또는 같지 않습니다.**

  - **이전 버전**

  - **보다 오래되거나 같아야 합니다.**

- **작업** 이전 단계의 조건이 충족될 때 수행할 작업을 지정할 수 있습니다. 사용할 수 있는 작업은 다음과 같습니다.

  - **허용** 클라이언트가 로그온할 수 있습니다.

  - **허용 및 업그레이드** 클라이언트가 로그온하여 서버 업데이트 서비스 또는 Microsoft Windows 업데이트를 받을 수 있습니다. 이 작업은 사용자 에이전트 **OC를** 선택한 경우만 사용할 수 있습니다.

    > [!NOTE]
    > 이 작업을 선택하면 사용자가 다음에 로그인할 때 알림이 비즈니스용 Skype. 알림에는 Windows Server Update Service 또는 Microsoft Update에 업데이트가 아직 게시되지 않았더라도 사용할 수 있는 업데이트가 표시됩니다. 혼란을 방지하기 위해서는 업데이트를 사용할 수 있게 된 뒤에만 이 작업을 선택해야 합니다.

  - **URL로 허용** 클라이언트가 로그온할 수 있으며 다른 클라이언트 버전을 다운로드할 위치와 관련한 메시지를 표시합니다. URL 필드에 URL을 **지정합니다.**

  - **차단** 클라이언트가 로그온할 수 없습니다.

  - **차단 및 업그레이드** 클라이언트 로그온을 방지하고 클라이언트가 서버 업데이트 서비스 또는 Microsoft 업데이트에서 Windows 수 있습니다. 이 작업은 사용자 에이전트 **OC를** 선택한 경우만 사용할 수 있습니다.

  - **URL로 차단은** 클라이언트가 로그온하지 못하게 방지하고 다른 클라이언트 버전을 다운로드할 수 있는 위치의 메시지를 표시합니다. URL 필드에 URL을 **지정합니다.**

클라이언트와 클라이언트 버전 간 상호 연결성에 대한 자세한 내용은 계획 설명서에서 [Client Interoperability를](/previous-versions/office/lync-server-2013/lync-server-2013-client-interoperability-in-lync-2013) 참조하십시오. 클라이언트 버전 구성을 사용하는 방법에 대한 자세한 내용은 작업 설명서에서 [Modify the Default Action for Clients Not Explicitly Supported or Restricted](/previous-versions/office/lync-server-2013/lync-server-2013-modify-the-default-action-for-clients-not-explicitly-supported-or-restricted)을 참조하십시오.