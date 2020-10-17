---
title: 'Lync Server 2013: 웹 회의 요구 사항'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Web conferencing requirements
ms:assetid: 125f847c-58ab-450f-ae43-41219fd38477
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619171(v=OCS.15)
ms:contentKeyID: 49733559
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 404ce93e841bbbefd62498a1dbb3da664eb927ff
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48518255"
---
# <a name="web-conferencing-requirements-in-lync-server-2013"></a>Lync Server 2013의 웹 회의 요구 사항

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-01-30_

웹 회의를 사용하도록 설정한 경우에는 다음 사항을 계획해야 합니다.

  - <span></span>  
    웹 회의 콘텐츠를 저장하는 데 사용되는 파일 저장소 액세스

  - <span></span>  
    전화 회의 중에 PowerPoint 파일을 공유 하기 위해 필요한 Office Web Apps Server와의 통합

<div>

## <a name="file-store"></a>파일 저장소

Lync Server 2013 웹 회의 서비스는 파일 저장소의 모임 중에 공유 되는 콘텐츠를 저장 합니다. 배포의 일부로, Standard Edition server 또는 Enterprise Edition 프런트 엔드 풀에 대 한 파일 저장소로 사용할 파일 공유를 지정 해야 합니다. 기존 파일 공유를 파일 저장소로 사용하거나 파일 공유가 위치할 파일 서버의 FQDN(정규화된 도메인 이름) 및 새 파일 공유의 폴더 이름을 지정하여 새 파일 공유를 지정할 수 있습니다.자세한 내용은 토폴로지 작성기 - 프런트 엔드에 대해 파일 저장소 정의를 참조하십시오. 웹 회의 서비스는 콘텐츠를 파일 저장소에 저장하기 전에 암호화합니다.

Lync Server 2013에서는 DFS (직접 연결 된 저장소) 또는 SAN (저장 영역 네트워크)을 포함 하는 파일 공유 (분산 파일 시스템) 또는 파일 저장소에 대 한 중복 배열 (RAID)을 지원 합니다. Lync Server 배포 마법사가 파일 공유 위치를 정의한 후 Lync Server에서는 다음과 같은 파일 공유 내에 폴더 구조를 만듭니다.

  - 1-ApplicationServer-1

  - 1-CentralMgmt-1

  - 1-WebServices-1
    
      - CollabContent
    
      - CollabMetadata
    
      - DataConf

그러면 웹 회의 서비스에서 PowerPoint 슬라이드, 화이트보드, 설문 조사, 첨부 파일 등의 콘텐츠를 WebServices 폴더에 있는 CollabContent 및 CollabMetadata 폴더에 저장합니다.

관리자는 RTC 그룹이 필요한 읽기 및 쓰기 권한을 가지도록 파일 공유에 대한 사용 권한을 설정해야 합니다.

<div>


> [!WARNING]  
> 사용 권한과 관련한 오류가 발생하는 경우 토폴로지 작성기를 열고 기존 토폴로지를 다운로드해 다시 게시합니다. 토폴로지를 게시하면 파일 공유 사용 권한이 확인되고 필요한 경우 다시 설정됩니다.



</div>

다음 설정을 사용하여 모임에 대해 콘텐츠가 저장되는 방법을 관리할 수 있습니다.

  - **ContentGracePeriod**은 모임이 종료 된 후 웹 회의 콘텐츠가 서버에 남아 있는 시간을 설정 [-get-csconferencingconfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingConfiguration)에 있습니다.

  - [Get-csconferencingconfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingConfiguration)에 있는 **Maxcontentstoragemb**은 단일 모임 중에 콘텐츠 저장소에 허용 되는 최대 파일 공간 크기를 설정 합니다.

**MaxUploadFileSizeMb** 에서는 Lync Web App에 대 한 파일 업로드 설정이 제한 되지 않습니다. Lync Web App에 대 한 파일 크기 업로드 제한은 대략 30MB으로 설정 되며 IIS web.config file:/Datacol Web/int \[ Ext \] /Handler/web.config에 의해 제어 됩니다. Lync Web App에 대 한 파일 크기 업로드 제한을 구성 하려면 `maxRequestLength` 아래에 `maxAllowedContentLength` 나와 있는 대로 web.config 파일을 업데이트 하십시오.

    <system.web>
        <!-- 
            Since this handler is used to upload files to DMCU the request size (in kilobytes) 
            has to fit max allowed file size uploaded by Lync Web App client.
            The timeout has to reflect the min client bandwidth. Timeout of 600 secs 
            and 512 Kbits of *client* bandwidth would result into aproximately 30 Mbytes 
            for Lync Web App upload size limit.
        -->
          <httpRuntime maxRequestLength="500000" executionTimeout="600" />
    
    
    
                    <security>
                    <requestFiltering>
                               <requestLimits maxAllowedContentLength="524288000" />
                    </requestFiltering>
                    </security>

각 프런트 엔드 서버에 대 한 web.config 파일을 업데이트 해야 합니다.

</div>

<div>

## <a name="office-web-apps-server"></a>Office Web Apps 서버

이러한 새 기능을 사용 하려면 관리자는 Office Web apps 서버를 설치 하 고 Office Web Apps 서버와 통신 하도록 Lync Server 2013을 구성 해야 합니다. 이 문서에서는 Office Web Apps 서버에서 작동 하도록 Lync Server 2013을 구성 하는 방법에 대 한 정보를 제공 합니다. 이 설명서에서 제공 하지 않는 것은 Office Web Apps 서버를 설치 하는 방법에 대 한 정보입니다. 설치에 대 한 자세한 내용은 Microsoft Office Web Apps 배포 웹 사이트를 참조 하세요 <https://go.microsoft.com/fwlink/p/?linkid=257525> . 이 가이드에는 Office Web Apps 서버에 대 한 전체 필수 구성 요소 정보가 포함 되어 있습니다. Office Web Apps 서버는 Lync Server, SQL Server 또는 기타 서버 응용 프로그램이 실행 되 고 있지 않은 독립 실행형 컴퓨터에 설치 되어 있어야 합니다. (해당 컴퓨터에 설치 된 Office 버전이 없어야 합니다.) Office Web Apps 서버를 실행 하는 데 사용 되는 모든 컴퓨터에는 .NET Framework 4.5 및 Windows PowerShell 3.0를 포함 하 여 특정 소프트웨어 집합도 설치 되어 있어야 합니다. 이러한 요구 사항은 인증서 및 IIS (인터넷 정보 서비스) 구성에 대 한 정보와 함께 Microsoft Office Web Apps 배포 웹 사이트에 자세히 설명 되어 <https://go.microsoft.com/fwlink/p/?linkid=257525> 있습니다.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013의 웹 회의 개요](lync-server-2013-web-conferencing-overview.md)  
[Lync Server 2013의 웹 회의에 대 한 배포 검사 목록](lync-server-2013-deployment-checklist-for-web-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

