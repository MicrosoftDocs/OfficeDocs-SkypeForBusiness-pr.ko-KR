---
title: Lync Server 2013 Active Directory 지원
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Active Directory support
ms:assetid: 28ed9ac4-586d-4803-ad45-99c4fa793f54
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425756(v=OCS.15)
ms:contentKeyID: 48183679
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8a7da4487c376ceea4c5c3e41e20a55874b27f06
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200001"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="active-directory-support-in-lync-server-2013"></a>Lync Server 2013의 Active Directory 지원

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-12-04_

Lync Server 2013에서 지원 되는 Active Directory 도메인 서비스 온-프레미스 토폴로지는 다음과 같습니다.

  - 도메인이 하나인 단일 포리스트

  - 트리가 하나이고 도메인이 여러 개인 단일 포리스트

  - 트리 여러 개와 연결되지 않은 네임스페이스가 포함된 단일 포리스트

  - 중앙 포리스트 토폴로지의 다중 포리스트

  - 리소스 포리스트 토폴로지의 다중 포리스트

<div>


> [!NOTE]  
> Lync Server 2013에서는 단일 레이블 도메인을 지원 하지 않습니다. 예를 들어 <STRONG>contoso. local</STRONG> 이라는 루트 도메인을 사용 하는 포리스트는 지원 되지만 <STRONG>로컬</STRONG> 이라는 단일 레이블 루트 도메인은 지원 되지 않습니다. 자세한 내용은 Microsoft 기술 자료 문서 300684, "단일 레이블 DNS 이름이 있는 도메인에 대 한 Windows 구성 정보"를 참조 하세요 <A href="https://go.microsoft.com/fwlink/p/?linkid=143752">https://go.microsoft.com/fwlink/p/?linkId=143752</A>.



</div>

<div>


> [!NOTE]  
> Lync Server 2013에서는 도메인 이름을 바꿀 수 없습니다. Lync Server가 배포 되는 도메인의 이름을 바꾸려는 경우에는 먼저 Lync Server를 제거한 다음 도메인 이름을 바꾼 다음 Lync Server를 다시 설치 해야 합니다.



</div>

온-프레미스 배포를 위한 지원 되는 토폴로지 및 요구 사항에 대 한 자세한 내용은 계획 설명서에서 [Active Directory 도메인 서비스 요구 사항, 지원 및 토폴로지를 Lync Server 2013](lync-server-2013-active-directory-domain-services-requirements-support-and-topologies.md) 을 참조 하십시오.

</div>

<span> </span>

</div>

</div>

</div>

