---
title: 'Lync Server 2013: 사용자 계정 설정 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure user account settings
ms:assetid: b7c74ecc-b924-4efc-8a56-3a5f94a9ef13
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412896(v=OCS.15)
ms:contentKeyID: 48185200
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b4d06405d2f80aef5decb69d564ae399401d4328
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985195"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-user-account-settings-in-lync-server-2013"></a>Lync Server 2013에서 사용자 계정 설정 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-05_

전화 접속 사용자는 전화 번호나 내선 번호와 PIN을 입력 하 여 인증 된 사용자로 회의에 참가할 수 있습니다. Lync Server 사용자 계정에 지정 된 전화 통신 **회선 URI** 가 인증에 필요 합니다.

이 항목의 절차에서는 단일 사용자 계정에 대 한 **회선 URI** 를 할당 하는 방법에 대해 설명 합니다. 여러 사용자 계정에 대 한 **줄 URI** 를 할당 해야 하는 경우 **Set csuser** cmdlet을 사용 하는 스크립트를 만들 수 있습니다. 샘플 스크립트를 사용 하 여 여러 사용자 계정에 **줄 uri** 를 할당 하는 방법에 대 한 자세한 내용은에서 [http://go.microsoft.com/fwlink/p/?linkId=196945](http://go.microsoft.com/fwlink/p/?linkid=196945)"여러 사용자에 게 줄 uri 할당"을 참조 하세요.

<div>

## <a name="to-configure-user-account-settings"></a>사용자 계정 설정을 구성 하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 또는 **Cs-useradministrator** 또는 **csadministrator** 역할의 구성원으로 컴퓨터에 로그온 합니다.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.

3.  왼쪽 탐색 모음에서 **사용자**를 클릭 합니다.

4.  검색 필드에 전화 접속 회의에 대해 구성할 사용자의 이름을 입력 하거나, **필터 추가** 를 클릭 하 여 검색 필드를 지정 하 고 **찾기를**클릭 합니다.

5.  사용자 이름을 두 번 클릭 하 여 **Lync Server 사용자 편집** 대화 상자를 엽니다.

6.  **전화 통신**아래의 **줄 URI** 필드에 고유한 정규화 된 전화 번호 (예: tel: + 14255550200)를 입력 합니다.
    
    <div>
    

    > [!NOTE]  
    > <STRONG>전화 통신이</STRONG> <STRONG>pc 대 pc 전용</STRONG>, <STRONG>엔터프라이즈 음성</STRONG>, <STRONG>원격 통화 제어</STRONG> 또는 <STRONG>원격 통화 제어 전용 으로만</STRONG>설정 된 경우에만 <STRONG>줄 URI</STRONG> 를 지정할 수 있습니다.

    
    </div>

7.  **커밋**을 클릭합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

