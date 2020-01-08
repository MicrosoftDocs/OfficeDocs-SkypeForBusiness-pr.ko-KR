---
title: 'Lync Server 2013: 익명 사용자 지원을 위한 회의 정책 할당'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Assign conferencing policies to support anonymous users
ms:assetid: 662de022-1111-40f7-bad4-f2b686f30973
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521007(v=OCS.15)
ms:contentKeyID: 48184333
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 94ff3fe520b776d6f6043abb66f9926da5acaa22
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982357"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assign-conferencing-policies-to-support-anonymous-users-in-lync-server-2013"></a>Lync Server 2013에서 익명 사용자 지원을 위한 회의 정책 할당

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-19_

기본적으로 모든 사용자는 익명 사용자를 초대 하 여 모임에 참가할 수 없습니다. 익명 사용자를 지원 하도록 회의 정책을 구성 하 고 특정 사용자에 게 해당 회의 정책을 적용 하 여 익명 사용자를 초대할 수 있는 사용자를 제어 합니다. 익명 사용자를 지원 하도록 회의 정책을 구성 하는 방법에 대 한 자세한 내용은 [Lync server 2013에서 회의 정책 만들기 또는 수정을](lync-server-2013-create-or-modify-a-conferencing-policy.md) 참조 하 고 [페더레이션 및 lync server 2013에 대 한 외부 액세스를 관리](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md)하세요.

이 섹션의 절차를 사용 하 여 이미 만든 회의 정책을 하나 이상의 사용자 또는 사용자 그룹에 적용할 수 있습니다.

<div>


> [!NOTE]  
> 사용자가 익명 사용자를 초대할 수 있도록 하는 정책을 구성 하 고 적용 하는 것 외에도 조직의 익명 사용자에 대 한 지원을 사용 하도록 설정 해야 합니다. 자세한 내용은 <A href="lync-server-2013-configure-policies-to-control-public-user-access.md">Lync Server 2013에서 공용 사용자 액세스를 제어 하는 정책 구성을</A>참조 하세요.



</div>

<div>

## <a name="to-configure-a-user-policy-for-anonymous-participation-in-meetings"></a>모임에서 익명 참가에 대 한 사용자 정책을 구성 하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.

3.  왼쪽 탐색 모음에서 **회의**를 클릭 하 고 다음 중 하나를 수행 합니다.
    
    1.  새 사용자 정책을 만들려면 **새로 만들기**를 클릭 한 다음 **사용자 정책을**클릭 합니다. 사용자 정책이 어떤 역할을 하는지 나타내는 **이름** 필드에 고유한 이름을 만듭니다 (예: 익명 사용자와의 통신을 가능 하 게 하는 사용자 정책에 **익명** 허용).
    
    2.  기존 사용자 정책을 구성 하려면 표에 나열 된 적절 한 정책을 클릭 하 고 **편집**을 클릭 한 다음 **세부 정보 표시**를 클릭 합니다.

4.  **회의 정책** 대화 상자에서 **참가자가 익명 사용자 초대를 허용** 확인란을 선택 합니다.

5.  **커밋**을 클릭합니다.

6.  왼쪽 탐색 모음에서 **사용자**를 클릭 하 고 구성 하려는 사용자 계정에서 검색 합니다.

7.  검색 결과가 나열된 표에서 사용자 계정을 클릭하고 **편집**을 클릭한 후에 **자세한 정보 표시**를 클릭합니다.

8.  **회의 정책**에서 **Lync Server 사용자 편집** 에서이 사용자에 게 적용 하려는 익명 사용자 액세스 구성이 있는 사용자 정책을 선택 합니다.
    
    <div>
    

    > [!NOTE]  
    > 자동 설정은 기본 서버 설치 설정을 적용 하 고 서버에 의해 자동으로 적용 됩니다. <STRONG> &lt;&gt; </STRONG>

    
    </div>

사용자가 회의에 익명 사용자를 초대할 수 있도록 하려면 조직의 익명 사용자에 대 한 지원도 사용 하도록 설정 해야 합니다. 자세한 내용은 배포 설명서 또는 운영 설명서의 [Lync Server 2013에서 공용 사용자 액세스를 제어 하는 정책 구성을](lync-server-2013-configure-policies-to-control-public-user-access.md) 참조 하세요.

</div>

</div>

<span> </span>

</div>

</div>

</div>

