---
title: 'Lync Server 2013: 기존 PIN 정책 수정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify an existing PIN policy
ms:assetid: 517caaee-3349-4fa6-8d86-e4da3258a445
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520993(v=OCS.15)
ms:contentKeyID: 48184143
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 27f5fcc560f302021effd90ce1b16cafb933ae03
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035874"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-an-existing-pin-policy-in-lync-server-2013"></a>Lync Server 2013에서 기존 PIN 정책 수정

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-06-19_

**Pin 정책** 탭을 사용 하 여 IP 전화와 함께 Lync 2013에 연결 하는 사용자에 게 pin (개인 식별 번호) 인증을 제공할 수 있습니다. PIN 인증을 사용하려면 웹 서비스 설정에서 **PIN 인증 사용**이 선택되어 있는지 확인합니다. 자세한 내용은 [Modify 기존 웹 서비스 구성 설정에서 Lync Server 2013](lync-server-2013-modify-existing-web-service-configuration-settings.md)를 참조 하세요.

사용자 수준 또는 사이트 수준 PIN 정책을 수정하려면 다음 단계를 수행합니다.

<div>

## <a name="to-modify-an-existing-pin-policy"></a>기존 PIN 정책을 수정하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 이거나이에 해당 하는 사용자 권한이 있는 사용자 계정 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당 된 경우 Lync Server 2013을 배포한 네트워크에 있는 컴퓨터에 로그온 합니다.

2.  브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.

3.  왼쪽 탐색 모음에서 **보안**을 클릭하고 **PIN 정책**을 클릭합니다.

4.  **PIN 정책** 페이지에서 정책을 클릭하고 **편집**을 클릭한 후에 **세부 정보 표시**를 클릭합니다.

5.  **PIN 정책 편집**의 **최소 PIN 길이**에서 허용할 최소 PIN 길이를 입력하거나 선택합니다. 기본 최소 길이는 5자리입니다.

6.  사용자가 잠길 때까지의 최대 로그온 시도 횟수를 지정하려면 **최대 로그온 시도 횟수 지정** 확인란을 선택합니다. 이 옵션을 선택하지 않으면 PIN 길이에 따라 최대 로그온 시도 횟수가 자동으로 결정됩니다. 기본적으로 최대 시도 횟수는 자동으로 결정됩니다.

7.  **최대 로그온 시도 횟수 지정** 확인란을 선택한 경우 **최대 로그온 시도 횟수**에 허용할 최대 로그온 시도 횟수를 입력하거나 선택합니다.

8.  PIN이 만료되도록 하려면 **PIN 만료 사용** 확인란을 선택합니다. 이 옵션을 선택하지 않으면 PIN이 만료되지 않습니다. 기본적으로 PIN은 만료되지 않습니다.

9.  **PIN 만료 사용** 확인란을 선택한 경우 **다음 이후 PIN 만료(일)** 에 PIN이 만료될 때까지의 기간(일)을 입력하거나 선택합니다.

10. **PIN 기록 카운트**에 사용자가 PIN을 다시 사용할 수 있을 때까지 만들어야 하는 PIN의 개수를 입력합니다. 기본적으로 사용자는 PIN을 다시 사용할 수 있습니다.

11. PIN에서 연속하는 숫자, 반복되는 숫자 집합 등의 공통 숫자 패턴을 허용하려면 **공통 패턴 허용** 확인란을 선택합니다. 이 옵션을 선택하지 않으면 복잡한 숫자 패턴만 허용됩니다. 기본적으로는 복잡한 숫자 패턴만 허용됩니다.
    
    <div>
    

    > [!IMPORTANT]  
    > 공통 패턴은 허용하지 않는 것이 좋습니다.

    
    </div>

12. **커밋**을 클릭합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

