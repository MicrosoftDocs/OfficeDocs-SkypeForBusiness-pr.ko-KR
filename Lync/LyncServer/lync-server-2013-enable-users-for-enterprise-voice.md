---
title: 'Lync Server 2013: Enterprise Voice 사용자 사용'
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
ms.openlocfilehash: 0b851c8807e12456c600b2ca176b0fa5a834f0d5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736018"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-users-for-enterprise-voice-in-lync-server-2013"></a>Lync Server 2013에서 엔터프라이즈 음성에 대 한 사용자 활성화

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-11-01_

하나 이상의 중재 서버에 대 한 파일을 설치 하 고, 아웃 바운드 호출 라우팅을 구성 하 고, 선택적으로 하나 이상의 고급 엔터프라이즈 음성 기능을 배포 하는 경우 다음 절차를 사용 하 여 사용자가 엔터프라이즈 음성을 사용 하 여 전화를 걸 수 있습니다.

<div>


> [!NOTE]  
> 다음 절차 중 첫 번째는 Lync Server 제어판을 사용 하 여 수행할 수 있습니다. 나머지 절차는 Lync Server 관리 셸로만 사용할 수 있습니다.



</div>

  - 엔터프라이즈 음성에 대 한 사용자 계정을 사용 하도록 설정 합니다.

  - ) 사용자 계정에 사용자 특정 음성 정책을 할당 합니다.

  - ) 사용자 계정에 사용자 특정 다이얼 플랜을 할당 합니다.

<div>

## <a name="to-enable-a-user-account-for-enterprise-voice"></a>엔터프라이즈 음성에 대 한 사용자 계정을 사용 하도록 설정 하려면

1.  CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.

3.  왼쪽 탐색 모음에서 **사용자**를 클릭 합니다.

4.  **사용자 검색** 상자에 표시 이름, 성, 이름, SAM (보안 계정 관리자) 계정 이름, SIP 주소 또는 사용 하도록 설정할 사용자 계정의 URI (Uniform resource identifier) 중 일부 또는 전체를 입력 한 다음 **찾기를**클릭 합니다.

5.  표에서 Enterprise Voice에 사용할 사용자 계정을 클릭 합니다.

6.  **편집** 메뉴에서 **세부 정보 표시**를 클릭 합니다.

7.  **Lync Server 사용자 편집** 페이지의 **전화 통신**에서 **엔터프라이즈 음성을**클릭 합니다.

8.  **줄 URI**를 클릭 한 다음 고유한 정규화 된 전화 번호를 입력 합니다 (예: tel: + 14255550200).

9.  **커밋**을 클릭합니다.

사용자가 엔터프라이즈 음성을 사용할 수 있도록 설정 하려면 사용자에 게 음성 정책 및 다이얼 플랜 (전역 (기본적으로 할당 됨) 인지 여부) 또는 사용자 관련 기능을 지정 해야 합니다.

기본적으로 모든 사용자에 게는 전역 음성 정책 및 다이얼 플랜을 할당 합니다. 사용자 계정이 속한 사이트의 사이트 수준에 음성 정책 또는 다이얼 플랜이 있는 경우 해당 사이트 정책이 사용자에 게 자동으로 적용 됩니다. 사용자 단위 음성 정책 또는 다이얼 플랜을 사용자에 게 적용 하려면 **CsVoicePolicy** 및 **부여-csdialplan 다이얼** cmdlet을 실행 해야 합니다. 자세한 내용은 [Lync Server 2013 관리 셸](lync-server-2013-lync-server-management-shell.md) 설명서를 참조 하세요.

</div>

<div>

## <a name="voice-policy-assignment"></a>음성 정책 할당

전역 및 사이트 수준 음성 정책은 Enterprise Voice에 대해 사용 하도록 설정 된 모든 사용자 계정에 자동으로 할당 됩니다. 특정 사용자 또는 그룹에 적용 되는 음성 정책을 만들 수도 있습니다. 이러한 사용자별 정책은 사용자 또는 그룹에 명시적으로 할당 되어야 합니다. Enterprise Voice를 사용 하도록 설정 된 모든 사용자에 대해 전역 또는 사이트 음성 정책을 사용 하려는 경우이 섹션을 건너뛰고이 항목의 뒷부분에 나오는 다이얼 플랜 할당 섹션을 계속할 수 있습니다.

<div>

## <a name="to-assign-a-user-specific-voice-policy"></a>사용자 관련 음성 정책 지정

1.  CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.

2.  Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.

3.  사용자에 게 기존 사용자 음성 정책을 할당 하려면 명령 프롬프트에서 다음을 실행 합니다.
    
        Grant-CsVoicePolicy -Identity <UserIdParameter> -PolicyName <String>
    
    예를 들면 다음과 같습니다.
    
        Grant-CsVoicePolicy -Identity "Bob Kelly" -PolicyName VoicePolicyJapan
    
    이 예제에서 표시 이름이 Bob 최소라 인 사용자에 게는 이름 **VoicePolicyJapan**음성 정책이 할당 됩니다.

사용자 관련 음성 정책 지정 또는 **CsVoicePolicy** cmdlet 실행에 대 한 자세한 내용은 [Lync Server 2013 관리 셸](lync-server-2013-lync-server-management-shell.md) 설명서를 참조 하세요.

</div>

</div>

<span id="BKMK_DialPlanAssignment"></span>

<div>

## <a name="dial-plan-assignment"></a>다이얼 플랜 배정

Enterprise Voice 사용자 또는 전화 접속 회의 사용자에 대 한 사용자 계정 구성을 완료 하려면 사용자에 게 다이얼 플랜을 할당 해야 합니다. 사용자 계정에 글로벌 다이얼 플랜 (있는 경우)이 자동으로 사용 되며, 기존 사용자 단위 다이얼 플랜을 명시적으로 할당 하지 않은 경우에는 사이트 수준 다이얼 플랜입니다. Enterprise Voice를 사용 하도록 설정 된 모든 사용자에 대해 전역 또는 사이트 다이얼 플랜을 사용 하려는 경우이 섹션을 건너뛸 수 있습니다.

<div>

## <a name="to-assign-a-dial-plan"></a>다이얼 플랜 지정

1.  CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.

2.  Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.

3.  사용자 지정 다이얼 플랜을 할당 하려면 명령 프롬프트에서 다음을 실행 합니다.
    
        Grant-CsDialPlan -Identity <UserIdParameter> -PolicyName <String>
    
    예를 들면 다음과 같습니다.
    
        Grant-CsDialPlan -Identity "Bob Kelly" -PolicyName DialPlanJapan
    
    이 예제에서 표시 이름이 Bob 최소라 인 사용자는 이름 **DialPlanJapan**를 사용 하 여 사용자 다이얼 플랜을 할당 합니다.

사용자 다이얼 플랜 또는 **부여-CsDialPlan 다이얼** cmdlet을 실행 하는 방법에 대 한 자세한 내용은 [Lync Server 2013 관리 셸](lync-server-2013-lync-server-management-shell.md) 설명서를 참조 하세요.

</div>

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 엔터프라이즈 음성에 대 한 사용자 사용 안 함](lync-server-2013-disable-a-user-for-enterprise-voice.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

