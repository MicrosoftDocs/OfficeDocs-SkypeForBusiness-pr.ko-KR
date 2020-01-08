---
title: 'Lync Server 2013: Active Directory 스키마 준비'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Preparing the Active Directory schema
ms:assetid: 067726ae-fd3f-4133-a32f-26d2603ac674
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398119(v=OCS.15)
ms:contentKeyID: 48183300
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5479bfbb0774ddd68015de470de082f0cc185b98
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985402"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-the-active-directory-schema-in-lync-server-2013"></a>Lync Server 2013에서 Active Directory 스키마 준비

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-08-27_

Active Directory 도메인 서비스의 준비를 시작 하기 전에 Windows 메모장과 같은 텍스트 편집기를 사용 하 여 스키마 파일을 열거나 lync Server 2013에서 Lync server 2013에 대해 수정 될 모든 Active Directory 도메인 서비스 스키마 확장을 검토 하 [는 데 사용 되는 Active directory 스키마 확장, 클래스 및 특성을](lync-server-2013-active-directory-schema-extensions-classes-and-attributes-used-by-lync-server.md) 확인할 수 있습니다. Lync Server는 네 가지 스키마 파일을 사용 합니다.

  - Microsoft Exchange Server와의 상호 운용성에 사용 되는 ExternalSchema .ldf

  - 기본 Lync Server 2013 스키마 파일인 ServerSchema .ldf

  - 이전 릴리스의 구성 요소와 상호 운용 하는 데 사용 되는 BackCompatSchema

  - 준비 된 스키마의 버전 정보에 사용 되는 VersionSchema. .ldf

모든 .ldf 파일은 이전 릴리스의 마이그레이션 또는 새로 설치 수행 여부에 관계 없이 스키마 준비 중에 설치 됩니다. 이러한 스키마 파일은 앞의 목록에 표시 된 순서 대로 설치 되며 설치 미디어의 \\지원\\스키마 폴더에 있습니다.

Lync Server 스키마 확장은 네트워크 트래픽에 영향을 주는 모든 도메인에 복제 됩니다. 네트워크 사용량이 낮을 때 스키마 준비를 한 번에 실행 합니다.

<div>


> [!NOTE]  
> Microsoft® Office Communicator Mobile 2007 R2 for Java 및 Microsoft® Nokia 1.0 모바일 클라이언트의 Lync Server 2013 배포에 대 한 지원을 추가 해야 하는 경우 Microsoft Office 용 Active Directory 스키마를 준비 해야 합니다. Lync Server 2013를 설치 하는 동안 통신 서버 2007 R2. 필요한 소프트웨어와 설명서는를 참조 <A href="http://go.microsoft.com/fwlink/p/?linkid=207172">http://go.microsoft.com/fwlink/p/?linkId=207172</A>하세요.



</div>

<div>

## <a name="adsi-edit"></a>ADSI 편집

Active Directory 서비스 인터페이스 편집기 (ADSI Edit)는 스키마 준비 및 복제를 확인 하는 데 사용할 수 있는 AD DS 관리 도구입니다.

ADSI Edit는 서버를 도메인 컨트롤러로 만들기 위해 AD DS 역할을 설치할 때 기본적으로 설치 됩니다. Windows Server 2008 및 Windows Server 2008 R2의 경우 ADSI Edit (adsiedit)는 원격 서버 관리 도구 (RSAT)에 포함 되어 있습니다. 도메인 구성원 서버나 독립 실행형 서버에 RSAT를 설치할 수도 있습니다. RSAT 패키지는 Windows를 설치할 때 기본적으로 이러한 서버에 복사 되지만 기본적으로 설치 되지 않습니다. 서버 관리자를 사용 하 여 개별 도구를 설치 합니다. ADSI 편집은 **역할 관리 도구**, **Active Directory 도메인 서비스 도구**, **active directory 도메인 컨트롤러 도구**에 포함 되어 있습니다.

Windows Server 2003의 경우 ADSI 편집이 지원 도구에 포함 되어 있습니다. 지원 도구는 Windows Server 2003 CD의 \\지원\\도구 폴더에서 사용할 수 있거나 "Windows server 2003 서비스 팩 2 32 비트 지원 도구"에서 다운로드할 수 있습니다. [http://go.microsoft.com/fwlink/p/?linkId=125770](http://go.microsoft.com/fwlink/p/?linkid=125770) 제품 CD에서 지원 도구를 설치 하는 방법에 대 한 자세한 내용은의 [http://go.microsoft.com/fwlink/p/?linkId=125771](http://go.microsoft.com/fwlink/p/?linkid=125771)"Windows 지원 도구 설치"에서 확인할 수 있습니다. 지원 도구를 설치할 때 Adsiedit가 자동으로 등록 됩니다. 그러나 파일을 컴퓨터로 복사한 경우에는 **regsvr32** 명령을 실행 하 여 adsiedit 파일을 등록 해야 도구를 실행할 수 있습니다.

</div>

<div>

## <a name="in-this-section"></a>이 섹션의 내용

  - [Lync Server 2013에서 Active Directory 스키마 준비 실행](lync-server-2013-running-schema-preparation.md)

  - [Lync Server 2013에서 Active Directory 스키마 복제 확인](lync-server-2013-verifying-schema-replication.md)

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에 대한 포리스트 준비](lync-server-2013-preparing-the-forest.md)  
[Lync Server 2013에 대한 도메인 준비](lync-server-2013-preparing-domains.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

