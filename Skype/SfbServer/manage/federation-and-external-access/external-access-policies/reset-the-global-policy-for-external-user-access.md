---
title: 외부 사용자 액세스에 대한 전역 정책 다시 설정
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
localization_priority: Normal
description: 전역 정책은 완전히 삭제할 수 없습니다. 전역 정책에 대해 **Delete** 옵션을 사용 하면 전역 정책만 기본 설정으로 재설정 되며,이는 외부 사용자 액세스 옵션에 대 한 지원을 포함 하지 않습니다.
ms.openlocfilehash: 339ad22e1d049510416bfc3433c6c8a104455504
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188802"
---
# <a name="reset-the-global-policy-for-external-user-access-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 외부 사용자 액세스에 대 한 글로벌 정책 다시 설정 

더 이상 사용 하지 않을 외부 사용자 액세스 정책을 만들거나 구성한 경우 다음을 수행할 수 있습니다.

  - 만든 사이트 또는 사용자 정책을 삭제 합니다.

  - 전역 정책을 기본 설정으로 다시 설정 합니다. 기본 전역 정책 설정에서는 외부 사용자 액세스를 거부 합니다. 전역 정책은 삭제할 수 없습니다.

전역 정책은 완전히 삭제할 수 없습니다. 전역 정책에 대해 **Delete** 옵션을 사용 하면 전역 정책만 기본 설정으로 재설정 되며,이는 외부 사용자 액세스 옵션에 대 한 지원을 포함 하지 않습니다.

## <a name="to-reset-the-global-policy-to-the-default-settings"></a>전역 정책을 기본 설정으로 다시 설정 하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다.

3.  왼쪽 탐색 모음에서 **외부 사용자 액세스**를 클릭 하 고 **외부 액세스 정책을**클릭 합니다.

4.  **외부 액세스 정책** 탭에서 전역 정책을 클릭 하 고 **편집**을 클릭 한 다음 **삭제**를 클릭 합니다.

5.  삭제를 확인 하는 메시지가 표시 되 면 **확인**을 클릭 합니다. 전역 정책이 재설정 되었음을 알리는 메시지가 페이지 맨 위에 표시 됩니다.


## <a name="resetting-the-global-external-access-policy-by-using-windows-powershell-cmdlets"></a>Windows PowerShell Cmdlet을 사용 하 여 전역 외부 액세스 정책 다시 설정

전역 외부 액세스 정책은 Windows PowerShell 및 CsExternalAccessPolicy cmdlet을 사용 하 여 다시 설정할 수 있습니다. 이 cmdlet은 비즈니스용 Skype 서버 관리 셸에서 또는 원격 세션 Windows PowerShell에서 실행할 수 있습니다. 

## <a name="to-reset-the-global-external-access-policy"></a>전역 외부 액세스 정책을 다시 설정 하려면 다음을 실행 합니다.

  - 이 명령은 글로벌 외부 액세스 정책을 다시 설정 합니다.
    
        Remove-CsExternalAccessPolicy -Identity "global"

자세한 내용은 [제거 CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy) cmdlet에 대 한 도움말 항목을 참조 하세요.


