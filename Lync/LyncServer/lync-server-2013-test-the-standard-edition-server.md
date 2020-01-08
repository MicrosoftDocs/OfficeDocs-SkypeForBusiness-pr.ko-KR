---
title: 'Lync Server 2013: Standard Edition 서버 테스트'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Test the Standard Edition server
ms:assetid: b6ef67bb-9665-43e4-b8b3-eac8898eebf6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412890(v=OCS.15)
ms:contentKeyID: 48185220
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a960451ebdd1e6e8728bf3b6c7df6e267c49c3f8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981507"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-the-standard-edition-server-in-lync-server-2013"></a>Lync Server 2013에서 Standard Edition 서버 테스트

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-01_

다음 절차에서는 스탠더드 버전 서버의 배포를 테스트 하는 방법을 설명 합니다.

<div>

## <a name="to-test-the-deployment-of-a-standard-edition-server"></a>스탠더드 버전 서버의 배포를 테스트 하려면

1.  Active Directory 컴퓨터와 사용자를 사용 하 여 lync server 제어판이 설치 되어 있는 Lync Server 2013 배포에 대 한 관리자 역할의 Active Directory 사용자 개체를 **csadministrator** 그룹에 추가 합니다.

2.  사용자 개체가 현재 로그온 되어 있으면 로그 오프 한 다음 다시 로그온 하 여 새 그룹 할당을 등록 합니다.
    
    <div>
    

    > [!NOTE]  
    > 사용자 계정은 Lync Server 2013, Standard Edition을 실행 하는 서버의 로컬 관리자가 될 수 없습니다. CsAdministors 그룹에 적절 한 사용자 및 그룹을 추가 하지 않으면 Lync Server 2013 제어판을 열 때 오류가 발생 하며,이는 "허용 되지 않음: ' RBAC (역할 기반 액세스 제어) 권한 부여 오류로 인해 액세스가 거부 됨" 이라는 것을 표시 합니다.

    
    </div>

3.  관리자 계정을 사용 하 여 Lync Server 제어판이 설치 되어 있는 컴퓨터에 로그온 합니다.

4.  Lync Server 제어판을 시작 하 고 메시지가 표시 되 면 자격 증명을 입력 합니다. Lync Server 2013 제어판에 배포 정보가 표시 됩니다.

5.  왼쪽 탐색 모음에서 **토폴로지**를 클릭 한 다음 서비스 상태가 녹색 화살표가 있는 컴퓨터 아이콘 인지 확인 하 고, 배포 되 고 온라인 상태가 된 각 Lync server 역할 옆에 녹색 확인 표시가 있습니다.

6.  왼쪽 탐색 모음에서 **사용자**를 클릭 한 다음 Lync Server 2013의 두 사용자를 사용 하도록 설정 합니다.

7.  도메인에 가입 된 컴퓨터와 도메인의 다른 컴퓨터에 있는 다른 사용자에 게 한 명의 사용자를 로그인 합니다.

8.  두 클라이언트 컴퓨터 각각에 Lync Server 2013을 설치한 다음 두 사용자가 Lync Server 2013에 로그인 하 여 서로에 게 인스턴트 메시지를 보낼 수 있는지 확인 합니다.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 클라이언트 및 장치 배포](lync-server-2013-deploying-clients-and-devices.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

