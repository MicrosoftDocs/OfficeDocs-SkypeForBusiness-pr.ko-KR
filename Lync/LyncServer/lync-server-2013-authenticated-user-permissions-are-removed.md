---
title: 'Lync Server 2013: 인증 된 사용자 권한이 제거 됨'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Authenticated user permissions are removed
ms:assetid: 5fcd70a5-813a-4076-9bb6-5b0d47505038
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398425(v=OCS.15)
ms:contentKeyID: 48184304
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 52815327d185355c6c5762252e4ad9b34e77ea85
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42197001"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="authenticated-user-permissions-are-removed-in-lync-server-2013"></a>Lync Server 2013에서 인증 된 사용자 권한이 제거 됨

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-02-21_

잠겨 있는 Active Directory 환경에서는 사용자 및 컴퓨터 개체가 저장되는 OU(조직 구성 단위), 구성 또는 시스템, 사용자를 비롯한 기본 Active Directory 컨테이너에서 인증된 사용자 ACE(액세스 제어 항목)가 제거됩니다. 인증된 사용자 ACE를 제거하면 Active Directory 정보를 읽을 수 없습니다. 그러나 Ace를 제거 하면 이러한 컨테이너에 대 한 읽기 권한이 있어 사용자가 도메인 준비를 실행할 수 있기 때문에 Lync Server 2013에 대 한 문제가 발생 합니다.

이 상황에서 도메인 준비, 서버 활성화 및 풀 만들기를 실행하는 데 필요한 Domain Admins 그룹의 구성원이 기본 컨테이너에 저장된 Active Directory 정보에 대한 읽기 권한을 더 이상 부여할 수 없습니다. 필요한 포리스트 준비 절차가 완료되었는지 확인하려면 포리스트 루트 도메인의 여러 도메인에 대한 읽기 권한을 수동으로 부여해야 합니다.

포리스트 루트 도메인이 아닌 모든 도메인에서 도메인 준비, 서버 활성화 또는 풀 만들기를 활성화하기 위한 방법은 다음과 같습니다.

  - 엔터프라이즈 관리자 그룹의 구성원 인 계정을 사용 하 여 도메인 준비를 실행 합니다.

  - Domain Admins 그룹의 구성원인 계정을 사용하고 포리스트 루트 도메인의 다음 컨테이너에 대한 읽기 권한을 이 계정에 부여합니다.
    
      - 도메인
    
      - 구성 또는 시스템

Enterprise Admins 그룹의 구성원인 계정을 사용하여 도메인 준비 작업이나 기타 설치 작업을 실행하지 않으려는 경우 사용할 계정에 포리스트 루트의 관련 컨테이너에 대한 읽기 권한을 명시적으로 부여하십시오.

<div>

## <a name="to-give-users-read-access-permissions-on-containers-in-the-forest-root-domain"></a>사용자에게 포리스트 루트 도메인의 컨테이너에 대한 읽기 권한을 부여하려면

1.  포리스트 루트 도메인에 대한 Domain Admins 그룹의 구성원인 계정으로 포리스트 루트 도메인에 가입된 컴퓨터에 로그온합니다.

2.  포리스트 루트 도메인에 대해 adsiedit.msc를 실행합니다.
    
    인증된 사용자 ACE가 도메인, 구성 또는 시스템 컨테이너에서 제거된 경우에는 다음 단계를 따라 컨테이너에 대한 읽기 전용 권한을 부여해야 합니다.

3.  컨테이너를 마우스 오른쪽 단추로 클릭한 다음 **속성**을 클릭합니다.

4.  **보안** 탭을 클릭합니다.

5.  **고급**을 클릭합니다.

6.  **사용 권한** 탭에서 **추가**를 클릭합니다.

7.  다음 형식을 `domain\account name`사용 하 여 사용 권한을 받는 사용자 또는 그룹의 이름을 입력 하 고 **확인**을 클릭 합니다.

8.  **개체** 탭의 **적용 대상**에서 **이 개체만**을 클릭합니다.

9.  **사용 권한**에서 **허용** 열을 클릭하여 **내용 보기**, **모든 속성 읽기** 및 **읽기 권한** 허용 ACE를 선택합니다.

10. **확인**을 두 번 클릭합니다.

11. 2단계에 나열된 모든 관련 컨테이너에 대해 위의 단계를 반복합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

