---
title: 'Lync Server 2013: 프런트 엔드 풀 연결 데이터 보안'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Front End pool pairing data security
ms:assetid: edb852b8-ea86-4948-b756-60fe6ee876d2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721930(v=OCS.15)
ms:contentKeyID: 49733865
ms.date: 10/07/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: efe51da622107183d3dbf2897a9e2a708acd78dd
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739758"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="front-end-pool-pairing-data-security-in-lync-server-2013"></a>Lync Server 2013의 프런트 엔드 풀 연결 데이터 보안

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2014-10-07_

백업 서비스는 재해 복구용으로 두 개의 연결 된 프런트 엔드 풀 간에 사용자 데이터 및 회의 콘텐츠를 지속적으로 전송 하는 Lync Server 2013에 도입 되는 데이터 복제 메커니즘입니다. 사용자 데이터에는 사용자 SIP Uri 및 연락처 목록 및 설정이 포함 되어 있습니다. 회의 내용에는 Microsoft PowerPoint 2010 업로드와 회의에 사용 되는 화이트 보드도 포함 됩니다. 원본 풀에서 사용자 데이터 및 회의 콘텐츠는 대상 풀로 전송 되는 로컬 저장소의 압축으로 내보내지고 로컬 저장소로 가져올 수 있습니다. 백업 서비스는 두 데이터 센터 간의 통신 연결이 인터넷에서 보호 되는 회사 네트워크 내에 있다고 가정 합니다. 두 데이터 센터 간에 전송 된 데이터를 암호화 하지 않으며 HTTPS와 같은 보안 프로토콜 내에서 기본적으로 캡슐화 되지 않습니다. 따라서 회사 네트워크 내에서 내부 담당자의 중간자 공격이 가능 합니다.

<div>

## <a name="evaluating-security-risks"></a>보안 위험 평가

여러 데이터 센터에서 Lync Server 2013을 배포 하 고 재해 복구 기능을 사용 하는 모든 엔터프라이즈는 교차 데이터 센터 트래픽이 해당 회사 인트라넷으로 보호 되는지 확인 해야 합니다. 내부 공격 보호에 대해 주의를 기울여야 하는 기업은 데이터 센터 간의 통신 연결을 보호 해야 합니다.

기업의 데이터 센터가 회사 인트라넷 뒤에서 보호 되는 것으로 가정 하면 표준입니다. 이러한 데이터 센터 간에 전송 되는 회사의 민감한 데이터에는 여러 가지 종류가 있습니다. 엔터프라이즈의 IT 인프라는 이러한 교차 데이터 센터 링크가 보호 되지 않는 경우 아무리 위험 합니다.

회사 네트워크 내에서 중간자 공격으로 인 한 공격의 위험은 인터넷에 소통량을 노출 하는 것과 비교 하 여 상대적으로 포함 되어 있습니다. 특히, 백업 서비스 (예: SIP Uri)가 제공 하는 사용자 데이터는 일반적으로 Exchange 또는 기타 디렉터리 소프트웨어의 글로벌 주소록과 같은 다른 수단을 통해 회사 내의 모든 직원에 게 제공 됩니다. 따라서 두 개의 연결 된 풀 간에 데이터를 복사 하는 데 백업 서비스를 사용 하는 경우 두 데이터 센터 간의 WAN 보안에 중점을 두어야 합니다.

</div>

<div>

## <a name="mitigating-security-risks"></a>보안 위험 경감

데이터 센터에 대 한 액세스를 제한 하 고 두 데이터 센터 간의 WAN 전송 보안을 유지 하는 것에 이르기까지 백업 서비스 트래픽에 대 한 보안 보호를 향상 시킬 수 있는 여러 가지 방법이 있습니다. 대부분의 경우, Lync Server 2013를 배포 하는 기업은 이미 필요한 보안 인프라를 보유 하 고 있을 수 있습니다. 지침을 찾는 엔터프라이즈의 경우 Microsoft는 보안 IT 인프라를 구축 하는 방법의 예로 솔루션을 제공 합니다. 그러나이 솔루션이 유일한 솔루션 이라고 의미 하는 것은 아니며 Lync Server의 기본 설정 솔루션 이라고 의미 하지는 않습니다. 기업 고객은 IT 보안 인프라 및 요구 사항에 따라 특정 요구 사항에 맞는 솔루션을 선택 하는 것이 좋습니다. 예제 Microsoft 솔루션은 서버 및 도메인 격리를 위해 IPSec 및 그룹 정책을 채택 합니다. 자세한 내용은을 참조 [http://go.microsoft.com/fwlink/p/?LinkId=268544](http://go.microsoft.com/fwlink/p/?linkid=268544)하세요. 질문과 설명은 secwish@microsoft.com에 문의 하세요.

또 다른 문제 해결 방법은 백업 서비스 자체에서 보내는 데이터를 보호 하기 위해 IPSec을 사용 하는 것입니다. 이 방법을 선택 하는 경우 다음 서버에 대해 SMB 프로토콜에 대 한 IPSec 규칙을 구성 해야 하며, 여기에서 풀 A 및 풀 B는 2 쌍의 프런트 엔드 풀입니다.

  - 풀 A의 각 프런트 엔드 서버에서 풀 B에 사용 되는 파일 저장소 까지의 SMB 서비스 (TCP/445)

  - 풀 B의 각 프런트 엔드 서버에서 풀 A에 사용 되는 파일 저장소로 SMB 서비스 (TCP/445).

<div>


> [!WARNING]  
> IPsec는 SSL/TLS와 같은 응용 프로그램 수준의 보안을 대체 하는 것이 아닙니다. IPsec을 사용할 때의 이점 중 하나는 기존 응용 프로그램에 대 한 네트워크 트래픽 보안을 변경할 필요 없이 제공할 수 있다는 것입니다. 두 데이터 센터 간의 전송을 안전 하 게 보호 하려는 기업은 해당 네트워킹 하드웨어 공급 업체에 문의 하 여 공급 업체 장비를 사용 하 여 보안 WAN 연결을 설정 하는 방법을 알아봅니다.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

