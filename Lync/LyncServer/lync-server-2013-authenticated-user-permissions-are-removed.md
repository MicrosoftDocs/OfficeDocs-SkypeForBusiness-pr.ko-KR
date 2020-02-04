---
title: 'Lync Server 2013: 인증된 사용자 권한이 제거됨'
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
ms.openlocfilehash: 63b9761f96156fdc4dea124d4438cdb8685add26
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722609"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="authenticated-user-permissions-are-removed-in-lync-server-2013"></a>Lync Server 2013에서 인증된 사용자 권한이 제거됨

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-02-21_

잠겨진 Active Directory 환경에서 인증 된 Ace (사용자 액세스 제어 항목)는 사용자 및 컴퓨터의 사용자, 구성 또는 시스템, 조직 구성 단위 (Ou) 등의 기본 Active Directory 컨테이너에서 제거 됩니다. 개체가 저장 됩니다. 인증 된 사용자 Ace를 제거 하면 Active Directory 정보에 대 한 읽기 액세스가 차단 됩니다. 그러나 Ace를 제거 하면 사용자가 도메인 준비를 실행할 수 있도록 하기 위해 이러한 컨테이너에 대 한 읽기 권한에 따라 Lync 서버 2013에 대 한 문제가 생성 됩니다.

이 경우 도메인 준비, 서버 활성화, 풀 만들기를 실행 하는 데 필요한 Domain Admins 그룹의 구성원은 더 이상 기본 컨테이너에 저장 된 Active Directory 정보에 대 한 읽기 권한을 부여 하지 않습니다. 필수 구성 요소 포리스트 준비 절차가 완료 되었는지 확인 하려면 포리스트 루트 도메인의 다양 한 컨테이너에 대 한 읽기 액세스 권한을 수동으로 부여 해야 합니다.

사용자가 포리스트 이외의 루트 도메인에서 도메인 준비, 서버 활성화 또는 풀 만들기를 실행할 수 있도록 설정 하려면 다음 옵션을 사용 합니다.

  - 엔터프라이즈 관리자 그룹의 구성원 인 계정을 사용 하 여 도메인 준비를 실행 합니다.

  - 도메인 관리자 그룹의 구성원 인 계정을 사용 하 고 포리스트 루트 도메인의 다음 컨테이너 각각에 대해이 계정에 대 한 읽기 액세스 권한을 부여 합니다.
    
      - 도메인이
    
      - 구성 또는 시스템

엔터프라이즈 관리자 그룹의 구성원 인 계정을 사용 하 여 도메인 준비 나 기타 설치 작업을 실행 하지 않으려는 경우에는 포리스트 루트의 관련 컨테이너에 대 한 읽기 권한을 사용 하도록 계정을 명시적으로 부여 합니다.

<div>

## <a name="to-give-users-read-access-permissions-on-containers-in-the-forest-root-domain"></a>사용자에 게 포리스트 루트 도메인의 컨테이너에 대 한 읽기 액세스 권한을 부여 하려면 다음을 실행 합니다.

1.  포리스트 루트 도메인에 대 한 Domain Admins 그룹의 구성원 인 계정을 사용 하 여 포리스트 루트 도메인에 연결 된 컴퓨터에 로그온 합니다.

2.  포리스트 루트 도메인에 대해 adsiedit를 실행 합니다.
    
    인증 된 사용자 Ace가 도메인, 구성 또는 시스템 컨테이너에서 제거 되 면 다음 단계에 설명 된 대로 컨테이너에 읽기 전용 권한을 부여 해야 합니다.

3.  컨테이너를 마우스 오른쪽 단추로 클릭 한 다음 **속성**을 클릭 합니다.

4.  **보안** 탭을 클릭 합니다.

5.  **고급**을 클릭합니다.

6.  **사용 권한** 탭에서 **추가**를 클릭 합니다.

7.  다음 형식으로 권한을 받는 사용자 또는 그룹의 이름을 입력 하 고 `domain\account name` **확인**을 클릭 합니다.

8.  **개체** 탭의 **적용 대상**에서 **해당 개체만**을 클릭 합니다.

9.  **사용 권한**에서 **허용** 열: **콘텐츠 목록**, **모든 속성 읽기**, **권한 읽기**를 차례로 클릭 하 여 다음 ace 허용을 선택 합니다.

10. **확인을** 두 번 클릭 합니다.

11. 2 단계에 나열 된 관련 컨테이너에 대해이 단계를 반복 합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

