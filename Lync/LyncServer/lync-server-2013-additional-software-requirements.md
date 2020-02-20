---
title: 'Lync Server 2013: 추가 소프트웨어 요구 사항'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Additional software requirements
ms:assetid: 87b318e3-03ae-41f7-af5e-29bb294f6af0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398686(v=OCS.15)
ms:contentKeyID: 48184731
ms.date: 12/09/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e725c4c425492316d13b4a1f5957e37199f1521f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146041"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="additional-software-requirements-for-lync-server-2013"></a>Lync Server 2013의 추가 소프트웨어 요구 사항

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2016-12-08_

Lync Server 2013에서는 서버 플랫폼의 하드웨어 및 운영 체제 요구 사항 외에도 배포 하는 서버에 추가 소프트웨어를 설치 해야 합니다.

<div>


> [!NOTE]  
> Lync Server를 실행 하는 서버의 플랫폼 요구 사항에 대 한 자세한 내용은 lync server <A href="lync-server-2013-server-hardware-platforms.md">2013에 대 한 서버 하드웨어 플랫폼</A> 및 <A href="lync-server-2013-server-and-tools-operating-system-support.md">lync Server 2013의 서버 및 도구 운영 체제 지원을</A>참조 하십시오. 클라이언트 컴퓨터 및 장치에 대 한 시스템 요구 사항에 대 한 자세한 내용은 계획 설명서에서 <A href="lync-server-2013-planning-for-clients-and-devices.md">Lync Server 2013의 클라이언트 및 장치에 대 한 계획</A> 을 참조 하십시오. 관리 도구에 대 한 소프트웨어 요구 사항에 대 한 자세한 내용은 <A href="lync-server-2013-administrative-tools-software-requirements.md">Lync Server 2013의 관리 도구 소프트웨어 요구 사항을</A>참조 하세요.



</div>

<div>

## <a name="additional-software-necessary-for-all-internal-server-roles"></a>모든 내부 서버 역할에 필요한 추가 소프트웨어

이 섹션에는 모든 내부 서버 역할 (에 지 서버를 제외한 모든 Lync Server 서버 역할)에 필요한 소프트웨어가 나열 되어 있습니다. 에 지 서버 및에 지 풀에 대 한 요구 사항은이 항목의 뒷부분에 있는 **추가 소프트웨어의에 지 서버에**나열 되어 있습니다.

</div>

<div>

## <a name="windows-powershell-30"></a>Windows PowerShell 3.0

Lync Server 2013을 실행 하는 각 서버에 올바른 버전의 Windows PowerShell 3.0이 설치 되어 있어야 합니다. 자세한 내용은 [설치 Windows PowerShell 3.0 For Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md)을 참조 하십시오.

</div>

<div>

## <a name="microsoft-net-framework-45"></a>Microsoft .NET Framework 4.5

Lync Server에는 모든 내부 서버 역할 및 Lync Server 관리 도구 또는 Microsoft Lync Server 2013, 계획 도구를 실행 하는 모든 컴퓨터에 Microsoft .NET Framework 4.5이 필요 합니다. Lync Server 2013의 경우 Lync Server 2013을 설치 하기 전에 서버에 64 비트 버전의 Microsoft .NET Framework 4.5을 수동으로 설치 해야 합니다. 이를 수동으로 설치 하려면 Microsoft 다운로드 센터에서 Microsoft .NET 4.5 Framework를 다운로드 하세요.[https://go.microsoft.com/fwlink/p/?LinkId=268529](https://go.microsoft.com/fwlink/p/?linkid=268529)

<div>

## <a name="installing-microsoft-net-framework-45-on-servers-running-windows-server-2012"></a>Windows Server 2012를 실행 하는 서버에 Microsoft .NET Framework 4.5 설치

Lync Server 2013 및 Windows Server 2012을 실행할 서버에 Microsoft .NET Framework 4.5을 설치 하는 경우에는 하나의 추가 단계를 수행 해야 합니다. .NET Framework 4.5이 설치 되 면 서버 관리자를 사용 하 여 HTTP 정품 인증을 설치 합니다.

**Windows Server 2012에서 .NET 4.5 HTTP 정품 인증을 설치 하려면**

1.  **시작** 메뉴에서 **프로그램**, **관리 도구**를 차례로 클릭 한 다음 **서버 관리자**를 클릭 합니다.

2.  서버 관리자의 **기능 요약**에서 **기능 추가**를 선택 합니다.

3.  **.Net Framework 4.5**를 확장 합니다.

4.  **WCF 활성화** 가 아직 선택 되어 있지 않으면 선택 합니다. 그런 다음 **HTTP 정품 인증**을 선택 합니다.

5.  **다음** 을 클릭 하 고 화면의 지시에 따라 설치를 완료 합니다.

</div>

</div>

<div>

## <a name="windows-identity-foundation"></a>Windows Identity Foundation

Lync Server 2013의 **Windows Identity foundation** 을 사용 하려면 서버 간 인증 시나리오를 지원 하기 위해 Windows identity foundation을 설치 해야 합니다. Windows Server 2008 R2 및 Windows Server 2012을 설치 하려면 다른 절차가 필요 합니다. 다음 목록에서 서버 운영 체제를 선택 합니다.

  - Windows server 2008 r 2의 경우 컴퓨터에 이미 설치 되어 있는지 확인 합니다. 2008 이렇게 하려면 **프로그램 추가/제거**, **설치 된 업데이트 보기**및 **windows** 에서 windows **Identity Foundation (KB974405)** 항목을 확인 하세요. Windows Identity Foundation을 설치 하는 방법에 [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657)대 한 자세한 내용은를 참조 하세요.

  - Windows server 2012 For Windows Server 2012의 경우 **서버 관리자** 를 사용 하 여 Windows Identity Foundation을 설치 합니다. 서버 관리자 **역할 및 기능 추가 마법사**에서 **기능**을 선택 합니다. 목록에서 **Windows Identity Foundation 3.5** 을 선택 합니다. **다음**을 클릭 하 고 **설치**를 클릭 합니다.

</div>

<div>

## <a name="additional-software-for-all-front-end-servers-and-standard-edition-servers"></a>모든 프런트 엔드 서버 및 Standard Edition Server에 대 한 추가 소프트웨어

또한 모든 프런트 엔드 서버 및 Standard Edition 서버에서 특정 모듈을 사용 하 여 IIS (인터넷 정보 서비스)를 실행 해야 합니다. 또한 회의, 통화 대기 응용 프로그램, 알림 또는 응답 그룹이 배포 되는 모든 프런트 엔드 서버 및 Standard Edition 서버는 Windows Media 형식 런타임을 실행 해야 합니다.

<div>

## <a name="internet-information-services-iis"></a>IIS(인터넷 정보 서비스)

프런트 엔드 서버 및 Standard Edition 서버는 다음 모듈을 사용 하 여 IIS (인터넷 정보 서비스)를 실행 해야 합니다.

  - 정적 콘텐츠

  - 기본 문서

  - HTTP 오류

  - ASP.NET

  - .NET 확장성

  - ISAPI(인터넷 서버 API) 확장

  - ISAPI 필터

  - HTTP 로깅

  - 로깅 도구

  - 추적은

  - Windows 인증

  - 요청 필터링

  - 정적 콘텐츠 압축

  - 동적 콘텐츠 압축

  - IIS 관리 콘솔

  - IIS 관리 스크립트 및 도구

  - 익명 인증 (IIS가 설치 될 때 기본적으로 설치 됩니다.)

  - 클라이언트 인증서 매핑 인증

</div>

<div>

## <a name="windows-media-format-runtime-and-windows-desktop-experience"></a>Windows Media 형식 런타임 및 Windows 데스크톱 환경

**Windows 데스크톱 환경** 회의를 배포할 모든 프런트 엔드 서버 및 Standard Edition 서버에 windows Media 형식 런타임이 설치 되어 있어야 하며,이는 windows Server 2012를 제외 하 고 windows 데스크톱 환경의 일부로 설치 됩니다. Windows Server 2012에는 Microsoft Media Foundation이 필요 합니다. Windows Media 형식 런타임은 통화 대기, 알림 및 응답 그룹 응용 프로그램에서 알림 및 음악에 대해 재생하는 Windows Media Audio(.wma) 파일을 실행하는 데 필요합니다.

Lync Server 2013을 설치 하기 전에 Windows 데스크톱 환경을 설치 하는 것이 좋습니다. Lync Server 2013이 서버에서이 소프트웨어를 찾지 못하는 경우 설치 하 라는 메시지가 표시 되 고 서버를 다시 시작 하 여 설치를 완료 해야 합니다.

</div>

</div>

<div>

## <a name="additional-software-for-front-end-servers-and-standard-edition-servers-running-on-windows-server-2012"></a>Windows Server 2012에서 실행 되는 프런트 엔드 서버 및 Standard Edition Server 용 추가 소프트웨어

프런트 엔드 서버에는 Windows Server 2012에 기본적으로 설치 되지 않는 .NET 3.5이 필요 합니다. 설치 하려면 Windows Server 2012 설치 미디어를 D 드라이브에 넣고 다음을 입력 합니다.

    Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Desktop-Experience, Telnet-Client, BITS -Source D:\sources\sxs

Windows Server 2012을 실행 하는 서버에 .NET 3.5을 설치 하는 방법에 대 한 자세한 내용은의 " <https://go.microsoft.com/fwlink/p/?linkid=275032>Microsoft .net Framework 3.5 배포 고려 사항"을 참조 하십시오.

</div>

<div>

## <a name="additional-software-for-directors"></a>디렉터용 추가 소프트웨어

디렉터는 다음 모듈을 사용 하 여 IIS (인터넷 정보 서비스)를 실행 해야 합니다.

  - 정적 콘텐츠

  - 기본 문서

  - HTTP 오류

  - ASP.NET

  - .NET 확장성

  - ISAPI(인터넷 서버 API) 확장

  - ISAPI 필터

  - HTTP 로깅

  - 로깅 도구

  - 추적은

  - Windows 인증

  - 요청 필터링

  - 정적 콘텐츠 압축

  - IIS 관리 콘솔

  - IIS 관리 스크립트 및 도구

  - 익명 인증(IIS 설치 시 기본적으로 설치됨)

  - 클라이언트 인증서 매핑 인증

</div>

<div>

## <a name="additional-software-for-persistent-chat-front-end-servers"></a>영구 채팅 프런트 엔드 서버용 추가 소프트웨어

영구 채팅 프런트 엔드 서버는 Windows Server의 구성 요소인 메시지 큐 (MSMQ 라고도 함)를 실행 해야 합니다.

MSMQ 사용에 대 한 자세한 내용은 [여기를 클릭 하세요.](https://technet.microsoft.com/library/cc771474.aspx)

</div>

<div>

## <a name="additional-software-for-edge-servers"></a>에 지 서버용 추가 소프트웨어

에 지 서버에는 다음 소프트웨어가 필요 합니다.

  - Lync Server 2013을 실행 하는 각 서버에 올바른 버전의 Windows PowerShell 3.0이 설치 되어 있어야 합니다. 자세한 내용은 [설치 Windows PowerShell 3.0 For Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md)을 참조 하십시오.

  - Lync Server에는 Microsoft .NET Framework 4.5이 필요 합니다. Windows Server 2008 r 2에 설치 된 Lync Server 2013의 경우 Lync Server 2013을 설치 하기 전에 서버에 64 비트 버전의 Microsoft .NET Framework 4.5을 설치 해야 합니다. 이를 수동으로 설치 하려면 Microsoft 다운로드 센터에서 Microsoft .NET 4.5 Framework를 다운로드 하세요.[https://go.microsoft.com/fwlink/p/?LinkId=268529](https://go.microsoft.com/fwlink/p/?linkid=268529)

  - Lync Server 2013의 **Windows Identity foundation** 을 사용 하려면 서버 간 인증 시나리오를 지원 하기 위해 Windows identity foundation을 설치 해야 합니다. Windows Server 2008 R2 및 Windows Server 2012을 설치 하려면 다른 절차가 필요 합니다. 다음 목록에서 서버 운영 체제를 선택 합니다.
    
      - Windows server 2008 r 2의 경우 컴퓨터에 이미 설치 되어 있는지 확인 합니다. 2008 이렇게 하려면 **프로그램 추가/제거**, **설치 된 업데이트 보기**및 **windows** 에서 windows **Identity Foundation (KB974405)** 항목을 확인 하세요. Windows Identity Foundation을 설치 하는 방법에 [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657)대 한 자세한 내용은를 참조 하세요.
    
      - Windows server 2012 For Windows Server 2012의 경우 **서버 관리자** 를 사용 하 여 Windows Identity Foundation을 설치 합니다. 서버 관리자 **역할 및 기능 추가 마법사**에서 **기능**을 선택 합니다. 목록에서 **Windows Identity Foundation 3.5** 을 선택 합니다. **다음**을 클릭 하 고 **설치**를 클릭 합니다.

</div>

<div>

## <a name="do-not-install-layered-socket-providers-on-media-servers"></a>미디어 서버에 LSP(Layered Service Provider) 설치 금지

모든 프런트 엔드 서버 또는 독립 실행형 중재 서버에는 Microsoft Internet Security and 가속이 (ISA) 서버 클라이언트 소프트웨어 또는 기타 모든 Winsock 계층화 된 서비스 공급자 (LSP) 소프트웨어를 설치 하지 마십시오. 이 소프트웨어를 설치 하면 미디어 트래픽 성능이 저하 될 수 있습니다.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013의 관리 도구 소프트웨어 요구 사항](lync-server-2013-administrative-tools-software-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

