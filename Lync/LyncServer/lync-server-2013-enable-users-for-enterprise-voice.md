---
title: 'Lync Server 2013: 사용자가 Enterprise Voice를 사용할 수 있도록 설정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable users for Enterprise Voice
ms:assetid: f252b23b-9641-4160-aa81-bf06dc2eced3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413011(v=OCS.15)
ms:contentKeyID: 48185800
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c48f701f9396c43337e2723f0dc83a8eda8d96ee
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046691"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-users-for-enterprise-voice-in-lync-server-2013"></a>Lync Server 2013에서 Enterprise Voice를 사용할 수 있도록 사용자 설정

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-11-01_

하나 이상의 중재 서버에 대 한 파일을 설치 하 고, 아웃 바운드 호출 라우팅을 구성 하 고, 필요에 따라 하나 이상의 고급 Enterprise Voice 기능을 배포 하는 경우 다음 절차를 사용 하 여 사용자가 Enterprise Voice를 사용 하 여 전화를 걸 수 있습니다.

<div>


> [!NOTE]  
> 다음 절차 중 첫 번째 방법은 Lync Server 제어판을 사용 하 여 수행할 수 있습니다. 나머지 절차는 Lync Server 관리 셸을 사용 하는 경우에만 사용할 수 있습니다.



</div>

  - Enterprise Voice에 대 한 사용자 계정을 사용 하도록 설정 합니다.

  - 반드시 사용자 계정에 사용자별 음성 정책을 할당 합니다.

  - 반드시 사용자 계정에 사용자별 다이얼 플랜을 할당 합니다.

<div>

## <a name="to-enable-a-user-account-for-enterprise-voice"></a>Enterprise Voice에 대해 사용자 계정을 사용 하도록 설정 하려면

1.  CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.

2.  브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.

3.  왼쪽 탐색 모음에서 **사용자**를 클릭합니다.

4.  **사용자 검색** 상자에 사용하도록 설정할 사용자 계정의 표시 이름, 이름, 성, SAM(보안 계정 관리자) 계정 이름, SIP 주소 또는 줄 URI(Uniform Resource Identifier)를 모두 또는 첫부분을 입력하고 **찾기**를 클릭합니다.

5.  테이블에서 Enterprise Voice를 사용 하도록 설정 하려는 사용자 계정을 클릭 합니다.

6.  **편집** 메뉴에서 **자세한 정보 표시**를 클릭합니다.

7.  **Lync Server 사용자 편집** 페이지의 **전화 통신** 아래에서 **Enterprise Voice**를 클릭합니다.

8.  **줄 URI**를 클릭 하 고 정규화 된 고유 전화 번호를 입력 합니다 (예: tel-+ 14255550200).

9.  **커밋**을 클릭합니다.

사용자가 Enterprise Voice를 사용할 수 있도록 설정 하는 작업을 완료 하려면 사용자에 게 전역 (기본적으로 할당 됨) 인지 또는 사용자 마다 고유한 음성 정책 및 다이얼 플랜을 할당 해야 합니다.

기본적으로 모든 사용자에 게는 전역 음성 정책 및 다이얼 플랜을 할당 합니다. 사용자 계정이 홈으로 설정 된 사이트의 사이트 수준에 음성 정책 또는 다이얼 플랜이 있는 경우 해당 사이트 정책이 사용자에 게 자동으로 적용 됩니다. 사용자에 게 사용자별 음성 정책 또는 다이얼 플랜을 적용 하려면 **set-csvoicepolicy** 및 **Grant-csdialplan 플랜** cmdlet을 실행 해야 합니다. 자세한 내용은 [Lync Server 2013 관리 셸](lync-server-2013-lync-server-management-shell.md) 설명서를 참조 하십시오.

</div>

<div>

## <a name="voice-policy-assignment"></a>음성 정책 할당

전역 및 사이트 수준 음성 정책은 Enterprise Voice를 사용 하도록 설정 된 모든 사용자 계정에 자동으로 할당 됩니다. 특정 사용자 또는 그룹에 적용 되는 음성 정책을 만들 수도 있습니다. 이러한 사용자별 정책을 사용자 또는 그룹에 명시적으로 할당 해야 합니다. Enterprise Voice를 사용 하도록 설정 된 모든 사용자에 대해 전역 또는 사이트 음성 정책을 사용 하려면이 항목의 뒷부분에 나오는이 섹션을 건너뛰고 다이얼 플랜 할당을 계속 진행할 수 있습니다.

<div>

## <a name="to-assign-a-user-specific-voice-policy"></a>사용자 관련 음성 정책을 할당 하려면

1.  CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.

2.  **시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.

3.  기존 사용자 음성 정책을 사용자에게 할당하려면 명령 프롬프트에서 다음을 실행합니다.
    
        Grant-CsVoicePolicy -Identity <UserIdParameter> -PolicyName <String>
    
    예:
    
        Grant-CsVoicePolicy -Identity "Bob Kelly" -PolicyName VoicePolicyJapan
    
    이 예에서 표시 이름이 Bob 최소라 인 사용자에 게는 이름이 **voicepolicyjapan 인**인 음성 정책이 할당 됩니다.

사용자 관련 음성 정책을 할당 하거나 **set-csvoicepolicy** cmdlet을 실행 하는 방법에 대 한 자세한 내용은 [Lync Server 2013 관리 셸](lync-server-2013-lync-server-management-shell.md) 설명서를 참조 하십시오.

</div>

</div>

<span id="BKMK_DialPlanAssignment"></span>

<div>

## <a name="dial-plan-assignment"></a>다이얼 플랜 할당

Enterprise Voice 사용자 또는 전화 접속 회의 사용자에 대한 사용자 계정 구성을 완료하려면 사용자에게 다이얼 플랜이 할당되어 있어야 합니다. 사용자 계정은 기존 사용자 단위 다이얼 플랜을 명시적으로 할당 하지 않을 때 전역 다이얼 플랜을 자동으로 사용 하거나, 한 경우에는 사이트 수준 다이얼 플랜을 사용할 수 있습니다. Enterprise Voice를 사용할 수 있는 모든 사용자에 대해 전역 또는 사이트 다이얼 플랜을 사용 하려면이 섹션을 건너뛰어도 됩니다.

<div>

## <a name="to-assign-a-dial-plan"></a>다이얼 플랜을 할당 하려면

1.  CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.

2.  **시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.

3.  사용자별 다이얼 플랜을 할당하려면 명령 프롬프트에서 다음을 실행합니다.
    
        Grant-CsDialPlan -Identity <UserIdParameter> -PolicyName <String>
    
    예를 들면 다음과 같습니다.
    
        Grant-CsDialPlan -Identity "Bob Kelly" -PolicyName DialPlanJapan
    
    이 예에서는 표시 이름이 Bob 최소라 인 사용자에 게 이름이 **DialPlanJapan**사용자 다이얼 플랜을 할당 합니다.

사용자 다이얼 플랜을 할당 하거나 **Grant-CsDialPlan 플랜** cmdlet을 실행 하는 방법에 대 한 자세한 내용은 [Lync Server 2013 관리 셸](lync-server-2013-lync-server-management-shell.md) 설명서를 참조 하십시오.

</div>

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 Enterprise Voice에 대 한 사용자 사용 안 함](lync-server-2013-disable-a-user-for-enterprise-voice.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

