---
title: 'Lync Server 2013: Lync Server 2013 제어판의 문제 해결'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Troubleshooting Lync Server 2013 Control Panel
ms:assetid: 54e7ab57-34ce-4a07-bcc9-643379eb4eb7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg195689(v=OCS.15)
ms:contentKeyID: 48184145
ms.date: 07/28/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 943f2ab5f0fe808d1bf5e10cf8b451ac1df2575b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985220"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="troubleshooting-lync-server-2013-control-panel"></a>Lync Server 2013 제어판의 문제 해결

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2016-07-28_

이 항목에서는 Lync Server 2013 제어판에 대 한 액세스 문제를 해결 하는 데 도움이 되는 정보 및 절차에 대해 설명 합니다.

<div>

## <a name="internet-browser-requirements"></a>인터넷 브라우저 요구 사항

Lync Server Control Panel을 사용 하려면 Microsoft Silverlight 브라우저 플러그 인 버전 4.0.50524.0 또는 최신 버전이 설치 되어 있어야 합니다. Silverlight가 설치 되어 있지 않거나 이전 버전이 설치 되어 있는 경우 메시지의 지침에 따라 필요한 버전을 설치 합니다.

<div>


> [!NOTE]  
> Lync server 제어판의 다른 소프트웨어 요구 사항은 Lync Server 제어판 및 다른 모든 Lync Server 2013 관리 도구를 설치할 수 있는 운영 체제와 관련이 있습니다. 자세한 내용은 지원 가능성 설명서의 <A href="lync-server-2013-server-and-tools-operating-system-support.md">Lync server 2013에서 서버 및 도구 운영 체제 지원을</A> 참조 하세요.



</div>

인터넷 브라우저가 보안 고려 사항으로 인해 Silverlight 설치를 차단 하는 경우 Lync Server 제어판을 여는 URL (Uniform Resource Locator)을 신뢰할 수 있는 사이트 목록에 추가 합니다. Internet Explorer 보안 설정에서 **ActiveX 컨트롤 및 플러그 인 실행** 이 **사용**으로 설정 되어 있는지 확인 합니다. 자세한 내용은을 참조 [http://go.microsoft.com/fwlink/p/?linkId=214060](http://go.microsoft.com/fwlink/p/?linkid=214060)하세요. 또한 브라우저가 SSL 3.0을 사용 하도록 구성 되어 있는지 확인 합니다.

인터넷 브라우저가 프록시 서버를 사용 하도록 구성 된 경우 브라우저가 내부 사이트로 자동으로 감지 되는 사이트에 대해 프록시 서버를 우회 하도록 구성 되어 있는지 확인 합니다. 또는 프록시 서버 구성 설정에서 브라우저의 예외 목록에 주소를 추가 합니다.

</div>

<div>

## <a name="dns-record-and-certificate-requirements-for-the-administrative-access-url"></a>관리 액세스 URL에 대 한 DNS 레코드 및 인증서 요구 사항

Lync Server 제어판에 액세스 하기 위한 간단한 URL을 구성한 경우에는 해당 관리 액세스 URL을 사용 하는 데 필요한 정적 DNS (Domain Name System) 호스트 (A) 리소스 레코드와 인증서도 구성 되어 있어야 합니다. 언제 든 지 기본 URL을 변경 하는 경우, 변경 내용이 적절 한 DNS 레코드 및 인증서에 반영 되 고 각 디렉터 및 프런트 엔드 서버에서 *CsComputer* 를 실행 하 여 변경 내용을 등록 하도록 합니다. 자세한 내용은 계획 설명서의 다음 항목을 참조 하세요.

  - [Lync Server 2013의 단순 URL 계획](lync-server-2013-planning-for-simple-urls.md)

  - [Lync Server 2013의 단순 URL에 대한 DNS 요구 사항](lync-server-2013-dns-requirements-for-simple-urls.md)

  - [Lync Server 2013의 내부 서버에 대한 인증서 요구 사항](lync-server-2013-certificate-requirements-for-internal-servers.md)

관리 액세스 URL을 구성 하는 단계별 절차는 배포 설명서의 [Lync Server 2013에서 간단한 Url 편집 또는 구성을](lync-server-2013-edit-or-configure-simple-urls.md) 참조 하세요.

</div>

<div>

## <a name="internet-information-services-iis-requirements"></a>IIS (인터넷 정보 서비스) 요구 사항

Lync Server 제어판은 IIS (인터넷 정보 서비스)를 필요로 하는 Lync Server 2013의 구성 요소 중 하나입니다. 특히, HTTP 리디렉션 및 Windows 인증 기능을 사용 하도록 설정 하 고 W3SVC (World Wide Web Publishing 서비스)가 실행 중인지 확인 합니다.

<div>

## <a name="world-wide-publishing-service-windows-service-dependency"></a>World Wide Publishing 서비스 (Windows 서비스) 종속성

World Wide Web Publishing 서비스를 중지할 경우 Lync Server 제어판에 액세스할 수 없습니다. Windows 서비스 MMC (Microsoft Management Console)를 사용 하 여 서비스를 다시 시작할 수 있습니다.

**World Wide Web Publishing 서비스를 시작 하려면**

1.  IIS (인터넷 정보 서비스)의 일부로 World Wide Web Publishing 서비스가 설치 되어 있는 컴퓨터에 로그온 합니다.

2.  **시작**을 클릭 하 고 **관리 도구**를 클릭 한 다음 **서비스**를 클릭 합니다.

3.  **World Wide Web Publishing 서비스**를 마우스 오른쪽 단추로 클릭 한 다음 **시작**을 클릭 합니다.

</div>

<div>

## <a name="application-pool-mode"></a>응용 프로그램 풀 모드

CsManagementAppPool 응용 프로그램 풀이 네트워크 서비스 계정을 프로세스 모델 id로 사용 하도록 IIS를 구성 합니다.

</div>

</div>

<div>

## <a name="user-rights-and-permissions"></a>사용자 권한 및 사용 권한

CsAdministrator 그룹의 구성원 인 도메인 계정을 사용 하거나 사용자 권한 및 사용 권한을 위임한 계정을 사용 하 여 Lync Server 제어판에 로그인 해야 합니다. 로컬 컴퓨터 계정을 사용 하 여 Lync Server 제어판에 로그인 할 수 없습니다. RBAC (역할 기반 액세스 제어)를 통해 관리 작업을 위임 하는 방법에 대 한 자세한 내용은 계획 문서에서 [Lync Server 2013의 역할 기반 액세스 제어 계획](lync-server-2013-planning-for-role-based-access-control.md) 을 참조 하세요.

간단한 URL을 사용 하 여 Lync Server 제어판에 액세스 하는 경우 웹 서버가 RTCUniversalServerAdmins 및 RTCUniversalUserAdmins 그룹에 추가 되어 있는지 확인 합니다.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013 관리 도구](lync-server-2013-lync-server-administrative-tools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

