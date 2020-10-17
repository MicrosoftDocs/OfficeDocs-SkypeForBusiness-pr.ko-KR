---
title: 'Lync Server 2013: 공개 키 인프라'
description: 'Lync Server 2013: 공개 키 인프라'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Public Key Infrastructure for Lync Server 2013
ms:assetid: 737c8a25-23e9-4494-ab76-5a7b729b44ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481131(v=OCS.15)
ms:contentKeyID: 59893870
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0b8f2ee8c6b1524cec461ad90a4d4cb1a1003b51
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565564"
---
# <a name="public-key-infrastructure-for-lync-server-2013"></a>Lync Server 2013 용 공개 키 인프라

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-11-13_

Microsoft Lync Server 2013에서는 인증서를 사용 하 여 서버를 인증 하 고 클라이언트와 서버 간 및 서로 다른 서버 역할 간에 트러스트 체인을 설정 합니다. Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows server 2008 및 Windows Server 2003 PKI (공개 키 인프라)에서는이 신뢰 체인을 설정 하 고 유효성을 검사 하기 위한 인프라를 제공 합니다.

인증서는 디지털 Id입니다. 이름으로 서버를 식별 하 고 해당 속성을 지정 합니다. 인증서에 대 한 정보가 올바른지 확인 하려면 클라이언트 또는 서버에 연결 하는 다른 서버에서 신뢰 하는 CA에서 인증서를 발급 해야 합니다. 서버가 개인 네트워크에 있는 다른 클라이언트 및 서버에만 연결 하는 경우에는 CA가 엔터프라이즈 CA가 될 수 있습니다. 서버가 개인 네트워크 외부의 엔터티와의 상호 작용 하는 경우 공용 CA가 필요할 수도 있습니다.

인증서의 정보가 유효하더라도 인증서를 제공하는 서버가 실제로 인증서에 나와 있는 서버인지를 확인하는 방법이 있어야 합니다. 이를 위해 Windows PKI를 사용합니다.

각 인증서는 공개 키에 연결됩니다. 인증서에 이름이 지정되어 있는 서버는 다른 위치에서는 알 수 없는 해당 개인 키를 포함합니다. 이 서버에 연결하는 클라이언트 또는 서버는 공개 키를 사용하여 임의의 정보를 암호화한 다음 서버로 보냅니다. 서버에서 이 정보의 암호를 해독하여 일반 텍스트로 반환하면 연결 대상 엔터티는 해당 서버가 인증서의 개인 키를 포함하며 인증서에 이름이 나와 있는 서버임을 확인할 수 있습니다.

<div>


> [!NOTE]  
> 모든 공용 Ca가 Lync Server 2013 인증서의 요구 사항을 준수 하는 것은 아닙니다. 따라서 인증된 공용 CA 공급업체 목록을 참조하여 공용 인증서 요구 사항을 확인하는 것이 좋습니다. 자세한 내용은의 통합 통신 인증서 파트너를 참조 하세요 <A href="https://go.microsoft.com/fwlink/p/?linkid=140898">https://go.microsoft.com/fwlink/p/?LinkId=140898</A> .



</div>

<div>

## <a name="crl-distribution-points"></a>CRL 배포 지점

Lync Server 2013에서는 모든 서버 인증서에 CRL (인증서 해지 목록) 배포 지점을 하나 이상 포함 해야 합니다. CDP(CRL 배포 지점)는 인증서 발급 시점 이후로 인증서가 해지되지 않았는지 그리고 인증서가 아직 유효 기간 내에 있는지 확인하기 위해 CRL을 다운로드할 수 있는 위치입니다. CRL 배포 지점은 인증서 속성에 URL로 기록되며 일반적으로 보안 HTTP입니다.

</div>

<div>

## <a name="enhanced-key-usage"></a>향상 키 사용

Lync Server 2013에서는 서버 인증 목적으로 모든 서버 인증서에 대해 EKU (확장 된 키 사용)를 지원 해야 합니다. 서버 인증을 위해 EKU 필드를 구성하면 인증서를 서버 인증용으로 사용할 수 있습니다. 이 EKU는 MTLS에 필수적인 요소입니다. EKU에 여러 항목을 포함하여 인증서를 다양한 용도로 활용할 수 있습니다.

<div>


> [!NOTE]  
> Live Communications Server 2003 및 Live Communications Server 2005로부터의 아웃바운드 MTLS 연결에는 클라이언트 인증 EKU가 필요했지만 이제는 더 이상 필요하지 않습니다. 그러나 공용 IM 연결을 통해 AOL에 연결하는 에지 서버에는 이 EKU가 있어야 합니다.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

