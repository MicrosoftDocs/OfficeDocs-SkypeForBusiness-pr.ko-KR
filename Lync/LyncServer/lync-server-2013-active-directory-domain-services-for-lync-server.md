---
title: 'Lync Server 2013: Lync Server 용 Active Directory 도메인 서비스'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Active Directory Domain Services for Lync Server 2013
ms:assetid: 5483afd5-d8af-4825-ae95-a82dbe941dbf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481129(v=OCS.15)
ms:contentKeyID: 59893871
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f05832a3390101aad7acb1c9d25f532288ca020a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135595"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="active-directory-domain-services-for-lync-server-2013"></a>Lync Server 2013에 대 한 Active Directory 도메인 서비스

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-11-13_

Active Directory 도메인 서비스는 Windows Server 2003, Windows Server 2008, Windows Server 2012 및 Windows Server 2012 R2 네트워크용 디렉터리 서비스로 작동 합니다. 또한 Active Directory 도메인 서비스는 Microsoft Lync Server 2013 보안 인프라가 빌드되는 기반 역할도 합니다. 이 섹션의 목적은 Lync Server 2013이 Active Directory 도메인 서비스를 사용 하 여 IM, 웹 회의, 미디어 및 음성에 대 한 신뢰할 수 있는 환경을 만드는 방법을 설명 하기 위한 것입니다. Active directory 도메인 서비스에 대 한 Lync Server 확장에 대 한 자세한 내용과 Active Directory 도메인 서비스의 환경을 준비 하는 방법에 대 한 자세한 내용은 배포 설명서에서 [Active Directory 도메인 서비스에 대 한 Lync server 2013 준비](lync-server-2013-preparing-active-directory-domain-services.md) 를 참조 하십시오. Windows Server 네트워크에서 Active Directory 도메인 서비스의 역할에 대한 자세한 내용은 사용 중인 운영 체제의 버전에 대한 설명서를 참조하십시오.

Lync Server 2013에서는 Active Directory 도메인 서비스를 사용 하 여 다음을 저장 합니다.

  - 전역 설정 포리스트에서 Lync Server 2013을 실행 하는 모든 서버에 필요 합니다.

  - 포리스트에서 Lync Server 2013을 실행 하는 모든 서버의 역할을 식별 하는 서비스 정보입니다.

  - 일부 사용자 설정

<div>

## <a name="active-directory-infrastructure"></a>Active Directory 인프라

Active Directory의 인프라 요구 사항은 다음과 같습니다.

  - 도메인 컨트롤러에 대한 운영 체제 요구 사항

  - 도메인 및 포리스트 기능 수준 요구 사항

  - 글로벌 카탈로그 도메인 요구 사항

자세한 내용은 배포 설명서의 " [Lync Server 2013에 대 한 Active Directory 인프라 요구 사항](lync-server-2013-active-directory-infrastructure-requirements.md) "을 참조 하십시오.

</div>

<div>

## <a name="active-directory-domain-services-preparation"></a>Active Directory 도메인 서비스 준비

<div>


> [!NOTE]  
> 시스템 컨테이너 대신 구성 컨테이너에 전역 설정을 배포하는 것이 좋습니다. 이렇게 하면 보안이 향상되지 않지만 일부 Active Directory 도메인 서비스 토폴로지에 대한 확장성이 향상될 수 있습니다. Microsoft Office Communications Server 2007에서 마이그레이션하고 System 컨테이너를 사용 하지만 구성 컨테이너를 사용 하려는 경우에는 업그레이드 준비를 수행 하기 전에 시스템 컨테이너에서 설정을 이동 해야 합니다. 구성 컨테이너로 시스템 컨테이너 설정을 마이그레이션하려면 Office Communications Server 2007 전역 설정 마이그레이션 도구를 참조 하세요 <A href="https://go.microsoft.com/fwlink/p/?linkid=145236">https://go.microsoft.com/fwlink/p/?LinkId=145236</A>.



</div>

Lync Server 2013를 배포할 때 첫 번째 단계는 Active Directory 도메인 서비스를 준비 하는 것입니다. Lync Server 2013에 대 한 Active Directory 도메인 서비스 준비는 다음 세 단계로 구성 됩니다.

  - **스키마 준비**. 이 작업은 Lync Server 2013와 관련 된 클래스 및 특성을 포함 하도록 Active Directory 도메인 서비스의 스키마를 확장 합니다. 스키마를 준비 하는 방법에 대 한 자세한 내용은 배포 설명서의 [Lync Server 2013에서 Active Directory 스키마 준비 실행](lync-server-2013-running-schema-preparation.md) 을 참조 하십시오. 자세한 내용은 [Office Communications Server 2007 R2에서 Lync Server 2013로 마이그레이션을](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md)참조 하세요.

  - **포리스트 준비** 이 작업에서는 포리스트 루트 도메인에 전역 설정 및 개체를 만들고, 이 설정 및 개체에 대한 액세스를 제어하는 유니버설 서비스 및 관리 그룹도 함께 만듭니다. 포리스트 준비에 대 한 자세한 내용은 배포 설명서에서 [Lync Server 2013에 대 한 포리스트 준비 실행](lync-server-2013-running-forest-preparation.md) 을 참조 하십시오.

  - **도메인 준비**. 이 작업에서는 도메인 내의 사용자를 호스트 및 관리할 수 있는 권한을 부여할 유니버설 그룹에 필요한 ACE(액세스 제어 항목)를 추가합니다. 이 작업은 Lync Server 2013를 실행 하는 서버와 Lync Server 사용자가 거주 하는 모든 도메인을 배포 하려는 모든 도메인에서 완료 되어야 합니다. 도메인을 준비 하는 방법에 대 한 자세한 내용은 배포 설명서에서 " [Lync Server 2013에 대 한 도메인 준비 실행](lync-server-2013-running-domain-preparation.md) "을 참조 하십시오.

Active Directory 준비 프로세스 및 각 단계를 수행 하는 데 필요한 권한 및 사용 권한에 대 한 개요를 보려면 배포 설명서에서 " [Lync Server 2013에 대 한 Active Directory 인프라 요구 사항](lync-server-2013-active-directory-infrastructure-requirements.md) "을 참조 하십시오.

</div>

<div>

## <a name="universal-groups"></a>유니버설 그룹

이 포리스트를 준비 하는 동안 Lync Server 2013는 전역 설정 및 서비스에 액세스 하 고 관리 하는 권한을 가진 Active Directory 도메인 서비스 내의 다양 한 유니버설 그룹을 만듭니다. 이러한 유니버설 그룹은 다음과 같습니다.

  - **관리 그룹**. 이러한 그룹은 Lync Server 네트워크에 대 한 기본 관리자 역할을 정의 합니다. 포리스트 준비를 진행 하는 동안 이러한 관리자 그룹은 Lync Server 인프라 그룹에 추가 됩니다.

  - **서비스 그룹**. 이러한 그룹은 Lync Server에서 제공 하는 다양 한 서비스에 액세스 하는 데 필요한 서비스 계정입니다.

  - **인프라 그룹**. 이러한 그룹은 Lync Server 인프라의 특정 영역에 액세스할 수 있는 권한을 제공 합니다. 이 그룹은 관리 그룹의 구성 요소로 작동하므로 이 그룹을 수정하거나 이 그룹에 사용자를 직접 추가해서는 안 됩니다. 포리스트 준비를 진행 하는 동안 특정 서비스 및 관리 그룹이 적절 한 인프라 그룹에 추가 됩니다.

Lync Server에 대 한 AD를 준비할 때 만들어지는 특정 유니버설 그룹 및 인프라 그룹에 추가 되는 서비스 및 관리 그룹에 대 한 자세한 내용은 배포 설명서에서 [Lync server 2013의 포리스트 준비에서 수행한 변경 사항](lync-server-2013-changes-made-by-forest-preparation.md) 를 참조 하십시오.

<div>


> [!NOTE]  
> Lync Server 2013에서는 windows Server 2012에서 Lync Server 2013을 실행 하는 서버에 대 한 유니버설 그룹을 지원 하며, 도메인 컨트롤러용 Windows Server 2003 운영 체제를 사용할 수도 있습니다. 유니버설 그룹의 구성원은 도메인 트리 또는 포리스트에 있는 도메인의 다른 그룹 및 계정을 포함할 수 있고 도메인 트리 또는 포리스트에 있는 도메인의 사용 권한이 할당될 수 있습니다. 관리자 위임과 함께 유니버설 그룹을 지원 하면 Lync Server 배포를 간편 하 게 관리할 수 있습니다. 예를 들어 한 도메인을 다른 도메인에 추가하지 않아도 관리자가 둘 다 관리할 수 있습니다.



</div>

</div>

<div>

## <a name="role-based-access-control"></a>역할 기반 액세스 제어

유니버설 서비스 및 관리 그룹을 만들고 해당 유니버설 그룹에 서비스 및 관리 그룹을 추가 하는 것 외에도 포리스트 준비에서는 RBAC (역할 기반 액세스 제어) 그룹을 만듭니다. 포리스트 준비로 만든 특정 RBAC 그룹에 대 한 자세한 내용은 배포 설명서에서 [Lync Server 2013의 포리스트 준비에서 수행한 변경 사항을](lync-server-2013-changes-made-by-forest-preparation.md) 참조 하세요. RBAC 그룹에 대 한 자세한 내용은 [rbac (역할 기반 액세스 제어)에 대 한 Lync Server 2013](lync-server-2013-role-based-access-control-rbac.md)을 참조 하십시오.

</div>

<div>

## <a name="access-control-entries-aces-and-inheritance"></a>ACE(액세스 제어 항목) 및 상속성

포리스트 준비 중에는 개인 및 공용 ACE를 모두 만들어서 만들어진 유니버설 그룹에 ACE를 추가합니다. Lync Server에서 사용 하는 전역 설정 컨테이너에 특정 개인 Ace를 만듭니다. 이 컨테이너는 Lync Server 에서만 사용 되며 전역 설정을 저장 하는 위치에 따라 루트 도메인의 구성 컨테이너나 시스템 컨테이너에 있습니다.

도메인 준비 단계에서는 호스트에 권한을 부여하고 도메인 내의 사용자를 관리하는 유니버설 그룹에 필요한 ACE(액세스 제어 항목)를 추가합니다. 도메인 준비는 도메인 루트와 세 개의 기본 제공 컨테이너인 사용자, 컴퓨터 및 도메인 컨트롤러에 ACE를 만듭니다.

포리스트 준비 및 도메인 준비에서 만들고 추가 하는 공용 Ace에 대 한 자세한 내용은 배포 설명서에서 lync server [2013의 포리스트 준비에서 수행한 변경 내용](lync-server-2013-changes-made-by-forest-preparation.md) 및 [lync server 2013에서 도메인 준비로 인 한 변경](lync-server-2013-changes-made-by-domain-preparation.md) 사항를 참조 하십시오.

조직에서는 보안 위험을 줄이기 위해 AD DS(Active Directory 도메인 서비스)를 잠그는 경우가 자주 있습니다. 그러나 잠겨 있는 Active Directory 환경은 Lync Server 2013에 필요한 권한을 제한할 수 있습니다. 여기에는 컨테이너 및 OU에서 ACE 제거, User, Contact, InetOrgPerson 또는 Computer 개체에 대한 권한 상속 비활성화가 포함됩니다. 잠겨 있는 Active Directory 환경에서는 권한이 필요한 컨테이너 및 OU에서 권한을 수동으로 설정해야 합니다. 자세한 내용은 배포 설명서의 [Lync Server 2013에서 잠긴 Active Directory 도메인 서비스 준비](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md) 를 참조 하십시오.

</div>

<div>

## <a name="server-information"></a>서버 정보

정품 인증을 수행 하는 동안 Lync Server 2013에서는 Active Directory 도메인 서비스의 다음 세 위치에 서버 정보를 게시 합니다.

  - Lync Server 2013이 설치 된 실제 컴퓨터에 해당 하는 각 Active Directory 컴퓨터 개체의 SCP (서비스 연결 지점)입니다.

  - **msRTCSIP-Pools** 클래스의 컨테이너에 만든 서버 개체

  - 토폴로지 작성기에 지정 된 신뢰할 수 있는 서버

</div>

<div>

## <a name="service-connection-points"></a>서비스 연결 지점

Active Directory 도메인 서비스의 각 Lync Server 2013 개체에는 RTC 서비스 라는 SCP가 있으며,이 경우 각 컴퓨터를 식별 하는 다양 한 특성을 포함 하 고이를 통해 제공 되는 서비스를 지정 합니다. 보다 중요 한 SCP 특성 중에는 *serviceDNSName*, *serviceDNSNameType*, *serviceClassname*및 *serviceBindingInformation*가 있습니다. 타사 자산 관리 응용 프로그램은 이러한 및 기타 SCP 특성에 대해 쿼리를 수행 하 여 배포 전체에서 서버 정보를 검색할 수 있습니다.

</div>

<div>

## <a name="active-directory-server-objects"></a>Active Directory 서버 개체

각 Lync Server 2013 서버 역할에는 해당 특성이 해당 역할에서 제공 하는 서비스를 정의 하는 해당 Active Directory 개체가 있습니다. 또한 Standard Edition 서버를 활성화 하거나 Enterprise Edition 풀을 만들 때 Lync Server 2013는 **msrtcsip-gateways** 컨테이너에 새 **msrtcsip-gateways** 개체를 만듭니다. **msRTCSIP-Pool** 클래스는 풀의 FQDN(정규화된 도메인 이름) 및 풀의 프런트 엔드와 백 엔드 구성 요소 간 연결을 지정합니다. Standard Edition 서버는 프런트 엔드 및 백 엔드가 같은 컴퓨터에 배치되는 논리적 풀로 간주됩니다.

</div>

<div>

## <a name="trusted-servers"></a>트러스트된 서버

Lync Server 2013에서 트러스트 된 서버는 토폴로지 작성기를 실행 하 고 토폴로지를 게시할 때 지정 됩니다. 모든 서버 정보를 포함하여 게시된 토폴로지는 중앙 관리 저장소에 저장됩니다. 중앙 관리 저장소에 정의된 서버만 트러스트됩니다. Lync Server 2013에서는 신뢰할 수 있는 서버가 다음 기준을 충족 하는 서버를 신뢰 합니다.

  - 서버의 FQDN은 중앙 관리 저장소에 저장된 토폴로지에 발생합니다.

  - 서버는 트러스트된 CA에서 적합한 인증서를 제공합니다. 자세한 내용은 [Lync Server 2013의 인증서 인프라 요구 사항](lync-server-2013-certificate-infrastructure-requirements.md)를 참조 하십시오.

이러한 기준 중 하나라도 맞지 않으면 서버가 트러스트되지 않고 서버와의 연결이 거부됩니다. 이러한 이중 요구 사항을 통해 Rogue 서버가 유효한 서버 FQDN을 획득하려고 하는 공격을 방지할 수 있습니다.

또한 Microsoft Office Communications Server 2007 R2 및 Microsoft Office Communications Server 2007 배포가 Lync Server 2013 서버와 통신 하도록 하기 위해 Lync Server 2013은 포리스트 준비 중에 컨테이너를 만듭니다. 목록 보관 이전 릴리스에 대 한 신뢰할 수 있는 서버 다음 표에서는 이전 배포와의 호환성을 위해 만드는 컨테이너에 대해 설명합니다.

### <a name="trusted-server-lists-and-their-active-directory-containers-for-compatibility-with-previous-releases"></a>트러스트된 서버 목록 및 이전 릴리스와의 호환성을 위한 해당 Active Directory 컨테이너

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>트러스트된 서버 목록</th>
<th>Active Directory 컨테이너</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Standard Edition 서버 및 엔터프라이즈 풀 프런트 엔드 서버</p></td>
<td><p>RTC 서비스/전역 설정</p></td>
</tr>
<tr class="even">
<td><p>회의 서버</p></td>
<td><p>RTC 서비스/트러스트된 MCU</p></td>
</tr>
<tr class="odd">
<td><p>웹 구성 요소 서버</p></td>
<td><p>RTC 서비스/TrustedWebComponentsServers</p></td>
</tr>
<tr class="even">
<td><p>중재 서버 및 Communicator Web Access 서버, 응용 프로그램 서버, QoE 등록자, A/V 회의 서비스(타사 SIP 서버도 포함)</p></td>
<td><p>RTC 서비스/트러스트된 서비스</p></td>
</tr>
<tr class="odd">
<td><p>프록시 서버</p></td>
<td><p>Lync Server 2013에서는 프록시 서버에 대 한 이전 버전과의 호환성을 지원 하지 않습니다.</p></td>
</tr>
</tbody>
</table>


이전 릴리스의 신뢰할 수 있는 서버를 지원 하려면 모범 사례 분석기 도구를 실행 해야 합니다. 모범 사례 분석기를 실행 하는 방법에 대 [https://go.microsoft.com/fwlink/p/?LinkId=330633](https://go.microsoft.com/fwlink/p/?linkid=330633)한 자세한 내용은를 참조 하세요.

</div>

</div>

<span> </span>

</div>

</div>

</div>

