---
title: 'Lync Server 2013: Active Directory 스키마 준비'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing the Active Directory schema
ms:assetid: 067726ae-fd3f-4133-a32f-26d2603ac674
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398119(v=OCS.15)
ms:contentKeyID: 48183300
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 27c785596d1fe994e3156eb0e52ed840609a5c26
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48506855"
---
# <a name="preparing-the-active-directory-schema-in-lync-server-2013"></a>Lync Server 2013에서 Active Directory 스키마 준비

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-08-27_

Active Directory 도메인 서비스 준비를 시작 하기 전에 Windows 메모장과 같은 텍스트 편집기를 사용 하 여 스키마 파일을 열거나 lync [server 2013에서 사용 하는 Active directory 스키마 확장, 클래스 및 특성](lync-server-2013-active-directory-schema-extensions-classes-and-attributes-used-by-lync-server.md) 을 확인 하 여 lync server 2013에 대해 수정 될 모든 Active Directory 도메인 서비스 스키마 확장을 검토할 수 있습니다. Lync Server에서는 다음과 같은 네 개의 스키마 파일을 사용 합니다.

  - Microsoft Exchange Server와의 상호 운용성을 위해 사용 되는 ExternalSchema .ldf

  - 기본 Lync Server 2013 스키마 파일인 ServerSchema .ldf

  - BackCompatSchema.ldf - 이전 릴리스 구성 요소와의 상호 운용성을 위해 사용됩니다.

  - VersionSchema.ldf - 준비된 스키마의 버전 정보에 사용됩니다.

모든 .ldf 파일은 이전 릴리스에서 마이그레이션하든, 새 설치를 수행하든 관계없이 스키마 준비 중에 설치됩니다. 이러한 스키마 파일은 앞의 목록에 표시 된 순서 대로 설치 되며 \\ \\ 설치 미디어의 지원 스키마 폴더에 있습니다.

Lync Server 스키마 확장은 네트워크 트래픽에 영향을 주는 모든 도메인에서 복제 됩니다. 따라서 스키마 준비는 네트워크 사용량이 적을 때 실행해야 합니다.

<div>


> [!NOTE]  
> Microsoft® Office Communicator Mobile 2007 R2 for Java 및 Microsoft® Office Communicator Mobile for Nokia 1.0 모바일 클라이언트를 Lync Server 2013 배포에 추가 해야 하는 경우 Lync Server 2013을 설치 하는 동안 Microsoft Office Communications Server 2007 r 2에 대 한 Active Directory 스키마를 준비 해야 합니다. 필요한 소프트웨어 및 설명서는를 참조 하세요 <A href="https://go.microsoft.com/fwlink/p/?linkid=207172">https://go.microsoft.com/fwlink/p/?linkId=207172</A> .



</div>

<div>

## <a name="adsi-edit"></a>ADSI 편집

ADSI 편집(Active Directory 서비스 인터페이스 편집기)은 스키마 준비 및 복제를 확인하는 데 사용할 수 있는 AD DS 관리 도구입니다.

서버를 도메인 컨트롤러로 만들기 위해 AD DS 역할을 설치할 때 ADSI 편집이 기본적으로 설치됩니다. Windows Server 2008 및 Windows Server 2008 r 2의 경우 RSAT (원격 서버 관리 도구)에 ADSI 편집 (adsiedit)이 포함 되어 있습니다. RSAT를 도메인 구성원 서버 또는 독립 실행형 서버에 설치할 수도 있습니다. RSAT 패키지는 Windows를 설치할 때 이러한 서버에 기본적으로 복사되지만, 기본적으로 설치되지는 않습니다. 서버 관리자를 사용하여 개별 도구를 설치합니다. ADSI 편집은 **역할 관리 도구**, **Active Directory 도메인 서비스 도구** 및 **Active Directory 도메인 컨트롤러 도구**에 포함되어 있습니다.

Windows Server 2003의 경우 ADSI 편집은 지원 도구에 포함되어 있습니다. 지원 도구는 Windows Server 2003 CD의 \\ 지원 \\ 도구 폴더에서 제공 되거나 "windows Server 2003 서비스 팩 2 32 비트 지원 도구"에서 다운로드할 수 있습니다 [https://go.microsoft.com/fwlink/p/?linkId=125770](https://go.microsoft.com/fwlink/p/?linkid=125770) . 제품 CD에서 지원 도구를 설치 하는 방법에 대 한 자세한 내용은의 "Windows 지원 도구 설치"를 참조 [https://go.microsoft.com/fwlink/p/?linkId=125771](https://go.microsoft.com/fwlink/p/?linkid=125771) 하십시오. Adsiedit.dll은 지원 도구를 설치할 때 자동으로 등록됩니다. 그러나 이 파일을 컴퓨터에 그냥 복사한 경우에는 도구를 실행하기 전에 **regsvr32** 명령을 실행하여 adsiedit.dll 파일을 등록해야 합니다.

</div>

<div>

## <a name="in-this-section"></a>이 섹션의 내용

  - [Lync Server 2013에서 Active Directory 스키마 준비 실행](lync-server-2013-running-schema-preparation.md)

  - [Lync Server 2013에서 Active Directory 스키마 복제 확인](lync-server-2013-verifying-schema-replication.md)

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에 대 한 포리스트 준비](lync-server-2013-preparing-the-forest.md)  
[Lync Server 2013에 대 한 도메인 준비](lync-server-2013-preparing-domains.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

