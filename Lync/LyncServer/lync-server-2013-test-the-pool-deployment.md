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
ms.openlocfilehash: cfde95e7323d68f05e78f670a6b027a5949f0169
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746068"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-the-pool-deployment-in-lync-server-2013"></a>Lync Server 2013에서 풀 배포 테스트

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-09-25_

다음 절차에서는 프런트 엔드 풀의 배포를 테스트 하는 방법을 설명 합니다.

<div>

## <a name="to-test-the-pool-deployment"></a>풀 배포를 테스트 하려면

1.  Active Directory 컴퓨터와 사용자를 사용 하 여 lync server 2013 제어판에 설치 되어 있는 Lync Server 2013 배포에 대 한 관리자 역할의 Active Directory 사용자 개체를 **csadministrator** 그룹에 추가 합니다.
    
    <div>
    

    > [!IMPORTANT]  
    > 적절 한 사용자 및 그룹을 CsAdministors 그룹에 추가 하지 않으면 Lync Server 제어판을 열 때 오류가 표시 되며,이는 "허용 되지 않음: ' 사용자가 RBAC (역할 기반 액세스 제어) 권한 부여 오류로 인해 액세스가 거부 됨을 나타내는"입니다. "

    
    </div>

2.  사용자 개체가 현재 로그온 되어 있으면 로그 오프 한 다음 다시 로그온 하 여 새 그룹 할당을 등록 합니다.
    
    <div>
    

    > [!NOTE]  
    > 사용자 계정은 Lync Server 2013을 실행 하는 서버의 로컬 관리자가 될 수 없습니다.

    
    </div>

3.  관리자 계정을 사용 하 여 Lync Server 제어판이 설치 되어 있는 컴퓨터에 로그온 합니다.

4.  Lync Server 제어판을 시작한 다음 메시지가 표시 되 면 자격 증명을 제공 합니다. Lync Server 제어판에 배포 정보가 표시 됩니다.

5.  왼쪽 탐색 모음에서 **토폴로지**를 클릭 한 다음 서비스 상태가 녹색 화살표가 있는 컴퓨터를 표시 하 고 복제 상태에 대 한 녹색 확인 표시가 배포 되어 온라인 상태가 된 각 Lync server 역할 옆에 있는지 확인 합니다.

6.  왼쪽 탐색 모음에서 **사용자**를 클릭 한 다음 **사용자 사용**을 클릭 합니다.

7.  **새 Lync Server 사용자** 페이지에서 **추가**를 클릭 합니다.

8.  찾으려는 개체에 대 한 검색 매개 변수를 정의 하려면 **Active Directory에서 선택** 페이지에서 **검색**을 선택한 다음 필요에 따라 **필터 추가**를 클릭할 수 있습니다. **Ldap 검색** 을 선택 하 고 ldap 식을 입력 하 여 반환 되는 개체를 필터링 하거나 제한할 수도 있습니다. 검색 옵션을 결정 한 후에는 clink **찾기를**선택 합니다.

9.  검색 결과 창에서이 검색 세션의 모든 개체를 선택 하 고 **확인**을 클릭 합니다.

10. **새 Lync Server 사용자** 페이지에서 선택한 개체는 **사용자가** 표시 합니다. **풀에 사용자 할당** 목록에서 개체를 배치할 서버를 선택 합니다.
    
    다음은 개체를 구성 하는 여러 가지 옵션입니다.
    
      - **사용자의 SIP URI 생성**
    
      - **통신**
    
      - **줄 URI**
    
      - **회의 정책**
    
      - **클라이언트 버전 정책**
    
      - **고정 정책**
    
      - **외부 액세스 정책**
    
      - **보관 정책**
    
      - **위치 정책**
    
      - **클라이언트 정책**
    
    기본 기능을 테스트 하기 위해 **사용자의 SIP URI 생성** 설정 (구성의 다른 옵션에서 기본 설정을 사용 함)에 대해 원하는 옵션을 선택한 다음 **사용**을 클릭 합니다.

11. 사용 **가능** 열에 확인 표시가 표시 된 요약 페이지가 표시 되 고 이제 해당 개체를 사용할 준비가 되었음을 나타냅니다. **SIP 주소** 열에는 사용자 로그인 구성에 필요한 주소가 표시 됩니다.

12. 도메인에 가입 된 컴퓨터와 도메인의 다른 컴퓨터에 대 한 다른 사용자에 게 한 명의 사용자를 로그인 합니다.

13. 두 클라이언트 컴퓨터 각각에 Lync 2013를 설치한 다음 두 사용자가 Lync Server 2013에 로그인 하 여 서로에 게 인스턴트 메시지를 보낼 수 있는지 확인 합니다.

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

