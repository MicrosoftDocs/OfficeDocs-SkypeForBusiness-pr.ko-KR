---
title: 'Lync Server 2013: 사용자 단위 호스팅 음성 메일 정책 할당'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Assign a per-user hosted voice mail policy
ms:assetid: d44c71a0-4407-4ab4-b7e0-d671dde3425f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398919(v=OCS.15)
ms:contentKeyID: 48185456
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2202e1b4c03eb25d12e46c3a533313a54bc76c4f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978929"
---
# <a name="assign-a-per-user-hosted-voice-mail-policy-in-lync-server-2013"></a>Lync Server 2013에서 사용자 단위 호스팅 음성 메일 정책 할당

 


하나 이상의 사용자 단위 호스팅 음성 메일 정책을 배포 하는 것은 선택 사항입니다. 사용자별 정책을 배포 하는 경우 사용자, 그룹 또는 연락처 개체에 명시적으로 할당 해야 합니다.

사용자 단위 호스팅 음성 메일 정책의 할당을 할당 하거나 제거 하는 방법에 대 한 자세한 내용은 다음 cmdlet에 대 한 Lync Server 관리 셸 설명서를 참조 하세요.

  - 부여-CsHostedVoicemailPolicy

  - 제거-CsHostedVoicemailPolicy

## <a name="to-assign-a-per-user-hosted-voice-mail-policy"></a>사용자 단위 호스팅 음성 메일 정책을 할당 하려면

1.  Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.

2.  CsHostedVoicemailPolicy cmdlet을 실행 하 여 개별 사용자, 그룹 및 연락처 개체에 사용자 단위 호스팅 음성 메일 정책을 할당 합니다. 예를 들어 다음을 실행합니다.
    
        Grant-CsHostedVoicemailPolicy -Identity "Ken Myer" -PolicyName ExRedmond
    
    이 예제에서는 ExRedmond 호스팅 음성 메일 정책을 사용자: 진구 Myer에 할당 했습니다.
    
    **Id** 수정할 사용자 계정을 지정 합니다. Id 값은 다음 형식 중 하나를 사용 하 여 지정할 수 있습니다.
    
      - 사용자의 SIP 주소
    
      - 사용자의 Active Directory 사용자-주 이름
    
      - 사용자의 도메인\\로그온 이름 (예: contoso\\kenmyer)
    
      - 사용자의 Active Directory 도메인 서비스 표시 이름 (예:: 진구 Myer) 표시 이름을 Id 값으로 사용 하는 경우 별표 (\*) 와일드 카드 문자를 사용할 수 있습니다. 예를 들어 Id "\* smith"는 "smith" 문자열 값으로 끝나는 표시 이름을 가진 모든 사용자를 반환 합니다.
    

    > [!NOTE]  
    > SAM-계정 이름이 포리스트에서 고유 하지 않아도 되므로 사용자의 Active Directory SAM-계정 이름을 Id 값으로 사용할 수 없습니다.


