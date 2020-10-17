---
title: 'Lync Server 2013: Microsoft Exchange Server 통합 메시징을 실행 하는 서버에서 인증서 구성'
description: 'Lync Server 2013: Microsoft Exchange Server 통합 메시징을 실행 하는 서버에서 인증서를 구성 합니다.'
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
ms.openlocfilehash: 0a7d1e0aec3ec36723ee68c0a1dcd7f60050f9ea
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564404"
---
# <a name="configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging"></a>Microsoft Exchange Server 통합 메시징을 실행 하는 서버에서 인증서 구성

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-09-26_

계획 설명서의 [Lync Server 2013에서 Exchange 통합 메시징 통합 계획](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) 에 설명 된 대로 exchange Um (통합 메시징)을 배포한 후 조직의 음성 사용자에 게이 기능을 제공 하려면 다음 절차를 사용 하 여 exchange um을 실행 하는 서버에서 인증서를 구성할 수 있습니다.

<div>


> [!IMPORTANT]  
> 내부 인증서의 경우 Lync Server 2013을 실행 하는 서버와 Microsoft Exchange를 실행 하는 서버에 모두 함께 신뢰할 수 있는 루트 인증 기관 인증서가 있어야 합니다. 서버에 신뢰할 수 있는 루트 인증 기관 인증서 저장소에 등록 된 인증 기관의 루트 인증서가 있는 한, CA (인증 기관)는 동일 하거나 다른 인증 기관 중 하나 여야 합니다.



</div>

Lync Server 2013에 연결 하려면 서버 인증서를 사용 하 여 Exchange 서버를 구성 해야 합니다.

1.  Exchange Server에 대한 CA 인증서를 다운로드합니다.

2.  Exchange Server에 대한 CA 인증서를 설치합니다.

3.  Exchange Server의 신뢰할 수 있는 루트 CA 목록에 해당 CA가 있는지 확인합니다.

4.  Exchange Server에 대한 인증서 요청을 만들고 인증서를 설치합니다.

5.  Exchange Server에 대한 인증서를 할당합니다.

<div>

## <a name="to-download-the-ca-certificate"></a>CA 인증서를 다운로드하려면

1.  Exchange UM을 실행 하는 서버에서 **시작**, **실행**을 차례로 클릭 하 고 **http:// \<name of your Issuing CA Server\> /Certsrv**를 입력 한 후에 **확인**을 클릭 합니다.

2.  **작업 선택**에서 **CA 인증서, 인증서 체인 또는 CRL 다운로드**를 클릭합니다.

3.  **Ca 인증서, 인증서 체인 또는 CRL 다운로드**에서 **기본 64에 대 한 인코딩 방법을**선택 하 고 **CA 인증서 다운로드**를 클릭 합니다.
    
    <div>
    

    > [!NOTE]  
    > 이 단계에서는 DER (고유 인코딩 규칙) 인코딩을 지정할 수도 있습니다. DER 인코딩을 선택하는 경우 이 절차 다음 단계와 <STRONG>CA 인증서를 설치하려면</STRONG>의 10단계에서 파일 형식은 .cer이 아닌 .p7b입니다.

    
    </div>

4.  **파일 다운로드** 대화 상자에서 **저장**을 클릭한 다음 파일을 서버의 하드 디스크에 저장합니다. 이전 단계에서 선택한 인코딩에 따라 파일의 확장명은 .cer 또는 .p7b가 됩니다.

</div>

<div>

## <a name="to-install-the-ca-certificate"></a>CA 인증서를 설치하려면

1.  Exchange UM을 실행 하는 서버에서 **시작**, **실행**을 차례로 클릭 하 고 **열기** 상자에 **mmc** 를 입력 한 다음 **확인**을 클릭 하 여 mmc (Microsoft Management Console)를 엽니다.

2.  **파일** 메뉴에서 **스냅인 추가/제거**를 클릭한 다음 **추가**를 클릭합니다.

3.  **독립 실행형 스냅인 추가** 상자에서 **인증서**를 클릭한 다음 **추가**를 클릭합니다.

4.  **인증서 스냅인** 대화 상자에서 **컴퓨터 계정**을 클릭한 다음 **다음**을 클릭합니다.

5.  **컴퓨터 선택** 대화 상자에서 **로컬 컴퓨터: (이 콘솔이 실행 되 고 있는 컴퓨터)** 확인란이 선택 되어 있는지 확인 하 고 **마침을**클릭 합니다.

6.  **닫기**를 클릭한 다음 **확인**을 클릭합니다.

7.  콘솔 트리에서 **인증서(로컬 컴퓨터)**, **신뢰할 수 있는 루트 인증 기관**을 차례로 확장한 다음 **인증서**를 클릭합니다.

8.  **인증서**를 마우스 오른쪽 단추로 클릭하고 **모든 작업**을 클릭하고 **가져오기**를 클릭합니다.

9.  **다음**을 클릭합니다.

10. **찾아보기**를 클릭하여 파일을 찾은 다음 **다음**을 클릭합니다. **CA 인증서를 다운로드하려면**의 3단계에서 선택한 인코딩에 따라 파일의 확장명은 .cer 또는 .p7b가 됩니다.

11. **모든 인증서를 다음 저장소에 저장**을 클릭합니다.

12. **찾아보기**를 클릭한 다음 **신뢰할 수 있는 루트 인증 기관**을 선택합니다.

13. **다음**을 클릭하여 설정을 확인한 다음 **마침**을 클릭합니다.

</div>

<div>

## <a name="to-verify-that-the-ca-is-in-the-list-of-trusted-root-cas"></a>CA가 신뢰할 수 있는 루트 CA 목록에 있는지 확인하려면

1.  Exchange UM을 실행 하는 서버의 MMC에서 **인증서 (로컬 컴퓨터)**, **신뢰할 수 있는 루트 인증 기관을**차례로 확장 한 다음 **인증서**를 클릭 합니다.

2.  세부 정보 창에서 해당 CA가 신뢰할 수 있는 CA 목록에 있는지 확인합니다.

</div>

<div>

## <a name="to-configure-exchange-server-2013-um-with-lync-server"></a>Lync Server를 사용 하 여 Exchange Server 2013 UM을 구성 하려면

1.  자세한 내용은 Exchange Server 설명서에서 "Lync Server와 Exchange 2013 UM 통합"을 참조 하십시오 [https://go.microsoft.com/fwlink/p/?LinkId=265372](https://go.microsoft.com/fwlink/p/?linkid=265372) .

</div>

<div>

## <a name="to-create-a-certificate-request-and-install-the-certificate-on-exchange-server-2007-sp1"></a>Exchange Server 2007(SP1)에서 인증서 요청을 만들고 인증서를 설치하려면

1.  Exchange UM을 실행 하는 서버에서 **시작**, **실행**을 차례로 클릭 하 고 **http:// \<**name of your Issuing CA Server**\> /Certsrv**를 입력 한 후에 **확인**을 클릭 합니다.

2.  **작업 선택**에서 **인증서 요청**을 클릭합니다.

3.  **인증서 요청**에서 **고급 인증서 요청**을 클릭합니다.

4.  **고급 인증서 요청**에서 **이 CA에 요청을 만들어 제출합니다**를 클릭합니다.

5.  **고급 인증서 요청**에서 **웹 서버** 또는 서버 인증을 위해 구성된 다른 서버 인증서 템플릿을 선택합니다.

6.  **오프 라인 서식 파일 정보 확인**아래의 **이름** 상자에 Exchange 서버의 FQDN (정규화 된 도메인 이름)을 입력 합니다.
    
    <div>
    

    > [!NOTE]  
    > Exchange Server의 FQDN을 입력해야 통신이 이루어집니다.

    
    </div>

7.  **키 옵션**에서 **인증서를 로컬 컴퓨터의 인증서 저장소에 저장** 확인란을 클릭합니다.

8.  웹 페이지 아래쪽에서 **제출** 단추를 클릭합니다.

9.  확인하는 대화 상자가 열리면 **예**를 클릭합니다.

10. 발급된 인증서 페이지의 **발급된 인증서**에서 **이 인증서 설치**를 클릭합니다.

11. 확인하는 대화 상자가 열리면 **예**를 클릭합니다.

12. "새 인증서가 설치되었습니다."라는 메시지가 나타나는지 확인합니다.

</div>

<div>

## <a name="to-create-a-certificate-on-exchange-server-2010"></a>Exchange Server 2010에서 인증서를 만들려면

1.  적절 한 사용자 권한을 사용 하 여 Exchange UM을 실행 하는 서버에 로그온 합니다. 자세한 내용은에서 "클라이언트 액세스 권한"을 참조 하십시오 [https://go.microsoft.com/fwlink/p/?linkId=195499](https://go.microsoft.com/fwlink/p/?linkid=195499) .

2.  인증서를 만들려면 다음 절차를 참조하십시오.
    
    1.  "새 Exchange 인증서 만들기" [https://go.microsoft.com/fwlink/p/?linkId=195494](https://go.microsoft.com/fwlink/p/?linkid=195494)
    
    2.  "Exchange 인증서 가져오기" [https://go.microsoft.com/fwlink/p/?linkId=195496](https://go.microsoft.com/fwlink/p/?linkid=195496)
    
    <div>
    

    > [!NOTE]  
    > 인증서 <STRONG>주체 이름</STRONG>에 Exchange Server의 FQDN을 입력해야 통신이 이루어집니다.

    
    </div>

</div>

<div>

## <a name="to-assign-the-certificate-on-exchange-server-2007-sp1"></a>Exchange Server 2007(SP1)에서 인증서를 할당하려면

1.  Exchange UM을 실행 하는 서버에서 MMC를 엽니다.

2.  콘솔 트리에서 **개인**을 확장하고 **인증서**를 클릭합니다.

3.  세부 정보 창에서 개인 인증서가 표시되는지 확인합니다.

4.  인증서를 두 번 클릭 하 여 세부 정보를 읽고 유효한 지 확인 합니다.
    
    <div>
    

    > [!NOTE]  
    > 인증서가 유효한 것으로 표시될 때까지 몇 분 정도 걸릴 수 있습니다.

    
    </div>

5.  Microsoft Exchange 통합 메시징 서비스를 다시 시작합니다.
    
    <div>
    

    > [!NOTE]  
    > Exchange Server 2007 SP1 통합 메시징을 실행하는 서버에서 올바른 인증서를 자동으로 검색합니다.

    
    </div>

6.  이벤트 뷰어를 열고 이벤트 ID 1112를 찾습니다. 이 이벤트는 Exchange Server 2007 SP1 통합 메시징을 실행하는 서버가 검색한 인증서를 지정합니다.

</div>

<div>

## <a name="to-assign-the-certificate-on-exchange-server-2010"></a>Exchange Server 2010에서 인증서를 할당하려면

1.  적절 한 사용자 권한을 사용 하 여 Exchange UM을 실행 하는 서버에 로그온 합니다. 자세한 내용은에서 "클라이언트 액세스 권한"을 참조 하십시오 [https://go.microsoft.com/fwlink/p/?linkId=195499](https://go.microsoft.com/fwlink/p/?linkid=195499) .

2.  인증서를 할당 하는 절차는에서 "인증서에 서비스 할당"을 참조 하십시오 [https://go.microsoft.com/fwlink/p/?linkId=195497](https://go.microsoft.com/fwlink/p/?linkid=195497) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

