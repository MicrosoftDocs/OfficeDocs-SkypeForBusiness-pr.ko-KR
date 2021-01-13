---
title: 외부 사용자 액세스에 대한 전역 정책 다시 설정
ms.reviewer: ''
ms:assetid: 8207e1b1-de9e-461f-975f-fcc5c526849a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182545(v=OCS.15)
ms:contentKeyID: 48184675
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 글로벌 정책은 완전히 삭제할 수 없습니다. 글로벌 정책에 대해 **삭제** 옵션을 사용하면 글로벌 정책이 기본 설정으로 다시 설정되기만 하여 외부 사용자 액세스 옵션에 대한 지원을 포함하지 않게 됩니다.
ms.openlocfilehash: be4f99c5b98ca46e7fed57781cf1661a2755a4ff
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817248"
---
# <a name="reset-the-global-policy-for-external-user-access-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 외부 사용자 액세스에 대한 글로벌 정책 다시 설정 

만들거나 구성한 외부 사용자 액세스 정책을 더 이상 사용하지 않으려면 다음을 수행할 수 있습니다.

  - 만든 사이트 또는 사용자 정책을 삭제합니다.

  - 글로벌 정책을 기본 설정으로 다시 설정합니다. 기본 글로벌 정책 설정은 외부 사용자 액세스를 거부합니다. 글로벌 정책은 삭제할 수 없습니다.

글로벌 정책은 완전히 삭제할 수 없습니다. 글로벌 정책에 대해 **삭제** 옵션을 사용하면 글로벌 정책이 기본 설정으로 다시 설정되기만 하여 외부 사용자 액세스 옵션에 대한 지원을 포함하지 않게 됩니다.

## <a name="to-reset-the-global-policy-to-the-default-settings"></a>글로벌 정책을 기본 설정으로 다시 설정하려면

1.  RTCUniversalServerAdmins 그룹의 구성원(또는 이와 동등한 사용자 권한)인 사용자 계정에서 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포의 컴퓨터에 로그온합니다.

2.  브라우저 창을 열고 관리 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다.

3.  왼쪽 탐색 모음에서 **외부 사용자 액세스** 를 클릭한 다음 **외부 액세스 정책** 을 클릭합니다.

4.  **외부 액세스 정책** 탭에서 글로벌 정책, **편집** 을 차례로 클릭한 다음 **삭제** 를 클릭합니다.

5.  삭제를 확인하는 메시지가 표시되면 **확인** 을 클릭합니다. 글로벌 정책이 다시 설정되었음을 알리는 메시지가 페이지 상단에 나타납니다.


## <a name="resetting-the-global-external-access-policy-by-using-windows-powershell-cmdlets"></a>cmdlet을 사용하여 전역 외부 액세스 Windows PowerShell 다시 설정

전역 외부 액세스 정책은 전역 Windows PowerShell cmdlet을 사용하여 Remove-CsExternalAccessPolicy 있습니다. 이 cmdlet은 비즈니스용 Skype 서버 관리 셸 또는 원격 세션 셸에서 실행할 수 Windows PowerShell. 

## <a name="to-reset-the-global-external-access-policy"></a>전역 외부 액세스 정책을 다시 설정하는 경우

  - 이 명령은 전역 외부 액세스 정책을 다시 설정합니다.
    
        Remove-CsExternalAccessPolicy -Identity "global"

자세한 내용은 [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy) cmdlet에 대한 도움말 항목을 참조하십시오.


