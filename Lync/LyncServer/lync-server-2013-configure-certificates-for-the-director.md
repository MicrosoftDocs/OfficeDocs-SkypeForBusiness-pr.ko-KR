---
title: 'Lync Server 2013: 디렉터에 대한 인증서 구성'
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
ms.openlocfilehash: fccab201ee9ab16b0195bc2780c37ab85f0519e9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739388"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-certificates-for-the-director-in-lync-server-2013"></a>Lync Server 2013에서 디렉터에 대한 인증서 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-09-08_

<div>


> [!IMPORTANT]  
> 인증서 마법사를 실행할 때 사용할 인증서 서식 파일 형식에 대 한 적절 한 사용 권한이 할당 된 그룹의 구성원 인 계정을 사용 하 여 로그인 했는지 확인 합니다. 기본적으로 Lync Server 2013 인증서 요청에서는 웹 서버 인증서 템플릿을 사용 합니다. RTCUniversalServerAdmins 그룹의 구성원 인 계정을 사용 하 여이 서식 파일을 사용 하 여 인증서를 요청 하는 경우 해당 서식 파일을 사용 하는 데 필요한 등록 권한이 그룹에 할당 되었는지 확인 합니다.



</div>

각 디렉터에는 기본 인증서, 웹 내부 인증서, 웹 외부 인증서가 필요 합니다. 디렉터에 대 한 인증서 요구 사항에 대 한 자세한 내용은 계획 설명서의 [Lync Server 2013의 내부 서버에 대 한 인증서 요구 사항을](lync-server-2013-certificate-requirements-for-internal-servers.md) 참조 하세요.

다음 절차를 사용 하 여 디렉터 인증서를 구성 합니다. 각 디렉터에 대해이 절차를 반복 합니다. 이 절차의 단계에서는 조직에서 배포 하 고 오프 라인 요청 처리를 사용 하 여 내부 엔터프라이즈 루트 CA (인증 기관)에서 인증서를 구성 하는 방법에 대해 설명 합니다. 외부 CA에서 인증서를 가져오는 방법에 대 한 자세한 내용은 지원 팀에 문의 하세요.

<div>

## <a name="to-configure-certificates-for-the-director-or-director-pool"></a>디렉터 또는 디렉터 풀에 대 한 인증서를 구성 하려면

1.  Lync Server 배포 마법사의 **3 단계: 요청, 인증서 설치 또는 할당**옆에 있는 **실행**을 클릭 합니다.

2.  **인증서 마법사** 페이지에서 **요청**을 클릭 합니다.

3.  **인증서 요청** 페이지에서 **다음**을 클릭 합니다.

4.  **지연 또는 즉시 요청** 페이지에서 기본 **요청을 온라인 인증 기관에 보내기** 옵션을 적용 하 고 **다음**을 클릭 합니다.

5.  **CA (인증 기관) 선택** 페이지에서 사용 하려는 내부 Windows 인증 기관을 클릭 하 고 **다음**을 클릭 합니다.

6.  로그인 한 계정에 인증서를 요청할 수 있는 권한이 없는 경우 **인증 기관 계정** 페이지에서 사용할 대체 자격 증명을 지정 하 고 **다음**을 클릭 합니다.

7.  **대체 인증서 템플릿 지정** 페이지에서 **다음**을 클릭 합니다.

8.  **이름 및 보안 설정** 페이지에서 **이름을**지정 하 고 2048 비트 키 길이를 적용 한 후 **다음**을 클릭 합니다.

9.  **조직 정보** 페이지에서 필요에 따라 조직 정보를 지정 하 고 **다음**을 클릭 합니다.

10. **지리적 정보** 페이지에서 필요에 따라 지리 정보를 지정 하 고 **다음**을 클릭 합니다.

11. **주체 이름/제목 대체 이름** 페이지에서 **다음**을 클릭 합니다.
    
    <div>
    

    > [!NOTE]  
    > 주체 대체 이름 목록에는 디렉터를 설치 하는 컴퓨터의 이름 (단일 디렉터) 또는 디렉터 풀 이름과 조직에 대해 구성 된 간단한 URL 이름이 포함 되어야 합니다.

    
    </div>

12. **SIP 도메인 설정의 san (주체 대체 이름** ) 페이지에서 디렉터를 처리할 모든 도메인에 대해 **구성 된 sip 도메인** 을 선택 하 고 **다음**을 클릭 합니다.

13. **추가 주체 이름 구성** 페이지에서 필요한 추가 제목 대체 이름을 추가 하 고 **다음**을 클릭 합니다.

14. **인증서 요청 요약** 페이지에서 **다음**을 클릭 합니다.

15. **명령** 실행 페이지에서 명령이 실행을 완료 한 후 **다음** 을 클릭 합니다.

16. **온라인 인증서 요청 상태** 페이지에서 **마침을**클릭 합니다.

17. **인증서 할당** 페이지에서 **다음**을 클릭 합니다.
    
    <div>
    

    > [!NOTE]  
    > 인증서를 확인 하려면 목록에서 인증서를 두 번 클릭 합니다.

    
    </div>

18. **인증서 할당 요약** 페이지에서 **다음**을 클릭 합니다.

19. **명령 실행 페이지에서** 명령이 완료 된 후 **마침을** 클릭 합니다.

20. **인증서 마법사** 페이지에서 **닫기를**클릭 합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

