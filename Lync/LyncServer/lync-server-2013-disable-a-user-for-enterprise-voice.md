---
title: 'Lync Server 2013: 엔터프라이즈 음성에 대 한 사용자 사용 안 함'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Disable a user for Enterprise Voice
ms:assetid: 462002d8-21df-4d77-bf7f-4d059d6a4bb2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688043(v=OCS.15)
ms:contentKeyID: 49733635
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8f89b40a7398f35efab418fac7be92536ec17270
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762216"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="disable-a-user-for-enterprise-voice-in-lync-server-2013"></a>Lync Server 2013에서 엔터프라이즈 음성에 대 한 사용자 사용 안 함

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-09-21_

Lync Server 2013에 대해 설정 된 사용자 계정에 대해 Enterprise Voice를 사용 하지 않도록 설정 하려면 다음 절차를 사용 합니다.

<div>

## <a name="to-disable-a-user-account-for-enterprise-voice"></a>엔터프라이즈 음성에 대 한 사용자 계정을 사용 하지 않도록 설정 하려면

1.  CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.

3.  왼쪽 탐색 모음에서 **사용자**를 클릭 합니다.

4.  **사용자 검색** 상자에 표시 이름, 성, 이름, SAM (보안 계정 관리자) 계정 이름, SIP 주소 또는 사용 하도록 설정할 사용자 계정의 URI (Uniform resource identifier) 중 일부 또는 전체를 입력 한 다음 **찾기를**클릭 합니다.

5.  표에서 Enterprise Voice에 사용할 사용자 계정을 클릭 합니다.

6.  **편집** 메뉴에서 **세부 정보 표시**를 클릭 합니다.

7.  **Lync Server 사용자 편집** 페이지의 **전화 통신**에서 **엔터프라이즈 음성을**제외한 옵션을 클릭 합니다.
    
    <div>
    

    > [!NOTE]  
    > 사용자가 Lync를 사용 하 여 오디오 또는 비디오 전화를 걸 수 있도록 제한 하려면 <STRONG>전화 통신</STRONG>에서 <STRONG>오디오/비디오 사용 안 함</STRONG>을 클릭 합니다.

    
    </div>

8.  **커밋**을 클릭합니다.

사용자는 이제 엔터프라이즈 음성 기능을 사용할 수 없습니다.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 엔터프라이즈 음성에 대 한 사용자 활성화](lync-server-2013-enable-users-for-enterprise-voice.md)  


[Lync Server 2013의 사용자를 위한 엔터프라이즈 음성 관리](lync-server-2013-managing-enterprise-voice-for-users.md)  
[Lync Server 2013 관리 셸](lync-server-2013-lync-server-management-shell.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

