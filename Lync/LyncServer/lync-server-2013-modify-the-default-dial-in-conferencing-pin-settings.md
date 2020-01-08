---
title: 'Lync Server 2013: 기본 전화 접속 회의 PIN 설정 수정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Modify the default dial-in conferencing PIN settings
ms:assetid: 2d110e94-ad29-4755-b17f-d8c2da9b78a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425780(v=OCS.15)
ms:contentKeyID: 48183712
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4ee196fae24ba4a6b7bf8e0ede0bbc0b35a7b3fc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979541"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-the-default-dial-in-conferencing-pin-settings-in-lync-server-2013"></a>Lync Server 2013에서 기본 전화 접속 회의 PIN 설정 수정

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-18_

글로벌 PIN 정책은 포리스트 수준의 전화 접속 회의 핀에 대 한 규칙을 정의 합니다. 전역 전화 접속 회의 PIN 정책을 수정 하려면 다음 단계를 따르세요. 사이트 또는 사용자 수준에서 전화 접속 회의 PIN 정책을 만들거나 수정 하는 방법에 대 한 자세한 내용은 [사이트 또는 사용자 그룹에 대 한 Lync Server 2013에서 전화 접속 회의 pin 설정 만들기 또는 수정을](lync-server-2013-create-or-modify-dial-in-conferencing-pin-settings-for-a-site-or-group-of-users.md)참조 하세요.

<div>

## <a name="to-modify-the-global-pin-policy"></a>글로벌 PIN 정책 수정

1.  RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당 된 경우 Lync Server 2013을 배포한 네트워크에 있는 컴퓨터에 로그온 합니다.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.

3.  왼쪽 탐색 모음에서 **회의**를 클릭 한 다음 **고정 정책을**클릭 합니다.

4.  **고정 정책** 페이지에서 **전역** 정책을 클릭 하 고 **편집**을 클릭 한 다음 **세부 정보 표시**를 클릭 합니다.

5.  **Pin 편집 정책**에서 **최소 pin 길이**에 허용 하려는 최소 pin 길이를 입력 하거나 선택 합니다. 기본 최소 길이는 다섯 자리입니다.

6.  사용자가 잠길 때까지 허용 되는 최대 로그온 시도 횟수를 지정할 수 있으려면 **최대 로그온 시도 수 지정** 확인란을 선택 합니다. 이 옵션을 선택 하지 않으면 허용 되는 최대 시도 수는 PIN 길이에 따라 자동으로 결정 됩니다. 기본적으로 최대 시도 횟수는 자동으로 결정 됩니다.

7.  최대 로그온 시도 **횟수 지정** 확인란을 선택한 경우 **최대 로그온 시도**에서 허용 하려는 최대 로그온 시도 횟수를 입력 하거나 선택 합니다.

8.  핀이 만료 되 게 하려면 **PIN 만료 사용** 확인란을 선택 합니다. 이 옵션을 선택 하지 않으면 Pin이 만료 되지 않습니다. 기본적으로 Pin은 만료 되지 않습니다.

9.  **Pin 만료 사용** 확인란을 선택한 경우 **pin이 (일) 후에 만료**되는 경우 해당 pin이 만료 되는 일 수를 입력 하거나 선택 합니다.

10. **Pin 기록 개수**에 사용자가 PIN을 다시 사용할 수 있으려면 먼저 사용자가 만들어야 하는 pin의 수를 입력 합니다. 기본적으로 사용자는 Pin을 다시 사용할 수 있습니다.

11. 일련 번호와 반복 되는 숫자 집합 등의 일반 숫자 패턴을 허용 하려면 **일반 패턴 허용** 확인란을 선택 합니다. 이 옵션을 선택 하지 않으면 복잡 한 자릿수의 숫자만 사용할 수 있습니다. 기본적으로 복잡 한 자릿수 패턴만 사용할 수 있습니다.
    
    <div>
    

    > [!IMPORTANT]  
    > 공통 패턴을 허용 하지 않는 것이 좋습니다.

    
    </div>

12. **커밋**을 클릭합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

