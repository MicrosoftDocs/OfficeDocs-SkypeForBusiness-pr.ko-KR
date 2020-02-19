---
title: 'Lync Server 2013: Lync Server 2013 제어판 문제 해결'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Troubleshooting Lync Server 2013 Control Panel
ms:assetid: 54e7ab57-34ce-4a07-bcc9-643379eb4eb7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg195689(v=OCS.15)
ms:contentKeyID: 48184145
ms.date: 07/28/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 07e670dc0871490e513023d3276ad80126be173b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141051"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="troubleshooting-lync-server-2013-control-panel"></a>Lync Server 2013 제어판 문제 해결

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2016-07-28_

이 항목에서는 Lync Server 2013 제어판에 대 한 액세스 문제를 해결 하는 데 도움이 되는 정보 및 절차를 제공 합니다.

<div>

## <a name="internet-browser-requirements"></a>인터넷 브라우저 요구 사항

Lync Server Control Panel을 사용 하려면 Microsoft Silverlight browser 플러그 인 버전 4.0.50524.0 또는 최신 버전이 설치 되어 있어야 합니다. Silverlight가 설치 되어 있지 않거나 이전 버전이 설치 되어 있는 경우 메시지의 지침에 따라 필요한 버전을 설치 합니다.

<div>


> [!NOTE]  
> Lync Server 제어판의 기타 소프트웨어 요구 사항은 Lync Server 제어판과 기타 모든 Lync Server 2013 관리 도구를 설치할 수 있는 운영 체제와 관련이 있습니다. 자세한 내용은 지원 가능성 설명서의 <A href="lync-server-2013-server-and-tools-operating-system-support.md">Lync server 2013에서 서버 및 도구 운영 체제 지원을</A> 참조 하십시오.



</div>

인터넷 브라우저가 보안 고려 사항으로 인해 Silverlight 설치를 차단 하는 경우 Lync Server 제어판을 여는 URL (Uniform Resource Locator)을 신뢰할 수 있는 사이트 목록에 추가 합니다. Internet Explorer 보안 설정에서 **ActiveX 컨트롤 및 플러그인 실행**이 **사용**으로 설정되었는지 확인합니다. 자세한 내용은를 참조 [https://go.microsoft.com/fwlink/p/?linkId=214060](https://go.microsoft.com/fwlink/p/?linkid=214060)하세요. 또한 브라우저가 SSL 3.0을 사용하도록 구성되었는지 확인합니다.

인터넷 브라우저가 프록시 서버를 사용하도록 구성된 경우 자동으로 내부 사이트로 검색된 사이트에 대해 프록시 서버를 바이패스하도록 브라우저가 구성되었는지 확인합니다. 또는 프록시 서버 구성 설정에서 해당 주소를 브라우저의 예외 목록에 추가합니다.

</div>

<div>

## <a name="dns-record-and-certificate-requirements-for-the-administrative-access-url"></a>관리 액세스 URL에 대한 DNS 레코드 및 인증서 요구 사항

Lync Server 제어판에 액세스 하기 위한 단순 URL을 구성한 경우에는이 관리 액세스 URL을 사용 하는 데 필요한 정적 DNS (Domain Name System) 호스트 (A) 리소스 레코드 및 인증서도 구성 해야 합니다. 언제 든 지 기본 URL을 변경 하는 경우 변경 내용이 적절 한 DNS 레코드 및 인증서에 반영 되 고 각 디렉터 및 프런트 엔드 서버에서 *사용 하도록 설정 된 컴퓨터* 를 실행 하 여 변경 내용을 등록 했는지 확인 합니다. 자세한 내용은 계획 설명서에서 다음 항목들을 참조하십시오.

  - [Lync Server 2013의 단순 Url 계획](lync-server-2013-planning-for-simple-urls.md)

  - [Lync Server 2013의 단순 Url에 대 한 DNS 요구 사항](lync-server-2013-dns-requirements-for-simple-urls.md)

  - [Lync Server 2013의 내부 서버에 대 한 인증서 요구 사항](lync-server-2013-certificate-requirements-for-internal-servers.md)

관리 액세스 URL을 구성 하는 단계별 절차에 대 한 자세한 내용은 배포 설명서에서 [Lync Server 2013의 단순 Url 편집 또는 구성을](lync-server-2013-edit-or-configure-simple-urls.md) 참조 하십시오.

</div>

<div>

## <a name="internet-information-services-iis-requirements"></a>IIS(인터넷 정보 서비스) 요구 사항

Lync Server 제어판은 IIS (인터넷 정보 서비스)가 필요한 Lync Server 2013의 구성 요소 중 하나입니다. 특히 HTTP 리디렉션 및 Windows 인증 기능이 사용하도록 설정되었고 W3SVC(World Wide Web Publishing Service)가 실행 중인지 확인합니다.

<div>

## <a name="world-wide-publishing-service-windows-service-dependency"></a>World Wide Publishing Service(Windows Service) 종속성

World Wide Web Publishing 서비스가 중지 되 면 Lync Server 제어판에 액세스할 수 없습니다. Windows Services MMC(Microsoft Management Console)를 사용하여 서비스를 다시 시작할 수 있습니다.

**World Wide Web Publishing Service를 시작하려면**

1.  World Wide Web Publishing 서비스가 IIS (인터넷 정보 서비스)의 일부로 설치 된 컴퓨터에 로그온 합니다.

2.  **시작**, **관리 도구**, **서비스**를 클릭합니다.

3.  **World Wide Web Publishing Service**를 마우스 오른쪽 단추로 클릭한 후 **시작**을 클릭합니다.

</div>

<div>

## <a name="application-pool-mode"></a>응용 프로그램 풀 모드

CsManagementAppPool 응용 프로그램 풀에서 네트워크 서비스 계정을 프로세스 모델 ID로 사용하도록 IIS를 구성합니다.

</div>

</div>

<div>

## <a name="user-rights-and-permissions"></a>사용자 권한 및 사용 권한

CsAdministrator 그룹의 구성원 인 도메인 계정을 사용 하거나 사용자 권한 및 사용 권한을 위임한 계정을 사용 하 여 Lync Server 제어판에 로그인 해야 합니다. 로컬 컴퓨터 계정을 사용 하 여 Lync Server 제어판에 로그인 할 수 없습니다. RBAC (역할 기반 액세스 제어)를 통해 관리 작업을 위임 하는 방법에 대 한 자세한 내용은 계획 설명서의 [Lync Server 2013에서 역할 기반 액세스 제어 계획](lync-server-2013-planning-for-role-based-access-control.md) 을 참조 하십시오.

단순 URL을 사용 하 여 Lync Server 제어판에 액세스 하는 경우 웹 서버가 RTCUniversalServerAdmins 및 RTCUniversalUserAdmins 그룹에 추가 되어 있는지 확인 합니다.

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

