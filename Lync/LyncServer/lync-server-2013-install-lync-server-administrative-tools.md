---
title: 'Lync Server 2013: Lync Server 관리 도구 설치'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Install Lync Server administrative tools
ms:assetid: 842b85e4-2eeb-464f-b1c1-ceb8cc04f8d5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398665(v=OCS.15)
ms:contentKeyID: 48184695
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0f7d1b29ce4bad3b5a50c59d0da6911964f9e108
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147191"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="install-lync-server-2013-administrative-tools"></a>Lync Server 2013 관리 도구 설치

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-02-21_

이 항목에서는 Lync Server 2013를 배포 하 고 관리 하는 데 필요한 관리 도구를 설치 하는 방법에 대해 설명 합니다. 관리 도구는 Lync Server 2013를 실행 하는 각 서버에 기본적으로 설치 됩니다. 또한 전용 관리 콘솔과 같은 다른 컴퓨터에 관리 도구를 설치할 수도 있습니다. Active Directory 도메인 서비스 준비 단계가 이미 수행 되 고 있는지 확인 하기 때문에 만드는 Lync Server 2013 배포와 동일한 도메인 또는 포리스트에 있는 컴퓨터에 관리 도구를 설치 하는 것이 좋습니다. 완료-나중에 해당 컴퓨터의 관리 도구를 사용 하 여 토폴로지를 게시할 수 있습니다.

Lync Server 2013 관리 도구를 설치 하거나 사용 하기 전에 인프라, 운영 체제, 소프트웨어 및 관리자 권한 요구 사항을 검토 해야 합니다. 인프라 요구 사항에 대 한 자세한 내용은 [Lync Server 2013의 관리 도구 인프라 요구 사항을](lync-server-2013-administrative-tools-infrastructure-requirements.md)참조 하세요. Lync server 2013 관리 도구를 설치 하기 위한 운영 체제 및 소프트웨어 요구 사항에 대 한 자세한 내용은 [lync server 2013의 서버 및 도구 운영 체제 지원](lync-server-2013-server-and-tools-operating-system-support.md), lync server [2013의 추가 소프트웨어 요구 사항](lync-server-2013-additional-software-requirements.md)및 [lync server 2013의 추가 서버 지원 및 요구 사항을](lync-server-2013-additional-server-support-and-requirements.md)참조 하세요. 도구를 설치 및 사용 하는 데 필요한 사용자 권한 및 사용 권한에 대 한 자세한 내용은 [Lync Server 2013의 설정 및 관리에 필요한 관리자 권한 및 사용 권한](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)를 참조 하십시오.

<div>


> [!IMPORTANT]  
> 조직에서 IIS(인터넷 정보 서비스)와 모든 웹 서비스를 시스템 드라이브가 아닌 다른 드라이브에 배치해야 하는 경우 설치 프로그램 대화 상자에서 nm-server-w15-long 파일의 설치 위치 경로를 변경할 수 있습니다. OCSCore를 포함 하 여이 경로에 설치 파일을 설치 하는 경우 나머지 Lync Server 2013 파일은이 드라이브에도 배포 됩니다.



</div>

<div>

## <a name="to-install-the-lync-server-2013-administrative-tools"></a>Lync Server 2013 관리 도구를 설치 하려면

1.  관리 도구를 설치할 컴퓨터에 로컬 관리자(최소 요구 사항)로 로그온합니다. Windows Vista 또는 Windows 7 운영 체제에서 표준 사용자로 로그온하는 경우 UAC(사용자 계정 제어)가 사용하도록 설정되어 있으면 로컬 관리자 또는 도메인의 해당 사용자 이름과 암호를 입력하라는 메시지가 표시됩니다.

2.  컴퓨터에서 설치 미디어를 찾은 다음 Setup \\\\amd64\\setup.exe를 두 번 클릭 합니다.

3.  Microsoft Visual C++ 2008 배포 가능 파일을 설치할지 묻는 메시지가 표시되면 **예**를 클릭합니다.

4.  **Microsoft Lync Server 2013 설치 위치** 페이지에서 **확인**을 클릭 합니다. 다른 위치에 파일을 설치해야 하는 경우 이 경로를 다른 위치나 드라이브로 변경합니다.
    
    <div>
    

    > [!IMPORTANT]  
    > 조직에서 IIS (인터넷 정보 서비스) 및 모든 웹 서비스를 시스템 드라이브 이외의 드라이브에 배치 해야 하는 경우 설치 대화 상자에서 Lync Server 2013 파일의 설치 위치 경로를 변경할 수 있습니다. OCSCore를 포함 하 여이 경로에 설치 파일을 설치 하는 경우 나머지 Lync Server 2013 파일은이 드라이브에도 배포 됩니다.

    
    </div>

5.  **최종 사용자 사용권 계약** 페이지에서 사용 조건을 검토하고 **동의함**, **확인**을 차례로 클릭합니다. 계속하려면 이 단계를 수행해야 합니다.

6.  **Microsoft Lync Server 2013 – 배포 마법사** 페이지에서 **관리자 도구 설치**를 클릭 합니다.

7.  설치가 완료되면 **끝내기**를 클릭합니다.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)  


[Lync Server 2013 관리 도구](lync-server-2013-lync-server-administrative-tools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

