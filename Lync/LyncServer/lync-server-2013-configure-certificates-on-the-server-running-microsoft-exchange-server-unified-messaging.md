---
title: 'Lync Server 2013: Microsoft Exchange Server 통합 메시징을 실행 하는 서버에서 인증서 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure certificates on the server running Microsoft Exchange Server Unified Messaging
ms:assetid: 74c883b4-cef6-41a9-b2eb-7212be32fea4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398564(v=OCS.15)
ms:contentKeyID: 48184521
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6d31ed8b750d0162a2c09d49ca8a350731896086
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739358"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging"></a>Microsoft Exchange Server 통합 메시징을 실행 하는 서버에서 인증서 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-09-26_

계획 설명서의 [Lync Server 2013에서 Exchange 통합 메시징 통합 계획](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) 에 설명 된 대로 exchange Um (통합 메시징)를 배포 하 고 조직의 Enterprise Voice 사용자에 게 exchange um 기능을 제공 하려는 경우 다음 절차를 사용 하 여 exchange um을 실행 하는 서버에서 인증서를 구성할 수 있습니다.

<div>


> [!IMPORTANT]  
> 내부 인증서의 경우 Lync Server 2013를 실행 하는 서버와 Microsoft Exchange를 실행 하는 서버에 모두 상호 신뢰 되는 신뢰할 수 있는 루트 인증 기관 인증서가 있어야 합니다. CA (인증 기관)가 신뢰할 수 있는 루트 인증 기관 인증서 저장소에 등록 되어 있는 경우 해당 서버는 동일 하거나 다른 인증 기관 이어야 합니다.



</div>

Lync Server 2013에 연결 하려면 서버 인증서를 사용 하 여 Exchange 서버를 구성 해야 합니다.

1.  Exchange 서버에 대 한 CA 인증서를 다운로드 합니다.

2.  Exchange 서버에 대 한 CA 인증서를 설치 합니다.

3.  CA가 Exchange Server의 신뢰할 수 있는 루트 Ca 목록에 있는지 확인 합니다.

4.  Exchange 서버에 대 한 인증서 요청을 만들고 인증서를 설치 합니다.

5.  Exchange 서버에 대 한 인증서를 할당 합니다.

<div>

## <a name="to-download-the-ca-certificate"></a>CA 인증서를 다운로드 하려면

1.  Exchange UM을 (를) 실행 하는 서버에서 **시작**, **실행**을 차례로 클릭 하 고 **발급 하는 CA 서버\<\>/certsrv의 http://이름을**입력 한 다음 **확인**을 클릭 합니다.

2.  **작업 선택**에서 **CA 인증서, 인증서 체인 또는 CRL 다운로드**를 클릭 합니다.

3.  **Ca 인증서, 인증서 체인 또는 CRL 다운로드**에서 **Base 64에 대 한 인코딩 방법을**선택한 다음 **CA 인증서 다운로드**를 클릭 합니다.
    
    <div>
    

    > [!NOTE]  
    > 이 단계에서 DER (고유 인코딩 규칙) 인코딩을 지정할 수도 있습니다. DER 인코딩을 선택 하는 경우이 절차의 다음 단계인 <STRONG>CA 인증서를 설치 하</STRONG> 는 10 단계의 파일 형식은. .cer이 아닌.

    
    </div>

4.  **파일 다운로드** 대화 상자에서 **저장**을 클릭 한 다음 서버의 하드 디스크에 파일을 저장 합니다. (이 파일에는 이전 단계에서 선택한 인코딩에 따라 .cer 또는. p7b 확장명 중 하나가 사용 됩니다.)

</div>

<div>

## <a name="to-install-the-ca-certificate"></a>CA 인증서를 설치 하려면

1.  Exchange UM을 (를) 실행 하는 서버에서 **시작**을 클릭 하 고 **실행**을 클릭 한 다음 **열기** 상자에 **mmc** 를 입력 하 고 **확인**을 클릭 하 여 mmc (Microsoft Management Console)를 엽니다.

2.  **파일** 메뉴에서 **스냅인 추가/제거**를 클릭 한 다음 **추가**를 클릭 합니다.

3.  **독립 실행형 스냅인 추가** 상자에서 **인증서**를 클릭 한 다음 **추가**를 클릭 합니다.

4.  **인증서 스냅인** 대화 상자에서 **컴퓨터 계정을**클릭 하 고 **다음**을 클릭 합니다.

5.  **컴퓨터 선택** 대화 상자에서 **로컬 컴퓨터: (이 콘솔이 실행 되 고 있는 컴퓨터)** 확인란이 선택 되어 있는지 확인 한 다음 **마침을**클릭 합니다.

6.  **닫기를**클릭 한 다음 **확인**을 클릭 합니다.

7.  콘솔 트리에서 **인증서 (로컬 컴퓨터)** 를 확장 하 고 **신뢰할 수 있는 루트 인증 기관을**확장 한 다음 **인증서**를 클릭 합니다.

8.  **인증서**를 마우스 오른쪽 단추로 클릭 하 고 **모든 작업**을 클릭 한 다음 **가져오기를**클릭 합니다.

9.  **다음**을 클릭 합니다.

10. **찾아보기를** 클릭 하 여 파일을 찾은 후 **다음**을 클릭 합니다. (이 파일은 **CA 인증서를 다운로드 하기 위해**3 단계에서 선택한 인코딩에 따라 .cer 또는. p7b 파일 확장명을 갖습니다.

11. **모든 인증서를 다음 저장소에**저장을 클릭 합니다.

12. **찾아보기를**클릭 한 다음 **신뢰할 수 있는 루트 인증 기관을**선택 합니다.

13. **다음** 을 클릭 하 여 설정을 확인 한 다음 **마침을**클릭 합니다.

</div>

<div>

## <a name="to-verify-that-the-ca-is-in-the-list-of-trusted-root-cas"></a>CA가 신뢰할 수 있는 루트 Ca 목록에 있는지 확인 하려면 다음을 진행 합니다.

1.  Exchange UM을 실행 하는 서버의 MMC에서 **인증서 (로컬 컴퓨터)** 를 확장 하 고 **신뢰할 수 있는 루트 인증 기관**을 확장 한 다음 **인증서**를 클릭 합니다.

2.  세부 정보 창에서 CA가 신뢰할 수 있는 Ca 목록에 있는지 확인 합니다.

</div>

<div>

## <a name="to-configure-exchange-server-2013-um-with-lync-server"></a>Lync Server를 사용 하 여 Exchange Server 2013 UM을 구성 하려면

1.  자세한 내용은 Exchange Server 설명서에서 "Lync 서버와 Exchange 2013 UM 통합"을 참조 하세요 [http://go.microsoft.com/fwlink/p/?LinkId=265372](http://go.microsoft.com/fwlink/p/?linkid=265372).

</div>

<div>

## <a name="to-create-a-certificate-request-and-install-the-certificate-on-exchange-server-2007-sp1"></a>인증서 요청을 만들고이 인증서를 Exchange Server 2007 (SP1)에 설치 하려면

1.  Exchange UM을 (를) 실행 하는 서버에서 **시작**, **실행**을 차례로 클릭 하 고 발급 하는 CA 서버**\>/certsrv**의 **http://\<** 이름을 입력 한 다음 **확인**을 클릭 합니다.

2.  **작업 선택**에서 **인증서 요청**을 클릭 합니다.

3.  **인증서 요청**에서 **고급 인증서 요청**을 클릭 합니다.

4.  **고급 인증서 요청**에서 **이 CA에 대 한 요청 만들기 및 제출을**클릭 합니다.

5.  **고급 인증서 요청**에서 서버 인증을 위해 구성 된 **웹 서버** 또는 다른 서버 인증서 템플릿을 선택 합니다.

6.  **오프 라인 서식 파일에 대 한 정보 확인**아래에 있는 **이름** 상자에 Exchange Server의 FQDN (정규화 된 도메인 이름)을 입력 합니다.
    
    <div>
    

    > [!NOTE]  
    > 통신을 사용 하려면 Exchange 서버의 FQDN을 입력 해야 합니다.

    
    </div>

7.  **키 옵션**에서 **로컬 컴퓨터 인증서 저장소에 인증서 저장** 확인란을 클릭 합니다.

8.  웹 페이지 아래쪽에 있는 **제출** 단추를 클릭 합니다.

9.  확인 하 라는 메시지가 열리는 대화 상자에서 **예**를 클릭 합니다.

10. 인증서 발급 됨 페이지의 **인증서 발급 됨**에서 **이 인증서 설치**를 클릭 합니다.

11. 확인 하 라는 메시지가 열리는 대화 상자에서 **예**를 클릭 합니다.

12. "새 인증서가 성공적으로 설치 되었습니다" 라는 메시지가 나타나는지 확인 합니다.

</div>

<div>

## <a name="to-create-a-certificate-on-exchange-server-2010"></a>Exchange Server 2010에서 인증서를 만들려면

1.  적절 한 사용자 권한을 사용 하 여 Exchange UM을 (를) 실행 하는 서버에 로그온 합니다. 자세한 내용은에서 [http://go.microsoft.com/fwlink/p/?linkId=195499](http://go.microsoft.com/fwlink/p/?linkid=195499)"클라이언트 액세스 권한"을 참조 하세요.

2.  인증서를 만들려면 다음 절차를 참조 하세요.
    
    1.  "새 Exchange 인증서 만들기"[http://go.microsoft.com/fwlink/p/?linkId=195494](http://go.microsoft.com/fwlink/p/?linkid=195494)
    
    2.  "Exchange 인증서 가져오기"[http://go.microsoft.com/fwlink/p/?linkId=195496](http://go.microsoft.com/fwlink/p/?linkid=195496)
    
    <div>
    

    > [!NOTE]  
    > 인증서 <STRONG>주체 이름의</STRONG>경우 통신이 작동 하려면 EXCHANGE 서버의 FQDN을 입력 해야 합니다.

    
    </div>

</div>

<div>

## <a name="to-assign-the-certificate-on-exchange-server-2007-sp1"></a>Exchange Server 2007 (SP1)에서 인증서를 할당 하려면

1.  Exchange UM을 (를) 실행 하는 서버에서 MMC를 엽니다.

2.  콘솔 트리에서 **개인** 을 확장 한 다음 **인증서**를 클릭 합니다.

3.  세부 정보 창에서 개인 인증서가 표시 되는지 확인 합니다.

4.  인증서를 두 번 클릭 하 여 세부 정보를 읽고 유효한 지 확인 합니다.
    
    <div>
    

    > [!NOTE]  
    > 인증서가 유효한 것으로 표시 되기까지 몇 분이 소요 될 수 있습니다.

    
    </div>

5.  Microsoft Exchange 통합 메시징 서비스를 다시 시작 합니다.
    
    <div>
    

    > [!NOTE]  
    > Exchange Server 2007 SP1 통합 메시징을 실행 하는 서버는 올바른 인증서를 자동으로 검색 합니다.

    
    </div>

6.  이벤트 뷰어를 열고 Exchange Server 2007 SP1 통합 메시징을 실행 하는 서버가 검색 한 인증서를 지정 하는 이벤트 ID 1112을 찾습니다.

</div>

<div>

## <a name="to-assign-the-certificate-on-exchange-server-2010"></a>Exchange Server 2010에서 인증서를 할당 하려면

1.  적절 한 사용자 권한을 사용 하 여 Exchange UM을 (를) 실행 하는 서버에 로그온 합니다. 자세한 내용은에서 [http://go.microsoft.com/fwlink/p/?linkId=195499](http://go.microsoft.com/fwlink/p/?linkid=195499)"클라이언트 액세스 권한"을 참조 하세요.

2.  인증서를 할당 하는 절차는에서 [http://go.microsoft.com/fwlink/p/?linkId=195497](http://go.microsoft.com/fwlink/p/?linkid=195497)"인증서에 서비스 할당"을 참조 하세요.

</div>

</div>

<span> </span>

</div>

</div>

</div>

