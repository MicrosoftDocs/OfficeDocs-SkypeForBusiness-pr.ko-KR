---
title: 'Lync Server 2013: 사용자별 음성 정책 할당'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user voice policy
ms:assetid: 9ee47ee7-1030-43b8-a4dc-bf685ea24659
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688155(v=OCS.15)
ms:contentKeyID: 49733758
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1528ef6124193023a0e5938caac7b40c2c6187a2
ms.sourcegitcommit: 9b1c138b39fd87e239a7b1c5051f30c633e7d813
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "44943931"
---
# <a name="assign-a-per-user-voice-policy-in-lync-server-2013"></a>Lync Server 2013에서 사용자별 음성 정책 할당

 


전역 및 사이트 수준 음성 정책은 Enterprise Voice를 사용 하도록 설정 된 모든 Lync Server 2013 사용자 계정에 자동으로 할당 됩니다. Lync Server 2013 제어판 또는 Lync Server 2013 관리 셸을 사용 하 여 특정 사용자에 게 음성 정책을 할당할 수도 있습니다. 사용자 단위 정책을 Lync Server 사용자에 게 명시적으로 할당 하려면이 항목의 절차를 사용 합니다.

## <a name="to-assign-a-user-specific-voice-policy-using-the-lync-server-control-panel"></a>Lync Server 제어판을 사용 하 여 사용자 관련 음성 정책을 할당 하려면

1.  CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.

2.  브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.

3.  왼쪽 탐색 모음에서 **사용자**를 클릭하고 구성할 사용자 계정을 검색합니다.

4.  검색 결과가 나열된 표에서 사용자 계정을 클릭하고 **편집**을 클릭한 후에 **자세한 정보 표시**를 클릭합니다.

5.  **음성 정책** 아래의 **Lync Server 사용자 편집**에서 적용할 사용자 정책을 선택합니다.
    

    > [!NOTE]  
    > <STRONG> &lt; 자동 &gt; </STRONG> 설정은 기본 서버 또는 전역 정책 설정을 적용 합니다.



## <a name="assign-per-user-voice-policies"></a>사용자별 음성 정책 할당

Windows PowerShell 및 **set-csvoicepolicy** cmdlet을 사용 하 여 사용자별 음성 정책을 할당할 수 있습니다. Lync Server 2013 관리 셸 또는 Windows PowerShell의 원격 세션에서이 cmdlet을 실행할 수 있습니다. 원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용을 보려면이 Lync Server Windows PowerShell 블로그 게시물: [빠른 시작: 원격 PowerShell을 사용 하 여 Microsoft Lync server 2010 관리](https://go.microsoft.com/fwlink/p/?linkId=255876)를 참조 하세요.

### <a name="assign-a-per-user-voice-policy-to-a-single-user"></a>단일 사용자에 게 사용자별 음성 정책 할당

  - 다음 명령은 사용자 Ken Myer에게 사용자별 음성 정책 RedmondVoicePolicy를 할당합니다.
    
        Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

## <a name="assign-a-per-user-voice-policy-to-multiple-users"></a>여러 사용자에 게 사용자별 음성 정책 할당

  - 이 명령은 사용자별 음성 정책 FinanceVoicePolicy를 Active Directory의 Finance OU에 계정이 있는 모든 사용자에게 할당합니다. 이 명령에 사용 되는 OU 매개 변수에 대 한 자세한 내용은 [csuser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) u i c c i c c a c c # cmdlet의 설명서를 참조 하십시오.
    
        Get-CsUser -OU "ou=Finance,ou=North America,dc=litwareinc,dc=com" | Grant-CsVoicePolicy -PolicyName "FinanceVoicePolicy"

## <a name="unassign-a-per-user-voice-policy"></a>사용자별 음성 정책 할당 해제

  - The following command unassigns any per-user voice policy previously assigned to Ken Myer. After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy. A site policy takes precedence over the global policy.
    
        Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName $Null

자세한 내용은 [set-csvoicepolicy](https://technet.microsoft.com/library/gg398828\(v=ocs.15\)) cmdlet에 대 한 도움말 항목을 참조 하십시오.

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 Enterprise Voice에 대 한 사용자 사용 안 함](lync-server-2013-disable-a-user-for-enterprise-voice.md)  


[Lync Server 2013 관리 셸](lync-server-2013-lync-server-management-shell.md)

