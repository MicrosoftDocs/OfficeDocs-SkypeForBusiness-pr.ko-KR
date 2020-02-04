---
title: 'Lync Server 2013: 통합 된 대화 상대 저장소를 사용 하도록 Lync 서버 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Lync Server 2013 to use the unified contact store
ms:assetid: 6aa17ae3-764e-4986-a900-85a3cdb8c1fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688083(v=OCS.15)
ms:contentKeyID: 49733680
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 794d14172c5932436d46fbeb66ea1da4dd7a5e44
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762786"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-microsoft-lync-server-2013-to-use-the-unified-contact-store"></a>통합 된 대화 상대 저장소를 사용 하도록 Microsoft Lync Server 2013 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2014-02-07_

통합 된 연락처 저장소를 사용 하면 사용자가 단일 대화 상대 목록을 유지 관리 하 고 Microsoft Lync 2013, Microsoft Outlook 2013, Microsoft Outlook Web App 2013을 비롯 한 여러 응용 프로그램에서 해당 연락처를 사용할 수 있습니다. 사용자에 대 한 통합 된 연락처 저장소를 사용 하도록 설정 하는 경우 사용자의 연락처가 Microsoft Lync Server 2013에 저장 되지 않고 SIP 프로토콜을 사용 하 여 검색 됩니다. 대신 Microsoft Exchange Server 2013에 저장 되 고 Exchange 웹 서비스를 사용 하 여 검색 합니다.

<div>


> [!NOTE]  
> 기술적으로 연락처 정보는 사용자의 Exchange 2013 사서함에 있는 한 쌍의 폴더에 저장 됩니다. 연락처는 최종 사용자에 게 표시 되는 Lync 연락처 라는 폴더에 저장 됩니다. 연락처에 대 한 메타 데이터는 최종 사용자에 게 표시 되지 않는 하위 폴더에 저장 됩니다.



</div>

<div>

## <a name="enabling-the-unified-contact-store-for-a-user"></a>사용자에 대해 통합 된 연락처 저장소 사용

Lync Server 2013 및 Exchange 2013 간에 서버 간 인증을 이미 구성한 경우에도 통합 된 연락처 저장소를 사용할 수 있습니다. 추가 서버 구성은 필요 하지 않습니다. 그러나 사용자의 연락처를 통합 대화 상대 저장소로 이동 하려면 추가 사용자 계정 구성이 필요 합니다. 기본적으로 사용자 연락처는 통합 된 연락처 저장소가 아닌 Lync Server에 보관 됩니다.

통합 된 연락처 저장소에 대 한 액세스는 Lync Server 사용자 서비스 정책을 사용 하 여 관리 됩니다. 사용자 서버 정책에는 단일 속성 (일부는 허용 되지 않음)만 있습니다. 이 속성은 사용자의 연락처가 저장 되는 위치를 확인 하는 데 사용 됩니다. 사용자가 a를 True ($True)로 설정한 사용자 서비스 정책에 따라 관리 되는 경우 사용자의 연락처가 통합 대화 상대 저장소에 저장 됩니다. 사용자가 a를 False ($False)로 설정한 사용자 서비스 정책에 따라 관리 되는 경우 해당 연락처는 Lync Server에 저장 됩니다.

Lync Server 2013을 설치할 때 전역 범위에서 구성 된 단일 사용자 서비스 정책에도 설치 됩니다. 이 정책에서 사용할 수 있는 값이 True로 설정 되어 있으며,이는 기본적으로 사용자 연락처가 통합 된 연락처 저장소에 저장 됨을 의미 합니다 (이를 배포 하 고 구성한 경우). 모든 사용자 연락처를 통합 대화 상대 저장소로 마이그레이션하려면 아무런 작업도 수행 하지 않아도 됩니다.

모든 연락처를 통합 된 연락처 저장소로 마이그레이션하지 않으려면 전역 정책의 작업을 False로 설정 하 여 모든 사용자에 대해 통합 된 연락처 저장소를 사용 하지 않도록 설정할 수 있습니다.

    Set-CsUserServicesPolicy -Identity global -UcsAllowed $False

전역 정책에서 통합 된 연락처 저장소를 사용 하지 않도록 설정한 후에는 통합 된 연락처 저장소를 사용 하도록 설정 하는 사용자별 정책을 만들 수 있습니다. 이를 통해 일부 사용자는 통합 된 연락처 저장소에 연락처를 유지 하 고 다른 사용자는 계속 해 서 Lync 서버에서 연락처를 유지할 수 있습니다. 다음과 같은 명령을 사용 하 여 사용자별 사용자 서비스 정책을 만들 수 있습니다.

    New-CsUserServicesPolicy -Identity "AllowUnifiedContactStore" -UcsAllowed $True

새 정책을 만든 후에는 통합 된 연락처 저장소에 대 한 액세스 권한이 있는 모든 사용자에 게 해당 정책을 할당 해야 합니다. 사용자 단위 정책은 다음과 같은 명령을 사용 하 여 사용자에 게 할당할 수 있습니다.

    Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "AllowUnifiedContactStore"

정책이 지정 된 후에는 Lync Server가 사용자의 연락처를 통일 된 연락처 저장소로 마이그레이션하기 시작 합니다. 마이그레이션이 완료 되 면 사용자는 Lync Server 대신 Exchange에 저장 된 연락처를 갖게 됩니다. 마이그레이션이 완료 될 때 사용자가 Lync 2013에 로그온 되어 있으면 메시지 상자가 표시 되 고 Lync를 로그 오프 한 다음 프로세스를 완료 하기 위해 다시 로그온 하 라는 메시지가 나타납니다. 이 사용자별 정책에 할당 되지 않은 사용자의 연락처는 통합 된 연락처 저장소로 마이그레이션되지 않습니다. 그 이유는 해당 사용자는 전역 정책에 따라 관리 되 고 있으며, 통합 된 대화 상대 저장소는 전역 정책에서 사용 하지 않도록 설정 되었기 때문입니다.

Lync Server Management Shell 내에서 [CsUnifiedContactStore](https://docs.microsoft.com/powershell/module/skype/Test-CsUnifiedContactStore) cmdlet을 실행 하 여 사용자의 연락처가 통합 된 연락처 저장소로 성공적으로 마이그레이션 되었는지 확인할 수 있습니다.

    Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"

테스트-CsUnifiedContactStore 성공한 경우 사용자 sip:kenmyer@litwareinc.com에 대 한 연락처가 통합 된 연락처 저장소로 마이그레이션 되었음을 의미 합니다.

</div>

<div>

## <a name="rolling-back-the-unified-contact-store"></a>통합 된 대화 상대 저장소 롤백

통합 된 연락처 저장소에서 사용자의 연락처를 제거 해야 하는 경우 (예: 사용자가 Microsoft Lync Server 2010을 기반으로 하 여 더 이상 통합 된 연락처 저장소를 사용할 수 없는 경우) 두 가지 작업을 수행 해야 합니다. 먼저, 통합 된 연락처 저장소에 연락처 저장을 금지 하는 새 사용자 서비스 정책을 사용자에 게 할당 해야 합니다. (즉, 여러 부분을 허용 하는 속성을 $False로 설정한 정책) 이러한 정책이 없는 경우 다음과 같은 명령을 사용 하 여 만들 수 있습니다.

    New-CsUserServicesPolicy -Identity NoUnifiedContactStore -UcsAllowed $False

그러면 다음과 같은 명령을 사용 하 여이 새로운 사용자별 정책 (NoUnifiedContactStore)을 할당할 수 있습니다.

    Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName NoUnifiedContactStore

앞의 명령은 사용자: 진구 Myer에 새 정책을 할당 하 고: 진구의 연락처를 통합 대화 상대 저장소로 마이그레이션하는 것도 방지 합니다.

<div>


> [!NOTE]  
> 일부 경우에는 단순히 사용자의 현재 사용자 서비스 정책을 할당 취소 하 여 동일한 네트워크 효과를 얻을 수 있습니다. 예를 들어: 진구 Myer에는 통합 대화 상대 저장소를 사용할 수 있는 사용자 단위 정책이 있지만, 전역 정책은 통합 된 연락처 저장소의 사용을 금지 한다고 가정 합니다. 이 경우: 진구의 사용자 단위 서비스 정책을 할당 해제할 수 있습니다. 이렇게 하면: 진구이 전역 정책에 의해 자동으로 관리 되므로 더 이상 통합 된 연락처 저장소에 액세스할 수 없습니다.<BR>이전에 할당 된 사용자 단위 정책을 할당 취소 하려면 앞에서 설명한 것과 동일한 명령을 사용 하 되, 이번에는 PolicyName 매개 변수를 null 값으로 설정 합니다.<BR>부여-Csuser서비스 정책 – Id ": 진구 Myer" – PolicyName $Null



</div>

": 진구의 연락처를 통합 된 연락처 저장소로 마이그레이션하는 것을 금지" 라는 용어는 통합 된 연락처 저장소를 사용할 때 염두에 두어야 합니다. 새 사용자 서비스 정책: 진구 지정 하기만 해도 연락처가 통합 대화 상대 저장소 밖으로 이동 하지 않습니다. 사용자가 Lync Server 2013에 로그온 하면 시스템은 사용자의 사용자 서비스 정책을 검사 하 여 해당 연락처를 통합 대화 상대 저장소에 보관할지 여부를 확인 합니다. 대답이 yes 인 경우 (즉, (즉, to Sallowed 속성이 $True로 설정 된 경우) 해당 연락처는 통합 된 연락처 저장소로 마이그레이션됩니다 (해당 연락처가 아직 통합 대화 저장소에 있지 않은 경우). 아니오로 대답 한 경우에는 Lync Server가 사용자의 연락처를 무시 하 고 다음 작업으로 이동 합니다. 이는 사용자의 연락처를 통합 된 대화 상대 저장소 밖으로 이동 하는 것을 의미 하며,이는 일부 기능에는 허용 되지 않는 속성 값에 상관 없이

즉, 사용자에 게 새 사용자 서비스 정책을 할당 한 후에 [CsUcsRollback](https://docs.microsoft.com/powershell/module/skype/Invoke-CsUcsRollback) cmdlet을 실행 하 여 사용자의 연락처를 Exchange 2013에서 종료 하 고 다시 Lync Server 2013로 이동 해야 합니다. 예를 들어 새 사용자 서비스 정책에: 진구 Myer를 할당 한 후 다음 명령을 사용 하 여 연락처를 통합 된 연락처 저장소 외부로 이동할 수 있습니다.

    Invoke-CsUcsRollback -Identity "Ken Myer"

사용자 서비스 정책을 변경 했지만 실행 하지 않는 경우 CsUcsRollback cmdlet: 진구의 연락처는 통합 된 연락처 저장소에서 제거 되지 않습니다. CsUcsRollback를 실행 했지만: 진구 Myer의 사용자 서비스 정책은 변경 하지 않는 경우 어떻게 하나요? 이 경우: 진구의 연락처가 통합 된 연락처 저장소에서 일시적으로 제거 됩니다. 이 제거가 일시적인 것 이기는 데 유의 하세요. : 진구의 연락처가 통합 대화 상대 저장소에서 제거 된 후에 Lync Server 2013에서 7 일이 지난 후: 진구에 지정 된 사용자 서비스 정책이 있는지 확인 합니다. : 진구에 통합 된 연락처 저장소의 사용자를 설정 하는 정책이 할당 되 면 해당 연락처가 연락처 저장소로 다시 자동으로 이동 됩니다. 통합 된 대화 상대 저장소에서 연락처를 영구적으로 제거 하려면 CsUcsRollback cmdlet을 실행 하는 것 외에 사용자 서비스 정책을 변경 해야 합니다.

마이그레이션에 영향을 줄 수 있는 많은 수의 변수 때문에 계정이 통합 된 연락처 저장소에 완전히 마이그레이션 되기까지 걸리는 시간을 예측 하기가 어렵습니다. 그러나 일반적으로 마이그레이션이 즉시 적용 되지는 않습니다. 적은 수의 대화 상대를 마이그레이션하는 경우에도 이동이 완료 되기 전에 10 분 이상 걸릴 수 있습니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

