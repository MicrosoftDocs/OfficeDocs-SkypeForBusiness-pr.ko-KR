---
title: 클라이언트 버전 규칙
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ClientCVPolicyRuleEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6e7e94c2-1475-4334-b8da-716b24a4c255
description: 클라이언트 버전 정책은 클라이언트 버전 규칙 집합으로 구성됩니다. 이러한 규칙은 사용자가 특정 클라이언트 및 클라이언트 버전을 사용하여 로그온을 시도할 때 수행할 동작을 정의합니다.
ms.openlocfilehash: 870f0d46ff50b4fabab9b4f098cb569ae2c9ee82
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41823061"
---
# <a name="client-version-rule"></a>클라이언트 버전 규칙

클라이언트 버전 정책은 클라이언트 버전 규칙 집합으로 구성됩니다. 이러한 규칙은 사용자가 특정 클라이언트 및 클라이언트 버전을 사용하여 로그온을 시도할 때 수행할 동작을 정의합니다.

## <a name="tasks-you-can-perform"></a>수행할 수 있는 작업

**새 클라이언트 버전 구성** 또는 **클라이언트 버전 구성 편집** 페이지에서 다음 작업을 수행할 수 있습니다.

- 클라이언트 버전 정책에 새 규칙 추가

- 기존 클라이언트 버전 정책을 구성하는 규칙 수정

## <a name="ui-reference"></a>UI 참조

다음 목록에서는 페이지의 메뉴, 명령, 필드 및 속성에 대해 설명합니다.

- **사용자 에이전트** 목록에서 클라이언트 유형을 선택할 수 있습니다. 다음 표에서는 사용자 에이전트 코드를 정의 합니다.

|**클라이언트 이름**|**사용자 에이전트**|
|:-----|:-----|
|Lync 2013, Lync 2010, Office Communicator  <br/> |OC  <br/> |
|Lync Web App, Communicator Web Access  <br/> |CWA  <br/> |
|Lync Phone Edition, Office Communicator 휴대폰  <br/> |OCPhone  <br/> |
|Communicator Phone Edition 플랫폼  <br/> |CPE  <br/> |
|통합 통신 플랫폼  <br/> |UCCP  <br/> |
|Lync 2010 참석자  <br/> |AOC  <br/> |
|Live Meeting 추가 기능  <br/> |LiveMeetingAddins  <br/> |
|Office Live Meeting  <br/> |LMC  <br/> |
|Windows Messenger  <br/> |WM  <br/> |
|실시간 통신 클라이언트  <br/> |RTC  <br/> |
|IPad 용 Lync 2010  <br/> |iPadLync  <br/> |
|IPhone 용 Lync 2010  <br/> |iPhoneLync  <br/> |
|Windows Phone 용 Lync 2010  <br/> |WPLync  <br/> |
|Nokia 용 Lync 2010  <br/> |NokiaLync  <br/> |
|Android 용 Lync 2010  <br/> |AndroidLync  <br/> |
|모바일 서비스  <br/> |McxService  <br/> |

- **버전 번호** 다음 필드에 대 한 버전 번호를 지정 하거나 와일드 카드를 사용 하 여 클라이언트 버전 번호를 표시할 수 있습니다.

  - **주 버전** 클라이언트의 주요 릴리스에 해당 하는 번호를 지정 합니다.

  - **부 버전** 클라이언트의 부 릴리스에 해당 하는 번호를 지정 합니다.

  - **빌드** 클라이언트의 주 및 부 릴리스에 해당 하는 빌드 번호를 지정 합니다.

  - **업데이트** 업데이트 된 클라이언트의 릴리스에 해당 하는 번호를 지정 합니다.

- **비교 연산** 앞 단계에서 지정한 클라이언트 버전에 대 한 일치 작업을 지정할 수 있습니다. 다음과 같은 작업을 사용할 수 있습니다.

  - **같음**

  - **일치하지 않음**

  - **보다 최근임**

  - **보다 최근이거나 같음**

  - **보다 오래됨**

  - **보다 오래되거나 같음**

- **작업** 앞 단계의 조건이 충족 되는 경우 수행할 작업을 지정할 수 있습니다. 사용할 수 있는 작업은 다음과 같습니다.

  - **허용** 클라이언트가 로그온 할 수 있도록 합니다.

  - **허용 및 업그레이드** 클라이언트가 Windows Server Update 서비스 또는 Microsoft Update에서 로그온 하 고 업데이트를 받을 수 있도록 합니다. 이 작업은 사용자 에이전트 **OC** 를 선택한 경우에만 사용할 수 있습니다.

    > [!NOTE]
    > 이 작업을 선택 하면 다음에 사용자가 비즈니스용 Skype에 로그인 할 때 알림이 표시 됩니다. 알림에는 Windows Server Update Service 또는 Microsoft Update에 업데이트가 아직 게시되지 않았더라도 사용할 수 있는 업데이트가 표시됩니다. 혼란을 방지하기 위해서는 업데이트를 사용할 수 있는 경우에만 이 작업을 선택해야 합니다.

  - **URL에 허용** 클라이언트가 로그온 하도록 허용 하 고 다른 클라이언트 버전을 다운로드할 위치에 대 한 메시지를 표시 합니다. **URL** 필드에서 URL을 지정합니다.

  - **차단** 클라이언트가 로그온 할 수 없도록 합니다.

  - **차단 및 업그레이드** 클라이언트가 로그온 할 수 없고 클라이언트가 Windows Server Update 서비스 또는 Microsoft 업데이트에서 업데이트를 받을 수 있도록 합니다. 이 작업은 사용자 에이전트 **OC** 를 선택한 경우에만 사용할 수 있습니다.

  - **URL로 차단**을 선택하면 클라이언트가 로그온할 수 없도록 차단하고 다른 클라이언트 버전을 다운로드할 위치에 대한 메시지를 표시합니다. **URL** 필드에서 URL을 지정합니다.

클라이언트와 클라이언트 버전 간 상호 운용성에 대한 자세한 내용은 계획 설명서의 [Client Interoperability in Lync 2013 Preview](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx)을 참조하세요. 클라이언트 버전 구성을 사용하는 방법에 대한 자세한 내용은 작업 설명서의 [Modify the Default Action for Clients Not Explicitly Supported or Restricted](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx)을 참조하세요.

