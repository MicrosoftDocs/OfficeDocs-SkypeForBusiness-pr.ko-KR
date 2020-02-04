---
title: 'Lync Server 2013: 사용자에 대 한 전화 통신 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure telephony for a user
ms:assetid: 4546432e-c839-4517-a2c5-bc0d4d8c6a03
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520988(v=OCS.15)
ms:contentKeyID: 48183987
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d57c4799c0fe9bb9dc698c3e0e74a9d73cbde524
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740008"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-telephony-for-a-user-in-lync-server-2013"></a>Lync Server 2013에서 사용자에 대 한 전화 통신 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-11-01_

전화 통신 설정은 사용자의 Lync Server 제어판에서 구성할 수 있는 사용자 계정의 개별 설정 (즉, 개별 사용자가 Lync Server 2013에 대해 사용 하도록 설정 되어 있고, 조직에서 전화 접속을 지 원하는 경우).

Lync Server 사용자 전화 통신 옵션에는 다음이 포함 됩니다.

  - **오디오/비디오 사용 안 함**   사용자가 오디오 및 비디오로 전화를 걸 수 없습니다.

  - **Pc 대 pc 사용자만**   pc에서 pc 음성 또는 영상 통화를 할 수 있습니다.

  - **Enterprise Voice**   사용자는 Lync Server 2013 인프라를 사용 하 여 모든 수신 및 발신 전화를 라우팅할 수 있습니다. 사용자는 PC 대 PC 전화도 할 수 있습니다.

  - **원격 통화 제어**   사용자는 Lync Server 2013을 사용 하 여 데스크톱 전화를 제어할 수 있으며 pc 대 pc 전화도 할 수 있습니다.

조직의 전화 통신을 구성 하는 방법에 대 한 자세한 내용은 [Lync server 2013에서 사용자에 대 한 전화 통신 구성](lync-server-2013-configure-telephony-for-a-user.md) 및 [lync Server 2013](lync-server-2013-deploying-enterprise-voice.md) 의 배포 설명서에서 엔터프라이즈 음성 배포를 참조 하세요.

<div>

## <a name="to-configure-telephony-for-a-specific-user-account"></a>특정 사용자 계정에 대 한 전화 통신 구성

1.  CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.

3.  왼쪽 탐색 모음에서 **사용자**를 클릭 합니다.

4.  **사용자 검색** 상자에 원하는 사용자 계정의 표시 이름, 이름, 성, SAM (보안 계정 관리자) 계정 이름, SIP 주소 또는 줄의 URI (Uniform resource identifier) 중 일부 또는 전체를 입력 한 다음 **찾기를**클릭 합니다.

5.  표에서 수정 하려는 사용자 계정을 클릭 합니다.

6.  **편집** 메뉴에서 **수정을**클릭 합니다.

7.  **전화 통신**에서 다음을 수행 합니다.
    
      - 사용자에 게 오디오 및 비디오 통화를 사용 하지 않도록 설정 하려면 **오디오/비디오 사용 안 함을**클릭 합니다.
    
      - 사용자에 대해 PC 대 PC 오디오 통신을 사용 하도록 설정 하 고, 원격 통화 제어 또는 엔터프라이즈 음성을 지원 하지 않으려면 **pc 대 pc 전용**을 클릭 합니다. 사용자가 PC 대 PC 오디오 통신에 사용 하는 전화의 **회선 URI** 값을 지정 합니다.
    
      - Pc 대 PC 오디오 통신을 비롯 한 서비스 정책 수업에 따라 Lync Server 2010 인프라를 사용 하 여 사용자의 전화 통화를 라우팅하려면 **엔터프라이즈 음성을**클릭 합니다. **줄 URI**에서 엔터프라이즈 음성의 전화 번호를 지정 합니다. **다이얼 플랜 정책** 및 **음성 정책**에서 사용자에 대 한 적절 한 정책을 지정 합니다. 사용자가 거는 전화 번호를 E 164 형식으로 변환 하기 위한 정규화 규칙을 지정 하려면 **위치 정책**에서 적절 한 위치 프로필을 선택 합니다.
    
      - 사용자가 Lync Server 2013에서 데스크톱 전화선을 제어할 수 있도록 하는 원격 통화 제어 기능을 사용 하도록 설정 하려면 PC에서 PC로 거는 통화와 PC에서 전화 통화를 하는 데 **원격 통화 제어**를 클릭 합니다. **줄 URI**에서 원격 통화 제어에 대 한 전화 번호를 지정 합니다. 사용자에 게는 전화 라우팅에 대해 데스크톱 전화 및 PBX (개인 브랜치 교환) 연결이 있어야 합니다.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 사용자 계정 속성 수정](lync-server-2013-modifying-user-account-properties.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

