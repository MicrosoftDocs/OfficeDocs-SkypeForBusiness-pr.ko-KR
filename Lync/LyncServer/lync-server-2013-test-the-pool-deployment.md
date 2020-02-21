---
title: 'Lync Server 2013: 풀 배포 테스트'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test the pool deployment
ms:assetid: ffd80617-155a-4041-bbeb-74503e7938dd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413092(v=OCS.15)
ms:contentKeyID: 48185976
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 552677dde2706265093879bc9b48ac803e1365fb
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194471"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="test-the-pool-deployment-in-lync-server-2013"></a>Lync Server 2013에서 풀 배포 테스트

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-09-25_

다음 절차에서는 프런트 엔드 풀의 배포를 테스트 하는 방법을 설명 합니다.

<div>

## <a name="to-test-the-pool-deployment"></a>풀 배포를 테스트하려면

1.  Active Directory 컴퓨터 및 사용자를 사용 하 여 lync server 2013 제어판이 설치 된 경우의 관리자 2013 역할에 해당 하는 Active Directory 사용자 개체를 **csadministrator** 그룹에 추가 합니다.
    
    <div>
    

    > [!IMPORTANT]  
    > CsAdministors 그룹에 적절 한 사용자 및 그룹을 추가 하지 않으면 Lync Server 제어판을 여는 경우 "권한이 없음: ' 허용 되지 않음 ' 권한이 있는 RBAC (역할 기반 액세스 제어) 권한 부여 오류로 인해 액세스가 거부 됨을 나타내는 오류 메시지가 표시 됩니다."

    
    </div>

2.  사용자 개체가 현재 로그온되어 있는 경우 로그오프하고 다시 로그온하여 새 그룹 지정을 등록합니다.
    
    <div>
    

    > [!NOTE]  
    > 사용자 계정은 Lync Server 2013를 실행 하는 서버의 로컬 관리자 일 수 없습니다.

    
    </div>

3.  관리 계정을 사용 하 여 Lync Server 제어판이 설치 된 컴퓨터에 로그온 합니다.

4.  Lync Server 제어판을 시작한 다음 메시지가 표시 되 면 자격 증명을 제공 합니다. Lync Server 제어판이 배포 정보를 표시 합니다.

5.  왼쪽 탐색 모음에서 **토폴로지**를 클릭 하 고 서비스 상태에 녹색 화살표가 있는 컴퓨터가 표시 되 고, 배포 및 온라인 상태가 된 각 Lync Server 서버 역할 옆에 복제 상태에 대 한 녹색 확인 표시가 있는지 확인 합니다.

6.  왼쪽 탐색 표시줄에서 **사용자** 및 **사용자 사용**을 차례로 클릭합니다.

7.  **새 Lync Server 사용자** 페이지에서 **추가**를 클릭합니다.

8.  찾을 개체에 대한 검색 매개 변수를 정의하려면 **Active Directory에서 선택** 페이지에서 **검색**을 선택하고 경우에 따라 **필터 추가**를 클릭하면 됩니다. **LDAP 검색**을 선택하고 LDAP 식을 입력하여 반환되는 개체를 필터링하거나 제한할 수도 있습니다. 검색 옵션을 결정했으면 **찾기**를 클릭합니다.

9.  검색 결과 창에서 이 검색 세션에 대한 개체를 모두 선택하고 **확인**을 클릭합니다.

10. **새 Lync Server 사용자** 페이지의 **사용자** 화면 표시에 선택한 개체(들)가 나타납니다. **사용자를 풀에 할당** 목록에서 개체가 속해야 하는 서버를 선택합니다.
    
    아래에 개체를 구성할 수 있는 여러 옵션이 나와 있습니다.
    
      - **사용자의 SIP URI 생성**
    
      - **통신과**
    
      - **줄 URI**
    
      - **회의 정책**
    
      - **클라이언트 버전 정책**
    
      - **PIN 정책**
    
      - **외부 액세스 정책**
    
      - **보관 정책**
    
      - **위치 정책**
    
      - **클라이언트 정책**
    
    기본적인 기능을 테스트하기 위해 **사용자의 SIP URI 생성** 설정에 대해 원하는 옵션을 선택하고 **사용**을 클릭합니다(구성의 다른 옵션에는 기본 설정이 사용됨).

11. 요약 페이지가 표시되며, 이 페이지의 **사용** 열에는 개체를 바로 사용할 수 있다는 확인 표시가 나타납니다. **SIP 주소** 열에 사용자 로그인 구성에 필요한 주소가 표시됩니다.

12. 도메인에 가입된 컴퓨터에 사용자 로그온하고 도메인의 다른 컴퓨터에 다른 사용자로 로그온합니다.

13. 두 클라이언트 컴퓨터 각각에 Lync 2013을 설치한 다음 두 사용자가 Lync Server 2013에 로그인 하 여 서로에 게 인스턴트 메시지를 보낼 수 있는지 확인 합니다.

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

