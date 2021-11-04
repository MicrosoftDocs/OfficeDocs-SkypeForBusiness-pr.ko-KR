---
title: 외부 사용자 액세스에 대한 전역 정책 다시 설정
ms.reviewer: ''
ms:assetid: 8207e1b1-de9e-461f-975f-fcc5c526849a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182545(v=OCS.15)
ms:contentKeyID: 48184675
mtps_version: v=OCS.15
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 전역 정책은 완전히 삭제할 수 없습니다. 전역 **정책에서 삭제** 옵션을 사용하면 전역 정책만 기본 설정으로 다시 설정되고, 외부 사용자 액세스 옵션에 대한 지원은 포함하지 않습니다.
ms.openlocfilehash: b3748ee6a2e8bcfde9cec58a45db48f73bbabcc3
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60765436"
---
# <a name="reset-the-global-policy-for-external-user-access-in-skype-for-business-server"></a>2013에서 외부 사용자 액세스에 대한 글로벌 정책을 비즈니스용 Skype 서버 

더 이상 사용하지 못하도록 외부 사용자 액세스 정책을 만들거나 구성한 경우 다음 방법을 사용할 수 있습니다.

  - 만든 사이트 또는 사용자 정책을 삭제합니다.

  - 글로벌 정책을 기본 설정으로 다시 설정합니다. 기본 글로벌 정책 설정은 외부 사용자 액세스를 거부합니다. 전역 정책은 삭제할 수 없습니다.

전역 정책은 완전히 삭제할 수 없습니다. 전역 **정책의** 삭제 옵션은 전역 정책만 기본 설정으로 다시 설정하고, 외부 사용자 액세스 옵션에 대한 지원은 포함하지 않습니다.

## <a name="to-reset-the-global-policy-to-the-default-settings"></a>글로벌 정책을 기본 설정으로 다시 설정하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 또는 이와 동등한 사용자 권한을 들이거나 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포의 컴퓨터에 로그온합니다.

2.  브라우저 창을 열고 관리 URL을 입력하여 관리 비즈니스용 Skype 서버 열 수 있습니다.

3.  왼쪽 탐색 모음에서 **외부 사용자 액세스** 를 클릭한 다음 **외부 액세스 정책** 을 클릭합니다.

4.  **외부 액세스 정책** 탭에서 글로벌 정책, **편집** 을 차례로 클릭한 다음 **삭제** 를 클릭합니다.

5.  삭제를 확인하는 메시지가 표시되면 **확인** 을 클릭합니다. 글로벌 정책이 다시 설정되었음을 알리는 메시지가 페이지 상단에 나타납니다.


## <a name="resetting-the-global-external-access-policy-by-using-windows-powershell-cmdlets"></a>Cmdlet을 사용하여 전역 외부 액세스 Windows PowerShell 다시 설정

전역 외부 액세스 정책은 전역 Windows PowerShell cmdlet을 사용하여 Remove-CsExternalAccessPolicy 있습니다. 이 cmdlet은 비즈니스용 Skype 서버 관리 셸 또는 원격 세션 세션에서 실행할 수 Windows PowerShell. 

## <a name="to-reset-the-global-external-access-policy"></a>전역 외부 액세스 정책을 다시 설정하는 경우

  - 이 명령은 전역 외부 액세스 정책을 다시 설정합니다.<br/><br/>Remove-CsExternalAccessPolicy -Identity "global"

자세한 내용은 [Remove-CsExternalAccessPolicy](/powershell/module/skype/Remove-CsExternalAccessPolicy) cmdlet에 대한 도움말 항목을 참조하십시오.
