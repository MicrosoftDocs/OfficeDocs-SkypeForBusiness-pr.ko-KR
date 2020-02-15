---
title: 외부 사용자 액세스에 대 한 전역 정책 다시 설정
ms.reviewer: ''
ms:assetid: 8207e1b1-de9e-461f-975f-fcc5c526849a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182545(v=OCS.15)
ms:contentKeyID: 48184675
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 글로벌 정책은 완전히 삭제할 수 없습니다. 글로벌 정책에 대해 **삭제** 옵션을 사용하면 글로벌 정책이 기본 설정으로 다시 설정되기만 하여 외부 사용자 액세스 옵션에 대한 지원을 포함하지 않게 됩니다.
ms.openlocfilehash: acb275ac924dbb5b7e9ad377ab4d287a0734f752
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043660"
---
# <a name="reset-the-global-policy-for-external-user-access-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 외부 사용자 액세스에 대 한 전역 정책 다시 설정 

만들거나 구성한 외부 사용자 액세스 정책을 더 이상 사용하지 않으려면 다음을 수행할 수 있습니다.

  - 만든 사이트 또는 사용자 정책을 삭제합니다.

  - 글로벌 정책을 기본 설정으로 다시 설정합니다. 기본 글로벌 정책 설정은 외부 사용자 액세스를 거부합니다. 글로벌 정책은 삭제할 수 없습니다.

글로벌 정책은 완전히 삭제할 수 없습니다. 글로벌 정책에 대해 **삭제** 옵션을 사용하면 글로벌 정책이 기본 설정으로 다시 설정되기만 하여 외부 사용자 액세스 옵션에 대한 지원을 포함하지 않게 됩니다.

## <a name="to-reset-the-global-policy-to-the-default-settings"></a>글로벌 정책을 기본 설정으로 다시 설정하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 인 사용자 계정 (또는 이와 동등한 사용자 권한 포함) 또는 CsAdministrator 역할이 할당 되 면 내부 배포의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다.

3.  왼쪽 탐색 모음에서 **외부 사용자 액세스**를 클릭한 다음 **외부 액세스 정책**을 클릭합니다.

4.  **외부 액세스 정책** 탭에서 글로벌 정책, **편집**을 차례로 클릭한 다음 **삭제**를 클릭합니다.

5.  삭제를 확인하는 메시지가 표시되면 **확인**을 클릭합니다. 글로벌 정책이 다시 설정되었음을 알리는 메시지가 페이지 상단에 나타납니다.


## <a name="resetting-the-global-external-access-policy-by-using-windows-powershell-cmdlets"></a>Windows PowerShell Cmdlet을 사용 하 여 전역 외부 액세스 정책 다시 설정

Windows PowerShell 및 Get-csexternalaccesspolicy cmdlet을 사용 하 여 전역 외부 액세스 정책을 다시 설정할 수 있습니다. 이 cmdlet은 비즈니스용 Skype 서버 관리 셸 또는 원격 세션 Windows PowerShell에서 실행할 수 있습니다. 

## <a name="to-reset-the-global-external-access-policy"></a>전역 외부 액세스 정책을 다시 설정 하려면

  - 이 명령은 전역 외부 액세스 정책을 다시 설정합니다.
    
        Remove-CsExternalAccessPolicy -Identity "global"

자세한 내용은 [get-csexternalaccesspolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy) cmdlet에 대 한 도움말 항목을 참조 하십시오.


