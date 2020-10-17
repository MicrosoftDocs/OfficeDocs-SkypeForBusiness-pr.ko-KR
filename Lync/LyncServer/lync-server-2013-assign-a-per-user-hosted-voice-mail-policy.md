---
title: 'Lync Server 2013: 사용자별 호스팅된 음성 메일 정책 할당'
description: 'Lync Server 2013: 사용자별 호스팅 음성 메일 정책을 할당 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user hosted voice mail policy
ms:assetid: d44c71a0-4407-4ab4-b7e0-d671dde3425f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398919(v=OCS.15)
ms:contentKeyID: 48185456
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 071d504c452b4d3adb1b636cb5c4ff8835200107
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559894"
---
# <a name="assign-a-per-user-hosted-voice-mail-policy-in-lync-server-2013"></a>Lync Server 2013에서 사용자별 호스팅 음성 메일 정책 할당

 


사용자별로 하나 이상의 호스팅된 음성 메일 정책을 배포하는 것은 선택 사항입니다. 사용자별 정책을 배포하려면 이 정책을 사용자, 개체 또는 대화 상대 개체에 명시적으로 할당해야 합니다.

사용자별 호스팅 음성 메일 정책에 대 한 할당을 할당 하거나 제거 하는 방법에 대 한 자세한 내용은 다음 cmdlet에 대 한 Lync Server 관리 셸 설명서를 참조 하십시오.

  - Grant-CsHostedVoicemailPolicy

  - Remove-CsHostedVoicemailPolicy

## <a name="to-assign-a-per-user-hosted-voice-mail-policy"></a>사용자별 호스팅된 음성 메일 정책을 할당하려면

1.  **시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.

2.  Grant-CsHostedVoicemailPolicy cmdlet를 실행하여 개별 사용자, 그룹 및 대화 상대 개체에 사용자별 호스팅된 음성 메일 정책을 할당합니다. 예를 들어 다음을 실행합니다.
    
        Grant-CsHostedVoicemailPolicy -Identity "Ken Myer" -PolicyName ExRedmond
    
    이 예에서는 ExRedmond hosted 음성 메일 정책이 Ken Myer라는 사용자에게 할당되었습니다.
    
    **Identity**는 수정할 사용자 계정을 지정합니다. Identity 값은 다음 형식 중 하나를 사용하여 지정할 수 있습니다.
    
      - 사용자의 SIP 주소
    
      - 사용자의 Active Directory 사용자 계정 이름
    
      - 사용자의 도메인 \\ 로그온 이름 (예: contoso \\ kenmyer)
    
      - 사용자의 Active Directory 도메인 서비스 표시 이름(예: Ken Myer). Id 값으로 Display-Name을 사용 하는 경우 별표 ( \* ) 와일드 카드 문자를 사용할 수 있습니다. 예를 들어 Id " \* smith"는 Display-Name 문자열 값 "smith"로 끝나는 모든 사용자를 반환 합니다.
    

    > [!NOTE]  
    > SAM 계정 이름은 포리스트에서 고유하지 않아도 되므로 사용자의 Active Directory SAM 계정 이름을 Identity 값으로 사용할 수 없습니다.


