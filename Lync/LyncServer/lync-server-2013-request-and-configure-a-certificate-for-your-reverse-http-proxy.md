---
title: HTTP 역방향 프록시에 대한 인증서 요청 및 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Request and configure a certificate for your reverse HTTP proxy
ms:assetid: 4b70991e-5f10-40a3-b069-0b227c3a3a0a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429704(v=OCS.15)
ms:contentKeyID: 48184085
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2597bf31c9f0cc9f4316f505811426f2c9948a6f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723856"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="request-and-configure-a-certificate-for-your-reverse-http-proxy-in-lync-server-2013"></a>Lync Server 2013에서 HTTP 역방향 프록시에 대한 인증서 요청 및 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2014-02-14_

Microsoft Lync를 실행 하는 서버에 대 한 루트 CA (인증 기관) 인증서를 설치 해야 합니다 (서버 인증서를 발급 하는 CA 인프라에 대 한 microsoft Forefront 위협 관리 게이트웨이 2010 또는 IIS ARR을 사용할 수 있습니다.) 서버 2013.

또한 역방향 프록시 서버에 공용 웹 서버 인증서를 설치 해야 합니다. 이 인증서의 주체 대체 이름에는 원격 액세스를 사용 하도록 설정 된 사용자에 게 가정용으로 지정 되는 각 풀의 게시 된 외부 Fqdn (정식 도메인 이름)과, 내에서 사용할 모든 디렉터 또는 디렉터 풀의 외부 Fqdn이 포함 됩니다. 해당 Edge 인프라. 또한 제목 대체 이름에는 모임 간단한 URL, 전화 접속 간단한 URL, 모바일 응용 프로그램을 배포 하는 경우 다음 표에 표시 된 대로 자동 검색 서비스 URL을 사용 하는 경우와 같이 해당 사용자에 게 연결 하는 방법에 대


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>값</th>
<th>예</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>주체 이름</p></td>
<td><p>풀 FQDN</p></td>
<td><p>webext.contoso.com</p></td>
</tr>
<tr class="even">
<td><p>주체 대체 이름</p></td>
<td><p>풀 FQDN</p></td>
<td><p>webext.contoso.com</p>



> [!IMPORTANT]
> 주체 이름은 주체 대체 이름에도 표시 되어야 합니다.

</td>
</tr>
<tr class="odd">
<td><p>주체 대체 이름</p></td>
<td><p>선택적 디렉터 웹 서비스 (디렉터가 배포 된 경우)</p></td>
<td><p>webdirext.contoso.com</p></td>
</tr>
<tr class="even">
<td><p>주체 대체 이름</p></td>
<td><p>간단한 모임 URL</p>



> [!NOTE]
> 모든 모임 단순 Url은 주체 대체 이름에 있어야 합니다. 각 SIP 도메인에는 활성 모임의 간단한 URL이 하나 이상 있어야 합니다.

</td>
<td><p>meet.contoso.com</p></td>
</tr>
<tr class="odd">
<td><p>주체 대체 이름</p></td>
<td><p>전화 접속 간단한 URL</p></td>
<td><p>dialin.contoso.com</p></td>
</tr>
<tr class="even">
<td><p>주체 대체 이름</p></td>
<td><p>Office Web Apps 서버</p></td>
<td><p>officewebapps01.contoso.com</p></td>
</tr>
<tr class="odd">
<td><p>주체 대체 이름</p></td>
<td><p>외부 자동 검색 서비스 URL</p></td>
<td><p>lyncdiscover.contoso.com</p>



> [!NOTE]
> Microsoft Exchange Server를 사용 하는 경우에도 Exchange 자동 검색 및 웹 서비스 Url에 대 한 리버스 프록시 규칙도 구성 해야 합니다.

</td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]
> 내부 배포가 둘 이상의 Standard Edition server 또는 프런트 엔드 풀로 구성 된 경우 각 외부 웹 팜 FQDN에 대해 웹 게시 규칙을 구성 해야 하며 각각에 대 한 인증서 및 웹 수신기가 필요 하거나 인증서를 받아야 합니다. 해당 주체 대체 이름에는 모든 풀에서 사용 되는 이름이 포함 되어 있으며, 웹 수신기에 할당 하 고, 여러 웹 게시 규칙 간에 공유 합니다.



</div>

<div>

## <a name="create-a-certificate-request"></a>인증서 요청 만들기

역방향 프록시에 대 한 인증서 요청을 만듭니다. 다른 컴퓨터에서 요청을 만들지만 공개 인증 기관에서 받은 인증서를 개인 키를 사용 하 여 내보낸 후 역방향 프록시로 가져와야 합니다.

<div>


> [!NOTE]
> 인증서 요청 또는 CSR (인증서 서명 요청)는 신뢰할 수 있는 CA (인증 기관)에 대 한 요청으로, 요청 하는 컴퓨터의 공개 키에 대 한 유효성을 검사 하 고 서명 합니다. 인증서가 생성 되 면 공개 키와 개인 키가 만들어집니다. 공개 키만 공유 되 고 서명 됩니다. 이름에서 알 수 있듯이 공개 키는 공개 요청에 대해 제공 됩니다. 공개 키는 정보를 안전 하 게 교환 하 고 컴퓨터 id를 확인 해야 하는 클라이언트, 서버 및 기타 요청자에 의해 사용 됩니다. 개인 키는 보호 된 상태로 유지 되며 공개 키를 사용 하 여 암호화 된 메시지의 암호를 해독 하기 위해 키 쌍을 만든 컴퓨터 에서만 사용 됩니다. 개인 키를 다른 목적으로 사용할 수 있습니다. 역방향 프록시를 위해 데이터 암호화가 기본 용도로 사용 됩니다. Secondarily는 인증서 키 수준의 인증서 인증을 사용할 수 있으며, 요청자에 게 컴퓨터의 공개 키가 있거나 해당 공개 키가 있는 컴퓨터가 실제로 주장 하는 컴퓨터 인지 확인 하는 경우에만 제한 됩니다.



</div>

<div>


> [!TIP]
> Edge 서버 인증서와 역방향 프록시 인증서를 동시에 계획 하는 경우 두 개의 인증서 요구 사항 사이에 상당한 유사도가 있다는 것을 확인 해야 합니다. Edge 서버 인증서를 구성 하 고 요청할 때 Edge 서버와 리버스 프록시 제목 대체 이름을 결합 합니다. 인증서와 개인 키를 내보내고 내보낸 파일을 리버스 프록시로 복사한 다음, 이후 절차에서 필요에 따라 인증서/키 쌍을 가져와 필요한 경우 역방향 프록시에 대해 동일한 인증서를 사용할 수 있습니다. Lync server 2013 및 lync server 2013의 역방향&nbsp;프록시 <A href="lync-server-2013-certificate-summary-reverse-proxy.md">인증서 요약-리버스 프록시의</A>edge 서버 계획에 대 한 edge server<A href="lync-server-2013-plan-for-edge-server-certificates.md">요금제</A> 의 인증서 요구 사항을 참조 하세요. 내보낼 수 있는 개인 키를 사용 하 여 인증서를 만들어야 합니다. 풀링된 Edge 서버에는 내보낼 수 있는 개인 키를 사용 하 여 인증서 및 인증서 요청 만들기가 필요 하므로,이는 일반적인 관행으로, Edge 서버용 Lync Server 배포 마법사의 인증서 마법사를 사용 하 여 <STRONG>개인 키 내보내기 가능한 사용자 만들기</STRONG> 플래그를 설정할 수 있습니다. 공용 인증 기관에서 인증서 요청을 받은 후에는 인증서와 개인 키를 내보냅니다. 개인 키를 사용 하 여 인증서를 만들고 내보내는 방법에 대 한 자세한 내용은 <A href="lync-server-2013-set-up-certificates-for-the-external-edge-interface.md">Lync Server 2013의 외부에 지 인터페이스</A> 에 대 한 인증서를 설정 하는 항목의 "풀의 Edge 서버의 개인 키를 사용 하 여 인증서를 내보내려면" 섹션을 참조 하세요. 인증서의 확장명은 .pfx 형식 이어야 합니다 <STRONG>.</STRONG>



</div>

인증서와 개인 키가 할당 될 컴퓨터에서 인증서 서명 요청을 생성 하려면 다음을 수행 합니다.

**인증서 서명 요청 만들기**

1.  MMC (Microsoft Management Console)를 열고 인증서 스냅인을 추가 하 고 **컴퓨터**를 선택한 다음 **개인**을 확장 합니다. MMC (Microsoft Management Console)에서 인증서 콘솔을 만드는 방법에 대 한 자세한 내용은을 참조 [http://go.microsoft.com/fwlink/?LinkId=282616](http://go.microsoft.com/fwlink/?linkid=282616)하세요.

2.  **인증서**를 마우스 오른쪽 단추로 클릭 하 고 **모든 작업**을 클릭 한 다음 **고급 작업**을 클릭 하 고 **사용자 지정 요청 만들기**를 클릭 합니다.

3.  **인증서 등록** 페이지에서 **다음**을 클릭 합니다.

4.  **인증서 등록 정책 선택** 페이지의 **사용자 지정 요청**에서 **등록 정책 없이 진행**을 선택 합니다. **다음**을 클릭 합니다.

5.  **사용자 지정 요청** 페이지에서 **서식 파일** 선택 **(템플릿 없음) 레거시 키** 다른 방법으로 인증서 공급자가 지정 하지 않는 한 **기본 확장명** 을 선택 하지 않은 상태로 유지 하 **고 \#PKCS 10**의 **요청 형식** 선택 항목을 해제 합니다. **다음**을 클릭 합니다.

6.  **인증서 정보** 페이지에서 **세부 정보**를 클릭 한 다음 **속성**을 클릭 합니다.

7.  **일반** 탭의 **인증서 속성** 페이지에서 **이름** 필드에이 인증서의 이름을 입력 합니다. 필요에 따라 **설명** 필드에 설명을 입력 합니다. 일반적으로 이름 및 설명은 관리자가 인증서 용도를 식별 하는 데 사용 됩니다 (예: **Lync Server의 리버스 프록시 수신기**).

8.  **제목** 탭을 선택 합니다. 유형의 **주체 이름** 에서 주체 **** 이름 유형의 **일반 이름을** 선택 합니다. 해당 **값**에는 리버스 프록시에 사용할 주체 이름을 입력 하 고 **추가**를 클릭 합니다. 이 항목의 표에 나와 있는 예제에서는 주체 이름이 webext.contoso.com 주체 이름에 대 한 값 필드에 입력 됩니다.

9.  **대체 이름**아래의 **제목** 탭에서 **유형에**대 한 드롭다운에서 **DNS** 를 선택 합니다. 인증서에 대해 요구 하는 정의 된 각 주체의 대체 이름에 대해 정규화 된 도메인 이름을 입력 한 다음 **추가**를 클릭 합니다. 예를 들어 표에는 세 가지 주제 대체 이름인 meet.contoso.com, dialin.contoso.com 및 lyncdiscover.contoso.com이 있습니다. **값** 필드에 meet.contoso.com를 입력 한 다음 **추가**를 클릭 합니다. 정의 해야 하는 각 주체의 대체 이름에 대해이를 반복 합니다.

10. **인증서 속성** 페이지에서 **확장** 탭을 클릭 합니다. 이 페이지에서는 **키 사용** 및 확장 키 사용 **(용도 정책)** 에서 확장 키 사용을 통해 암호화 키 용도를 정의 합니다.

11. **키 용도** 화살표를 클릭 하 여 **사용 가능한 옵션**을 표시 합니다. 사용 가능한 옵션에서 **디지털 서명을**클릭 한 다음 **추가**를 클릭 합니다. **키 암호화**를 클릭 한 다음 **추가**를 클릭 합니다. **이 키** 를 사용 하는 데 필요한 확인란의 선택을 취소 한 경우 확인란을 선택 합니다.

12. 확장 된 **키 사용 (응용 프로그램 정책)** 화살표를 클릭 하 여 **사용 가능한 옵션**을 표시 합니다. 사용 가능한 옵션에서 **서버 인증**을 클릭 한 다음 **추가**를 클릭 합니다. **클라이언트 인증**을 클릭 한 다음 **추가**를 클릭 합니다. **확장 키** 사용을 중요 한 것으로 설정 확인란을 선택 하는 경우 확인란을 선택 취소 합니다. 선택 해야 하는 키 용도 확인란에 반대 되는 것은 확장 된 키 사용 확인란이 선택 되어 있지 않은지 확인 해야 합니다.

13. **인증서 속성** 페이지에서 **개인 키** 탭을 클릭 합니다. **키 옵션** 화살표를 클릭 합니다. **키 크기**의 경우 드롭다운에서 **2048** 를 선택 합니다. 이 인증서를 대상으로 하는 역방향 프록시 이외의 컴퓨터에서이 키 쌍과 CSR을 생성 하는 경우 **개인 키를 내보낼 수 있도록 만들기**를 선택 합니다.
    
    <div>
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg398321.security(OCS.15).gif" title="보안이" alt="security" />보안 참고 사항:</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><strong>개인 키를 내보낼 수 있도록 만들기</strong> 를 선택 하는 것은 일반적으로 팜에 있는 각 컴퓨터에 인증서와 개인 키를 복사할 때 발생 하는 하나 이상의 역방향 프록시가 있는 경우에 적합 합니다. 내보낼 수 있는 개인 키를 허용 하는 경우 인증서와이를 생성 하는 컴퓨터를 추가로 주의 해야 합니다. 개인 키 (손상 된 경우)는 해당 인증서를 쓸모 없는 상태로 렌더링 하 고 컴퓨터 또는 컴퓨터를 외부 액세스 및 기타 보안 취약점에 노출 시킬 수 있습니다.</td>
    </tr>
    </tbody>
    </table>
    
    </div>

14. **개인 키** 탭에서 **키 유형** 화살표를 클릭 합니다. **Exchange** 옵션을 선택 합니다.

15. **확인** 을 클릭 하 여 설정한 **인증서 속성** 을 저장 합니다.

16. **인증서 등록** 페이지에서 **다음**을 클릭 합니다.

17. **오프 라인 요청을 어디에 저장 하 시겠습니까?** 페이지에서 **파일 이름과** 인증서 서명 요청을 저장할 **파일 형식을** 입력 하 라는 메시지가 표시 됩니다.

18. **파일 이름** 입력 필드에 요청의 경로와 파일 이름을 입력 하거나 **찾아보기를** 클릭 하 여 파일의 위치를 선택 하 고 요청에 대 한 파일 이름을 입력 합니다.

19. **파일 형식**에 대해 **Base 64** 또는 **Binary**를 클릭 합니다. 공급 업체에서 인증서에 대해 다른 방법으로 지시가 있지 않은 한 **기본 64** 를 선택 합니다.

20. 이전 단계에서 저장 한 요청 파일을 찾습니다. 공용 인증 기관에 제출 합니다.
    
    <div>
    

    > [!IMPORTANT]
    > Microsoft는 통합 커뮤니케이션 목적에 대 한 요구 사항을 충족 하는 공개 Ca를 확인 했습니다. 목록은 다음 기술 자료 문서에서 유지 관리 됩니다. <A href="http://go.microsoft.com/fwlink/?linkid=282625">http://go.microsoft.com/fwlink/?LinkId=282625</A>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

