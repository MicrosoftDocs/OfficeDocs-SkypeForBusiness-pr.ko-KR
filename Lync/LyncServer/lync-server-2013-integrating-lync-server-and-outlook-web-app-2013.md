---
title: 'Lync Server 2013: Lync Server 및 Outlook Web App 2013 통합'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Integrating Lync Server 2013 and Outlook Web App 2013
ms:assetid: 513d4cc7-aa87-4f68-b99d-d58b63bdf242
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688055(v=OCS.15)
ms:contentKeyID: 49733649
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 31a25e1d0a6410171201af578d6b28f496468e06
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983557"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="integrating-microsoft-lync-server-2013-and-microsoft-outlook-web-app-2013"></a>Microsoft Lync Server 2013 및 Microsoft Outlook Web App 2013 통합

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-02-03_

Microsoft Outlook 2013와 통합 하는 것 외에 microsoft Lync Server 2013는 Microsoft Outlook Web App 2013과 완벽 하 게 통합 될 수 있습니다. 그 외에, Outlook Web App에 인스턴트 메시징 및 현재 상태를 추가 하 고 Outlook Web App과 Microsoft Lync 2013 간에 통합 된 연락처 목록을 공유할 수 있습니다. Lync Server 2013 및 Outlook Web App을 통합 하려면 먼저 Microsoft Exchange Server 2013 백 엔드 서버에 통합 커뮤니케이션 관리 API 4.0 런타임이 설치 되어 있는지 확인 해야 합니다. 다음 레지스트리 값이 있는지 검색 하 여이 작업을 수행할 수 있습니다.

HKEY\_로컬\_컴퓨터\\시스템\\CurrentControlSet\\서비스\\MSExchange OWA\\InstantMessaging\\ImplementationDLLPath

ImplementationDLLPath는 파일에 대 한 폴더 위치 (예를 들어, Web.config. dll)를 가리켜야 합니다. 그렇지 않은 경우 또는 레지스트리 값이 없는 경우 Microsoft 다운로드 센터에서 앱 MA 런타임 설치 프로그램을 다운로드 하 여 설치 해야 <http://www.microsoft.com/en-us/download/details.aspx?id=34992>합니다. 웹 페이지 런타임을 설치 하는 방법에 대 한 정보는 동일한 페이지에서 찾을 수 있습니다.

**이전 버전과의 호환성**

Lync Server 2013는 통합 메시징 및 Outlook Web App의 Microsoft Exchange Server 2010 버전과 통합할 수 있습니다. 자세한 내용은 온-프레미스 Exchange UM 배포 문서를 참조 하 여 Lync Server 2010에서 [http://technet.microsoft.com/en-us/library/gg398768.aspx](lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md)음성 메일을 제공 합니다. Exchange 2010와 통합 하는 경우 통합 된 연락처 저장소와 Lync에서 Exchange 보관 등의 Lync Server 관련 기능을 사용할 수 없습니다.

Microsoft Lync 2013는 Exchange 2010 및 Outlook 2010과 함께 사용할 수도 있습니다. 그러나이 경우에도 Lync 2013 사용자는 통합 된 연락처 저장소와 고해상도 사진 등의 새로운 기능을 사용할 수 없습니다. 이러한 새로운 접근 권한 값에는 Lync Server 2013 및 Exchange 2013이 모두 필요 합니다.

**Outlook Web App에 대 한 신뢰할 수 있는 응용 프로그램 풀 만들기**

Microsoft Exchange 통합 메시징 호출 라우터 서비스와 Microsoft Exchange 통합 메시징 서비스를 동일한 컴퓨터에 설치한 경우 Outlook Web App에 대해 신뢰할 수 있는 응용 프로그램 풀을 만들 필요가 없습니다. (해당 서버가 SipName UM 다이얼 플랜을 호스트 하 고 있다고 가정 합니다.) 단일 컴퓨터를 사용 하 여 이러한 서비스를 모두 호스트 하는 경우 **Outlook Web App에서 인스턴트 메시지를 사용 하도록 설정**하는이 문서의 섹션으로 건너뛸 수 있습니다.

Lync Server 2013는 SipName UM 다이얼 플랜을 호스트 하는 Exchange 서버를 자동 검색 하도록 할 수 있습니다. 이러한 서버는 Lync Server 알려진 서버 목록에 자동으로 추가 됩니다. 신뢰할 수 있는 응용 프로그램 풀을 만들고이 서버를 알려진 서버 목록에 추가할 필요가 없습니다. 실제로 이렇게 하면 Outlook Web App 통합이 작동을 중지 하 게 됩니다.

<div>


> [!NOTE]  
> 이는 Lync Server 토폴로지에서 같은 컴퓨터에 대 한 두 개의 항목, 즉 autodiscovered 항목 및 수동으로 추가 된 항목을 사용 하는 것 이기 때문입니다. 문제를 해결 하 고 Outlook Web App이 다시 작동 하 게 하려면 Windows PowerShell을 사용 하 여 서버에 대 한 신뢰할 수 있는 풀 및 신뢰할 수 있는 응용 프로그램 항목을 제거 하세요. 자세한 내용은 <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsTrustedApplicationPool">remove-CsTrustedApplicationPool</A> 및 <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsTrustedApplication">remove-CsTrustedApplication</A> cmdlet에 대 한 도움말 항목을 참조 하세요.



</div>

이러한 두 서비스가 별도의 컴퓨터에서 실행 되는 경우 통합 커뮤니케이션 관리 API 4.0 런타임이 설치 되어 있는지 확인 한 후에는 Lync Server 신뢰할 수 있는 응용 프로그램 풀과 연결 된 신뢰할 수 있는 응용 프로그램을 만들어야 합니다. Outlook Web App 그러면 서버를 알려진 서버 목록에 추가 하 게 됩니다. 이렇게 하려면 먼저 Lync Server 관리 셸에서 다음과 같은 명령을 실행 합니다.

    New-CsTrustedApplicationPool -Identity atl-owa-001.litwareinc.com -Registrar atl-cs-001.litwareinc.com -Site Redmond -RequiresReplication $False

앞의 명령에서 atl-owa-001.litwareinc.com은 Outlook Web App 풀의 정규화 된 도메인 이름입니다. Outlook Web App에 대 한 액세스를 제공 하는 인증서의 주체 이름 및 SAN (주체 대체 이름) 필드에 표시 되는 이름과 같아야 합니다. 마찬가지로 atl-cs-001.litwareinc.com는 새 신뢰할 수 있는 응용 프로그램 풀을 호스팅하는 Lync Server 2013 풀의 정규화 된 도메인 이름입니다. 참고로, 지정 된 사이트 Redmond는 Lync Server 사이트의 SiteID를 나타냅니다. SiteID는 사이트의 DisplayName과 같을 필요는 없습니다. Lync 서버 관리 셸에서 다음 명령을 실행 하 여 Lync Server 사이트의 SiteIDs 검색할 수 있습니다.

    Get-CsSite | Select-Object DisplayName, SiteID

신뢰할 수 있는 응용 프로그램 풀을 만든 후 다음과 같은 명령을 사용 하 여 Outlook Web App 용 포트 및 응용 프로그램 Id를 구성 합니다.

    New-CsTrustedApplication -ApplicationId OutlookWebApp -TrustedApplicationPoolFqdn atl-owa-001.litwareinc.com  -Port 5199

앞의 명령에서 ApplicationID는 신뢰할 수 있는 응용 프로그램을 구분 하는 데 사용 되는 편리한 식별자입니다. ApplicationID는 공백이 나 허용 되지 않는 문자가 포함 되지 않은 텍스트 문자열일 수 있습니다. 유효한 식별자를 만들려면 ApplicationId를 지정할 때 문자와 숫자만 사용 하는 것이 좋습니다. Port 매개 변수에 할당 되는 값은 관리자의 재량으로 남아 있습니다 (사용 가능한 모든 네트워크 포트가 될 수 있음).

신뢰할 수 있는 응용 프로그램을 만든 후 다음 명령을 실행 하 여 Lync Server 토폴로지의 변경 내용을 사용 하도록 설정 해야 합니다.

    Enable-CsTopology

Exchange 클라이언트 액세스 및 사서함 서버도 모든 SIP Uri 다이얼 플랜에 추가 해야 합니다. 그러면 서버는 Lync Server 용 ExUmRouting topology를 사용 하 여 신뢰할 수 있는 SIP 피어로 구성 됩니다.

**Outlook Web App에서 인스턴트 메시지 사용**

Lync Server가 올바르게 구성 되 면 Outlook Web App 구성을 시작할 수 있습니다. 해당 프로세스의 첫 번째 단계는 프런트 엔드 서버의 모든 Outlook Web App 가상 디렉터리에서 인스턴트 메시지를 사용 하도록 설정 하는 것입니다. 백 엔드 서버의 가상 디렉터리에 대해 인스턴트 메시지를 사용 하도록 설정할 필요는 없습니다. 사실 백 엔드 서버에서 인스턴트 메시지를 사용 하지 않는 것이 좋습니다. Exchange 관리 셸에서 다음 명령을 실행 하 여 클라이언트 액세스 서버에서 인스턴트 메시지를 사용 하도록 설정할 수 있습니다.

    Get-OwaVirtualDirectory | Set-OwaVirtualDirectory -InstantMessagingEnabled $True -InstantMessagingType OCS

<div>


> [!NOTE]  
> Outlook Web App을 설치 하면 기본적으로 인스턴트 메시지를 사용할 수 있습니다. 즉, InstantMessagingEnabled 속성이 True로 설정 됩니다. 그러나 인스턴트 메시지 형식을 OCS로 설정 하려면 앞의 명령을 계속 실행 해야 합니다. 기본적으로 InstantMessagingType는 없음으로 설정 됩니다.



</div>

다음 두 줄을 Outlook Web App web.config 파일에 추가 해야 합니다 (이 파일은\\일반적으로 C: 폴더에 있습니다 (\\Microsoft\\Exchange Server\\V15\\clientaccess\\Owa). 이러한 두 줄은 web.config 파일의 \<AppSettings\> 노드 아래에 추가 되어야 하며, Outlook Web App이 설치 된 백 엔드 서버 에서만이 절차를 수행 해야 합니다.

    <add key="IMCertificateThumbprint" value="EA5A332496CC05DA69B75B66111C0F78A110D22d"/>
    <add key="IMServerName" value="atl-cs-001.litwareinc.com"/>

앞의 예제에서 IMCertificateThumbprint의 값은 백 엔드 서버에 설치 된 Exchange 2013 인증서의 지문 이어야 합니다. Exchange 관리 셸에서 다음 명령을 실행 하 여 해당 정보를 검색할 수 있습니다.

    Get-ExchangeCertificate

또한 IMServerName에 할당 된 값이 Outlook Web App에 대해 신뢰할 수 있는 응용 프로그램 풀을 만든 Lync Server 풀의 정규화 된 도메인 이름입니다.

Outlook Web App에 사용 하는 인증서는 Lync Server에서 신뢰 하는 인증서 여야 합니다. Lync Server와 Exchange에서 모두 인증서를 신뢰할 수 있는지 확인 하는 한 가지 방법은 내부 인증 기관을 사용 하 여 사서함 서버에서 인증서를 만든 후 해당 서버 FQDN이 주체 이름에 사용 되 고이 FQDN이 t e에 표시 되도록 하는 것입니다. 인증서 대체 이름 필드 인증서를 만든 후에는 백엔드 서버로 가져올 수 있습니다. 결과적으로 동일한 인증서가 Exchange 통합 메시징과 Lync Server 간의 두 가지 목적으로 통신 하는 데 사용 됩니다. and, 2) Outlook Web App과 Lync 서버 간의 통합.

Web.config 파일을 업데이트 한 후에는 Outlook Web App 풀을 재생 하기 위해 Exchange 백 엔드 서버에서 다음 명령을 실행 해야 합니다.

    C:\Windows\System32\Inetsrv\Appcmd.exe recycle apppool /apppool.name:"MSExchangeOWAAppPool"

재활용 작업에 성공 하면 Exchange 관리 셸에서 다음 메시지가 표시 됩니다.

    "MSExchangeOWAAppPool" successfully recycled

**Outlook Web App 사서함 정책 구성**

이 시점에서 다음 명령을 사용 하 여 적절 한 Outlook Web App 사서함 정책 (또는 정책)에서 인스턴트 메시지를 구성할 수 있습니다. 예를 들어 사서함 서버 중 하나에서이 명령을 실행 하 여 기본 정책에서 인스턴트 메시지를 사용할 수 있습니다.

    Set-OwaMailboxPolicy -Identity "Default" -InstantMessagingEnabled $True -InstantMessagingType "OCS"

이 명령은 모든 Outlook Web App 사서함 정책에 대해 인스턴트 메시지를 사용할 수 있도록 합니다.

    Get-OwaMailboxPolicy | Set-OwaMailboxPolicy -InstantMessagingEnabled $True -InstantMessagingType "OCS"

사서함 정책을 사용 하도록 설정한 후에는 해당 정책에서 관리 하는 모든 사용자가 Lync Server와 Outlook Web App 간에 완전 한 통합을 제공 합니다.

  - 사용자에 게 Exchange 2013 사서함이 있습니다.

  - 사용자가 Lync Server 2013에 대해 사용 하도록 설정 되었습니다.

  - 사용자에 게 유효한 SIP 프록시 주소가 있습니다.

**Outlook Web App에서 인스턴트 메시지를 사용 하지 않도록 설정**

앞에서 설명한 대로 Outlook Web App에서 인스턴트 메시지는 기본적으로 사용 하도록 설정 되어 있습니다. 즉, Outlook Web App을 Lync Server와 통합 하지 않으면 사용자가 Outlook Web App에 로그온 할 때마다 빈 현재 상태 아이콘과 오류 메시지가 표시 됩니다. 이 문제를 방지 하려면 다음 Exchange 관리 셸 명령을 사용 하 여 Outlook web App에서 인스턴트 메시지를 사용 하지 않도록 설정 합니다.

    Get-OwaVirtualDirectory | Set-OwaVirtualDirectory -InstantMessagingEnabled $False

**Outlook Web App과 통합 확인**

인스턴트 메시지와 현재 상태가 Outlook Web App과 통합 되었는지 확인 하려면 Outlook Web App 2013에 로그인 합니다. 화면 오른쪽 위 모서리에 Exchange 표시 이름이 표시 됩니다. 사용자 이름 옆에 현재 상태를 나타내는 녹색 아이콘이 있는 경우, 예를 들어 Lync Server 및 Outlook Web App이 성공적으로 통합 되었음을 나타냅니다.

Outlook Web App에 초기 로그온 한 후 이벤트 ID 112 (및 원본 MSExchange OWA)를 사용 하는 이벤트가 사서함 서버의 이벤트 로그에 기록 되었는지 확인 합니다. 이 이벤트는 메신저 끝점 관리자가 성공적으로 초기화 되었음을 나타냅니다. 인스턴트 메시지를 사용할 수 없는 경우\\사서함 서버에서 C: Program files\\폴더에서 로그 파일을 찾습니다. Microsoft\\Exchange server\\V15\\로깅\\OWA\\InstantMessaging. 통합이 실패 했음을 나타내는 로깅 또는 InstantMessaging 폴더가 없는 경우 이 경우 Lync Server에서 SIPStack 추적 (모든 수준 및 모든 플래그)을 사용 하 여 통합에 실패 한 이유를 확인할 수 있습니다.

</div>

<span> </span>

</div>

</div>

</div>

