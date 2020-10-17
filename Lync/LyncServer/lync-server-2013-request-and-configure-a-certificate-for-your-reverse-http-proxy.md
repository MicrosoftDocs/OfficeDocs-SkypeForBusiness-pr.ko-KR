---
title: 역방향 HTTP 프록시에 대 한 인증서 요청 및 구성
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
ms.openlocfilehash: 7651e3da61e5ca197d36ca59ad8216af4c0188af
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511985"
---
# <a name="request-and-configure-a-certificate-for-your-reverse-http-proxy-in-lync-server-2013"></a>Lync Server 2013에서 역방향 HTTP 프록시에 대 한 인증서 요청 및 구성

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2014-02-14_

Microsoft Lync Server 2013을 실행 하는 내부 서버에 서버 인증서를 발급 한 CA 인프라에 대해 Microsoft Forefront Threat Management Gateway 2010 또는 IIS ARR을 실행 하는 서버에 루트 CA (인증 기관) 인증서를 설치 해야 합니다.

또한 역방향 프록시 서버에 공용 웹 서버 인증서를 설치해야 합니다. 이 인증서의 주체 대체 이름에는 원격 액세스가 가능하도록 설정된 사용자의 홈인 각 풀의 게시된 외부 FQDN(정규화된 도메인 이름)과 해당 에지 인프라 내에서 사용될 모든 디렉터 또는 디렉터 풀의 외부 FQDN이 포함되어야 합니다. 또한 주체 대체 이름은 모임 단순 URL과 전화 접속 단순 URL을 포함해야 하며, 모바일 응용 프로그램을 배포하고 자동 검색을 사용하려는 경우에는 아래 표에 나와 있는 외부 자동 검색 서비스 URL도 포함해야 합니다.


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
<th>예제</th>
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
> 주체 이름도 주체 대체 이름에 있어야 합니다.

</td>
</tr>
<tr class="odd">
<td><p>주체 대체 이름</p></td>
<td><p>선택적 디렉터 웹 서비스 (디렉터가 배포 된 경우)</p></td>
<td><p>webdirext.contoso.com</p></td>
</tr>
<tr class="even">
<td><p>주체 대체 이름</p></td>
<td><p>모임 단순 URL</p>



> [!NOTE]
> 모든 모임 단순 URL은 주체 대체 이름에 있어야 합니다. 각 SIP 도메인에는 하나 이상의 활성 모임 단순 URL이 있어야 합니다.

</td>
<td><p>meet.contoso.com</p></td>
</tr>
<tr class="odd">
<td><p>주체 대체 이름</p></td>
<td><p>전화 접속 단순 URL</p></td>
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
> Microsoft Exchange Server도 사용 하는 경우에는 Exchange 자동 검색 및 웹 서비스 Url에 대 한 역방향 프록시 규칙도 구성 해야 합니다.

</td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]
> 내부 배포가 둘 이상의 Standard Edition 서버 또는 프런트 엔드 풀로 구성되는 경우에는 각 외부 웹 팜 FQDN에 대해 웹 게시 규칙을 구성해야 하고 각 항목에 대해 인증서와 웹 수신기가 필요하게 됩니다. 아니면, 해당 주체 대체 이름이 모든 풀에서 사용되는 이름을 포함하는 인증서를 가져와서 웹 수신기에 지정한 다음 여러 웹 게시 규칙 간에 공유해야 합니다.



</div>

<div>

## <a name="create-a-certificate-request"></a>인증서 요청 만들기

역방향 프록시에 대 한 인증서 요청을 만듭니다. 다른 컴퓨터에서 요청을 만들었지만 공개 인증 기관에서 받은 인증서를 가져온 후에 개인 키를 사용 하 여이 사용자를 역방향 프록시로 내보내야 합니다.

<div>


> [!NOTE]
> 인증서 요청 또는 CSR (인증서 서명 요청)은 신뢰할 수 있는 공용 CA (인증 기관)에 대 한 요청으로, 해당 컴퓨터의 공개 키에 대 한 유효성을 검사 하 고 서명 합니다. 인증서가 생성 되 면 공개 키와 개인 키가 만들어집니다. 공개 키만 공유 및 서명 됩니다. 이름에서 알 수 있듯이 공개 키는 공용 요청에 사용 가능 하도록 구성 됩니다. 공개 키는 정보를 안전 하 게 교환 하 고 컴퓨터 id를 확인 해야 하는 클라이언트, 서버 및 기타 요청자에서 사용 합니다. 개인 키는 보호 된 상태로 유지 되며, 공개 키로 암호화 된 메시지를 해독 하기 위해 키 쌍을 만든 컴퓨터 에서만 사용 됩니다. 개인 키를 다른 용도로 사용할 수 있습니다. 역방향 프록시를 사용 하는 경우에는 데이터 암호화가 기본 용도입니다. Secondarily에서 인증서 키 수준의 인증서 인증을 사용할 수 있으며, 해당 요청에 컴퓨터의 공개 키가 있거나, 공개 키가 있는 컴퓨터가 실제로 주장 하는 컴퓨터 인지 확인 하기 위한 유효성 검사로만 제한 됩니다.



</div>

<div>


> [!TIP]
> 에 지 서버 인증서와 역방향 프록시 인증서를 동시에 계획 하는 경우 두 가지 인증서 요구 사항 사이에 많은 유사도가 있다는 것을 알 수 있습니다. 에 지 서버 인증서를 구성 하 고 요청 하는 경우에 지 서버 및 역방향 프록시 주체 대체 이름을 결합 합니다. 인증서와 개인 키를 내보내고 내보낸 파일을 역방향 프록시로 복사한 다음 앞으로의 절차에서 필요에 따라 인증서/키 쌍을 가져오는 경우 역방향 프록시에 대해 동일한 인증서를 사용할 수 있습니다. Lync server 2013의 &nbsp; <A href="lync-server-2013-plan-for-edge-server-certificates.md">lync server 2013</A> 및 역방향 프록시 <A href="lync-server-2013-certificate-summary-reverse-proxy.md">인증서 요약-역방향 프록시</A>에서 edge 서버 요금제에 대 한 인증서 요구 사항을 참조 하세요. 내보낼 수 있는 개인 키를 사용 하 여 인증서를 만들어야 합니다. 풀링된에 지 서버에는 내보낼 수 있는 개인 키를 사용 하 여 인증서 및 인증서 요청 만들기가 필요 하므로,이는 일반적인 관행으로,에 지 서버에 대 한 Lync Server 배포 마법사의 인증서 마법사를 사용 하 여 <STRONG>개인 키 내보내기 가능</STRONG> 플래그를 설정 하면 됩니다. 공용 인증 기관에서 인증서 요청을 받은 후에는 인증서와 개인 키를 내보냅니다. 개인 키를 사용 하 여 인증서를 만들고 내보내는 방법에 대 한 자세한 내용은 " <A href="lync-server-2013-set-up-certificates-for-the-external-edge-interface.md">Lync Server 2013에</A> 대 한 외부에 지 서버의 개인 키로 인증서 내보내기" 섹션을 참조 하십시오. 인증서의 확장명은 <STRONG>.pfx</STRONG>형식 이어야 합니다.



</div>

인증서와 개인 키가 할당 될 컴퓨터에서 인증서 서명 요청을 생성 하려면 다음을 수행 합니다.

**인증서 서명 요청 만들기**

1.  MMC (Microsoft Management Console)를 열고 인증서 스냅인을 추가 하 고 **컴퓨터**를 선택한 다음 **개인**을 확장 합니다. MMC (Microsoft Management Console)에서 인증서 콘솔을 만드는 방법에 대 한 자세한 내용은를 참조 하세요 [https://go.microsoft.com/fwlink/?LinkId=282616](https://go.microsoft.com/fwlink/?linkid=282616) .

2.  **인증서**를 마우스 오른쪽 단추로 클릭 하 고 **모든 작업**, **고급 작업**을 차례로 클릭 한 다음 **사용자 지정 요청 만들기**를 클릭 합니다.

3.  **인증서 등록** 페이지에서 **다음**을 클릭 합니다.

4.  **인증서 등록 정책 선택** 페이지의 **사용자 지정 요청**에서 **등록 정책 없이 계속**을 선택 합니다. **다음**을 클릭합니다.

5.  **사용자 지정 요청** 페이지에서 **서식 파일** 선택 **(서식 파일 없음) 레거시 키** 다른 방식으로 인증서 공급자가 지정 되지 않은 경우 **기본 확장명** 을 선택 하지 않은 상태로 설정 하 고 **PKCS \# 10**에 대해 **형식 요청** 선택을 유지 합니다. **다음**을 클릭합니다.

6.  **인증서 정보** 페이지에서 **세부 정보**를 클릭 한 다음 **속성**을 클릭 합니다.

7.  **인증서 속성** 페이지의 **이름** 필드에 있는 **일반** 탭에서이 인증서의 이름을 입력 합니다. 필요한 경우 **설명** 필드에 설명을 입력 합니다. 일반적으로 이름 및 설명은 **Lync Server의 역방향 프록시 수신기**와 같이 관리자가 인증서 용도를 식별 하는 데 사용 됩니다.

8.  **제목** 탭을 선택 합니다. 유형의 **주체 이름** 에서 주체 **Type**이름 유형의 **일반 이름을** 선택 합니다. 이 **값**에 대해 역방향 프록시에 사용할 주체 이름을 입력 한 다음 **추가**를 클릭 합니다. 이 항목의 표에서 제공 하는 예에서 주체 이름은 webext.contoso.com 이며 주체 이름에 대 한 값 필드에 입력 됩니다.

9.  **대체 이름**아래의 **제목** 탭에서 **유형에**대해 드롭다운에서 **DNS** 를 선택 합니다. 인증서에 필요한 각 정의 된 주체 대체 이름에 대해 정규화 된 도메인 이름을 입력 한 다음 **추가**를 클릭 합니다. 예를 들어이 표에는 meet.contoso.com, dialin.contoso.com 및 lyncdiscover.contoso.com의 세 가지 주체 대체 이름이 있습니다. **값** 필드에 meet.contoso.com를 입력 하 고 **추가**를 클릭 합니다. 정의 해야 하는 각 주체 대체 이름에 대해이 방법을 반복 합니다.

10. **인증서 속성** 페이지에서 **확장** 탭을 클릭 합니다. 이 페이지에서는 **키 사용** 에 대 한 암호화 키 용도와 **확장 키 사용 (응용 프로그램 정책)** 의 확장 된 키 사용을 정의 합니다.

11. **키 사용** 화살표를 클릭 하 여 **사용 가능한 옵션**을 표시 합니다. 사용 가능한 옵션에서 **디지털 서명을**클릭 한 다음 **추가**를 클릭 합니다. **키 암호화**를 클릭 한 다음 **추가**를 클릭 합니다. 이러한 키 사용을 **필수로 설정** 확인란의 선택을 취소 한 경우에는 확인란을 선택 합니다.

12. 확장 된 **키 사용 (응용 프로그램 정책)** 화살표를 클릭 하 여 **사용 가능한 옵션**을 표시 합니다. 사용 가능한 옵션에서 **서버 인증**을 클릭 하 고 **추가**를 클릭 합니다. **클라이언트 인증**을 클릭 하 고 **추가**를 클릭 합니다. **확장 키** 사용을 필수로 설정 확인란을 선택 하는 경우 확인란을 선택 취소 합니다. 키 사용 확인란 (선택 해야 함)과는 반대로, 확장 된 키 사용 확인란이 선택 되어 있지 않아야 합니다.

13. **인증서 속성** 페이지에서 **개인 키** 탭을 클릭 합니다. **키 옵션** 화살표를 클릭 합니다. **키 크기**의 경우 드롭다운에서 **2048** 을 선택 합니다. 이 인증서에 해당 하는 역방향 프록시가 아닌 다른 컴퓨터에서이 키 쌍과 CSR을 생성 하려면 **개인 키를 내보낼 수 있도록 만들기**를 선택 합니다.
    
    <div>
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg398321.security(OCS.15).gif" title="보안이" alt="security" />보안 메모:</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>팜에 있는 각 컴퓨터에 인증서와 개인 키를 복사 하기 때문에 나중에 <strong>개인 키를 내보낼 수 있도록 설정</strong> 하는 것이 좋습니다. 내보낼 수 있는 개인 키를 허용 하는 경우 인증서 및이를 생성 하는 컴퓨터를 추가로 주의 해야 합니다. 개인 키가 손상 된 경우에는 인증서가 쓸모 없게 되 고 컴퓨터 또는 컴퓨터가 외부 액세스 및 기타 보안 취약성에 노출 될 수 있습니다.</td>
    </tr>
    </tbody>
    </table>
    
    </div>

14. **개인 키** 탭에서 **키 유형** 화살표를 클릭 합니다. **Exchange** 옵션을 선택 합니다.

15. **확인** 을 클릭 하 여 설정한 **인증서 속성** 을 저장 합니다.

16. **인증서 등록** 페이지에서 **다음**을 클릭 합니다.

17. **오프 라인 요청을 어디에 저장** 하 시겠습니까? 페이지에서 **파일 이름** 및 인증서 서명 요청을 저장할 **파일 형식을 지정** 하 라는 메시지가 표시 됩니다.

18. **파일 이름** 입력 필드에 요청의 경로와 파일 이름을 입력 하거나, **찾아보기를** 클릭 하 여 파일의 위치를 선택 하 고 요청의 파일 이름을 입력 합니다.

19. **파일 형식**에 대해 **기본 64** 또는 **이진**을 클릭 합니다. 인증서에 대 한 공급 업체가 다른 방식으로 지시 하지 않는 한 **기본 64** 를 선택 합니다.

20. 이전 단계에서 저장 한 요청 파일을 찾습니다. 공용 인증 기관에 전송 합니다.
    
    <div>
    

    > [!IMPORTANT]
    > Microsoft는 통합 통신 목적에 대 한 요구 사항을 충족 하는 공용 Ca를 확인 했습니다. 목록은 다음 기술 자료 문서에 유지 됩니다. <A href="https://go.microsoft.com/fwlink/?linkid=282625">https://go.microsoft.com/fwlink/?LinkId=282625</A>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

