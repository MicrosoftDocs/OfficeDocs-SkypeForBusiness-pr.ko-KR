---
title: 'Lync Server 2013: 공용 사용자 액세스를 제어하도록 정책 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure policies to control public user access
ms:assetid: 090aea0f-ef0b-49da-9c80-02d9279f2fa6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520946(v=OCS.15)
ms:contentKeyID: 48183343
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b348abcce00eb57988c7aa5184c0cfb5ea302adb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763280"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-policies-to-control-public-user-access-in-lync-server-2013"></a>Lync Server 2013에서 공용 사용자 액세스를 제어하도록 정책 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-10-07_

공용 im (인스턴트 메시징) 연결을 사용 하면 조직의 사용자가 인터넷 서비스, Yahoo\!및 AOL의 Windows Live 네트워크를 포함 하 여 공용 메신저 서비스 공급자가 제공 하는 im 서비스 사용자와 통신할 수 있습니다. 공용 사용자가 내부 Lync Server 사용자와 공동 작업할 수 있는지 여부를 제어 하는 하나 이상의 외부 사용자 액세스 정책을 구성 합니다. 공용 인스턴트 메시징 연결은 배포 및 사용자의 구성에 의존 하는 추가 된 기능입니다. 또한 공용 IM 공급자에서 서비스를 제공 하는 방법에 따라서도 달라 집니다. 공용 공급자를 사용 하도록 배포를 프로 비전 하는 방법에 대 한 자세한 내용은 "공용 IM 연결 가이드 Microsoft Lync Server, Office Communications Server 및 Live Communications Server" 가이드를 참조 하세요.[http://go.microsoft.com/fwlink/?LinkId=269821](http://go.microsoft.com/fwlink/?linkid=269821)

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P>2012 년 9 월 1 일부 터, Microsoft Lync 공용 IM 연결 사용자 구독 라이선스 ("PIC USL")는 신규 또는 갱신 계약에 대해 더 이상 구매할 수 없습니다. 활성 라이선스가 있는 고객은 계속 Yahoo!에 페더레이션 할 수 있습니다. 서비스 종료 날짜가 될 때까지 메신저를 종료 합니다. AOL 및 Yahoo!에 대 한 6 월 2014의 기간 종료 날짜 님이 발표 되었습니다. 자세한 내용은 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013에서 공개 인스턴트 메신저 연결 지원을</A>참조 하세요.</P>
> <LI>
> <P>PIC USL은 Lync Server 또는 Office Communications Server와 Yahoo!에 페더레이션 하는 데 필요한 사용자별 사용자 단위 구독 라이선스입니다. 받으려면. 이 서비스를 제공 하는 Microsoft의 기능은 기본 계약 인 Yahoo!에 대 한 지원을 받을 수 있습니다.</P>
> <LI>
> <P>이전 보다 훨씬 더 많은 수의 Lync는 전세계의 조직과 사용자 간에 연결 하는 강력한 도구입니다. Windows Live Messenger를 사용 하는 페더레이션에서는 Lync 표준 CAL 외에 추가 사용자/장치 라이선스가 필요 하지 않습니다. Skype 페더레이션이이 목록에 추가 되어 Lync 사용자가 IM 및 음성을 사용 하 여 수백만 명의 사용자에 게 연락할 수 있도록 합니다.</P></LI></UL>



</div>

Microsoft Lync Server 공용 IM 연결 프로 비전 사이트에 액세스 하려면 다음 링크를 사용 합니다.[http://go.microsoft.com/fwlink/p/?linkId=212638](http://go.microsoft.com/fwlink/p/?linkid=212638)

공용 사용자 액세스를 제어 하기 위해 전역, 사이트 및 사용자 수준에서 정책을 구성할 수 있습니다. 구성할 수 있는 정책의 유형에 대 한 자세한 내용은 배포 설명서 또는 계획 설명서의 [Lync Server 2013에서 외부 사용자 액세스에 대 한 지원 구성을](lync-server-2013-configuring-support-for-external-user-access.md) 참조 하세요. 하나의 정책 수준에서 적용 되는 Lync Server 정책 설정은 다른 정책 수준에서 적용 된 설정을 재정의할 수 있습니다. Lync Server 정책 우선 순위: 사용자 정책 (대부분의 영향을 주지 않음)이 사이트 정책을 무시 하 고 사이트 정책이 글로벌 정책에 우선 합니다 (최소 영향). 즉 정책 설정이 정책에 영향을 미치는 개체에 대 한 자세한 내용은 개체에 더 많은 영향을 줍니다.

IM 초대의 경우 응답은 클라이언트 소프트웨어에 따라 달라 집니다. 외부 보낸 사람이 사용자 구성 규칙 (즉, 사용자의 클라이언트 **허용** 및 **차단** 목록의 설정)에 의해 명시적으로 차단 되지 않는 한 요청이 허용 됩니다. 또한 사용자가 **허용** 목록에 없는 사용자의 모든 IM을 차단 하는 경우 메신저 대화 초대가 차단 될 수 있습니다.

<div>


> [!NOTE]  
> 조직을 위해 페더레이션을 설정 하지 않은 경우에도 정책을 구성 하 여 공용 사용자 액세스를 제어할 수 있습니다. 그러나 구성 하는 정책은 조직에 페더레이션이 설정 되어 있는 경우에만 적용 됩니다. 페더레이션 사용에 대 한 자세한 내용은 배포 설명서 또는 운영 설명서의 <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Lync Server 2013에서 원격 사용자 액세스 사용 또는 사용 안 함을</A> 참조 하세요. 또한 공용 사용자 액세스를 제어 하는 사용자 정책을 지정 하는 경우에는 Lync Server에 대해 사용 하도록 설정 하 고 정책을 사용 하도록 구성 된 사용자 에게만 정책이 적용 됩니다. Lync Server에 로그인 할 수 있는 공용 사용자를 지정 하는 방법에 대 한 자세한 내용은 배포 설명서 또는 운영 설명서의 <A href="lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md">Lync server 2013에서 lync 사용 가능 사용자에 게 외부 사용자 액세스 정책 할당</A> 을 참조 하세요.



</div>

하나 이상의 공용 IM 공급자 사용자가 액세스를 지원 하도록 정책을 구성 하려면 다음 절차를 사용 합니다.

<div>

## <a name="to-configure-an-external-access-policy-to-support-public-user-access"></a>공용 사용자 액세스를 지원 하도록 외부 액세스 정책을 구성 하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.

3.  왼쪽 탐색 모음에서 **외부 사용자 액세스**를 클릭 한 다음 **외부 액세스 정책을**클릭 합니다.

4.  **외부 액세스 정책** 페이지에서 다음 중 하나를 수행 합니다.
    
      - 전역 정책을 구성 하 여 공용 사용자 액세스를 지원 하려면 전역 정책을 클릭 하 고 **편집**을 클릭 한 다음 **세부 정보 표시**를 클릭 합니다.
    
      - 새 사이트 정책을 만들려면 **새로 만들기**를 클릭 한 다음 **사이트 정책을**클릭 합니다. **사이트 선택**의 목록에서 해당 사이트를 클릭 한 다음 **확인**을 클릭 합니다.
    
      - 새 사용자 정책을 만들려면 **새로 만들기**를 클릭 한 다음 **사용자 정책을**클릭 합니다. **새 외부 액세스 정책**에서 사용자 정책에 대 한 설명 (예: 공용 사용자에 게 통신을 사용 하도록 설정 하는 사용자 정책에 대해 **public사용자** 를 지정 하는 경우)의 **이름** 필드에 고유한 이름을 만듭니다.
    
      - 기존 정책을 변경 하려면 표에 나열 된 적절 한 정책을 클릭 하 고 **편집**을 클릭 한 다음 **세부 정보 표시**를 클릭 합니다.

5.  ) 설명을 추가 하거나 편집 하려면 **설명**에서 정책에 대 한 정보를 지정 합니다.

6.  다음 중 하나를 수행 합니다.
    
      - 정책에 대 한 공용 사용자 액세스를 사용 하도록 설정 하려면 **공용 사용자와 통신 사용** 확인란을 선택 합니다.
    
      - 정책에 대해 공용 사용자 액세스를 사용 하지 않도록 설정 하려면 **공용 사용자와 통신 사용** 확인란의 선택을 취소 합니다.

7.  **커밋**을 클릭합니다.

공용 사용자 액세스를 사용 하도록 설정 하려면 조직의 페더레이션에 대 한 지원도 사용 하도록 설정 해야 합니다. 자세한 내용은 [Lync Server 2013에서 페더레이션된 사용자 액세스를 제어 하도록 정책 구성을](lync-server-2013-configure-policies-to-control-federated-user-access.md)참조 하세요.

사용자 정책 인 경우 공용 사용자와 공동 작업을 수행할 수 있는 공용 사용자에 게 정책만 적용 해야 합니다. 자세한 내용은 [Lync Server 2013에서 사용자별 정책 지정](lync-server-2013-assigning-per-user-policies.md)을 참조 하세요.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 공용 SIP 페더레이션 공급자 만들기 또는 편집](lync-server-2013-create-or-edit-public-sip-federated-providers.md)  


[Lync Server 2013에서 조직에 대한 SIP 페더레이션 공급자 관리](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

