---
title: 'Lync Server 2013: 사이트 또는 사용자 그룹에 대 한 전화 접속 회의 PIN 설정 만들기 또는 수정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify dial-in conferencing PIN settings for a site or group of users
ms:assetid: c29bab5c-2b93-48e0-ae0b-29564daaff9a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412959(v=OCS.15)
ms:contentKeyID: 48185326
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5b65d62514cabe64381fc002e4c7242c9a782acb
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151760"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-dial-in-conferencing-pin-settings-in-lync-server-2013-for-a-site-or-group-of-users"></a>Lync Server 2013에서 사이트 또는 사용자 그룹에 대 한 전화 접속 회의 PIN 설정 만들기 또는 수정

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-18_

다음 단계에 따라 사용자 수준 또는 사이트 수준 전화 접속 회의의 PIN(개인 식별 번호) 정책을 만들거나 수정할 수 있습니다. 글로벌 PIN 정책을 변경 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 기본 전화 접속 회의 PIN 설정 수정을](lync-server-2013-modify-the-default-dial-in-conferencing-pin-settings.md)참조 하십시오.

<div>

## <a name="to-create-a-user-or-site-pin-policy"></a>사용자 또는 사이트 PIN 정책을 만들려면

1.  RTCUniversalServerAdmins 그룹의 구성원 이거나이에 해당 하는 사용자 권한이 있는 사용자 계정 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당 된 경우 Lync Server 2013을 배포한 네트워크에 있는 컴퓨터에 로그온 합니다.

2.  브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.

3.  왼쪽 탐색 모음에서 **회의**를 클릭하고 **PIN 정책**을 클릭합니다.

4.  **PIN 정책** 페이지에서 **새로 만들기**를 클릭한 다음, 다음 중 하나를 수행합니다.
    
      - 사용자 수준 정책을 만들려면 **사용자 정책**을 클릭합니다. **새 PIN 정책**의 **이름**에 정책에 대해 설명하는 이름을 입력합니다.
    
      - 사이트 수준 정책을 만들려면 **사이트 정책**을 클릭합니다. **사이트 선택** 검색 필드에 정책을 만들 사이트의 이름 전부 또는 일부를 입력합니다. 사이트 목록에서 원하는 사이트를 클릭한 다음 **확인**을 클릭합니다.

5.  **설명** 필드에 PIN 정책에 대한 설명을 입력합니다.

6.  **최소 PIN 길이** 필드에서 허용할 최소 PIN 길이를 입력하거나 선택합니다. 기본 최소 길이는 5자리입니다.

7.  사용자가 잠길 때까지의 최대 로그온 시도 횟수를 지정하려면 **최대 로그온 시도 횟수 지정** 확인란을 선택합니다. 이 옵션을 선택하지 않으면 PIN 길이에 따라 최대 로그온 시도 횟수가 자동으로 결정됩니다. 기본적으로 최대 시도 횟수는 자동으로 결정됩니다.

8.  **최대 로그온 시도 횟수 지정** 확인란을 선택한 경우 **최대 로그온 시도 횟수**에 허용할 최대 로그온 시도 횟수를 입력하거나 선택합니다.

9.  PIN이 만료되도록 하려면 **PIN 만료 사용** 확인란을 선택합니다. 이 옵션을 선택하지 않으면 PIN이 만료되지 않습니다. 기본적으로 PIN은 만료되지 않습니다.

10. **PIN 만료 사용** 확인란을 선택한 경우 **다음 이후 PIN 만료(일)** 에 PIN이 만료될 때까지의 기간(일)을 입력하거나 선택합니다.

11. **PIN 기록 카운트**에 사용자가 PIN을 다시 사용할 수 있을 때까지 만들어야 하는 PIN의 개수를 입력합니다. 기본적으로 사용자는 PIN을 다시 사용할 수 있습니다.

12. PIN에서 연속하는 숫자, 반복되는 숫자 집합 등의 공통 숫자 패턴을 허용하려면 **공통 패턴 허용** 확인란을 선택합니다. 이 옵션을 선택하지 않으면 복잡한 숫자 패턴만 허용됩니다. 기본적으로는 복잡한 숫자 패턴만 허용됩니다.
    
    <div>
    

    > [!IMPORTANT]
    > 공통 패턴은 허용하지 않는 것이 좋습니다.

    
    </div>

13. **커밋**을 클릭합니다.

</div>

<div>

## <a name="to-change-a-user-or-site-pin-policy"></a>사용자 또는 사이트 PIN 정책을 변경하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 이거나이에 해당 하는 사용자 권한이 있는 사용자 계정 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당 된 경우 Lync Server 2013을 배포한 네트워크에 있는 컴퓨터에 로그온 합니다.

2.  브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.

3.  왼쪽 탐색 모음에서 **회의**를 클릭하고 **PIN 정책**을 클릭합니다.

4.  **PIN 정책** 페이지에서 변경할 PIN 정책을 클릭한 다음 **편집**, **자세한 정보 표시**를 차례로 클릭합니다.

5.  **PIN 정책 편집**에서 원하는 정책 설정을 수정합니다(이름은 수정할 수 없음).

6.  **커밋**을 클릭합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

