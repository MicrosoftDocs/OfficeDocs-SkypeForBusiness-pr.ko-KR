---
title: 'Lync Server 2013: Active Directory 도메인 서비스 준비 개요'
description: 'Lync Server 2013: Active Directory 도메인 서비스 준비 개요'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of Active Directory Domain Services preparation
ms:assetid: cdd2a652-6a0d-4728-9950-3fcaa7a80066
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398869(v=OCS.15)
ms:contentKeyID: 48185662
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 18b22e11a73ad7a181e2eaf887b1b49b934d9db5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566844"
---
# <a name="overview-of-active-directory-domain-services-preparation-in-lync-server-2013"></a>Lync Server 2013의 Active Directory 도메인 서비스 준비 개요

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-29_

Lync Server 2013 배포에 대 한 Active Directory 도메인 서비스를 준비 하려면 특정 순서에 따라 세 가지 단계를 수행 해야 합니다.

다음 표에서는 Lync Server 용 AD DS를 준비 하는 데 필요한 단계를 설명 합니다.

### <a name="active-directory-preparation-steps"></a>Active Directory 준비 단계

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>단계</th>
<th>설명</th>
<th>실행 위치</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1.</p></td>
<td><p><a href="lync-server-2013-preparing-the-active-directory-schema.md">Lync Server 2013에서 Active Directory 스키마 준비</a></p></td>
<td><p>Lync Server에서 사용 되는 새 클래스 및 특성을 추가 하 여 Active Directory 스키마를 확장 합니다.</p>
<p>Lync Server를 배포할 배포의 각 포리스트에서 한 번씩 실행 합니다.</p></td>
<td><p>Lync Server를 배포할 각 포리스트의 루트 도메인에 있는 스키마 마스터에 대해</p>
<div>

> [!NOTE]  
> 스키마 마스터에 대 한 사용 권한이 있는 경우 루트 도메인에서이 단계를 실행할 필요가 없지만 루트 도메인에 있는 Schema Admins 그룹의 구성원 이어야 하 고 스키마 마스터에서 Enterprise Admins 그룹의 구성원이 되어야 합니다. 리소스 포리스트 토폴로지에서는이 단계를 사용자 포리스트에서 사용 하지 않고 리소스 포리스트에서만 실행 합니다. 중앙 포리스트 토폴로지에서는 사용자 포리스트가 아닌 중앙 포리스트에서만이 단계를 실행 합니다.


</div></td>
</tr>
<tr class="even">
<td><p>2.</p></td>
<td><p><a href="lync-server-2013-preparing-the-forest.md">Lync Server 2013에 대 한 포리스트 준비</a></p></td>
<td><p>Lync Server에서 사용 하는 전역 설정 및 유니버설 그룹을 만듭니다.</p>
<p>Lync Server를 배포할 배포의 각 포리스트에서 한 번씩 실행 합니다.</p></td>
<td><p>Lync Server를 배포할 각 포리스트의 루트 도메인 이 단계를 실행 하려면 Enterprise Admins 그룹의 구성원 이어야 합니다.</p>
<div>

> [!NOTE]  
> 리소스 포리스트 토폴로지에서는이 단계를 사용자 포리스트에서 사용 하지 않고 리소스 포리스트에서만 실행 합니다. 중앙 포리스트 토폴로지에서는 사용자 포리스트가 아닌 중앙 포리스트에서만이 단계를 실행 합니다.


</div></td>
</tr>
<tr class="odd">
<td><p>3.</p></td>
<td><p><a href="lync-server-2013-preparing-domains.md">Lync Server 2013에 대 한 도메인 준비</a></p></td>
<td><p>유니버설 그룹의 구성원에 게 사용할 개체에 대 한 사용 권한을 추가 합니다.</p>
<p>사용자 도메인 또는 서버 도메인 별로 한 번씩 실행 됩니다.</p>
<div>

> [!NOTE]  
> Lync Server 2010에서 Lync Server 2013로 마이그레이션하는 경우 배포 마법사에서 도메인 준비가 이미 완료 된 것으로 표시 될 수 있습니다. 도메인 준비를 다시 실행할 필요가 없습니다. 사용 권한이 Lync Server 2010에서 Lync Server 2013로 변경 되지 않았습니다.


</div></td>
<td><p>Lync Server를 배포할 각 도메인의 구성원 서버 이 단계를 실행 하려면 Domain Admins 그룹의 구성원 이어야 합니다.</p></td>
</tr>
</tbody>
</table>


<div id="sectionSection0" class="section">

Lync server 2010와 같은 lync 서버 2013는 Office Communications Server 2007 r 2의 경우 처럼 AD DS 대신 중앙 관리 저장소에 많은 구성 정보를 저장 합니다. 그러나 AD DS에 저장 되는 정보는 다음과 같습니다.

  - **스키마 확장**:
    
      - 사용자 개체 확장
    
      - 이전 버전과의 호환성을 유지 하기 위한 Office Communications Server 2007 R2 클래스에 대 한 확장

<!-- end list -->

  - **데이터** (Lync Server 확장 스키마 및 기존 스키마 클래스에 저장):
    
      - 사용자 SIP URI(Uniform Resource Identifier) 및 기타 사용자 설정
    
      - 응답 그룹 및 회의 길잡이 등과 같은 응용 프로그램에 대한 대화 상대 개체
    
      - 중앙 관리 저장소에 대한 포인터
    
      - Kerberos 인증 계정(선택적 컴퓨터 개체)

Lync Server 2013에서는 RTCUniversalServerAdmins 유니버설 그룹에 대 한 설치 권한을 부여 하 여 설치 및 관리를 위임 하므로 해당 그룹의 구성원이 로컬 서버에서 Lync Server 2013을 설치 하 고 활성화할 수 있습니다 (서버를 토폴로지에 추가 하 고 게시 하 고 사용 하도록 설정한 후). 위임 된 사용자는 Lync Server 2013을 설치 하 고 활성화 하는 컴퓨터의 로컬 관리자 여야 하지만 Domain Admins 그룹의 구성원 일 필요는 없습니다. 또한 지정 된 Ou (조직 구성 단위)에서 개체에 대 한 사용 권한을 부여 하 여 포리스트 준비 중에 만들어지는 유니버설 그룹의 구성원이 Domain Admins 그룹의 구성원이 없어도 해당 개체에 액세스할 수 있도록 할 수 있습니다.

Lync Server 2013의 새 배포의 경우 전역 설정을 구성 컨테이너에 저장 해야 합니다. 조직이 이전 버전에서 업그레이드 되는 동안 여전히 System 컨테이너에 전역 설정이 있으면 System 컨테이너가 여전히 지원 됩니다.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 Active Directory 스키마 준비](lync-server-2013-preparing-the-active-directory-schema.md)  
[Lync Server 2013에서 사용 하는 Active Directory 스키마 확장, 클래스 및 특성](lync-server-2013-active-directory-schema-extensions-classes-and-attributes-used-by-lync-server.md)  


[Lync Server 2013에 대 한 포리스트 준비](lync-server-2013-preparing-the-forest.md)  
[Lync Server 2013에 대 한 도메인 준비](lync-server-2013-preparing-domains.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

