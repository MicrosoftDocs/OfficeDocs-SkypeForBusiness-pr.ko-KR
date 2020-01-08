---
title: 'Lync Server 2013: 사이트 또는 사용자 그룹에 대한 전화 접속 회의 PIN 설정 만들기 또는 수정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify dial-in conferencing PIN settings for a site or group of users
ms:assetid: c29bab5c-2b93-48e0-ae0b-29564daaff9a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412959(v=OCS.15)
ms:contentKeyID: 48185326
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2af1dc8e3f9bde06e799c758b711f94b7c0e6411
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981522"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-dial-in-conferencing-pin-settings-in-lync-server-2013-for-a-site-or-group-of-users"></a>Lync Server 2013에서 사이트 또는 사용자 그룹에 대한 전화 접속 회의 PIN 설정 만들기 또는 수정

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-18_

다음 단계에 따라 사용자 수준 또는 사이트 수준의 전화 접속 회의 PIN (개인 식별 번호) 정책을 만들거나 수정 합니다. 글로벌 PIN 정책을 변경 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 기본 전화 접속 회의 PIN 설정 수정을](lync-server-2013-modify-the-default-dial-in-conferencing-pin-settings.md)참조 하세요.

<div>

## <a name="to-create-a-user-or-site-pin-policy"></a>사용자 또는 사이트 PIN 정책을 만들려면

1.  RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당 된 경우 Lync Server 2013을 배포한 네트워크에 있는 컴퓨터에 로그온 합니다.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.

3.  왼쪽 탐색 모음에서 **회의**를 클릭 한 다음 **고정 정책을**클릭 합니다.

4.  **고정 정책** 페이지에서 **새로 만들기**를 클릭 하 고 다음 중 하나를 수행 합니다.
    
      - 사용자 수준 정책을 만들려면 **사용자 정책을**클릭 합니다. **새 PIN 정책의** **이름**에 정책을 설명 하는 이름을 입력 합니다.
    
      - 사이트 수준 정책을 만들려면 **사이트 정책을**클릭 합니다. 사이트 검색 **선택** 필드에 정책을 만들려는 사이트 이름의 전부 또는 일부를 입력 합니다. 사이트 목록에서 원하는 사이트를 클릭 한 다음 **확인**을 클릭 합니다.

5.  **설명** 필드에 고정 정책에 대 한 설명을 입력 합니다.

6.  **최소 pin 길이** 필드에 허용 하려는 최소 pin 길이를 입력 하거나 선택 합니다. 기본 최소 길이는 다섯 자리입니다.

7.  사용자가 잠길 때까지 허용 되는 최대 로그온 시도 횟수를 지정할 수 있으려면 **최대 로그온 시도 수 지정** 확인란을 선택 합니다. 이 옵션을 선택 하지 않으면 허용 되는 최대 시도 수는 PIN 길이에 따라 자동으로 결정 됩니다. 기본적으로 최대 시도 횟수는 자동으로 결정 됩니다.

8.  최대 로그온 시도 **횟수 지정** 확인란을 선택한 경우 **최대 로그온 시도**에서 허용 하려는 최대 로그온 시도 횟수를 입력 하거나 선택 합니다.

9.  핀이 만료 되 게 하려면 **PIN 만료 사용** 확인란을 선택 합니다. 이 옵션을 선택 하지 않으면 Pin이 만료 되지 않습니다. 기본적으로 Pin은 만료 되지 않습니다.

10. **Pin 만료 사용** 확인란을 선택한 경우 **pin이 (일) 후에 만료**되는 경우 해당 pin이 만료 되는 일 수를 입력 하거나 선택 합니다.

11. **Pin 기록 개수**에 사용자가 PIN을 다시 사용할 수 있으려면 먼저 사용자가 만들어야 하는 pin의 수를 입력 합니다. 기본적으로 사용자는 Pin을 다시 사용할 수 있습니다.

12. 일련 번호와 반복 되는 숫자 집합 등의 일반 숫자 패턴을 허용 하려면 **일반 패턴 허용** 확인란을 선택 합니다. 이 옵션을 선택 하지 않으면 복잡 한 자릿수의 숫자만 사용할 수 있습니다. 기본적으로 복잡 한 자릿수 패턴만 사용할 수 있습니다.
    
    <div>
    

    > [!IMPORTANT]
    > 공통 패턴을 허용 하지 않는 것이 좋습니다.

    
    </div>

13. **커밋**을 클릭합니다.

</div>

<div>

## <a name="to-change-a-user-or-site-pin-policy"></a>사용자 또는 사이트 PIN 정책을 변경 하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당 된 경우 Lync Server 2013을 배포한 네트워크에 있는 컴퓨터에 로그온 합니다.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.

3.  왼쪽 탐색 모음에서 **회의**를 클릭 한 다음 **고정 정책을**클릭 합니다.

4.  **고정 정책** 페이지에서 변경 하려는 pin 정책을 클릭 하 고 **편집**을 클릭 한 다음 **세부 정보 표시**를 클릭 합니다.

5.  **PIN 정책 편집**에서 정책 설정을 수정 합니다 (수정할 수 없는 정책 이름을 제외한).

6.  **커밋**을 클릭합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

