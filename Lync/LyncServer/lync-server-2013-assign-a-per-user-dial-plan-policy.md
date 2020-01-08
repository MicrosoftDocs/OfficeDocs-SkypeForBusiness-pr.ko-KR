---
title: 'Lync Server 2013: 사용자 단위 다이얼 플랜 정책 할당'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Assign a per-user dial plan policy
ms:assetid: 9fea861f-7770-4cae-9b1f-2a960595bfc9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688156(v=OCS.15)
ms:contentKeyID: 49733760
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e7f9bca09515daba6db7e072625d5b4a217d37cd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982331"
---
# <a name="assign-a-per-user-dial-plan-policy-in-lync-server-2013"></a>Lync Server 2013에서 사용자 단위 다이얼 플랜 정책 할당

 


Enterprise Voice 사용자 또는 전화 접속 회의 사용자에 대 한 사용자 계정 구성을 완료 하려면 사용자에 게 다이얼 플랜을 할당 해야 합니다. 사용자 계정에 글로벌 다이얼 플랜 (있는 경우)이 자동으로 사용 되며, 기존 사용자 단위 다이얼 플랜을 명시적으로 할당 하지 않은 경우에도 사이트 수준 다이얼 플랜입니다. Enterprise Voice에 대해 설정 된 모든 사용자에 대해 전역 또는 사이트 다이얼 플랜을 사용 하려는 경우이 섹션을 건너뛸 수 있습니다.

## <a name="to-assign-a-dial-plan-by-using-the-lync-server-2013-control-panel"></a>Lync Server 2013 제어판을 사용 하 여 다이얼 플랜을 할당 하려면

1.  CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.

3.  왼쪽 탐색 모음에서 **사용자**를 클릭 합니다.

4.  **사용자 검색** 상자에 표시 이름, 성, 이름, SAM (보안 계정 관리자) 계정 이름, SIP 주소 또는 사용 하도록 설정할 사용자 계정의 URI (Uniform resource identifier) 중 일부 또는 전체를 입력 한 다음 **찾기를**클릭 합니다.

5.  테이블에서 다이얼 플랜을 할당할 사용자 계정을 클릭 합니다.

6.  **편집** 메뉴에서 **세부 정보 표시**를 클릭 합니다.

7.  **Lync Server 사용자 편집** 페이지의 **전화 통신**에서 **엔터프라이즈 음성을**클릭 합니다.

8.  **다이얼 플랜 정책을**클릭 한 다음 원하는 다이얼 플랜을 선택 합니다.

9.  **커밋**을 클릭합니다.

다이얼 플랜을 구성 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 다이얼 플랜 구성](lync-server-2013-configuring-dial-plans.md) 항목을 참조 하세요.

## <a name="assign-a-per-user-dial-plan-by-using-windows-powershell-cmdlets"></a>Windows PowerShell Cmdlet을 사용 하 여 사용자 단위 다이얼 플랜 할당

Windows PowerShell 및 **권한 부여-csdialplan** cmdlet을 사용 하 여 사용자 단위 다이얼 플랜을 할당할 수 있습니다. Lync Server 2013 관리 셸에서 또는 Windows PowerShell의 원격 세션에서이 cmdlet을 실행할 수 있습니다. 원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.

## <a name="to-assign-a-per-user-dial-plan-to-a-single-user"></a>사용자 당 다이얼 플랜을 단일 사용자에 게 할당 하려면

  - 다음 명령은 사용자 단위 다이얼 플랜 RedmondDialPlan을 사용자: 진구 Myer에 할당 합니다.
    
        Grant-CsDialPlan -Identity "Ken Myer" -PolicyName "RedmondDialPlan"

## <a name="to-assign-a-per-user-dial-plan-to-multiple-users"></a>사용자 단위 다이얼 플랜을 여러 사용자에 게 할당 하려면

  - 이 명령은 Redmond의 구/군/시를 사용 하는 모든 사용자에 게 사용자 단위 다이얼 플랜 RedmondDialPlan를 할당 합니다. 이 명령에 사용 되는 LdapFilter 매개 변수에 대 한 자세한 내용은 [Get CsUser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)) cmdlet에 대 한 설명서를 참조 하세요.
    
        Get-CsUser -LdapFilter "l=Redmond" | Grant-CsDialPlan -PolicyName "RedmondDialPlan"

## <a name="to-unassign-a-per-user-dial-plan"></a>사용자 단위 다이얼 플랜을 할당 취소 하려면

  - 다음 명령은: 진구 Myer에 이전에 할당 된 사용자 단위 다이얼 플랜을 할당 해제 합니다. 사용자 단위 다이얼 플랜의 할당을 해제 한 후에는 전역 다이얼 플랜, 해당 로컬 사이트 다이얼 플랜 (있는 경우) 또는 해당 레지스트라 또는 PSTN 게이트웨이에 지정 된 서비스 범위 다이얼 플랜을 사용 하 여: 진구 Myer가 자동으로 관리 됩니다. 서비스 범위 다이얼 플랜은 사이트 다이얼 플랜 보다 우선 하므로 사이트 다이얼 플랜은 전역 다이얼 플랜 보다 우선 합니다.
    
        Grant-CsDialPlan -Identity "Ken Myer" -PolicyName $Null

자세한 내용은 [CsDialPlan 플랜](https://technet.microsoft.com/en-us/library/gg398547\(v=ocs.15\)) cmdlet에 대 한 도움말 항목을 참조 하세요.

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 다이얼 플랜 구성](lync-server-2013-configuring-dial-plans.md)  
[Lync Server 2013에 대해 사용 하도록 설정 된 사용자 계정](lync-server-2013-user-accounts-enabled-for-lync-server.md)

