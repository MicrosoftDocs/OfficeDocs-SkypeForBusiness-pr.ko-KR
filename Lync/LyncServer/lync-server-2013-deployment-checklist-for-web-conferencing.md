---
title: 웹 회의에 대 한 Lync Server 2013 배포 검사 목록
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for web conferencing
ms:assetid: 9908ebe0-e5d3-4920-b9b1-85021f7e69e9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205104(v=OCS.15)
ms:contentKeyID: 48184878
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0085f2990d2541c27392d52143ff69b4fb4711bc
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049450"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-web-conferencing-in-lync-server-2013"></a>Lync Server 2013의 웹 회의에 대 한 배포 검사 목록

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-09-30_

다른 Lync Server 2013 구성 요소를 배포 하는 경우와 마찬가지로, 웹 회의를 배포 하려면 토폴로지 작성기를 사용 하 여 회의가 통합 된 토폴로지를 만들고 게시 해야 합니다.

<div>

## <a name="deployment-sequence"></a>배포 순서

초기 토폴로지를 배포 하는 동시에 또는 하나 이상의 프런트 엔드 풀 또는 Standard Edition server를 배포한 후에 회의를 배포할 수 있습니다.

</div>

<div>

## <a name="conferencing-deployment-process"></a>회의 배포 프로세스

다음 표에서는 기존 토폴로지에 회의를 배포하는 데 필요한 단계를 간략하게 보여 줍니다.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>단계</th>
<th>단계</th>
<th>역할 및 그룹 구성원 자격</th>
<th>설명서</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>하드웨어 및 소프트웨어 필수 구성 요소 설치</strong></p></td>
<td><p>프런트 엔드 풀 및 Standard Edition 서버의 프런트 엔드 서버에서 회의가 실행 됩니다. 이러한 서버를 설치하는 데 필요한 것 외에 추가 하드웨어 또는 소프트웨어 요구 사항은 없습니다.</p>
<div>

> [!NOTE]  
> Lync Server 2013에서는 Office Web Apps와 Office Web Apps 서버를 사용 하 여 PowerPoint 프레젠테이션의 공유 및 렌더링을 처리 합니다. Office Web Apps 서버를 설치 및 구성 하는 방법에 대 한 자세한 내용은 <A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">Office Web Apps 서버 및 Lync server 2013의 통합 구성을</A>참조 하세요.


</div></td>
<td><p>로컬 Administrators 그룹의 구성원인 도메인 사용자</p></td>
<td><p>지원 가능성 설명서의 <a href="lync-server-2013-supported-hardware.md">Lync Server 2013에 대해 지 원하는 하드웨어</a></p>
<p>지원 가능성 설명서의 <a href="lync-server-2013-server-software-and-infrastructure-support.md">서버 소프트웨어 및 인프라 지원 (Lync Server 2013</a> )</p>
<p>계획 설명서의 <a href="lync-server-2013-determining-your-system-requirements.md">Lync Server 2013에 대 한 시스템 요구 사항 결정</a></p>
<p>계획 설명서의 <a href="lync-server-2013-technical-requirements-for-archiving.md">Lync Server 2013에 보관에 대 한 기술 요구 사항</a></p></td>
</tr>
<tr class="even">
<td><p><strong>회의를 지원하는 데 적절한 내부 토폴로지 만들기</strong></p></td>
<td><p>토폴로지 작성기를 실행 하 여 토폴로지에 회의를 추가 하 고 토폴로지를 게시 합니다.</p></td>
<td><p>토폴로지를 정의하려면 로컬 Users 그룹의 구성원 계정 필요</p>
<p>토폴로지를 게시 하려면 Domain Admins 그룹 및 RTCUniversalServerAdmins 그룹의 구성원이 며 Lync Server 2013 파일 저장소에 사용할 파일 공유에 대 한 모든 권한 (읽기/쓰기/수정)을 포함 하 고, 토폴로지 작성기가 필요한 Dacl을 구성할 수 있도록 하는 모든 권한을 갖는 계정입니다.</p></td>
<td><p>배포 설명서에서 <a href="lync-server-2013-define-and-configure-a-topology-in-topology-builder.md">Lync Server 2013에 대 한 토폴로지 작성기에서 토폴로지를 정의 하 고 구성</a> 합니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>회의 정책 및 지원 구성</strong></p></td>
<td><p>Lync Server 2013 제어판 또는 Lync Server 관리 셸을 사용 하 여 회의 설정을 구성 합니다.</p></td>
<td><p>RTCUniversalServerAdmins 그룹 (Windows PowerShell만) 또는 사용자를 [] 또는 CSAdministrator 역할에 할당</p></td>
<td><p>작업 설명서의 <a href="lync-server-2013-conferencing-policies.md">Lync Server 2013에 있는 회의 정책</a></p></td>
</tr>
</tbody>
</table>


Lync Server 2013에는 모임 중에 업로드할 수 있는 파일의 크기를 제한 하는 **MaxUploadFileSizeMb** 설정이 포함 되어 있습니다. 이 설정의 기본값은 500MB입니다. **Set-CsConferencingConfiguration** cmdlet을 사용하여 **MaxUploadFileSizeMb**를 조정할 수 있습니다.

**MaxUploadFileSizeMb** 에서는 Lync Web App에 대 한 파일 업로드 설정이 제한 되지 않습니다. Lync Web App에 대 한 파일 크기 업로드 제한은 대략 30MB로 설정 되어 있으며 IIS web.config 파일:/DataCollabWeb/Int\[Ext\]/Handler/web.config. 의해 제어 됩니다. Lync Web App에 대 한 파일 크기 업로드 제한을 구성 하려면 아래 `maxRequestLength` 와 `maxAllowedContentLength` 같이 web.config 파일을 업데이트 합니다.

    <system.web>
        <!-- 
            Since this handler is used to upload files to DMCU the request size (in kilobytes) 
            has to fit max allowed file size uploaded by LWA client.
            The timeout has to reflect the min client bandwidth. Timeout of 600 secs 
            and 512 Kbits of *client* bandwidth would result into aproximately 30 Mbytes 
            for LWA upload size limit.
        -->
          <httpRuntime maxRequestLength="500000" executionTimeout="600" />
    
    
    
                    <security>
                    <requestFiltering>
                               <requestLimits maxAllowedContentLength="524288000" />
                    </requestFiltering>
                    </security>

각 프런트 엔드 서버에 대해 web.config 파일을 업데이트 해야 합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

