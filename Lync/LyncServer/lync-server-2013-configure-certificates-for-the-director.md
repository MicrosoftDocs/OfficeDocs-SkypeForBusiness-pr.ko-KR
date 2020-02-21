---
title: 'Lync Server 2013: 디렉터에 대 한 인증서 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure certificates for the Director
ms:assetid: 22988186-15ae-43b1-92f4-0adb3b75a7fd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398296(v=OCS.15)
ms:contentKeyID: 48183612
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7c5fef23ca24d9a09d326b75ec2ad2e30704852f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205099"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-certificates-for-the-director-in-lync-server-2013"></a>Lync Server 2013에서 디렉터에 대 한 인증서 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-09-08_

<div>


> [!IMPORTANT]  
> 인증서 마법사를 실행할 때는 사용할 인증서 템플릿의 유형에 대해 적절한 권한이 할당된 그룹 구성원인 계정을 사용하여 로그인해야 합니다. 기본적으로 Lync Server 2013 인증서 요청은 웹 서버 인증서 템플릿을 사용 합니다. RTCUniversalServerAdmins 그룹 구성원인 계정을 사용하여 이 템플릿을 사용하는 인증서를 요청하는 경우 이 그룹에 해당 템플릿을 사용하는 데 필요한 등록 권한이 할당되었는지 확인하십시오.



</div>

각 디렉터에는 기본 인증서, 웹 내부 인증서 및 웹 외부 인증서가 필요합니다. 디렉터에 대 한 인증서 요구 사항에 대 한 자세한 내용은 계획 설명서에서 [Lync Server 2013의 내부 서버에 대 한 인증서 요구 사항을](lync-server-2013-certificate-requirements-for-internal-servers.md) 참조 하십시오.

다음 절차에 따라 디렉터 인증서를 구성 합니다. 각 디렉터에 대해이 절차를 반복 합니다. 이 절차의 단계에서는 조직 및 오프 라인 요청 처리를 통해 배포 된 내부 엔터프라이즈 루트 CA (인증 기관)에서 인증서를 구성 하는 방법을 설명 합니다. 외부 CA에서 인증서를 가져오는 방법에 대 한 자세한 내용은 지원 팀에 문의 하세요.

<div>

## <a name="to-configure-certificates-for-the-director-or-director-pool"></a>디렉터 또는 디렉터 풀에 대 한 인증서를 구성 하려면

1.  Lync Server 배포 마법사의 **3 단계: 인증서 요청, 설치 또는 할당**옆에 있는 **실행**을 클릭 합니다.

2.  **인증서 마법사** 페이지에서 **요청**을 클릭합니다.

3.  **인증서 요청** 페이지에서 **다음**을 클릭합니다.

4.  **지연 또는 즉시 요청** 페이지에서 기본 **요청을 온라인 인증 기관에 즉시 보내기** 옵션을 수락 하 고 **다음**을 클릭 합니다.

5.  **CA (인증 기관) 선택** 페이지에서 사용할 내부 Windows 인증 기관을 클릭 하 고 **다음**을 클릭 합니다.

6.  **인증 기관 계정** 페이지에서 로그온 하는 데 사용 하는 계정에 인증서 요청 권한이 없는 경우 사용할 대체 자격 증명을 지정 하 고 **다음**을 클릭 합니다.

7.  **대체 인증서 템플릿 지정** 페이지에서 **다음**을 클릭 합니다.

8.  **이름 및 보안 설정** 페이지에서 **대화명**을 지정 하 고, 2048 비트 키 길이를 적용 하 고, **다음**을 클릭할 수 있습니다.

9.  **조직 정보** 페이지에서 선택적으로 조직 정보를 지정 하 고 **다음**을 클릭 합니다.

10. **지역 정보** 페이지에서 선택적으로 지역 정보를 지정 하 고 **다음**을 클릭 합니다.

11. **주체 이름/주체 대체 이름** 페이지에서 **다음**을 클릭 합니다.
    
    <div>
    

    > [!NOTE]  
    > 주체 대체 이름 목록에는 디렉터를 설치할 컴퓨터의 이름 (디렉터가 하나인 경우) 또는 디렉터 풀 이름이 있고 조직에 대해 구성 된 단순 URL 이름이 포함 되어야 합니다.

    
    </div>

12. **주체 대체 이름 (san)에 대 한 SIP 도메인 설정** 페이지에서 디렉터가 처리할 모든 도메인에 대해 **구성 된 SIP 도메인** 을 선택 하 고 **다음**을 클릭 합니다.

13. **추가 주체 대체 이름 구성** 페이지에서 필요한 주체 대체 이름을 추가 하 고 **다음**을 클릭 합니다.

14. **인증서 요청 요약** 페이지에서 **다음**을 클릭 합니다.

15. **명령** 실행 중 페이지에서, 해당 명령이 완료 되 면 **다음** 을 클릭 합니다.

16. **온라인 인증서 요청 상태** 페이지에서 **다음**을 클릭합니다.

17. **인증서 지정** 페이지에서 **다음**을 클릭합니다.
    
    <div>
    

    > [!NOTE]  
    > 인증서를 보려면 목록에서 인증서를 두 번 클릭 합니다.

    
    </div>

18. **인증서 지정 요약** 페이지에서 **다음**을 클릭합니다.

19. 명령을 실행 한 후 **명령 실행** 페이지에서 **마침을** 클릭 합니다.

20. **인증서 마법사** 페이지에서 **닫기**를 클릭합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

